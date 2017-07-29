# First Project

The goal of the this project is to create a turn based game in order to learn python, git, etc.  The project will increase in scope as it goes, but to start, all I want to do is create a simple command line game that will emulate a simple combat from a table top game.

## OrcSlayer Synopsis

We will need a *D20* (20 sided die) and a *D6*.  These will be created as functions.  We will use the *D20* to determine initiatives (who goes first, you or the orc).  Who ever goes first, roles the *D20* again to try to hit the opponent.  The result is compared to an Armor Class (AC) to determine a hit or a miss.  If it's a miss, the other opponent gets to roll to see if they hit.  If its a hit, roll the *D6* to determine damage.  The damage gets decremented from a pool of Hit Points (HP).  Play continues until the orc or the player reaches 0 HP.  Then it displays a win or lose output and you choose to play again or exit.

## OrcSlayer Code Description

- Create dice function that lets you choose a number of faces on the die
- Create a brief print to screen for player something to the effect of
```
"You are walking through the forest and you come across an orc.  All you have on you is a stick.  He's coming right at you! Roll initiative!"
```
- Use a 20 sided die rolled once for the player, once for the orc.  (will need input from player to roll their initiative)
    - If player goes, start **Player Turn**
    - If Orc goes, start **Orc Turn**

    - **Player Turn** prompts the player to roll the D20 to beat he orcs armor class and does damage to the Orc if player hits. 
        - If player beats the Orc AC, prompt player to roll D6
            - subtract D6 roll from HP of Orc
            - Print to screen letting player know how many damage points they did (maybe damage vs total for initial game...then replace with discription of orc based on % of damage done)
            - If Orc HP = 0, game is over; print 
            ```
            "The Orc has been slain! You win! play again?"
            ```
        - If player does not beat the Orc AC, player misses.
            - Print 
            ```
            "You missed!, Its the Orcs turn now"
            ```
        - **Orc Turn** starts
    - **Orc Turn** calculates roll and damage and displays both to user without prompting player for any input
        - Call the D20 to determine if the orc beats the players AC
            - If orc beats the AC, roll D6 to determine damage
                - subtract D6 roll from HP of player
                - Print to screen letting player know they've been hit and how many damage points they lost
                - If Player HP = 0, game is over; print
                ```
                "The Orc has killed you and is feasting on your flesh.  C'est damage.  Play again?"
                ```
            - If orc does not beat the Player AC, orc misses
                - Print
                ```
                "The Orc missed! now it's your turn!  get him!"
                ```
            - **Player Turn** starts
    

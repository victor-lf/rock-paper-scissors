# rock-paper-scissors

This is a simple Rock Paper Scissors game written in JavaScript and played against the computer. The player plays a 5 round game that keeps score and reports whether the player wins or loses at the end.  
It consists of three functions:

- `computerPlay()`
- `playRound()`
- `game()`

`computerPlay()` is used to make the computer's play. It randomly returns 'Rock', 'Paper' or 'Scissors'. This is achieved using an array with the options and the `Math.random()` and `Math.floor()` methods. 
`Math.random()` returns a floating-point pseudo-random number between 0 and 1 (1 excluded), which we scale by 3, using the result as input for `Math.floor()`. This will generate 0, 1 or 2, randomly. We assign this value to a variable called `random`, using it as an index number to access an element of the array with the options, returning the element.

`playRound()` is used to play a single round. It takes two parameters - `playerSelection` and `computerSelection` - and returns a string that declares the winner of the round or throws an error if the player chooses an invalid option. 
The `toLowerCase()` method is used in `playerSelection`, and its first letter is capitalized. So, no matter what the player enters (rock, Rock, rocK, etc), it will always be with the first letter capitalized so that the comparisons that follow work.

`game()` is used to play a 5 round game. A **for loop** is used to play the 5 rounds. In each iteration, the player enters the choice via the `prompt()` method, and this choice is stored in the variable `playerSelection`. The `computerPlay()` function is called, storing the computer choice in the `computerSelection` variable. The `playRound()` function is then called with `playerSelection` and `computerSelection` as arguments, storing the returned string in the `roundResult` variable.  
Then, **conditional statements (if, else if)** are used to give the player or the computer a score based on the content of `roundResult` (using the `includes()` method). No one scores in case of a draw.  
`console.log()` is used to inform the round number, the computer choice and the round result.  
After the loop ends, a string is stored in the variable `message`. This string depends on the result of the game. If the player score is greater than the computer score, the string is 'You win!'. If the player score is less than the computer score, the string is 'You lose!'. Otherwise, the string is 'Draw!'. This is achieved using the **conditional (ternary) operator '?'**. We could use **if...else** statements, but as this is only a variable assignment that depends on some conditions, it's much shorter and simpler to use the ternary operator.  
Then, the `game()` function returns a string with the player score, the computer score, and the value inside 'message'.

---

From The Odin Project's [curriculum](https://www.theodinproject.com/courses/web-development-101/lessons/rock-paper-scissors).

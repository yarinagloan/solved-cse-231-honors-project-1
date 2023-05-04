Download Link: https://assignmentchef.com/product/solved-cse-231-honors-project-1
<br>
<h2>Assignment Overview</h2>

<h2>Overview</h2>

Write a program that plays the game dots-and-boxes: <a href="https://en.wikipedia.org/wiki/Dots_and_Boxes">https://en.wikipedia.org/wiki/Dots_and_Boxes</a> and record some statistics about using a player who plays “randomly” i.e., a player who has no strategy except random play (to be described below). This version will focus on scoring play and getting RandomPlayer to play the game. The game should work for any dimensions (hint hint).

<h2>Play</h2>

The scoring is pretty well explained in the link above, but let’s review:

<ul>

 <li>During a player’s turn, they must draw a line that connects two dots o They <strong><em><u>must</u></em></strong> play, they must draw a line, during their turn if a move is available.</li>

 <li>Result of the line drawing:</li>

</ul>

o If drawing a line results in a box, that is a square is produced in the grid, then that player adds one to their score and can play again

<ul>

 <li>The square is typically marked on the grid for that player o If no box is created, the turn ends and the next player plays.</li>

 <li>Game ends when no more lines can be placed, that is all the lines have been played o Player with the most boxes wins</li>

</ul>




<h2>More details on play</h2>

The grid will be represented by ASCII characters on the terminal. A typical look below:













Some details:

<ul>

 <li>If a player wins a box, it gets labeled. To keep things simple the two players are always named ‘A’ and ‘B’.

  <ul>

   <li>Who goes first is very important. You should flip a “dice” (generate a random number) and decide who goes first.</li>

  </ul></li>

 <li>A move is a pair of integers. For example, as player A I made a move 4 5 (two space separated integers) which would draw that line. That’s a box, so when the grid is redrawn the square is filled in with A, and I get another turn using the updated grid. o You must prevent a user from redoing a move, so 2 6 would be illegal o Note an alternate naming of that same move would 5 4 and that would also be a legal move</li>

 <li>Your program should:

  <ul>

   <li>Keep score and update it after every turn o Allow for extra moves when a box is drawn o Know when the game is over and report the results.</li>

  </ul></li>

</ul>

<strong> </strong>

<h2>Data Structures</h2>

Come up with your own data structures. Things you will likely need:

<ul>

 <li>A way to represent the grid o In that data structure, who drew what lines</li>

 <li>A way to keep score</li>

</ul>




<h2>Functions or Classes</h2>

I don’t want to restrict you too much, but I do want readable code! You should be using functions or classes or you may not get credit. Some good functions (as suggestions):




<ul>

 <li>draw_board: takes in your representation of moves and draws the board</li>

 <li>check_for_box: takes in your representation of moves and determines, did that move just made make a box?</li>

 <li>score: takes in score representation, perhaps using check_for_box, updating scores.</li>

</ul>




<h2>Random player</h2>

We are not going for automated strategy here nor are we going for human interaction. In the second round we are going to be making players that play the game well, but for now we are going to make a random player function called random_play

<ul>

 <li>random_play: random_play could just keep picking until it finds a legal move but that is going to get to be painful. Instead, provide some information on available legal moves (state of the grid, something) and have it return a legal move. It selects its move using a random number generator, selecting from the available moves.</li>

</ul>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<h2>Main Program</h2>

You are going to use your random_play function to play dots-and-boxes. Your main program will operate in two modes:

<ul>

 <li><u>single play</u>: with two random_player players A and B, it is going to generate a fully detailed game, drawing grids, keeping score and showing in great detail the progress of the game.</li>

 <li><u>multiple play</u>: it will then play a lot of random games with two random_play players, however it will be reporting <strong><em>only</em></strong> statistics on how the two players did.</li>

</ul>




<h2>More detail</h2>

<ul>

 <li>prompt for grid size</li>

 <li>prompt for a random seed integer</li>

 <li>prompt for a number of rounds the multi-player (shown below) will play</li>

 <li>“flip a coin” to see who goes first and report it</li>

 <li>your program will then play one round using two random_play players and report each individual play, stored in a file called “single_play.txt” to be created in the same directory as the project.

  <ul>

   <li>For each turn:

    <ul>

     <li>draw the grid</li>

     <li>the score</li>

     <li>whose move it is</li>

     <li>what move was made</li>

     <li>was that a box just made, did they go again</li>

     <li>anything else that might be useful</li>

    </ul></li>

   <li>it then will play the provided number of rounds using two random_play players and report statistics of the results to a file called</li>

  </ul></li>

</ul>

“multiple_play.txt”. The statistics to include are:

<ul>

 <li>the number of rounds played o average score overall and for each player o the median score overall and for each player o the highest and lowest score achieved for each player o anything else you think might be a good idea</li>

</ul>




<h2>Deliverables</h2>

The deliverable for this assignment is the following files:




honors1.py – the source code for your Python program single_play.txt– the text file reporting each individual play  multiple_play.txt– the text file reporting the statistics of all the rounds Be sure to use the specified file names and to submit it via the <strong>Mimir</strong> <strong>system</strong> before the project deadline. No automatic tests will be posted in Mimir. The grading will be done manually.




<strong>Requirements </strong>

Your code must adhere to the entire Coding Standard.

<h2>Notes</h2>

<ul>

 <li>because these are two random players the statistics on multiple hands will be revealing. What would you expect to happen?</li>

 <li>you should be able to play thousands of games in multiple play to get some good stats.</li>

</ul>

o if it takes minutes to do that, you need to rethink it.

<ul>

 <li>drawing a line might result in two boxes.</li>

</ul>
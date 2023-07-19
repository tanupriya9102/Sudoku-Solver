# Operating Systems and System Processing Project
METHODOLOGY:
 This project consists of designing a multithreaded application that determines whether the solution to a Sudoku puzzle is valid.
.Our strategy is to create threads that check the following criteria:

      • A thread to check that each column contains the digits 1 through 9.

      • A thread to check that each row contains the digits 1 through 9.

      • 9 threads to check that each of the 3 × 3 subgrids contains the digits 1 through 9.

This would result in a total of eleven separate threads for validating a Sudoku puzzle. 
 I. Passing Parameters to Each Thread
The parent thread will create the worker threads, passing each worker the location that it must check in the Sudoku grid. 
This step will require passing several parameters to each thread. The easiest approach is to create a data structure using a struct.

 II. Returning Results to the Parent Thread

  Each worker thread is assigned the task of determining the validity of a particular region of the Sudoku puzzle. Once a worker has performed this check, it must pass its results back to the parent. One good way to handle this is to create an array of integer values that is visible to each thread. The i th index in this array corresponds to the i th worker thread. If a worker sets its corresponding value to 1, it is indicating that its region of the Sudoku puzzle is valid. A value of 0 indicates otherwise. When all worker threads have completed, the parent thread checks each entry in the result array to determine if the Sudoku puzzle is valid.


REQUIREMENTS:
C LANGUAGE
THREADS

# PA-09

TreeCompare
Problem Context

Similar to Programming Assignment 3 (Sort Compare), computer scientists sometimes implement additional methods and functionality within existing objects to generate metrics for comparison. Since a BST and an AVL Tree are quite similar (one rebalances after insert/removal, the other does not), writing out separate classes for both would not be good code style, as a lot of code is the same. To enable sharing code across BST and AVL Tree implementations, you will implement a TreeCompare class that allows the user to use one class for both kinds of trees. 

More specifically, you are provided a working AVL Tree implementation (renamed to TreeCompare), and will need to add the following functionality:

When initializing a TreeCompare, give the option to specify whether a regular BST or an AVL Tree is created

We will do this by passing a boolean AVL into the __init__() method. AVL  is True to create an AVL Tree, False to create a regular BST.

When inserting to a TreeCompare, rebalancing should only happen if the tree is an AVL Tree

You will also implement additional methods that will help compare the state of a BST and AVL Tree after insertions:

height(): Returns the height of the tree. The height of an AVL Tree should be the same or shorter than the equivalent BST, depending on order of insertions.

range(): Returns the largest value in the tree minus the smallest value in the tree. Note that the range should be the same across regular BSTs and AVL Trees.

nodes_at_level(): Returns a list of the values of the nodes at a specified level, using in-order traversal order.

sum_leaves(): Returns the sum of all leaf nodes in the tree.

left_view(): Returns the list of the values of the left-most nodes at each level, in order of increasing level.

Input

The program input file will include 2 lines: the first line will be a list of numbers to be added to the tree, and the second line will indicate the level with which to call nodes_at_level().

See tree.in for a sample input.

Output

Compare your output with the sample output file provided in tree.out.

Let's walk through a more detailed example. If you were to uncomment Line 28 in main.py the output for calling AVLtree.print() would be as follows:

         -> 98
      -> 98
         -> 90
   -> 77
         -> 72
      -> 71
-> 70
         -> 67
      -> 50
   -> 46
         -> 32
      -> 10
         -> 5

Notice how the root node has value 70. Its left child has value 46, and its right child has value 77. This structure is repeated for the rest of the tree. Use the output to check if the tree structure matches what you would expect. Then, you can also use this output to check the associated calls to the new methods

Tree height: 3                                # 3 nodes from root to leaf
Tree range: 93                                # Largest value is 98, smallest value is 5, range is the same
Values at level  3  : [5, 32, 67, 72, 90, 98] # Level 3 happens to contain all the leaves for this case
Sum of leaf nodes: 364
Tree left side view: [70, 46, 10, 5]          # The left-most nodes correspond with the bottom nodes from the print()
Starter Code

The starter code includes a complete main() method. We have also provided a helper print() method for you to print the state of the tree. Make sure to remove calls to the print() method before submitting.

Notice how the main method includes a debug flag. When set to True, notice how your program will use the tree.in file as the input, which you can use to write custom test cases. When set to False, the program will use stdin. Make sure to set debug to False when submitting as the grading scripts will pass inputs through stdin.

Take note of the code style used in the starter file. We will apply a similar rubric (see below) when manually assessing code style.

Recommended Approach

We recommend implementing your program incrementally, following the order described below and testing each method as they are written:

Trace the insertions provided in tree.in for a BST then for an AVL Tree.

Make sure you understand if/when rotations are called, and what the resulting tree should look like

From the manual trace, calculate the values that should be returned from calling the additional methods.

Add the AVL boolean flag to the TreeCompare class.

Read through the TreeCompare implementation. Which lines should execute when AVL=False? Which lines should execute when AVL=True?

Implement the height() method, and compare results with your manual trace.

Implement the range() method, and compare results with your manual trace.

Where is the largest value in the tree located? Where is the smallest value in the tree located?

Implement the nodes_at_level() method, and compare results with your manual trace.

Does recursion or iteration make more sense here? Do you need a helper method?

Implement the sum_leaves() method, and compare results with your manual trace.

Does recursion or iteration make more sense here? Do you need a helper method?

Implement the left_view() method, and compare results with your manual trace.

Does recursion or iteration make more sense here? Do you need a helper method?

Grading

Grading scripts (automated): 70/100 points. The test cases will test your code against different input orders and different lengths of input.

Code review: 30/100 points. TAs will complete a manual code review for each assignment, similar to how a Team Lead would complete a code review in a professional setting. TAs will also complete a technical requirements review in addition to a code style review.

Please refer to the following code style guidelines for this assignment: 15/100 points

Readability: Descriptive variable and method names, no unused code, no commented out code, and proper indentation.

Documentation: One comment per added/modified method describing the input, output, and purpose of the function. Optional additional comments describing high level purpose of each step within a method.

Organization: Lines of code are less than 100 characters long, methods have one primary purpose, logical structure to approach.

Please refer to the following technical requirements for this assignment: 15/100 points

TreeCompare supports BST and AVLTree implementations in the same class.

Each additional method is implemented as described (e.g., no hardcoding).

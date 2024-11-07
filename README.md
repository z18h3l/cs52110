java c
CSCI 1133, Fall 2024 
Homework 09 
Due:  6:00 pm, Tuesday, November 5, 2024 
Purpose: The primary purpose of this assignment is to get practice reading and writing from files.
Instructions: This assignment consists of 4 problems, worth a total of 30 points.
Because your homework file is submitted and tested electronically, the following are very important:
●   Submit the file called hw09.py to the Homework 09 submission link on Gradescope by the due date deadline.  You don’t need to submit the sample files.
● Your program should run without errors when we execute it using Python 3.
The following will result in a score reduction equal to a percentage of the total possible points:
● Bad coding style. (missing documentation, meaningless variable names, etc.) (up to 20%)
● Breaking constraints (up to 40%)
A note on break: While the break keyword can be a useful tool forgetting out of loops early, it tends to be misused by intro students to get out of writing a proper loop condition. So for the purposes of this class, the break keyword is considered bad style. and will lose you points.
Documentation: 
Use the following template for EVERY function that you write.  The docstring below should be placed inside of the function, just after the function signature.
'''
Purpose:
Parameter(s):
Return Value:
'''
Download the hw09files.zip archive from Canvas, and extract the files somewhere you can easily find them.  You’ll want all the files to be present in whatever directory   you’rerunning Python from.  Create a file called hw09.py in the same directory as all  the test files.
Problem A. (5 points) Total Hours The employees at Holistic Synergies, Ltd. submit their timesheets indicating how many hours they’ve worked each day over the past week as a text document containing 7 integers, one per line.  For example, the contents of employee1.txt:
0
5
2
8
7
8
0
would indicate an employee that worked 0 hours on Sunday, 5 on Monday, 2 on Tuesday, 8 on Wednesday, 7 on Thursday, 8 on Friday, and 0 on Saturday.  Employees are required to work shifts that are in increments of full hours, so you’ll never see a decimal value present in the timesheet.
We want to compute the total hours for a given week; in the above example, that would be 0+5+2+8+7+8+0 = 30.
Write a function total_hours(filename) that takes in one parameter, filename, which should be a string representing the name of a file that contains an employee’s hours worked, formatted as described above.
●   The function should return the total amount of hours the employee worked.
You can assume for this problem that the specified file does exist in the directory you’rerunning Python from: no need for a try-except block to avoid FileNotFound errors.
Hints: 
● Remember to close any files you open.
●   The information from each line will always be read in as a string, even if it consists only of digits.  Use the int() function before adding it to your total.
Examples: (assumes that the files in the hw09files.zip archive are in the same directory you’re running Python from):
if   name  == '  main  ':
print(total_hours('employee1.txt')) #30
print(total_hours('employee2.txt')) #22
print(total_hours('employee3.txt')) #40
Problem B. (7 points) Adding Day Names 
To make the timesheets easier to read, HR has decided to require that employees resubmit all timesheets so that each line contains the day of the week, followed by a colon and a space, and then the number of hours worked.
The name of the new file should be the same as the old file, but with ‘labeled_ ’ concatenated to the beginning.  So if we ran the function on the employee1.txt file:
0
5
2
8
7
8
0
the resulting labeled_employee1.txt file would look like this:
Sunday: 0
Monday: 5
Tuesday: 2
Wednesday: 8 Thursday: 7
Friday: 8
Saturday: 0
Write a function label_days(filename) that takes in one parameter, filename, which should be a string representing the name of a file that contains an employee’s hours worked, formatted as described above.
●   The function should create a new file which has the same name as the original, but with 'labeled_' concatenated to the beginning.
●   The new file should have the same numbers on each line, but each number
should be preceded by the day of the week (starting with Sun代 写CSCI 1133, Fall 2024 Homework 09Python
代做程序编程语言day), then a colon, then a space.
●   This function should not return anything.
You can assume for this problem that the specified file does exist in the directory you’rerunning Python from: no need for a try-except block to avoid FileNotFound errors.
Hints: 
● Remember to close any files you open.
Examples: 
For this problem, we’re not checking the return value (which is why there’s no expected output for any of the test cases below).  You must instead produce the correct output file for each test.
Inside ofhw09files.zip we’ve included three test files: employee1.txt, employee2.txt, and employee3.txt.
●   For each test file employeeX.txt, we’ve also included a file with a name of the form. correct_labeled_employeeX.txt, which is what the corresponding
labeled_employeeX.txt should look like.
if   name  == '  main  ':
label_days('employee1.txt')
label_days('employee2.txt')
label_days('employee3.txt')
Problem C. (9 points) Stretching a 3D Model 
In computer graphics, 3D objects are stored in files that are meant to be loaded anddisplayed on the screen.  Although multiple file formats exist for 3D models, OBJ is one of the most commonly used.  These files are plain text ending in .obj that contain the following:
1)  A list of vertices that specifies the x,y,z coordinates of each point in 3D space
2)  A list of faces, each of which specifies the index number of three points that form. a triangle
Each vertex is listed on one line, and begins with the letter v.  The x, y, and z coordinates are included next, separated by spaces.  After all the vertices are done, each face is then listed on one line beginning with the letter f.  The three index numbers are included next, starting with 1, also  separated by spaces.  For example, this OBJ file contains a single triangle and would be displayed as follows:
Write a function stretch_model(fname_in, fname_out) that reads all the vertices and faces in the OBJ file specified by the string fname_in.  The function should then transform. the vertices to stretch the model by a factor of 2 along the y-axis, and then save the transformed vertices and faces to a file specified by the string fname_out.  This function should return the total number of vertices in the file.
If the specified file fname_in does not exist, stretch_model should instead return -1.
To stretch the model along the y-axis, the y-coordinate for each vertex should be multiplied by 2. The x and z coordinates should not be affected.
So, for the example given above, the output file would look like this (note that due to the OBJ model viewer automatically adjusting the boundaries, the image looks shortened rather than stretched):

You can use the example OBJ files in hw09files.zip on Canvas to test your function.  Verify that your output looks correct using this online viewer: https://3dviewer.net/  .
Hints: 
●   You only need to alter the vertex lines (the ones starting with ‘v’); the lines starting with ‘f’ can just be copied directly from the input file into the output file.
●   If you want to see text contents of an OBJ file rather than the 3D model, be sure to open the file with a text editor (like VS Code) and not something like 3D Model Viewer.
● You can convert a line from the OBJ file into a list with the statement
listName = stringName.split(' ').  Using a space as a delimiter rather than leaving it blank will ensure that you don’t lose the newline character at the end.
●   You can convert this list back into a string with the statement stringName = ' '.join(listName).
Constraints: 
● All files must be properly opened and closed.
●   You must use a try-except block to prevent a FileNotFoundError in the case that the given file does not exist.
Note: For this problem getting the correct return value is not sufficient: you must also match the expected output file.  See the sample output files in your hw09files.zipfolder to see what each    should look like.
Examples (assumes that missing.obj does not exist within your current directory):
if   name  == '  main  ':
print(stretch_model('missing.obj', 'doesntmatter.obj')) #-1
print(stretch_model('triforce.obj', 'triforce_stretched.obj')) #9
print(stretch_model('teapot.obj', 'tall_teapot.obj')) #3644
Example Screenshots: (using https://3dviewer.net/)




         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com

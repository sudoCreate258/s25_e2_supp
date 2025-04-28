# Exam2 Supplemental Assignment
## TLDR
Refactor an existing Java program to utilize heaps, i.e., priority queues.
### Programming Language 
You are required to program using Java. 
### Version Control Usage
Utilize github to store your code and provide a helpful description for each commit message.
### Compilation Method 
Compilation: Your code should compile on vsphere, online gdb, or whatever IDE you utilize 
### Policy on sharing of code 
EVERY line of code that you submit in this assignment should be written by you. Do NOT show your code to any other student. Do not copy any code from any online source. Code for File I/O or String operations, if found online, should be clearly cited, and you cannot use more than 5 lines of such online code. Code snippets, if used from an online source should be cited by mentioning it in the README.md and also in the documentation of every source file in which that code appears. Post to the BrightSpace discussion if you have any questions about the requirements. Do NOT post your code asking for help with debugging. 
### Team Work 
No team work is allowed. Work individually. You cannot discuss the 
assignment with ANYONE other than the instructor and discussion board. 

## Project Description 
### Assignment Goal: Refactor a program to efficiently accumulate attendance and handle excused absences. 

(1) Read through the attendance file. For each line create a Day object such that each object contains the date and array of students for that day. Add each day object to a priority queue based on the number of students for that day. (SEE [split()]([url](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#split-java.lang.String-)))

(2) Next, loop through the array of students in the priority queue. Then, create a Student object such that each has a name, number of classes attended, and explanations. Utilize the student name as the key and the student object as the value and place this pair in a hash map. For students in the hash map increment the value, otherwise add them to the hash map.

(3) Next, read the reason file to update the hash map using the name as the key. Then, update the student object value by 1 day and concatenate the explanations with the respective date.

(4) Finally, loop through the hash map and write the studdent data to a third file with each separated student separated by commas. 

## INPUT FORMAT (attendance_file.txt)
```
<date> <student_0>, <student_1>, <student_2>, ..., <student_n>
```
### INPUT EXAMPLES 
```
1/21 John Doe, Jane Doe, Jason X, Dr. J
1/23 Jane Doe, George W, Jackson A, Axel Rhodes
```

## INPUT FORMAT (reason_file.txt)
```
<dateY> <student_0>, <reason_1>
<dateY> <student_1>, <reason_3>
<dateZ> <student_0>, <reason_1>
```
### INPUT EXAMPLES (absense_sheet.txt)
```
1/21 John Doe, “Called out to military service”
1/23 Jane Doe, “Job Interview”
1/25 John Doe, “Sickness”
```

### OUTPUT FORMAT (attendance_book.csv)
Your program should write to an output file called 
```
<student_0>,<classes_attended>,<explanations> 
<student_1>,<classes_attended>,<explanations> 
<student_2>,<classes_attended>,<explanations> 
```
## OUTPUT EXAMPLES 
```
John Doe, 23, “Called out to military service (1/21), Sickness (1/25)”
Jane Doe, 23, “Job Interview (1/23)”
```

## NOTES ON GRADING 
Extra points will be given to students who post interesting sample input files: see BrightSpace discussion
Create a README (MD) file which should have the following information: 
```
(1) instructions on how to compile the code 
(2) instructions on how to run the code 
(3) justification for the choice of data structures (in terms of time and/or space complexity). 
(4) citations for code referenced online
```

### Submission 
```
Upload your assignment as a zipped folder to BrightSpace
In the submission comments provide your github username and hash code [(how?](https://docs.google.com/presentation/d/1TpamPnZ4kqU4pYk86vwq_uqyRJUnHFUXsdNEobfmi7w/edit?usp=sharing)).
Example:  userName123 - 96905470a5a3bc23293ffd5a003350138a1ce8c6
```

## General Requirements 
```
(1) Separate out code appropriately into methods, one for each purpose. 
(2) You should document your code. The comments should not exceed 72 columns in width. 
(3) Use javadoc style comments if you are coding in Java. Include javadoc style documentation. It is acceptable for this assignment to just have the return type described for each method's documentation. 
(4) All objects, in Java, that may be needed for debugging purposes should  have the "toString()" method defined. By default, just place a toString() in every class. 
(5) Every class that has data members, should have corresponding accessors and mutators (unless the data member(s) is/are for use just within the method.).
```

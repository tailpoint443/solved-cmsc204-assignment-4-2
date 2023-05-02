Download Link: https://assignmentchef.com/product/solved-cmsc204-assignment-4-2
<br>
Most data is stored in databases, for ready access and organization.  Our course data is backed up by IT in databases which makes our data easy to access and use.

Write a program that creates a database of courses.  It will either read from a file of courses, or allow the user to add one course at a time.   Upload the initial files and your working files in the repository in GitHub you created in Lab 1, in a directory named Assignment4. Take a screenshot of your repo, and post the assignment to the Assignment 4 dropbox.

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Concepts tested by this assignment</strong></td>

  </tr>

 </tbody>

</table>

Hash Table,

Link List,

hash code, buckets/chaining,

exception handling,

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Classes</strong></td>

  </tr>

 </tbody>

</table>

read/write files using FileChooser

<strong>Data Element – </strong>CourseDBElement,

CourseDBElement implements Comparable, and consists of five attributes: the Course ID (a String), the CRN (an int), the number of credits (an int), the room number (a String), and the instructor name (a String).   Normally the CourseDBElement will be an object consisting of these five attributes, and is referred to as a CDE.

<strong>Data Structure – </strong>CourseDBStructure

Implements the CourseDBStructureInterface that is provided.

You will be implementing a hash table with buckets.  It will be an array of linked lists of CourseDBElements.  Each CDE will have a hash code that comes from the CRN, since the CRN is unique for courses.  Note that the CRN is an int, and the tests require the hashcode of a string, so you will need to coerce it to a String, and take the hash code of the resulting string.  The add method will take a CourseDBElement and add it to the data structure. If a linked list at the relevant hash code doesn’t exist, create a LinkedList with the first element being the CDE and add it to the HashTable. If the LinkedList already exists, add the CDE to the existing list. Two constructors for the CDS will be required, one that takes in an integer that is the estimated number of courses, the other is used for testing purposes.  The comments in the CourseDBStructureInterface (provided) should help you figure out how to set the length of the hash table.  You will not need to use the 4k+3 code.

<strong>Data Manager – </strong>CourseDBManager

Implements the CourseDBManagerInterface that is provided.

The data manager allows the user to read the courses from a file or to enter the data by hand, and uses an Alert to print out the database elements. The input is read from a file or read from the textfields and is added to the data structure through the add method.  The add method uses the CDS add method. The CourseDBManager is also referred to as a CDM.

<strong>Exception Classes</strong>

IOException – created and thrown when user selects an input file that cannot be read or attempting to retrieve a CDE that does not exist in the DB.

<strong>GUI Driver (provided)</strong>

<ul>

 <li>User will only create a course database once they have entered an input file or entered one or more sets of attributes.</li>

 <li>Buttons and textfields are grayed out if they are not relevant at the current time.</li>

 <li>A FileChooser is used to select the input and output files.</li>

 <li>Inform the user if there is an error with the input file.</li>

 <li>Use exception handling for the validity of the files.</li>

 <li>A way is provided for the user to “clear” the text fields.</li>

 <li>A way is provided for the user to select a CRN and retrieve the corresponding course.</li>

</ul>

<strong>Testing</strong>

Create a JUnit Test – CourseDBManager_STUDENT_Test.

There will be two ways to create a course database.  The first requires a document to be read from an input file.  The second reads the input from five textfields.  Once there is data in the database, the GetCourse button will be enabled to allow you to see the data. See the example below.

Example of creating a Course database from an input file

Select the input file button and navigate to the file.

Use ShowDB button to display the CDEs that were read:

Example of Creating a CDE from text fields.  First select the other radio button, then fill in the textfields, then select the “Add to DB” button.

Select the Show DB button to see the resulting CDEs

Example of retrieving a CDE.  First select the GetCourse button.  Three components at the bottom of the screen will become enabled.  Then fill in the CRN and select the FindCourse button to find the applicable course from the database.

The general design is shown here to guide you in formulating your own design:



For Declaring Array
	myarr=(one two three four five)
For Printing One Element 
	echo=${myarr[1]} ## This is will print two
For Printing All Elements
	echo=${myarr[*]} ## This will remove all Elements
For Removing Specific Element
	unset myarr[1] #This will remove the second element
For Removing All elements
	unset myarr    #This will remove all elements


echo "Hello $*" ### This will Print all Argument passed 
echo echo "You are using $(basename $0)" ### This will print the first name from the command which is fileName without space

-- Variable Scope
export name # The variable will be accessible to other processes

Few Important Commands:
read -p "May I ask your name: " name
echo "Hello $name"
read -sn1 -p "Press any key to continue"
echo

exit 0 ## what does this means

The types of command is listed as follows:
	• Alias
	• Function
	• Shell built in
	• Keyword
	• File

#!/bin/bash: Normally, this is always the first line of the script and is known as the shebang. 
The shebang starts with a comment but the system still uses this line. A comment in a shell script has the # symbol. 
The shebang instructs the system to the interpreter to execute the script. We use bash for shell scripts and 
we may use PHP or Perl for other scripts, as required. 
If we do not add this line, then the commands will be run within the current shell;it may cause issues if we run another shell.

exit 0: The exit command is a built in shell and is used to leave or exit the script. The exit code is supplied as an integer argument. 
A value of anything other than 0 will indicate some type of error in the script's execution.

Checking the exit status:
	$ command1 || command2 ##command2 will run if command1 fails that means exits with a status code other than 0.
	$ command1 && command2 ##execute command2 if command1 succeeds and issues an exit code of 0.

Ensuring a unique name:
	$ type hello1.sh #To determine the type and path
	$ type -a hello1.sh #To print all commands found if the name is NOT unique
	$ type -t hello1.sh ~To print the simple type of the command
	
Running the script with arguments:
	$0 The name of the script itself and is often used in usage statements.
	$1 Positional argument, the first argument passed to the script.
	${10} Where two or more digits are needed to represent the argument position. Brace brackets are used to delimit the variable name
		  from any other content. Single value digits are expected.
	$# Argument count is especially useful when we need to set the amount of arguments needed for correct script execution.
	$* Refers to all arguments.
	
If we want to suppress the new line, especially useful if we are to prompt users, we can do this in the following two ways with the help of echo:
	$ echo -n "Which directory do you want to use? "
	$ echo -e "Which directory do you want to use? \c"

If we use the -n option followed by an integer, we can specify the characters to accept before continuing, we will set 1 in this case.
	#!/bin/bash
	read -p "May I ask your name: " name
	echo "Hello $name"
	read -n1 -p "Press any key to exit"
	echo
	exit 0
	
In Above example code will exit with character will be shown on screen. If we want it to happen silently.
-s to achieve this



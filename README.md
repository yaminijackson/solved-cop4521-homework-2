Download Link: https://assignmentchef.com/product/solved-cop4521-homework-2
<br>
The objective for this assignment is to make sure

<ul>

 <li>You are familiar with native Python and Python syntax.</li>

 <li>You can write small programs that demonstrate Python’s capabilities.</li>

 <li>You can use Python to solve small problems.</li>

 <li>You are comfortable with Python’s Object Oriented Programming concepts.</li>

 <li>You can do some research on a particular problem and learn about its general background and then use Python to solve the problem. You will be expected to do this at any Software Engineering job, and it is good to practice while you’re still in school.</li>

</ul>

<h1>1           log decorator.py</h1>

Your goal is to create a decorator that extends a function with some logging statements. The logging decorator must be called log and must be defined in the module log decorator.py. The decorator may optionally take a single argument that indicates the file to which the statements should be appended. If no argument is provided, the statements are written to stdout. If the filename provided cannot be opened for whatever reason, logging should be directed to stdout. The logging decorator should extend the function by printing the following items:

<ul>

 <li>The name of the function being called. (Hint: Make use of the name attribute available on every function object).</li>

 <li>A list of the arguments supplied to the function as well as the type of the argument. If no arguments are supplied, you must report this. You might want to make use of name here as well!</li>

 <li>The output of the function.</li>

 <li>The execution time of the function (elapsed wall clock time) in seconds. The time should be rounded to 5 decimal places.</li>

 <li>The return value and the type of the return value. Note that even when multiple values are returned, the return value is a single tuple object. If there is no return value, you must report this.</li>

</ul>

To demonstrate the behavior of the log decorator, take a look at the following example log.py, which defines (but does not show!) the log decorator:

@log () def factorial (∗ num list ): results = [ ] for number in num list :

res = number

for    i           in range (number−1,0,−1):

res = i ∗res

results . append( res ) return    results @log(” logger . txt ”) def  waste time (a , b,              c ): print (”Wasting time .”) time . sleep (5)

return a , b,        c

@log(” logger . txt ”) def gcd(a , b ): print (”The GCD of ” , a , ”and” , b, ” is ” , end=””) while a!=b: i f a <em>&gt; </em>b:

<ul>

 <li>−= b else :</li>

 <li>−= a</li>

</ul>

print (abs(a)) return abs(a) @log () def     print hello ():

print (” Hello !”) @log(10) def print goodbye ():

print (”Goodbye !”) i f            name      == ”        main               ”: factorial (4 , 5) waste time (”one” , 2 , ”3”) gcd (15 ,9)

print hello () print goodbye ()

The results of executing this module are given below:

$ python log . py

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

Calling           function          factorial .

Arguments :

− 4 of type         int .

− 5 of type         int .

Output :

Execution time : 0.00002 s . Return value :                [24 ,        120]               of type   l i s t .

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

Calling           function         print hello .

No arguments .

Output :

Hello !

Execution time : 0.00002 s . No return value .

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗ ∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

Calling           function         print goodbye .

No arguments .

Output :

Goodbye !

Execution time : 0.00037 s . No return value .

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

$ more logger . txt

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

Calling           function        waste time .

Arguments :

− one of type               str .

− 2 of type            int . − 3 of type     str .

Output :

Wasting time .

Execution time : 5.00539 s . Return value :                ( ’one ’ , 2 ,            ’3 ’)         of type tuple .

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

Calling             function gcd .

Arguments :

− 15 of type              int .

− 9 of type              int .

Output :

The GCD of 15 and 9 is 3

Execution time : 0.00010 s . Return value : 3 of type               int .

∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗∗

<h1>2           oop.py</h1>

Define a student class. A student has the following attributes: firstname, lastname, gender which can be male or female, status which can be equal to freshman, sophomore, junior, and senior and gpa. Then define the following methods for the student class.

<ul>

 <li>The show myself method will simply print all the attribute variables when called upon the object. This method has no input arguments.</li>

 <li>The study time method will increment the gpa of the student according to the following formula: ‘ gpa = gpa + log(study time)’. The only input argument of this method is the variable study time. In addition make sure that the gpa variable never exceeds 4.0 even if the student studies for a very long time.</li>

</ul>

Create 5 student objects and store the objects in a list called student list. The five students are: Mike Barnes, Jim Nickerson, Jack Indabox, Jane Miller and Mary Scott. Mike is a freshman, Jim a sophomore, Jack a junior, Jane and Mary are seniors. Their respective GPAs are: 4, 3, 2.5, 3.6 and 2.7. Make sure you assign the gender when you instantiate the objects.

Then call the show myself method on all of them. I suggest you use a loop for making the objects and a separate loop for showing the objects.
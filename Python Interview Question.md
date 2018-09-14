#### Q1. What is the difference between shallow copy and deep copy ?

Ans : Shallow copy is used when a new instance type gets created and it keeps the values that are copied in the new instance. 
Shallow copy is used to copy the reference pointers just like it copies the values. These references point to the original objects
and the changes made in any member of the class will also affect the original copy of it. Shallow copy allows faster execution of the program 
and it depends on the size of the data that is used.
[Shallow copy doesn't copy the admin structure, just copies the top level references and the original values ]

Deep copy is used to store the values that are already copied. Deep copy doesn’t copy the reference pointers to the objects. 
It makes the reference to an object and the new object that is pointed by some other object gets stored. 
The changes made in the original copy won’t affect any other copy that uses the object. 
Deep copy makes execution of the program slower due to making certain copies for each object that is been called.
[Deep copy has to copy all the references , all the admin structures , all the values each and everything]

```
l1= [1,2,3,4]

l2 = l1

l2.append(10)

l2

[1,2,3,4,10]

l1

[1,2,3,4,10]

import copy 

l1

[1,2,3,4,10]

l3 = copy.copy(l1)

l3

[1,2,3,4,10]

l3.append(11)

l1
[1,2,3,4,10]

l2
[1,2,3,4,10]

l3
[1,2,3,4,10,11]
 
# To check the memory location
id(l1)

id(l2)

l4 = copy.deepcopy(l2)

l4
[1,2,3,4,10]
```

#### Q2. What is the difference between list and tuples?

Ans: Lists are mutable i.e they can be edited. Tuples are immutable (tuples are lists which can’t be edited).
Lists are slower than tuples.
List Syntax: list_1 = [10, ‘Chelsea’, 20]	
Tuple Syntax: tup_1 = (10, ‘Chelsea’ , 20)


l1= [1,2,3,4]
l1.append(40)  // is possible

t1= (1,2,3,4)
t1.append(40)  // is NOT possible


#### Q3. How is Multithreading achieved in Python?

Ans: Python has a multi-threading package but if you want to multi-thread to speed your code up, then it’s usually not a good idea to use it.
Python has a construct called the Global Interpreter Lock (GIL). The GIL makes sure that only one of your ‘threads’ can execute at any one time. 
A thread acquires the GIL, does a little work, then passes the GIL onto the next thread.
This happens very quickly so to the human eye it may seem like your threads are executing in parallel, but they are really just taking turns using the same CPU core.
All this GIL passing adds overhead to execution. This means that if you want to make your code run faster then using the threading package often isn’t a good idea.

import multiprocessing 
import threading 


#### Q4. How can the ternary operators be used in python?

Ans: The Ternary operator is the operator that is used to show the conditional statements. 
This consists of the true or false values with a statement that has to be evaluated for it.

x,y = 23,50
big = x if x>y else y
big 
50


#### Q5. What is monkey patching in Python?
Ans: In Python, the term monkey patch only refers to dynamic modifications of a class or module at run-time.

Consider the below example:

# m.py
class MyClass:
def f(self):
print "f()"


We can then run the monkey-patch testing like this:

import m
def monkey_f(self):
print "monkey_f()"

m.MyClass.f = monkey_f
obj = m.MyClass()
obj.f()
The output will be as below:

monkey_f()
As we can see, we did make some changes in the behavior of f() in MyClass using the function we defined, monkey_f(), outside of the module m.


#### Q6. How can you randomize the items of a list in place in Python?

Ans: 
from random import shuffle
x = ['Keep', 'The', 'Blue', 'Flag', 'Flying', 'High']
shuffle(x)
print(x)
['Flying', 'Keep', 'Blue', 'High', 'The', 'Flag']



#### Q7. Write a sorting algorithm for a numerical dataset in Python.

Ans: 

list = ["1", "4", "0", "6", "9"]
list = [int(i) for i in list]
list.sort()
print (list)



#### Q8. Looking at the below code, write down the final values of A0, A1, …An.
A0 = dict(zip(('a','b','c','d','e'),(1,2,3,4,5)))
A1 = range(10)A2 = sorted([i for i in A1 if i in A0])
A3 = sorted([A0[s] for s in A0])
A4 = [i for i in A1 if i in A3]
A5 = {i:i*i for i in A1}
A6 = [[i,i*i] for i in A1]
print(A0,A1,A2,A3,A4,A5,A6)


Ans: The following will be the final outputs of A0, A1, … A6

A0 = {'a': 1, 'c': 3, 'b': 2, 'e': 5, 'd': 4} # the order may vary
A1 = range(0, 10) 
A2 = []
A3 = [1, 2, 3, 4, 5]
A4 = [1, 2, 3, 4, 5]
A5 = {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49, 8: 64, 9: 81}
A6 = [[0, 0], [1, 1], [2, 4], [3, 9], [4, 16], [5, 25], [6, 36], [7, 49], [8, 64], [9, 81]]




#### Q9. Explain split(), sub(), subn() methods of “re” module in Python.

Ans: To modify the strings, Python’s “re” module is providing 3 methods. They are:

split() – uses a regex pattern to “split” a given string into a list.
sub() – finds all substrings where the regex pattern matches and then replace them with a different string
subn() – it is similar to sub() and also returns the new string along with the no. of replacements.

import re 
// Example goes here .


#### Q10. Explain Inheritance in Python with an example.

Ans: Inheritance allows One class to gain all the members(say attributes and methods) of another class. Inheritance provides code reusability,
makes it easier to create and maintain an application. The class from which we are inheriting is called super-class and the class 
that is inherited is called a derived / child class.

They are different types of inheritance supported by Python:-

Single Inheritance – where a derived class acquires the members of a single super class.
Multi-level inheritance – a derived class d1 in inherited from base class base1, and d2 are inherited from base2.
Hierarchical inheritance – from one base class you can inherit any number of child classes
Multiple inheritance – a derived class is inherited from more than one base class.

# Python basics


BB2441 

---

layout: false

# Basics of Python


## Running

### Interactive

* Python without arguments starts up  the interpreter with a prompt that expects Python code lines 

```
    $ python
    >>> 
    >>> print("Hello world")
    Hello world

```

---

### Executing files


```
    $ python file.py
```

(Linux) Or if the first line is 

```
    #!/usr/bin/env python
```

and the file is executable

```
    $ chmod +x file.py
    $ ./file.py 
```

---

### Integrated development environments (IDE)

* idle: a builtin Python editor/environment

```
$ python -m idlelib.idle
```

(tip: define a shell alias in startupfile)
```
alias idle=`python -m idlelib.idle`
```

Advanced IDEs

* pycharm
* spyder


---

### Notebooks

```
$ jupyter notebook
```

* work/develop in browser
* mix documentation and code

<img src='jupyter.png' height="300" >

---

### Syntax

#### Blocking

* First line of a block is marked by a colon
* Rest of the block have common indentation

```
    >>> for i in (1,2,3):
    ...    print(i)
    ... 
    1
    2

```

* Incorrect indentation leads to runtime error

```
    >>> for i in (1, 2, 3): #doctest: +SKIP
    ... print(i)
      File "<stdin>", line 2
        print(i)
            ^
    IndentationError: expected an indented block

```

---

### Objects

*Everything is an object* ... almost

Objects have

* value
* type
* identity

```
    >>> 3.14
    >>> type(3.14)
    <class 'float'>
    >>> id(3.14)
    140215166415160

```

in addition

* associated data and/or functions


---

### Variables

* python assignment

    Var = obj

* Assignment is to bind a name to an object
* free typing - one name can have different types
* one object can have many names

```python
>>> pi = 3.14
>>> print(pi)
3.14
>>> π = pi
>>> print(π)
3.14
>>> π is pi
True
```

---

### Some basic Python types

* Bool
* Number
    * `int`
    * `float`
    * `complex`
* String


```
>>> type(True)
<class 'bool'>
>>> type(1)
<class 'int'>
>>> type(1.0)
<class 'float'>
>>> type('one')
<class 'str'>
```


---

### Bool

* True
* False

```
    >>> a = (1 > 0)
    >>> print(a)
    True

```

--

### Numbers

* int
* float
* complex

```
    i = 1
    x = 3.14
    z = 5 + 1j
```

---

### Strings

* *str* type
* Single, double or triple quotes

```
    str1 = 'abc'
    str2 = "abc"
    str3 = "abc's"
    str4 = """Time to learn
    abc"""
```

---

## Container objects

* Lists
* Sets
* Dictionaries


### Lists

* A numbered sequence of objects
* First element has index zero
* Square brackets
* [] is the empty list
* [1, True, 'you']


---

### Tuples

* An immutable (unchangeable) sequence of objects
* Similar to lists
* () is the empty tuple
* (1,)  contains 1 element -note the comma

---

### Dictionaries

* Sets of key-value pairs
* The key can be any immutable object
* Very useful for complex structures
* Efficient and highly optimized

```
empty =  {} # empty dict
newdict = {'a':1, 'b':2}
```

---

### Sets

* Unordered collecetion of objects
* Supports set operations

```
    a = set([1,2]); b = set([2,3])
    a|b #union
    a&b #intersection
```


---

### Repetition (looping)

```
>>> for e in [1, 2, 3]: 
...    print(e)
1
2
3
```



```
newdict = {'a': 1, 'b': 2}
for k in newdict:
    print(k, newdict[k])
a 1
b 2
```


---

### Functions

* Definition

```
   >>> def f(args):
   ...    #*statements*
   ...    return #[value]

```

* functions are also objects
* have identity and type
* can be passed as arguments to other functions
    

* Function are called

```
>>> v = f(x)
```

* Arguments `x` are input
* Return values output (saved in `v`)
* Changing input arguments in functions is possible but not recommended

---

### Modules


* a file with python source 
   - name is the filename without the ``.py`` extension
* `import` modules to reuse code
* members of module referenced with dot notatoin `module.member`

Commonly used Python modules

* ``sys``
* ``os``
* ``math``

---

#### `sys`

* system modules
* needed e.g. for arguments to a script
* `sys.argv` is a list of string arguments
* `sys.argv\[0\]` is the file name

```
    import sys
    infile = sys.argv[1]
```

#### `os`

* Interaction with operating system
* Example: execute a unix command 

```
    import os
    os.system('/bin/date')
```


#### `math`

* all basic elementry functions
* fundamental constants

```
    import math
    print(math.sin(math.pi/2))
```

#### Tip

Many use the math modules as a desktop calculator

    $ python
    >>> from math import *
    >>> print(pi/2)
    1.5707963267948966
    >>>

---

#### Writing/using your own modules

* Suppose you have written file ``a.py`` with function ``b``
```
    #a.py
    def fun():
        ...
        return some_value
```

* To access the same function in other code, import module
```
    import a
    val = a.fun()
```

* or to import an individual function of a module
```
    from a import fun
    c = fun()
```


---

### Files

```
    >>> fo = open('foo', 'r')

```

* opens the file name for reading
* if is does not exist - Error
* returns a file object assigned to variable fo

```
    >>> file_str = fo.read()

```
* loads the contensts of the file to a string *file_str*

```
    >>> fo.close()

```
* close the file when done

---

### Reading text

Other ways to read a file into memory

* As a list of strings
```
    fo.readlines()
```
* One line at a time
```
    fo.readline() 
```
* In a for loop
```
    fo = open('file.txt') 
    for line in fo:
        *work on line*
```

The for statement is very powerful!
First example of iterator

---

### Summary


* Basic syntax - indentation
* Basic built in variable types
* Scalar and container types
* Modules
* Files


### On-line reference

Jake van der Plas: 
<a href="http://nbviewer.jupyter.org/github/jakevdp/WhirlwindTourOfPython/blob/master/Index.ipynb"> A Worldwind Tour of Python</a>

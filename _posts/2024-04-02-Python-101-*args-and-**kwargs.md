---
title: Python 101 - *args and **kwargs
tags: [Pyhton Programming]
style: fill
color: dark
description: Understanding what *args and **kwargs are and how to use them.
---

Source: [Rushikesh Konapure](https://medium.com/analytics-vidhya/python-101-args-and-kwargs-e27f7a0b3de9)

Let’s say we have a function that adds numbers.

```python
def adding(x,y):
  print(x + y)
adding(2,3)
```
If we run this code we will get 5 as output, simple enough. But if we pass more than 2 arguments(numbers to add) on the adding functions like:

```python
adding(2,3,4,5)
```
we’ll get an error like this

```python
TypeError : adding( ) takes 2 positional arguments but 4 were given
```
The reason why this happens is that the function expects only 2 numbers which it will add (x and y which we passed as arguments in the function).

But here we have given it 4 values to add which simply does not work. But we want our ‘adding’ to add as many numbers as we want.

## How do we fix this?

Using *args in a function, you can pass any number of arguments inside of a function. If we run the adding function now and just print the *args: we’ll get 1 2 3 4 5 as the output, so the *args acts as a variable that stores all of the arguments that we pass into it as a list.

```python
def adding(*args):
   print(*args)
adding(1,2,3,4,5)
```
Now we can add as many numbers as we want using the adding function! We don’t need to worry about how many parameters we have to pass into the adding function.

```python
def adding(*args):
 sum = 0
 for n in args:
   sum = sum + n
 print(sum)
adding(1,2,3,4,5)
```

The function looks a bit different because remember that the *args variable is treated as a list, we need to iterate over it to add all the numbers.

I’d encourage you to try this out for yourself right now. Open your IDE and start playing around with it.

**kwargs does something similar to *args, here we put “keyword arguments” instead of just “arguments”

Let’s look at this code and you’ll understand better.

```python
def func(**kwargs):
   print(kwargs)
func(Firstname = “Rishi”, Lastname = “Konapure”, Age = 25, Phone = 1234567890)
```

You will get the output as

```python
{Firstname = “Rishi”, Lastname = “Konapure”, Age = 25, Phone = 1234567890}
```

The **kwargs returns a dictionary instead of a list as *args did.

Alright, *args and **kwargs are cool but where do we use them?

I first encountered *args and **kwargs when working with database queries. Many times you don't know the nature of the input that you will get, *args and **kwargs helps us with these exact issues.

My suggestion would be to use them in a project and only then will you really understand their purpose.
# Python Programming Notes
## From Basics to Object-Oriented Programming

---

## Table of Contents
1. [Basic Input/Output](#basic-inputoutput)
2. [Data Types and Type Conversion](#data-types-and-type-conversion)
3. [Arithmetic Operations](#arithmetic-operations)
4. [Built-in Mathematical Functions](#built-in-mathematical-functions)
5. [Conditional Statements](#conditional-statements)
6. [Logical Operators](#logical-operators)
7. [Ternary Operator](#ternary-operator)
8. [String Methods](#string-methods)
9. [String Indexing and Slicing](#string-indexing-and-slicing)
10. [Format Specifiers](#format-specifiers)
11. [Loops](#loops)
12. [Collections](#collections)
13. [Dictionaries](#dictionaries)
14. [Modules and Random](#modules-and-random)
15. [Functions](#functions)
16. [Advanced Function Concepts](#advanced-function-concepts)
17. [Iterables and Membership Operators](#iterables-and-membership-operators)
18. [Match Case (Switch Statement)](#match-case-switch-statement)
19. [Object-Oriented Programming](#object-oriented-programming)

---

## Basic Input/Output

### User Input and Basic Operations
```python
# Getting user input
name = input("What is your name: ")
age = input("Enter your age: ")
age = int(age)
age = age + 1

# Output with f-strings
print(f"Hi {name}")
print(f"This is your age: {age}")
```

### Rectangle Area Calculator
```python
length = float(input("Enter the length: "))
breadth = float(input("Enter the breadth: "))
area = length * breadth
print(f"Area of rectangle: {area}")
```

---

## Data Types and Type Conversion

- `int()` - Convert to integer
- `float()` - Convert to floating point
- `str()` - Convert to string
- Always convert input to appropriate data type before calculations

---

## Arithmetic Operations

### Basic Operators
```python
friends = int(input("Enter number: "))

# Addition
friends += 1

# Subtraction  
friends -= 1

# Multiplication
friends *= 2

# Division
friends /= 2

# Exponentiation (Power)
friends **= 2

# Modulus (Remainder)
friends %= 5
```

---

## Built-in Mathematical Functions

```python
x = 3.14
y = -4
z = 33

result = round(x)        # Round to nearest integer
result = abs(y)          # Absolute value
result = pow(4, 3)       # Power function (4^3)
result = max(x, y, z)    # Maximum value
result = min(x, y, z)    # Minimum value
print(result)
```

---

## Conditional Statements

### If-Elif-Else Structure
```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You're an adult")
elif age < 0:
    print("Invalid age")
else:
    print("You're a minor")
```

---

## Logical Operators

### AND, OR, NOT Examples
```python
age = int(input("Enter your age: "))
has_permission = input("Do you have parental permission? (yes/no): ").lower()

if age >= 18 or (age >= 13 and not has_permission == "no"):
    print("You are allowed to enter.")
else:
    print("Sorry, you are not allowed to enter.")
```

**Logical Operators:**
- `and` - Both conditions must be True
- `or` - At least one condition must be True  
- `not` - Reverses the boolean value

---

## Ternary Operator

### Conditional Expression
```python
# Syntax: x if condition else y
num = int(input("Enter a number: "))
print("even" if num % 2 == 0 else "odd")
```

---

## String Methods

### Important String Functions
```python
name = input("Enter your name: ")

result = len(name)              # Length of string
result = name.find(" ")         # Find first occurrence
result = name.rfind(" ")        # Find last occurrence
result = name.capitalize()      # Capitalize first letter
result = name.upper()           # Convert to uppercase
result = name.lower()           # Convert to lowercase
result = name.title()           # Title case
result = name.replace(" ", "_") # Replace characters
result = name.count("a")        # Count occurrences

print(result)
```

### Get Help on String Methods
```python
print(help(str))  # Display all string methods
```

---

## String Indexing and Slicing

### Syntax: [start:end:step]
```python
text = "Hello World"

# Indexing (starts from 0)
first_char = text[0]      # 'H'
last_char = text[-1]      # 'd'

# Slicing
substring = text[0:5]     # 'Hello'
reverse_text = text[::-1] # 'dlroW olleH'
```

---

## Format Specifiers

### Decimal Places Control
```python
import math

radius = float(input("Enter radius: "))
circumference = 2 * math.pi * radius

# .2f for 2 decimal places
print(f"Circumference: {circumference:.2f}")
```

---

## Loops

### While Loop
```python
# Input validation with while loop
name = input("Enter your name: ")
while name == "":
    print("You didn't enter your name. Please type your name.")
    name = input("Enter your name: ")
print(f"Hello, {name}")
```

### Compound Interest Calculator
```python
principle = 0
rate = 0
time = 0

while principle <= 0:
    principle = float(input("Enter principle amount: "))
    if principle <= 0:
        print("You cannot enter zero or negative values")

while rate <= 0:
    rate = float(input("Enter rate of interest: "))
    if rate <= 0:
        print("You cannot enter zero or negative values")

while time <= 0:
    time = float(input("Enter time in years: "))
    if time <= 0:
        print("You cannot enter zero or negative values")

total = principle * pow((1 + rate/100), time)
print(f"Total amount is: {total}")
```

### For Loop
```python
# Print numbers 1 to 10
for x in range(1, 11):
    print(x)

# Print horizontally
for x in range(1, 11):
    print(x, end=' ')
```

### Loop Control Statements
```python
# Continue statement (skip iteration)
for x in range(1, 11):
    if x == 8:
        continue
    print(x)

# Break statement (exit loop)
for x in range(1, 11):
    if x == 8:
        break
    print(x)
```

### Countdown Timer
```python
import time

my_time = int(input("Enter time in seconds: "))
for x in range(my_time, 0, -1):
    seconds = x % 60
    minutes = (x // 60) % 60
    hours = x // 3600
    print(f"{hours:02}:{minutes:02}:{seconds:02}")
    time.sleep(1)
print("Time's up!")
```

### Nested Loops
```python
# Pattern printing
rows = int(input("Enter number of rows: "))
columns = int(input("Enter number of columns: "))
symbol = input("Enter the symbol: ")

for x in range(rows):
    for y in range(columns):
        print(symbol, end='')
    print()  # New line after each row
```

---

## Collections

### Collection Types
- **List** `[]` - Ordered and changeable, duplicates allowed
- **Set** `{}` - Unordered and immutable, add/remove OK, no duplicates
- **Tuple** `()` - Ordered and unchangeable, duplicates allowed, faster

### Lists
```python
fruits = ["apple", "banana", "orange", "kiwi"]

# Modify elements
fruits[0] = "cherry"
fruits[2] = "peaches"

# List methods
fruits.append("black grapes")    # Add to end
fruits.remove("orange")          # Remove specific item
fruits.insert(1, "mango")        # Insert at specific position
fruits.sort()                    # Sort alphabetically
fruits.reverse()                 # Reverse order
fruits.clear()                   # Remove all elements

# Print all elements
for fruit in fruits:
    print(fruit)
```

### Sets
```python
my_set = {"apple", "banana", "orange"}

# Set methods
my_set.add("kiwi")           # Add element
my_set.remove("banana")      # Remove element
my_set.pop()                 # Remove random element
my_set.clear()               # Remove all elements
```

### Restaurant Bill Calculator
```python
foods = []
prices = []
total = 0

while True:
    food = input("Enter food name (press 'q' to quit): ")
    if food.lower() == "q":
        break
    else:
        price = float(input(f"Enter price of {food}: "))
        foods.append(food)
        prices.append(price)
        total += price

print(f"Your total bill is: ${total}")
```

---

## Dictionaries

### Dictionary Basics
```python
# Dictionary: collection of {key: value} pairs
capitals = {
    "France": "Paris",
    "Germany": "Berlin", 
    "Spain": "Madrid",
    "India": "New Delhi",
    "Bangladesh": "Dhaka"
}

# Dictionary methods
print(capitals.get("India"))           # Get value by key
capitals.update({"India": "Chennai"})  # Update value
capitals.pop("Spain")                  # Remove specific key
capitals.popitem()                     # Remove last item
capitals.clear()                       # Remove all items

# Get keys and values
keys = capitals.keys()
values = capitals.values()

# Iterate through dictionary
for country, capital in capitals.items():
    print(f"{country}: {capital}")
```

---

## Modules and Random

### Random Module
```python
import random

# Random integer between 1 and 20
number = random.randint(1, 20)
print(number)

# Random choice from list
options = ("rock", "paper", "scissors")
choice = random.choice(options)
print(choice)

# Random float between 0 and 1
random_float = random.random()
print(random_float)
```

**Three types of random functions:**
1. `randint()` - Random integer in range
2. `random()` - Random float between 0 and 1
3. `choice()` - Random selection from sequence

---

## Functions

### Basic Function Structure
```python
def greet(name):
    print(f"I love you {name}")
    print("You're mine")

# Call function
greet(input("Enter the name: "))
```

### Function with Multiple Parameters
```python
def invoice(username, amount, due_date):
    print(f"Hello {username}")
    print(f"Your due amount is ${amount}")
    print(f"Payment due by {due_date}")

username = input("Enter username: ")
amount = float(input("Enter amount: "))
due_date = input("Enter due date: ")

invoice(username, amount, due_date)
```

### Return Statement
```python
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    return x / y

# Using functions
result = add(222, 1111111)
print(result)
```

### String Processing Function
```python
def create_full_name(first_name, last_name):
    first_name = first_name.capitalize()
    last_name = last_name.capitalize()
    return first_name + " " + last_name

# Use function multiple times
full_name = create_full_name("sai", "charan")
print(full_name)

another_name = create_full_name("surya", "vikas")
print(another_name)
```

### Default Arguments
```python
def net_price(list_price, discount=0, sales_tax=0.18):
    return list_price * (1 - discount) * (1 + sales_tax)

# Use with default values
print(net_price(45000))

# Override default values
print(net_price(45000, 0.1, 0.20))
```

### Timer Function Exercise
```python
import time

def countdown(start, end):
    for x in range(start, end + 1):
        print(x)
        time.sleep(1)
    print("Time's up!")

countdown(0, 10)
```

---

## Advanced Function Concepts

### Keyword Arguments
```python
def hello(greeting, title, first, last):
    print(f"{greeting} {title} {first} {last}")

# Using keyword arguments
hello("Hello", "Mr.", first="Sai", last="Charan")
```

### *args (Variable Arguments)
```python
def multiply(*args):
    total = 1
    for x in args:
        total *= x
    return total

result = multiply(1, 2, 3, 4, 5, 6)
print(result)
```

### **kwargs (Keyword Variable Arguments)
```python
def display_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

display_info(name="John", age=25, city="New York")
```

---

## Iterables and Membership Operators

### Iterables
```python
# Tuple is iterable
numbers = (1, 2, 3, 4, 5)

# Forward iteration
for number in numbers:
    print(number, end=" ")

# Reverse iteration
for number in reversed(numbers):
    print(number, end=" ")
```

### Membership Operators (in, not in)

#### String Example
```python
word = "APPLE"
letter = input("Guess a letter in the secret word: ")

if letter not in word:
    print(f"{letter} was not found")
else:
    print(f"There is a {letter}")
```

#### Set Example
```python
students = {"mahesh", "ntr", "arjun"}
student = input("Enter the name of a student: ")

if student not in students:
    print(f"{student} was not found")
else:
    print(f"{student} is a student")
```

#### Dictionary Example
```python
grades = {
    "sai": "A",
    "akshay": "B", 
    "karthik": "C",
    "chimtu": "D"
}

student = input("Enter the name of a student: ")

if student in grades:
    print(f"{student}'s grade is {grades[student]}")
else:
    print(f"{student} was not found")
```

---

## Match Case (Switch Statement)

### Match Case Example (Python 3.10+)
```python
def is_weekend(day):
    match day:
        case "Sunday":
            return True
        case "Monday":
            return False
        case "Tuesday":
            return False
        case "Wednesday":
            return False
        case "Thursday":
            return False
        case "Friday":
            return False
        case "Saturday":
            return True
        case _:  # Default case
            return False

print(is_weekend("Monday"))  # False
print(is_weekend("Sunday"))  # True
```

---

## Object-Oriented Programming

### What is OOP?
- **Class**: Like a blueprint or template (similar to a class in school)
- **Object**: Instance of a class (like students in the class)

### Basic Class Example
```python
class Car:
    color = "white"
    brand = "supra"

# Create object
car_1 = Car()
print(car_1.brand)  # supra
print(car_1.color)  # white
```

### Constructor (__init__ method)
```python
class Student:
    def __init__(self, name1, name2):
        self.name1 = name1
        self.name2 = name2
        print("Adding student to database")

# Create student object
s1 = Student("charan", "varma")
print(f"{s1.name1}\n{s1.name2}")
```

### Methods in Classes
```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks
    
    def get_avg(self):
        sum_marks = sum(self.marks)
        avg = sum_marks / len(self.marks)
        print(f"Hi {self.name}, your average score = {avg}")

# Create and use objects
s1 = Student("sai", [99, 99, 93, 98])
print(f"Name: {s1.name}")
print(f"Marks: {s1.marks}")
s1.get_avg()

s2 = Student("chimtu", [99, 99, 92, 98])
print(f"Name: {s2.name}")
print(f"Marks: {s2.marks}")
s2.get_avg()
```

### Four Pillars of OOP

1. **Inheritance** - Allows a class to inherit attributes and methods from another class
2. **Encapsulation** - Wrapping data and functions into a single unit (object)
3. **Abstraction** - Hiding implementation details and showing only essential features
4. **Polymorphism** - Same interface for different underlying data types

---

## 1. Inheritance

### Single Inheritance
```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        print(f"{self.name} makes a sound")

class Dog(Animal):  # Dog inherits from Animal
    def speak(self):
        print(f"{self.name} barks")

# Usage
my_dog = Dog("Buddy")
my_dog.speak()  # Buddy barks
```

### Multiple Inheritance
```python
class Father:
    def father_method(self):
        print("This is from father")

class Mother:
    def mother_method(self):
        print("This is from mother")

class Child(Father, Mother):  # Inherits from both
    def child_method(self):
        print("This is from child")

# Usage
child = Child()
child.father_method()  # This is from father
child.mother_method()  # This is from mother
child.child_method()   # This is from child
```

### Multilevel Inheritance
```python
class GrandParent:
    def grandparent_method(self):
        print("This is from grandparent")

class Parent(GrandParent):
    def parent_method(self):
        print("This is from parent")

class Child(Parent):  # Inherits from Parent, which inherits from GrandParent
    def child_method(self):
        print("This is from child")

# Usage
child = Child()
child.grandparent_method()  # This is from grandparent
child.parent_method()       # This is from parent
child.child_method()        # This is from child
```

### Super() Function
```python
class Parent:
    def __init__(self, name):
        self.name = name
    
    def show(self):
        print(f"Parent: {self.name}")

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  # Call parent constructor
        self.age = age
    
    def show(self):
        super().show()  # Call parent method
        print(f"Child age: {self.age}")

# Usage
child = Child("Alice", 10)
child.show()
# Output: Parent: Alice
#         Child age: 10
```

---

## 2. Encapsulation

### Public, Protected, and Private Attributes
```python
class BankAccount:
    def __init__(self, account_number, balance):
        self.account_number = account_number    # Public
        self._balance = balance                 # Protected (convention)
        self.__pin = 1234                      # Private (name mangling)
    
    def get_balance(self):  # Public method
        return self._balance
    
    def _internal_method(self):  # Protected method
        return "This is protected"
    
    def __private_method(self):  # Private method
        return "This is private"
    
    def verify_pin(self, pin):
        return self.__pin == pin

# Usage
account = BankAccount("123456", 1000)
print(account.account_number)  # 123456 (accessible)
print(account._balance)        # 1000 (accessible but shouldn't be used directly)
# print(account.__pin)         # Error! Not accessible
print(account.verify_pin(1234))  # True (access through public method)
```

### Property Decorators
```python
class Temperature:
    def __init__(self):
        self._celsius = 0
    
    @property
    def celsius(self):
        return self._celsius
    
    @celsius.setter
    def celsius(self, value):
        if value < -273.15:
            raise ValueError("Temperature cannot be below absolute zero")
        self._celsius = value
    
    @property
    def fahrenheit(self):
        return (self._celsius * 9/5) + 32

# Usage
temp = Temperature()
temp.celsius = 25
print(temp.celsius)     # 25
print(temp.fahrenheit)  # 77.0
```

---

## 3. Abstraction

### Abstract Base Classes
```python
from abc import ABC, abstractmethod

class Shape(ABC):  # Abstract class
    @abstractmethod
    def area(self):
        pass
    
    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        return 3.14159 * self.radius ** 2
    
    def perimeter(self):
        return 2 * 3.14159 * self.radius

# Usage
# shape = Shape()  # Error! Cannot instantiate abstract class
rect = Rectangle(5, 3)
circle = Circle(4)

print(rect.area())      # 15
print(circle.area())    # 50.26544
```

---

## 4. Polymorphism

### Method Overriding
```python
class Animal:
    def make_sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    def make_sound(self):
        print("Dog barks")

class Cat(Animal):
    def make_sound(self):
        print("Cat meows")

# Polymorphism in action
def animal_sound(animal):
    animal.make_sound()

# Usage
animals = [Dog(), Cat(), Animal()]
for animal in animals:
    animal_sound(animal)
# Output: Dog barks
#         Cat meows  
#         Animal makes a sound
```
## Advanced OOP Concepts

### Class Methods and Static Methods
```python
class Student:
    school_name = "Python High School"  # Class variable
    
    def __init__(self, name, grade):
        self.name = name      # Instance variable
        self.grade = grade    # Instance variable
    
    @classmethod
    def get_school_name(cls):
        return cls.school_name
    
    @classmethod
    def from_string(cls, student_str):
        name, grade = student_str.split('-')
        return cls(name, int(grade))
    
    @staticmethod
    def is_passing_grade(grade):
        return grade >= 60

# Usage
student1 = Student("Alice", 85)
student2 = Student.from_string("Bob-92")  # Alternative constructor

print(Student.get_school_name())     # Python High School
print(Student.is_passing_grade(75))  # True
```

### Magic/Dunder Methods
```python
class Book:
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages
    
    def __str__(self):  # String representation for users
        return f"{self.title} by {self.author}"
    
    def __repr__(self):  # String representation for developers
        return f"Book('{self.title}', '{self.author}', {self.pages})"
    
    def __len__(self):  # Length of the object
        return self.pages
    
    def __eq__(self, other):  # Equality comparison
        return self.title == other.title and self.author == other.author
    
    def __add__(self, other):  # Addition operation
        return self.pages + other.pages

# Usage
book1 = Book("1984", "George Orwell", 328)
book2 = Book("Animal Farm", "George Orwell", 112)

print(str(book1))     # 1984 by George Orwell
print(repr(book1))    # Book('1984', 'George Orwell', 328)
print(len(book1))     # 328
print(book1 + book2)  # 440 (total pages)
```

### Composition vs Inheritance
```python
# Composition - "has-a" relationship
class Engine:
    def start(self):
        print("Engine started")

class Car:
    def __init__(self, brand):
        self.brand = brand
        self.engine = Engine()  # Car HAS an Engine
    
    def start_car(self):
        print(f"Starting {self.brand}")
        self.engine.start()

# Inheritance - "is-a" relationship  
class Vehicle:
    def move(self):
        print("Vehicle is moving")

class Bicycle(Vehicle):  # Bicycle IS a Vehicle
    def pedal(self):
        print("Pedaling the bicycle")

# Usage
car = Car("Toyota")
car.start_car()  # Starting Toyota
                 # Engine started

bike = Bicycle()
bike.move()      # Vehicle is moving
bike.pedal()     # Pedaling the bicycle

### Operator Overloading

class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
    
    def __sub__(self, other):
        return Vector(self.x - other.x, self.y - other.y)
    
    def __mul__(self, scalar):
        return Vector(self.x * scalar, self.y * scalar)
    
    def __str__(self):
        return f"Vector({self.x}, {self.y})"

# Usage
v1 = Vector(2, 3)
v2 = Vector(1, 4)

v3 = v1 + v2   # Vector(3, 7)
v4 = v1 - v2   # Vector(1, -1)  
v5 = v1 * 3    # Vector(6, 9)

print(v3)  # Vector(3, 7)
```

---

## Design Patterns in OOP

### Singleton Pattern
```python
class Singleton:
    _instance = None
    
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super(Singleton, cls).__new__(cls)
        return cls._instance

# Usage
s1 = Singleton()
s2 = Singleton()
print(s1 is s2)  # True - same instance
```

### Factory Pattern
```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

class AnimalFactory:
    @staticmethod
    def create_animal(animal_type):
        if animal_type.lower() == "dog":
            return Dog()
        elif animal_type.lower() == "cat":
            return Cat()
        else:
            raise ValueError("Unknown animal type")

# Usage
factory = AnimalFactory()
dog = factory.create_animal("dog")
cat = factory.create_animal("cat")

print(dog.speak())  # Woof!
print(cat.speak())  # Meow!
```

---

## Real-World OOP Example

### Banking System
```python
class Account:
    def __init__(self, account_number, account_holder, balance=0):
        self.account_number = account_number
        self.account_holder = account_holder
        self._balance = balance
        self._transaction_history = []
    
    @property
    def balance(self):
        return self._balance
    
    def deposit(self, amount):
        if amount > 0:
            self._balance += amount
            self._transaction_history.append(f"Deposited: ${amount}")
            return True
        return False
    
    def withdraw(self, amount):
        if 0 < amount <= self._balance:
            self._balance -= amount
            self._transaction_history.append(f"Withdrew: ${amount}")
            return True
        return False
    
    def get_statement(self):
        return self._transaction_history.copy()

class SavingsAccount(Account):
    def __init__(self, account_number, account_holder, balance=0, interest_rate=0.02):
        super().__init__(account_number, account_holder, balance)
        self.interest_rate = interest_rate
    
    def calculate_interest(self):
        interest = self._balance * self.interest_rate
        self.deposit(interest)
        return interest

class CheckingAccount(Account):
    def __init__(self, account_number, account_holder, balance=0, overdraft_limit=100):
        super().__init__(account_number, account_holder, balance)
        self.overdraft_limit = overdraft_limit
    
    def withdraw(self, amount):
        if 0 < amount <= (self._balance + self.overdraft_limit):
            self._balance -= amount
            self._transaction_history.append(f"Withdrew: ${amount}")
            return True
        return False

# Usage
savings = SavingsAccount("SAV001", "Alice", 1000)
checking = CheckingAccount("CHK001", "Bob", 500, 200)

savings.deposit(200)
print(f"Savings balance: ${savings.balance}")  # $1200

checking.withdraw(600)  # Uses overdraft
print(f"Checking balance: ${checking.balance}")  # $-100
```

---

## Key Concepts Summary

### Important Notes:
- Use `True` and `False` (capitalized) for boolean values
- `time.sleep()` pauses program execution for specified seconds
- Modules help organize code into reusable files
- Functions promote code reusability and organization
- OOP provides better code organization and reusability
- Always close resources and handle edge cases

### Getting Help:
```python
print(help("modules"))  # List all available modules
print(help(str))        # Help for string methods
print(help(list))       # Help for list methods

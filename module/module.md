Here’s the **complete module-wise Dart learning guide** with **code examples** and **practice problems** combined:

---

### **Module 1: Introduction & Basics**  
**Topics Covered:**  
- What is Dart? (Uses in Flutter, backend, etc.)  
- Setting up Dart (Installing SDK, using DartPad, IDEs)  
- Basic syntax: `main()` function, `print()`, comments  
- Variables: `var`, `final`, `const`  
- Data Types: `int`, `double`, `String`, `bool`, `dynamic`  
- Type casting and interpolation  

**Code Examples:**  
```dart
void main() {
  print("Hello, Dart!"); // Basic print statement

  // Variables
  var name = "Alice"; // Type inferred as String
  final age = 25; // Runtime constant
  const pi = 3.14159; // Compile-time constant

  // Type casting
  String numberText = "10";
  int parsedNumber = int.parse(numberText); // String to int

  // String interpolation
  print("My name is $name. I'm ${age + 5} years old in 5 years.");
}
```

**Problem to Solve:**  
1. Write a program that declares:  
   - A constant `pi` with value 3.14159.  
   - A variable `radius` with value 5.  
   - Calculate and print the area of a circle (`pi * radius^2`).  
2. Create a string variable with your name and interpolate it into a sentence: "Hello, my name is [YOUR_NAME]".  

---

### **Module 2: Control Flow & Loops**  
**Topics Covered:**  
- Conditional statements: `if`, `else if`, `else`  
- Ternary operator  
- Loops: `for`, `while`, `do-while`  
- `break` and `continue`  
- Switch-case statements  

**Code Examples:**  
```dart
void main() {
  // If-else example
  int num = 0;
  if (num > 0) {
    print("Positive");
  } else if (num < 0) {
    print("Negative");
  } else {
    print("Zero");
  }

  // Ternary operator
  String result = num >= 0 ? "Non-negative" : "Negative";

  // For loop (print 1-5)
  for (int i = 1; i <= 5; i++) {
    print(i);
  }

  // Switch-case
  int dayNumber = 3;
  switch (dayNumber) {
    case 1:
      print("Monday");
      break;
    case 2:
      print("Tuesday");
      break;
    default:
      print("Invalid day");
  }
}
```

**Problem to Solve:**  
1. Write a program that checks if a number is even, odd, or zero using `if-else`.  
2. Use a `for` loop to print the first 10 Fibonacci numbers.  
3. Use a `switch` statement to print the day name based on a number (1=Monday, 2=Tuesday, etc.).  

---

### **Module 3: Functions**  
**Topics Covered:**  
- Declaring functions (parameters, return types)  
- Optional parameters: named (`{}`) and positional (`[]`)  
- Arrow syntax for short functions  
- Lexical scope  

**Code Examples:**  
```dart
// Function with return type
int add(int a, int b) {
  return a + b;
}

// Optional named parameters
void greetUser({String name = "Guest", int? age}) {
  print("Hello, $name! Age: ${age ?? 'unknown'}");
}

// Arrow function
double cube(double n) => n * n * n;

void main() {
  print(add(3, 4)); // Output: 7
  greetUser(name: "Bob", age: 30); // Output: Hello, Bob! Age: 30
  print(cube(3)); // Output: 27.0
}
```

**Problem to Solve:**  
1. Write a function `isPrime(n)` that checks if a number is prime.  
2. Create a function `greetUser()` with optional named parameters `name` (default: "Guest") and `age`. Print a greeting.  
3. Use an arrow function to calculate the cube of a number.  

---

### **Module 4: Collections**  
**Topics Covered:**  
- Lists: `List`, methods like `add()`, `remove()`, `map()`, `where()`  
- Sets: `Set` (unique elements)  
- Maps: `Map` (key-value pairs)  
- Spread operator (`...`) and collection `if`/`for`  

**Code Examples:**  
```dart
void main() {
  // List operations
  List<int> numbers = [1, 2, 3];
  numbers.add(4); // [1, 2, 3, 4]
  numbers.remove(2); // [1, 3, 4]

  // Set (removes duplicates)
  Set<int> uniqueNumbers = {1, 2, 2, 3}; // {1, 2, 3}

  // Map (key-value pairs)
  Map<String, dynamic> person = {
    "name": "Alice",
    "age": 25,
  };
  print(person["name"]); // Output: Alice

  // Spread operator
  List<int> combined = [...numbers, ...uniqueNumbers];
}
```

**Problem to Solve:**  
1. Create a list of numbers. Remove duplicates using a `Set` and print the result.  
2. Write a function that takes a list and returns a new list with only even numbers.  
3. Create a `Map` storing student names and marks. Add a student and update marks for an existing student.  

---

### **Module 5: Object-Oriented Programming (OOP)**  
**Topics Covered:**  
- Classes and objects  
- Constructors (default, named, `this` keyword)  
- Getters and setters  
- Inheritance (`extends`, `super`)  
- Polymorphism (`@override`)  
- Abstract classes and interfaces  

**Code Examples:**  
```dart
// Base class
class Vehicle {
  String brand;
  int year;

  Vehicle(this.brand, this.year);

  void honk() => print("Beep!");
}

// Inheritance example
class Car extends Vehicle {
  String model;

  Car(String brand, this.model, int year) : super(brand, year);
}

// Abstract class example
abstract class Shape {
  double area(); // Abstract method
}

class Circle implements Shape {
  double radius;
  Circle(this.radius);

  @override
  double area() => 3.14 * radius * radius;
}
```

**Problem to Solve:**  
1. Create a `Vehicle` class with properties `brand` and `year`. Extend it to `Car` with an additional property `model`.  
2. Create an abstract class `Shape` with an abstract method `area()`. Implement it for `Circle` and `Rectangle`.  

---

### **Module 6: Error Handling**  
**Topics Covered:**  
- `try`, `catch`, `on`, `finally`  
- Throwing custom exceptions with `throw`  
- Creating custom exception classes  

**Code Examples:**  
```dart
double divide(int a, int b) {
  if (b == 0) throw ArgumentError("Cannot divide by zero!");
  return a / b;
}

void main() {
  try {
    print(divide(10, 0));
  } on ArgumentError catch (e) {
    print("Error: ${e.message}"); // Output: Error: Cannot divide by zero!
  } finally {
    print("Operation attempted"); // Always executed
  }
}
```

**Problem to Solve:**  
1. Write a function that divides two numbers but throws an `ArgumentError` if the denominator is zero.  
2. Handle the exception using `try-catch` and print a custom message.  

---

### **Module 7: Asynchronous Programming**  
**Topics Covered:**  
- Futures and `async`/`await`  
- `Future` chaining with `.then()`  
- Error handling in Futures  
- Using `Future.delayed()`  

**Code Examples:**  
```dart
// Simulate API call
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 2)); // Simulate delay
  return '{"id": 1, "name": "Alice"}';
}

void main() async {
  print("Fetching data...");
  String data = await fetchData();
  print("Received: $data"); // Output after 2 seconds: Received: {"id": 1, "name": "Alice"}
}
```

**Problem to Solve:**  
1. Simulate fetching data from an API using `Future.delayed()`. Return a mock JSON response after 2 seconds.  
2. Write an async function that calls the mock API and prints the result.  

---

### **Module 8: Advanced Topics**  
**Topics Covered:**  
- Mixins (`with` keyword)  
- Generics (`List<T>`, custom generics)  
- Enums and pattern matching  
- Extension methods  

**Code Examples:**  
```dart
// Mixin example
mixin Logger {
  void log(String message) => print("Log: $message");
}

class Application with Logger {} // Inherit mixin methods

// Generic function
void swap<T>(T a, T b) {
  T temp = a;
  a = b;
  b = temp;
}

// Enum example
enum Day { monday, tuesday }

// Extension method
extension StringExtension on String {
  String capitalize() => this[0].toUpperCase() + substring(1);
}
```

**Problem to Solve:**  
1. Create a `mixin Logger` that logs method execution time.  
2. Write a generic function `swap<T>(T a, T b)` that swaps two values.  
3. Create an enum `Day` and write a function that returns the number of hours in a working day (e.g., Monday=8).  

---

### **Module 9: Final Project**  
**Problem to Solve:**  
Build a **console-based task manager** with:  
- Add, delete, and list tasks (use classes for tasks).  
- Save tasks to a file (simulate with async operations).  
- Handle invalid inputs with exceptions.  
- Use OOP principles (inheritance, mixins, etc.).  

**Code Skeleton:**  
```dart
import 'dart:io';

class Task {
  String title;
  bool isCompleted;

  Task(this.title, [this.isCompleted = false]);
}

class TaskManager {
  List<Task> tasks = [];

  void addTask(String title) => tasks.add(Task(title));
}

void main() async {
  // Implement your task manager here!
}
```

---

### **Next Steps**  
1. Practice on platforms like [DartPad](https://dartpad.dev/).  
2. Explore [Flutter](https://flutter.dev/) for building apps with Dart.  
3. Dive deeper with the [Dart Documentation](https://dart.dev/guides).  

Need solutions or further explanations? Let me know! 😊
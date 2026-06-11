# README.md

# 2D Graphics Editor in C

A simple **console-based 2D Graphics Editor** written in C that allows users to draw, modify, delete, and display basic geometric shapes on a text-based canvas.

---

## Overview

This project simulates a basic graphics editor using a 2D character array as a drawing canvas. Users can create and manage different shapes such as:

* Line
* Rectangle
* Triangle
* Circle

Each shape is stored as an object with a unique ID, allowing easy modification and deletion.

---

## Features

* Draw horizontal and vertical lines
* Draw filled rectangles
* Draw filled triangles
* Draw filled circles
* Display canvas contents
* Modify existing objects
* Delete objects using ID
* Maintain a list of all created objects
* Automatic canvas redraw after modifications

---

## Technologies Used

* C Programming Language
* Standard Libraries:

  * `stdio.h`
  * `stdlib.h`
  * `math.h`

---

## Canvas Specifications

| Property        | Value |
| --------------- | ----- |
| Rows            | 30    |
| Columns         | 60    |
| Maximum Objects | 100   |

The canvas is represented by a 2D character array:

```c
char canvas[ROWS][COLS];
```

Empty cells are displayed as:

```text
_
```

Drawn pixels are displayed as:

```text
*
```

---

## Supported Shapes

### 1. Line

Supports:

* Horizontal Line
* Vertical Line

Example:

```text
******
```

or

```text
*
*
*
*
```

---

### 2. Rectangle

Filled rectangle using width and height.

Example:

```text
*****
*****
*****
```

---

### 3. Triangle

Filled pyramid-shaped triangle.

Example:

```text
    *
   ***
  *****
 *******
```

---

### 4. Circle

Filled circle generated using:

```text
(x-cx)² + (y-cy)² ≤ r²
```

Example:

```text
   ***
 *****
 *****
  ***
```

---

## Data Structure

Each shape is stored using the following structure:

```c
typedef struct
{
    int id;
    int type;

    int x1, y1;
    int x2, y2;

    int width, height;
    int radius;

} Object;
```

### Shape Type Mapping

| Type | Shape     |
| ---- | --------- |
| 1    | Line      |
| 2    | Rectangle |
| 3    | Triangle  |
| 4    | Circle    |

---

## Menu Options

```text
=================================
      2D GRAPHICS EDITOR
=================================

1. Draw Line
2. Draw Rectangle
3. Draw Triangle
4. Draw Circle
5. Delete Object
6. Modify Object
7. Display Canvas
8. Show Object List
9. Exit

Enter Choice:
```

---

## Compilation

### GCC Compiler

Compile using:

```bash
gcc graphics_editor.c -o graphics_editor -lm
```

### Run

Linux/macOS:

```bash
./graphics_editor
```

Windows:

```bash
graphics_editor.exe
```

---

## Sample Execution

### Draw Rectangle

```text
Choice: 2

Enter x y:
5 5

Enter width height:
6 3
```

### Draw Circle

```text
Choice: 4

Enter center x y:
20 10

Enter radius:
4
```

### Display Canvas

```text
_____******____________________
_____******_______***__________
_____******_____*******________
_______________*********_______
________________*******________
_________________*****_________
__________________***__________
```

---

## Program Workflow

1. Initialize canvas with `_`.
2. User selects a drawing option.
3. Shape information is stored in an object array.
4. Shape receives a unique ID.
5. Canvas is redrawn whenever:

   * Object is added
   * Object is modified
   * Object is deleted
6. User can display the canvas or object list at any time.

---

## Time Complexity

| Operation          | Complexity         |
| ------------------ | ------------------ |
| Add Object         | O(1)               |
| Delete Object      | O(n)               |
| Modify Object      | O(n)               |
| Show Objects       | O(n)               |
| Redraw All Objects | O(n × Canvas Area) |

Where:

* `n` = Number of stored objects
* Canvas Area = `ROWS × COLS`

---

## Learning Concepts Demonstrated

This project demonstrates:

* Structures (`struct`)
* Arrays
* Functions
* Object-Oriented Style Data Management in C
* 2D Array Manipulation
* Shape Drawing Algorithms
* Dynamic Canvas Redrawing
* Menu-Driven Programming

---

## Future Enhancements

Possible improvements include:

* Diagonal line support (Bresenham Algorithm)
* Hollow rectangles and circles
* Shape color support
* Save and load drawings from files
* Undo/Redo functionality
* Mouse-based GUI version using Graphics Library
* Shape movement and scaling

---

## Author

**2D Graphics Editor in C**

A console-based mini CAD/graphics application developed for learning data structures, graphics algorithms, and object management in C.

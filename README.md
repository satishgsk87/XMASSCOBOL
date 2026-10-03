
# 🎄 XMASTREE — COBOL Christmas Tree

 A simple COBOL console program that generates a Christmas tree using characters and displays a **MERRY CHRISTMAS** greeting.

 ## 📌 Project Overview

 **XMASTREE** is a beginner-friendly COBOL program designed to demonstrate basic COBOL programming concepts such as:

 - Variables and data declarations
- `MOVE` statements
- `DISPLAY` statements
- `INITIALIZE`
- `PERFORM VARYING` loops
- Conditional statements using `IF`
- Arithmetic calculations using `COMPUTE`
- COBOL reference modification
- Formatted console output

 The program creates the Christmas tree dynamically by increasing the number of `*` characters on each row and adjusting their position.

 ## 🛠️ Technologies

 | Technology | Details |
| --- | --- |
| Programming Language | COBOL |
| Program ID | `XMASTREE` |
| Compiler / Online IDE | JDOODLE |
| Output | Console |
| File Type | `.cob` / `.cbl` |

## 📂 Program Structure

 The program contains the following COBOL divisions:

```
IDENTIFICATION DIVISION
        ↓
DATA DIVISION
        ↓
WORKING-STORAGE SECTION
        ↓
PROCEDURE DIVISION
```

 ### Working-Storage Variables

 | Variable | Picture | Description |
| --- | --- | --- |
| `WS-OUT` | `X(80)` | Stores the current output line |
| `WS-N` | `9(2)` | Controls the number of stars |
| `WS-CENTER` | `9(2)` | Controls the horizontal position of the tree |

## 🔄 How It Works

 The program first initializes an 80-character output area.

 It then displays the top portion of the tree:

```
MOVE '|' TO WS-OUT(WS-CENTER:1).
DISPLAY WS-OUT.

MOVE '\|/' TO WS-OUT(39:3).
DISPLAY WS-OUT.
```

 The main tree is generated using a loop:

```
PERFORM VARYING WS-N FROM 1 BY 2 UNTIL WS-N > 20
```

 For every iteration:

 1. The output line is initialized.
2. `WS-N` determines how many `*` characters are displayed.
3. The starting position is controlled by `WS-CENTER`.
4. The center position is adjusted using `COMPUTE`.
5. The completed row is displayed.

 After the tree is generated, the program displays the base and greeting:

```
MOVE '_ __| |__ _' TO WS-OUT(35:11).
DISPLAY WS-OUT.

MOVE 'MERRY CHRISTMAS' TO WS-OUT(33:15).
DISPLAY WS-OUT.
```

 ## ▶️ Running the Program

 This program was compiled and executed using **JDOODLE**.

 ### Using JDOODLE

 1. Open the JDOODLE online compiler.
2. Select **COBOL** as the programming language.
3. Copy the contents of the `XMASTREE` source file into the editor.
4. Click **Execute/Run**.
5. The Christmas tree will be displayed in the console output.

 ## 🖥️ Sample Output

 The program produces a Christmas-tree-style console output similar to:

```
                                                                             
                                      \|/
                                     --*--
                                      ***
                                     *****
                                    *******
                                   *********
                                  ***********
                                 *************
                                ***************
                               *****************
                              *******************
                                  _ __| |__ _
                                 MERRY CHRISTMAS
```

 > **Note:** The exact alignment may vary depending on the console, compiler, and font used by the execution environment.

 ## 📚 COBOL Concepts Demonstrated

 ### 1\. Working Storage

```
01 WS-OUT     PIC X(80) VALUE SPACES.
01 WS-N       PIC 9(2)  VALUE 0.
01 WS-CENTER  PIC 9(2)  VALUE 40.
```

 Defines the variables required by the program.

 ### 2\. Reference Modification

```
WS-OUT(WS-CENTER:WS-N)
```

 This allows a specific portion of the `WS-OUT` field to be accessed and modified.

 ### 3\. Looping

```
PERFORM VARYING WS-N FROM 1 BY 2 UNTIL WS-N > 20
```

 The loop increases the number of stars by two on every iteration.

 ### 4\. Conditional Logic

```
IF WS-N = 1 THEN
    MOVE '--' TO WS-OUT(38:2)
    MOVE '--' TO WS-OUT(41:2)
END-IF
```

 Adds additional decoration to the first row of the tree.

 ### 5\. Arithmetic

```
COMPUTE WS-CENTER = WS-CENTER - 1
```

 Moves the starting position to help maintain the tree's shape.

 ## 📁 Suggested Project Structure

```
XMASTREE/
│
├── README.md
└── XMASTREE.cob
```

 ## 🎯 Purpose of the Project

 This project can be used as a small COBOL practice program for beginners learning:

 - COBOL syntax
- Loops
- String handling
- Reference modification
- Console formatting
- Basic arithmetic and conditional logic

 ## 👤 Author

 **Satish**

 ## 🎄 Message

 > **MERRY CHRISTMAS!** 🎄

---

 ### License

 This project is provided for educational and practice purposes.

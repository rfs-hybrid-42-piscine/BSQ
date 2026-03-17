*This project has been created as part of the 42 curriculum by maaugust.*

<div align="center">
  <img src="https://raw.githubusercontent.com/rfs-hybrid/42-piscine-artwork/main/assets/covers/cover-bsq.png" alt="BSQ Cover" width="100%" />
</div>

<div align="center">
  <h1>🚀 BSQ: The Biggest Square</h1>
  <p><i>The final C Piscine project: Algorithm optimization, File I/O, and Dynamic Programming.</i></p>
  
  <img src="https://img.shields.io/badge/Language-C-blue" alt="Language badge" />
  <img src="https://img.shields.io/badge/Grade-100%2F100-success" alt="Grade badge" />
  <img src="https://img.shields.io/badge/Norminette-Passing-success" alt="Norminette badge" />
</div>

---

## 💡 Description
**BSQ** is the final and most algorithmic project of the 42 C Piscine. The core objective of this assignment is to locate the largest possible square area within a given two-dimensional grid without overlapping any blocked spaces. 

A text file representing the grid is passed as an argument to the executable. The program must then replace the designated empty spaces with filling characters to visually demonstrate the maximum square found. If multiple squares of the exact same maximum dimensions exist, the algorithm is required to prioritize the one located closest to the top edge, followed by the one closest to the left edge.

---

## 🧠 Core Logic Breakdown

To solve this efficiently without timing out on massive maps, a brute-force approach will not work. We must use **Dynamic Programming**, parsing the map into a numeric matrix to track the maximum possible square size at every single coordinate.

| Phase | Concept & Implementation |
| :--- | :--- |
| **1. Header Parsing** | The first line of any valid file acts as a legend. It dictates the total number of rows, the character representing an empty space, the character representing an obstacle, and the character used to draw the final square. |
| **2. Strict Validation** | The grid must follow strict geometric rules: all rows must be identical in length, it must contain at least one valid row, and every row must terminate with a newline. Additionally, the defining characters must be unique, and the grid cannot contain any undocumented symbols. |
| **3. The Algorithm** | As the grid is read, it is converted into a 2D integer array. Every empty coordinate evaluates its top, left, and top-left neighbors to calculate the maximum square it can anchor. The coordinates of the highest resulting value are saved to draw the final shape. |
| **4. Error Handling** | If the parser detects an invalid format, the program must instantly output a standard error string to the error output stream and proceed to evaluate the next file without crashing. |

---

## 🛠️ Instructions

### 🧪 Compilation & Testing
This project utilizes a professional directory structure (**[`srcs/`](srcs/)**, **[`includes/`](includes/)**, **[`maps/`](maps/)**, `objs/`) and requires a **[`Makefile`](Makefile)** to compile.

1. **Clone the repository:**
   ```bash
   git clone git@github.com:rfs-hybrid-42-piscine/BSQ.git BSQ
   cd BSQ
   ```

2. **Compile the executable:**
   ```bash
   make
   ```

3. **Execute with one or more files:**
   The program is built to process sequential file parameters. When evaluating multiple files, the standard output separates each grid solution (or error) with an empty line.
   ```bash
   ./bsq maps/map1.txt maps/map2.txt
   ```

4. **Execute via Standard Input:**
   If no arguments are provided to the executable, it dynamically reads the grid data from the standard input stream.
   ```bash
   ./bsq < maps/map_file.txt
   # OR
   cat maps/map_file.txt | ./bsq
   ```

### 🚨 The Norm & Constraints
* **Allowed Functions:** You are strictly limited to basic system calls for file manipulation (`open`, `close`, `read`, `write`), memory management (`malloc`, `free`), and `exit`. 
* **Memory Management:** Any memory allocated on the heap must be rigorously freed. Leaks will result in an immediate evaluation failure.
* **The Norm:** Every single `.c` and `.h` file must pass the 42 Norm.
* **The 42 Header:**
Before writing any code, every file must start with the standard 42 header. `norminette` will automatically fail any file missing this specific signature.
```c
/* ************************************************************************** */
/*                                                                            */
/*                                                        :::      ::::::::   */
/*   main.c                                             :+:      :+:    :+:   */
/*                                                    +:+ +:+         +:+     */
/*   By: maaugust <maaugust@student.42porto.com>    +#+  +:+       +#+        */
/*                                                +#+#+#+#+#+   +#+           */
/*   Created: 2026/03/17 02:50:57 by maaugust          #+#    #+#             */
/*   Updated: 2026/03/17 02:50:59 by maaugust         ###   ########.fr       */
/*                                                                            */
/* ************************************************************************** */
```

Run the following command before pushing to evaluate your directories:
```bash
norminette -R CheckForbiddenSourceHeader srcs/ includes/
```

---

## 📚 Resources & References

* [Dynamic Programming for Maximal Square](https://www.geeksforgeeks.org/maximum-size-sub-matrix-with-all-1s-in-a-boolean-matrix/) - The foundational algorithm required to solve BSQ efficiently.
* `man 2 read` / `man 2 malloc` - Manuals for system calls required for dynamic file I/O.
* [42 Norm V4](https://cdn.intra.42.fr/pdf/pdf/96987/en.norm.pdf) - The strict coding standard for 42 C projects.
* [Official 42 Norminette Repository](https://github.com/42School/norminette) - The open-source linter enforcing the strict 42 coding standard.

### 🤖 AI Usage Guidelines
* **Code:** No AI-generated code was used to solve these exercises. All C functions were built manually to strictly comply with the 42 Norm and deeply understand manual memory manipulation and dynamic programming algorithms.
* **Documentation:** AI tools were utilized to structure this `README.md` and format the logic breakdowns to create a clean, accessible educational resource for fellow 42 students.

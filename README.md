# Rubik's Cube Solver 🧩

A C++ based Rubik's Cube Solver that explores multiple search algorithms, cube representations, and pattern database heuristics to solve a 3×3 Rubik's Cube.

The project combines classical AI search techniques with efficient state representations and camera-based cube scanning using OpenCV.

## ✨ Features

- **Multiple Search Algorithms:** Implements DFS, BFS, IDDFS, and IDA*.
- **Multiple Cube Representations:** Supports 3D Array, 1D Array, and Bitboard representations.
- **Pattern Database:** Uses a precomputed corner pattern database to guide heuristic search.
- **Camera-Based Cube Scanner:** Uses OpenCV to capture and scan a physical Rubik's Cube.
- **Efficient State Representation:** Uses hashing and compact representations to support search operations.
- **C++ and CMake:** Organized into modular components for easier development and compilation.

## 🧠 Algorithms Implemented

| Algorithm | Description |
|---|---|
| DFS | Depth First Search explores one branch deeply before backtracking. |
| BFS | Breadth First Search explores states level by level. |
| IDDFS | Iterative Deepening DFS combines depth-limited search with repeated deepening. |
| IDA* | Iterative Deepening A* combines heuristic evaluation with depth-first search to reduce unnecessary exploration. |

### Pattern Database Heuristic

The project uses a precomputed corner pattern database to provide heuristic information during IDA* search.

Instead of exploring every possible cube state blindly, the solver uses stored pattern information to estimate the remaining work and guide its search.

The database is stored in:

`Databases/cornerDepth5V1.txt`

## 🧊 Cube Representations

The project implements three different ways of representing a Rubik's Cube:

- **3D Array Representation:** Represents cube faces using a three-dimensional array.
- **1D Array Representation:** Stores cube information in a linear array.
- **Bitboard Representation:** Uses bit-level encoding for compact state representation and efficient operations.

These implementations provide an opportunity to study how data structures influence search performance.

## 📷 Camera-Based Cube Scanner

The project includes a webcam-based cube scanning module built with OpenCV.

The scanner is designed to:

- Capture cube faces using a connected camera.
- Read sticker colors from the captured faces.
- Convert scanned information into a cube state.
- Pass the scanned cube state to the solver.

The camera scanner requires a working webcam and appropriate camera permissions.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| C++14 | Core implementation |
| STL | Data structures and algorithms |
| CMake | Build system |
| OpenCV | Camera access and image processing |
| Pattern Database | Heuristic guidance for IDA* |

## 📁 Project Structure

```text
rubiks-cube-solver/
│
├── Databases/
│   └── cornerDepth5V1.txt
│
├── Model/
│   ├── RubiksCube.h
│   ├── RubiksCube.cpp
│   ├── RubiksCube1dArray.cpp
│   ├── RubiksCube3dArray.cpp
│   └── RubiksCubeBitboard.cpp
│
├── PatternDatabases/
│   ├── CornerDBMaker.cpp
│   ├── CornerPatternDatabase.cpp
│   ├── NibbleArray.cpp
│   └── ...
│
├── Scanner/
│   ├── CubeScanner.h
│   └── CubeScanner.cpp
│
├── Solver/
│   ├── DFSSolver.h
│   ├── BFSSolver.h
│   ├── IDDFSSolver.h
│   └── IDAstarSolver.h
│
├── bits/
│   └── stdc++.h
│
├── main.cpp
├── CMakeLists.txt
├── .gitignore
└── README.md
```

## ⚙️ Installation and Setup

### Prerequisites

Make sure the following tools are installed:

- C++ compiler (GCC or Clang)
- CMake 3.20 or newer
- OpenCV
- Git

### 1. Install Dependencies

**macOS (Homebrew):**

```bash
brew install cmake opencv
```

**Ubuntu / Debian:**

```bash
sudo apt update
sudo apt install build-essential cmake libopencv-dev
```

### 2. Clone the Repository

```bash
git clone https://github.com/rishav1626/rubik-cube-solver.git
```

Move into the project directory:

```bash
cd rubik-cube-solver
```

### 3. Configure the Project

```bash
cmake -S . -B build
```

### 4. Build the Project

```bash
cmake --build build -j4
```

### 5. Run the Solver

Run the executable from the project root directory:

```bash
./build/rubiks_cube_solver
```

**Important:** The program expects the pattern database at `Databases/cornerDepth5V1.txt`. Run the executable from the repository root so that the relative database path resolves correctly.

## 🎯 Learning Objectives

This project provides practical exposure to:

- State-space search and graph traversal.
- Uninformed and heuristic search algorithms.
- Iterative Deepening techniques.
- Pattern database construction and heuristic search.
- Bit-level data representation.
- Hashing and state management.
- Computer vision fundamentals using OpenCV.
- Modular C++ development and CMake.

## 🚀 Future Improvements

- Add a performance benchmarking module to compare DFS, BFS, IDDFS, and IDA*.
- Improve camera-based color detection under different lighting conditions.
- Add a graphical 3D Rubik's Cube visualization.
- Optimize memory usage and search performance.
- Improve input validation and error handling.
- Add automated unit tests.

## 👨‍💻 Repository

**GitHub:** [Rishav Raj – Rubik's Cube Solver](https://github.com/rishav1626/rubik-cube-solver)

## 🙌 Acknowledgements

This repository builds upon an existing open-source Rubik's Cube Solver project.

Original project and contributors are acknowledged through the preserved Git history:

[Original upstream repository](https://github.com/shubhampatil11/rubiks-cube-solver)

The project is maintained as a learning and development project. Original authorship and applicable licensing terms should be respected.

---

**Built with C++ | Search Algorithms | Pattern Databases | OpenCV**

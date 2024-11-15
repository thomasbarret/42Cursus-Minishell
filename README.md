# 42 Cursus - Minishell

**Minishell** is a project designed to create a simple shell-like environment using C. It simulates the behavior of a Unix shell, with support for executing commands, managing processes, handling redirections, and managing environment variables. The project demonstrates key skills in C programming, such as working with system calls, process management, file handling, and memory management.

---

## Table of Contents
- [Requirements](#requirements)
- [Compilation and Usage](#compilation-and-usage)
- [Features](#features)
- [File Structure](#file-structure)
- [Builtins](#builtins)
- [Redirection and Pipelines](#redirection-and-pipelines)
- [Libraries](#libraries)

---

## Requirements

- GCC (GNU Compiler Collection)
- Make
- A Unix-based system (Linux/macOS recommended)

---

## Compilation and Usage

To compile and run the project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/minishell.git
   cd minishell
   ```

2. To compile the project:
   ```bash
   make
   ```

3. To run the minishell:
   ```bash
   ./minishell
   ```

4. Type commands just like you would in a standard shell (e.g., `ls`, `pwd`, `echo`, etc.):

   Example:
   ```bash
   $ echo "Hello, World!"
   Hello, World!
   ```

---

## Features

- **Command Execution**: Executes standard Unix commands and external binaries.
- **Builtins**: Implements common shell built-in commands such as `cd`, `pwd`, `echo`, `export`, `exit`, `unset`, etc.
- **Environment Management**: Supports environment variable manipulation and reading.
- **Pipes**: Handles piping between commands (e.g., `cat file.txt | grep "text"`).
- **Redirection**: Supports input/output redirection (`>`, `>>`, `<`).
- **Heredoc**: Allows command substitution with multi-line input redirection (`<<`).
- **Error Handling**: Provides error feedback for invalid commands or system calls.

---

## File Structure

```
.
├── Makefile                # Makefile to compile the project
├── includes                # Header files for project
│   ├── libft              # Library functions (e.g., ft_atoi, ft_lstadd_back)
│   ├── minishell.h        # Main header file for Minishell
├── src                     # Source code
│   ├── builtins           # Builtin command implementations
│   ├── main.c             # Main entry point of the program
│   ├── parsing            # Parsing logic for commands, arguments, and redirections
│   ├── pipe               # Pipe management and process creation
└── utils                   # Utility functions for Minishell
```

---

## Builtins

Minishell includes several built-in commands that are implemented directly within the shell. These commands are:

- **cd**: Change the current working directory.
- **echo**: Print text to the standard output.
- **env**: Display the current environment variables.
- **exit**: Exit the shell.
- **export**: Set environment variables.
- **pwd**: Print the current working directory.
- **unset**: Remove an environment variable.

Each builtin is implemented in a corresponding `.c` file in the `builtins/` directory.

---

## Redirection and Pipelines

Minishell supports both **redirection** and **pipelines** for chaining commands together.

- **Redirection**:
   - `>`: Redirect standard output to a file.
   - `<`: Redirect standard input from a file.
   - `>>`: Append output to a file.

- **Pipes**:
   - `|`: Send the output of one command into the input of another.

These features are implemented using system calls (`fork()`, `exec()`, etc.) and are managed in the `pipe/` directory.

---

## Libraries

The project uses the following libraries:

- **libft**: A custom C library containing various utility functions, such as `ft_atoi`, `ft_strjoin`, `ft_lstadd_back`, etc.
- **get_next_line**: A utility function to read input line by line.
- **ft_printf**: A custom implementation of the `printf` function.
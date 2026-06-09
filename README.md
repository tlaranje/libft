# libft

A custom C standard library built from scratch as part of the 42 School curriculum. It reimplements a wide set of standard libc functions and adds extra utilities for strings, memory, linked lists, number conversion, file descriptors, and formatted output.

---

## Overview

`libft` is a static library (`libft.a`) that serves as the foundation for all subsequent 42 projects. It is compiled from modular source files organized by category, each compiled into object files under `obj/`.

---

## Project Structure

```
libft/
├── libft.h                  # Master header — all prototypes and t_list typedef
├── Makefile
├── ft_is/                   # Character classification
│   ├── ft_is_alpha_digit.c
│   ├── ft_is_alnum_acscii.c
│   ├── ft_is_print_space.c
│   └── ft_is_sign.c
├── ft_mem/                  # Memory operations
│   ├── ft_memset.c
│   ├── ft_bzero.c
│   ├── ft_memcpy.c
│   ├── ft_memmove.c
│   ├── ft_memchr.c
│   ├── ft_memcmp.c
│   └── ft_calloc.c
├── ft_str/                  # String operations
│   ├── ft_strlen.c
│   ├── ft_strchr.c
│   ├── ft_strrchr.c
│   ├── ft_strncmp.c
│   ├── ft_strnstr.c
│   ├── ft_strlcpy.c
│   ├── ft_strlcat.c
│   ├── ft_strdup.c
│   ├── ft_substr.c
│   ├── ft_strjoin.c
│   ├── ft_strtrim.c
│   ├── ft_split.c
│   ├── ft_strmapi.c
│   ├── ft_striteri.c
│   ├── ft_tolower.c
│   └── ft_toupper.c
├── ft_nbr/                  # Number conversion
│   ├── ft_atoi.c
│   ├── ft_itoa.c
│   ├── ft_utoa.c
│   └── ft_putnbr.c
├── ft_put_fd/               # Output to file descriptors
│   ├── ft_putchar_fd.c
│   ├── ft_putstr_fd.c
│   ├── ft_putendl_fd.c
│   └── ft_putnbr_fd.c
├── ft_lst/                  # Linked list (bonus)
│   ├── ft_lstnew.c
│   ├── ft_lstadd_front.c
│   ├── ft_lstadd_back.c
│   ├── ft_lstlast.c
│   ├── ft_lstsize.c
│   ├── ft_lstdelone.c
│   ├── ft_lstclear.c
│   ├── ft_lstiter.c
│   └── ft_lstmap.c
└── ft_printf/               # ft_printf integration
    ├── ft_printf.c
    ├── ft_put_char_str.c
    ├── ft_put_nbr_unbr.c
    └── ft_put_ptr_hex.c
```

---

## Function Reference

### Character Classification — `ft_is/`

| Function | Description |
|----------|-------------|
| `ft_isalpha(c)` | Checks if `c` is alphabetic |
| `ft_isdigit(c)` | Checks if `c` is a decimal digit |
| `ft_isalnum(c)` | Checks if `c` is alphanumeric |
| `ft_isascii(c)` | Checks if `c` is a valid ASCII character (0–127) |
| `ft_isprint(c)` | Checks if `c` is a printable character |
| `ft_isspace(c)` | Checks if `c` is a space |
| `ft_issign(c)` | Checks if `c` is `+` or `-` |

### Memory — `ft_mem/`

| Function | Description |
|----------|-------------|
| `ft_memset(s, c, len)` | Fills memory with a constant byte |
| `ft_bzero(s, n)` | Zeroes out a memory area |
| `ft_memcpy(dst, src, n)` | Copies memory area (no overlap) |
| `ft_memmove(dst, src, n)` | Copies memory area (overlap-safe) |
| `ft_memchr(s, c, n)` | Finds first occurrence of byte in memory |
| `ft_memcmp(s1, s2, n)` | Compares two memory areas |
| `ft_calloc(nmemb, size)` | Allocates zero-initialised memory |

### Strings — `ft_str/`

| Function | Description |
|----------|-------------|
| `ft_strlen(s)` | Returns length of string |
| `ft_strchr(s, c)` | Finds first occurrence of `c` in string |
| `ft_strrchr(s, c)` | Finds last occurrence of `c` in string |
| `ft_strncmp(s1, s2, n)` | Compares up to `n` characters of two strings |
| `ft_strnstr(big, little, n)` | Finds substring within `n` characters |
| `ft_strlcpy(dst, src, n)` | Safe string copy |
| `ft_strlcat(dst, src, n)` | Safe string concatenation |
| `ft_strdup(s)` | Allocates a duplicate of string |
| `ft_substr(s, start, len)` | Extracts a substring |
| `ft_strjoin(s1, s2)` | Concatenates two strings into a new allocation |
| `ft_strtrim(s, set)` | Trims characters from both ends of a string |
| `ft_split(s, c)` | Splits string by delimiter into array |
| `ft_strmapi(s, f)` | Applies function to each character, returns new string |
| `ft_striteri(s, f)` | Applies function to each character in-place |
| `ft_tolower(c)` | Converts character to lowercase |
| `ft_toupper(c)` | Converts character to uppercase |

### Number Conversion — `ft_nbr/`

| Function | Description |
|----------|-------------|
| `ft_atoi(str)` | Converts string to integer |
| `ft_itoa(n)` | Converts integer to string |
| `ft_utoa(un)` | Converts unsigned long to string |
| `ft_putnbr(n)` | Writes a long long number to stdout, returns char count |

### File Descriptor Output — `ft_put_fd/`

| Function | Description |
|----------|-------------|
| `ft_putchar_fd(c, fd)` | Writes character to file descriptor |
| `ft_putstr_fd(s, fd)` | Writes string to file descriptor |
| `ft_putendl_fd(s, fd)` | Writes string followed by newline to file descriptor |
| `ft_putnbr_fd(n, fd)` | Writes integer to file descriptor |

### Linked List — `ft_lst/`

| Function | Description |
|----------|-------------|
| `ft_lstnew(content)` | Creates a new list node |
| `ft_lstadd_front(lst, new)` | Adds node at the front of the list |
| `ft_lstadd_back(lst, new)` | Adds node at the back of the list |
| `ft_lstlast(lst)` | Returns the last node |
| `ft_lstsize(lst)` | Returns the number of nodes |
| `ft_lstdelone(lst, del)` | Deletes a single node |
| `ft_lstclear(lst, del)` | Deletes all nodes in the list |
| `ft_lstiter(lst, f)` | Applies function to each node's content |
| `ft_lstmap(lst, f, del)` | Creates a new list by applying function to each node |

### printf — `ft_printf/`

| Function | Description |
|----------|-------------|
| `ft_printf(fmt, ...)` | Formatted output (see specifiers below) |

Supported specifiers: `%c`, `%s`, `%p`, `%d`, `%i`, `%u`, `%x`, `%X`, `%%`

---

## Usage

### Build

```bash
make
```

Produces `libft.a` in the project root.

### Use in your project

```c
#include "libft.h"

int main(void)
{
    char *s = ft_strdup("hello, 42!");
    ft_printf("%s\n", s);
    free(s);
    return 0;
}
```

Compile with:

```bash
cc main.c -L. -lft -o my_program
```

### Makefile rules

| Rule | Description |
|------|-------------|
| `make` / `make all` | Build the library |
| `make clean` | Remove object files |
| `make fclean` | Remove object files and the library |
| `make re` | Full rebuild |

---

## Author

**tlaranje** — [42 Porto](https://www.42porto.com)

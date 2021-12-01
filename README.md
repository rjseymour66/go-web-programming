# Go basics

# Types

## Arrays

An array is a fixed-length data type that contains a contiguous block of elements of the same type. Because each element is of the same type and in sequential memory spaces, you can iterate over the values quickly and easily.

An array is a value in go, so you can assign it to a variable like any other value.

### Declaring an array

Arrays are immutable, and initialized to the zero value for the array type.

```go
var array [5]int
```
An array literal is when you declare the number of elements and their values:

```go
array := [5]int{10, 20, 30, 40, 50}
```

You can specify the size and only specific elements with at `key: value` syntax:

```go
array := [5]int{1: 10, 2: 20}
```

Access elements in the array using the `[]` operator:

```go
array := [5]int{1: 10, 2: 20}

array[2] = 25
```

An array of pointers: 

```go 
array := [5]*int{0: new(int), 1: new(int)}
```
Multidimensional arrays:

```go
var array[4][2]int

// literal
array := [4][2]int{{10, 11}, {20, 21}, {30, 31}, {40, 41}}
```

### Passing arrays to functions

In Go, variables are passed to functions by value. This means that Go creates a copy of the variable and passes that variable to the function.  

To reduce the amount of data copied to the stack, pass a pointer to the function:

```go
var array [1000000000]int

randomFunc(&array)
```
# ECE-2112-PA-1
 
Created by: Raphael Luis L. Bachoco | 2ECE-D

This repository contains content that pertains to Programming Assignment 1 of ECE 2112: Advanced Computer Programming and Algorithms, 
SY: 2026-2027

# 1. Word Rotation Problem 
>Objective: Create a function named rotate word() that accepts a non-empty string. Move the first character  
>of the string to the end while keeping all remaining characters in their original order. Preserve the capitalization of every character 


To solve the following problem basic string slicing and indexing must be done to create a function that manages to shift the characters to the left by 1 index value. 

When counting the index value of a string, The values will start at `0` and increase by increments of `1`. Essentially we can assign index values to each character in each string for example the word `dog`
of which the values will be `d = 0`, `o = 1` and `g = 2` respectively.

By making use of the fact that `word[0]` starts at the original index value which would be the first character of the string, we can use `word[1:]` to slice the string and reconnect it with `word[0]`, such as `word[1:] + word[0]`. 

This works since we are basically slicing the string at its beginning and reconnecting it at the end of the string. For example in the word `dog`, the expression `word[1:]` would be any character equal to and above the index value of `1` and `word[0]` is the first character of the string. Hence when used as `word[1:] + word [0]` the end result would be `ogd`. It should also be noted that any capitalization of characters used will also carry over as they are not affected.

Word Rotation function:
```
def rotate_word(word):
    return word[1:] + word [0]
```

# 2. Username Builder Problem
>Create a function named make username() that accepts two strings: first name and last name. The
function must:
>1. convert all letters to lowercase;
>2. remove all spaces from the first name;
>3. remove all spaces from the last name; and
>4. join the processed first and last names using one period (.).

The username problem requires two strings to be converted to lowercase letters while also joining both `firstname` and `lastname` 

To convert all letters to lowercase we can use `lower()` to erase any capital letters and we can use `replace(" ","")` to remove the spaces between the 
strings

To see our final output and to combine both strings we can use `return` as well as `+` to join the `firstname` and `lastname` together and to satisfy condition 4 we can use `+ "."` to add a `.` between the processed first and last name.

In essence `firstname.lower().replace(" ","")` represents the `firstname` in lowercase letters and removes all the spaces in the first name, ` + "." ` completes condition 4 and `+ lastname.lower().replace(" ", "")` is the `lastname` in lowercase and removes spaces in between as well.

Username Builder function:
```
def make_username(firstname, lastname):
  return firstname.lower().replace(" ","") + "." + lastname.lower().replace(" ", "")
```


# 3. Bookend Swap Problem
> Create a function named swap bookends() that accepts a list containing at least two elements.
> Unpack the list into three variables: • first – the first element; • middle – a list containing everything between the first and last elements; and • last – the > last element.
> Using these variables, return a new list in which the first and last elements have exchanged positions.
> The elements in middle must remain in their original order. Do not modify the input list.

The approach to this problem is to extract certain elements and be able to swap both the first element and last elements.

First we must separate the list into three parts namely `first` `middle` and `last` of which they will be assigned to the elements inside the list
for instance `first` would indicate the first element, `last` for the last element and `*middle` which would be any element in the middle of the list. 
Note that we are not separating the middle part into more detailed parts since they will remain unchanged in their order.

By assigning the first element to `first` and the last element to `last` we can change their orientation in the list by returning them using 
`return [last] + middle + [first]`. Using `*middle` allows us to bypass certain conditions namely when the list only has 2 elements as it allows the middle of the list to be flexible in size as without it the code strictly expects a list with exactly three elements, raising a `ValueError` if the list has fewer or more items.


Bookend Swap function:
```
def swap_bookends(items):
    first, *middle, last = items
    return [last] + middle + [first]
```

## History
- August 21, 2026 - File Created, Created Solution for Problem 1
- August 22, 2026 - Created Solution for Problem 2
- August 23, 2026 - Created Solution for Problem 3, Uploaded Jupyter Notebook

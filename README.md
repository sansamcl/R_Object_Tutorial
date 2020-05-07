# Object Types and Reading, Reshaping, and Writing Data

----------
# Reading data
https://www.statmethods.net/input/importingdata.html

###Use the read.table() most of the time!

```
table.object <- read.table("yourTable.txt", sep="\t")
```

# Object Types

https://rstudio-education.github.io/hopr/r-objects.html



## Common Classes:
- ### Scalar
    - 1 value
    - common types of data:
        - numeric
        - character
        - logical - TRUE/FALSE

    ```
    # set the number 1 to a numeric scalar called "scalar.object"
    scalar.object <- 1
    
    # what is the class of this object?
    class(scalar.object)
    
    # what is the type of data in this object?
    typeof(scalar.object)
    
    # what is the length of this object
    length(scalar.object)
    
    # what are the dimensions of this object?
    dim(scalar.object)
    
    # can you add this object?
    scalar.object + scalar.object
    ```
```
    # set the string "1" to a character scalar called "scalar.object"
    scalar.object <- "1"
    
    # what is the class of this object?
    class(scalar.object)
    
    # what is the type of data in this object?
    typeof(scalar.object)
    
    # can you add this object?
    scalar.object + scalar.object
    
    # change the data type to numeric
    scalar.object <- as.numeric(scalar.object)
    
    # now can you add this object?
    scalar.object + scalar.object
    ```


- ### Vector
    - >1 value (all of the same type)
    - 1 dimensional
   
    ```
    # set the numbers 1,2,3 to a numeric vector called "vector.object" using the 
    # combine function - c()
    vector.object <- c(1,2,3)
    
    # what is the class of this object?
    class(vector.object)
    
    # what is the type of data in this object?
    typeof(vector.object)
    
    # what is the length of this object
    length(vector.object)
    
    # what are the dimensions of this object?
    dim(vector.object)
    
    # can you add this object?
    vector.object + vector.object
    ```
    
- ### Matrix
    - >1 value (all of the same type)
    - 2 dimensional (like an excel table)
    - I rarely use this. What not a dataframe?
    
    ```
    # construct a matrix with the "matrix()" function
    matrix.object <- matrix(c(1,2,3,4,5,6,7,8,9,10,11,12), nrow=6, ncol=2)
    
    # what is the class of this object?
    class(matrix.object)
    
    # what is the type of data in this object?
    typeof(matrix.object)
    
    # what are the attributes of this object
    attributes(matrix.object)
    
    # what are the dimensions of this object?
    dim(matrix.object)
    
    # can you add this object?
    matrix.object + matrix.object
    ```
    
     ```
    # construct a matrix with the "matrix()" function
    matrix.object <- matrix(c(1,2,3,4,5,6,7,8,9,10,11,"12"), nrow=6, ncol=2)
    
    # what is the class of this object?
    class(matrix.object)
    
    # what is the type of data in this object?
    typeof(matrix.object)
    
    # what are the attributes of this object
    attributes(matrix.object)
    
    # what are the dimensions of this object?
    dim(matrix.object)
    
    # can you add this object?
    matrix.object + matrix.object
    
    # convert the object to numeric type
    matrix.object <- as.numeric(matrix.object)
    
    # what is the class of this object now?
    class(matrix.object)
    ```

    
- ### Data frame
    - >1 value 
    	- each column must be all of the same type
    	- columns can be of different types
    - 2 dimensional (like an excel table)
    - Most commonly used
    
   ```
   # construct a matrix with the "matrix()" function
    matrix.object <- matrix(c(1,2,3,4,5,6,7,8,9,10,11,"12"), nrow=6, ncol=2)
    
    # convert the matrix to a dataframe
    df.object <- as.data.frame(matrix.object)
    
    # what is the class of this object?
    class(df.object)
    
    # what is the type of data in this object?
    typeof(df.object)
    
    # what are the attributes of this object
    attributes(df.object)
    
    # what are the dimensions of this object?
    dim(df.object)
    
    # can you add this object?
    df.object + df.object
   ```
   
    ```
   # construct a matrix with the "matrix()" function
    matrix.object <- matrix(c(1,2,3,4,5,6,7,8,9,10,11,12), nrow=6, ncol=2)
    
    # convert the matrix to a dataframe
    df.object <- as.data.frame(matrix.object)
    
    # what is the class of this object?
    class(df.object)
    
    # what is the type of data in this object?
    typeof(df.object)
    
    # what are the attributes of this object
    attributes(df.object)
    
    # what are the dimensions of this object?
    dim(df.object)
    
    # can you add this object?
    df.object + df.object
   ```
   
- ### List
    - >1 class 
    	- each element can be any class of object
    - 1 dimensional (like a vector)
    - Extremely useful!
    
    ```
   # construct a matrix with the "matrix()" function
    matrix.object <- matrix(c(1,2,3,4,5,6,7,8,9,10,11,12), nrow=6, ncol=2)
    
    # convert the matrix to a dataframe
    df.object <- as.data.frame(matrix.object)
    
    # Using the list() function, create a list with the df and matrix above
    list.object <- list(df = df.object, mtrix = matrix.object)
    
    # what is the class of this object?
    class(list.object)
    
    # what is the type of data in this object?
    typeof(list.object)
    
    # what are the attributes of this object
    attributes(list.object)
    
    # what are the names of the elements in the list?
    names(list.object)
    
    # does the object have dimensions?
    dim(list.object)
    
    ```
    
- ### Function
    
    ```
   # construct a function with the "function()" function
   
   addTwoNumbersFunction <- function(number1=1, number2=2){number1 + number2}
    
    # what is the class of this object?
    class(addTwoNumbersFunction)
    
    # use the function with default arguments
    addTwoNumbersFunction()
    
    # use the function with specified numbers
    addTwoNumbersFunction(10,20)
```



# Write data as text file

```
write.table(objectName, "dirName/fileName", quote=FALSE)
```


# Write data as rds file
```
saveRDS(objectName, file="fileName.rds")
objectName <- readRDS(file="fileName.rds")
```
Val, Var, Types, & Nullability 

```
val GlobalName: String? = "Top Level Nullable Variable"
var Greeting: String = "Hello"

fun main(){
    //available only within scope of main
    var typeInfrancedName = "Jack" // Compiler infers that this is a string
    println(GlobalName)
    println(Greeting)
}
```
Conditionals, Control Flow 
```
if (greeting != null){
    println(greeting)
}else{
    println(name)
}

//OR//

when(greeting){
    null -> println("hi")
    else -> println(greeting)
}

// If and when can be used to assign variables to values they are checking //

val greetingToPrint = if(greeting != null) greeting else "Hi"

//OR//

val greetingToPrint = when (greeting) {
    null -> "Hi"
    else -> greeting
}

```

Functions and return values 

```
fun functionName( <params> ): ReturnValue{
    // Do Stuff //
    return value;
}

```
"Unit" in Kotlin is saying "the absence of any useful type." In otherwords, void. This is the default return type for functions without specified return types.
```
fun function(): Unit{
    // returns nothing 
}
```
How would you get a function to return null? Return a type by inference?
```
fun getSomeString: String?{
    return someString// can be null
}

fun getSomeString() = "Hello Kotlin" // single expression function 
```
Function parameters 
```
fun sayHello(myString: String){
    print("Hello $myString")
}

//OR//

fun sayHello(myString: String) = println("Hello $myString")
```
String template > concatenation.. remove boilerplate 
```
val message = "Hello $name"
```
Functions outside of any enclosing class are Top Level or Global Functions. 

---------------------------------------------------------------------------------------
DATA TYPES 
---------------------------------------------------------------------------------------
Arrays
```
val myArray = arrayOf("Bob", "Tom") // arrayOf is called a convenience function. Performs type inference and builds your list. 
myArray.size
myArray[ <element index> ]
myArray.get( <element index> )

for (myItem in myArray){
    println(myItem)
}

// OR Invoke a foreach lambda function //

myArray.forEach { item ->
    println(item)
}

// Using an index with a lambda function //

myArray.forEachIndexed { index, item ->
    println("myArray[$index] = $item")
}

```
listOf function // Lists have the same functions as arrays PLUS immutable:

"Array<T> is mutable (it can be changed through any reference to it), but List<T> doesn't have modifying methods (it is either read-only view of MutableList<T> or an immutable list implementation)."

A mutable list would be `mutableListOf(...)`.

Maps (associated key/value pairs for quick lookups): 
```
val map = mapOf(1 to "A", 2 to "B", 3 to "C") // access by map[1], map[2]

map.forEach { key, value -> println("$key -> $value") }
```
A mutable map would be `mutableMapOf(...)`.

VARARG is a variable number of arguments.

```
fun sayHello(greeting:String, vararg itemsToGreet:String) {
    itemsToGreet.forEach { item -> 
        println("Hi $item")
    }
}
sayHello("Hi", "Bob", "Jerry", "Alice")
```
Spread Parameter "*". How we pass in a collection as a vararg: 

```
val interestingThings = arrayOf("kotlin", "Programming", "Books")
sayHello("Hi", *interestingThings)
```
Default parameters
```
fun sayHello(greeting:String = "Hello", vararg itemsToGreet:String) {
    ...
}
```

---------------------------------------------------------------------------------------
Classes
---------------------------------------------------------------------------------------



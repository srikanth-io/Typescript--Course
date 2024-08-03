## TYPESCRIPT

* Typescript is a superset of Javascript that enables the Static Types
* Syntatic superset that basically shares the same base has javascript, but adding the overlay of Types that developers to finds the error from origin

## Why should I use Typescript

* Javascript is loosely typed language, It can be difficult to understand the type of data being passed around in Javascript
* Typescript allows specifying the type of data being passed around within the code, and ability to report errors when the types doesn't match
* Typescript uses compile time type checking. Which means it checks if the specified types match before running the code, not while running the code.

## Typescript Compiler

* Typescript being converted into Javascript means it runs anywhere that Javascript runs.

## Typescript Installation

`npm install -g typescript --save-dev`

* `tsc ` is the command to compile the code
* `tsconfig.json` file used to config the typescript

## Types

> * Typescript support primitive types
> * boolean - returns true or false value
> * number - whole numbers and float point values
> * string  - returns Text values with " "
> * bigint - same has numbers, but allows larger negative and positive numbers
> * symbol - used to create a globally unique identifier

## Type Assignment

Variable creating has possible with two ways :

```
Explicit - eg: let firstName: string = "Srikanth"
implicit - eg: let firstName = "Srikanth"
```

```
Note : having Typescript "guess" the type of the valueis called "infer"
```

## Error in Typee Assignment

```
let firstName: string = "Dylan"; // type string
firstName = 33; // attempts to re-assign the value to a different type
```

* **Implicit ** type assignment would have made firstName less noticeable as a string, but both will throw an error:

let firstName = "Dylan"; // inferred to type string
firstName = 33; // attempts to re-assign the value to a different type

## Unable to Infer

Typescript may not always properly infer what the type of a variable may be, it will set the type to "any" which disables type checking

```
// Implicit any as JSON.parse doesn't know what type of data it returns so it can be "any" thing...
const json = JSON.parse("55");
// Most expect json to be an object, but it can be a string or a number like this example
console.log(typeof json);
```

## Typescript Special Types

Typescript has special types that may not refer to any specific type of data.

### Type: any

`any` is a type disables type checking and effectively allows all types to be used

```
let u = true;
u = "string"; // Error: Type 'string' is not assignable to type 'boolean'.
Math.round(u); // Error: Argument of type 'boolean' is not assignable to parameter of type 'number'.


Setting any to the special type it disables type checking :


let v: any = true;
v = "string"; // no error as it can be "any" type
Math.round(v); // no error as it can be "any" type
```

### Type: unknown

`unkown` is similar to `any` but safer than `any` when we don't know the type of data being typed. To add a type later, we need to cast it.

* Casting is when we use the "as" keyword to say property or variable is of the casted type.

### Type: never

`never ` effectively throws an error whenever it is defined. rarely used, its primary use in advanced generics.

```
let x: never = true; // Error: Type 'boolean' is not assignable to type 'never'.
```

### Type: Undefined & null

`undefined` and `null `are types that refer to the javascript primitives undefined and null respectively

```
let y: undefined = undefined;
let z: null = null;
```

these types don't have much use unless `strictNullChecks ` is enabled in the tsconfig.json file

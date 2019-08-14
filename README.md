# Recursion Exercises

- ### Sum of all from 1 to n - done

Write a function that takes in a number as input and recursively finds the sum of all numbers up to and including that number.

```js
input: 6
output: 21

//21 = 6 + 5 + 4 + 3 + 2 + 1


func iterativeSumOfAll(n: Int) -> Int {
var sum = 0

for i in 0...n{
sum += i
print(i)
}
return sum
}

iterativeSumOfAll(n: 6)

func recursiveSumOfAll(n: Int) -> Int {
//base call
if n == 1 {return 1}
return n + recursiveSumOfAll(n: n - 1)
}

recursiveSumOfAll(n: 6)

```



- ### Multiply array - done

Write a function called `multArr` that takes in an array of numbers as an argument and recursively multiplies together all of the values in the array.

```js
multArr([2, 3, 5]); // returns 30
multArr([5, 5, 1, 2]); //returns 50



func multArr(arr: [Int], index: Int) -> Int {
// base case
if index == arr.count  { return 1 }
return arr[index] * multArr(arr: arr, index: index + 1)

}

multArr(arr: [2,3,5], index: 0)

```

- ### Concatenate array - done

Write a function called `concatArr` that takes in an array of strings as an argument and recursively concatenates the strings together into a single string, with spaces between each original string.

```js
concatArr(['is', 'it', 'tomorrow']); // returns 'is it tomorrow'
concatArr(['or', 'just', 'the', 'end', 'of', 'time']); //returns 'or just the end of time'


func concatArr(strings: [String], i: Int) -> String {

if i == strings.count {return "" }

return strings[i] + " " + concatArr(strings: strings, i: i + 1)

}

concatArr(strings: ["is", "it", "tomorrow"], i: 0)
```

- ### Sum evens - done

Write a function called `sumEvens` that takes in an array of numbers as an argument and recursively sums only the even numbers in the array.

```js
sumEvens([2, 3, 5, 6]); // returns 8
sumEvens([10, 5, 1, 2, 12]); //returns 24


func sumEvens(nums: [Int]) -> Int {

var nums = nums
guard !nums.isEmpty else {
return 0
}
var first = nums.removeFirst()
if first % 2 != 0 {
first = 0
}
return sumEvens(nums: nums) + first

}

sumEvens(nums: [2, 3, 5, 6])
```

- ### Recursive range - done

Write a function called `range` which takes in two numbers (num1, num2) as arguments. The function should return an array of numbers between num1 and num2.

```js
range(2,10); // returns [2, 3, 4, 5, 6,7, 8, 9, 10]
range(17,20); // returns [17, 18, 19, 20]

func range(num1: Int, num2: Int) -> [Int]{
var product: [Int] = []
if num1 == num2 + 1 { return product }
product += [num1]
return product + range(num1: num1 + 1 , num2: num2)
}

range(num1: 3, num2: 7)

```


- ### Triple Step

A child is running up a staircase with n steps and can hop either 1 step 2 steps or 3 steps at a time. Write a function called 'tripleStep', that takes in an argument `n` that represents the number of steps in the staircase, and returns a count of how many possible ways the child can run up the stairs.

```js
tripleStep(3); //returns 4
tripleStep(4); //returns 7
tripleStep(5); //returns 13
tripleStep(10); //returns 274

func tripleStep(n: Int) -> Int {
if n == 1 || n == 0 { return 1 }
else if n == 2 { return 2 }
return tripleStep(n: n - 3) + tripleStep(n: n - 2) + tripleStep(n: n - 1)
//2                     //3                     //4
//1                     //0                     //3
}


tripleStep(n: 5)
```

Source: Cracking the Coding Interview

- ### Coin Combos

Given an infinite number of quarters, dimes, nickels, and pennies, write code to calculate the number of possible ways of giving exact change for `n` cents.

In other words, write a function called `coinCombos` that takes in one argument: `n`, which represents the total amount of money (in cents) that you need to make change for. Your function should return the amount of possible combinations you can make to return that exact amount of change.

For example:
```js
coinCombos(5); //returns 2
coinCombos(10); //returns 4
coinCombos(25); //returns 13
coinCombos(60); //returns 73
```

Source: CTCI

# Resources
- [JavaScript Recursion Exercises](http://www.w3resource.com/javascript-exercises/javascript-recursion-functions-exercises.php)
- [Swift Recursion Exercises](https://www.weheartswift.com/recursion/)

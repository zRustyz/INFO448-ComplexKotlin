# UW Homework: Complex Kotlin
This homework is designed to force you to exercise your knowledge of the Kotlin programming language. It does not involve Android in any way yet. Like the previous assignment, it will be done entirely from the command-line using Gradle and a good text editor.

## Goal
Your task is simple: ***Make the code compile, and make all the unit tests pass.***

Again, all your work should be in the `Homework.kt` file, and you may not modify the `HomeworkTest.kt` file in any substantive way.

## To obtain this code...
... clone the repository using Git:

    git clone https://github.com/tedneward/uw-complex-kotlin

Build and run the tests by using `gradlew` or `gradlew.bat`, depending on your operating system.

    ./gradlew test

Make sure to create a GitHub repository for your clone, and re-home the remote origin to it:

    git remote set-url origin https://github.com/[your-ID]/complexkotlin

If you find it hard to remember what to do, look back at the previous assignment for details. Reach out to the TA if you are still stuck.

## Now what?
If you do not see the `Homework` and `HomeworkTest` files at first, you can find them here:

* `src/main/kotlin/edu/uw/basic-kotlin/Homework.kt`
* `src/test/kotlin/edu/uw/basic-kotlin/HomeworkTest.kt`

Note that you will do all of your work in the `Homework.kt` file, and you should not need to modify anything in the `HomeworkTest.kt` file; in fact, modifying that file could jeopardize your grade! If you feel you need to make changes to it, contact the TA before doing so--chances are very good that the problem lies elsewhere.

## The assignment
The code is broken into a sequence of sections. Your job is to implement the body of each section, so that the tests will pass.

### FIZZBUZZ lambda
In the first section, you will be using the collection methods `map` and `fold` to perform the "FIZZBUZZ test". This is a simple algorithm, usually used as part of an interview process as a way of verifying developer skill (and rather poorly at that). FIZZBUZZ goes like this: Iterate across a sequence of numbers (1 to 15), and any number that is divisible by 3 returns "FIZZ", and any number divisible by 5 returns "BUZZ". Numbers which are divisible by both 3 and 5 return "FIZZBUZZ". Use the map function to transform the range of numbers into an list of strings (either "FIZZ", "BUZZ" or the empty string ""), and then use fold to combine them all down into a single String. The end result should be "FIZZBUZZFIZZFIZZBUZZFIZZFIZZBUZZ". (This is an exercise in understanding how map and fold work, as they are commonly used in Kotlin code, along with filter. You are free to use filter as well, if you so choose, but you do not need to in order to pass the tests.) You need to define all this in a lambda value, called `fizzbuzz`, that I can call from the tests. Be prepared to support *any* range of numbers from 0 to 15 (0 to 1, 0 to 0, 4 to 12, and so on).

> In addition to teaching you FizzBuzz (which really is used a lot in programmer interviews, I'm not making that up), this teaches you how to use `map` and `fold`, and forces you to get comfortable with lambda and block syntax.

### Use `process`
In the second section, your job is to use the `process` function defined in the code to generate strings. The process function takes a parameter and a block of code. Your job is to write the lambdas `r1` and `r2` to call `process` such that the tests for r1 and r2 pass. 

> This is an exercise in getting the "block syntax" correct, as well as more practice around lambdas. If it's not becoming clear, the use of anonymous functions, lambdas, and block syntax is really important to be able to understand. Lambdas open up a whole new world of capability in code design, and you need to know it.

### Ho, Socrates!
In the third section, you are to create an `enum` class called `Philosopher`. This is going to be a peculiar use of `enum`, however, as we are going to model a very simple state machine: that of the classic Greek philosopher. 

As everybody knows, philosophers split their time between THINKING and TALKING, and only shift from one state to the other when told to do so via the method call `signal` (which you will need to define). Additionally, each state should override the `toString` function to indicate the `Philosopher`'s current state. When THINKING, a `Philosopher` will return "Deep thoughts..." and when TALKING, a `Philosopher` will return "Allow me to suggest an idea...". If you are not sure of the syntax here, check out [the Kotlin reference page on Enum classes](https://kotlinlang.org/docs/enum-classes.html).

> Modeling state machines in a mobile application is a very common occurrence, so it's worth taking the time to give this exercise a shot. And giving you the link to the Kotlin reference page really makes this a "gimme", honestly.

> By the way, I will give a bonus extra credit point to anyone who can find out who Seneca the Younger was, an additional point if you can tell me which school of philosophy he is commonly associated with, and a third point if you can summarize that school of philosophy in a single sentence. Put your answers in comments in the code, and let the TA know so they can make sure to look for them. Direct copy-and-paste from Wikipedia does not count.

> On another note, when you have some time to kill, play "The Wikipedia Game"--pick any random subject on Wikipedia, and click the first link on that page. On the page that comes up, click the first link on that page. Continue doing this until you have reached the Wikipedia page on Philosophy, and marvel at how everything in human existence essentially traces its roots back to philosophy and a bunch of dead Greeks in togas.

## Command (object)!
In the fourth section, create a class called Command that can be used as a function. This means you will need to provide a invoke method on the class. The primary constructor should take a String parameter (prompt), and the invoke operator should also take a String parameter (message), and simply return a concatenation of the two. The tests will invoke Command objects in several different ways, to verify that the concatenation works correctly.

## Rubric
As with the previous assignment, 5 points if all the tests pass, and 0 points if any of them fail.

Where this README appears to disagree with the code, follow the code, but do not change the tests.

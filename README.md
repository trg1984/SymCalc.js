SymCalc.js - a Symbolic Calculator for JavaScript
=================================================

Does not use eval(), does not rely on server side code
------------------------------------------------------

A while back I realized that there were a lot of symbolic calculators and parsers for JavaScript, but all of the ones that I could find were either based on server side implementations or used eval in some part of the execution. Server side implementations are not available in offline mode and eval gives too much access to the client's browser architecture. Eval is also deprecated and planned to be removed in future versions of EMCAScript (at least so I've heard). This lead me to make my own implementation of a programming language, that is defined in the `fn` object of `symcalc.js`.

The beauty of SymCalc.js is that the command set can be freely defined in JavaScript and executed in a WebWorker thread. If you don't want to allow while loops or sin function, you simply remove the function from the `fn` object and it is gone. There should not be direct access to the JavaScript side; if it exists, it is a bug or defined in your `fn` object. Even if such thing would exist, the code is run in a WebWorker, so it won't go very far. That said, this is experimental, made for a specific purpose and I will not take any responsibility of the code quality at this point.

[Live demo](http://kulmakerroin.net/symcalc/)

License
-------
MIT license. Have fun. Please send bug fixes back as pull requests so I can merge them to the project.

About the Reference Programming Language Implementation
-------------------------------------------------

The reference programming language is made for a backend of a calculator. Therefore it does not have any of the fancy things one might expect from a programming language. Feel free to extend/modify the language for your personal needs.


Cheat Sheet for the Reference Programming Language
--------------------------------------------------
* sum: Sum of elements given as a list.
* sub: Substract a list of elements from left to right.
* mul: Multiply a list of elements.
* div: Divide a list of elements.
* neg: Negate the given element.
* sin : Sine of the given element.
* cos : Cosine of the given element.
* tan : Tangent of the given element.
* cot : Cotangent of the given element.
* arctan : Inverse of tangent of the given element.
* arccos : Inverse of cosine of the given element.
* arcsin : Inverse of sine of the given element.
* sinh : Hyperbolic sine of the given element.
* cosh : Hyperbolic cosine of the given element.
* tanh : Hyperbolic tangent of the given element.
* arcsinh : Inverse hyperbolic sine of the given element.
* arccosh : Inverse hyperbolic cosine of the given element.
* arctanh : Inverse hyperbolic tangent of the given element.
* exp : Exponent of the given element.
* ln : Natural logarithm of the given element.
* sqr : Square of the given element.
* sqrt : Square root of the given element.
* abs : Absolute value of the given element.
* print : Prints the given element on the screen.
* block : A Block of elements to be executed.
* while: A while loop function. Requires two elements:
	* First element is the while condition.
	* The second one is the clause that is executed on each iteration.
* for: A for loop function. Requires four elements:
	* First element is the for loop initialization part.
	* Second element is the continue condition.
	* Third element is the iteration update operation
	* Fourth element is the clause that is executed on each iteration.
* if: Conditional execution. Requires two elements:
	* First element is the condition that needs to be met in order to execute.
	* Second element is the clause that is executed if the first element evaluates to true.
* ifelse: Conditional execution with else. Requires three elements:
	* First element is the condition that needs to be met in order to execute.
	* Second element is the clause that is executed if the first element evaluates to true.
	* Third element is the clause that is executed if the first element does not evaluate to true.
* set: Sets value of a variable. Requires two elements:
	* Name of the element to be set.
	* New value of the element to be set.
* Basic arithmetic operators (`-`, `+`, `*` and `/`) work as one would expect.

Localization
------------

As an experiment, a localized version of the command set has been added in finnish. If `Finnish, Finland` is selected from the drop down menu at the top, following new function names replace their english counterparts (if a function is not in this list, the name remains the same):

* 'summa': 'sum',
* 'erotus': 'sub',
* 'tulo': 'mul',
* 'jaa': 'div',
* 'vastaluku': 'neg',
* 'e': 'exp',
* 'neliö': 'sqr',
* 'neliöjuuri': 'sqrt',
* 'itseisarvo': 'abs',
* 'kirjoita': 'print',
* 'lohko': 'block',
* 'kun': 'while',
* 'toista': 'for',
* 'jos': 'if',
* 'jokotai': 'ifelse',
* 'aseta': 'set',
* 'satunnainen': 'random',
* 'pyöristä': 'round'
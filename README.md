# MBC16_Regex-Tutorial

### Using regular expression to validate email entry

A regular expression, also known as regex is simply a sequence of characters coded in a stuctured way to form a pattern. The pattern is then used as an algorithm to match character combinations in strings. Its commonly used for "find" or "find and replace" operations on strings, or for input validation such as verifying whether a user has correctly entered something into a form.

Nowadays, when signing up or accessing information from an online application we are asked to enter an email address. Ever wondered how the system knows your email has not been entered in the correct format? Programmers use Regex to used validate the entry format of an email. It can't verify that the user has entered a legitimate address but it can ensure the entered email is in the format required to support send as a means to reduce the number of undeliverable emails.

This article will explore the following regex code and how it is used to validate user input of an email address.


    /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Email Regex Explained](#email-regex-explained)


Lets understand regex construction and how its used in our email regex emample.

### Anchors
Used to match start and end of a string.

/^ Matches the beginning.
$/ Matches the end.

### Quantifiers

Used to match a preceeding element and is surrounded using curly braces {}.
In this regex expression the quantifier is {2,6}.
It is used to identify that the preceeding expression must happen at least 2 times, but no more than 6 times and is preceeded using [a-z.].  
Combined it ensures entry of 2-6 characters using a-z or \ .

### Grouping Constructs

() are used to group sections of the code. With a section grouped that then allows us to use a quantifier on that entire section.
We can then use quantifiers to validate that section.

### Bracket Expressions

Square brackets [] designate character classes for individual characters inside of a string like [a-z0-9_.-].
The individual character can be any letter from a-z, or any number from 0-1, or .-

### Character Classes

Whenever the search string includes a list of characters inside a pair of square brackets, treat the square brackets and whatever's inside them to mean "match exactly one character that's inside these brackets".
Refer to the pattern ([\da-z.-]) of our example. \d is used match a single character that is a digit. It is the shorhand version of [0-9].

### Flags

Used for advanced searching. In our example we are using a multi-line flag that is shown by the use of ^ in the begining and $ at the end of the regex. This allows the expression to be on multiple lines without breaking the code.

### Character Escapes

Character escaping is what allows certain characters (reserved by the regex engine for manipulating searches) to be literally searched for and found in the input string.
There are several characters that need to be escaped to be taken literally (at least outside char classes):

Brackets: []
Parentheses: ()
Curly braces: {}
Operators: \*, +, ?, |
Anchors: ^, $
Others: ., \
In order to use a literal ^ at the start or a literal $ at the end of a regex, the character must be escaped.


### Email Regex Explained

Using the above information lets go back to our regex email example and look at it further:

    /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

Start and End (with character escape)
  
    /^
    $/

Each character set in the pattern is surrounded brackets ().

    ([a-z0-9_.-]+)

Verifies that each character will be either a lower case letter, number from 0-9 or special character shown in the code. 
The + sign allows an infininate number of characters in this section.

    ([\da-z.-]+)
    
As above, but instead of stating (0-9) the shorhand (\d) is used to depict allowing entry of any digit equal to (0-9).

    ([a-z.]{2,6})

Verifies that the last set of characters will be only 2-6 characters long, any letter from a-z, or a character(.)


## Author

Visit https://github.com/vvnnzar

## Acknowledgements

This article was developed in part using the following online resources:

https://www.w3schools.com/jsref/jsref_obj_regexp.asp

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions

https://en.wikipedia.org/wiki/Regular_expression

https://www.computerhope.com/jargon/r/regex.htm

https://codeburst.io/javascript-learn-regular-expressions-for-beginners-bb6107015d91

https://www.codespot.org/javascript-email-validation/

https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial

https://blog.robertelder.org/character-classes-intro-regular-expressions/

https://riptutorial.com/regex/example/15848/what-characters-need-to-be-escaped-

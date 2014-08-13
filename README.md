pure-erl
========

A parse transform for erlang code to show which functions are purely functional 


This parse transform will attempt to determine which functions are
pure in erlang code. In order to do that it will examine the ast of
the code to look for impure operations.

If you wish to mark a function as pure you can do so with the
directive `-pure(my_fun/3)` if the function in question is not pure it
will create a compile error.

This will also add 2 functions to the module, `pure/1` which will take
a function and return true if it is pure and false otherwise, and
`pure/0` which will return a list of pure functions.

Note that this does not provide the type of garantee that Haskell can
provide but does make for a strong hint.


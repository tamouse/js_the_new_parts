* Kyle Simpson: JavaScript: The Recent Parts on Frontend Masters, March 9, 2019

  ES2019 (and beyond!)

  Kyle Simpson <getify@gmail.com>

  JavaScript: The Recent Parts


** string interpolation: template literals

*** tag functions
    preprocessing input values for the template literal

    can be used to create entirely new languages, even! See JSX tag literal

** array destructuring

   Added in ES6/ ES2015.

   *de*composing a *structure* into its individual parts.

   The left hand side is a *pattern* to describe what we want out of the right hand side:

   #+BEGIN_SRC rjsx
     var [
         {
             name: firstName,
             email: firstEmail = "nobody@example.com"
         },
         {
             name: secondName,
             email: secondEmail = "nobody@example.com"
         }
     ] = getSomeRecords(); // an API call , for example
   #+END_SRC

   The pattern does not have to fully describe the return value, just the ones we care about at the moment.

   Somewhat self-documenting -- more descriptive than the imperative style, for sure. Eliminate need for a JSDoc comment -- maybe, but how would you extract the info into another form?

*** default assignment

    Only picks up when the item is ~undefined~, i.e., ~null~ would not fire the default assignment.

*** gather (aka "rest") operator

    Using the ~...~ syntax assign all the rest of the elements

*** confusing aspects:

    #+BEGIN_SRC rjsx
      function data() {
          return [1.2.3.4.5];
      }

      var tmp, o = [];
      tmp = [
          o[42], // gets value 1
          o[12], // gets value 2
          o[2], // get value 3
          ...o[100] // gets [4, 5]
      ] = data();

      // tmp gets [1,2,3,4,5] !!!
    #+END_SRC

*** nesting destructuring patterns

*** keep using the default assignment operators in the destructuring patters to have graceful fallbacks

*** destructuring patterns are *declarative*
    they are declaring what is *expected*, can't really do polymorphic patters.

** object destructuring

*** disabiguating an object destructuring pattern without a declarator in front of it

    #+BEGIN_SRC rjsx
      function data() { return {a: 1, b: 2, c: 3}}

      var first, second;

      // wrap it in parentheses, so JS sees it as an expression

      ({
          a: first,
          b: second
      } = data());

    #+END_SRC


*** put defaults inline, not in default object


FUCK FUCK FUCK HE'S NOT ANSWERING MY QUESTIONS

Left because my questions were not getting answered in chat.

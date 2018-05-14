# Turing CSS Style Guide {

*A primarily decent approach to CSS*

## Style Guides

### other style guides

  - [HTML](https://github.com/turingschool-examples/html)
  - [JavaScript](https://github.com/turingschool-examples/javascript)

This style guide has been adapted from [the airbnb css style guide](https://github.com/airbnb/css)

## Table of Contents

  - [Rule Declaration](#rule-declaration)
  - [Selectors](#selectors)
  - [Properties](#properties)
  - [Formatting](#formatting)
  - [Comments](#comments)
  - [ID Selectors](#id-selectors)
  - [JavaScript hooks](#javascript-hooks)
  - [Border](#border)


### Rule declaration

A “rule declaration” is the name given to a selector (or a group of selectors) with an accompanying group of properties. Here's an example:

```css
.listing {
  font-size: 18px;
  line-height: 1.2;
}
```

### Selectors

In a rule declaration, “selectors” are the bits that determine which elements in the DOM tree will be styled by the defined properties. Selectors can match HTML elements, as well as an element's class, ID, or any of its attributes. Here are some examples of selectors:

```css
.my-element-class {
  /* ... */
}

[aria-hidden] {
  /* ... */
}
```

### Properties

Finally, properties are what give the selected elements of a rule declaration their style. Properties are key-value pairs, and a rule declaration can contain one or more property declarations. Property declarations look like this:

```css
/* some selector */ {
  background: #f1f1f1;
  color: #333;
}
```

**[back to top](#table-of-contents)**

### Formatting

* Use soft tabs (2 spaces) for indentation
* Use dashes or kabob-case in class and id names.
* When using multiple selectors in a rule declaration, give each selector its own line.
* Put a space before the opening brace `{` in rule declarations
* In properties, put a space after, but not before, the `:` character.
* Put closing braces `}` of rule declarations on a new line
* Put blank lines between rule declarations

**Bad**

```css
.notGood{
color:red;
}
.avatar{
    border-radius:50%;
    border:2px solid white; }
.no, .nope, .not_good {
    // ...
}
```

**Good**

```css
.good {
  color: green;
}

.avatar {
  border-radius: 50%;
  border: 2px solid white;
}

.one,
.selector,
.per-line {
  // ...
}
```

### Comments

* Use comments on their own line. Avoid end-of-line comments.
* Write comments to organize blocks of code
* Write detailed comments for code that isn't self-documenting:
  - Uses of z-index
  - Compatibility or browser-specific hacks

### ID Selectors
While it is possible to select elements by ID in CSS, it should generally be considered an anti-pattern. ID selectors introduce an unnecessarily high level of specificity to your rule declarations, and they are not reusable.

For more on this subject, read CSS Wizardry's article on dealing with specificity.

### JavaScript hooks

Avoid binding to the same class in both your CSS and JavaScript. Conflating the two often leads to, at a minimum, time wasted during refactoring when a developer must cross-reference each class they are changing, and at its worst, developers being afraid to make changes for fear of breaking functionality.

We recommend creating JavaScript-specific classes to bind to, prefixed with `.js-`:

```html
<button class="btn btn-primary js-request-to-book">Request to Book</button>
```

### Border

Use `0` instead of `none` to specify that a style has no border.

**Bad**

```css
.foo {
  border: none;
}
```

**Good**

```css
.foo {
  border: 0;
}
```

**[back to top](#table-of-contents)**

# }

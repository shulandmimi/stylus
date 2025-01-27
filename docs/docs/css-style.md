---
layout: default
permalink: docs/css-style.html
---

# CSS Style Syntax

Stylus transparently supports a regular CSS-style syntax. This means you don't need an alternative parser, or specify that a certain file uses a specific style.

## Example

 Below is a small style using the indented approach:
 
 ```stylus
border-radius()
  -webkit-border-radius arguments
  -moz-border-radius arguments
  border-radius arguments

body a
  font 12px/1.4 "Lucida Grande", Arial, sans-serif
  background black
  color #ccc

form input
  padding 5px
  border 1px solid
  border-radius 5px
```

Since braces, colons, and semi-colons are optional, we could write this example just as we would with normal CSS:
 
```stylus
border-radius() {
  -webkit-border-radius: arguments;
  -moz-border-radius: arguments;
  border-radius: arguments;
}

body a {
  font: 12px/1.4 "Lucida Grande", Arial, sans-serif;
  background: black;
  color: #ccc;
}

form input {
  padding: 5px;
  border: 1px solid;
  border-radius: 5px;
}
```

While Stylus doesn't support _every_ possible CSS-like syntax, it can understand even such code:

```stylus
      border-radius() {
        -webkit-border-radius: arguments;
        -moz-border-radius: arguments;
        border-radius: arguments;
      }

  body a
  {
    font: 12px/1.4 "Lucida Grande", Arial, sans-serif;
      background: black;
    color: #ccc;
  }

      form input {
        padding: 5px;
    border: 1px solid;
        border-radius: 5px;
        }
```

Since we may mix and match the two variants, the following is valid as well:
 
```stylus
border-radius()
  -webkit-border-radius: arguments;
  -moz-border-radius: arguments;
  border-radius: arguments;

body a {
  font: 12px/1.4 "Lucida Grande", Arial, sans-serif;
  background: black;
  color: #ccc;
}

form input
  padding: 5px;
  border: 1px solid;
  border-radius: 5px;
```
 Variables, functions, mixins, and all the other features provided by Stylus still work as expected:
 
 ```stylus
main-color = white
main-hover-color = black

body a {
  color: main-color;
  &:hover { color: main-hover-color; }
}

body a { color: main-color; &:hover { color: main-hover-color; }}
```

There are a few caveats to this rule: since the two styles may be mixed and matched, some indentation rules still apply. So although not _every_ plain-CSS stylesheet will work with zero modification, this feature allows those who prefer CSS syntax to continue doing so while leveraging Stylus' other powerful features.
 


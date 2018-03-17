---
templateKey: blog-post
title: Create Visual Code Code Snippets
date: 2017-01-10T10:04:10-05:00
description: Create custom snippets in Visual Code that can be invoked using a shortcut.
---
We are going to create a JavaScript snippet that scaffolds a Promise construct:

```js
return new Promise((resolve, reject) => {
    
  });
```

We are going to invoke this snippet by typing the word `newprom` in the editor.

### What You Need

* Installation of Visual Code

### Make It

Let's open the snippet file and edit it:

Windows:

```text
File > Preferences > User Snippets
```

Mac: 

```text
Code > Preferences > User Snippets
```

Once the dropdown menu has opened choose *JavaScript*. `javascript.json` will open up. This file gives us some insight on the process:

* We place our snippets in `javascript.json`. For other languages, we'd just replace `javascript` with the other language ID as defined by the Visual Code documentation. It's easier to access then through the menu. 
* Each snippet is defined under a snippet name and has a prefix, body and a description on what the snippet does.
* The prefix is used to invoke the code snippet - it is the typed shortcut.
* Once invoked, the body is what is inserted in your active editor. 
* You can define variables in the body of the snippet. $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the same ids are connected.
  * You can also define variables to indicate choice and that represent a value to be resued within the snippet.

To build the `console.log` snippet, we insert this property in the existing JSON object in the `javascript.json` file:

```json
{
  "Create the body of a new Promise": {
		"prefix": "newprom",
		"body": [
      "return new Promise((resolve, reject) => {",
        " $0",
      "});"
		],
		"description": "Log output to console"
	}
}
```

Since we want the cursor to end up indented within the curly braces, the second string in the `body` arrays is `" $0",`. This string explicitly indicates the whitespace that is to be included. You can create the indentation either pressing the tab key or the space bar - up to your preference! 

That's it! We have now easily created a custom JavaScript snippet. Visual Code comes with some handy snippets already installed. We can also get pre-built bundles for a language in the Marketplace, or, as we've seen, we can create our own! 

Have fun creating as many snippets as you need and increasing your developer experience an productivity! 

Happy Snippiting! 










<p align="center">
    <img src="https://files.dulliag.de/share/qr-code.png" width="240px" height="auto">
</p>

<h1 align="center">Markdown-To-HTML-Converter</h1>

### Introduction

This Project is build using ShowdownJS, jQuery and some useles text inside this README.md

### Installation

**1. Get the Markdown-file**

```
function getFile(file) {
  return new Promise((res, rej) => {
    $.ajax({
      url: file,
      success: (response) => {
        res(response);
      },
      error: (error) => {
        rej(error);
      },
    });
  });
}

```

**2. Get the file data & display the generated HTML**

```
Promise.resolve(getFile("./README.md")).then((value) => {
  const converter = new showdown.Converter(),
    markdown = value,
    generatedHTML = converter.makeHtml(markdown);

  document.querySelector("#content #markdown").innerHTML += markdown;
  document.querySelector("#content #html").innerHTML += generatedHTML;
});
```

### Ressources

[jQuery](https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js)
[ShowdownJS](http://showdownjs.com/)

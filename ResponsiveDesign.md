# Responsive Design 101s


## Pixels

### dip <> hp
* The browser reports the width as Device Independent Pixels and not in physical Hardware Pixels!

### DPR
* Device Pixel Ratio: dips per hp calculated in one dimension.

## Viewport

* Always set the viewport!

```
<meta name="viewport"
      content="width=device-width, initial-scale=1.0">
```

* In special cases disable user zoom.

```
<meta name="viewport"
      content="width=device-width, user-scalable=no,
      initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```

## Relative Units

* Avoid shrinking or overflowing with use of percentages. Do not use absolute numbers.

```
... width: 100% instead of say 540px
```

* Suggested catch-all for *main.css*:

```
img, embed, object, video {
  max-width: 100%;
}
```

## Tap targets

* Elements that are to be touched should be at least 40px wide and high. Suggested size is 48px.

```
nav a, button {
  min-width: 48px;
  min-height: 48px;
}  
```


## Small to Large

* Start design and code for a small viewport. Adapt for larger afterwards.


## Media Queries

* Use them like:

```
@media screen and (max-width: 600px) {
  body { background-color: red; }
}

@media screen and (min-width: 601px) {
  body { background-color: green; }
}

@media screen and (min-width: 1200px) {
  body { background-color: blue; }
}
```

* Or with overlaps.

```
@media screen and (max-width: 400px) { ... }

@media screen and (min-width: 301px) and (max-width: 600px) { ... }

@media screen and (min-width: 601px) { ... }

@media screen and (min-width: 961px) { ... }
```

## Breakpoints

* Pick them considering the content instead of devices.

* Typical use includes two breakpoints in order to style for small, medium and large view.


## Flexbox

* Usage example:

```
<html>
  <head>
    <meta charset="utf-8">
    <title>flexbox test</title>
    <style type="text/css">
      .container {
        width: 100%;
        display: flex;
        flex-wrap: wrap;
      }
      div { width: 100%; height: 100px;}
      .red { background-color: red; width: 100%; order: 1; }
      .green { background-color: green; width: 50%; order: 2; }
      .blue { background-color: blue; width: 50%; order: 3; }
      .orange { background-color: orange; width: 25%; order: 4; }
      .pink { background-color: pink; width: 50%; order: 5; }
      .yellow { background-color: yellow; width: 25%; order: 6; }
      .purple { background-color: purple; width: 100%; order: 7; }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="red"></div>
      <div class="green"></div>
      <div class="blue"></div>
      <div class="orange"></div>
      <div class="pink"></div>
      <div class="yellow"></div>
      <div class="purple"></div>
    </div>
  </body>
</html>
```

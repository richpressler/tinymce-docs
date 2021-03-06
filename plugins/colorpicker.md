---
layout: default
title: Color Picker Plugin
title_nav: Color Picker
description: Select a color from a pallete.
keywords: colorpicker color color_picker_callback
---

The `colorpicker` plugin adds an HSV color picker dialog to the editor. When activated **in conjunction with** the [textcolor plugin](../textcolor/) it adds a "custom color" button to the text color toolbar dropdown. When a user clicks "custom color" a modal will open presenting a color wheel so that the user can choose their own colors (rather than the ones defined by `textcolor`) to be applied to text and/or the selected text's background.

The plugin hooks into the [`color_picker_callback`](#color_picker_callback) so you provide your own color picker specification to the user.

**Type:** `String`

##### Example

In this example you'll note that we have also activated the `textcolor` plugin. This is necessary because in a typical TinyMCE installation `colorpicker` is dependent on activation of `textcolor`. Try it out. Remove `textcolor` and see what happens.

```js
tinymce.init({
  selector: "textarea",  // change this value according to your HTML
  plugins: "textcolor colorpicker",
  toolbar: "forecolor backcolor"
});
```

### `color_picker_callback`

This option enables you to provide your own color picker.

##### Example

```js
tinymce.init({
  selector: "textarea",  // change this value according to your HTML
  plugins: "textcolor colorpicker",
  toolbar: "forecolor backcolor"
  color_picker_callback: function(callback, value) {
    callback('#FF00FF');
  }
});
```

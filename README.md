html-to-vdom [![Build Status](https://travis-ci.org/TimBeyer/html-to-vdom.svg?branch=master)](https://travis-ci.org/TimBeyer/html-to-vdom)
============

About
-----

This is yet another library to convert HTML into a [vtree](https://github.com/Matt-Esch/vtree).
It's used in conjunction with [virtual-dom](https://github.com/Matt-Esch/virtual-dom) to convert template based views into `virtual-dom` views.

Note
----

As of v0.3.0, the VNode and VText classes need to be passed in during library initialization from the `virtual-dom` module you are using.  
This is to reduce incompatibilties you might have due to depending on a different version of `virtual-dom` than the one this library would use. 

Usage
-----

```javascript
var VNode = require('virtual-dom/vnode/vnode');
var VText = require('virtual-dom/vnode/vtext');

var convertHTML = require('html-to-vdom')({
    VNode: VNode,
    VText: VText
});

var html = '<div>Foobar</div>';

var vtree = convertHTML(html);
var createElement = require('virtual-dom/create-element');
var el = createElement(vTree);
document.body.appendChild(el);
```

Credits
-------

Thanks to [@mattferrin](https://github.com/mattferrin) for noticing that promises could be removed from the API and contributing a PR to do so.

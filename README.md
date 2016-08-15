[![Build Status](https://travis-ci.org/vladimirgamalian/rectangle-bin-pack.svg?branch=master)](https://travis-ci.org/vladimirgamalian/rectangle-bin-pack)

![](http://imgur.com/g6sqBcB)

# rectangle-bin-pack

Fast (in native c++) implementation of bin packing algorithm for Node.js. Based on https://github.com/juj/RectangleBinPack.


## Information

<table>
<tr>
<td>Package</td><td>rectangle-bin-pack</td>
</tr>
<tr>
<td>Description</td>
<td>Fast rect packer</td>
</tr>
<tr>
<td>Node Version</td>
<td>>= 0.10</td>
</tr>
</table>

## Install

```
$ npm install --save-dev rectangle-bin-pack
```


## Usage

```js
var rbp = require('rectangle_bin_pack');

var arr = [{w: 32, h: 32}, {w: 64, h: 64}];
rbp.solveSync({"algorithm": "BSSF"}, arr);
console.log(arr);

```

```
[ { w: 32, h: 32, x: 0, y: 0 }, { w: 64, h: 64, x: 0, y: 64 } ]
```


## API

`solveSync(options, rects);`

Pack rectangles from rects array in place.


`solve(options, rects, cb);`

Pack rectangles and return new array in callback.


`options`

- `width` - width of bin (default 2048)
- `height` - height of bin (default 2048)
- `algorithm` - type of algorithm:
  - BestShortSideFit or BSSF
  - BestLongSideFit or BLSF
  - BestAreaFit or BAF (default)
  - BottomLeftRule or BL
  - ContactPointRule or CP


## LICENSE

The MIT License (MIT)

Copyright (c) 2016 Vladimir Gamalian

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

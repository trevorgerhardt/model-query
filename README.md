
# model-query

Advanced `Model.all()` queries for [component/model](https://github.com/component/model).

## Installation

Install with [component(1)](http://component.io):

```bash
$ component install trevorgerhardt/model-query
```

## API

Plugin to your model and query away.

```javascript
var model = require('model');
var Item = model('Item').use(require('model-query'));

Item.query({ type: 'expensive' }).limit(10).skip(20, function(err, items, res) {
  // the 20th-30th items that are 'expensive'
});
```

### .req([callback])

If a callback is passed it has the same functionality as `Model.all()`. If not it returns a modified version of the model's [superagent](https://github.com/visionmedia/superagent) request object. If a callback is passed to any of the functions the query gets sent to `#end()`.

### #end(callback)

The results will be passed into a `[component/collection](https://component/collection).

### .query(params[, callback])

Pass a parameters object that you would normally pass to `superagent.query()`

### .limit(limit[, callback])

Sugar for `Model.query({ limit: limit }, callback)`.

### .skip(skip[, callback])

Sugar for `Model.query({ skip: skip }, callback)`.

## License

  The MIT License (MIT)

  Copyright (c) 2014 Trevor Gerhardt

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files (the "Software"), to deal
  in the Software without restriction, including without limitation the rights
  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
  copies of the Software, and to permit persons to whom the Software is
  furnished to do so, subject to the following conditions:

  The above copyright notice and this permission notice shall be included in
  all copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
  THE SOFTWARE.
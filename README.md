### tape
---
.js
https://github.com/substack/tape

.java
https://github.com/square/tape

```js
var test = require('tape');
var path = require('path');

test.createStream({ objectMode: true }).on('data', function (row) {
  console.log(JSON.stringify(row));
});
process.argv.slice(2).forEach(function (file) {
  require(path.resolve(file));
});


var test = require('tape');
test('timing test', function(t){
  t.plan(2);
  
  t.equal(typeof Date.now, 'function');
  var start = Date.now();
  
  setTimeout(function () {
    t.equal(Date.now() - start, 100);
  }, 100);
});
```

```
node object.js test/x.js test/y.js

npm install tape --save-dev

node exapmle/timing.js

tape tests/**/*.js

tape 'tests/**/*.js'
tape "tests/**/*.js"

tape -r babel-register tests/**/*.js
tape -r ./my/local/module tests/**/*.js
```

```
```



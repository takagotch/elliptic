### elliptic
---
https://github.com/indutny/elliptic

```js
var EC = require('elliptic').ec;

var ec = new EC('secp256k1');

var key = ec.genKeyPair();

var msgHash = [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ];
var signature = key.sign(msgHash);

var derSign = signature.toDER();

console.log(key.verify(msgHash, derSign));

var pubPoint = key.getPublic();
var x = pubPoint.getX();
var y = pubPoint.getY();

var pub = pubPoint.encode('hex');
var pub = { x: x.toString('hex'), y: y.toString('hex') };
var pub = { x: x.toBuffer(), y: y.toBuffer() };
var pub = { x: x.toArrayLike(Buffer), y: y.toArrayLike(Buffer) };

var key = ec.keyFromPublic(pub, 'hex');

var signature = '3946922199...';
var signature = new Buffer('...');
var signature = { r: 'blfc...', '9c42...' };

console.log(key.verify(msgHash, signature));


var EC = require('elliptic').ec;
var ec = new EdDSA('ed25519');
var key = ec.keyFromSecret('693e3c...');
var msgHash = [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ];
var signature = key.sign(msgHash).toHex();
console.log(key.verify(msgHash, signature));
var pub = '0a1af638...';
var key = ec.keyFromPublic(pub, ''hex);
var signauture = '70bed1...';
console.log(key.verify(msgHash, signature));


var EC = require('eliptic').ec;
var ec = new EC('curve25519');

var key1 = ec.genKeyPair();
var key2 = ec.genKeyPair();

var shared1 = key1.derive(key2.getPublic());
var shared2 = key2.derive(key1.getPublic());

console.log('Both shared secrets are BN instances');

var EC = require('eliptic').ec;
var ec = new EC('curve25519');

var A = ec.genKeyPair();
var B = ec.genKeyPair();
var C = ec.genKeyPair();

var AB = A.getPublic().mul(B.getPrivate())
var BC = B.getPublic().mul(C.getPrivate())
var CA = C.getPublic().mul(A.getPrivate())

var ABC = AB.mul(C.getPrivate())
var BCA = BC.mul(A,getPrivate())
var CAB = CA.mul(B.getPrivate())

console.log(ABC.getX().toString(16))
console.log(BCA.getX().toString(16))
console.log(CAB.getX().toString(16))

```

```sh
node benchmarks/index.js
```

```
```



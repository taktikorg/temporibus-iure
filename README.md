# @taktikorg/temporibus-iure <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Robustly `.call.bind()` a function.

## Getting started

```sh
npm install --save @taktikorg/temporibus-iure
```

## Usage/Examples

```js
const assert = require('assert');
const callBind = require('@taktikorg/temporibus-iure');
const callBound = require('@taktikorg/temporibus-iure/callBound');

function f(a, b) {
	assert.equal(this, 1);
	assert.equal(a, 2);
	assert.equal(b, 3);
	assert.equal(arguments.length, 2);
}

const fBound = callBind(f);

const slice = callBound('Array.prototype.slice');

delete Function.prototype.call;
delete Function.prototype.bind;

fBound(1, 2, 3);

assert.deepEqual(slice([1, 2, 3, 4], 1, -1), [2, 3]);
```

## Tests

Clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@taktikorg/temporibus-iure
[npm-version-svg]: https://versionbadg.es/ljharb/@taktikorg/temporibus-iure.svg
[deps-svg]: https://david-dm.org/ljharb/@taktikorg/temporibus-iure.svg
[deps-url]: https://david-dm.org/ljharb/@taktikorg/temporibus-iure
[dev-deps-svg]: https://david-dm.org/ljharb/@taktikorg/temporibus-iure/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@taktikorg/temporibus-iure#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@taktikorg/temporibus-iure.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@taktikorg/temporibus-iure.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@taktikorg/temporibus-iure.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@taktikorg/temporibus-iure
[codecov-image]: https://codecov.io/gh/ljharb/@taktikorg/temporibus-iure/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@taktikorg/temporibus-iure/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@taktikorg/temporibus-iure
[actions-url]: https://github.com/taktikorg/temporibus-iure/actions

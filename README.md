<!--

@license Apache-2.0

Copyright (c) 2023 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->

# rpad

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Right pad a string.



<section class="usage">

## Usage

```javascript
import rpad from 'https://cdn.jsdelivr.net/gh/stdlib-js/string-base-right-pad@v0.0.1-deno/mod.js';
```

#### rpad( str, len, pad )

Right pads a string such that the padded string has a length of **at least** `len`.

```javascript
var str = rpad( 'a', 5, ' ' );
// returns 'a    '

str = rpad( 'beep', 10, 'b' );
// returns 'beepbbbbbb'

str = rpad( 'boop', 12, 'beep' );
// returns 'boopbeepbeep'
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   An output string is **not** guaranteed to have a length of **exactly** `len`, but to have a length of **at least** `len`. To generate a padded string having a length equal to `len`

    ```javascript
    var str = rpad( 'boop', 10, 'beep' ); // => length 12
    // returns 'boopbeepbeep'

    str = str.substring( 0, 10 ); // => length 10
    // returns 'boopbeepbe'

    str = str.substring( str.length-10 ); // => length 10
    // returns 'opbeepbeep'
    ```

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import discreteUniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-array-discrete-uniform@deno/mod.js';
import papply from 'https://cdn.jsdelivr.net/gh/stdlib-js/utils-papply@deno/mod.js';
import papplyRight from 'https://cdn.jsdelivr.net/gh/stdlib-js/utils-papply-right@deno/mod.js';
import naryFunction from 'https://cdn.jsdelivr.net/gh/stdlib-js/utils-nary-function@deno/mod.js';
import map from 'https://cdn.jsdelivr.net/gh/stdlib-js/utils-map@deno/mod.js';
import logEach from 'https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each@deno/mod.js';
import rpad from 'https://cdn.jsdelivr.net/gh/stdlib-js/string-base-right-pad@v0.0.1-deno/mod.js';

// Define a string to pad:
var str = 'beep';

// Generate random lengths:
var lens = discreteUniform( 10, str.length, str.length+10 );

// Create a function for creating padded strings:
var fcn = naryFunction( papply( papplyRight( rpad, 'b' ), str ), 1 );

// Generate padded strings:
var out = map( lens, fcn );

// Print results:
logEach( '%s', out );
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/string-base-right-pad.svg
[npm-url]: https://npmjs.org/package/@stdlib/string-base-right-pad

[test-image]: https://github.com/stdlib-js/string-base-right-pad/actions/workflows/test.yml/badge.svg?branch=v0.0.1
[test-url]: https://github.com/stdlib-js/string-base-right-pad/actions/workflows/test.yml?query=branch:v0.0.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/string-base-right-pad/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/string-base-right-pad?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/string-base-right-pad.svg
[dependencies-url]: https://david-dm.org/stdlib-js/string-base-right-pad/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/string-base-right-pad/tree/deno
[umd-url]: https://github.com/stdlib-js/string-base-right-pad/tree/umd
[esm-url]: https://github.com/stdlib-js/string-base-right-pad/tree/esm
[branches-url]: https://github.com/stdlib-js/string-base-right-pad/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/string-base-right-pad/main/LICENSE

</section>

<!-- /.links -->

<!--

@license Apache-2.0

Copyright (c) 2021 The Stdlib Authors.

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


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# conj

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return the [complex conjugate][complex-conjugate] of a single-precision complex floating-point number.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/complex-float32-conj
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var conj = require( '@stdlib/complex-float32-conj' );
```

#### conj( z )

Returns the [complex conjugate][complex-conjugate] of a single-precision complex floating-point number.

```javascript
var Complex64 = require( '@stdlib/complex-float32-ctor' );

var z = new Complex64( 5.0, 3.0 );

var v = conj( z );
// returns <Complex64>[ 5.0, -3.0 ]
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint-disable max-len -->

<!-- eslint no-undef: "error" -->

```javascript
var Complex64 = require( '@stdlib/complex-float32-ctor' );
var discreteUniform = require( '@stdlib/random-base-discrete-uniform' );
var filledarrayBy = require( '@stdlib/array-filled-by' );
var conj = require( '@stdlib/complex-float32-conj' );

function random() {
    return new Complex64( discreteUniform( -10, 10 ), discreteUniform( -10, 10 ) );
}

// Generate an array of random complex numbers:
var x = filledarrayBy( 100, 'complex64', random );
// returns <Complex64Array>

// Compute the complex conjugate of each complex number...
var z;
var i;
for ( i = 0; i < 100; i++ ) {
    z = x.get( i );
    console.log( 'conj(%s) = %s', z.toString(), conj( z ).toString() );
}
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/complex/float32/conj.h"
```

#### stdlib_complex64_conj( z )

Returns the [complex conjugate][complex-conjugate] of a single-precision complex floating-point number.

```c
#include "stdlib/complex/float32/ctor.h"
#include "stdlib/complex/float32/real.h"
#include "stdlib/complex/float32/imag.h"

stdlib_complex64_t z = stdlib_complex64( 5.0f, 2.0f );

// ...

stdlib_complex64_t v = stdlib_complex64_conj( z );

float re = stdlib_complex64_real( v );
// returns 5.0f

float im = stdlib_complex64_imag( v );
// returns -2.0f
```

The function accepts the following arguments:

-   **z**: `[in] stdlib_complex64_t` single-precision complex floating-point number.

```c
stdlib_complex64_t stdlib_complex64_conj( const stdlib_complex64_t z );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

### Examples

```c
#include "stdlib/complex/float32/conj.h"
#include "stdlib/complex/float32/real.h"
#include "stdlib/complex/float32/imag.h"
#include "stdlib/complex/float32/ctor.h"
#include <stdio.h>

int main( void ) {
    const stdlib_complex64_t x[] = {
        stdlib_complex64( 5.0f, 2.0f ),
        stdlib_complex64( -2.0f, 1.0f ),
        stdlib_complex64( 0.0f, -0.0f ),
        stdlib_complex64( 0.0f/0.0f, 0.0f/0.0f )
    };

    stdlib_complex64_t z;
    stdlib_complex64_t v;
    int i;
    for ( i = 0; i < 4; i++ ) {
        z = x[ i ];
        v = stdlib_complex64_conj( z );
        printf( "conj(%f + %fi) = %f + %fi\n", stdlib_complex64_real( z ), stdlib_complex64_imag( z ), stdlib_complex64_real( v ), stdlib_complex64_imag( v ) );
    }
}
```

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/complex-float64/conj`][@stdlib/complex/float64/conj]</span><span class="delimiter">: </span><span class="description">return the complex conjugate of a double-precision complex floating-point number.</span>
-   <span class="package-name">[`@stdlib/complex-float32/imag`][@stdlib/complex/float32/imag]</span><span class="delimiter">: </span><span class="description">return the imaginary component of a single-precision complex floating-point number.</span>
-   <span class="package-name">[`@stdlib/complex-float32/real`][@stdlib/complex/float32/real]</span><span class="delimiter">: </span><span class="description">return the real component of a single-precision complex floating-point number.</span>
-   <span class="package-name">[`@stdlib/complex-float32/reim`][@stdlib/complex/float32/reim]</span><span class="delimiter">: </span><span class="description">return the real and imaginary components of a single-precision complex floating-point number.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/complex-float32-conj.svg
[npm-url]: https://npmjs.org/package/@stdlib/complex-float32-conj

[test-image]: https://github.com/stdlib-js/complex-float32-conj/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/complex-float32-conj/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/complex-float32-conj/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/complex-float32-conj?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/complex-float32-conj.svg
[dependencies-url]: https://david-dm.org/stdlib-js/complex-float32-conj/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/complex-float32-conj/tree/deno
[deno-readme]: https://github.com/stdlib-js/complex-float32-conj/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/complex-float32-conj/tree/umd
[umd-readme]: https://github.com/stdlib-js/complex-float32-conj/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/complex-float32-conj/tree/esm
[esm-readme]: https://github.com/stdlib-js/complex-float32-conj/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/complex-float32-conj/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/complex-float32-conj/main/LICENSE

[complex-conjugate]: https://en.wikipedia.org/wiki/Complex_conjugate

<!-- <related-links> -->

[@stdlib/complex/float64/conj]: https://github.com/stdlib-js/complex-float64-conj

[@stdlib/complex/float32/imag]: https://github.com/stdlib-js/complex-float32-imag

[@stdlib/complex/float32/real]: https://github.com/stdlib-js/complex-float32-real

[@stdlib/complex/float32/reim]: https://github.com/stdlib-js/complex-float32-reim

<!-- </related-links> -->

</section>

<!-- /.links -->

# javascript-plugin-architecture-with-typescript-definitions

> Plugin architecture example with full TypeScript support

[![@latest](https://img.shields.io/npm/v/javascript-plugin-architecture-with-typescript-definitions.svg)](https://www.npmjs.com/package/javascript-plugin-architecture-with-typescript-definitions)
[![Build Status](https://github.com/gr2m/javascript-plugin-architecture-with-typescript-definitions/workflows/Test/badge.svg)](https://github.com/gr2m/javascript-plugin-architecture-with-typescript-definitions/actions)
[![Greenkeeper](https://badges.greenkeeper.io/gr2m/javascript-plugin-architecture-with-typescript-definitions.svg)](https://greenkeeper.io/)

The goal of this repository is to provide a template of a simple plugin Architecture which allows plugins to created and authored as separate npm modules and shared as official or 3rd party plugins.

Usage

```ts
import { Base } from "javascript-plugin-architecture-with-typescript-definitions";

function myFooPlugin(instance: Base) {
  return {
    foo: () => "foo"
  };
}

function myBarPlugin(instance: Base) {
  return {
    bar: () => "bar"
  };
}

const FooTest = Base.plugin(myFooPlugin);
const fooTest = new FooTest();
fooTest.foo(); // has full TypeScript intellisense

const FooBarTest = Base.plugin([myFooPlugin, myBarPlugin]);
const fooBarTest = new FooBarTest();
fooBarTest.foo(); // has full TypeScript intellisense
fooBarTest.bar(); // has full TypeScript intellisense
```

## Credit

This example was extracted from [`@octokit/core`](https://github.com/gr2m/javascript-plugin-architecture-with-typescript-definitions). The implementation was made possible by help from [@karol-majewski](https://github.com/karol-majewski) and [@dragomirtitian](https://github.com/dragomirtitian).

## LICENSE

[ISC](LICENSE)
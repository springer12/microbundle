<p align="center">
  <img src="https://i.imgur.com/LMEgZMh.gif" width="597" alt="microbundle">
</p>
<h1 align="center">
	Microbundle
	<a href="https://www.npmjs.org/package/microbundle"><img src="https://img.shields.io/npm/v/microbundle.svg?style=flat" alt="npm"></a> <a href="https://travis-ci.org/developit/microbundle"><img src="https://travis-ci.org/developit/microbundle.svg?branch=master" alt="travis"></a>
</h1>
<p align="center">The <strong>zero-configuration</strong> bundler for <em>tiny modules</em>, powered by <a href="https://github.com/rollup/rollup">Rollup</a>.</p>

---

## ✨ Features:

- **One dependency** to bundle your library using only a `package.json`
- Support for ESnext & async/await _(via [Bublé] & [Nodent])_
- Produces tiny, optimized code for all inputs
- Supports multiple entry modules _(`cli.js` + `index.js`, etc)_
- Creates multiple output formats for each entry _(<abbr title="CommonJS (node)">CJS</abbr>, <abbr title="Universal Module Definition">UMD</abbr> & <abbr title="ECMAScript Modules">ESM</abbr>)_
- Built-in Uglify compression & gzipped bundle size tracking

## 🔧 Installation

`npm i -D microbundle`

... then add the scripts to your `package.json`:

```js
{
  "scripts": {
    "build": "microbundle",
    "dev": "microbundle watch"
  }
}
```


## 📦 Usage

Microbundle includes two commands - `build` (the default) and `watch`. Neither require any options, but you can tailor things to suit your needs a bit if you like.

### `microbundle` / `microbundle build`

By default, microbundle will infer the location of your source entry file
(the root module in your program) from the `source` field in your `package.json`. It will infer the output directory and filename(s) from the `main` field. For UMD builds, microbundle will use a snake case version of the `name` field in your `package.json` for the export name; you can also specify a name via an `amdName` field or the `name` CLI option.

### `microbundle watch`

Just like `microbundle build`, but watches your source files and rebuilds on any change.

### All CLI Options

```
microbundle [entries..]

Build once and exit

Commands:
  cli.js build [entries..]  Build once and exit             [default]
  cli.js watch [entries..]  Rebuilds on any change

Options:
  --version        Show version number                      [boolean]
  --entry, -i      Entry module(s)
                                 [string] [default: <package.module>]
  --output, -o     Directory to place build files into
                  [string] [default: <dirname(package.main), build/>]
  --cwd            Use an alternative working directory
                                                [string] [default: .]
  --format         Only build specified formats
                                       [string] [default: es,cjs,umd]
  --target         Specify your target environment
                                             [string] [default: node]
  --compress       Compress output using UglifyJS
                                            [boolean] [default: true]
  --strict         Enforce undefined global context and add "use
                   strict"                           [default: false]
  --name           Specify name exposed in UMD builds        [string]
```


## 🛣 Roadmap

Here's what's coming up for Microbundle:

- [TypeScript support](https://github.com/developit/microbundle/issues/5)
- [Flowtype support](https://github.com/developit/microbundle/issues/5#issuecomment-351075881)


## 🥂 License

[MIT](https://oss.ninja/mit/developit/)


[Rollup]: https://github.com/rollup/rollup
[Bublé]: https://github.com/Rich-Harris/buble
[Nodent]: https://github.com/MatAtBread/nodent-compiler

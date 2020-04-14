# EventSource Polyfill

[![npm version](https://img.shields.io/npm/v/%40rexxars%2Feventsource-polyfill.svg?style=flat-square)](https://www.npmjs.com/package/%40rexxars/eventsource-polyfill)[![npm bundle size](https://img.shields.io/bundlephobia/minzip/%40rexxars%2Feventsource-polyfill.svg?style=flat-square)](https://bundlephobia.com/result?p=%40rexxars%2Feventsource-polyfill)

**Forked from [amvtek/EventSource](https://github.com/amvtek/EventSource)**. See [fork modification](#fork-modifications) for more details.

Provide polyfill to support EventSource in browser where it is not available.

> - Used in production
> - Tested in Internet Explorer 8 +
> - Tested in Android browser 2.1 +

## Installing

```bash
$ npm install @rexxars/eventsource-polyfill
```

## Usage (through bundler)

```js
const EventSource =
  typeof window !== 'undefined' && window.EventSource
    ? window.EventSource
    : require('@rexxars/eventsource-polyfill')

const es = new EventSource('/my-es-endpoint')
```

## Usage (drop-in script)

```html
<script src="https://unpkg.com/@rexxars/eventsource-polyfill"></script>
<script>
  var es = new EventSource('/my-es-endpoint')
</script>
```

## Fork modifications

- New package name: `@rexxars/eventsource-polyfill`
- UMD module definition - CommonJS, AMD and browser globals
- Fixed a few global variable leaks-
- Check for `window.location` before usage (fixes react native crashing)
- Stop dispatching events after closed

## License

MIT-licensed. See LICENSE.

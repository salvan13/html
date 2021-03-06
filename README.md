# @hyperapp/html

[![Travis CI](https://img.shields.io/travis/hyperapp/html/master.svg)](https://travis-ci.org/hyperapp/html) [![Codecov](https://img.shields.io/codecov/c/github/hyperapp/html/master.svg)](https://codecov.io/gh/hyperapp/html) [![npm](https://img.shields.io/npm/v/@hyperapp/html.svg)](https://www.npmjs.org/package/@hyperapp/html) [![Slack](https://hyperappjs.herokuapp.com/badge.svg)](https://hyperappjs.herokuapp.com "Join us")

Html helper functions for [Hyperapp](https://github.com/hyperapp/hyperapp). Use it as an alternative to JSX or the built-in `h()` function.

[Try it Online](https://codepen.io/hyperapp/pen/MrBgMy)

```jsx
import { h, app } from "hyperapp"
import { div, h1, button } from "@hyperapp/html"

const state = {
  count: 0
}

const actions = {
  down: () => state => ({ count: state.count - 1 }),
  up: () => state => ({ count: state.count + 1 })
}

const view = (state, actions) =>
  div([
    h1({}, state.count),
    button({ onclick: actions.down }, "ー"),
    button({ onclick: actions.up }, "＋")
  ])

const main = app(state, actions, view, document.body)
```

See [/vars.json](/vars.json) for the list of tags available to import into your file.

## Installation

Install with npm or Yarn.

<pre>
npm i <a href="https://www.npmjs.com/package/@hyperapp/html">@hyperapp/html</a>
</pre>

Then with a module bundler like [Rollup](https://github.com/rollup/rollup) or [Webpack](https://github.com/webpack/webpack), use as you would anything else.

```jsx
import { h1, div, a } from "@hyperapp/html"
```

If you prefer not to use a build system, you can load @hyperapp/html from [unpkg](https://unpkg.com/@hyperapp/html) or [jsDelivr](https://cdn.jsdelivr.net/npm/@hyperapp/html@latest/dist/html.dist.js) and it will be globally available through the `window.html` object.

```html
<!doctype html>
<html>
<body>
  <script src="https://unpkg.com/@hyperapp/html"></script>
  <script>

  const { h1, div, a } = html

  </script>
</body>
</html>
```

## License

@hyperapp/html is MIT licensed. See [LICENSE](LICENSE.md).

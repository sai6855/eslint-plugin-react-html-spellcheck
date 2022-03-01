## ESLinting to avoid inline styles

## Installation

You'll first need to install [ESLint](http://eslint.org):

```
$ npm i eslint --save-dev
```

Next, install `npm i eslint-plugin-react-html-spellcheck`:

```
$ npm install eslint-plugin-html-spellcheck --save-dev
```

**Note:** If you installed ESLint globally (using the `-g` flag) then you must also install `npm i eslint-plugin-react-html-spellcheck` globally.

## Usage

Add `react-html-spellcheck` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
  "plugins": ["react-html-spellcheck"]
}
```

Then configure the rules you want to use under the rules section.

```json
{
  "rules": {
    "react-html-spellcheck/html-spell-check": 2
  }
}
```

You can change rule from 2 to 1 which is warning or you can disable with zero.

## Rule Details

This rule aims to dissallow invalid html elements in react app.

Examples oforf **incorrect** code for this rule:

```jsx
class Component extends React.Component {
  render() {
    <spa>Hello world!!</spa>;
  }
}
class Component extends React.Component {
  render() {
    <h12>Hello world!!</h12>;
  }
}
```

Examples for **correct** code for this rule:

```jsx
class Component extends React.Component {
  render() {
    <span>Hello world!!</span>;
  }
}
class Component extends React.Component {
  render() {
    <h1>Hello world!!</h1>;
  }
}
```

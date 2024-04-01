# LAZY a.k.a. lazy-dom
A lean and mean open-source TypeScript library for building user interfaces.

## Why?
I need it. Tried other options, but nothing seems to fit. Mostly because of - at least observed - lack of KISS.

Also, lazy.

## What? (hint: KISS)
- declarative UI just by calling functions (no extra preprocessing/deps, HTML is not that good a syntax)
- no CSS, everything is handled programmatically for maximum control (CSS is used in the web target, but internally)
- ESM and other "esnext" features that make sense
- can be used for native PC/mobile/console apps (as everything goes through an interface), with or without DOM layout/renderer and JS interpreter/JIT

## How?
- just function calls to build a tree (or DAG) of UI elements
- tree nodes usually map directly to DOM elements on the web backend, but can do Virtual DOMming
- if want a different target than web, just implement the interface
- TODO: explain functional components, state, events.. state, event -> f -> state etc.

## Show me the code!
```
// example-screen.ts
import * as LAZY from 'lazy-dom'

export const VCOMP = () => {
  const onEnter = () => { console.log("Entering the dungeon!"); }; // textinput read omitted

  return LAZY.div([
    LAZY.text("Hack & Hack"),
    LAZY.textinput("Your character name.."),
    LAZY.button("Enter", onEnter)
  ])
};
```

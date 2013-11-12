gallery-soon
============

`Y.soon` is YUI's method for scheduling an asynchronous operation that runs as
soon as possible. In environments where it's supported, `soon` is a wrapper on
top of `setImmediate`. Where it's not supported, it falls back to
`setTimeout(fn, 0)`.

This module extends `soon`'s behavior to make use of faster scheduling options
provided by browsers. These methods are not designed for scheduling a task and
so their behavior may change as standards evolve.

`gallery-soon` specifically uses under the hood:

 * `MutationObserver`. A method for observing changes in DOM nodes.
 * `postMessage`. A cross-frame messaging mechanism.
 * `MessageChannel`. A friendly version of `postMessage` that doesn't pollute
 a global event.

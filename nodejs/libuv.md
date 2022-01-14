- LibUV is the core engine that powers NodeJS. It provides support for asynchronous I/O operations.
- LibUV is written in C
- LibUV provides a interface for event-driven system

- NodeJS uses libuv to handle file system, DNS, network, child process, pipes, signal handling, polling, streaming and thread pool.
- From Node 10.5, we can use worker thread in order to run Javascript in parallel
```javascript
const {
  Worker,
  isMainThread,
  setEnvironmentData,
  getEnvironmentData,
} = require('worker_threads');

if (isMainThread) {
  setEnvironmentData('Hello', 'World!');
  const worker = new Worker(__filename); // fun this file in other thread
} else {
  console.log(getEnvironmentData('Hello'));  // Prints 'World!'.
}
```

Refs: 
- https://soshace.com/16-node-js-lessons-event-loop-libuv-library-pt-1/
- https://nodejs.org/en/docs/meta/topics/dependencies/#libuv

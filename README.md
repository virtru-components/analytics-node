
#analytics-node

A node.js client for [Segment](https://segment.com) — The hassle-free way to integrate analytics into any application.

This fork supports usage with browserify using something like the following command:
```
$ browserify lib/** -o analytics-node.js -s analytics-node -r ./lib/index.js:analytics-node-req
```

Building this library using browserify allows for importing this library into other build systems such as Component.  Our
primary use-case for the ability to do this is we're then able to emit analytics in the background script for both Chrome
and Firefox without having to rely on Analytics.js side-loading scripts into the DOM and violating the Content Security
Policy (CSP) of the site we're integrating with.

This fork removes references to `superagent-proxy` and `debug` to reduce the size of the built library.

Also, there's a check for a predefined global variable named `componentRequest` specifically so that an object
matching the `superagent` API can be injected for use instead of `superagent`.  The purpose here is to allow us
to configure a `superagent` object that is provided with the FF xhr object.

## Documentation

Documentation is available at [https://segment.com/libraries/node](https://segment.com/libraries/node).

## License (MIT)

    WWWWWW||WWWWWW
     W W W||W W W
          ||
        ( OO )__________
         /  |           \
        /o o|    MIT     \
        \___/||_||__||_|| *
             || ||  || ||
            _||_|| _||_||
           (__|__|(__|__|

Copyright &copy; 2013 Segment Inc. \<friends@segment.com\>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

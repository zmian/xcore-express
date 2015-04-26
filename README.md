# xcore-express [![NPM version][npm-version-image]][npm-url] [![MIT License][license-image]][license-url]

A lightweight library that brings middlewares to handle error reporting in web applications using [Node](https://nodejs.org) and [Express](http://expressjs.com).

## Dependencies

- [Exception.io](https://github.com/zmian/Exception.io)

## Guide

A reference guide to middlewares and helper functions included in xcore.

### [Exception Classes](https://github.com/zmian/Exception.io)

<table>
  <thead>
    <tr><th>Class Name</th><th>Description</th><th>Default Message</th></tr>
  </thead>
  <tbody>
    <tr><td>Exception</td><td>The exception that is thrown when an error occurs.</td><td>No Description</td></tr>
    <tr><td>ArgumentException</td><td>The exception that is thrown when one of the arguments provided to a method is not valid.</td><td>Invalid Argument</td></tr>
    <tr><td>InvalidInputException</td><td>The exception that is thrown when one of the input provided to a method is not valid.</td><td>Invalid Input</td></tr>
    <tr><td>NotImplementedException</td><td>The exception that is thrown when a requested method or operation is not implemented.</td><td>Not Implemented</td></tr>
    <tr><td>NotSupportedException</td><td>The exception that is thrown when a requested method or operation is not supported.</td><td>Not Supported</td></tr>
    <tr><td>NotFoundException</td><td>The exception that is thrown when an attempt is made to find something that does not exist.</td><td>Not Found</td></tr>
    <tr><td>UnauthenticatedException</td><td>The exception that is thrown when a requested method or operation requires authentication.</td><td>Not Authenticated</td></tr>
    <tr><td>UnauthorizedException</td><td>The exception that is thrown when the current user is not allowed to perform an attempted operation.</td><td>Not Authorized</td></tr>
  </tbody>
</table>

### Middlewares

##### ErrorHandler

A middleware to detect error type and send a JSON response with approperiate HTTP Status code and message.

Usage:

    if (!req.isAuthenticated()) {
      throw new UnauthenticatedException("Authentication is required.");
    }


Example response:

    {
      "meta": {
        "code": 401,
        "success": false,
        "message": "Authentication is required."
      }
    }

##### Logger

A middleware to format and log errors to console.

Sample console log:

    >> GET /api/users/me
    >> [UnauthenticatedException] Authentication is required.
    >> [Error]
    >> ... stack trace ...

## Creator

- [Zeeshan Mian](https://github.com/zmian) ([@zmian](https://twitter.com/zmian))

## License

xcore-express is released under the MIT license. See LICENSE for details.

[license-image]: http://img.shields.io/badge/license-MIT-blue.svg
[license-url]: LICENSE

[npm-url]: https://www.npmjs.com/package/xcore-express
[npm-version-image]: http://img.shields.io/npm/v/xcore-express.svg

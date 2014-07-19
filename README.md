Harcon - Messaging/Service Bus for the harmonic convergence of node-based enterprise entities

[![NPM](https://nodei.co/npm/harcon.png)](https://nodei.co/npm/harcon/)


========
[harcon](https://github.com/imrefazekas/harcon) is a enterprise-level service bus for NodeJS giving high abstractation layer for interoperability between entities in a highly structured and fragmented ecosystem.

The library has a stunning feature list beyond basic rest functionality.


Just a few examples: (far from incomplete):
	... Features to be introduced


__!Note__: Harcon's concept is to introduce an clean and high abstration layer over messaging between entities. Like in case of every abstraction tool, for simple webapps or plain REST services, it can be proven as a liability.

This frameworks start to shine in a highly structured and distributed environment.


# Installation

	$ npm install harcon

## Features:

	... to be filled

## Quick setup

	var Inflicter = require('../lib/Inflicter');

	// [logger instance]
	var winston = require('winston');
	var logger = new (winston.Logger)({
		transports: [
			new (winston.transports.Console)( { level: 'debug' } )
		]
	});

	var inflicter = new Inflicter( logger );

	// define a listener function listening every message withing the context "morning"
	inflicter.addict('steve', 'morning.*', function(greetings, callback){
		callback(null, 'Leave me please!');
	} );

	// define an listener object listening every message withing the context "greet"
	var alice = {
		name: 'alice',
		handler: function(greetings1, greetings2, callback){
			callback( null, 'Hello there!' );
		}
	};
	inflicter.addicts( alice, [ 'greet.*' ], [ alice.handler ] );

	// sends a communication 'greet.everyone' with parameters and defines a callback to handle responses
	inflicter.ignite( 'catty', 'greet.everyone', 'whatsup?', 'how do you do?', function(err, res){
		console.log( err, res );
	} );

[Back to Feature list](#features)


## License

(The MIT License)

Copyright (c) 2014 Imre Fazekas

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


## Bugs

See <https://github.com/imrefazekas/harcon/issues>.


## Changelog

- 0.5.0 : initial release

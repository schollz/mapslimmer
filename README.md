# mapshrink

[![travis](https://travis-ci.org/schollz/mapshrink.svg?branch=master)](https://travis-ci.org/schollz/mapshrink) 
[![go report card](https://goreportcard.com/badge/github.com/schollz/mapshrink)](https://goreportcard.com/report/github.com/schollz/mapshrink) 
[![coverage](https://img.shields.io/badge/coverage-92%25-brightgreen.svg)](https://gocover.io/github.com/schollz/mapshrink)
[![godocs](https://godoc.org/github.com/schollz/mapshrink?status.svg)](https://godoc.org/github.com/schollz/mapshrink) 

A very simple way to exchange keys in a map for a shorter version of the key (1-2 chars).

Basically it converts something like:

```json
{"ab:cd:ef:gh:ij":-42,"zack":"something"}
```

into

```
"a":-42,"b":"something"
```

while generating a compressor that includes the values that were exchanged:

```json
{
  "To":{"a":"ab:cd:ef:gh:ij","b":"zack"}
}
```

so that they can be changed back.

## Why?

I plan on encoding the same set of 10-100 MAC addresses and this way will be a fast and efficient way to store the random sets in a database.

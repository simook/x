# Toolkit [![GoDoc](https://godoc.org/github.com/bbengfort/x?status.svg)](https://godoc.org/github.com/bbengfort/x)

**Go packages that are common to many of my projects &mdash; in the spirit of golang.org/x**

## Usage

To get these packages on your system, it's as easy as:

```
$ go get github.com/bbengfort/x/[pkg]
```

Where `[pkg]` is the name of the package you want to install. Import the packages required in your code, vendoring as necessary in order to use them in other projects.

## About

Package x hosts several packages, modules, and libraries that are common across most of my code for easy reuse. This package is very much in the spirit of [golang.org/x](https://godoc.org/-/subrepo) though it does have a slightly longer import path as a result of being hosted in my GitHub repository.

One thing that I think is important to note is that most of the subpackages in this repository are independent. That is that they are implemented and tested separately from other subpackages. Future me and anyone who would like to use this package should only go get exactly what they need and rely on the documentation on godoc and in the subpackage README.md for more information.

Generally speaking, these things are simply ported out of my other applications once I discover that they need to be reused. The x repository gives me the ability to manage them all in the same version control without jumping through all the GitHub hoops. I'm not sure this is what was intended by Golang, but managing multiple repositories with just one or two files was too much of a pain, hence this system.

## Subpackages

This is a single repository that stores many, independent subpackages. This list changes often as common code gets moved from specific projects into this repository.

- [net](net/): additional networking packages
- [peers](peers/): defines and synchronizes remote peers on the network
- [pid](pid/): manages pid files and background processes
- [noplog](noplog/): no operation logger to capture internal logging
- [stats](stats/): online computation of summary statistics
- [console](console/): hierarchical console logging
- [events](events/): event dispatcher and callbacks
- [bandit](bandit/): multi-armed bandit strategies for random choice
- [lock](lock/): provides logging to diagnose lock contention issues
- [unique](unique/): finds unique elements in a slice

### Under Development

The following subpackages are currently under development

- [cfrv](cfrv/README.md): implements conflict-free replicated versions of multiple types.
- [interval](interval/): provides an interface for time based event dispatchers.

## Tests and Benchmarks

Packages in this repository use different tests and benchmarking tools. Beyond the standard `go test` environment, most packages will probably use [ginkgo](http://onsi.github.io/ginkgo/) for BDD style testing and [gomega](http://onsi.github.io/gomega/) for matching and assertions. To install these packages:

```
$ go get github.com/onsi/ginkgo/ginkgo
$ go get github.com/onsi/gomega
```

This will install the libraries as well as the runner executables.

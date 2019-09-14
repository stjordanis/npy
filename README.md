# Npy

Save and load NumPy `npy` and `npz` files in Ruby - no Python required

:fire: Uses [Numo::NArray](https://github.com/ruby-numo/numo-narray) for blazing performance

[![Build Status](https://travis-ci.org/ankane/npy.svg?branch=master)](https://travis-ci.org/ankane/npy)

## Installation

Add this line to your application’s Gemfile:

```ruby
gem 'npy'
```

## Getting Started

### npy

`npy` files contain a single array

Save an array [master]

```ruby
arr = Numo::Int32[0...10]
Npy.save("x.npy", arr)
```

Load an `npy` file

```ruby
arr = Npy.load("x.npy")
```

Load an `npy` string

```ruby
byte_str = File.binread("x.npy")
arr = Npy.load_string(byte_str)
```

### npz

`npz` files contain multiple arrays

Save multiple arrays [master]

```ruby
x =  Numo::Int32[0...10]
y = x * 2
Npy.save_npz("mnist.npz", x: x, y: y)
```

Load an `npz` file

```ruby
arrs = Npy.load_npz("mnist.npz")
```

Get keys

```ruby
arrs.keys
```

Get an array

```ruby
arrs["x"]
```

Arrays are lazy loaded for performance

## Resources

- [npy format](https://docs.scipy.org/doc/numpy/reference/generated/numpy.lib.format.html#module-numpy.lib.format)
- [NumPy data types](https://docs.scipy.org/doc/numpy/user/basics.types.html)
- [Numo::NArray docs](https://ruby-numo.github.io/narray/narray/Numo/NArray.html)

## History

View the [changelog](https://github.com/ankane/npy/blob/master/CHANGELOG.md)

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/ankane/npy/issues)
- Fix bugs and [submit pull requests](https://github.com/ankane/npy/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features

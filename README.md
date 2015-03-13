# Torch Developer Guide

[![Join the chat at https://gitter.im/Atcold/Torch-Developer-Guide](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Atcold/Torch-Developer-Guide?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This repository tries to provide some advanced tricks with [Torch7](http://torch.ch/) explained easily

## *FFI* series

[*LuaJIT*](http://luajit.org/) [*FFI library*](http://luajit.org/ext_ffi.html) provides an incredible easy way to call external *C* functions and use *C* data structures from pure Lua code.
The *FFI series* will provide several working examples of playing with *C* from within *Torch*, taking for granted no prior knowledge of building `.so` libraries, using `Makefile` or tackling *Tensors* pointers.

 1. [*FFI* and `.so` library](FFI-so/README.md)

## Debugging

If you found yourself using several `print()` and `io.read()` around the code with the purpose of finding out what's going on, well… there's a better and more efficient way: using a *debugger*.
There are few alternatives, but we'll start with the easiest one: a command-line debugger.

 1. [MobDebug](MobDebug/README.md) (command-line)


## Designing Modules

One of the major concerns of a new developer is how to write and design new modules for Torch, especially the `nn` package. Modules, based on their functionality, parameters and code, can be categorized as the following:

* Modules that act as a function on the input and do not have any parameters to optimize
* Modules that have parameters to be optimized and have been written in pure **Lua** 
* Modules that have optimizataion parameters but have been written in C
* Finaally, Modules that have parameters and use CUDA code for GPU acceleration. 

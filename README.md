# evm-legacy: the 0.x line of SputnikVM, the Rust Ethereum Virtual Machine

[![Build Status](https://github.com/rust-ethereum/evm-legacy/actions/workflows/rust.yml/badge.svg)](https://github.com/rust-ethereum/evm-legacy/actions/workflows/rust.yml)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](./LICENSE)

This repository is the 0.x line of SputnikVM. It was the `v0.x` branch of [rust-ethereum/evm](https://github.com/rust-ethereum/evm), and it keeps that branch's code and history. The 0.x line's fixes and releases happen here.

New projects should use the 1.x line instead: the crate [`evm`](https://crates.io/crates/evm), from [rust-ethereum/evm](https://github.com/rust-ethereum/evm).

## Moving from `evm` 0.x

Releases up to 0.43.4 were published as the crate `evm`. From 0.44.0 on, the main crate is published as `evm-legacy`. Its library is still named `evm`, so code keeps its `use evm::...` lines, and only the dependency changes:

```toml
[dependencies]
evm-legacy = "0.44"
```

The crates `evm-core`, `evm-gasometer` and `evm-runtime` keep their names, and their releases also come from this repository.

## Crates

| Name          | Description                                                     | Crates.io                                                                                                 | Documentation                                                                              |
|---------------|:---------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------:|
| evm-legacy    | Main library that re-exports most things, imported as `evm`.    | [![crates.io](https://img.shields.io/crates/v/evm-legacy.svg)](https://crates.io/crates/evm-legacy)       | [![Documentation](https://docs.rs/evm-legacy/badge.svg)](https://docs.rs/evm-legacy)       |
| evm-core      | Core library defining the basic execution rules.                | [![crates.io](https://img.shields.io/crates/v/evm-core.svg)](https://crates.io/crates/evm-core)           | [![Documentation](https://docs.rs/evm-core/badge.svg)](https://docs.rs/evm-core)           |
| evm-gasometer | Integration of Ethereum gas rules.                              | [![crates.io](https://img.shields.io/crates/v/evm-gasometer.svg)](https://crates.io/crates/evm-gasometer) | [![Documentation](https://docs.rs/evm-gasometer/badge.svg)](https://docs.rs/evm-gasometer) |
| evm-runtime   | Runtime defining interface for block, transaction, and storage. | [![crates.io](https://img.shields.io/crates/v/evm-runtime.svg)](https://crates.io/crates/evm-runtime)     | [![Documentation](https://docs.rs/evm-runtime/badge.svg)](https://docs.rs/evm-runtime)     |

## Features

* **Standalone** - can be launched as an independent process or integrated into other apps
* **Universal** - supports different Ethereum chains, such as ETC, ETH or private ones
* **Stateless** - only an execution environment connected to independent State storage
* **Fast** - main focus is on performance
* written in Rust, can be used as a binary, cargo crate or shared
  library

### Feature Flags

SputnikVM provides optional feature flags to enable specific functionalities:

- `allow_explicit_address`
Enables the `transact_create_force_address` method, allowing contract creation with a predefined address.
- `with-codec`
- `with-serde`
- `tracing`
- `force-debug`

## Dependencies

Ensure you have at least `rustc 1.51.0 (2fd73fabe 2021-03-23)`. Rust 1.50.0 and
before are not supported.

## Documentation

* [Latest release documentation](https://docs.rs/evm-legacy)
* [Documentation of the releases up to 0.43.4, as `evm`](https://docs.rs/evm/0.43.4)

## Build from sources

SputnikVM is written in Rust. If you are not familiar with Rust, please
see the [starting documentation](https://www.rust-lang.org/learn).

### Build

To start working with SputnikVM you'll
need to install [rustup](https://www.rustup.rs/), then you can do:

```bash
$ git clone https://github.com/rust-ethereum/evm-legacy.git
$ cd evm-legacy
$ cargo build --release --all
```

## License

Apache 2.0

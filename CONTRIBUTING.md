# Contributing

## Fast local builds (fork)

Install [Soldr](https://github.com/zackees/soldr), then run Cargo through the
fork's wrapper:

```sh
tools/soldr check --locked
tools/soldr build --locked
tools/soldr test --locked
```

The wrapper pins Rust 1.94.1 through `RUSTUP_TOOLCHAIN` and lets Soldr cache
compiler outputs across rebuilds. Set `RUSTUP_TOOLCHAIN` explicitly if you need
another compiler. It leaves `rust-toolchain.toml` absent so the existing CI
matrix can continue testing both stable Rust and the crate's minimum version.
On Linux, the wrapper uses `mold` if it is installed to shorten test-binary
links; other hosts use their normal linker.
Keep the same checkout and `target/` directory for the fastest incremental
rebuilds. For a release artifact, pass `--release` to `tools/soldr build`.

## License

By contributing to this project, you agree that your contributions will be licensed under the project's license (MIT OR Apache-2.0).

Thank you for your contribution!

## Looking for issues?

https://github.com/fjall-rs/fjall/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22

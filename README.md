# What's mdub?

This is a fork/translation of Doug Borg's [gdub][] project to support the
[maven wrapper][], which was designed to be analogous to the gradle wrapper.

mdub (`mw` on the command line) is a `maven` / `mvn` wrapper, `mw` invokes
`./mvnw` on projects where one is configured, and falls back to use the `mvn`
from the `$PATH` if a wrapper is not available.

[gdub]: https://github.com/dougborg/gdub
[maven wrapper]: https://github.com/takari/maven-wrapper

# Installation

Check out a copy of the mdub repository. Then, either add the mdub `bin`
directory to your `$PATH`, or run the provided `install` command with the
location to the prefix in which you want to install mdub. The default prefix is
`/usr/local`.

For example, to install mdub into `/usr/local/bin`:

```bash
git clone https://github.com/stormbeta/mdub.git
cd mdub
./install
```

Note: you may need to run `./install` with `sudo` if you do not have
permission to write to the installation prefix.

## Aliasing the `mvn` command
For maximum fidelity add a `mvn` alias to `mw` to your shell's configuration
file.

Example *bash*:

```bash
echo "alias mvn=mw" >> ~/.bashrc
source ~/.bashrc
```

From now on you can just type `mvn ...` from wherever you are and `mw` takes
care of the rest. Happiness ensues!

# Why mdub?

Largely the same reasons as the gdub script, which you can read
[here](https://github.com/dougborg/gdub#why-gdub). In particular, this allows
you to run maven from any subdirectory of your project and have it use the
logical pom to run.

# Ravelin tools homebrew tap

This repository contains MacOS Homebrew formulas for various tools used at Ravelin but not available in main repository. At this moment it contains only Protobuf at specific version. That may, or may not, change in future. 😀

# For users

In this example we'll use Protobuf at specific version as we need that to generate Go files.

## How to install formula?

Add tap on you local machine if you haven't already.

```
brew tap unravelin/tools
```

Search for formula.

```
brew search protobuf
```

Result may be something like this.

```
==> Formulae
protobuf      protobuf@3.6       unravelin/tools/protobuf@3.17.3
protobuf-c    swift-protobuf
```

As you can see, it picked up the version from our tap. Now, you can install it.

```
brew install unravelin/tools/protobuf@3.17.3
```

_Note: Brew needs to build it from source on your machine so it'll take couple of minutes. You need to be patient. Took me close to 10 min to complete._

After that, try to confirm `protoc` version.

```
protoc --version
```

It should result with below.

```
libprotoc 3.17.3
```

That's it, really. You're good to go! 🚀

## How to upgrade formula?

When you update all repos the usual way, it will also update Ravelin's tap. Whenever new version appears, you will see it while searching.

Unfortunately, since we need to keep Protobuf at specific version. That means, each version is a separate formula. All you need to is - uninstall current version.
```
unravelin/tools/protobuf@x.x.x
```
And then install the version you need.
```
unravelin/tools/protobuf@y.y.y
```
Again, this must be built from source so it will take time.

## How to remove your tap?

If you ever need to remove the tap, just type below.
```
brew untap unravelin/tools
```

# For maintainers

When you first add the tap on your local machine, Brew will clone the repository for you. In my case it went to `/usr/local/Homebrew/Library/Taps/unravelin/homebrew-tools`.

```
brew tap unravelin/tools
```

```
...
==> Tapping unravelin/tools
Cloning into '/usr/local/Homebrew/Library/Taps/unravelin/homebrew-tools'...
...
```

_Note: Tap `unravelin/tools` is essentially shortcut to `https://github.com/unravelin/homebrew-tools`._

When you need to add new version of Protobuf formula, all you need to do is.

```
brew extract --version=x.x.x protobuf unravelin/tools
```

You'll notice new formula has been added to your local repository. All you need to do is to commit changes and push.

From now on, everyone can install new version after updating their taps. 🎉

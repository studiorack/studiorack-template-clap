# studiorack-template-clap
![Release](https://github.com/studiorack/studiorack-template-clap/workflows/Release/badge.svg)

Audio plugin starter template using Clever Audio Plugin SDK to build binaries using:

* Bash
* CMake 3.4.x
* Clever Audio Plugin 1.0.x


## Installation

Install CMake and Xcode using:

    brew install automake autoconf ninja cmake
    xcode-select --install

Check you have the correct dependencies installed:

    cmake -version
    xcodebuild -version

Ensure all git submodules are initialized:

    git submodule update --init --recursive


## Usage

Make all your plugin development changes in the source folder at:

    ./src

Ensure you also update the preview image and audio files:

    ./src/assets/name.png
    ./src/assets/name.wav


## Testing your plugin

Todo


## Build (manual)

Compile a development version of the plugin using:

    cmake \
      -G "Ninja Multi-Config" \
      -DCMAKE_EXPORT_COMPILE_COMMANDS=true \
      -DCLAP_BUILD_TESTS=true \
      -S ./sdk \
      -B ./build
    cmake --build ./build --config Debug --target "clap-tests"


## Build (automatic)

Release a plugin version on GitHub by simply creating a version tag:

    git tag v0.0.1
    git push && git push origin --tags

This will run an automated build and release process on GitHub Actions:

    .github/workflows/release.yml


## Resources & guides

* [Clap SDK and examples](https://github.com/free-audio/clap)


## Contact

For more information please contact kmturley

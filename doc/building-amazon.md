## Building Seastar on Amazon Linux

### Building Seastar on Amazon Linux 2

Installing required packages:
```
sudo ./install-dependencies.sh

./configure.py --cflags="-fvisibility=default" --mode=release --cook dpdk --cook fmt --cook ragel --cook yaml-cpp --cook Boost --cook c-ares --cook cryptopp
```

To compile Seastar use:
```
ninja-build -C build/release
```

In case there are compilation issues, especially like ```g++: internal compiler error: Killed (program cc1plus)``` try giving more memory to gcc, either by limiting the amount of threads ( -j1 ) and/or allowing at least 4g ram to your machine

# DJL - MXNet engine implementation

## Overview

This module contains the MXNet implementation of the Deep Java Library (DJL) EngineProvider.

We don't recommend that developers use classes in this module directly. Use of these classes will couple your code with MXNet and make switching between frameworks difficult. Even so, developers are not restricted from using engine-specific features. For more information, see [NDManager#invoke()](https://javadoc.io/static/ai.djl/api/0.5.0/ai/djl/ndarray/NDManager.html#invoke-java.lang.String-ai.djl.ndarray.NDList-ai.djl.ndarray.NDList-ai.djl.util.PairList-).

## Documentation

The latest javadocs can be found on the [djl.ai website](https://javadoc.io/doc/ai.djl.mxnet/mxnet-engine/latest/index.html).

You can also build the latest javadocs locally using the following command:

```sh
./gradlew javadoc
```
The javadocs output is built in the `build/doc/javadoc` folder.


## Installation
You can pull the MXNet engine from the central Maven repository by including the following dependency:

```xml
<dependency>
    <groupId>ai.djl.mxnet</groupId>
    <artifactId>mxnet-engine</artifactId>
    <version>0.5.0</version>
    <scope>runtime</scope>
</dependency>
```

Besides the `mxnet-engine` library, you may also need to include the MXNet native library in your project.
All current provided MXNet native libraries are built with [MKLDNN](https://github.com/intel/mkl-dnn).

Choose a native library based on your platform and needs:

### Automatic (Recommended)

We offer an automatic option that will download the jars the first time you run DJL.
It will automatically determine the appropriate jars for your system based on the platform and GPU support.

```xml
    <dependency>
      <groupId>ai.djl.mxnet</groupId>
      <artifactId>mxnet-native-auto</artifactId>
      <version>1.7.0-a</version>
      <scope>runtime</scope>
    </dependency>
```

### macOS
For macOS, you can use the following library:

- ai.djl.mxnet:mxnet-native-mkl:1.7.0-a:osx-x86_64

    This package takes advantage of the Intel MKL library to boost performance.
```xml
    <dependency>
      <groupId>ai.djl.mxnet</groupId>
      <artifactId>mxnet-native-mkl</artifactId>
      <classifier>osx-x86_64</classifier>
      <version>1.7.0-a</version>
      <scope>runtime</scope>
    </dependency>
```

### Linux
For the Linux platform, you can choose between CPU, GPU. If you have Nvidia [CUDA](https://en.wikipedia.org/wiki/CUDA)
installed on your GPU machine, you can use one of the following library:

GPU:
- ai.djl.mxnet:mxnet-native-cu102mkl:1.7.0-a:linux-x86_64 - CUDA 10.2
- ai.djl.mxnet:mxnet-native-cu101mkl:1.7.0-a:linux-x86_64 - CUDA 10.1
- ai.djl.mxnet:mxnet-native-cu92mkl:1.7.0-a:linux-x86_64 - CUDA 9.2

```xml
    <dependency>
      <groupId>ai.djl.mxnet</groupId>
      <artifactId>mxnet-native-cu102mkl</artifactId>
      <classifier>linux-x86_64</classifier>
      <version>1.7.0-a</version>
      <scope>runtime</scope>
    </dependency>
```

```xml
    <dependency>
      <groupId>ai.djl.mxnet</groupId>
      <artifactId>mxnet-native-cu101mkl</artifactId>
      <classifier>linux-x86_64</classifier>
      <version>1.7.0-a</version>
      <scope>runtime</scope>
    </dependency>
```

```xml
    <dependency>
      <groupId>ai.djl.mxnet</groupId>
      <artifactId>mxnet-native-cu92mkl</artifactId>
      <classifier>linux-x86_64</classifier>
      <version>1.7.0-a</version>
      <scope>runtime</scope>
    </dependency>
```

CPU
- ai.djl.mxnet:mxnet-native-mkl:1.7.0-a:linux-x86_64

```xml
    <dependency>
      <groupId>ai.djl.mxnet</groupId>
      <artifactId>mxnet-native-mkl</artifactId>
      <classifier>linux-x86_64</classifier>
      <scope>runtime</scope>
      <version>1.7.0-a</version>
    </dependency>
```

### Windows

For the Windows platform, you can use CPU package. MXNet windows GPU native
library size are large, we no longer provide GPU package, instead you have to
use [Automatic](#automatic-(recommended)) package.

GPU
- ai.djl.mxnet:mxnet-native-auto:1.7.0-a

    This package supports CUDA 9.2, CUDA 10.1 and CUDA 10.2 for Windows.

CPU
- ai.djl.mxnet:mxnet-native-mkl:1.7.0-a:win-x86_64

```xml
    <dependency>
      <groupId>ai.djl.mxnet</groupId>
      <artifactId>mxnet-native-mkl</artifactId>
      <classifier>win-x86_64</classifier>
      <scope>runtime</scope>
      <version>1.7.0-a</version>
    </dependency>
```

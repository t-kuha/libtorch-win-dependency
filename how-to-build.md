# How to build libtorch depedencies fow Windows

***

## snappy

```msdos
> mkdir _build
> cd _build

> cmake .. -Ax64 -Thost=x64 -DCMAKE_INSTALL_PREFIX=D:\nn\pytorch\libtorch-win-dependency
> cmake --build . --config Release --target install
```

## leveldb

```msdos
> mkdir _build
> cd _build

> cmake .. -Ax64 -Thost=x64 -DCMAKE_INSTALL_PREFIX=D:\nn\pytorch\libtorch-win-dependenc -DLEVELDB_BUILD_TESTS=OFF -DLEVELDB_BUILD_BENCHMARKS=OFF
> cmake --build . --config Release --target install
```

## LMDB

Copy CMakeFiles.txt into lmdb-LMDB_0.9.24\libraries\liblmdb

```msdos
> mkdir _build
> cd _build

> cmake .. -Ax64 -Thost=x64 -DCMAKE_INSTALL_PREFIX=D:\nn\pytorch\libtorch-win-dependency
> cmake --build . --config Release --target install
```

## gflags

```msdos
> mkdir _build
> cd _build

> cmake .. -Ax64 -Thost=x64 -DCMAKE_INSTALL_PREFIX=D:\nn\pytorch\libtorch-win-dependency -DBUILD_SHARED_LIBS=ON -DBUILD_STATIC_LIBS=ON
> cmake --build . --config Release --target install
```

## glog

- Build gflags first

```msdos
> mkdir _build
> cd _build

> cmake .. -Ax64 -Thost=x64 -DCMAKE_INSTALL_PREFIX=D:\nn\pytorch\libtorch-win-dependency -DBUILD_TESTING=OFF -DBUILD_SHARED_LIBS=ON
> cmake --build . --config Release --target install
```

## ZeroMQ

```msdos
> mkdir _build
> cd _build
> cmake .. -Ax64 -Thost=x64 -DCMAKE_INSTALL_PREFIX=D:\nn\pytorch\libtorch-win-dependency -DBUILD_TESTS=OFF -DWITH_DOCS=OFF
> cmake --build . --config Release --target install
```

## OpenCV

```msdos
> mkdir _build
> cd _build
> cmake .. -Ax64 -Thost=x64 -DCMAKE_INSTALL_PREFIX=D:\nn\pytorch\libtorch-win-dependency ^
-DBUILD_WITH_STATIC_CRT=ON ^
-DBUILD_TESTS=OFF ^
-DBUILD_opencv_apps=OFF ^
-DBUILD_opencv_calib3d=OFF ^
-DBUILD_opencv_dnn=OFF ^
-DBUILD_opencv_features2d=OFF ^
-DBUILD_opencv_flann=OFF ^
-DBUILD_opencv_java_bindings_generator=OFF ^
-DBUILD_opencv_js=OFF ^
-DBUILD_opencv_ml=OFF ^
-DBUILD_opencv_objdetect=OFF ^
-DBUILD_opencv_photo=OFF ^
-DBUILD_opencv_python2=OFF ^
-DBUILD_opencv_python_bindings_generator=OFF ^
-DBUILD_opencv_python_tests=OFF ^
-DBUILD_opencv_shape=OFF ^
-DBUILD_opencv_stitching=OFF ^
-DBUILD_opencv_superres=OFF ^
-DBUILD_opencv_ts=OFF ^
-DBUILD_opencv_video=ON ^
-DBUILD_opencv_videoio=ON ^
-DBUILD_opencv_videostab=OFF ^
-DBUILD_opencv_world=OFF
> cmake --build . --config Release --target install
```

## FFMPEG

- Launch Visual Studio command prompt

```msdos
:: Use MSDOS's environment variables in MSYS
> set MSYS2_PATH_TYPE=inherit

:: Launch MSYS shell
> D:\Program\msys64\msys2_shell.cmd
```

- In MSYS shell

```shell-session
$ ./configure --toolchain=msvc --enable-shared --prefix=$(pwd)/_install
$ make -j$(nproc)
$ make install
```

- Copy files in _install to the destination directory

## RocksDB

```msdos
> mkdir _build
> cd _build
> cmake .. -Ax64 -Thost=x64 -DWITH_TESTS=OFF -DROCKSDB_LITE=ON

:: No INSTALL target
> cmake --build . --config Release
```

- Copy files manually

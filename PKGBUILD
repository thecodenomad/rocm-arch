# Maintainer: Jakub Okoński <jakub@okonski.org>
pkgname=clang-ocl
pkgver=0.2.0.688fe5d
pkgrel=1
pkgdesc="OpenCL compilation with clang compiler."
arch=('x86_64')
url="https://github.com/RadeonOpenCompute/clang-ocl"
license=('unknown')
makedepends=(git cmake ninja hcc)
source=("git+https://github.com/RadeonOpenCompute/clang-ocl.git#commit=688fe5d98b3d6a06838f10d3a7db951c288c0f54")
md5sums=('SKIP')

build() {
  mkdir -p "$srcdir/build"
  cd "$srcdir/build"
  cmake -DCMAKE_BUILD_TYPE=Release \
        -DOPENCL_ROOT=/opt/rocm/hcc \
        -DCMAKE_INSTALL_PREFIX="$pkgdir/opt/rocm" \
        -G Ninja \
        "$srcdir/clang-ocl"
  ninja
}

package() {
  ninja -C "$srcdir/build" install
}


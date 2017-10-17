# Maintainer: John Dewey <john@dewey.ws>
pkgname="goenv"
pkgver=1.5.0
pkgrel=1
pkgdesc='desc "Go version management'
url='https://github.com/syndbg/goenv'
arch=('any')
license=('MIT')
makedepends=()
depends=()
checkdepends=()
optdepends=('git: to install dev builds')
source=("https://github.com/syndbg/goenv/archive/${pkgver}.zip")
sha256sums=('841fe442e8407efa0db39f7e572a3082cce5f6b0c59c2cca4e4c8e4f3d78e0cc')

package() {
  mkdir -p "${pkgdir?}"/{opt/goenv,usr/bin}
  cd "${srcdir?}/$pkgname-$pkgver" || return
  cp -a -- * "$pkgdir"/opt/goenv
  ln -s /opt/goenv/libexec/goenv "$pkgdir/usr/bin/goenv"

  for bin in goenv-{,un}install go-build; do
    ln -s /opt/goenv/plugins/go-build/bin/"$bin" "$pkgdir/usr/bin/$bin"
  done
}

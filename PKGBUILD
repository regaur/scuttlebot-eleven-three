# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=scuttlebot-eleven-three
pkgver=11.3.5
pkgrel=1
pkgdesc="Secure scuttlebutt server 11.3.x"
arch=('x86_64')
url=""
license=('MIT')
groups=()
depends=('nodejs=10.8.0-2')
makedepends=('git' 'npm')
checkdepends=()
optdepends=()
provides=("scuttlebot")
conflicts=("scuttlebot")
replaces=()
source=('sbot@.service')

sha256sums=('09493f9f3edc39ea61c58da30ab2b1df803b65734437e946d1276c0c74d1a5ca')

package () {
  install -Dm 644 -t "${pkgdir}/usr/lib/systemd/system" "sbot@.service"
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" 'ssbc/scuttlebot-release#11.3.x-fixups'
}

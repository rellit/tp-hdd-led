# Maintainer: Tim Herbst <mail@timherbst.de>
pkgname=tp-hdd-led
pkgver=1.0.4
pkgrel=1
epoch=
pkgdesc="Use Thinkpad Think-LED as HDD led"
arch=(i686 x86_64)
url="http://timherbst.de"
license=('MIT')
groups=()
depends=('systemd' 'python')
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=(https://raw.githubusercontent.com/herbstmensch/tp-hdd-led/master/tp-hdd-led.py
        https://raw.githubusercontent.com/herbstmensch/tp-hdd-led/master/tp-hdd-led.service
        https://raw.githubusercontent.com/herbstmensch/tp-hdd-led/master/LICENSE)
noextract=()

md5sums=('d897ecad631d82a7ba5e6a20486b75e8'
         '78e2fcca40a023ed6cf702604ea39d87'
         'f366d0875d3b869f206f16a06c345f40')
package() {
  cd "${srcdir}"
  mkdir -p $pkgdir/usr/lib/systemd/system
  mkdir -p $pkgdir/usr/share/$pkgname
  mkdir -p $pkgdir/usr/share/licenses/$pkgname
  install -m644 hdd_led.service "${pkgdir}/usr/lib/systemd/system"
  install -m755 hdd_led.py "${pkgdir}/usr/share/${pkgname}"
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

note() {
    printf "${blue}==>${yellow} NOTE:${bold} $1${all_off}\n"
}

post_install() {
    note "Start with     'systemctl start hdd_led'\nAutostart with 'systemctl enable tp-hdd-led'"
}

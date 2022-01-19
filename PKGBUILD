# Maintainer: SamuelNihBos <samuelnihbos@disroot.org>
pkgname=dmenu-samuel
pkgver=1.0.r22.8695f74
pkgrel=1
epoch=
pkgdesc="Patched dmenu for my daily needs."
arch=(x86_64)
url="https://www.github.com/samuelnihbos/dmenu.git"
license=('MIT')
groups=()
depends=(ttf-hack ttf-joypixels ttf-iosevka-nerd)
makedepends=(git)
checkdepends=()
optdepends=()
provides=(dmenu)
conflicts=(dmenu)
replaces=()
backup=()
options=()
install=
changelog=
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
	cd "${_pkgname}"
    printf "5.0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd dmenu-samuel
    make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
    cd dmenu-samuel  
    mkdir -p ${pkgdir}/opt/${pkgname}
    cp -rf * ${pkgdir}/opt/${pkgname}
    make PREFIX=/usr DESTDIR="${pkgdir}" install
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -Dm644 README.org "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}
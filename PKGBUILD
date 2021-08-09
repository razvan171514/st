# Maintainer: Your Name <youremail@domain.com>
pkgname=st-razvan-git
pkgver=0.8.4.r8.f0b1442
pkgrel=1
epoch=
pkgdesc="Personal st build. The list of patches is found in the github reopsitory on the file entitled list-of-patches.readme"
arch=(x86_64)
url="https://github.com/razvan171514/st.git"
license=('MIT')
groups=()
depends=()
makedepends=(git make)
checkdepends=()
optdepends=()
provides=(st)
conflicts=(st)
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
	cd st
	printf "0.8.4.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd st
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd st
	mkdir -p ${pkgdir}/opt/${pkgname}
	cp -rf * ${pkgdir}/opt/${pkgname}
	make PREFIX=/usr DESTDIR="${pkgdir}" clean install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 README "${pkgdir}/usr/share/doc/${pkgname}/README"
}

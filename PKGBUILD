# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>

_git=false
_py="python"
_pkgname=stear-keyboard
pkgname="${_pkgname}"
pkgver=0.1
pkgrel=2
pkgdesc="Simple remote keyboard"
arch=(
  'any'
)
_ns='tallero'
_http="https://gitlab.gnome.org"
url="${_http}/${_ns}/${_pkgname}"
license=(
  AGPL3
)
depends=(
 "${_py}-appdirs"
 "${_py}-keyboard"
 "${_py}-gnupg"
 "${_py}-setproctitle"
)
makedepends=(
 "${_py}-setuptools"
)
sha256sums=()
source=()
if [[ "${_git}" == 'true' ]]; then
  makedepends+=(
    "git"
  )
  source+=(
    "${_pkgname}-${pkgver}::git+${url}#tag=${pkgver}"
  )
  sha256sums+=(
    'SKIP'
  )
elif [[ "${_git}" == 'false' ]]; then
  source+=(
    "${url}/-/archive/${pkgver}/${_pkgname}-${pkgver}.tar.gz"
  )
  sha256sums+=(
    'f0694c7845b2f4effd1e1a95a7aae2ba32192c897732033685a7508cc0ca98cf'
  )
fi

package() {
  cd \
    "${_pkgname}-${pkgver}"
  "${_py}" \
    setup.py \
      install \
        --root="${pkgdir}" \
	--optimize=1
}

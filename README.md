# AWS Simple Icons for dia
This provides `AWS Shapes` for [Dia](https://wiki.gnome.org/Apps/Dia) which 
programatically creates icons from the iconset provided by AWS at
[AWS Simple Icons for Architecture Diagrams](https://aws.amazon.com/architecture/icons/).

This is a fork and slight rewrite of [pieterlange/aws-dia-shapes](https://github.com/pieterlange/aws-dia-shapes)
which in turn appears to be a fork of [kazuhisya/dia-aws-simple-icons](https://github.com/kazuhisya/dia-aws-simple-icons).

This fork/rewrite takes my work of figuring out dependencies, reverse-engineering
and ironing out issues with the original [./do-it.sh](https://github.com/pieterlange/aws-dia-shapes/blob/master/doit.sh)
script and so should produce a more reliable build.

The `AWS shapes` shape sheet is generated from a template (see [makefile](https://github.com/shalomb/aws-dia-shapes/blob/master/makefile#L51))
and is currently  installed into `~/.dia/{shapes,sheets}`.
No system install is supported but PRs welcome (see TODO list below).


## System Requirements

- [Dia](https://wiki.gnome.org/Apps/Dia)
- [convert](https://packages.debian.org/stretch/imagemagick)       from [ImageMagick](https://www.imagemagick.org/)
- [convert-im6](https://packages.debian.org/stretch/imagemagick)   from [ImageMagick](https://www.imagemagick.org/)
- [make](https://packages.debian.org/stretch/make)          from [Gnu Make](https://www.gnu.org/software/make/)
- [rsvg-convert](https://packages.debian.org/stretch/librsvg2-bin)  from [libRSVG](https://wiki.gnome.org/Projects/LibRsvg)
- [unzip](https://packages.debian.org/stretch/unzip)
- [wget](https://packages.debian.org/stretch/wget)

## Usage

Build and install the `AWS Shapes`
```bash
  git clone https://github.com/shalomb/aws-dia-shapes.git
  cd aws-dia-shapes
  ./configure
  make clean
  make
  make install
```

_NOTE_ : A restart of dia may be needed once the above steps are complete. A
         new sheet named `AWS Shapes` should be present under the sheets menu
         under `Other sheets >`.

## Licence

- [AWS Simple Icons for Architecture Diagrams](https://aws.amazon.com/architecture/icons/)
    - No license specified.

## See Also
- [Introducing AWS Simple Icons for your Architecture Diagrams | AWS Blog](https://aws.amazon.com/jp/blogs/aws/introducing-aws-simple-icons-for-your-architecture-diagrams/)
- [How do I import custom SVG shapes into Dia? - Stack Overflow](https://stackoverflow.com/questions/4643243/how-do-i-import-custom-svg-shapes-into-dia)
- [How to add a new shape to Dia](http://dia-installer.de/howto/create_shape/index.html.en)
- [pieterlange/aws-dia-shapes/blob/master/makefile](https://github.com/pieterlange/aws-dia-shapes/blob/master/makefile)
- [cipriancraciun/mosaic-blueprints/blob/master/dia-shapes/aws/makefile](https://github.com/cipriancraciun/mosaic-blueprints/blob/master/dia-shapes/aws/makefile)

## TODO
- Some icons turn out to be grayscale and/or colours are not preserved.
- Allow `./configure` to do a system install.
- Build debian packages via [CheckInstall - Debian Wiki](https://wiki.debian.org/CheckInstall)


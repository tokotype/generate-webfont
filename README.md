# Generate Webfont

A Guide to installing:
- WOFF CLI converter (with ZOPFLI compression)
- WOFF2 CLI converter (with Brotli compression)

# Prerequisites

- [snft2woff](https://github.com/bramstein/sfnt2woff-zopfli)
- [Google's woff2 tools](https://github.com/google/woff2)

# Instructions

## WOFF CLI converter (with ZOPFLI compression)

Compile and install `sfnt2woff1` by pasting all of the following code into a terminal:

```
git clone https://github.com/bramstein/sfnt2woff-zopfli.git woff &&
cd woff &&
make &&
chmod 755 woff2sfnt-zopfli sfnt2woff-zopfli &&
mv woff2sfnt-zopfli sfnt2woff-zopfli /usr/local/bin &&
rm -rf ../woff
```

Once the tool has been compiled and installed, convert a TTF or OTF file to WOFF by running:

```
sfnt2woff-zopfli myfont.ttf
```

To convert all files in the current directory to WOFF:

```
for i in *; \
do sfnt2woff-zopfli.exe "$i"; \
done
```

## WOFF2 CLI converter (with Brotli compression)

Compile and install Google's woff2 tools by pasting all of the following code into a terminal:

```
git clone --recursive https://github.com/google/woff2.git &&
cd woff2 &&
make clean all &&
mv woff2_compress woff2_decompress woff2_info /usr/local/bin &&
rm -rf ../woff2
```

Once the tool has been compiled and installed, convert a single TTF or OTF file to WOFF2 by running:

```
woff2_compress myfont.ttf
```
To convert all files in the current directory to WOFF2:

```
for i in *; \
do woff2_compress.exe "$i"; \
done
```
Decompress
```
woff2_decompress myfont.woff2
```

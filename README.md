# Boost subset for VG

This repo contains the subset of Boost needed to build the Boost-depending things that vg depends on.

It was extracted by cloning the full Boost into vg at `deps/boost` and then running:

```
./bootstrap.sh
./b2 tools/bcp

mkdir ./subset 
./dist/bin/bcp --scan --boost=. ../vowpal_wabbit/vowpalwabbit/*.cc ../vowpal_wabbit/vowpalwabbit/*.h ./subset
./dist/bin/bcp config build ./subset
```

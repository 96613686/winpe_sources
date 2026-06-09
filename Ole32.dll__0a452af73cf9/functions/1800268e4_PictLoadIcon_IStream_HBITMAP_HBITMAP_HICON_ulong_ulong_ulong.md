# _PictLoadIcon(IStream *,HBITMAP__ * *,HBITMAP__ * *,HICON__ * *,ulong,ulong,ulong)

- ea: `0x1800268e4`
- end: `0x180026d63`
- name: `?_PictLoadIcon@@YAJPEAUIStream@@PEAPEAUHBITMAP__@@1PEAPEAUHICON__@@KKK@Z`
- size: `1151`
- prototype: `HRESULT __fastcall(IStream *pstm, HBITMAP__ **phbmpXor, HBITMAP__ **phbmpAnd, HICON__ **phIcon, unsigned int xSizeDesired, unsigned int ySizeDesired, unsigned int dwFlags)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800b64ec`

## callees

- `0x1800185ec`
- `0x1800268e4`
- `0x180026d6c`
- `0x180027c48`
- `0x180028b48`
- `0x18004291c`
- `0x180052390`
- `0x1800b0564`
- `0x1800b0590`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180026c2a`
- `KERNELBASE!GlobalAlloc` at `0x180026c2a`
- `KERNELBASE!GlobalFree` at `0x180026c81`
- `KERNELBASE!GlobalFree` at `0x180026c81`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180026c74`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180026c74`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180026c4d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180026c4d`

## string_xrefs

- `0x180026999`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x1800269f9`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x180026d21`: `com\oleaut32\stdtypes\pictobj.cpp`

## pseudocode

```c

```

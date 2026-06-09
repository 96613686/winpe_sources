# PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)

- ea: `0x180005ed0`
- end: `0x180006c87`
- name: `?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z`
- size: `3511`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, enum PATHCCH_OPTIONS)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x180005970`
- `0x180011900`

## callees

- `0x180005ed0`
- `0x180006c90`
- `0x180006cc0`
- `0x1800074a0`
- `0x180051bf4`
- `0x18005ab30`
- `0x18005ab4c`
- `0x180115ed8`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180006098`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180006b9a`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180006098`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180006b9a`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x1800060e3`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x1800060e3`

## string_xrefs

- `0x180006800`: `RtlAreLongPathsEnabled`
- `0x1800067f1`: `ntdll.dll`

## pseudocode

```c

```

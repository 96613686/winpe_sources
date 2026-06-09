# CheckDriverStrongNamesMatch(IMMDevice *,IPnpDevnode *,bool *)

- ea: `0x18002a824`
- end: `0x18002aa4b`
- name: `?CheckDriverStrongNamesMatch@@YAJPEAUIMMDevice@@PEAUIPnpDevnode@@PEA_N@Z`
- size: `551`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct IPnpDevnode *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052ffc`

## callees

- `0x1800017f4`
- `0x180006b0c`
- `0x180010da8`
- `0x18001f374`
- `0x180024d54`
- `0x18002a824`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a9b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a9b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002aa07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002aa12`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002aa07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002aa12`

## string_xrefs

- `0x18002a8cf`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c

```

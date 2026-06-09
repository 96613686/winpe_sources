# WrpMitigation_Resolve(unsigned __int64,unsigned __int64,unsigned __int64,void *)

- ea: `0x1800b58b0`
- end: `0x1800b5a18`
- name: `?WrpMitigation_Resolve@@YAK_K00PEAX@Z`
- size: `360`
- prototype: `unsigned int(unsigned __int64, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180012920`
- `0x1800b58b0`
- `0x1800ee7b4`
- `0x1800eea2c`
- `0x1800eee18`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b5924`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b5991`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b5924`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b5991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b59b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b59b4`
- `USER32!LoadStringW` at `0x1800b593d`
- `USER32!LoadStringW` at `0x1800b59aa`
- `USER32!LoadStringW` at `0x1800b593d`
- `USER32!LoadStringW` at `0x1800b59aa`

## string_xrefs

- `0x1800b5917`: `pcasvc.dll`
- `0x1800b598a`: `pcasvc.dll`

## pseudocode

```c

```

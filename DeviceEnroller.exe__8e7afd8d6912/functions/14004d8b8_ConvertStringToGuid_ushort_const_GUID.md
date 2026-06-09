# ConvertStringToGuid(ushort const *,_GUID *)

- ea: `0x14004d8b8`
- end: `0x14004da99`
- name: `?ConvertStringToGuid@@YAJPEBGPEAU_GUID@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14004a704`
- `0x14004a854`
- `0x14004a9a4`
- `0x14004ba08`
- `0x14004c074`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x14004d8b8`
- `0x14004f4d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da39`
- `RPCRT4!UuidFromStringW` at `0x14004da1a`
- `RPCRT4!UuidFromStringW` at `0x14004da1a`

## string_xrefs

- `0x14004d954`: `ConvertStringToGuid - Copy String StringCchLength() failed with hr = 0x%1!x!. GetLastError () 0x%2!x!`
- `0x14004da04`: `ConvertStringToGuid - StringCchCopyN failed with with hr = 0x%1!x!. GetLastError () 0x%2!x!`

## pseudocode

```c

```

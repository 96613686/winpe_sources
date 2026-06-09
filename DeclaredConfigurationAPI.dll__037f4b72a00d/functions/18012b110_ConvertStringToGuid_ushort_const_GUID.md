# ConvertStringToGuid(ushort const *,_GUID *)

- ea: `0x18012b110`
- end: `0x18012b270`
- name: `?ConvertStringToGuid@@YAJPEBGPEAU_GUID@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _GUID *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180129750`
- `0x18012981c`
- `0x1801298fc`
- `0x180129a5c`
- `0x18012a3f4`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18004a5d4`
- `0x18009ac5c`
- `0x18012b110`
- `0x18012c77c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b22d`
- `RPCRT4!UuidFromStringW` at `0x18012b20e`
- `RPCRT4!UuidFromStringW` at `0x18012b20e`

## string_xrefs

- `0x18012b198`: `ConvertStringToGuid - Copy String StringCchLength() failed with hr = 0x%1!x!. GetLastError () 0x%2!x!`
- `0x18012b1fb`: `ConvertStringToGuid - StringCchCopyN failed with with hr = 0x%1!x!. GetLastError () 0x%2!x!`

## pseudocode

```c

```

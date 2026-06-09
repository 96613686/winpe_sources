# ConvertDevicePathToDrivePath(ushort const *,ushort *)

- ea: `0x180116360`
- end: `0x1801165b7`
- name: `?ConvertDevicePathToDrivePath@@YAJPEBGPEAG@Z`
- size: `599`
- prototype: `__int64 __fastcall(wchar_t *String1, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180011900`

## callees

- `0x180015eec`
- `0x180059920`
- `0x18005a7d8`
- `0x18005a8bc`
- `0x180116360`
- `0x1801165c0`
- `0x1801167f0`
- `0x180116834`

## import_xrefs

- `KERNEL32!GetLogicalDriveStringsW` at `0x1801163e8`
- `KERNEL32!GetLogicalDriveStringsW` at `0x1801163e8`
- `KERNEL32!QueryDosDeviceW` at `0x18011642a`
- `KERNEL32!QueryDosDeviceW` at `0x18011642a`

## string_xrefs

- `0x18011655d`: `Bad length for resulting drive path: %d`
- `0x1801164f4`: `Failed to put drive path together [%#x]`

## pseudocode

```c

```

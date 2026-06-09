# IsCatalogSignatureValidForFile(ushort const *,ushort const *,Win32HandleRAII *)

- ea: `0x180014b24`
- end: `0x180014f1a`
- name: `?IsCatalogSignatureValidForFile@@YA_NPEBG0PEAVWin32HandleRAII@@@Z`
- size: `1014`
- prototype: `bool(const unsigned __int16 *, const unsigned __int16 *, struct Win32HandleRAII *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180018200`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x18000f380`
- `0x18000f6a0`
- `0x180014b24`
- `0x1800183f8`
- `0x180018b44`
- `0x180018bbc`
- `0x180150ce8`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180014c09`
- `KERNEL32!CreateFileW` at `0x180014c09`
- `KERNEL32!GetProcAddress` at `0x180014b9b`
- `KERNEL32!GetProcAddress` at `0x180014bb5`
- `KERNEL32!GetProcAddress` at `0x180014b9b`
- `KERNEL32!GetProcAddress` at `0x180014bb5`
- `KERNEL32!FreeLibrary` at `0x180014db5`
- `KERNEL32!FreeLibrary` at `0x180014db5`
- `KERNEL32!CloseHandle` at `0x180014da1`
- `KERNEL32!CloseHandle` at `0x180014da1`
- `KERNEL32!GetLastError` at `0x180014eac`
- `KERNEL32!GetLastError` at `0x180014eac`

## string_xrefs

- `0x180014b7b`: `wintrust.dll`

## pseudocode

```c

```

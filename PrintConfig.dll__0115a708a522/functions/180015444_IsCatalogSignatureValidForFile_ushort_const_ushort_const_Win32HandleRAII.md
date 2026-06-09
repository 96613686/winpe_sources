# IsCatalogSignatureValidForFile(ushort const *,ushort const *,Win32HandleRAII *)

- ea: `0x180015444`
- end: `0x18001585f`
- name: `?IsCatalogSignatureValidForFile@@YA_NPEBG0PEAVWin32HandleRAII@@@Z`
- size: `1051`
- prototype: `char __fastcall(const unsigned __int16 *, const unsigned __int16 *, char **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180018d54`

## callees

- `0x180003400`
- `0x180004558`
- `0x180004564`
- `0x18000f830`
- `0x18000fb68`
- `0x180015444`
- `0x180018f58`
- `0x18001973c`
- `0x1800197b4`
- `0x180157d60`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180015535`
- `KERNEL32!CreateFileW` at `0x180015535`
- `KERNEL32!GetProcAddress` at `0x1800154bb`
- `KERNEL32!GetProcAddress` at `0x1800154db`
- `KERNEL32!GetProcAddress` at `0x1800154bb`
- `KERNEL32!GetProcAddress` at `0x1800154db`
- `KERNEL32!FreeLibrary` at `0x1800156ed`
- `KERNEL32!FreeLibrary` at `0x1800156ed`
- `KERNEL32!CloseHandle` at `0x1800156d3`
- `KERNEL32!CloseHandle` at `0x1800156d3`
- `KERNEL32!GetLastError` at `0x1800157eb`
- `KERNEL32!GetLastError` at `0x1800157eb`

## string_xrefs

- `0x18001549b`: `wintrust.dll`

## pseudocode

```c

```

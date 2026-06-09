# LookupPrivilegeValueA

- ea: `0x180020550`
- end: `0x180020613`
- name: `LookupPrivilegeValueA`
- size: `195`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, LPCSTR lpName, PLUID lpLuid)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001ff80`
- `0x180020550`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800205e8`
- `ntdll!RtlFreeUnicodeString` at `0x1800205f2`
- `ntdll!RtlFreeUnicodeString` at `0x1800205e8`
- `ntdll!RtlFreeUnicodeString` at `0x1800205f2`
- `ntdll!RtlInitAnsiString` at `0x18002057f`
- `ntdll!RtlInitAnsiString` at `0x18002058c`
- `ntdll!RtlInitAnsiString` at `0x18002057f`
- `ntdll!RtlInitAnsiString` at `0x18002058c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800205ad`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800205c6`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800205ad`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800205c6`
- `KERNEL32!BaseSetLastNTError` at `0x180020609`
- `KERNEL32!BaseSetLastNTError` at `0x180020609`

## pseudocode

```c

```

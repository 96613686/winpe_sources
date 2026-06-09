# LookupPrivilegeValueA

- ea: `0x18001f5b0`
- end: `0x18001f69e`
- name: `LookupPrivilegeValueA`
- size: `238`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, LPCSTR lpName, PLUID lpLuid)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001de40`
- `0x18001f5b0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001f660`
- `ntdll!RtlFreeUnicodeString` at `0x18001f670`
- `ntdll!RtlFreeUnicodeString` at `0x18001f660`
- `ntdll!RtlFreeUnicodeString` at `0x18001f670`
- `ntdll!RtlInitAnsiString` at `0x18001f5df`
- `ntdll!RtlInitAnsiString` at `0x18001f5f2`
- `ntdll!RtlInitAnsiString` at `0x18001f5df`
- `ntdll!RtlInitAnsiString` at `0x18001f5f2`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001f619`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001f638`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001f619`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001f638`
- `KERNEL32!BaseSetLastNTError` at `0x18001f68e`
- `KERNEL32!BaseSetLastNTError` at `0x18001f68e`

## pseudocode

```c

```

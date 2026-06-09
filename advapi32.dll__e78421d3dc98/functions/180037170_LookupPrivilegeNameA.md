# LookupPrivilegeNameA

- ea: `0x180037170`
- end: `0x1800372c0`
- name: `LookupPrivilegeNameA`
- size: `336`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, PLUID lpLuid, LPSTR lpName, LPDWORD cchName)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001fdf0`
- `0x180037170`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003723f`
- `ntdll!RtlFreeHeap` at `0x1800372a0`
- `ntdll!RtlFreeHeap` at `0x18003723f`
- `ntdll!RtlFreeHeap` at `0x1800372a0`
- `ntdll!RtlFreeUnicodeString` at `0x180037204`
- `ntdll!RtlFreeUnicodeString` at `0x180037249`
- `ntdll!RtlFreeUnicodeString` at `0x1800372aa`
- `ntdll!RtlFreeUnicodeString` at `0x180037204`
- `ntdll!RtlFreeUnicodeString` at `0x180037249`
- `ntdll!RtlFreeUnicodeString` at `0x1800372aa`
- `ntdll!RtlAllocateHeap` at `0x1800371f2`
- `ntdll!RtlAllocateHeap` at `0x1800371f2`
- `ntdll!RtlInitAnsiString` at `0x1800371a4`
- `ntdll!RtlInitAnsiString` at `0x1800371a4`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180037282`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180037282`
- `ntdll!RtlInitUnicodeString` at `0x180037260`
- `ntdll!RtlInitUnicodeString` at `0x180037260`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800371b5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800371b5`
- `KERNEL32!BaseSetLastNTError` at `0x1800371c1`
- `KERNEL32!BaseSetLastNTError` at `0x1800371c1`

## pseudocode

```c

```

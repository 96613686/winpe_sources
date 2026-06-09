# LookupPrivilegeNameA

- ea: `0x18003b1b0`
- end: `0x18003b343`
- name: `LookupPrivilegeNameA`
- size: `403`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, PLUID lpLuid, LPSTR lpName, LPDWORD cchName)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001dc90`
- `0x18003b1b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003b29d`
- `ntdll!RtlFreeHeap` at `0x18003b316`
- `ntdll!RtlFreeHeap` at `0x18003b29d`
- `ntdll!RtlFreeHeap` at `0x18003b316`
- `ntdll!RtlFreeUnicodeString` at `0x18003b25c`
- `ntdll!RtlFreeUnicodeString` at `0x18003b2ad`
- `ntdll!RtlFreeUnicodeString` at `0x18003b326`
- `ntdll!RtlFreeUnicodeString` at `0x18003b25c`
- `ntdll!RtlFreeUnicodeString` at `0x18003b2ad`
- `ntdll!RtlFreeUnicodeString` at `0x18003b326`
- `ntdll!RtlAllocateHeap` at `0x18003b244`
- `ntdll!RtlAllocateHeap` at `0x18003b244`
- `ntdll!RtlInitAnsiString` at `0x18003b1e4`
- `ntdll!RtlInitAnsiString` at `0x18003b1e4`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18003b2f2`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18003b2f2`
- `ntdll!RtlInitUnicodeString` at `0x18003b2ca`
- `ntdll!RtlInitUnicodeString` at `0x18003b2ca`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003b1fb`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003b1fb`
- `KERNEL32!BaseSetLastNTError` at `0x18003b20d`
- `KERNEL32!BaseSetLastNTError` at `0x18003b20d`

## pseudocode

```c

```

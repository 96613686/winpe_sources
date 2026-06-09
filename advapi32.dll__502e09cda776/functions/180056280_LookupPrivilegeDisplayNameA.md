# LookupPrivilegeDisplayNameA

- ea: `0x180056280`
- end: `0x18005647b`
- name: `LookupPrivilegeDisplayNameA`
- size: `507`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, LPCSTR lpName, LPSTR lpDisplayName, LPDWORD cchDisplayName, LPDWORD lpLanguageId)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180056280`
- `0x180056490`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800563a6`
- `ntdll!RtlFreeHeap` at `0x18005645c`
- `ntdll!RtlFreeHeap` at `0x1800563a6`
- `ntdll!RtlFreeHeap` at `0x18005645c`
- `ntdll!RtlFreeUnicodeString` at `0x180056340`
- `ntdll!RtlFreeUnicodeString` at `0x180056388`
- `ntdll!RtlFreeUnicodeString` at `0x18005642e`
- `ntdll!RtlFreeUnicodeString` at `0x18005643e`
- `ntdll!RtlFreeUnicodeString` at `0x180056340`
- `ntdll!RtlFreeUnicodeString` at `0x180056388`
- `ntdll!RtlFreeUnicodeString` at `0x18005642e`
- `ntdll!RtlFreeUnicodeString` at `0x18005643e`
- `ntdll!RtlAllocateHeap` at `0x180056328`
- `ntdll!RtlAllocateHeap` at `0x180056328`
- `ntdll!RtlInitAnsiString` at `0x1800562c3`
- `ntdll!RtlInitAnsiString` at `0x18005635a`
- `ntdll!RtlInitAnsiString` at `0x1800562c3`
- `ntdll!RtlInitAnsiString` at `0x18005635a`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180056418`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180056418`
- `ntdll!RtlInitUnicodeString` at `0x1800563f0`
- `ntdll!RtlInitUnicodeString` at `0x1800563f0`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800562df`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056371`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800562df`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180056371`
- `KERNEL32!BaseSetLastNTError` at `0x1800562f1`
- `KERNEL32!BaseSetLastNTError` at `0x1800562f1`

## pseudocode

```c

```

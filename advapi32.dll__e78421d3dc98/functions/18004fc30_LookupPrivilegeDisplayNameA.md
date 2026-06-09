# LookupPrivilegeDisplayNameA

- ea: `0x18004fc30`
- end: `0x18004fdd6`
- name: `LookupPrivilegeDisplayNameA`
- size: `422`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, LPCSTR lpName, LPSTR lpDisplayName, LPDWORD cchDisplayName, LPDWORD lpLanguageId)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18004fc30`
- `0x18004fde0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004fd26`
- `ntdll!RtlFreeHeap` at `0x18004fdbe`
- `ntdll!RtlFreeHeap` at `0x18004fd26`
- `ntdll!RtlFreeHeap` at `0x18004fdbe`
- `ntdll!RtlFreeUnicodeString` at `0x18004fcd8`
- `ntdll!RtlFreeUnicodeString` at `0x18004fd0e`
- `ntdll!RtlFreeUnicodeString` at `0x18004fd9c`
- `ntdll!RtlFreeUnicodeString` at `0x18004fda6`
- `ntdll!RtlFreeUnicodeString` at `0x18004fcd8`
- `ntdll!RtlFreeUnicodeString` at `0x18004fd0e`
- `ntdll!RtlFreeUnicodeString` at `0x18004fd9c`
- `ntdll!RtlFreeUnicodeString` at `0x18004fda6`
- `ntdll!RtlAllocateHeap` at `0x18004fcc6`
- `ntdll!RtlAllocateHeap` at `0x18004fcc6`
- `ntdll!RtlInitAnsiString` at `0x18004fc73`
- `ntdll!RtlInitAnsiString` at `0x18004fcec`
- `ntdll!RtlInitAnsiString` at `0x18004fc73`
- `ntdll!RtlInitAnsiString` at `0x18004fcec`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18004fd8c`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18004fd8c`
- `ntdll!RtlInitUnicodeString` at `0x18004fd6a`
- `ntdll!RtlInitUnicodeString` at `0x18004fd6a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fc89`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fcfd`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fc89`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004fcfd`
- `KERNEL32!BaseSetLastNTError` at `0x18004fc95`
- `KERNEL32!BaseSetLastNTError` at `0x18004fc95`

## pseudocode

```c

```

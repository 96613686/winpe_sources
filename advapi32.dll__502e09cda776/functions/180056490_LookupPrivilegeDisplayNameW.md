# LookupPrivilegeDisplayNameW

- ea: `0x180056490`
- end: `0x180056630`
- name: `LookupPrivilegeDisplayNameW`
- size: `416`
- prototype: `BOOL __stdcall(LPCWSTR lpSystemName, LPCWSTR lpName, LPWSTR lpDisplayName, LPDWORD cchDisplayName, LPDWORD lpLanguageId)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180056280`

## callees

- `0x18001df64`
- `0x18001e120`
- `0x180045230`
- `0x180056490`
- `0x18007204e`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005651f`
- `ntdll!RtlInitUnicodeString` at `0x180056562`
- `ntdll!RtlInitUnicodeString` at `0x18005651f`
- `ntdll!RtlInitUnicodeString` at `0x180056562`
- `KERNEL32!LocalFree` at `0x1800565e0`
- `KERNEL32!LocalFree` at `0x1800565ef`
- `KERNEL32!LocalFree` at `0x1800565e0`
- `KERNEL32!LocalFree` at `0x1800565ef`
- `KERNEL32!BaseSetLastNTError` at `0x180056548`
- `KERNEL32!BaseSetLastNTError` at `0x180056548`

## pseudocode

```c

```

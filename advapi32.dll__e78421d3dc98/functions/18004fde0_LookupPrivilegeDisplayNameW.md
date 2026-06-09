# LookupPrivilegeDisplayNameW

- ea: `0x18004fde0`
- end: `0x18004ff61`
- name: `LookupPrivilegeDisplayNameW`
- size: `385`
- prototype: `BOOL __stdcall(LPCWSTR lpSystemName, LPCWSTR lpName, LPWSTR lpDisplayName, LPDWORD cchDisplayName, LPDWORD lpLanguageId)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004fc30`

## callees

- `0x180020088`
- `0x180020234`
- `0x1800401a0`
- `0x18004fde0`
- `0x18006504e`
- `0x180065090`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004fe6f`
- `ntdll!RtlInitUnicodeString` at `0x18004fea6`
- `ntdll!RtlInitUnicodeString` at `0x18004fe6f`
- `ntdll!RtlInitUnicodeString` at `0x18004fea6`
- `KERNEL32!LocalFree` at `0x18004ff1e`
- `KERNEL32!LocalFree` at `0x18004ff27`
- `KERNEL32!LocalFree` at `0x18004ff1e`
- `KERNEL32!LocalFree` at `0x18004ff27`
- `KERNEL32!BaseSetLastNTError` at `0x18004fe92`
- `KERNEL32!BaseSetLastNTError` at `0x18004fe92`

## pseudocode

```c

```

# ConvertStringSidToSidA

- ea: `0x180019440`
- end: `0x1800194ef`
- name: `ConvertStringSidToSidA`
- size: `175`
- prototype: `BOOL __stdcall(LPCSTR StringSid, PSID *Sid)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180019344`
- `0x180019440`
- `0x180019550`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800194dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800194dc`
- `ntdll!RtlInitAnsiString` at `0x180019485`
- `ntdll!RtlInitAnsiString` at `0x180019485`
- `KERNEL32!LocalFree` at `0x1800194b8`
- `KERNEL32!LocalFree` at `0x1800194b8`
- `KERNEL32!SetLastError` at `0x180019463`
- `KERNEL32!SetLastError` at `0x1800194ca`
- `KERNEL32!SetLastError` at `0x180019463`
- `KERNEL32!SetLastError` at `0x1800194ca`

## pseudocode

```c

```

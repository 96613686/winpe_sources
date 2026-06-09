# ConvertStringSidToSidA

- ea: `0x18001aaf0`
- end: `0x18001ab7d`
- name: `ConvertStringSidToSidA`
- size: `141`
- prototype: `BOOL __stdcall(LPCSTR StringSid, PSID *Sid)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001aa10`
- `0x18001aaf0`
- `0x18001abc0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001ab73`
- `ntdll!RtlNtStatusToDosError` at `0x18001ab73`
- `ntdll!RtlInitAnsiString` at `0x18001ab2e`
- `ntdll!RtlInitAnsiString` at `0x18001ab2e`
- `KERNEL32!LocalFree` at `0x18001ab5b`
- `KERNEL32!LocalFree` at `0x18001ab5b`
- `KERNEL32!SetLastError` at `0x18001ab13`
- `KERNEL32!SetLastError` at `0x18001ab67`
- `KERNEL32!SetLastError` at `0x18001ab13`
- `KERNEL32!SetLastError` at `0x18001ab67`

## pseudocode

```c

```

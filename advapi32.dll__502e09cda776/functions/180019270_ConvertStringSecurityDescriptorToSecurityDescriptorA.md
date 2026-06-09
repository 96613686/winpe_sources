# ConvertStringSecurityDescriptorToSecurityDescriptorA

- ea: `0x180019270`
- end: `0x18001933b`
- name: `ConvertStringSecurityDescriptorToSecurityDescriptorA`
- size: `203`
- prototype: `BOOL __stdcall(LPCSTR StringSecurityDescriptor, DWORD StringSDRevision, PSECURITY_DESCRIPTOR *SecurityDescriptor, PULONG SecurityDescriptorSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180019270`
- `0x180019344`
- `0x180019e70`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180019328`
- `ntdll!RtlNtStatusToDosError` at `0x180019328`
- `ntdll!RtlInitAnsiString` at `0x1800192cc`
- `ntdll!RtlInitAnsiString` at `0x1800192cc`
- `KERNEL32!LocalFree` at `0x180019304`
- `KERNEL32!LocalFree` at `0x180019304`
- `KERNEL32!SetLastError` at `0x1800192a0`
- `KERNEL32!SetLastError` at `0x180019316`
- `KERNEL32!SetLastError` at `0x1800192a0`
- `KERNEL32!SetLastError` at `0x180019316`

## pseudocode

```c

```

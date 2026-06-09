# ConvertStringSecurityDescriptorToSecurityDescriptorA

- ea: `0x18001a960`
- end: `0x18001aa09`
- name: `ConvertStringSecurityDescriptorToSecurityDescriptorA`
- size: `169`
- prototype: `BOOL __stdcall(LPCSTR StringSecurityDescriptor, DWORD StringSDRevision, PSECURITY_DESCRIPTOR *SecurityDescriptor, PULONG SecurityDescriptorSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001a960`
- `0x18001aa10`
- `0x18001b420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001a9ff`
- `ntdll!RtlNtStatusToDosError` at `0x18001a9ff`
- `ntdll!RtlInitAnsiString` at `0x18001a9b5`
- `ntdll!RtlInitAnsiString` at `0x18001a9b5`
- `KERNEL32!LocalFree` at `0x18001a9e7`
- `KERNEL32!LocalFree` at `0x18001a9e7`
- `KERNEL32!SetLastError` at `0x18001a990`
- `KERNEL32!SetLastError` at `0x18001a9f3`
- `KERNEL32!SetLastError` at `0x18001a990`
- `KERNEL32!SetLastError` at `0x18001a9f3`

## pseudocode

```c

```

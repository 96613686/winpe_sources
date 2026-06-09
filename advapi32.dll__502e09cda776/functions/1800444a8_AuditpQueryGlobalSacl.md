# AuditpQueryGlobalSacl

- ea: `0x1800444a8`
- end: `0x180044594`
- name: `AuditpQueryGlobalSacl`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180044330`

## callees

- `0x1800444a8`
- `0x180072042`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180044557`
- `ntdll!RtlNtStatusToDosError` at `0x180044557`
- `KERNELBASE!LocalAlloc` at `0x180044513`
- `KERNELBASE!LocalAlloc` at `0x180044513`
- `KERNEL32!LocalFree` at `0x180044547`
- `KERNEL32!LocalFree` at `0x180044547`
- `KERNEL32!SetLastError` at `0x180044577`
- `KERNEL32!SetLastError` at `0x180044577`
- `RPCRT4!NdrClientCall3` at `0x1800444f1`
- `RPCRT4!NdrClientCall3` at `0x1800444f1`

## pseudocode

```c

```

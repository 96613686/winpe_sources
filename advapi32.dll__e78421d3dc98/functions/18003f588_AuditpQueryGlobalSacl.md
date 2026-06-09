# AuditpQueryGlobalSacl

- ea: `0x18003f588`
- end: `0x18003f655`
- name: `AuditpQueryGlobalSacl`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003f450`

## callees

- `0x18003f588`
- `0x180065042`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f625`
- `ntdll!RtlNtStatusToDosError` at `0x18003f625`
- `KERNELBASE!LocalAlloc` at `0x18003f5ed`
- `KERNELBASE!LocalAlloc` at `0x18003f5ed`
- `KERNEL32!LocalFree` at `0x18003f61b`
- `KERNEL32!LocalFree` at `0x18003f61b`
- `KERNEL32!SetLastError` at `0x18003f63f`
- `KERNEL32!SetLastError` at `0x18003f63f`
- `RPCRT4!NdrClientCall3` at `0x18003f5d1`
- `RPCRT4!NdrClientCall3` at `0x18003f5d1`

## pseudocode

```c

```

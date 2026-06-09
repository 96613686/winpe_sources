# AuditQueryGlobalSaclA

- ea: `0x18003f450`
- end: `0x18003f4e1`
- name: `AuditQueryGlobalSaclA`
- size: `145`
- prototype: `BOOLEAN __stdcall(PCSTR ObjectTypeName, PACL *Acl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18003f450`
- `0x18003f588`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18003f4ce`
- `ntdll!RtlFreeUnicodeString` at `0x18003f4ce`
- `ntdll!RtlNtStatusToDosError` at `0x18003f4a8`
- `ntdll!RtlNtStatusToDosError` at `0x18003f4a8`
- `ntdll!RtlInitAnsiString` at `0x18003f489`
- `ntdll!RtlInitAnsiString` at `0x18003f489`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003f49c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003f49c`
- `KERNEL32!SetLastError` at `0x18003f479`
- `KERNEL32!SetLastError` at `0x18003f479`

## pseudocode

```c

```

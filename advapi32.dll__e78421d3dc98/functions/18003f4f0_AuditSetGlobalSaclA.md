# AuditSetGlobalSaclA

- ea: `0x18003f4f0`
- end: `0x18003f581`
- name: `AuditSetGlobalSaclA`
- size: `145`
- prototype: `BOOLEAN __stdcall(PCSTR ObjectTypeName, PACL Acl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18003f4f0`
- `0x18003f65c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18003f56e`
- `ntdll!RtlFreeUnicodeString` at `0x18003f56e`
- `ntdll!RtlNtStatusToDosError` at `0x18003f548`
- `ntdll!RtlNtStatusToDosError` at `0x18003f548`
- `ntdll!RtlInitAnsiString` at `0x18003f529`
- `ntdll!RtlInitAnsiString` at `0x18003f529`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003f53c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003f53c`
- `KERNEL32!SetLastError` at `0x18003f519`
- `KERNEL32!SetLastError` at `0x18003f519`

## pseudocode

```c

```

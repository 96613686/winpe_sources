# AuditSetGlobalSaclA

- ea: `0x1800443f0`
- end: `0x1800444a0`
- name: `AuditSetGlobalSaclA`
- size: `176`
- prototype: `BOOLEAN __stdcall(PCSTR ObjectTypeName, PACL Acl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800443f0`
- `0x18004459c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180044486`
- `ntdll!RtlFreeUnicodeString` at `0x180044486`
- `ntdll!RtlNtStatusToDosError` at `0x18004445a`
- `ntdll!RtlNtStatusToDosError` at `0x18004445a`
- `ntdll!RtlInitAnsiString` at `0x18004442f`
- `ntdll!RtlInitAnsiString` at `0x18004442f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180044448`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180044448`
- `KERNEL32!SetLastError` at `0x180044419`
- `KERNEL32!SetLastError` at `0x180044419`

## pseudocode

```c

```

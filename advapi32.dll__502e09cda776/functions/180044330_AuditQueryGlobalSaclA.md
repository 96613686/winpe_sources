# AuditQueryGlobalSaclA

- ea: `0x180044330`
- end: `0x1800443e0`
- name: `AuditQueryGlobalSaclA`
- size: `176`
- prototype: `BOOLEAN __stdcall(PCSTR ObjectTypeName, PACL *Acl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180044330`
- `0x1800444a8`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800443c6`
- `ntdll!RtlFreeUnicodeString` at `0x1800443c6`
- `ntdll!RtlNtStatusToDosError` at `0x18004439a`
- `ntdll!RtlNtStatusToDosError` at `0x18004439a`
- `ntdll!RtlInitAnsiString` at `0x18004436f`
- `ntdll!RtlInitAnsiString` at `0x18004436f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180044388`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180044388`
- `KERNEL32!SetLastError` at `0x180044359`
- `KERNEL32!SetLastError` at `0x180044359`

## pseudocode

```c

```

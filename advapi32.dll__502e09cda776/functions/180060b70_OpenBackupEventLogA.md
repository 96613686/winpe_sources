# OpenBackupEventLogA

- ea: `0x180060b70`
- end: `0x180060c8f`
- name: `OpenBackupEventLogA`
- size: `287`
- prototype: `HANDLE __stdcall(LPCSTR lpUNCServerName, LPCSTR lpFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800607b0`
- `0x180060b70`
- `0x180061b38`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180060c26`
- `ntdll!RtlFreeUnicodeString` at `0x180060c5f`
- `ntdll!RtlFreeUnicodeString` at `0x180060c6f`
- `ntdll!RtlFreeUnicodeString` at `0x180060c26`
- `ntdll!RtlFreeUnicodeString` at `0x180060c5f`
- `ntdll!RtlFreeUnicodeString` at `0x180060c6f`
- `ntdll!RtlInitAnsiString` at `0x180060ba6`
- `ntdll!RtlInitAnsiString` at `0x180060bf9`
- `ntdll!RtlInitAnsiString` at `0x180060ba6`
- `ntdll!RtlInitAnsiString` at `0x180060bf9`
- `ntdll!RtlInitUnicodeString` at `0x180060be1`
- `ntdll!RtlInitUnicodeString` at `0x180060c3c`
- `ntdll!RtlInitUnicodeString` at `0x180060be1`
- `ntdll!RtlInitUnicodeString` at `0x180060c3c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180060bbd`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180060c10`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180060bbd`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180060c10`

## pseudocode

```c

```

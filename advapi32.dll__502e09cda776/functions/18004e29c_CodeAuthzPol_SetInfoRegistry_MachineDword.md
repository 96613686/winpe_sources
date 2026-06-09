# CodeAuthzPol_SetInfoRegistry_MachineDword

- ea: `0x18004e29c`
- end: `0x18004e3b0`
- name: `CodeAuthzPol_SetInfoRegistry_MachineDword`
- size: `276`
- prototype: `__int64 __fastcall(int, const WCHAR *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18004afb0`

## callees

- `0x1800134c4`
- `0x18004e29c`

## import_xrefs

- `ntdll!NtClose` at `0x18004e385`
- `ntdll!NtClose` at `0x18004e385`
- `ntdll!NtSetValueKey` at `0x18004e36b`
- `ntdll!NtSetValueKey` at `0x18004e36b`
- `ntdll!RtlLeaveCriticalSection` at `0x18004e398`
- `ntdll!RtlLeaveCriticalSection` at `0x18004e398`
- `ntdll!RtlEnterCriticalSection` at `0x18004e2db`
- `ntdll!RtlEnterCriticalSection` at `0x18004e2db`
- `ntdll!RtlInitUnicodeString` at `0x18004e346`
- `ntdll!RtlInitUnicodeString` at `0x18004e346`

## pseudocode

```c

```

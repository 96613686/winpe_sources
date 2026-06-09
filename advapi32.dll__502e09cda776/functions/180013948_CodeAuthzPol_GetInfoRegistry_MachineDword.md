# CodeAuthzPol_GetInfoRegistry_MachineDword

- ea: `0x180013948`
- end: `0x180013b13`
- name: `CodeAuthzPol_GetInfoRegistry_MachineDword`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180014c6c`

## callees

- `0x1800134c4`
- `0x180013948`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180013a46`
- `ntdll!NtQueryValueKey` at `0x180013a46`
- `ntdll!NtClose` at `0x180013a61`
- `ntdll!NtClose` at `0x180013a61`
- `ntdll!RtlLeaveCriticalSection` at `0x180013a96`
- `ntdll!RtlLeaveCriticalSection` at `0x180013a96`
- `ntdll!RtlEnterCriticalSection` at `0x1800139a0`
- `ntdll!RtlEnterCriticalSection` at `0x1800139a0`
- `ntdll!RtlInitUnicodeString` at `0x180013a13`
- `ntdll!RtlInitUnicodeString` at `0x180013a13`

## pseudocode

```c

```

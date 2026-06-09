# CodeAuthzPol_SetInfoRegistry_MachineDword

- ea: `0x18004874c`
- end: `0x18004883e`
- name: `CodeAuthzPol_SetInfoRegistry_MachineDword`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180045850`

## callees

- `0x18000db68`
- `0x18004874c`

## import_xrefs

- `ntdll!NtClose` at `0x180048820`
- `ntdll!NtClose` at `0x180048820`
- `ntdll!NtSetValueKey` at `0x18004880c`
- `ntdll!NtSetValueKey` at `0x18004880c`
- `ntdll!RtlLeaveCriticalSection` at `0x18004882d`
- `ntdll!RtlLeaveCriticalSection` at `0x18004882d`
- `ntdll!RtlEnterCriticalSection` at `0x18004878b`
- `ntdll!RtlEnterCriticalSection` at `0x18004878b`
- `ntdll!RtlInitUnicodeString` at `0x1800487ed`
- `ntdll!RtlInitUnicodeString` at `0x1800487ed`

## pseudocode

```c

```

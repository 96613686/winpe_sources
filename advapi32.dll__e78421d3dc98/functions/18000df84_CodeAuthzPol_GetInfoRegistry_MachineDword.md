# CodeAuthzPol_GetInfoRegistry_MachineDword

- ea: `0x18000df84`
- end: `0x18000e12c`
- name: `CodeAuthzPol_GetInfoRegistry_MachineDword`
- size: `424`
- prototype: `__int64 __fastcall(unsigned int, const WCHAR *, unsigned int, int *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000f164`

## callees

- `0x18000db68`
- `0x18000df84`
- `0x180065090`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18000e076`
- `ntdll!NtQueryValueKey` at `0x18000e076`
- `ntdll!NtClose` at `0x18000e087`
- `ntdll!NtClose` at `0x18000e087`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e0b6`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e0b6`
- `ntdll!RtlEnterCriticalSection` at `0x18000dfdc`
- `ntdll!RtlEnterCriticalSection` at `0x18000dfdc`
- `ntdll!RtlInitUnicodeString` at `0x18000e049`
- `ntdll!RtlInitUnicodeString` at `0x18000e049`

## pseudocode

```c

```

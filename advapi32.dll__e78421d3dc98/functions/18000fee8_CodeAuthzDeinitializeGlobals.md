# CodeAuthzDeinitializeGlobals

- ea: `0x18000fee8`
- end: `0x18000ffaa`
- name: `CodeAuthzDeinitializeGlobals`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000fd00`

## callees

- `0x18000fee8`
- `0x18000ffb0`
- `0x18001001c`

## import_xrefs

- `ntdll!NtClose` at `0x18000ff5f`
- `ntdll!NtClose` at `0x18000ff5f`
- `ntdll!RtlDestroyHandleTable` at `0x18000ff06`
- `ntdll!RtlDestroyHandleTable` at `0x18000ff06`
- `ntdll!EtwEventUnregister` at `0x18000ff97`
- `ntdll!EtwEventUnregister` at `0x18000ff97`
- `ntdll!RtlDeleteCriticalSection` at `0x18000ff54`
- `ntdll!RtlDeleteCriticalSection` at `0x18000ff54`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ff7e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ff88`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ff7e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000ff88`

## pseudocode

```c

```

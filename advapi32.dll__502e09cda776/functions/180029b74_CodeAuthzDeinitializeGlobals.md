# CodeAuthzDeinitializeGlobals

- ea: `0x180029b74`
- end: `0x180029c5e`
- name: `CodeAuthzDeinitializeGlobals`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180029960`

## callees

- `0x180029b74`
- `0x180029c64`
- `0x180029ce0`

## import_xrefs

- `ntdll!NtClose` at `0x180029bf8`
- `ntdll!NtClose` at `0x180029bf8`
- `ntdll!RtlDestroyHandleTable` at `0x180029b92`
- `ntdll!RtlDestroyHandleTable` at `0x180029b92`
- `ntdll!EtwEventUnregister` at `0x180029c42`
- `ntdll!EtwEventUnregister` at `0x180029c42`
- `ntdll!RtlDeleteCriticalSection` at `0x180029be6`
- `ntdll!RtlDeleteCriticalSection` at `0x180029be6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029c1d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029c2d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029c1d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180029c2d`

## pseudocode

```c

```

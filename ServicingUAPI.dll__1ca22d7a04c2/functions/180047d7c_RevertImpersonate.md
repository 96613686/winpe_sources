# RevertImpersonate

- ea: `0x180047d7c`
- end: `0x180047e66`
- name: `RevertImpersonate`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1801b164c`

## callees

- `0x180006484`
- `0x18000fe74`
- `0x180047d7c`

## import_xrefs

- `ntdll!NtClose` at `0x180047e3c`
- `ntdll!NtClose` at `0x180047e3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047df9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047df9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047db5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047db5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180047e0a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180047e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047dc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047dc5`

## pseudocode

```c

```

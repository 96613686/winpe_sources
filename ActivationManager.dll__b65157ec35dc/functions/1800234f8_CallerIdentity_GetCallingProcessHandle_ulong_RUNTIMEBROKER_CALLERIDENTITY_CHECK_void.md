# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800234f8`
- end: `0x18002360b`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `275`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022c60`
- `0x18004e288`
- `0x18004ebc0`
- `0x180095f20`

## callees

- `0x18000b5c0`
- `0x180010a34`
- `0x1800234f8`
- `0x1800998c0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023560`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023560`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180023576`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180023576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023587`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002352e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002352e`

## pseudocode

```c

```

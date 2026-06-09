# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180072800`
- end: `0x180072946`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072694`
- `0x180072764`

## callees

- `0x180011618`
- `0x180072800`
- `0x18007294c`
- `0x180072bb0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007284b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007284b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800728c5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800728c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800728d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800728d6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180072834`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180072834`

## pseudocode

```c

```

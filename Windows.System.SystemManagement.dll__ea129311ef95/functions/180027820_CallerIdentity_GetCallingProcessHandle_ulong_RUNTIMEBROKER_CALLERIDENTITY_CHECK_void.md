# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180027820`
- end: `0x1800278cf`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `175`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027800`

## callees

- `0x180007d74`
- `0x180027820`
- `0x1800278d8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027888`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027888`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180027853`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180027853`

## pseudocode

```c

```

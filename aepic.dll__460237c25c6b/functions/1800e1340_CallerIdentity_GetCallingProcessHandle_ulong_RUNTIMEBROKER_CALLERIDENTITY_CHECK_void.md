# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800e1340`
- end: `0x1800e13ef`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `175`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e1320`

## callees

- `0x18000c37c`
- `0x1800e1340`
- `0x1800e1498`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e13a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e13a8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800e1373`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800e1373`

## pseudocode

```c

```

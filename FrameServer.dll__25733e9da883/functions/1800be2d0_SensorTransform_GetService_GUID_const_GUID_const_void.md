# SensorTransform::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800be2d0`
- end: `0x1800be418`
- name: `?GetService@SensorTransform@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(SensorTransform *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180009608`
- `0x1800be2d0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800be403`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800be2f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800be2f3`
- `MFPlat!MFTraceError` at `0x1800be32d`
- `MFPlat!MFTraceError` at `0x1800be32d`

## string_xrefs

- `0x1800be31a`: `SensorTransform::GetService`

## pseudocode

```c

```

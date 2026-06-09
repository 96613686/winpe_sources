# SensorTransformStream::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800c5be0`
- end: `0x1800c5d6f`
- name: `?GetService@SensorTransformStream@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `399`
- prototype: `__int64 __fastcall(SensorTransformStream *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x1800c5be0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5d5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5d5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5bfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5bfd`
- `MFPlat!MFTraceError` at `0x1800c5c37`
- `MFPlat!MFTraceError` at `0x1800c5c37`

## string_xrefs

- `0x1800c5c24`: `SensorTransformStream::GetService`

## pseudocode

```c

```

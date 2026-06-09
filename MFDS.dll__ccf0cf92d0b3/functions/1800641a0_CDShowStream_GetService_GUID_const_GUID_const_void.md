# CDShowStream::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800641a0`
- end: `0x180064318`
- name: `?GetService@CDShowStream@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `376`
- prototype: `__int64 __fastcall(CDShowStream *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180010350`
- `0x1800140b0`
- `0x180032a50`
- `0x180051ce4`
- `0x1800641a0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800642f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800642f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800641c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800641c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064218`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064218`

## string_xrefs

- `0x1800641f3`: `CDShowStream::GetService`
- `0x180064275`: `CDShowStream::GetService`

## pseudocode

```c

```

# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800144bc`
- end: `0x1800145b3`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(ATL::CComModule *this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017bb0`

## callees

- `0x18001310c`
- `0x1800144bc`
- `0x180035010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001453e`
- `KERNEL32!EnterCriticalSection` at `0x18001453e`
- `KERNEL32!LeaveCriticalSection` at `0x180014569`
- `KERNEL32!LeaveCriticalSection` at `0x180014569`

## pseudocode

```c

```

# PixLogger::OnEtwProviderEnabledThunk(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18002c260`
- end: `0x18002c2fe`
- name: `?OnEtwProviderEnabledThunk@PixLogger@@CAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `158`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, PixLogger *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002bd40`
- `0x18002c130`
- `0x18002c260`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c281`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c2ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c281`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c2ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c2e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c2e6`

## pseudocode

```c

```

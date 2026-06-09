# CQueryResultSet::FetchResultAndPreFetch(uint,IServiceProvider *,_GUID const &,void * *)

- ea: `0x18001def0`
- end: `0x18001e2f2`
- name: `?FetchResultAndPreFetch@CQueryResultSet@@UEAAJIPEAUIServiceProvider@@AEBU_GUID@@PEAPEAX@Z`
- size: `1026`
- prototype: `__int64 __usercall@<rax>(CQueryResultSet *__hidden this@<rcx>, unsigned int@<edx>, struct IServiceProvider *@<r8>, const struct _GUID *@<r9>, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001ec80`
- `0x18001f67c`

## callees

- `0x18001d280`
- `0x18001def0`
- `0x18001e4c4`
- `0x180048134`
- `0x1800589c8`
- `0x180063a68`
- `0x180071dc0`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x18001df96`
- `SHCORE!IUnknown_SetSite` at `0x18001dfe9`
- `SHCORE!IUnknown_SetSite` at `0x18001df96`
- `SHCORE!IUnknown_SetSite` at `0x18001dfe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dff2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dff2`

## pseudocode

```c

```

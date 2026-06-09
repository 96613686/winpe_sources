# CQueryResultSet::_LocateHROW(IRowsetLocate *,unsigned __int64,IServiceProvider *,_GUID const &,IUnknown * *)

- ea: `0x180048f0c`
- end: `0x1800490c5`
- name: `?_LocateHROW@CQueryResultSet@@AEAAJPEAUIRowsetLocate@@_KPEAUIServiceProvider@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `441`
- prototype: `int(CQueryResultSet *__hidden this, struct IRowsetLocate *, unsigned __int64, struct IServiceProvider *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800b3200`

## callees

- `0x18001e4c4`
- `0x180048f0c`
- `0x180063a68`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180048f89`
- `SHCORE!IUnknown_QueryService` at `0x180048f89`
- `SHCORE!IUnknown_SetSite` at `0x180048fe7`
- `SHCORE!IUnknown_SetSite` at `0x180049016`
- `SHCORE!IUnknown_SetSite` at `0x180048fe7`
- `SHCORE!IUnknown_SetSite` at `0x180049016`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048fda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048fda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049023`

## pseudocode

```c

```

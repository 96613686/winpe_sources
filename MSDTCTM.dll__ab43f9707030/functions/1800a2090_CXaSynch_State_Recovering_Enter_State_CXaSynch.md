# CXaSynch_State_Recovering::Enter_State(CXaSynch *)

- ea: `0x1800a2090`
- end: `0x1800a2277`
- name: `?Enter_State@CXaSynch_State_Recovering@@UEAAXPEAVCXaSynch@@@Z`
- size: `487`
- prototype: `void __fastcall(CXaSynch_State_Recovering *__hidden this, struct CXaSynch *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a1174`

## callees

- `0x1800240b0`
- `0x1800846c0`
- `0x18009abb8`
- `0x18009dfc0`
- `0x1800a109c`
- `0x1800a2090`
- `0x1800a2ce0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2224`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2224`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a215d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a215d`

## string_xrefs

- `0x1800a21af`: `CRecoverTask::Init (com\complus\dtc\dtc\xatm\src\xataskmgr.cpp@1512): pszXaDll != NULL`
- `0x1800a2232`: `com\complus\dtc\dtc\xatm\src\xasynch.cpp`
- `0x1800a223f`: `CRecoverTask`

## pseudocode

```c

```

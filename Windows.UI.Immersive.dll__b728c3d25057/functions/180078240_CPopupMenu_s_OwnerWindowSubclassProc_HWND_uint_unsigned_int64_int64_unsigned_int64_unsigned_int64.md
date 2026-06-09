# CPopupMenu::s_OwnerWindowSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x180078240`
- end: `0x180078308`
- name: `?s_OwnerWindowSubclassProc@CPopupMenu@@CA_JPEAUHWND__@@I_K_J11@Z`
- size: `200`
- prototype: `__int64(HWND hwnd, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800780c8`
- `0x180078240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800782e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800782e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007828b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007828b`
- `USER32!NotifyWinEvent` at `0x1800782ad`
- `USER32!NotifyWinEvent` at `0x1800782ad`
- `USER32!PostMessageW` at `0x18007827c`
- `USER32!PostMessageW` at `0x18007827c`
- `SHCORE!__imp_SHRemoveWindowSubclass` at `0x1800782db`
- `SHCORE!__imp_SHRemoveWindowSubclass` at `0x1800782db`
- `SHCORE!__imp_SHDefSubclassProc` at `0x180078301`

## pseudocode

```c

```

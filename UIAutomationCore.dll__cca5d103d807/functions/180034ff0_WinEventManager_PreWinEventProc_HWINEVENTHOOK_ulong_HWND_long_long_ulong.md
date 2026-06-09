# WinEventManager::PreWinEventProc(HWINEVENTHOOK__ *,ulong,HWND__ *,long,long,ulong)

- ea: `0x180034ff0`
- end: `0x180035452`
- name: `?PreWinEventProc@WinEventManager@@CAJPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJK@Z`
- size: `1122`
- prototype: `static int(HWINEVENTHOOK, unsigned int, HWND, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180035ea0`

## callees

- `0x1800182b0`
- `0x1800192f4`
- `0x180019394`
- `0x180033e04`
- `0x180034ff0`
- `0x180035458`
- `0x180035490`
- `0x1800354bc`
- `0x18003bbcc`
- `0x180091bf4`
- `0x180109898`
- `0x18013eba8`
- `0x180173444`
- `0x1801a6a40`
- `0x1801b78fc`
- `0x1801e8320`
- `0x1801e8344`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180035415`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180035415`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003506b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003506b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800350f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800350f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180035334`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180035334`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsChild` at `0x1800352ea`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsChild` at `0x1800352ea`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x180035305`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x180035305`

## string_xrefs

- `0x1800350d8`: `ComboLBox`
- `0x1800352a1`: `ComboLBox`

## pseudocode

```c

```

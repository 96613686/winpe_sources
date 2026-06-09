# CApplication::GetBackgroundTaskId(void)

- ea: `0x180038928`
- end: `0x1800389d4`
- name: `?GetBackgroundTaskId@CApplication@@QEAA?AU_GUID@@XZ`
- size: `172`
- prototype: `struct _GUID *__fastcall(CApplication *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003ce48`

## callees

- `0x18001b750`
- `0x1800327d4`
- `0x180038928`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003894f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003894f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800389bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800389bb`

## pseudocode

```c

```

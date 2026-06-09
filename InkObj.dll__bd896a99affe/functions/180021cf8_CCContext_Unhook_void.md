# CCContext::Unhook(void)

- ea: `0x180021cf8`
- end: `0x180021ec3`
- name: `?Unhook@CCContext@@IEAAJXZ`
- size: `459`
- prototype: `__int64 __fastcall(CCContext *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180021ed0`
- `0x180064af0`

## callees

- `0x1800021b0`
- `0x180021cf8`
- `0x180021f84`
- `0x1800347a4`
- `0x18003492c`
- `0x180039efc`
- `0x180044ad2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021eac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021eac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021d2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021d2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021e9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d3a`
- `USER32!UnhookWindowsHookEx` at `0x180021e70`
- `USER32!UnhookWindowsHookEx` at `0x180021e70`
- `USER32!IsWindow` at `0x180021d4c`
- `USER32!IsWindow` at `0x180021d4c`

## string_xrefs

- `0x180021d67`: `CCContext::Unhook (%x): window %x (valid:%d), thread: %x(cur %x), context: %x \n`

## pseudocode

```c

```

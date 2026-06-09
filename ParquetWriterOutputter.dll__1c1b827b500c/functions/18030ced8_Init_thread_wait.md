# _Init_thread_wait

- ea: `0x18030ced8`
- end: `0x18030cf4f`
- name: `_Init_thread_wait`
- size: `119`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18030ce20`

## callees

- `0x18030ced8`
- `0x180358070`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18030cf48`
- `KERNEL32!LeaveCriticalSection` at `0x18030cf24`
- `KERNEL32!LeaveCriticalSection` at `0x18030cf24`
- `KERNEL32!WaitForSingleObjectEx` at `0x18030cf36`
- `KERNEL32!WaitForSingleObjectEx` at `0x18030cf36`

## pseudocode

```c

```

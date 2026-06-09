# BipActivateCoalesedTriggersForPackage

- ea: `0x180007938`
- end: `0x180007aff`
- name: `BipActivateCoalesedTriggersForPackage`
- size: `455`
- prototype: `__int64 __fastcall(struct _BI_LOCK *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180014208`

## callees

- `0x180005d30`
- `0x1800075f8`
- `0x180007938`
- `0x180007b10`
- `0x18001027c`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007990`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007990`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007a09`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007a09`
- `ntdll!RtlFreeHeap` at `0x180007af4`
- `ntdll!RtlFreeHeap` at `0x180007af4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007996`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007996`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007aaa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007aaa`

## pseudocode

```c

```

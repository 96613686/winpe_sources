# BipNotifyAllSubscribers

- ea: `0x18003a024`
- end: `0x18003a14d`
- name: `BipNotifyAllSubscribers`
- size: `297`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007204`
- `0x180044630`
- `0x18005650c`
- `0x1800603d0`

## callees

- `0x18003a024`
- `0x18003a154`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a078`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a078`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a0f1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a0f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a07e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a07e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003a12e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003a12e`

## pseudocode

```c

```

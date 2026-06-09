# BipGetWorkItemCoalescedActivationAction

- ea: `0x1800076f4`
- end: `0x180007931`
- name: `BipGetWorkItemCoalescedActivationAction`
- size: `573`
- prototype: `__int64 __fastcall(struct _BI_LOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800144f4`

## callees

- `0x1800075f8`
- `0x1800076f4`
- `0x180007b10`
- `0x180007c68`
- `0x18001027c`
- `0x180042acc`
- `0x18005c418`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000775e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000775e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077a4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800077a4`
- `ntdll!RtlFreeHeap` at `0x180007926`
- `ntdll!RtlFreeHeap` at `0x180007926`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007764`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007764`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007861`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007861`

## pseudocode

```c

```

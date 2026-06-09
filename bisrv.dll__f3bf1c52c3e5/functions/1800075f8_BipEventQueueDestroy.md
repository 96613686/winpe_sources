# BipEventQueueDestroy

- ea: `0x1800075f8`
- end: `0x1800076ec`
- name: `BipEventQueueDestroy`
- size: `244`
- prototype: `__int64 __fastcall(struct _BI_LOCK *)`
- caller_count: `29`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004d4c`
- `0x180005b90`
- `0x180005d30`
- `0x1800072f8`
- `0x1800073e4`
- `0x1800076f4`
- `0x180007938`
- `0x180007c68`
- `0x180009100`
- `0x18000a46c`
- `0x18000ac6c`
- `0x18000b7a8`
- `0x18000bb10`
- `0x18000d50c`
- `0x1800317f0`
- `0x1800437fc`
- `0x18004786c`
- `0x18004e7f0`
- `0x18005df20`
- `0x18005f8f0`
- `0x180060198`
- `0x18007debc`
- `0x18007e2ac`
- `0x18007e45c`
- `0x18007eb4c`
- `0x18007f8bc`
- `0x18007faf0`
- `0x18007fdf8`
- `0x180083410`

## callees

- `0x1800075f8`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000763e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000763e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000769a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000769a`
- `ntdll!TpPostWork` at `0x1800076ad`
- `ntdll!TpPostWork` at `0x1800076ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007644`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007644`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076ca`

## pseudocode

```c

```

# BipWorkItemTpWorkerCleanup(_BI_WORK_ITEM *)

- ea: `0x180041a9c`
- end: `0x180041b61`
- name: `?BipWorkItemTpWorkerCleanup@@YAXPEAU_BI_WORK_ITEM@@@Z`
- size: `197`
- prototype: `void __fastcall(struct _BI_WORK_ITEM *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180057dec`

## callees

- `0x180041a9c`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180041ae0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180041ae0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180041b23`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180041b23`
- `ntdll!TpReleaseWork` at `0x180041b35`
- `ntdll!TpReleaseWork` at `0x180041b35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041ae6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041ae6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180041b4a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180041b4a`

## pseudocode

```c

```

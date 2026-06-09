# BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)

- ea: `0x18000da50`
- end: `0x18000db2f`
- name: `?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z`
- size: `223`
- prototype: `void __fastcall(struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)`
- caller_count: `109`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800044f8`
- `0x180005188`
- `0x180005280`
- `0x180005b90`
- `0x180006014`
- `0x180007014`
- `0x180007ebc`
- `0x1800080f0`
- `0x18000820c`
- `0x180008598`
- `0x180009728`
- `0x18000a560`
- `0x18000ac6c`
- `0x18000b0e0`
- `0x18000b7a8`
- `0x18000bb10`
- `0x18000db40`
- `0x18000f334`
- `0x180010370`
- `0x180011d90`
- `0x180011e98`
- `0x180013214`
- `0x180016d24`
- `0x18002731c`
- `0x18002da30`
- `0x180037928`
- `0x180039d14`
- `0x18003ad50`
- `0x18003d104`
- `0x18003d5b4`
- `0x18003dc6c`
- `0x1800437fc`
- `0x180044b34`
- `0x18004e12c`
- `0x18004e7f0`
- `0x18004fc90`
- `0x180054c20`
- `0x180055490`
- `0x180055b80`
- `0x180055c70`
- `0x180055df0`
- `0x180055f80`
- `0x1800563a0`
- `0x1800568b8`
- `0x180056ff0`
- `0x180057614`
- `0x180057830`
- `0x180057dec`
- `0x180057f40`
- `0x1800580c0`

## callees

- `0x18000da50`
- `0x1800121b0`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000da8f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000da8f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dada`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dada`
- `ntdll!RtlWakeAddressAll` at `0x18000db27`
- `ntdll!RtlWakeAddressAll` at `0x18000db27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da95`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000daee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000daee`

## pseudocode

```c

```

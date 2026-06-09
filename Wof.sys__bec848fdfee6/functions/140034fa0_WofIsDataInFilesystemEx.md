# WofIsDataInFilesystemEx

- ea: `0x140034fa0`
- end: `0x140035111`
- name: `WofIsDataInFilesystemEx`
- size: `369`
- prototype: `__int64 __fastcall(_DWORD *, _QWORD *, bool *, struct _EX_RUNDOWN_REF **)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140007b20`
- `0x140008e30`
- `0x140023a50`
- `0x140024448`
- `0x140032e2c`
- `0x140032ee4`
- `0x1400331d0`
- `0x140033930`
- `0x140034740`
- `0x1400361b0`
- `0x140036540`
- `0x14003e870`

## callees

- `0x140007670`
- `0x140034fa0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140035024`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140035024`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140035043`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140035043`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035037`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035037`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140034fbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140034fbe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140034fd1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140034fd1`
- `FLTMGR!FltGetStreamHandleContext` at `0x140035085`
- `FLTMGR!FltGetStreamHandleContext` at `0x140035085`
- `FLTMGR!FltReleaseContext` at `0x1400350a3`
- `FLTMGR!FltReleaseContext` at `0x1400350c3`
- `FLTMGR!FltReleaseContext` at `0x1400350fe`
- `FLTMGR!FltReleaseContext` at `0x1400350a3`
- `FLTMGR!FltReleaseContext` at `0x1400350c3`
- `FLTMGR!FltReleaseContext` at `0x1400350fe`

## pseudocode

```c

```

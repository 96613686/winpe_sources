# NtfsPrepareBitmapCacheForKSR

- ea: `0x1400dcf5c`
- end: `0x1400dda97`
- name: `NtfsPrepareBitmapCacheForKSR`
- size: `2875`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400dcec0`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x140042e10`
- `0x140042edc`
- `0x1400592c0`
- `0x1400dcf5c`
- `0x1401cbe6c`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400dd5e4`
- `ntoskrnl!IoAllocateMdl` at `0x1400dd5e4`
- `ntoskrnl!IoFreeMdl` at `0x1400dd8ce`
- `ntoskrnl!IoFreeMdl` at `0x1402c20a8`
- `ntoskrnl!IoFreeMdl` at `0x1400dd8ce`
- `ntoskrnl!IoFreeMdl` at `0x1402c20a8`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400dd63b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400dd63b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400dd00c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400dd00c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dd8f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dd929`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c20cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c2116`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dd8f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dd929`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c20cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c2116`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400dd2d8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400dd500`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400dd71b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400dd2d8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400dd500`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400dd71b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400dd1d0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400dd1d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400dd942`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c2132`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400dd942`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c2132`
- `HAL!KeQueryPerformanceCounter` at `0x1400dd053`
- `HAL!KeQueryPerformanceCounter` at `0x1400dd95a`
- `HAL!KeQueryPerformanceCounter` at `0x1402c2152`
- `HAL!KeQueryPerformanceCounter` at `0x1400dd053`
- `HAL!KeQueryPerformanceCounter` at `0x1400dd95a`
- `HAL!KeQueryPerformanceCounter` at `0x1402c2152`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1400dd0c8`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1400dd0c8`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrMdlToMemoryRuns` at `0x1400dd660`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrMdlToMemoryRuns` at `0x1400dd794`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrMdlToMemoryRuns` at `0x1400dd660`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrMdlToMemoryRuns` at `0x1400dd794`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrPersistMemory` at `0x1400dd844`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrPersistMemory` at `0x1400dd844`

## pseudocode

```c

```

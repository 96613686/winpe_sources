# MpDlpProcessRemoveSensitiveSectionFromRunningProcesses

- ea: `0x140060234`
- end: `0x140060325`
- name: `MpDlpProcessRemoveSensitiveSectionFromRunningProcesses`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14005f510`

## callees

- `0x140060234`
- `0x140060330`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400602f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400602f4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400602e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400602e8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140060281`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140060281`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006026f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006026f`

## pseudocode

```c

```

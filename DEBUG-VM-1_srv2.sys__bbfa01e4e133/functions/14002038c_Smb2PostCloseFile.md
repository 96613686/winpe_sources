# Smb2PostCloseFile

- ea: `0x14002038c`
- end: `0x14002047d`
- name: `Smb2PostCloseFile`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002ddb0`

## callees

- `0x140004960`
- `0x140005070`
- `0x140012ca0`
- `0x14002038c`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140020434`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140020434`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002044f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002044f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400203b3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400203b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400203dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400203dd`

## string_xrefs

- `0x140020415`: `Srv2PostToThreadPool`

## pseudocode

```c

```

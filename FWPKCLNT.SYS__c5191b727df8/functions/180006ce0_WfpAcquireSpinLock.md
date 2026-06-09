# WfpAcquireSpinLock

- ea: `0x180006ce0`
- end: `0x180006d6c`
- name: `WfpAcquireSpinLock`
- size: `140`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PKLOCK_QUEUE_HANDLE LockHandle)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c10`
- `0x180005720`
- `0x180006c88`
- `0x180006f60`
- `0x180007910`
- `0x180008aac`
- `0x18000a9d0`
- `0x18000baa0`
- `0x18000becc`
- `0x18000c8e0`
- `0x18001cbb8`
- `0x18001d4e8`
- `0x18001d7b0`
- `0x18001e440`
- `0x18001e9c0`
- `0x18001ea0c`
- `0x18001eec8`
- `0x18001f038`
- `0x18001f0b4`
- `0x18001f130`

## callees

- `0x180006ce0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180006d27`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180006d27`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180006d0a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180006d0a`
- `ntoskrnl!KeGetCurrentIrql` at `0x180006cf5`
- `ntoskrnl!KeGetCurrentIrql` at `0x180006cf5`

## pseudocode

```c

```

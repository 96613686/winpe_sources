# AfdTimerWheelHandler

- ea: `0x140035b60`
- end: `0x140035e9a`
- name: `AfdTimerWheelHandler`
- size: `826`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x14001c708`
- `0x140035b60`
- `0x140041eac`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!KeSetCoalescableTimer` at `0x140035e5e`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140035e5e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035bf7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035d39`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035da8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035bf7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035d39`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035da8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035d62`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035df4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035d62`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035df4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035c5d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035d08`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035d73`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035c5d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035d08`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035d73`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c39`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c76`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035ce4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035d21`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c39`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c76`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035ce4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035d21`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140035d53`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140035d53`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140035dbb`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140035dbb`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140035c1b`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140035c1b`

## pseudocode

```c

```

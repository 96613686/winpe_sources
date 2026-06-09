# AfdTimerWheelHandler

- ea: `0x140035b40`
- end: `0x140035e7a`
- name: `AfdTimerWheelHandler`
- size: `826`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x14001c708`
- `0x140035b40`
- `0x140041e8c`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!KeSetCoalescableTimer` at `0x140035e3e`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140035e3e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035bd7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035d19`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035d88`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035bd7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035d19`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035d88`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035d42`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035dd4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035d42`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140035dd4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035c3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035ce8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035d53`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035c3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035ce8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140035d53`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c19`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c56`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035cc4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035d01`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c19`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035c56`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035cc4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140035d01`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140035d33`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140035d33`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140035d9b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140035d9b`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140035bfb`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140035bfb`

## pseudocode

```c

```

# A2DP_Device::SetCloseCompleteEvent(void)

- ea: `0x1400355fc`
- end: `0x140035672`
- name: `?SetCloseCompleteEvent@A2DP_Device@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002f3f0`
- `0x140030740`
- `0x140032d7c`
- `0x1400356d4`

## callees

- `0x1400355fc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140035655`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035655`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035618`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035618`
- `ntoskrnl!KeSetEvent` at `0x14003563c`
- `ntoskrnl!KeSetEvent` at `0x14003563c`

## pseudocode

```c

```

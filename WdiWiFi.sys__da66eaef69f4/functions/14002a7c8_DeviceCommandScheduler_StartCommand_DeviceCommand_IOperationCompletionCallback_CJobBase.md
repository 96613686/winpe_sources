# DeviceCommandScheduler::StartCommand(DeviceCommand *,IOperationCompletionCallback *,CJobBase *)

- ea: `0x14002a7c8`
- end: `0x14002aa1f`
- name: `?StartCommand@DeviceCommandScheduler@@QEAAHPEAVDeviceCommand@@PEAVIOperationCompletionCallback@@PEAVCJobBase@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(DeviceCommandScheduler *__hidden this, struct DeviceCommand *, struct IOperationCompletionCallback *, struct CJobBase *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140029f94`
- `0x14002a604`
- `0x14004bf10`

## callees

- `0x1400067b0`
- `0x1400122e0`
- `0x140023ae0`
- `0x14002a7c8`
- `0x14002aa28`
- `0x140034e04`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002a8fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a8fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a89e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a89e`

## pseudocode

```c

```

# DeviceCommandScheduler::OnCtlPlaneWdiOidCompleteCallback(ulong,_WFC_MESSAGE_METADATA *,IWdiMessageMemoryManager *)

- ea: `0x140025ad8`
- end: `0x140025d30`
- name: `?OnCtlPlaneWdiOidCompleteCallback@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@PEAVIWdiMessageMemoryManager@@@Z`
- size: `600`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, unsigned int, struct _WFC_MESSAGE_METADATA *, struct IWdiMessageMemoryManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400258c0`

## callees

- `0x1400067b0`
- `0x140025ad8`
- `0x140026490`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140025c1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025c1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025bbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025bbb`
- `ntoskrnl!ExAllocatePool2` at `0x140025b34`
- `ntoskrnl!ExAllocatePool2` at `0x140025b34`

## pseudocode

```c

```

# Fn_EVENT_ReadRemoteExtendedFeaturesComplete(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x1400ad400`
- end: `0x1400ad57c`
- name: `?Fn_EVENT_ReadRemoteExtendedFeaturesComplete@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `380`
- prototype: `unsigned __int8 __fastcall(struct HCI_INTERFACE *, union _HCI_COMMAND *, union _HCI_EVENT *, struct _HCI_CONNECTION *, struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400278d8`
- `0x14005b478`
- `0x1400ad400`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ad561`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ad561`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400ad555`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400ad555`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400ad528`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400ad528`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ad510`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ad510`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ad4bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ad4bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ad504`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ad504`

## pseudocode

```c

```

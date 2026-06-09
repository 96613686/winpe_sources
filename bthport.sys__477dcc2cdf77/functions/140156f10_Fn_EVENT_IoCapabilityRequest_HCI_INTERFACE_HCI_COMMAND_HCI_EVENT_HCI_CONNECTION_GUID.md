# Fn_EVENT_IoCapabilityRequest(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x140156f10`
- end: `0x1401579d4`
- name: `?Fn_EVENT_IoCapabilityRequest@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `2756`
- prototype: `unsigned __int8 __usercall@<al>(struct HCI_INTERFACE *@<rcx>, union _HCI_COMMAND *@<rdx>, union _HCI_EVENT *@<r8>, struct _HCI_CONNECTION *@<r9>, struct _GUID *)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005a64`
- `0x140005b4c`
- `0x140005c04`
- `0x14000764c`
- `0x14001fddc`
- `0x1400350f0`
- `0x14003b644`
- `0x14007403c`
- `0x1400a7fb4`
- `0x140156f10`
- `0x14015b5cc`
- `0x140162f44`
- `0x140165540`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401578d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401578d9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401578cd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401578cd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140157044`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140157044`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015702d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015702d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401578f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401578f2`
- `ntoskrnl!ExAllocatePool2` at `0x1401570b9`
- `ntoskrnl!ExAllocatePool2` at `0x1401570b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140156fc0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140156fc0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140157021`
- `ntoskrnl!KeReleaseSpinLock` at `0x140157021`

## pseudocode

```c

```

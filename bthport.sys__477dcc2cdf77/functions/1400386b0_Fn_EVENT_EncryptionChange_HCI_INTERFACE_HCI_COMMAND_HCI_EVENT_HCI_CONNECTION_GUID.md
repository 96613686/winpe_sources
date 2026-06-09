# Fn_EVENT_EncryptionChange(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x1400386b0`
- end: `0x140038a16`
- name: `?Fn_EVENT_EncryptionChange@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `870`
- prototype: `unsigned __int8 __usercall@<al>(struct HCI_INTERFACE *@<rcx>, union _HCI_COMMAND *@<rdx>, union _HCI_EVENT *@<r8>, struct _HCI_CONNECTION *@<r9>, struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140005608`
- `0x140035fc8`
- `0x1400368b0`
- `0x140036dac`
- `0x1400386b0`
- `0x1400457f4`
- `0x140092338`
- `0x140092fe8`
- `0x1400a53fc`
- `0x140161a44`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140038885`
- `ntoskrnl!KeSetTimer` at `0x140038885`
- `ntoskrnl!KeCancelTimer` at `0x1400388a7`
- `ntoskrnl!KeCancelTimer` at `0x1400388a7`
- `ntoskrnl!ExAllocatePool2` at `0x140038926`
- `ntoskrnl!ExAllocatePool2` at `0x140038926`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003872f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003872f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400388e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400388e1`

## pseudocode

```c

```

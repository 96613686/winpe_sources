# Fn_CC_Change_Local_Name(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x1400ac9f0`
- end: `0x1400acb7a`
- name: `?Fn_CC_Change_Local_Name@@YAXPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `394`
- prototype: `void __usercall(struct HCI_INTERFACE *@<rcx>, union _HCI_COMMAND *@<rdx>, union _HCI_EVENT *@<r8>, struct _HCI_CONNECTION *@<r9>, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14006a708`
- `0x140165540`

## import_xrefs

- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x1400acb57`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x1400acb57`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400aca20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400aca20`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400acaf9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400acaf9`

## pseudocode

```c

```

# Fn_EVENT_InquiryResult(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x14006f030`
- end: `0x14006f27f`
- name: `?Fn_EVENT_InquiryResult@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `591`
- prototype: `unsigned __int8 __usercall@<al>(struct HCI_INTERFACE *@<rcx>, union _HCI_COMMAND *@<rdx>, union _HCI_EVENT *@<r8>, struct _HCI_CONNECTION *@<r9>, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140005690`
- `0x140005748`
- `0x140065b40`
- `0x14006f030`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006f0e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006f0e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006f181`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006f198`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006f181`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006f198`

## pseudocode

```c

```

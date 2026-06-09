# Fn_EVENT_ExtendedInquiryResult(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x14006ed90`
- end: `0x14006f020`
- name: `?Fn_EVENT_ExtendedInquiryResult@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `656`
- prototype: `unsigned __int8 __usercall@<al>(struct HCI_INTERFACE *@<rcx>, union _HCI_COMMAND *@<rdx>, union _HCI_EVENT *@<r8>, struct _HCI_CONNECTION *@<r9>, struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140005690`
- `0x140005748`
- `0x140065b40`
- `0x14006ed90`
- `0x1400af954`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006ee49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006ee49`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006eee4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006eefb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006eee4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006eefb`

## pseudocode

```c

```

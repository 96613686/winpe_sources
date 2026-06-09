# Fn_EVENT_ConnectionRequest(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x140037f30`
- end: `0x14003843a`
- name: `?Fn_EVENT_ConnectionRequest@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `1290`
- prototype: `unsigned __int8 __usercall@<al>(struct HCI_INTERFACE *@<rcx>, union _HCI_COMMAND *@<rdx>, union _HCI_EVENT *@<r8>, struct _HCI_CONNECTION *@<r9>, struct _GUID *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140001098`
- `0x14000113c`
- `0x140005608`
- `0x1400350f0`
- `0x14003667c`
- `0x140036780`
- `0x140037f30`
- `0x140043a60`
- `0x14004bb00`
- `0x14004bc08`
- `0x14013a260`
- `0x14013b394`
- `0x140165540`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400381fb`
- `ntoskrnl!ExAllocatePool2` at `0x1400381fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400380c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400380c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003813c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038155`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003813c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038155`

## pseudocode

```c

```

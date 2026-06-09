# Fn_EVENT_ReadClockOffsetComplete(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x1400393f0`
- end: `0x140039609`
- name: `?Fn_EVENT_ReadClockOffsetComplete@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `537`
- prototype: `unsigned __int8 __fastcall(struct HCI_INTERFACE *, union _HCI_COMMAND *, union _HCI_EVENT *, struct _HCI_CONNECTION *, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140005690`
- `0x140036020`
- `0x1400393f0`
- `0x140060dc4`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400394e6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400394e6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140039483`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140039483`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003943e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003943e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400395ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400395ce`

## pseudocode

```c

```

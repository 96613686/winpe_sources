# Fn_EVENT_RemoteNameRequestComplete(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x1400a9a50`
- end: `0x1400aa232`
- name: `?Fn_EVENT_RemoteNameRequestComplete@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `2018`
- prototype: `unsigned __int8 __fastcall(struct HCI_INTERFACE *, union _HCI_COMMAND *, union _HCI_EVENT *, struct _HCI_CONNECTION *, struct _GUID *)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x140005b4c`
- `0x140010bf8`
- `0x14001d1c0`
- `0x140041f28`
- `0x140052db8`
- `0x1400594d8`
- `0x14005ad28`
- `0x14005f234`
- `0x14005fcf4`
- `0x14007fb74`
- `0x1400a9a50`
- `0x1400aa380`
- `0x1400ab004`
- `0x1400ab1e8`
- `0x1400af954`
- `0x1400b9d78`
- `0x140158760`
- `0x140161a44`
- `0x140161d7c`
- `0x14016235c`
- `0x140162f44`
- `0x140165540`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa1d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa1d8`
- `ntoskrnl!ExAllocatePool2` at `0x1400a9ec1`
- `ntoskrnl!ExAllocatePool2` at `0x1400a9ec1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a9b17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a9b17`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400aa13f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400aa13f`

## pseudocode

```c

```

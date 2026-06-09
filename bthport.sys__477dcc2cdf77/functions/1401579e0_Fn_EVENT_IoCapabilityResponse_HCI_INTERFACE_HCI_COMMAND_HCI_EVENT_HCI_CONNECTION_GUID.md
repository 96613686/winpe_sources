# Fn_EVENT_IoCapabilityResponse(HCI_INTERFACE *,_HCI_COMMAND *,_HCI_EVENT *,_HCI_CONNECTION *,_GUID *)

- ea: `0x1401579e0`
- end: `0x140157b76`
- name: `?Fn_EVENT_IoCapabilityResponse@@YAEPEAUHCI_INTERFACE@@PEAT_HCI_COMMAND@@PEAT_HCI_EVENT@@PEAU_HCI_CONNECTION@@PEAU_GUID@@@Z`
- size: `406`
- prototype: `unsigned __int8 __fastcall(struct HCI_INTERFACE *, union _HCI_COMMAND *, union _HCI_EVENT *, struct _HCI_CONNECTION *, struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x1401579e0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157ab8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140157ab8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140157aac`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140157aac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140157a79`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140157a79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157a62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157a62`

## pseudocode

```c

```

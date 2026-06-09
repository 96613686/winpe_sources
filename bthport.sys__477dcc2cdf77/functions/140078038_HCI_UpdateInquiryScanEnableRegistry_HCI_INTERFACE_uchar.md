# HCI_UpdateInquiryScanEnableRegistry(HCI_INTERFACE *,uchar)

- ea: `0x140078038`
- end: `0x1400781b0`
- name: `?HCI_UpdateInquiryScanEnableRegistry@@YAXPEAUHCI_INTERFACE@@E@Z`
- size: `376`
- prototype: `void __fastcall(struct HCI_INTERFACE *, unsigned __int8)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140077144`
- `0x140078c00`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005690`
- `0x14000f27c`
- `0x14000fab4`
- `0x140078038`
- `0x14015ce38`
- `0x1401b8fc0`
- `0x1402093a8`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1400780ec`
- `ntoskrnl!ZwSetValueKey` at `0x1400780ec`
- `ntoskrnl!KeGetCurrentIrql` at `0x140078052`
- `ntoskrnl!KeGetCurrentIrql` at `0x140078052`

## string_xrefs

- `0x140078098`: `Write Scan Enable`

## pseudocode

```c

```

# HCI_AuthenticationResponseComplete(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)

- ea: `0x1400a4e30`
- end: `0x1400a50ac`
- name: `?HCI_AuthenticationResponseComplete@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z`
- size: `636`
- prototype: `void(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005608`
- `0x140005748`
- `0x14000bdb8`
- `0x14003a890`
- `0x140042070`
- `0x1400a4e30`
- `0x140161d7c`
- `0x140162f44`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400a4fd2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a4fd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a5031`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a5031`
- `ntoskrnl!KeSetEvent` at `0x1400a4fc1`
- `ntoskrnl!KeSetEvent` at `0x1400a4fc1`

## pseudocode

```c

```

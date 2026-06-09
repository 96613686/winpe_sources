# SMPDibContext_Create(_SMP_INTERFACE *,DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE,SMPDIB_CONTEXT * *)

- ea: `0x1401f50d0`
- end: `0x1401f52f0`
- name: `?SMPDibContext_Create@@YAJPEAU_SMP_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@W4_HCI_PHY_TYPE@@PEAPEAUSMPDIB_CONTEXT@@@Z`
- size: `544`
- prototype: `int(struct _SMP_INTERFACE *, struct DEVICE_INFO_BLOCK *, enum _HCI_PHY_TYPE, struct SMPDIB_CONTEXT **)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x1401518a0`
- `0x14015319c`
- `0x140153c50`
- `0x140154e70`

## callees

- `0x140005690`
- `0x140005b4c`
- `0x14014ff90`
- `0x140153650`
- `0x14015eea0`
- `0x140161a44`
- `0x140161c78`
- `0x140165940`
- `0x1401f50d0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1401f51a4`
- `ntoskrnl!EtwActivityIdControl` at `0x1401f51a4`
- `ntoskrnl!KeInitializeDpc` at `0x1401f518c`
- `ntoskrnl!KeInitializeDpc` at `0x1401f518c`
- `ntoskrnl!KeInitializeTimerEx` at `0x1401f516f`
- `ntoskrnl!KeInitializeTimerEx` at `0x1401f516f`

## pseudocode

```c

```

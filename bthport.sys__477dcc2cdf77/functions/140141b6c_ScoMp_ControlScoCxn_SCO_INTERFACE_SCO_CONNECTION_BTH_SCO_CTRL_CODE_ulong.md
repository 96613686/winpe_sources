# ScoMp_ControlScoCxn(_SCO_INTERFACE *,_SCO_CONNECTION *,_BTH_SCO_CTRL_CODE,ulong)

- ea: `0x140141b6c`
- end: `0x140141d47`
- name: `?ScoMp_ControlScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@W4_BTH_SCO_CTRL_CODE@@K@Z`
- size: `475`
- prototype: `__int64 __fastcall(struct _SCO_INTERFACE *, struct _SCO_CONNECTION *, enum _BTH_SCO_CTRL_CODE, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140144140`

## callees

- `0x140005ce8`
- `0x14002702c`
- `0x14013e32c`
- `0x140141b6c`
- `0x140165540`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140141ca8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140141ca8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140141c4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140141c4e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141c71`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141c71`
- `ntoskrnl!KeSetEvent` at `0x140141c9c`
- `ntoskrnl!KeSetEvent` at `0x140141c9c`

## pseudocode

```c

```

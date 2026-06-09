# ScoMp_RemoveScoCxn(_SCO_INTERFACE *,_SCO_CONNECTION *)

- ea: `0x140141d50`
- end: `0x140141f33`
- name: `?ScoMp_RemoveScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct _SCO_INTERFACE *, struct _SCO_CONNECTION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401384b0`

## callees

- `0x140005ce8`
- `0x14000764c`
- `0x140139c94`
- `0x14013e32c`
- `0x140141d50`
- `0x140161d7c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140141e74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140141e74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140141e17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140141e17`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141e3a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141e3a`
- `ntoskrnl!KeSetEvent` at `0x140141e68`
- `ntoskrnl!KeSetEvent` at `0x140141e68`

## string_xrefs

- `0x140141e8a`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\scominiport.cpp`

## pseudocode

```c

```

# MpRemoveProcessNotifyRoutine

- ea: `0x140083b94`
- end: `0x140083c50`
- name: `MpRemoveProcessNotifyRoutine`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x140011890`
- `0x140083b94`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x140083c44`
- `ntoskrnl!ExUnregisterCallback` at `0x140083bca`
- `ntoskrnl!ExUnregisterCallback` at `0x140083bca`
- `ntoskrnl!ObfDereferenceObject` at `0x140083bab`
- `ntoskrnl!ObfDereferenceObject` at `0x140083be9`
- `ntoskrnl!ObfDereferenceObject` at `0x140083bab`
- `ntoskrnl!ObfDereferenceObject` at `0x140083be9`

## pseudocode

```c

```

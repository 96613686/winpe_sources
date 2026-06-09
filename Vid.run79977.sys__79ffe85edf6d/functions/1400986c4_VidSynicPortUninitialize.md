# VidSynicPortUninitialize

- ea: `0x1400986c4`
- end: `0x14009874f`
- name: `VidSynicPortUninitialize`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140083544`
- `0x140097d38`

## callees

- `0x1400986c4`

## import_xrefs

- `ntoskrnl!KeRemoveQueueDpc` at `0x1400986f9`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400986f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009872f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009872f`
- `winhvr!WinHvSetSyntheticInterruptHandler` at `0x1400986dd`
- `winhvr!WinHvSetSyntheticInterruptHandler` at `0x1400986dd`
- `winhvr!WinHvFreePartitionSintIndex` at `0x14009870e`
- `winhvr!WinHvFreePartitionSintIndex` at `0x14009870e`

## pseudocode

```c

```

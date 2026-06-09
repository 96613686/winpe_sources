# __imp_load_EaDeleteAggregatedEvent

- ea: `0x180026ea6`
- end: `0x180026eb2`
- name: `__imp_load_EaDeleteAggregatedEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180026e15`

## import_xrefs

- `EventAggregation!EaDeleteAggregatedEvent` at `0x180026ea6`

## pseudocode

```c
__int64 load_EaDeleteAggregatedEvent()
{
  return _tailMerge_eventaggregation_dll();
}

```

## disassembly

```asm
0x180026ea6  lea     rax, __imp_EaDeleteAggregatedEvent
0x180026ead  jmp     __tailMerge_eventaggregation_dll
```

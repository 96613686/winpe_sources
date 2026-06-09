# __imp_load_TbDeleteCEvent

- ea: `0x180010723`
- end: `0x18001072f`
- name: `__imp_load_TbDeleteCEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010680`

## import_xrefs

- `TimeBrokerClient!TbDeleteCEvent` at `0x180010723`

## pseudocode

```c
__int64 load_TbDeleteCEvent()
{
  return _tailMerge_timebrokerclient_dll();
}

```

## disassembly

```asm
0x180010723  lea     rax, __imp_TbDeleteCEvent
0x18001072a  jmp     __tailMerge_timebrokerclient_dll
```

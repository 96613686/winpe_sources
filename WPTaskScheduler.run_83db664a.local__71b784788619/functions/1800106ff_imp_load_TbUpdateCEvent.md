# __imp_load_TbUpdateCEvent

- ea: `0x1800106ff`
- end: `0x18001070b`
- name: `__imp_load_TbUpdateCEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180010680`

## import_xrefs

- `TimeBrokerClient!TbUpdateCEvent` at `0x1800106ff`

## pseudocode

```c
__int64 load_TbUpdateCEvent()
{
  return _tailMerge_timebrokerclient_dll();
}

```

## disassembly

```asm
0x1800106ff  lea     rax, __imp_TbUpdateCEvent
0x180010706  jmp     __tailMerge_timebrokerclient_dll
```

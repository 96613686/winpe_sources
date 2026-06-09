# __imp_load_SRCache_AllocStringBuffer

- ea: `0x1800025e0`
- end: `0x1800025ec`
- name: `__imp_load_SRCache_AllocStringBuffer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x1800025e0`

## pseudocode

```c
__int64 load_SRCache_AllocStringBuffer()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800025e0  lea     rax, __imp_SRCache_AllocStringBuffer
0x1800025e7  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```

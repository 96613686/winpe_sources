# __imp_load_MFCreateTopologyNode

- ea: `0x1800185f5`
- end: `0x180018601`
- name: `__imp_load_MFCreateTopologyNode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180018564`

## import_xrefs

- `MFCORE!MFCreateTopologyNode` at `0x1800185f5`

## pseudocode

```c
__int64 load_MFCreateTopologyNode()
{
  return _tailMerge_mfcore_dll();
}

```

## disassembly

```asm
0x1800185f5  lea     rax, __imp_MFCreateTopologyNode
0x1800185fc  jmp     __tailMerge_mfcore_dll
```

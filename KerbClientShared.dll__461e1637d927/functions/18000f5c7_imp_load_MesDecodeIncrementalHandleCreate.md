# __imp_load_MesDecodeIncrementalHandleCreate

- ea: `0x18000f5c7`
- end: `0x18000f5d3`
- name: `__imp_load_MesDecodeIncrementalHandleCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f536`

## import_xrefs

- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18000f5c7`

## pseudocode

```c
__int64 load_MesDecodeIncrementalHandleCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000f5c7  lea     rax, __imp_MesDecodeIncrementalHandleCreate
0x18000f5ce  jmp     __tailMerge_rpcrt4_dll
```

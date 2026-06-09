# __imp_load_FwRegSetDWord

- ea: `0x180020862`
- end: `0x18002086e`
- name: `__imp_load_FwRegSetDWord`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwRegSetDWord` at `0x180020862`

## pseudocode

```c
__int64 load_FwRegSetDWord()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020862  lea     rax, __imp_FwRegSetDWord
0x180020869  jmp     __tailMerge_fwbase_dll
```

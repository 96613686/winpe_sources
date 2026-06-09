# __imp_load_StgDeserializePropVariant

- ea: `0x18001826e`
- end: `0x18001827a`
- name: `__imp_load_StgDeserializePropVariant`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800181dd`

## import_xrefs

- `PROPSYS!StgDeserializePropVariant` at `0x18001826e`

## pseudocode

```c
__int64 load_StgDeserializePropVariant()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x18001826e  lea     rax, __imp_StgDeserializePropVariant
0x180018275  jmp     __tailMerge_propsys_dll
```

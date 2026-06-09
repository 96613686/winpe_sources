# __imp_load_PropVariantCompareEx

- ea: `0x180010154`
- end: `0x180010160`
- name: `__imp_load_PropVariantCompareEx`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800100d5`

## import_xrefs

- `PROPSYS!PropVariantCompareEx` at `0x180010154`

## pseudocode

```c
__int64 load_PropVariantCompareEx()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180010154  lea     rax, __imp_PropVariantCompareEx
0x18001015b  jmp     __tailMerge_propsys_dll
```

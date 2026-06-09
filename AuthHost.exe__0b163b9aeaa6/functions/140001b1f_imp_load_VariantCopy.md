# __imp_load_VariantCopy

- ea: `0x140001b1f`
- end: `0x140001b2b`
- name: `__imp_load_VariantCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001aa0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x140001b1f`

## pseudocode

```c
__int64 load_VariantCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x140001b1f  lea     rax, __imp_VariantCopy
0x140001b26  jmp     __tailMerge_oleaut32_dll
```

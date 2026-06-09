# __imp_load_SafeArrayAccessData

- ea: `0x1800025c7`
- end: `0x1800025d3`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d5f`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800025c7`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x1800025c7  lea     rax, __imp_SafeArrayAccessData
0x1800025ce  jmp     __tailMerge_oleaut32_dll
```

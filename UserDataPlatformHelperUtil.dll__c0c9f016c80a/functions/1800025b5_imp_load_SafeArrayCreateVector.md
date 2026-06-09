# __imp_load_SafeArrayCreateVector

- ea: `0x1800025b5`
- end: `0x1800025c1`
- name: `__imp_load_SafeArrayCreateVector`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d5f`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800025b5`

## pseudocode

```c
__int64 load_SafeArrayCreateVector()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x1800025b5  lea     rax, __imp_SafeArrayCreateVector
0x1800025bc  jmp     __tailMerge_oleaut32_dll
```

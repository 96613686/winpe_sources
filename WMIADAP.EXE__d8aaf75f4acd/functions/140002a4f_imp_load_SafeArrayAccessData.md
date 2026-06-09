# __imp_load_SafeArrayAccessData

- ea: `0x140002a4f`
- end: `0x140002a5b`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001dbc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140002a4f`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x140002a4f  lea     rax, __imp_SafeArrayAccessData
0x140002a56  jmp     __tailMerge_oleaut32_dll
```

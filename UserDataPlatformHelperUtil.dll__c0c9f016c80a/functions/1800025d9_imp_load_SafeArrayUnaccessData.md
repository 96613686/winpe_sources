# __imp_load_SafeArrayUnaccessData

- ea: `0x1800025d9`
- end: `0x1800025e5`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d5f`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800025d9`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x1800025d9  lea     rax, __imp_SafeArrayUnaccessData
0x1800025e0  jmp     __tailMerge_oleaut32_dll
```

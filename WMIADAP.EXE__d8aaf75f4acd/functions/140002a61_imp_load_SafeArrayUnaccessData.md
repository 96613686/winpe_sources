# __imp_load_SafeArrayUnaccessData

- ea: `0x140002a61`
- end: `0x140002a6d`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001dbc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140002a61`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x140002a61  lea     rax, __imp_SafeArrayUnaccessData
0x140002a68  jmp     __tailMerge_oleaut32_dll
```

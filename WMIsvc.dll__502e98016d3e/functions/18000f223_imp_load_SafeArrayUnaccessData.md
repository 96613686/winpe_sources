# __imp_load_SafeArrayUnaccessData

- ea: `0x18000f223`
- end: `0x18000f22f`
- name: `__imp_load_SafeArrayUnaccessData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f180`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000f223`

## pseudocode

```c
__int64 load_SafeArrayUnaccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000f223  lea     rax, __imp_SafeArrayUnaccessData
0x18000f22a  jmp     __tailMerge_oleaut32_dll
```

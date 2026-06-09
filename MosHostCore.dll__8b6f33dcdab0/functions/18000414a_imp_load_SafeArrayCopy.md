# __imp_load_SafeArrayCopy

- ea: `0x18000414a`
- end: `0x180004156`
- name: `__imp_load_SafeArrayCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000404d`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000414a`

## pseudocode

```c
__int64 load_SafeArrayCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000414a  lea     rax, __imp_SafeArrayCopy
0x180004151  jmp     __tailMerge_oleaut32_dll
```

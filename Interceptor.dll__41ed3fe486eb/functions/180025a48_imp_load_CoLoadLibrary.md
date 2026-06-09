# __imp_load_CoLoadLibrary

- ea: `0x180025a48`
- end: `0x180025a54`
- name: `__imp_load_CoLoadLibrary`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180025984`

## import_xrefs

- `ole32!CoLoadLibrary` at `0x180025a48`

## pseudocode

```c
__int64 load_CoLoadLibrary()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180025a48  lea     rax, __imp_CoLoadLibrary
0x180025a4f  jmp     __tailMerge_ole32_dll
```

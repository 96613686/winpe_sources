# __imp_load_PSCreateMemoryPropertyStore

- ea: `0x180010166`
- end: `0x180010172`
- name: `__imp_load_PSCreateMemoryPropertyStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800100d5`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180010166`

## pseudocode

```c
__int64 load_PSCreateMemoryPropertyStore()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180010166  lea     rax, __imp_PSCreateMemoryPropertyStore
0x18001016d  jmp     __tailMerge_propsys_dll
```

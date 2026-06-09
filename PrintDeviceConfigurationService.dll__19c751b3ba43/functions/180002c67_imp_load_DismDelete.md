# __imp_load_DismDelete

- ea: `0x180002c67`
- end: `0x180002c73`
- name: `__imp_load_DismDelete`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b8e`

## import_xrefs

- `DismApi!DismDelete` at `0x180002c67`

## pseudocode

```c
__int64 load_DismDelete()
{
  return _tailMerge_dismapi_dll();
}

```

## disassembly

```asm
0x180002c67  lea     rax, __imp_DismDelete
0x180002c6e  jmp     __tailMerge_dismapi_dll
```

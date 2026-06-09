# __imp_load_DismOpenSession

- ea: `0x180002c43`
- end: `0x180002c4f`
- name: `__imp_load_DismOpenSession`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b8e`

## import_xrefs

- `DismApi!DismOpenSession` at `0x180002c43`

## pseudocode

```c
__int64 load_DismOpenSession()
{
  return _tailMerge_dismapi_dll();
}

```

## disassembly

```asm
0x180002c43  lea     rax, __imp_DismOpenSession
0x180002c4a  jmp     __tailMerge_dismapi_dll
```

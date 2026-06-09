# __imp_load_CreateStoreManager

- ea: `0x180002387`
- end: `0x180002393`
- name: `__imp_load_CreateStoreManager`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002308`

## import_xrefs

- `unistore!CreateStoreManager` at `0x180002387`

## pseudocode

```c
__int64 load_CreateStoreManager()
{
  return _tailMerge_unistore_dll();
}

```

## disassembly

```asm
0x180002387  lea     rax, __imp_CreateStoreManager
0x18000238e  jmp     __tailMerge_unistore_dll
```

# __imp_load_NduOpenHandle

- ea: `0x18000933f`
- end: `0x18000934b`
- name: `__imp_load_NduOpenHandle`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800092c0`

## import_xrefs

- `NduProv!__imp_NduOpenHandle` at `0x18000933f`

## pseudocode

```c
__int64 load_NduOpenHandle()
{
  return _tailMerge_nduprov_dll();
}

```

## disassembly

```asm
0x18000933f  lea     rax, __imp_NduOpenHandle
0x180009346  jmp     __tailMerge_nduprov_dll
```

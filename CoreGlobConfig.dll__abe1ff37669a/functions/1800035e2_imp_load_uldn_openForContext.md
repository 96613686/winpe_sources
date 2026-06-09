# __imp_load_uldn_openForContext

- ea: `0x1800035e2`
- end: `0x1800035ee`
- name: `__imp_load_uldn_openForContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003563`

## import_xrefs

- `icu!uldn_openForContext` at `0x1800035e2`

## pseudocode

```c
__int64 load_uldn_openForContext()
{
  return _tailMerge_icu_dll();
}

```

## disassembly

```asm
0x1800035e2  lea     rax, __imp_uldn_openForContext
0x1800035e9  jmp     __tailMerge_icu_dll
```

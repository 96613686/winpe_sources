# __imp_load_CopySid

- ea: `0x180002436`
- end: `0x180002442`
- name: `__imp_load_CopySid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!CopySid` at `0x180002436`

## pseudocode

```c
__int64 load_CopySid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002436  lea     rax, __imp_CopySid
0x18000243d  jmp     __tailMerge_advapi32_dll
```

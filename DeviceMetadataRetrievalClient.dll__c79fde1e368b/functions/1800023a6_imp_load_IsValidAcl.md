# __imp_load_IsValidAcl

- ea: `0x1800023a6`
- end: `0x1800023b2`
- name: `__imp_load_IsValidAcl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!IsValidAcl` at `0x1800023a6`

## pseudocode

```c
__int64 load_IsValidAcl()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800023a6  lea     rax, __imp_IsValidAcl
0x1800023ad  jmp     __tailMerge_advapi32_dll
```

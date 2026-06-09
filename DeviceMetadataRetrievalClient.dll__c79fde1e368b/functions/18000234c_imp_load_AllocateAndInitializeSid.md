# __imp_load_AllocateAndInitializeSid

- ea: `0x18000234c`
- end: `0x180002358`
- name: `__imp_load_AllocateAndInitializeSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x18000234c`

## pseudocode

```c
__int64 load_AllocateAndInitializeSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000234c  lea     rax, __imp_AllocateAndInitializeSid
0x180002353  jmp     __tailMerge_advapi32_dll
```

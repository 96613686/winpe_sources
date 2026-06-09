# __imp_load_IsValidSid

- ea: `0x18000235e`
- end: `0x18000236a`
- name: `__imp_load_IsValidSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x18000235e`

## pseudocode

```c
__int64 load_IsValidSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000235e  lea     rax, __imp_IsValidSid
0x180002365  jmp     __tailMerge_advapi32_dll
```

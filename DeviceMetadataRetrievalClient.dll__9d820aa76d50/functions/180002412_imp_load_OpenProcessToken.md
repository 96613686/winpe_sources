# __imp_load_OpenProcessToken

- ea: `0x180002412`
- end: `0x18000241e`
- name: `__imp_load_OpenProcessToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180002412`

## pseudocode

```c
__int64 load_OpenProcessToken()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002412  lea     rax, __imp_OpenProcessToken
0x180002419  jmp     __tailMerge_advapi32_dll
```

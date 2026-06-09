# __imp_load_OpenThreadToken

- ea: `0x180002400`
- end: `0x18000240c`
- name: `__imp_load_OpenThreadToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x180002400`

## pseudocode

```c
__int64 load_OpenThreadToken()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002400  lea     rax, __imp_OpenThreadToken
0x180002407  jmp     __tailMerge_advapi32_dll
```

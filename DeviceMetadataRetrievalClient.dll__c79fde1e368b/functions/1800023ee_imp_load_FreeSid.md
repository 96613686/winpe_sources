# __imp_load_FreeSid

- ea: `0x1800023ee`
- end: `0x1800023fa`
- name: `__imp_load_FreeSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x1800023ee`

## pseudocode

```c
__int64 load_FreeSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800023ee  lea     rax, __imp_FreeSid
0x1800023f5  jmp     __tailMerge_advapi32_dll
```

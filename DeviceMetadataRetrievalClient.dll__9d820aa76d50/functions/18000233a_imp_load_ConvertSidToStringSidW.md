# __imp_load_ConvertSidToStringSidW

- ea: `0x18000233a`
- end: `0x180002346`
- name: `__imp_load_ConvertSidToStringSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x18000233a`

## pseudocode

```c
__int64 load_ConvertSidToStringSidW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000233a  lea     rax, __imp_ConvertSidToStringSidW
0x180002341  jmp     __tailMerge_advapi32_dll
```

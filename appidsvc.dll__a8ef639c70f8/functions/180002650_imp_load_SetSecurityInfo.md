# __imp_load_SetSecurityInfo

- ea: `0x180002650`
- end: `0x18000265c`
- name: `__imp_load_SetSecurityInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800025ac`

## import_xrefs

- `ADVAPI32!SetSecurityInfo` at `0x180002650`

## pseudocode

```c
__int64 load_SetSecurityInfo()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002650  lea     rax, __imp_SetSecurityInfo
0x180002657  jmp     __tailMerge_advapi32_dll
```

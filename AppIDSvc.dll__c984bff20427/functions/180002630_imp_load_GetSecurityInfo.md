# __imp_load_GetSecurityInfo

- ea: `0x180002630`
- end: `0x18000263c`
- name: `__imp_load_GetSecurityInfo`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800025ac`

## import_xrefs

- `ADVAPI32!GetSecurityInfo` at `0x180002630`

## pseudocode

```c
__int64 load_GetSecurityInfo()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002630  lea     rax, __imp_GetSecurityInfo
0x180002637  jmp     __tailMerge_advapi32_dll
```

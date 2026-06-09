# __imp_load_GetChamberSidFromId

- ea: `0x180003201`
- end: `0x18000320d`
- name: `__imp_load_GetChamberSidFromId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003182`

## import_xrefs

- `ext-ms-win-security-chambers-l1-1-0!GetChamberSidFromId` at `0x180003201`

## pseudocode

```c
__int64 load_GetChamberSidFromId()
{
  return _tailMerge_ext_ms_win_security_chambers_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003201  lea     rax, __imp_GetChamberSidFromId
0x180003208  jmp     __tailMerge_ext_ms_win_security_chambers_l1_1_0_dll
```

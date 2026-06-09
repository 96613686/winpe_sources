# __imp_load_Tbsip_Submit_Command

- ea: `0x180077cd6`
- end: `0x180077ce2`
- name: `__imp_load_Tbsip_Submit_Command`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180077c0f`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x180077cd6`

## pseudocode

```c
__int64 load_Tbsip_Submit_Command()
{
  return _tailMerge_tbs_dll();
}

```

## disassembly

```asm
0x180077cd6  lea     rax, __imp_Tbsip_Submit_Command
0x180077cdd  jmp     __tailMerge_tbs_dll
```

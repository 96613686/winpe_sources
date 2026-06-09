# __imp_load_SetupOpenInfFileW

- ea: `0x1800035bc`
- end: `0x1800035c8`
- name: `__imp_load_SetupOpenInfFileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800034d6`

## import_xrefs

- `ext-ms-win-setupapi-inf-l1-1-0!SetupOpenInfFileW` at `0x1800035bc`

## pseudocode

```c
__int64 load_SetupOpenInfFileW()
{
  return _tailMerge_ext_ms_win_setupapi_inf_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800035bc  lea     rax, __imp_SetupOpenInfFileW
0x1800035c3  jmp     __tailMerge_ext_ms_win_setupapi_inf_l1_1_0_dll
```

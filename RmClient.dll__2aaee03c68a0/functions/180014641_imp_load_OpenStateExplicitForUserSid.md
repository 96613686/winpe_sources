# __imp_load_OpenStateExplicitForUserSid

- ea: `0x180014641`
- end: `0x18001464d`
- name: `__imp_load_OpenStateExplicitForUserSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001459e`

## import_xrefs

- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicitForUserSid` at `0x180014641`

## pseudocode

```c
__int64 load_OpenStateExplicitForUserSid()
{
  return _tailMerge_api_ms_win_appmodel_state_l1_2_0_dll();
}

```

## disassembly

```asm
0x180014641  lea     rax, __imp_OpenStateExplicitForUserSid
0x180014648  jmp     __tailMerge_api_ms_win_appmodel_state_l1_2_0_dll
```

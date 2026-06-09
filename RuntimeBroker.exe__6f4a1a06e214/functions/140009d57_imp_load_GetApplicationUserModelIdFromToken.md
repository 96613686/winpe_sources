# __imp_load_GetApplicationUserModelIdFromToken

- ea: `0x140009d57`
- end: `0x140009d63`
- name: `__imp_load_GetApplicationUserModelIdFromToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140009cd8`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x140009d57`

## pseudocode

```c
__int64 load_GetApplicationUserModelIdFromToken()
{
  return _tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll();
}

```

## disassembly

```asm
0x140009d57  lea     rax, __imp_GetApplicationUserModelIdFromToken
0x140009d5e  jmp     __tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll
```

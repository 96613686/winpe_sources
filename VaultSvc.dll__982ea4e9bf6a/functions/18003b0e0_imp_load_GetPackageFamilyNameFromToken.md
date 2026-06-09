# __imp_load_GetPackageFamilyNameFromToken

- ea: `0x18003b0e0`
- end: `0x18003b0ec`
- name: `__imp_load_GetPackageFamilyNameFromToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18003b061`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18003b0e0`

## pseudocode

```c
__int64 load_GetPackageFamilyNameFromToken()
{
  return _tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll();
}

```

## disassembly

```asm
0x18003b0e0  lea     rax, __imp_GetPackageFamilyNameFromToken
0x18003b0e7  jmp     __tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll
```

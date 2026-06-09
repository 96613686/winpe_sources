# __imp_load_GetPackageFullNameFromToken

- ea: `0x1800044d6`
- end: `0x1800044e2`
- name: `__imp_load_GetPackageFullNameFromToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004457`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x1800044d6`

## pseudocode

```c
__int64 load_GetPackageFullNameFromToken()
{
  return _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_1_dll();
}

```

## disassembly

```asm
0x1800044d6  lea     rax, __imp_GetPackageFullNameFromToken
0x1800044dd  jmp     __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_1_dll
```

# __imp_load_GetStagedPackagePathByFullName

- ea: `0x180002510`
- end: `0x18000251c`
- name: `__imp_load_GetStagedPackagePathByFullName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000248c`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackagePathByFullName` at `0x180002510`

## pseudocode

```c
__int64 load_GetStagedPackagePathByFullName()
{
  return _tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll();
}

```

## disassembly

```asm
0x180002510  lea     rax, __imp_GetStagedPackagePathByFullName
0x180002517  jmp     __tailMerge_api_ms_win_appmodel_runtime_l1_1_1_dll
```

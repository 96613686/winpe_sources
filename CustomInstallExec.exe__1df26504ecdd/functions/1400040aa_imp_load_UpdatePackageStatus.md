# __imp_load_UpdatePackageStatus

- ea: `0x1400040aa`
- end: `0x1400040b6`
- name: `__imp_load_UpdatePackageStatus`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x14000402b`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1400040aa`

## pseudocode

```c
__int64 load_UpdatePackageStatus()
{
  return _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_1_dll();
}

```

## disassembly

```asm
0x1400040aa  lea     rax, __imp_UpdatePackageStatus
0x1400040b1  jmp     __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_1_dll
```

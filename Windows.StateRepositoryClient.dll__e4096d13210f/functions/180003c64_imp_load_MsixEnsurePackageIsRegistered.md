# __imp_load_MsixEnsurePackageIsRegistered

- ea: `0x180003c64`
- end: `0x180003c70`
- name: `__imp_load_MsixEnsurePackageIsRegistered`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180003be5`

## import_xrefs

- `ext-ms-onecore-appmodel-deployment-internal-l1-1-0!MsixEnsurePackageIsRegistered` at `0x180003c64`

## pseudocode

```c
__int64 load_MsixEnsurePackageIsRegistered()
{
  return _tailMerge_ext_ms_onecore_appmodel_deployment_internal_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003c64  lea     rax, __imp_MsixEnsurePackageIsRegistered
0x180003c6b  jmp     __tailMerge_ext_ms_onecore_appmodel_deployment_internal_l1_1_0_dll
```

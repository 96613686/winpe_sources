# __imp_load_AppContainerDeriveSidFromMoniker

- ea: `0x1800092d0`
- end: `0x1800092dc`
- name: `__imp_load_AppContainerDeriveSidFromMoniker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000921b`

## import_xrefs

- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800092d0`

## pseudocode

```c
__int64 load_AppContainerDeriveSidFromMoniker()
{
  return _tailMerge_api_ms_win_appmodel_identity_l1_2_0_dll();
}

```

## disassembly

```asm
0x1800092d0  lea     rax, __imp_AppContainerDeriveSidFromMoniker
0x1800092d7  jmp     __tailMerge_api_ms_win_appmodel_identity_l1_2_0_dll
```

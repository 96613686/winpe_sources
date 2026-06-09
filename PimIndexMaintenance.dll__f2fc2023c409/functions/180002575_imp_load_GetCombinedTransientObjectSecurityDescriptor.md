# __imp_load_GetCombinedTransientObjectSecurityDescriptor

- ea: `0x180002575`
- end: `0x180002581`
- name: `__imp_load_GetCombinedTransientObjectSecurityDescriptor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800024f6`

## import_xrefs

- `UserDataPlatformHelperUtil!GetCombinedTransientObjectSecurityDescriptor` at `0x180002575`

## pseudocode

```c
__int64 load_GetCombinedTransientObjectSecurityDescriptor()
{
  return _tailMerge_userdataplatformhelperutil_dll();
}

```

## disassembly

```asm
0x180002575  lea     rax, __imp_GetCombinedTransientObjectSecurityDescriptor
0x18000257c  jmp     __tailMerge_userdataplatformhelperutil_dll
```

# __imp_load_AddExtensionProgId

- ea: `0x18000444b`
- end: `0x180004457`
- name: `__imp_load_AddExtensionProgId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043ba`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-4!AddExtensionProgId` at `0x18000444b`

## pseudocode

```c
__int64 load_AddExtensionProgId()
{
  return _tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_4_dll();
}

```

## disassembly

```asm
0x18000444b  lea     rax, __imp_AddExtensionProgId
0x180004452  jmp     __tailMerge_api_ms_win_appmodel_runtime_internal_l1_1_4_dll
```

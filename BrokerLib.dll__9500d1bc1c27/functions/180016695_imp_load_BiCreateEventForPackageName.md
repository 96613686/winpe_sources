# __imp_load_BiCreateEventForPackageName

- ea: `0x180016695`
- end: `0x1800166a1`
- name: `__imp_load_BiCreateEventForPackageName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800165e0`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiCreateEventForPackageName` at `0x180016695`

## pseudocode

```c
__int64 load_BiCreateEventForPackageName()
{
  return _tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll();
}

```

## disassembly

```asm
0x180016695  lea     rax, __imp_BiCreateEventForPackageName
0x18001669c  jmp     __tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll
```

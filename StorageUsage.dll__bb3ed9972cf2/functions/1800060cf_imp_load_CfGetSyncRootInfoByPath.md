# __imp_load_CfGetSyncRootInfoByPath

- ea: `0x1800060cf`
- end: `0x1800060db`
- name: `__imp_load_CfGetSyncRootInfoByPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006050`

## import_xrefs

- `cldapi!CfGetSyncRootInfoByPath` at `0x1800060cf`

## pseudocode

```c
__int64 load_CfGetSyncRootInfoByPath()
{
  return _tailMerge_cldapi_dll();
}

```

## disassembly

```asm
0x1800060cf  lea     rax, __imp_CfGetSyncRootInfoByPath
0x1800060d6  jmp     __tailMerge_cldapi_dll
```

# __imp_load_DXCoreCreateAdapterFactory

- ea: `0x180003151`
- end: `0x18000315d`
- name: `__imp_load_DXCoreCreateAdapterFactory`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030d2`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180003151`

## pseudocode

```c
__int64 load_DXCoreCreateAdapterFactory()
{
  return _tailMerge_ext_ms_win_dxcore_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003151  lea     rax, __imp_DXCoreCreateAdapterFactory
0x180003158  jmp     __tailMerge_ext_ms_win_dxcore_l1_1_0_dll
```

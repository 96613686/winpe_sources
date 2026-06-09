# __imp_load_WriteStorageProperties

- ea: `0x18004e95b`
- end: `0x18004e967`
- name: `__imp_load_WriteStorageProperties`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004e8ca`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!WriteStorageProperties` at `0x18004e95b`

## pseudocode

```c
__int64 load_WriteStorageProperties()
{
  return _tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll();
}

```

## disassembly

```asm
0x18004e95b  lea     rax, __imp_WriteStorageProperties
0x18004e962  jmp     __tailMerge_ext_ms_win_ole32_oleautomation_l1_1_0_dll
```

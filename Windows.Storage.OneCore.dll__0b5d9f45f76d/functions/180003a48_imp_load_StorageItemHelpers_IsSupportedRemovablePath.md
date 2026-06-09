# __imp_load_StorageItemHelpers_IsSupportedRemovablePath

- ea: `0x180003a48`
- end: `0x180003a54`
- name: `__imp_load_StorageItemHelpers_IsSupportedRemovablePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800039c9`

## import_xrefs

- `ext-ms-win-winrt-storage-l1-2-2!StorageItemHelpers_IsSupportedRemovablePath` at `0x180003a48`

## pseudocode

```c
__int64 load_StorageItemHelpers_IsSupportedRemovablePath()
{
  return _tailMerge_ext_ms_win_winrt_storage_l1_2_2_dll();
}

```

## disassembly

```asm
0x180003a48  lea     rax, __imp_StorageItemHelpers_IsSupportedRemovablePath
0x180003a4f  jmp     __tailMerge_ext_ms_win_winrt_storage_l1_2_2_dll
```

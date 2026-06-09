# __imp_load_CreateStorageItemFromPath_FullTrustCaller

- ea: `0x180002134`
- end: `0x180002140`
- name: `__imp_load_CreateStorageItemFromPath_FullTrustCaller`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800020b5`

## import_xrefs

- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180002134`

## pseudocode

```c
__int64 load_CreateStorageItemFromPath_FullTrustCaller()
{
  return _tailMerge_ext_ms_win_winrt_storage_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002134  lea     rax, __imp_CreateStorageItemFromPath_FullTrustCaller
0x18000213b  jmp     __tailMerge_ext_ms_win_winrt_storage_l1_1_0_dll
```

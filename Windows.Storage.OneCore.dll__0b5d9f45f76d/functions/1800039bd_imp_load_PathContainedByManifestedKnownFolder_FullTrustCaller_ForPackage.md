# __imp_load_PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage

- ea: `0x1800039bd`
- end: `0x1800039c9`
- name: `__imp_load_PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000393e`

## import_xrefs

- `ext-ms-win-winrt-storage-l1-2-0!PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage` at `0x1800039bd`

## pseudocode

```c
__int64 load_PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage()
{
  return _tailMerge_ext_ms_win_winrt_storage_l1_2_0_dll();
}

```

## disassembly

```asm
0x1800039bd  lea     rax, __imp_PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage
0x1800039c4  jmp     __tailMerge_ext_ms_win_winrt_storage_l1_2_0_dll
```

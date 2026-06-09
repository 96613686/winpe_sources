# std::_Tree_val<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Min(std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x180001220`
- end: `0x18000123c`
- name: `?_Min@?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@PEAU342@@Z`
- size: `28`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001318`
- `0x180001498`

## callees

- `0x180001220`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Min(
        _QWORD *a1)
{
  __int64 *v1; // rdx

  v1 = (__int64 *)*a1;
  if ( !*(_BYTE *)(*a1 + 41LL) )
  {
    do
    {
      a1 = v1;
      v1 = (__int64 *)*v1;
    }
    while ( !*((_BYTE *)v1 + 41) );
  }
  return a1;
}

```

## disassembly

```asm
0x180001220  mov     rdx, [rcx]
0x180001223  cmp     byte ptr [rdx+29h], 0
0x180001227  jnz     short loc_180001238
0x180001229  mov     rax, [rdx]
0x18000122c  mov     rcx, rdx
0x18000122f  mov     rdx, rax
0x180001232  cmp     byte ptr [rax+29h], 0
0x180001236  jz      short loc_180001229
0x180001238  mov     rax, rcx
0x18000123b  retn
```

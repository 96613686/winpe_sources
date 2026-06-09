# std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x18000b3c4`
- end: `0x18000b40e`
- name: `?_Lrotate@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@@Z`
- size: `74`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d44`

## callees

- `0x18000b3c4`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *result; // rax

  v2 = *(_QWORD **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = *v2;
  if ( !*(_BYTE *)(*v2 + 41LL) )
    *(_QWORD *)(*v2 + 8LL) = a2;
  v2[1] = *(_QWORD *)(a2 + 8);
  result = *(_QWORD **)(a1 + 8);
  if ( a2 == result[1] )
  {
    result[1] = v2;
  }
  else
  {
    result = *(_QWORD **)(a2 + 8);
    if ( a2 == *result )
      *result = v2;
    else
      result[2] = v2;
  }
  *v2 = a2;
  *(_QWORD *)(a2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x18000b3c4  mov     r8, [rdx+10h]
0x18000b3c8  mov     rax, [r8]
0x18000b3cb  mov     [rdx+10h], rax
0x18000b3cf  mov     rax, [r8]
0x18000b3d2  cmp     byte ptr [rax+29h], 0
0x18000b3d6  jnz     short loc_18000B3DC
0x18000b3d8  mov     [rax+8], rdx
0x18000b3dc  mov     rax, [rdx+8]
0x18000b3e0  mov     [r8+8], rax
0x18000b3e4  mov     rax, [rcx+8]
0x18000b3e8  cmp     rdx, [rax+8]
0x18000b3ec  jnz     short loc_18000B3F4
0x18000b3ee  mov     [rax+8], r8
0x18000b3f2  jmp     short loc_18000B406
0x18000b3f4  mov     rax, [rdx+8]
0x18000b3f8  cmp     rdx, [rax]
0x18000b3fb  jnz     short loc_18000B402
0x18000b3fd  mov     [rax], r8
0x18000b400  jmp     short loc_18000B406
0x18000b402  mov     [rax+10h], r8
0x18000b406  mov     [r8], rdx
0x18000b409  mov     [rdx+8], r8
0x18000b40d  retn
```

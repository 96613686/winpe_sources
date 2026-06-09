# std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x18000b414`
- end: `0x18000b460`
- name: `?_Rrotate@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d44`

## callees

- `0x18000b414`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // rax
  _QWORD *result; // rax

  v2 = *a2;
  *a2 = *(_QWORD *)(*a2 + 16LL);
  v3 = *(_QWORD *)(v2 + 16);
  if ( !*(_BYTE *)(v3 + 41) )
    *(_QWORD *)(v3 + 8) = a2;
  *(_QWORD *)(v2 + 8) = a2[1];
  result = *(_QWORD **)(a1 + 8);
  if ( a2 == (_QWORD *)result[1] )
  {
    result[1] = v2;
  }
  else
  {
    result = (_QWORD *)a2[1];
    if ( a2 == (_QWORD *)result[2] )
      result[2] = v2;
    else
      *result = v2;
  }
  *(_QWORD *)(v2 + 16) = a2;
  a2[1] = v2;
  return result;
}

```

## disassembly

```asm
0x18000b414  mov     r8, [rdx]
0x18000b417  mov     rax, [r8+10h]
0x18000b41b  mov     [rdx], rax
0x18000b41e  mov     rax, [r8+10h]
0x18000b422  cmp     byte ptr [rax+29h], 0
0x18000b426  jnz     short loc_18000B42C
0x18000b428  mov     [rax+8], rdx
0x18000b42c  mov     rax, [rdx+8]
0x18000b430  mov     [r8+8], rax
0x18000b434  mov     rax, [rcx+8]
0x18000b438  cmp     rdx, [rax+8]
0x18000b43c  jnz     short loc_18000B444
0x18000b43e  mov     [rax+8], r8
0x18000b442  jmp     short loc_18000B457
0x18000b444  mov     rax, [rdx+8]
0x18000b448  cmp     rdx, [rax+10h]
0x18000b44c  jnz     short loc_18000B454
0x18000b44e  mov     [rax+10h], r8
0x18000b452  jmp     short loc_18000B457
0x18000b454  mov     [rax], r8
0x18000b457  mov     [r8+10h], rdx
0x18000b45b  mov     [rdx+8], r8
0x18000b45f  retn
```

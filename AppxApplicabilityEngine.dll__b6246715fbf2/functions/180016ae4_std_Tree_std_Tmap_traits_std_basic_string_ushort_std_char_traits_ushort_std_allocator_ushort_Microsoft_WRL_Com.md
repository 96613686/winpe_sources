# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x180016ae4`
- end: `0x180016b30`
- name: `?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z`
- size: `76`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002af4`

## callees

- `0x180016ae4`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // rax
  _QWORD *result; // rax

  v2 = *a2;
  *a2 = *(_QWORD *)(*a2 + 16LL);
  v3 = *(_QWORD *)(v2 + 16);
  if ( !*(_BYTE *)(v3 + 73) )
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
0x180016ae4  mov     r8, [rdx]
0x180016ae7  mov     rax, [r8+10h]
0x180016aeb  mov     [rdx], rax
0x180016aee  mov     rax, [r8+10h]
0x180016af2  cmp     byte ptr [rax+49h], 0
0x180016af6  jnz     short loc_180016AFC
0x180016af8  mov     [rax+8], rdx
0x180016afc  mov     rax, [rdx+8]
0x180016b00  mov     [r8+8], rax
0x180016b04  mov     rax, [rcx+8]
0x180016b08  cmp     rdx, [rax+8]
0x180016b0c  jnz     short loc_180016B14
0x180016b0e  mov     [rax+8], r8
0x180016b12  jmp     short loc_180016B27
0x180016b14  mov     rax, [rdx+8]
0x180016b18  cmp     rdx, [rax+10h]
0x180016b1c  jnz     short loc_180016B24
0x180016b1e  mov     [rax+10h], r8
0x180016b22  jmp     short loc_180016B27
0x180016b24  mov     [rax], r8
0x180016b27  mov     [r8+10h], rdx
0x180016b2b  mov     [rdx+8], r8
0x180016b2f  retn
```

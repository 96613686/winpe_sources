# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x180016a94`
- end: `0x180016ade`
- name: `?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z`
- size: `74`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002af4`

## callees

- `0x180016a94`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *result; // rax

  v2 = *(_QWORD **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = *v2;
  if ( !*(_BYTE *)(*v2 + 73LL) )
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
0x180016a94  mov     r8, [rdx+10h]
0x180016a98  mov     rax, [r8]
0x180016a9b  mov     [rdx+10h], rax
0x180016a9f  mov     rax, [r8]
0x180016aa2  cmp     byte ptr [rax+49h], 0
0x180016aa6  jnz     short loc_180016AAC
0x180016aa8  mov     [rax+8], rdx
0x180016aac  mov     rax, [rdx+8]
0x180016ab0  mov     [r8+8], rax
0x180016ab4  mov     rax, [rcx+8]
0x180016ab8  cmp     rdx, [rax+8]
0x180016abc  jnz     short loc_180016AC4
0x180016abe  mov     [rax+8], r8
0x180016ac2  jmp     short loc_180016AD6
0x180016ac4  mov     rax, [rdx+8]
0x180016ac8  cmp     rdx, [rax]
0x180016acb  jnz     short loc_180016AD2
0x180016acd  mov     [rax], r8
0x180016ad0  jmp     short loc_180016AD6
0x180016ad2  mov     [rax+10h], r8
0x180016ad6  mov     [r8], rdx
0x180016ad9  mov     [rdx+8], r8
0x180016add  retn
```

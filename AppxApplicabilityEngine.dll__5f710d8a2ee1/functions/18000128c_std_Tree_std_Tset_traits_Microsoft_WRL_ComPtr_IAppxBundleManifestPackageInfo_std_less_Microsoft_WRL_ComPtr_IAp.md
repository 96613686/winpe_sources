# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Lrotate(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)

- ea: `0x18000128c`
- end: `0x1800012d6`
- name: `?_Lrotate@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001c08`

## callees

- `0x18000128c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Lrotate(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *result; // rax

  v2 = *(_QWORD **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = *v2;
  if ( !*(_BYTE *)(*v2 + 33LL) )
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
0x18000128c  mov     r8, [rdx+10h]
0x180001290  mov     rax, [r8]
0x180001293  mov     [rdx+10h], rax
0x180001297  mov     rax, [r8]
0x18000129a  cmp     byte ptr [rax+21h], 0
0x18000129e  jnz     short loc_1800012A4
0x1800012a0  mov     [rax+8], rdx
0x1800012a4  mov     rax, [rdx+8]
0x1800012a8  mov     [r8+8], rax
0x1800012ac  mov     rax, [rcx+8]
0x1800012b0  cmp     rdx, [rax+8]
0x1800012b4  jnz     short loc_1800012BC
0x1800012b6  mov     [rax+8], r8
0x1800012ba  jmp     short loc_1800012CE
0x1800012bc  mov     rax, [rdx+8]
0x1800012c0  cmp     rdx, [rax]
0x1800012c3  jnz     short loc_1800012CA
0x1800012c5  mov     [rax], r8
0x1800012c8  jmp     short loc_1800012CE
0x1800012ca  mov     [rax+10h], r8
0x1800012ce  mov     [r8], rdx
0x1800012d1  mov     [rdx+8], r8
0x1800012d5  retn
```

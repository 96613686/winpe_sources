# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>> const &)

- ea: `0x1800019d4`
- end: `0x180001a6f`
- name: `??0?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA@AEBV01@@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000181c`

## callees

- `0x1800012e8`
- `0x1800019d4`
- `0x180001a78`
- `0x180001b18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // r8
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // rax
  char v8; // r9
  __int64 *v9; // r8
  __int64 v10; // rdx
  __int64 i; // rcx

  std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(a1);
  try
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(a1);
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
    v4 = *(_QWORD **)(a1 + 8);
    v5 = v4[1];
    if ( *(_BYTE *)(v5 + 33) )
    {
      *v4 = v4;
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
    }
    else
    {
      v7 = std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Min(v5);
      *v9 = v7;
      v10 = *(_QWORD *)(a1 + 8);
      for ( i = *(_QWORD *)(v10 + 8); *(_BYTE *)(*(_QWORD *)(i + 16) + 33LL) == v8; i = *(_QWORD *)(i + 16) )
        ;
      *(_QWORD *)(v10 + 16) = i;
    }
    result = a1;
  }
  catch ( ... )
  {
    std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::clear(a1);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800019d4  mov     [rsp+arg_0], rcx
0x1800019d9  push    rdi
0x1800019da  sub     rsp, 30h
0x1800019de  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800019e7  mov     [rsp+38h+arg_10], rbx
0x1800019ec  mov     rdi, rdx
0x1800019ef  mov     rbx, rcx
0x1800019f2  call    ??0?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA@AEBU?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z; std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> const &,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>)
0x1800019f7  nop
0x1800019f8  mov     rdx, [rdi+8]
0x1800019fc  mov     r8, [rbx+8]
0x180001a00  mov     rdx, [rdx+8]
0x180001a04  mov     rcx, rbx
0x180001a07  call    ?_Copy@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001a0c  mov     rcx, [rbx+8]
0x180001a10  mov     [rcx+8], rax
0x180001a14  mov     rax, [rdi+10h]
0x180001a18  mov     [rbx+10h], rax
0x180001a1c  mov     r8, [rbx+8]
0x180001a20  mov     rcx, [r8+8]
0x180001a24  xor     r9d, r9d
0x180001a27  cmp     [rcx+21h], r9b
0x180001a2b  jz      short loc_180001A46
0x180001a2d  mov     [r8], r8
0x180001a30  mov     rax, [rbx+8]
0x180001a34  mov     [rax+10h], rax
0x180001a38  mov     rax, rbx
0x180001a3b  mov     rbx, [rsp+38h+arg_10]
0x180001a40  add     rsp, 30h
0x180001a44  pop     rdi
0x180001a45  retn
0x180001a46  call    ?_Min@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Min(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001a4b  nop
0x180001a4c  mov     [r8], rax
0x180001a4f  mov     rdx, [rbx+8]
0x180001a53  mov     rcx, [rdx+8]
0x180001a57  jmp     short loc_180001A5D
0x180001a59  mov     rcx, [rcx+10h]
0x180001a5d  mov     rax, [rcx+10h]
0x180001a61  cmp     [rax+21h], r9b
0x180001a65  jz      short loc_180001A59
0x180001a67  mov     [rdx+10h], rcx
0x180001a6b  jmp     short loc_180001A38
```

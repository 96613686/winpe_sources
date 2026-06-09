# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)

- ea: `0x180001b18`
- end: `0x180001bac`
- name: `?_Copy@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@PEAU342@0@Z`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800019d4`
- `0x180001b18`

## callees

- `0x180001b18`
- `0x180001bb4`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rsi
  __int64 v8; // rbx

  v6 = *(_QWORD *)(a1 + 8);
  if ( !*(_BYTE *)(a2 + 33) )
  {
    v8 = std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(
           a1,
           (_QWORD **)(a2 + 24));
    *(_QWORD *)(v8 + 8) = a3;
    *(_BYTE *)(v8 + 32) = *(_BYTE *)(a2 + 32);
    if ( *(_BYTE *)(v6 + 33) )
      v6 = v8;
    try
    {
      *(_QWORD *)v8 = std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(a1);
      *(_QWORD *)(v8 + 16) = std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(a1);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Erase(
        a1,
        (__int64 *)v6);
      throw;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180001b18  mov     rax, rsp
0x180001b1b  mov     [rax+8], rcx
0x180001b1f  push    rdi
0x180001b20  push    r14
0x180001b22  push    r15
0x180001b24  sub     rsp, 30h
0x180001b28  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180001b30  mov     [rax+18h], rbx
0x180001b34  mov     [rax+20h], rsi
0x180001b38  mov     r15, r8
0x180001b3b  mov     r14, rdx
0x180001b3e  mov     rdi, rcx
0x180001b41  mov     rsi, [rcx+8]
0x180001b45  cmp     byte ptr [rdx+21h], 0
0x180001b49  jz      short loc_180001B62
0x180001b4b  mov     rax, rsi
0x180001b4e  mov     rbx, [rsp+48h+arg_10]
0x180001b53  mov     rsi, [rsp+48h+arg_18]
0x180001b58  add     rsp, 30h
0x180001b5c  pop     r15
0x180001b5e  pop     r14
0x180001b60  pop     rdi
0x180001b61  retn
0x180001b62  add     rdx, 18h
0x180001b66  call    ??$_Buynode@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@1@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@Z; std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &)
0x180001b6b  mov     rbx, rax
0x180001b6e  mov     [rax+8], r15
0x180001b72  mov     al, [r14+20h]
0x180001b76  mov     [rbx+20h], al
0x180001b79  cmp     byte ptr [rsi+21h], 0
0x180001b7d  cmovnz  rsi, rbx
0x180001b81  mov     [rsp+48h+arg_8], rsi
0x180001b86  mov     r8, rbx
0x180001b89  mov     rdx, [r14]
0x180001b8c  mov     rcx, rdi
0x180001b8f  call    ?_Copy@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001b94  mov     [rbx], rax
0x180001b97  mov     r8, rbx
0x180001b9a  mov     rdx, [r14+10h]
0x180001b9e  mov     rcx, rdi
0x180001ba1  call    ?_Copy@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001ba6  mov     [rbx+10h], rax
0x180001baa  jmp     short loc_180001B4B
```

# std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &)

- ea: `0x180001bb4`
- end: `0x180001bff`
- name: `??$_Buynode@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@1@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001318`
- `0x180001714`
- `0x180001b18`
- `0x1800052a0`

## callees

- `0x180001bb4`
- `0x180001d88`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(
        __int64 a1,
        _QWORD **a2)
{
  __int64 v3; // rax
  __int64 v4; // rbx
  _QWORD *v5; // rcx
  __int64 result; // rax
  void *v7; // [rsp+48h] [rbp+10h]

  v3 = std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode(a1);
  try
  {
    v4 = v3;
    v7 = (void *)v3;
    v5 = *a2;
    *(_QWORD *)(v3 + 24) = *a2;
    if ( v5 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v5 + 8LL))(v5, *v5);
    result = v4;
  }
  catch ( ... )
  {
    operator delete(v7);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180001bb4  push    rdi
0x180001bb6  sub     rsp, 30h
0x180001bba  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001bc3  mov     [rsp+38h+arg_0], rbx
0x180001bc8  mov     rdi, rdx
0x180001bcb  call    ?_Buynode@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@XZ; std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode(void)
0x180001bd0  mov     rbx, rax
0x180001bd3  mov     [rsp+38h+arg_8], rax
0x180001bd8  mov     rcx, [rdi]
0x180001bdb  mov     [rax+18h], rcx
0x180001bdf  test    rcx, rcx
0x180001be2  jz      short loc_180001BF1
0x180001be4  mov     rdx, [rcx]
0x180001be7  mov     rax, [rdx+8]
0x180001beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bf0  nop
0x180001bf1  mov     rax, rbx
0x180001bf4  mov     rbx, [rsp+38h+arg_0]
0x180001bf9  add     rsp, 30h
0x180001bfd  pop     rdi
0x180001bfe  retn
```

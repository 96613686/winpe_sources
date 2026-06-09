# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)

- ea: `0x180003c80`
- end: `0x180003cdc`
- name: `?_Erase@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z`
- size: `92`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003c30`
- `0x180003c80`
- `0x1800052a0`
- `0x18002290e`

## callees

- `0x180001250`
- `0x180003c80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003ccb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ccb`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Erase(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rbx
  __int64 v4; // rdi

  v2 = a2;
  v4 = (__int64)a2;
  if ( !*((_BYTE *)a2 + 33) )
  {
    do
    {
      std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Erase(
        a1,
        *(_QWORD *)(v4 + 16));
      v4 = *(_QWORD *)v4;
      Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(v2 + 3);
      operator delete(v2);
      v2 = (__int64 *)v4;
    }
    while ( !*(_BYTE *)(v4 + 33) );
  }
}

```

## disassembly

```asm
0x180003c80  mov     [rsp+arg_0], rbx
0x180003c85  mov     [rsp+arg_8], rsi
0x180003c8a  push    rdi
0x180003c8b  sub     rsp, 20h
0x180003c8f  cmp     byte ptr [rdx+21h], 0
0x180003c93  mov     rbx, rdx
0x180003c96  mov     rsi, rcx
0x180003c99  mov     rdi, rdx
0x180003c9c  jz      short loc_180003CB0
0x180003c9e  mov     rbx, [rsp+28h+arg_0]
0x180003ca3  mov     rsi, [rsp+28h+arg_8]
0x180003ca8  add     rsp, 20h
0x180003cac  pop     rdi
0x180003cad  retn
0x180003cb0  mov     rdx, [rdi+10h]
0x180003cb4  mov     rcx, rsi
0x180003cb7  call    ?_Erase@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180003cbc  mov     rdi, [rdi]
0x180003cbf  lea     rcx, [rbx+18h]
0x180003cc3  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x180003cc8  mov     rcx, rbx
0x180003ccb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003cd1  cmp     byte ptr [rdi+21h], 0
0x180003cd5  mov     rbx, rdi
0x180003cd8  jnz     short loc_180003C9E
0x180003cda  jmp     short loc_180003CB0
```

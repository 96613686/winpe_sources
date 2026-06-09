# std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(std::_Tree_nod<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x180003ce4`
- end: `0x180003d3c`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@IV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@5@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@IV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@5@$00@std@@@2@@Z`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001f74`
- `0x180003ce4`

## callees

- `0x180001250`
- `0x180003ce4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003d1d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d1d`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rbx
  __int64 v4; // rdi

  v2 = a2;
  v4 = (__int64)a2;
  if ( !*((_BYTE *)a2 + 41) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(
        a1,
        *(_QWORD *)(v4 + 16));
      v4 = *(_QWORD *)v4;
      Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(v2 + 4);
      operator delete(v2);
      v2 = (__int64 *)v4;
    }
    while ( !*(_BYTE *)(v4 + 41) );
  }
}

```

## disassembly

```asm
0x180003ce4  mov     [rsp+arg_0], rbx
0x180003ce9  mov     [rsp+arg_8], rsi
0x180003cee  push    rdi
0x180003cef  sub     rsp, 20h
0x180003cf3  cmp     byte ptr [rdx+29h], 0
0x180003cf7  mov     rbx, rdx
0x180003cfa  mov     rsi, rcx
0x180003cfd  mov     rdi, rdx
0x180003d00  jnz     short loc_180003D2C
0x180003d02  mov     rdx, [rdi+10h]
0x180003d06  mov     rcx, rsi
0x180003d09  call    ?_Erase@?$_Tree@V?$_Tmap_traits@IV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@5@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@IV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@5@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(std::_Tree_nod<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180003d0e  mov     rdi, [rdi]
0x180003d11  lea     rcx, [rbx+20h]
0x180003d15  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x180003d1a  mov     rcx, rbx
0x180003d1d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003d23  cmp     byte ptr [rdi+29h], 0
0x180003d27  mov     rbx, rdi
0x180003d2a  jz      short loc_180003D02
0x180003d2c  mov     rbx, [rsp+28h+arg_0]
0x180003d31  mov     rsi, [rsp+28h+arg_8]
0x180003d36  add     rsp, 20h
0x180003d3a  pop     rdi
0x180003d3b  retn
```

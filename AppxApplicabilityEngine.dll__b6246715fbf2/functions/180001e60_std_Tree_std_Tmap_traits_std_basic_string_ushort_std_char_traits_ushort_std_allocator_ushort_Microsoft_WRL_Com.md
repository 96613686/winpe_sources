# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(std::_Tree_nod<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x180001e60`
- end: `0x180001eea`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z`
- size: `138`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001e0c`
- `0x180001e60`

## callees

- `0x180001e60`
- `0x180025010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001ec6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001ee2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001ec6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001ee2`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rbx
  __int64 *i; // rdi
  __int64 v5; // rcx

  v2 = a2;
  for ( i = a2; !*((_BYTE *)i + 73); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(
      a1,
      i[2]);
    i = (__int64 *)*i;
    v5 = v2[8];
    if ( v5 )
    {
      v2[8] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( (unsigned __int64)v2[6] >= 8 )
      operator delete((void *)v2[3]);
    v2[6] = 7;
    v2[5] = 0;
    *((_WORD *)v2 + 12) = 0;
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180001e60  push    rbx
0x180001e62  push    rbp
0x180001e63  push    rsi
0x180001e64  push    rdi
0x180001e65  sub     rsp, 38h
0x180001e69  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180001e72  mov     rbx, rdx
0x180001e75  mov     rsi, rcx
0x180001e78  mov     rdi, rdx
0x180001e7b  cmp     byte ptr [rdx+49h], 0
0x180001e7f  jnz     short loc_180001ED5
0x180001e81  xor     ebp, ebp
0x180001e83  mov     rdx, [rdi+10h]
0x180001e87  mov     rcx, rsi
0x180001e8a  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180001e8f  mov     rdi, [rdi]
0x180001e92  mov     rcx, [rbx+40h]
0x180001e96  test    rcx, rcx
0x180001e99  jz      short loc_180001EAC
0x180001e9b  mov     [rbx+40h], rbp
0x180001e9f  mov     rax, [rcx]
0x180001ea2  mov     rax, [rax+10h]
0x180001ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eab  nop
0x180001eac  cmp     qword ptr [rbx+30h], 8
0x180001eb1  jnb     short loc_180001EDE
0x180001eb3  mov     qword ptr [rbx+30h], 7
0x180001ebb  mov     [rbx+28h], rbp
0x180001ebf  mov     [rbx+18h], bp
0x180001ec3  mov     rcx, rbx
0x180001ec6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001ecc  mov     rbx, rdi
0x180001ecf  cmp     byte ptr [rdi+49h], 0
0x180001ed3  jz      short loc_180001E83
0x180001ed5  add     rsp, 38h
0x180001ed9  pop     rdi
0x180001eda  pop     rsi
0x180001edb  pop     rbp
0x180001edc  pop     rbx
0x180001edd  retn
0x180001ede  mov     rcx, [rbx+18h]
0x180001ee2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001ee8  jmp     short loc_180001EB3
```

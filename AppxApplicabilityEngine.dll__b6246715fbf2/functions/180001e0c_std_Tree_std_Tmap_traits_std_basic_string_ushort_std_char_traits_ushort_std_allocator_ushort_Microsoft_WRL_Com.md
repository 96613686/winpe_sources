# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::~_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>(void)

- ea: `0x180001e0c`
- end: `0x180001e5a`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800012dc`
- `0x180003b30`

## callees

- `0x180001e60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001e53`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>(
        __int64 a1)
{
  std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(
    a1,
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL));
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  **(_QWORD **)(a1 + 8) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 16) = 0;
  operator delete(*(void **)(a1 + 8));
}

```

## disassembly

```asm
0x180001e0c  push    rbx
0x180001e0e  sub     rsp, 30h
0x180001e12  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001e1b  mov     rbx, rcx
0x180001e1e  mov     rdx, [rcx+8]
0x180001e22  mov     rdx, [rdx+8]
0x180001e26  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180001e2b  mov     rax, [rbx+8]
0x180001e2f  mov     [rax+8], rax
0x180001e33  mov     rax, [rbx+8]
0x180001e37  mov     [rax], rax
0x180001e3a  mov     rax, [rbx+8]
0x180001e3e  mov     [rax+10h], rax
0x180001e42  mov     qword ptr [rbx+10h], 0
0x180001e4a  mov     rcx, [rbx+8]
0x180001e4e  add     rsp, 30h
0x180001e52  pop     rbx
0x180001e53  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```

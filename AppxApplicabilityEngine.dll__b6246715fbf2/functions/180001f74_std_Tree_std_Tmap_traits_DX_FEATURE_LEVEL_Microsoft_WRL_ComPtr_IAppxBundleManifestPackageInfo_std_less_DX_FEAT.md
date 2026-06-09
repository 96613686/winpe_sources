# std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::~_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>(void)

- ea: `0x180001f74`
- end: `0x180001fc2`
- name: `??1?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000130c`
- `0x180003b30`

## callees

- `0x180003ce4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001fbb`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::~_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>(
        __int64 a1)
{
  std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(
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
0x180001f74  push    rbx
0x180001f76  sub     rsp, 30h
0x180001f7a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001f83  mov     rbx, rcx
0x180001f86  mov     rdx, [rcx+8]
0x180001f8a  mov     rdx, [rdx+8]
0x180001f8e  call    ?_Erase@?$_Tree@V?$_Tmap_traits@IV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@5@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@IV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@5@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Erase(std::_Tree_nod<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180001f93  mov     rax, [rbx+8]
0x180001f97  mov     [rax+8], rax
0x180001f9b  mov     rax, [rbx+8]
0x180001f9f  mov     [rax], rax
0x180001fa2  mov     rax, [rbx+8]
0x180001fa6  mov     [rax+10h], rax
0x180001faa  mov     qword ptr [rbx+10h], 0
0x180001fb2  mov     rcx, [rbx+8]
0x180001fb6  add     rsp, 30h
0x180001fba  pop     rbx
0x180001fbb  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```

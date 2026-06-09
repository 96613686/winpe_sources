# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::clear(void)

- ea: `0x180003c30`
- end: `0x180003c6b`
- name: `?clear@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAXXZ`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003c00`
- `0x18000cef0`
- `0x1800228d3`

## callees

- `0x180003c80`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::clear(
        __int64 a1)
{
  __int64 result; // rax

  std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Erase(
    a1,
    *(__int64 **)(*(_QWORD *)(a1 + 8) + 8LL));
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  **(_QWORD **)(a1 + 8) = *(_QWORD *)(a1 + 8);
  result = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(result + 16) = result;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180003c30  push    rbx
0x180003c32  sub     rsp, 20h
0x180003c36  mov     rdx, [rcx+8]
0x180003c3a  mov     rbx, rcx
0x180003c3d  mov     rdx, [rdx+8]
0x180003c41  call    ?_Erase@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180003c46  mov     rax, [rbx+8]
0x180003c4a  mov     [rax+8], rax
0x180003c4e  mov     rax, [rbx+8]
0x180003c52  mov     [rax], rax
0x180003c55  mov     rax, [rbx+8]
0x180003c59  mov     [rax+10h], rax
0x180003c5d  mov     qword ptr [rbx+10h], 0
0x180003c65  add     rsp, 20h
0x180003c69  pop     rbx
0x180003c6a  retn
```

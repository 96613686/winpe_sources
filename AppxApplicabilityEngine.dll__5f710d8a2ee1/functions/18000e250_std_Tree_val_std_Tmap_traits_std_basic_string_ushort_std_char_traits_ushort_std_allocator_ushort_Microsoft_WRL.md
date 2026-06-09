# std::_Tree_val<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<ushort *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::pair<ushort *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)

- ea: `0x18000e250`
- end: `0x18000e2b9`
- name: `??$_Buynode@U?$pair@PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@1@$$QEAU?$pair@PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002230`

## callees

- `0x180004df8`
- `0x18000e2c0`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<unsigned short *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
        __int64 a1,
        const char *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _QWORD *result; // rax
  void *v7; // [rsp+40h] [rbp+8h]

  v4 = std::_Allocate<std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(
         a1,
         a2);
  v5 = v4;
  v7 = v4;
  *v4 = *(_QWORD *)(a1 + 8);
  v4[1] = *(_QWORD *)(a1 + 8);
  v4[2] = *(_QWORD *)(a1 + 8);
  *((_WORD *)v4 + 36) = 0;
  try
  {
    std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(
      (__int64)(v4 + 3),
      (__int64)a2);
    result = v5;
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
0x18000e250  push    rdi
0x18000e252  sub     rsp, 30h
0x18000e256  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000e25f  mov     [rsp+38h+arg_8], rbx
0x18000e264  mov     [rsp+38h+arg_10], rsi
0x18000e269  mov     rsi, rdx
0x18000e26c  mov     rbx, rcx
0x18000e26f  call    ??$_Allocate@U_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@@std@@YAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@0@_KPEAU120@@Z; std::_Allocate<std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(unsigned __int64,std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x18000e274  mov     rdi, rax
0x18000e277  mov     [rsp+38h+arg_0], rax
0x18000e27c  mov     r8, [rbx+8]
0x18000e280  mov     [rax], r8
0x18000e283  mov     r8, [rbx+8]
0x18000e287  mov     [rax+8], r8
0x18000e28b  mov     rcx, [rbx+8]
0x18000e28f  mov     [rax+10h], rcx
0x18000e293  mov     word ptr [rax+48h], 0
0x18000e299  lea     rcx, [rax+18h]
0x18000e29d  mov     rdx, rsi
0x18000e2a0  call    ??$?0PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@QEAA@$$QEAU?$pair@PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z; std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(std::pair<ushort *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)
0x18000e2a5  nop
0x18000e2a6  mov     rax, rdi
0x18000e2a9  mov     rbx, [rsp+38h+arg_8]
0x18000e2ae  mov     rsi, [rsp+38h+arg_10]
0x18000e2b3  add     rsp, 30h
0x18000e2b7  pop     rdi
0x18000e2b8  retn
```

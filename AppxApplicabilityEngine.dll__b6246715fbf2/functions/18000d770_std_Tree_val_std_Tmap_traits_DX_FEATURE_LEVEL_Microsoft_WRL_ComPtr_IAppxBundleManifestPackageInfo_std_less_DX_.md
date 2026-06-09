# std::_Tree_val<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)

- ea: `0x18000d770`
- end: `0x18000d7e3`
- name: `??$_Buynode@U?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@1@$$QEAU?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z`
- size: `115`
- prototype: `_QWORD *__fastcall(__int64, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002230`
- `0x180016888`

## callees

- `0x18000d770`
- `0x18000d7ec`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
        __int64 a1,
        const char *a2)
{
  _QWORD *v4; // r9
  _QWORD *v5; // rcx

  v4 = std::_Allocate<std::_Tree_nod<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(
         a1,
         a2);
  *v4 = *(_QWORD *)(a1 + 8);
  v4[1] = *(_QWORD *)(a1 + 8);
  v4[2] = *(_QWORD *)(a1 + 8);
  *((_WORD *)v4 + 20) = 0;
  v5 = a2 + 8;
  *((_DWORD *)v4 + 6) = *(_DWORD *)a2;
  v4[4] = 0;
  if ( v4 + 4 != (_QWORD *)(a2 + 8) )
  {
    v4[4] = *v5;
    *v5 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18000d770  push    rdi
0x18000d772  sub     rsp, 30h
0x18000d776  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000d77f  mov     [rsp+38h+arg_8], rbx
0x18000d784  mov     rdi, rdx
0x18000d787  mov     rbx, rcx
0x18000d78a  call    ??$_Allocate@U_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@std@@YAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@0@_KPEAU120@@Z; std::_Allocate<std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(unsigned __int64,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x18000d78f  mov     r9, rax
0x18000d792  mov     [rsp+38h+arg_0], rax
0x18000d797  mov     r8, [rbx+8]
0x18000d79b  mov     [rax], r8
0x18000d79e  mov     r8, [rbx+8]
0x18000d7a2  mov     [rax+8], r8
0x18000d7a6  mov     rcx, [rbx+8]
0x18000d7aa  mov     [rax+10h], rcx
0x18000d7ae  xor     r8d, r8d
0x18000d7b1  mov     [rax+28h], r8w
0x18000d7b6  lea     rcx, [rdi+8]
0x18000d7ba  mov     eax, [rdi]
0x18000d7bc  mov     [r9+18h], eax
0x18000d7c0  lea     rdx, [r9+20h]
0x18000d7c4  mov     [rdx], r8
0x18000d7c7  cmp     rdx, rcx
0x18000d7ca  jz      short loc_18000D7D5
0x18000d7cc  mov     rax, [rcx]
0x18000d7cf  mov     [rdx], rax
0x18000d7d2  mov     [rcx], r8
0x18000d7d5  mov     rax, r9
0x18000d7d8  mov     rbx, [rsp+38h+arg_8]
0x18000d7dd  add     rsp, 30h
0x18000d7e1  pop     rdi
0x18000d7e2  retn
```

# std::multimap<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>>::insert<std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)

- ea: `0x180016888`
- end: `0x180016902`
- name: `??$insert@U?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@?$multimap@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@1@$$QEAU?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002230`

## callees

- `0x180003d44`
- `0x18000d770`
- `0x180016888`

## pseudocode

```c
__int64 **__fastcall std::multimap<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::insert<std::pair<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
        __int64 a1,
        __int64 **a2,
        const char *a3)
{
  __int64 *v5; // rax
  __int64 v6; // r10
  __int64 *v7; // r11
  __int64 v8; // r8
  int v9; // r9d
  bool v10; // al
  __int64 *v11; // rcx
  __int64 **result; // rax
  __int64 *v13; // [rsp+40h] [rbp+8h] BYREF

  v5 = std::_Tree_val<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
         a1,
         a3);
  v6 = *(_QWORD *)(a1 + 8);
  v7 = v5;
  v8 = *(_QWORD *)(v6 + 8);
  if ( *(_BYTE *)(v8 + 41) )
  {
    v10 = 1;
  }
  else
  {
    v9 = *((_DWORD *)v5 + 6);
    do
    {
      v6 = v8;
      v10 = v9 < *(_DWORD *)(v8 + 24);
      if ( v9 >= *(_DWORD *)(v8 + 24) )
        v8 = *(_QWORD *)(v8 + 16);
      else
        v8 = *(_QWORD *)v8;
    }
    while ( !*(_BYTE *)(v8 + 41) );
  }
  LOBYTE(v8) = v10;
  v11 = *std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(
           a1,
           &v13,
           v8,
           (__int64 **)v6,
           v7);
  result = a2;
  *a2 = v11;
  return result;
}

```

## disassembly

```asm
0x180016888  mov     [rsp+arg_8], rbx
0x18001688d  push    rdi
0x18001688e  sub     rsp, 30h
0x180016892  mov     rdi, rdx
0x180016895  mov     rbx, rcx
0x180016898  mov     rdx, r8
0x18001689b  call    ??$_Buynode@U?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@1@$$QEAU?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z; std::_Tree_val<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)
0x1800168a0  mov     r10, [rbx+8]
0x1800168a4  mov     r11, rax
0x1800168a7  mov     r8, [r10+8]
0x1800168ab  cmp     byte ptr [r8+29h], 0
0x1800168b0  jnz     short loc_1800168D4
0x1800168b2  mov     r9d, [rax+18h]
0x1800168b6  cmp     r9d, [r8+18h]
0x1800168ba  mov     r10, r8
0x1800168bd  setl    al
0x1800168c0  jge     short loc_1800168C7
0x1800168c2  mov     r8, [r8]
0x1800168c5  jmp     short loc_1800168CB
0x1800168c7  mov     r8, [r8+10h]
0x1800168cb  cmp     byte ptr [r8+29h], 0
0x1800168d0  jz      short loc_1800168B6
0x1800168d2  jmp     short loc_1800168D6
0x1800168d4  mov     al, 1
0x1800168d6  mov     r9, r10
0x1800168d9  mov     [rsp+38h+var_18], r11
0x1800168de  mov     r8b, al
0x1800168e1  lea     rdx, [rsp+38h+arg_0]
0x1800168e6  mov     rcx, rbx
0x1800168e9  call    ?_Insert@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@1@Z; std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x1800168ee  mov     rbx, [rsp+38h+arg_8]
0x1800168f3  mov     rcx, [rax]
0x1800168f6  mov     rax, rdi
0x1800168f9  mov     [rdi], rcx
0x1800168fc  add     rsp, 30h
0x180016900  pop     rdi
0x180016901  retn
```

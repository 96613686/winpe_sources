# ResourcePackResolver::ResourcePackResolver(IAppxBundleManifestReader *,ApplicabilityContext *)

- ea: `0x180004304`
- end: `0x18000448e`
- name: `??0ResourcePackResolver@@QEAA@PEAUIAppxBundleManifestReader@@PEAVApplicabilityContext@@@Z`
- size: `394`
- prototype: `ResourcePackResolver *__fastcall(ResourcePackResolver *__hidden this, struct IAppxBundleManifestReader *, struct ApplicabilityContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cef0`

## callees

- `0x180004304`
- `0x180004494`
- `0x18000abd0`
- `0x18000ad10`
- `0x18000d7ec`
- `0x18000e2c0`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
ResourcePackResolver *__fastcall ResourcePackResolver::ResourcePackResolver(
        ResourcePackResolver *this,
        struct IAppxBundleManifestReader *a2,
        struct ApplicabilityContext *a3)
{
  _QWORD *v6; // rax
  __int64 i; // rcx
  _QWORD *v8; // rax
  __int64 j; // rcx
  _QWORD *v10; // rax
  __int64 k; // rcx

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 3) = 0;
  v6 = (_QWORD *)std::_Allocate<std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(this);
  *((_QWORD *)this + 2) = v6;
  *v6 = v6;
  *(_QWORD *)(*((_QWORD *)this + 2) + 8LL) = *((_QWORD *)this + 2);
  *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) = *((_QWORD *)this + 2);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(i + *((_QWORD *)this + 2) + 72) = 1;
  *((_QWORD *)this + 7) = 0;
  v8 = (_QWORD *)std::_Allocate<std::_Tree_nod<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(2);
  *((_QWORD *)this + 6) = v8;
  *v8 = v8;
  *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = *((_QWORD *)this + 6);
  *(_QWORD *)(*((_QWORD *)this + 6) + 16LL) = *((_QWORD *)this + 6);
  for ( j = 0; j != 2; ++j )
    *(_BYTE *)(*((_QWORD *)this + 6) + j + 40) = 1;
  *((_QWORD *)this + 11) = 0;
  v10 = (_QWORD *)std::_Allocate<std::_Tree_nod<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(2);
  *((_QWORD *)this + 10) = v10;
  *v10 = v10;
  *(_QWORD *)(*((_QWORD *)this + 10) + 8LL) = *((_QWORD *)this + 10);
  *(_QWORD *)(*((_QWORD *)this + 10) + 16LL) = *((_QWORD *)this + 10);
  for ( k = 0; k != 2; ++k )
    *(_BYTE *)(k + *((_QWORD *)this + 10) + 40) = 1;
  std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>((char *)this + 104);
  std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>((char *)this + 136);
  std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>((char *)this + 168);
  std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>((char *)this + 200);
  std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>((char *)this + 232);
  std::set<std::wstring>::set<std::wstring>((char *)this + 264);
  std::set<unsigned int>::set<unsigned int>((char *)this + 296);
  std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>((char *)this + 328);
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 49) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IAppxBundleManifestReader *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 50) = a3;
  return this;
}

```

## disassembly

```asm
0x180004304  mov     [rsp+arg_0], rcx
0x180004309  push    rbp
0x18000430a  push    rsi
0x18000430b  push    rdi
0x18000430c  sub     rsp, 30h
0x180004310  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180004319  mov     [rsp+48h+arg_10], rbx
0x18000431e  mov     rbp, r8
0x180004321  mov     rsi, rdx
0x180004324  mov     rbx, rcx
0x180004327  mov     qword ptr [rcx], 0
0x18000432e  mov     qword ptr [rcx+18h], 0
0x180004336  call    ??$_Allocate@U_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@@std@@YAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@0@_KPEAU120@@Z; std::_Allocate<std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(unsigned __int64,std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x18000433b  mov     [rbx+10h], rax
0x18000433f  mov     [rax], rax
0x180004342  mov     rax, [rbx+10h]
0x180004346  mov     [rax+8], rax
0x18000434a  mov     rax, [rbx+10h]
0x18000434e  mov     [rax+10h], rax
0x180004352  xor     ecx, ecx
0x180004354  mov     rax, [rbx+10h]
0x180004358  mov     byte ptr [rcx+rax+48h], 1
0x18000435d  inc     rcx
0x180004360  cmp     rcx, 2
0x180004364  jnz     short loc_180004354
0x180004366  mov     qword ptr [rbx+38h], 0
0x18000436e  call    ??$_Allocate@U_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@std@@YAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@0@_KPEAU120@@Z; std::_Allocate<std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(unsigned __int64,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180004373  mov     [rbx+30h], rax
0x180004377  mov     [rax], rax
0x18000437a  mov     rax, [rbx+30h]
0x18000437e  mov     [rax+8], rax
0x180004382  mov     rax, [rbx+30h]
0x180004386  mov     [rax+10h], rax
0x18000438a  xor     ecx, ecx
0x18000438c  mov     rax, [rbx+30h]
0x180004390  mov     byte ptr [rax+rcx+28h], 1
0x180004395  inc     rcx
0x180004398  cmp     rcx, 2
0x18000439c  jnz     short loc_18000438C
0x18000439e  mov     qword ptr [rbx+58h], 0
0x1800043a6  call    ??$_Allocate@U_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@std@@YAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@0@_KPEAU120@@Z; std::_Allocate<std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(unsigned __int64,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x1800043ab  mov     [rbx+50h], rax
0x1800043af  mov     [rax], rax
0x1800043b2  mov     rax, [rbx+50h]
0x1800043b6  mov     [rax+8], rax
0x1800043ba  mov     rax, [rbx+50h]
0x1800043be  mov     [rax+10h], rax
0x1800043c2  xor     ecx, ecx
0x1800043c4  mov     rax, [rbx+50h]
0x1800043c8  mov     byte ptr [rcx+rax+28h], 1
0x1800043cd  inc     rcx
0x1800043d0  cmp     rcx, 2
0x1800043d4  jnz     short loc_1800043C4
0x1800043d6  lea     rcx, [rbx+68h]
0x1800043da  call    ??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ; std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)
0x1800043df  nop
0x1800043e0  lea     rcx, [rbx+88h]
0x1800043e7  call    ??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ; std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)
0x1800043ec  nop
0x1800043ed  lea     rcx, [rbx+0A8h]
0x1800043f4  call    ??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ; std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)
0x1800043f9  nop
0x1800043fa  lea     rcx, [rbx+0C8h]
0x180004401  call    ??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ; std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)
0x180004406  nop
0x180004407  lea     rcx, [rbx+0E8h]
0x18000440e  call    ??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ; std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)
0x180004413  nop
0x180004414  lea     rcx, [rbx+108h]
0x18000441b  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180004420  nop
0x180004421  lea     rcx, [rbx+128h]
0x180004428  call    ??0?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@QEAA@XZ; std::set<uint>::set<uint>(void)
0x18000442d  nop
0x18000442e  lea     rcx, [rbx+148h]
0x180004435  call    ??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ; std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)
0x18000443a  mov     qword ptr [rbx+168h], 0
0x180004445  mov     qword ptr [rbx+170h], 0
0x180004450  mov     qword ptr [rbx+178h], 0
0x18000445b  mov     [rbx+188h], rsi
0x180004462  test    rsi, rsi
0x180004465  jz      short loc_180004477
0x180004467  mov     rax, [rsi]
0x18000446a  mov     rcx, rsi
0x18000446d  mov     rax, [rax+8]
0x180004471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004476  nop
0x180004477  mov     [rbx+190h], rbp
0x18000447e  mov     rax, rbx
0x180004481  mov     rbx, [rsp+48h+arg_10]
0x180004486  add     rsp, 30h
0x18000448a  pop     rdi
0x18000448b  pop     rsi
0x18000448c  pop     rbp
0x18000448d  retn
```

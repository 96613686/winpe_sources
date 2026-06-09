# OptionalityFeaturesProvider::UninstallFeatures(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x180026f3c`
- end: `0x180027191`
- name: `?UninstallFeatures@OptionalityFeaturesProvider@@YAJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026020`

## callees

- `0x180003520`
- `0x1800040f4`
- `0x180004118`
- `0x1800092a4`
- `0x180012394`
- `0x18001855c`
- `0x18002621c`
- `0x1800266a8`
- `0x180026778`
- `0x1800268d4`
- `0x180026f3c`

## import_xrefs

- `ServicingUAPI!UninstallFeatures` at `0x180027107`
- `ServicingUAPI!UninstallFeatures` at `0x180027107`

## string_xrefs

- `0x18002711d`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagefeaturesprovider.cpp`

## pseudocode

```c
__int64 __fastcall OptionalityFeaturesProvider::UninstallFeatures(_QWORD *a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // rdi
  __int64 v4; // rax
  int v5; // ecx
  int v6; // eax
  unsigned int v7; // ebx
  __int128 v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+30h] [rbp-D0h]
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD Buf2[3]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+70h] [rbp-90h]
  _OWORD v14[10]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v15; // [rsp+118h] [rbp+18h]
  __int128 v16; // [rsp+128h] [rbp+28h]
  __int64 v17; // [rsp+138h] [rbp+38h]
  _QWORD v18[2]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v19[3]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD Buf1[3]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v21; // [rsp+198h] [rbp+98h]
  _OWORD v22[10]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v23; // [rsp+240h] [rbp+140h]
  __int128 v24; // [rsp+250h] [rbp+150h]
  __int64 v25; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  memset_0(v14, 0, 0xC8u);
  *(_QWORD *)&v14[0] = L"LanguageFeaturesOnDemand";
  LODWORD(v15) = 0;
  v22[0] = v14[0];
  v22[1] = v14[1];
  v22[2] = v14[2];
  v22[3] = v14[3];
  v22[4] = v14[4];
  v22[5] = v14[5];
  v22[6] = v14[6];
  v22[7] = v14[7];
  v22[8] = v14[8];
  v22[9] = v14[9];
  v23 = v15;
  v24 = v16;
  v25 = v17;
  LODWORD(v23) = 4;
  v9 = 0;
  v10 = 0;
  OptionalityFeaturesProvider::GetFeatureDescriptors(v19, a1);
  v2 = (__int64 *)v19[0];
  v3 = (__int64 *)v19[1];
  while ( v2 != v3 )
  {
    v4 = *v2;
    v11 = *v2;
    if ( *((_QWORD *)&v9 + 1) == v10 )
    {
      std::vector<FeatureDescriptor *>::_Emplace_reallocate<FeatureDescriptor *>(&v9, *((_QWORD *)&v9 + 1), &v11);
    }
    else
    {
      **((_QWORD **)&v9 + 1) = v4;
      *((_QWORD *)&v9 + 1) += 8LL;
    }
    ++v2;
  }
  v18[0] = v9;
  v18[1] = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a1[1] - *a1) >> 6);
  memset(Buf1, 0, sizeof(Buf1));
  v21 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  v13 = 0;
  if ( memcmp_0(Buf1, Buf2, 0x38u) )
    INTERNAL_ERROR_ACTION(v5);
  v6 = UninstallFeatures(v22, 1, v18, Buf1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    Windows::AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&void CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>::~AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&void CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>(Buf1);
    std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(v19);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(&v9);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagefeaturesprovider.cpp",
      (const char *)(unsigned int)v6,
      v9);
    Windows::AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&void CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>::~AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&void CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>(Buf1);
    std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(v19);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(&v9);
    return v7;
  }
}

```

## disassembly

```asm
0x180026f3c  push    rbp
0x180026f3e  push    rbx
0x180026f3f  push    rsi
0x180026f40  push    rdi
0x180026f41  lea     rbp, [rsp-188h]
0x180026f49  sub     rsp, 288h
0x180026f50  mov     rax, cs:__security_cookie
0x180026f57  xor     rax, rsp
0x180026f5a  mov     [rbp+1A0h+var_30], rax
0x180026f61  mov     rsi, rcx
0x180026f64  xor     edx, edx; Val
0x180026f66  mov     r8d, 0C8h; Size
0x180026f6c  lea     rcx, [rsp+2A0h+var_228]; void *
0x180026f71  call    memset_0
0x180026f76  lea     rax, aLanguagefeatur; "LanguageFeaturesOnDemand"
0x180026f7d  mov     qword ptr [rsp+2A0h+var_228], rax
0x180026f82  mov     dword ptr [rbp+1A0h+var_188], 0
0x180026f89  movups  xmm0, [rsp+2A0h+var_228]
0x180026f8e  movups  [rbp+1A0h+var_100], xmm0
0x180026f95  movups  xmm1, [rbp+1A0h+var_218]
0x180026f99  movups  [rbp+1A0h+var_F0], xmm1
0x180026fa0  movups  xmm0, [rbp+1A0h+var_208]
0x180026fa4  movups  [rbp+1A0h+var_E0], xmm0
0x180026fab  movups  xmm1, [rbp+1A0h+var_1F8]
0x180026faf  movups  [rbp+1A0h+var_D0], xmm1
0x180026fb6  movups  xmm0, [rbp+1A0h+var_1E8]
0x180026fba  movups  [rbp+1A0h+var_C0], xmm0
0x180026fc1  movups  xmm1, [rbp+1A0h+var_1D8]
0x180026fc5  movups  [rbp+1A0h+var_B0], xmm1
0x180026fcc  movups  xmm0, [rbp+1A0h+var_1C8]
0x180026fd0  movups  [rbp+1A0h+var_A0], xmm0
0x180026fd7  movups  xmm1, [rbp+1A0h+var_1B8]
0x180026fdb  movups  [rbp+1A0h+var_90], xmm1
0x180026fe2  movups  xmm0, [rbp+1A0h+var_1A8]
0x180026fe6  movups  [rbp+1A0h+var_80], xmm0
0x180026fed  movups  xmm1, [rbp+1A0h+var_198]
0x180026ff1  movups  [rbp+1A0h+var_70], xmm1
0x180026ff8  movups  xmm0, [rbp+1A0h+var_188]
0x180026ffc  movups  [rbp+1A0h+var_60], xmm0
0x180027003  movups  xmm1, [rbp+1A0h+var_178]
0x180027007  movups  [rbp+1A0h+var_50], xmm1
0x18002700e  mov     rax, [rbp+1A0h+var_168]
0x180027012  mov     [rbp+1A0h+var_40], rax
0x180027019  mov     dword ptr [rbp+1A0h+var_60], 4
0x180027023  xorps   xmm0, xmm0
0x180027026  movdqu  [rsp+2A0h+var_280], xmm0
0x18002702c  mov     [rsp+2A0h+var_270], 0
0x180027035  mov     rdx, rsi
0x180027038  lea     rcx, [rbp+1A0h+var_150]
0x18002703c  call    ?GetFeatureDescriptors@OptionalityFeaturesProvider@@YA?AV?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; OptionalityFeaturesProvider::GetFeatureDescriptors(std::vector<CbsLanguageFeature> const &)
0x180027041  nop
0x180027042  mov     rbx, [rbp+1A0h+var_150]
0x180027046  mov     rdi, [rbp+1A0h+var_148]
0x18002704a  jmp     short loc_18002707E
0x18002704c  mov     rax, [rbx]
0x18002704f  mov     [rsp+2A0h+var_268], rax
0x180027054  mov     rdx, qword ptr [rsp+2A0h+var_280+8]
0x180027059  cmp     rdx, [rsp+2A0h+var_270]
0x18002705e  jz      short loc_18002706B
0x180027060  mov     [rdx], rax
0x180027063  add     qword ptr [rsp+2A0h+var_280+8], 8
0x180027069  jmp     short loc_18002707A
0x18002706b  lea     r8, [rsp+2A0h+var_268]
0x180027070  lea     rcx, [rsp+2A0h+var_280]
0x180027075  call    ??$_Emplace_reallocate@PEAUFeatureDescriptor@@@?$vector@PEAUFeatureDescriptor@@V?$allocator@PEAUFeatureDescriptor@@@std@@@std@@AEAAPEAPEAUFeatureDescriptor@@QEAPEAU2@$$QEAPEAU2@@Z; std::vector<FeatureDescriptor *>::_Emplace_reallocate<FeatureDescriptor *>(FeatureDescriptor * * const,FeatureDescriptor * &&)
0x18002707a  add     rbx, 8
0x18002707e  cmp     rbx, rdi
0x180027081  jnz     short loc_18002704C
0x180027083  mov     rax, qword ptr [rsp+2A0h+var_280]
0x180027088  mov     [rbp+1A0h+var_160], rax
0x18002708c  mov     rax, [rsi+8]
0x180027090  sub     rax, [rsi]
0x180027093  sar     rax, 6
0x180027097  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800270a1  imul    rax, rcx
0x1800270a5  mov     [rbp+1A0h+var_158], rax
0x1800270a9  xorps   xmm0, xmm0
0x1800270ac  xor     eax, eax
0x1800270ae  movups  [rbp+1A0h+Buf1], xmm0
0x1800270b2  movups  [rbp+1A0h+var_128], xmm0
0x1800270b6  movups  [rbp+1A0h+var_118], xmm0
0x1800270bd  mov     [rbp+1A0h+var_108], rax
0x1800270c4  xorps   xmm1, xmm1
0x1800270c7  movups  [rsp+2A0h+Buf2], xmm1
0x1800270cc  movups  [rsp+2A0h+var_250], xmm1
0x1800270d1  movups  [rsp+2A0h+var_240], xmm1
0x1800270d6  mov     [rsp+2A0h+var_230], rax
0x1800270db  lea     r8d, [rax+38h]; Size
0x1800270df  lea     rdx, [rsp+2A0h+Buf2]; Buf2
0x1800270e4  lea     rcx, [rbp+1A0h+Buf1]; Buf1
0x1800270e8  call    memcmp_0
0x1800270ed  test    eax, eax
0x1800270ef  jnz     loc_18002718B
0x1800270f5  lea     r9, [rbp+1A0h+Buf1]
0x1800270f9  lea     r8, [rbp+1A0h+var_160]
0x1800270fd  lea     edx, [rax+1]
0x180027100  lea     rcx, [rbp+1A0h+var_100]
0x180027107  call    cs:__imp_UninstallFeatures
0x18002710d  mov     ebx, eax
0x18002710f  test    eax, eax
0x180027111  jns     short loc_180027169
0x180027113  mov     rcx, [rbp+1A8h]; this
0x18002711a  mov     r9d, eax; char *
0x18002711d  lea     r8, aOnecoreShellCp_3; "onecore\\shell\\cpls\\internationalsett"...
0x180027124  mov     edx, 0AAh; void *
0x180027129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002712e  lea     rcx, [rbp+1A0h+Buf1]
0x180027132  call    ??1?$AutoGenericHandleBase@UUninstallFeaturesResult@@$03V?$AutoGenericHandle@UUninstallFeaturesResult@@$03$1?CloseWithFreeUninstallFeaturesResult@@YAXU1@@Z@Windows@@@Windows@@QEAA@XZ; Windows::AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>::~AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>(void)
0x180027137  nop
0x180027138  lea     rcx, [rbp+1A0h+var_150]
0x18002713c  call    ??1?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(void)
0x180027141  nop
0x180027142  lea     rcx, [rsp+2A0h+var_280]
0x180027147  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(void)
0x18002714c  mov     eax, ebx
0x18002714e  mov     rcx, [rbp+1A0h+var_30]
0x180027155  xor     rcx, rsp; StackCookie
0x180027158  call    __security_check_cookie
0x18002715d  add     rsp, 288h
0x180027164  pop     rdi
0x180027165  pop     rsi
0x180027166  pop     rbx
0x180027167  pop     rbp
0x180027168  retn
0x180027169  lea     rcx, [rbp+1A0h+Buf1]
0x18002716d  call    ??1?$AutoGenericHandleBase@UUninstallFeaturesResult@@$03V?$AutoGenericHandle@UUninstallFeaturesResult@@$03$1?CloseWithFreeUninstallFeaturesResult@@YAXU1@@Z@Windows@@@Windows@@QEAA@XZ; Windows::AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>::~AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>(void)
0x180027172  nop
0x180027173  lea     rcx, [rbp+1A0h+var_150]
0x180027177  call    ??1?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(void)
0x18002717c  nop
0x18002717d  lea     rcx, [rsp+2A0h+var_280]
0x180027182  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(void)
0x180027187  xor     eax, eax
0x180027189  jmp     short loc_18002714E
0x18002718b  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

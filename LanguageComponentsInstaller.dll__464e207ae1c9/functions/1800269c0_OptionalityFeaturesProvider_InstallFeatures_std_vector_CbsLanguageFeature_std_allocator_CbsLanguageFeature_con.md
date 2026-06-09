# OptionalityFeaturesProvider::InstallFeatures(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x1800269c0`
- end: `0x180026c25`
- name: `?InstallFeatures@OptionalityFeaturesProvider@@YAJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025d20`

## callees

- `0x180003520`
- `0x1800040f4`
- `0x180004118`
- `0x1800092a4`
- `0x180012394`
- `0x18001855c`
- `0x18002621c`
- `0x180026600`
- `0x180026778`
- `0x1800268d4`
- `0x1800269c0`

## import_xrefs

- `ServicingUAPI!InstallFeatures` at `0x180026b9b`
- `ServicingUAPI!InstallFeatures` at `0x180026b9b`

## string_xrefs

- `0x180026bb1`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagefeaturesprovider.cpp`

## pseudocode

```c
__int64 __fastcall OptionalityFeaturesProvider::InstallFeatures(_QWORD *a1)
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
  _OWORD Buf2[4]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v13[10]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v14; // [rsp+120h] [rbp+20h]
  __int128 v15; // [rsp+130h] [rbp+30h]
  __int64 v16; // [rsp+140h] [rbp+40h]
  _QWORD v17[2]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v18[3]; // [rsp+158h] [rbp+58h] BYREF
  _OWORD Buf1[4]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v20[12]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v21; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  memset_0(v13, 0, 0xC8u);
  *(_QWORD *)&v13[0] = L"LanguageFeaturesOnDemand";
  LODWORD(v14) = 0;
  v20[0] = v13[0];
  v20[1] = v13[1];
  v20[2] = v13[2];
  v20[3] = v13[3];
  v20[4] = v13[4];
  v20[5] = v13[5];
  v20[6] = v13[6];
  v20[7] = v13[7];
  v20[8] = v13[8];
  v20[9] = v13[9];
  v20[10] = v14;
  v20[11] = v15;
  v21 = v16;
  v9 = 0;
  v10 = 0;
  OptionalityFeaturesProvider::GetFeatureDescriptors(v18, a1);
  v2 = (__int64 *)v18[0];
  v3 = (__int64 *)v18[1];
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
  v17[0] = v9;
  v17[1] = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a1[1] - *a1) >> 6);
  memset_0(Buf2, 0, sizeof(Buf2));
  Buf1[0] = Buf2[0];
  Buf1[1] = Buf2[1];
  Buf1[2] = Buf2[2];
  Buf1[3] = Buf2[3];
  memset_0(Buf2, 0, sizeof(Buf2));
  if ( memcmp_0(Buf1, Buf2, 0x40u) )
    INTERNAL_ERROR_ACTION(v5);
  v6 = InstallFeatures(v20, 1, v17, Buf1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    Windows::AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&void CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>::~AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&void CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>(Buf1);
    std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(v18);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(&v9);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagefeaturesprovider.cpp",
      (const char *)(unsigned int)v6,
      v9);
    Windows::AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&void CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>::~AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&void CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>(Buf1);
    std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(v18);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(&v9);
    return v7;
  }
}

```

## disassembly

```asm
0x1800269c0  push    rbp
0x1800269c2  push    rbx
0x1800269c3  push    rsi
0x1800269c4  push    rdi
0x1800269c5  lea     rbp, [rsp-198h]
0x1800269cd  sub     rsp, 298h
0x1800269d4  mov     rax, cs:__security_cookie
0x1800269db  xor     rax, rsp
0x1800269de  mov     [rbp+1B0h+var_30], rax
0x1800269e5  mov     rsi, rcx
0x1800269e8  xor     edx, edx; Val
0x1800269ea  mov     r8d, 0C8h; Size
0x1800269f0  lea     rcx, [rbp+1B0h+var_230]; void *
0x1800269f4  call    memset_0
0x1800269f9  lea     rax, aLanguagefeatur; "LanguageFeaturesOnDemand"
0x180026a00  mov     qword ptr [rbp+1B0h+var_230], rax
0x180026a04  mov     dword ptr [rbp+1B0h+var_190], 0
0x180026a0b  movups  xmm0, [rbp+1B0h+var_230]
0x180026a0f  movups  [rbp+1B0h+var_100], xmm0
0x180026a16  movups  xmm1, [rbp+1B0h+var_220]
0x180026a1a  movups  [rbp+1B0h+var_F0], xmm1
0x180026a21  movups  xmm0, [rbp+1B0h+var_210]
0x180026a25  movups  [rbp+1B0h+var_E0], xmm0
0x180026a2c  movups  xmm1, [rbp+1B0h+var_200]
0x180026a30  movups  [rbp+1B0h+var_D0], xmm1
0x180026a37  movups  xmm0, [rbp+1B0h+var_1F0]
0x180026a3b  movups  [rbp+1B0h+var_C0], xmm0
0x180026a42  movups  xmm1, [rbp+1B0h+var_1E0]
0x180026a46  movups  [rbp+1B0h+var_B0], xmm1
0x180026a4d  movups  xmm0, [rbp+1B0h+var_1D0]
0x180026a51  movups  [rbp+1B0h+var_A0], xmm0
0x180026a58  movups  xmm1, [rbp+1B0h+var_1C0]
0x180026a5c  movups  [rbp+1B0h+var_90], xmm1
0x180026a63  movups  xmm0, [rbp+1B0h+var_1B0]
0x180026a67  movups  [rbp+1B0h+var_80], xmm0
0x180026a6e  movups  xmm1, [rbp+1B0h+var_1A0]
0x180026a72  movups  [rbp+1B0h+var_70], xmm1
0x180026a79  movups  xmm0, [rbp+1B0h+var_190]
0x180026a7d  movups  [rbp+1B0h+var_60], xmm0
0x180026a84  movups  xmm1, [rbp+1B0h+var_180]
0x180026a88  movups  [rbp+1B0h+var_50], xmm1
0x180026a8f  mov     rax, [rbp+1B0h+var_170]
0x180026a93  mov     [rbp+1B0h+var_40], rax
0x180026a9a  xorps   xmm0, xmm0
0x180026a9d  movdqu  [rsp+2B0h+var_290], xmm0
0x180026aa3  mov     [rsp+2B0h+var_280], 0
0x180026aac  mov     rdx, rsi
0x180026aaf  lea     rcx, [rbp+1B0h+var_158]
0x180026ab3  call    ?GetFeatureDescriptors@OptionalityFeaturesProvider@@YA?AV?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; OptionalityFeaturesProvider::GetFeatureDescriptors(std::vector<CbsLanguageFeature> const &)
0x180026ab8  nop
0x180026ab9  mov     rbx, [rbp+1B0h+var_158]
0x180026abd  mov     rdi, [rbp+1B0h+var_150]
0x180026ac1  jmp     short loc_180026AF5
0x180026ac3  mov     rax, [rbx]
0x180026ac6  mov     [rsp+2B0h+var_278], rax
0x180026acb  mov     rdx, qword ptr [rsp+2B0h+var_290+8]
0x180026ad0  cmp     rdx, [rsp+2B0h+var_280]
0x180026ad5  jz      short loc_180026AE2
0x180026ad7  mov     [rdx], rax
0x180026ada  add     qword ptr [rsp+2B0h+var_290+8], 8
0x180026ae0  jmp     short loc_180026AF1
0x180026ae2  lea     r8, [rsp+2B0h+var_278]
0x180026ae7  lea     rcx, [rsp+2B0h+var_290]
0x180026aec  call    ??$_Emplace_reallocate@PEAUFeatureDescriptor@@@?$vector@PEAUFeatureDescriptor@@V?$allocator@PEAUFeatureDescriptor@@@std@@@std@@AEAAPEAPEAUFeatureDescriptor@@QEAPEAU2@$$QEAPEAU2@@Z; std::vector<FeatureDescriptor *>::_Emplace_reallocate<FeatureDescriptor *>(FeatureDescriptor * * const,FeatureDescriptor * &&)
0x180026af1  add     rbx, 8
0x180026af5  cmp     rbx, rdi
0x180026af8  jnz     short loc_180026AC3
0x180026afa  mov     rax, qword ptr [rsp+2B0h+var_290]
0x180026aff  mov     [rbp+1B0h+var_168], rax
0x180026b03  mov     rax, [rsi+8]
0x180026b07  sub     rax, [rsi]
0x180026b0a  sar     rax, 6
0x180026b0e  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180026b18  imul    rax, rcx
0x180026b1c  mov     [rbp+1B0h+var_160], rax
0x180026b20  mov     ebx, 40h ; '@'
0x180026b25  mov     r8d, ebx; Size
0x180026b28  xor     edx, edx; Val
0x180026b2a  lea     rcx, [rsp+2B0h+Buf2]; void *
0x180026b2f  call    memset_0
0x180026b34  movups  xmm0, [rsp+2B0h+Buf2]
0x180026b39  movaps  [rbp+1B0h+Buf1], xmm0
0x180026b3d  movups  xmm1, [rsp+2B0h+var_260]
0x180026b42  movaps  [rbp+1B0h+var_130], xmm1
0x180026b49  movups  xmm0, [rsp+2B0h+var_250]
0x180026b4e  movaps  [rbp+1B0h+var_120], xmm0
0x180026b55  movups  xmm1, [rsp+2B0h+var_240]
0x180026b5a  movaps  [rbp+1B0h+var_110], xmm1
0x180026b61  mov     r8d, ebx; Size
0x180026b64  xor     edx, edx; Val
0x180026b66  lea     rcx, [rsp+2B0h+Buf2]; void *
0x180026b6b  call    memset_0
0x180026b70  mov     r8d, ebx; Size
0x180026b73  lea     rdx, [rsp+2B0h+Buf2]; Buf2
0x180026b78  lea     rcx, [rbp+1B0h+Buf1]; Buf1
0x180026b7c  call    memcmp_0
0x180026b81  test    eax, eax
0x180026b83  jnz     loc_180026C1F
0x180026b89  lea     r9, [rbp+1B0h+Buf1]
0x180026b8d  lea     r8, [rbp+1B0h+var_168]
0x180026b91  lea     edx, [rbx-3Fh]
0x180026b94  lea     rcx, [rbp+1B0h+var_100]
0x180026b9b  call    cs:__imp_InstallFeatures
0x180026ba1  mov     ebx, eax
0x180026ba3  test    eax, eax
0x180026ba5  jns     short loc_180026BFD
0x180026ba7  mov     rcx, [rbp+1B8h]; this
0x180026bae  mov     r9d, eax; char *
0x180026bb1  lea     r8, aOnecoreShellCp_3; "onecore\\shell\\cpls\\internationalsett"...
0x180026bb8  mov     edx, 8Fh; void *
0x180026bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026bc2  lea     rcx, [rbp+1B0h+Buf1]; Buf1
0x180026bc6  call    ??1?$AutoGenericHandleBase@UInstallFeaturesResult@@$03V?$AutoGenericHandle@UInstallFeaturesResult@@$03$1?CloseWithFreeInstallFeaturesResult@@YAXU1@@Z@Windows@@@Windows@@QEAA@XZ; Windows::AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>::~AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>(void)
0x180026bcb  nop
0x180026bcc  lea     rcx, [rbp+1B0h+var_158]
0x180026bd0  call    ??1?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(void)
0x180026bd5  nop
0x180026bd6  lea     rcx, [rsp+2B0h+var_290]
0x180026bdb  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(void)
0x180026be0  mov     eax, ebx
0x180026be2  mov     rcx, [rbp+1B0h+var_30]
0x180026be9  xor     rcx, rsp; StackCookie
0x180026bec  call    __security_check_cookie
0x180026bf1  add     rsp, 298h
0x180026bf8  pop     rdi
0x180026bf9  pop     rsi
0x180026bfa  pop     rbx
0x180026bfb  pop     rbp
0x180026bfc  retn
0x180026bfd  lea     rcx, [rbp+1B0h+Buf1]; Buf1
0x180026c01  call    ??1?$AutoGenericHandleBase@UInstallFeaturesResult@@$03V?$AutoGenericHandle@UInstallFeaturesResult@@$03$1?CloseWithFreeInstallFeaturesResult@@YAXU1@@Z@Windows@@@Windows@@QEAA@XZ; Windows::AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>::~AutoGenericHandleBase<InstallFeaturesResult,4,Windows::AutoGenericHandle<InstallFeaturesResult,4,&CloseWithFreeInstallFeaturesResult(InstallFeaturesResult)>>(void)
0x180026c06  nop
0x180026c07  lea     rcx, [rbp+1B0h+var_158]
0x180026c0b  call    ??1?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(void)
0x180026c10  nop
0x180026c11  lea     rcx, [rsp+2B0h+var_290]
0x180026c16  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(void)
0x180026c1b  xor     eax, eax
0x180026c1d  jmp     short loc_180026BE2
0x180026c1f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

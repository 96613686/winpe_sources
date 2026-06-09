# CStorageProviderInfo::~CStorageProviderInfo(void)

- ea: `0x1800132d0`
- end: `0x1800135e1`
- name: `??1CStorageProviderInfo@@EEAA@XZ`
- size: `785`
- prototype: `void __fastcall(CStorageProviderInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013290`

## callees

- `0x1800132d0`
- `0x180029dfc`
- `0x180060218`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800133cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800133f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013440`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001348e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001352a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013551`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001359c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800135bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800133cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800133f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013440`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001348e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001352a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013551`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001359c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800135bd`

## pseudocode

```c
void __fastcall CStorageProviderInfo::~CStorageProviderInfo(CStorageProviderInfo *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx

  *(_QWORD *)this = &CStorageProviderInfo::`vftable';
  *((_QWORD *)this + 1) = &CStorageProviderInfo::`vftable'{for `IStorageProviderInfo2'};
  *((_QWORD *)this + 2) = &CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderInfo3,IStorageProviderStatusUIInfo,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'};
  *((_QWORD *)this + 3) = &CStorageProviderInfo::`vftable'{for `IStorageProviderStatusUIInfo'};
  *((_QWORD *)this + 4) = &CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'};
  *((_QWORD *)this + 5) = &CStorageProviderInfo::`vftable'{for `IStorageProviderInfoPriv'};
  *((_QWORD *)this + 6) = &CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'};
  *((_QWORD *)this + 7) = &CStorageProviderInfo::`vftable'{for `IStorageProviderIdentityInfo2'};
  *((_QWORD *)this + 8) = &CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'};
  *((_QWORD *)this + 9) = &CStorageProviderInfo::`vftable'{for `IStorageProviderShareLinkSourceInfo'};
  *((_QWORD *)this + 10) = &CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderSearchInfo>'};
  v2 = *((_QWORD *)this + 84);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*((_QWORD *)this + 86) - v2) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 84) = 0;
    *((_QWORD *)this + 85) = 0;
    *((_QWORD *)this + 86) = 0;
  }
  v3 = *((_QWORD *)this + 81);
  if ( v3 )
  {
    std::_Deallocate<16>(v3, (*((_QWORD *)this + 83) - v3) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 81) = 0;
    *((_QWORD *)this + 82) = 0;
    *((_QWORD *)this + 83) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 51);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 51) = 0;
  }
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  v5 = (void *)*((_QWORD *)this + 48);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 48) = 0;
  }
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  v6 = (void *)*((_QWORD *)this + 45);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 45) = 0;
  }
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  v7 = (void *)*((_QWORD *)this + 42);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 42) = 0;
  }
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  v8 = (void *)*((_QWORD *)this + 39);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)this + 39) = 0;
  }
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  v9 = (void *)*((_QWORD *)this + 36);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 36) = 0;
  }
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  v10 = (void *)*((_QWORD *)this + 33);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 33) = 0;
  }
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  v11 = (void *)*((_QWORD *)this + 30);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)this + 30) = 0;
  }
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  v12 = (void *)*((_QWORD *)this + 27);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)this + 27) = 0;
  }
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  v13 = (void *)*((_QWORD *)this + 24);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)this + 24) = 0;
  }
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  v14 = (void *)*((_QWORD *)this + 21);
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *((_QWORD *)this + 21) = 0;
  }
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  v15 = (void *)*((_QWORD *)this + 18);
  if ( v15 )
  {
    CoTaskMemFree(v15);
    *((_QWORD *)this + 18) = 0;
  }
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  v16 = (void *)*((_QWORD *)this + 15);
  if ( v16 )
  {
    CoTaskMemFree(v16);
    *((_QWORD *)this + 15) = 0;
  }
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  v17 = (void *)*((_QWORD *)this + 12);
  if ( v17 )
  {
    CoTaskMemFree(v17);
    *((_QWORD *)this + 12) = 0;
  }
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStorageProviderInfo,IStorageProviderInfo2,IStorageProviderInfo3,IStorageProviderStatusUIInfo,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStorageProviderInfo,IStorageProviderInfo2,IStorageProviderInfo3,IStorageProviderStatusUIInfo,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>(this);
}

```

## disassembly

```asm
0x1800132d0  mov     [rsp+arg_0], rbx
0x1800132d5  push    rdi
0x1800132d6  sub     rsp, 20h
0x1800132da  lea     rax, ??_7CStorageProviderInfo@@6B@; const CStorageProviderInfo::`vftable'
0x1800132e1  mov     rbx, rcx
0x1800132e4  mov     [rcx], rax
0x1800132e7  xor     edi, edi
0x1800132e9  lea     rax, ??_7CStorageProviderInfo@@6BIStorageProviderInfo2@@@; const CStorageProviderInfo::`vftable'{for `IStorageProviderInfo2'}
0x1800132f0  mov     [rcx+8], rax
0x1800132f4  lea     rax, ??_7CStorageProviderInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIStorageProviderInfo3@@UIStorageProviderStatusUIInfo@@UIStorageProviderAppInfo@@UIStorageProviderInfoPriv@@UIStorageProviderIdentityInfo@@UIStorageProviderIdentityInfo2@@UIStorageProviderIdentityInfo3@@UIStorageProviderShareLinkSourceInfo@@UIStorageProviderSearchInfo@@@Details@WRL@Microsoft@@@; const CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderInfo3,IStorageProviderStatusUIInfo,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'}
0x1800132fb  mov     [rcx+10h], rax
0x1800132ff  lea     rax, ??_7CStorageProviderInfo@@6BIStorageProviderStatusUIInfo@@@; const CStorageProviderInfo::`vftable'{for `IStorageProviderStatusUIInfo'}
0x180013306  mov     [rcx+18h], rax
0x18001330a  lea     rax, ??_7CStorageProviderInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIStorageProviderAppInfo@@UIStorageProviderInfoPriv@@UIStorageProviderIdentityInfo@@UIStorageProviderIdentityInfo2@@UIStorageProviderIdentityInfo3@@UIStorageProviderShareLinkSourceInfo@@UIStorageProviderSearchInfo@@@Details@WRL@Microsoft@@@; const CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'}
0x180013311  mov     [rcx+20h], rax
0x180013315  lea     rax, ??_7CStorageProviderInfo@@6BIStorageProviderInfoPriv@@@; const CStorageProviderInfo::`vftable'{for `IStorageProviderInfoPriv'}
0x18001331c  mov     [rcx+28h], rax
0x180013320  lea     rax, ??_7CStorageProviderInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIStorageProviderIdentityInfo@@UIStorageProviderIdentityInfo2@@UIStorageProviderIdentityInfo3@@UIStorageProviderShareLinkSourceInfo@@UIStorageProviderSearchInfo@@@Details@WRL@Microsoft@@@; const CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'}
0x180013327  mov     [rcx+30h], rax
0x18001332b  lea     rax, ??_7CStorageProviderInfo@@6BIStorageProviderIdentityInfo2@@@; const CStorageProviderInfo::`vftable'{for `IStorageProviderIdentityInfo2'}
0x180013332  mov     [rcx+38h], rax
0x180013336  lea     rax, ??_7CStorageProviderInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIStorageProviderIdentityInfo3@@UIStorageProviderShareLinkSourceInfo@@UIStorageProviderSearchInfo@@@Details@WRL@Microsoft@@@; const CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>'}
0x18001333d  mov     [rcx+40h], rax
0x180013341  lea     rax, ??_7CStorageProviderInfo@@6BIStorageProviderShareLinkSourceInfo@@@; const CStorageProviderInfo::`vftable'{for `IStorageProviderShareLinkSourceInfo'}
0x180013348  mov     [rcx+48h], rax
0x18001334c  lea     rax, ??_7CStorageProviderInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIStorageProviderSearchInfo@@@Details@WRL@Microsoft@@@; const CStorageProviderInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IStorageProviderSearchInfo>'}
0x180013353  mov     [rcx+50h], rax
0x180013357  mov     rcx, [rcx+2A0h]
0x18001335e  test    rcx, rcx
0x180013361  jz      short loc_18001338B
0x180013363  mov     rdx, [rbx+2B0h]
0x18001336a  sub     rdx, rcx
0x18001336d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180013371  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013376  mov     [rbx+2A0h], rdi
0x18001337d  mov     [rbx+2A8h], rdi
0x180013384  mov     [rbx+2B0h], rdi
0x18001338b  mov     rcx, [rbx+288h]
0x180013392  test    rcx, rcx
0x180013395  jz      short loc_1800133BF
0x180013397  mov     rdx, [rbx+298h]
0x18001339e  sub     rdx, rcx
0x1800133a1  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800133a5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800133aa  mov     [rbx+288h], rdi
0x1800133b1  mov     [rbx+290h], rdi
0x1800133b8  mov     [rbx+298h], rdi
0x1800133bf  mov     rcx, [rbx+198h]; pv
0x1800133c6  test    rcx, rcx
0x1800133c9  jz      short loc_1800133D8
0x1800133cb  call    cs:__imp_CoTaskMemFree
0x1800133d1  mov     [rbx+198h], rdi
0x1800133d8  mov     [rbx+1A0h], rdi
0x1800133df  mov     [rbx+1A8h], rdi
0x1800133e6  mov     rcx, [rbx+180h]; pv
0x1800133ed  test    rcx, rcx
0x1800133f0  jz      short loc_1800133FF
0x1800133f2  call    cs:__imp_CoTaskMemFree
0x1800133f8  mov     [rbx+180h], rdi
0x1800133ff  mov     [rbx+188h], rdi
0x180013406  mov     [rbx+190h], rdi
0x18001340d  mov     rcx, [rbx+168h]; pv
0x180013414  test    rcx, rcx
0x180013417  jz      short loc_180013426
0x180013419  call    cs:__imp_CoTaskMemFree
0x18001341f  mov     [rbx+168h], rdi
0x180013426  mov     [rbx+170h], rdi
0x18001342d  mov     [rbx+178h], rdi
0x180013434  mov     rcx, [rbx+150h]; pv
0x18001343b  test    rcx, rcx
0x18001343e  jz      short loc_18001344D
0x180013440  call    cs:__imp_CoTaskMemFree
0x180013446  mov     [rbx+150h], rdi
0x18001344d  mov     [rbx+158h], rdi
0x180013454  mov     [rbx+160h], rdi
0x18001345b  mov     rcx, [rbx+138h]; pv
0x180013462  test    rcx, rcx
0x180013465  jz      short loc_180013474
0x180013467  call    cs:__imp_CoTaskMemFree
0x18001346d  mov     [rbx+138h], rdi
0x180013474  mov     [rbx+140h], rdi
0x18001347b  mov     [rbx+148h], rdi
0x180013482  mov     rcx, [rbx+120h]; pv
0x180013489  test    rcx, rcx
0x18001348c  jz      short loc_18001349B
0x18001348e  call    cs:__imp_CoTaskMemFree
0x180013494  mov     [rbx+120h], rdi
0x18001349b  mov     [rbx+128h], rdi
0x1800134a2  mov     [rbx+130h], rdi
0x1800134a9  mov     rcx, [rbx+108h]; pv
0x1800134b0  test    rcx, rcx
0x1800134b3  jz      short loc_1800134C2
0x1800134b5  call    cs:__imp_CoTaskMemFree
0x1800134bb  mov     [rbx+108h], rdi
0x1800134c2  mov     [rbx+110h], rdi
0x1800134c9  mov     [rbx+118h], rdi
0x1800134d0  mov     rcx, [rbx+0F0h]; pv
0x1800134d7  test    rcx, rcx
0x1800134da  jz      short loc_1800134E9
0x1800134dc  call    cs:__imp_CoTaskMemFree
0x1800134e2  mov     [rbx+0F0h], rdi
0x1800134e9  mov     [rbx+0F8h], rdi
0x1800134f0  mov     [rbx+100h], rdi
0x1800134f7  mov     rcx, [rbx+0D8h]; pv
0x1800134fe  test    rcx, rcx
0x180013501  jz      short loc_180013510
0x180013503  call    cs:__imp_CoTaskMemFree
0x180013509  mov     [rbx+0D8h], rdi
0x180013510  mov     [rbx+0E0h], rdi
0x180013517  mov     [rbx+0E8h], rdi
0x18001351e  mov     rcx, [rbx+0C0h]; pv
0x180013525  test    rcx, rcx
0x180013528  jz      short loc_180013537
0x18001352a  call    cs:__imp_CoTaskMemFree
0x180013530  mov     [rbx+0C0h], rdi
0x180013537  mov     [rbx+0C8h], rdi
0x18001353e  mov     [rbx+0D0h], rdi
0x180013545  mov     rcx, [rbx+0A8h]; pv
0x18001354c  test    rcx, rcx
0x18001354f  jz      short loc_18001355E
0x180013551  call    cs:__imp_CoTaskMemFree
0x180013557  mov     [rbx+0A8h], rdi
0x18001355e  mov     [rbx+0B0h], rdi
0x180013565  mov     [rbx+0B8h], rdi
0x18001356c  mov     rcx, [rbx+90h]; pv
0x180013573  test    rcx, rcx
0x180013576  jz      short loc_180013585
0x180013578  call    cs:__imp_CoTaskMemFree
0x18001357e  mov     [rbx+90h], rdi
0x180013585  mov     [rbx+98h], rdi
0x18001358c  mov     [rbx+0A0h], rdi
0x180013593  mov     rcx, [rbx+78h]; pv
0x180013597  test    rcx, rcx
0x18001359a  jz      short loc_1800135A6
0x18001359c  call    cs:__imp_CoTaskMemFree
0x1800135a2  mov     [rbx+78h], rdi
0x1800135a6  mov     [rbx+80h], rdi
0x1800135ad  mov     [rbx+88h], rdi
0x1800135b4  mov     rcx, [rbx+60h]; pv
0x1800135b8  test    rcx, rcx
0x1800135bb  jz      short loc_1800135C7
0x1800135bd  call    cs:__imp_CoTaskMemFree
0x1800135c3  mov     [rbx+60h], rdi
0x1800135c7  mov     rcx, rbx
0x1800135ca  mov     [rbx+68h], rdi
0x1800135ce  mov     [rbx+70h], rdi
0x1800135d2  mov     rbx, [rsp+28h+arg_0]
0x1800135d7  add     rsp, 20h
0x1800135db  pop     rdi
0x1800135dc  jmp     ??1?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStorageProviderInfo@@UIStorageProviderInfo2@@UIStorageProviderInfo3@@UIStorageProviderStatusUIInfo@@UIStorageProviderAppInfo@@UIStorageProviderInfoPriv@@UIStorageProviderIdentityInfo@@UIStorageProviderIdentityInfo2@@UIStorageProviderIdentityInfo3@@UIStorageProviderShareLinkSourceInfo@@UIStorageProviderSearchInfo@@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStorageProviderInfo,IStorageProviderInfo2,IStorageProviderInfo3,IStorageProviderStatusUIInfo,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStorageProviderInfo,IStorageProviderInfo2,IStorageProviderInfo3,IStorageProviderStatusUIInfo,IStorageProviderAppInfo,IStorageProviderInfoPriv,IStorageProviderIdentityInfo,IStorageProviderIdentityInfo2,IStorageProviderIdentityInfo3,IStorageProviderShareLinkSourceInfo,IStorageProviderSearchInfo>(void)
```

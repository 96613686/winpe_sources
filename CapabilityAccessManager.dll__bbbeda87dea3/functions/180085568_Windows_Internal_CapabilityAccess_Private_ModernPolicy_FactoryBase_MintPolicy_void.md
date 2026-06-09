# Windows::Internal::CapabilityAccess::Private::ModernPolicy::FactoryBase::MintPolicy(void)

- ea: `0x180085568`
- end: `0x180085919`
- name: `?MintPolicy@FactoryBase@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ`
- size: `945`
- prototype: ``
- caller_count: `19`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180083aec`
- `0x180083bc4`
- `0x180083c9c`
- `0x180083d74`
- `0x180083e4c`
- `0x180083f24`
- `0x180083ffc`
- `0x1800840d4`
- `0x1800841ac`
- `0x1800842ac`
- `0x1800843ac`
- `0x1800844a8`
- `0x180084580`
- `0x180084658`
- `0x180084730`
- `0x180084830`
- `0x180084930`
- `0x180084a08`
- `0x180084ae0`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001f4c0`
- `0x180020fcc`
- `0x18002392c`
- `0x180029408`
- `0x18002e304`
- `0x18002e704`
- `0x18002f978`
- `0x18003b54c`
- `0x180052760`
- `0x180053560`
- `0x1800535b8`
- `0x180055114`
- `0x18008545c`
- `0x180085528`
- `0x180085568`
- `0x180085958`
- `0x180085b18`
- `0x180086024`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800857d9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18008572f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18008572f`

## string_xrefs

- `0x18008560d`: `Stack has not provided a mandatory policy value: m_accessChangeWnf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::ModernPolicy::FactoryBase::MintPolicy(
        __int64 a1,
        __int64 a2)
{
  bool v4; // al
  bool v5; // al
  unsigned int v6; // r14d
  __int64 v7; // rax
  void (__fastcall *v8)(__int64, __int64); // r8
  const OLECHAR *v9; // rax
  _BYTE *v10; // rsi
  HRESULT v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r9
  _QWORD *v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  void (__fastcall *v18)(__int64, _BYTE *, __int64); // r9
  __int64 v19; // rax
  void (__fastcall *v20)(__int64, __int64); // r8
  __int64 v21; // rax
  void (__fastcall *v22)(__int64, __int64); // r8
  __int64 v23; // rax
  void (__fastcall *v24)(__int64, __int64); // r8
  __int64 v25; // rax
  void (__fastcall *v26)(__int64, __int64); // r8
  _QWORD *v27; // rax
  int v29; // [rsp+20h] [rbp-39h]
  const char *v30; // [rsp+28h] [rbp-31h]
  const char *v31; // [rsp+28h] [rbp-31h]
  const char *v32; // [rsp+28h] [rbp-31h]
  const char *v33; // [rsp+28h] [rbp-31h]
  __int64 v34; // [rsp+30h] [rbp-29h] BYREF
  std::_Ref_count_base *v35; // [rsp+38h] [rbp-21h]
  int v36; // [rsp+40h] [rbp-19h]
  __int64 v37; // [rsp+48h] [rbp-11h]
  _BYTE v38[8]; // [rsp+50h] [rbp-9h] BYREF
  std::_Ref_count_base *v39; // [rsp+58h] [rbp-1h]
  _BYTE v40[16]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v41; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v37 = a2;
  v36 = 0;
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x19,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)(*(_QWORD *)(a1 + 24) == 0),
    (bool)"Stack has not provided a mandatory policy value: m_capability",
    v30);
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x1A,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)(*(_DWORD *)(a1 + 40) == 0),
    (bool)"Stack has not provided a mandatory policy value: m_baseline",
    v31);
  v4 = !*(_DWORD *)(a1 + 44) || !*(_DWORD *)(a1 + 48);
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x1B,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)v4,
    (bool)"Stack has not provided a mandatory policy value: m_accessChangeWnf",
    v32);
  v5 = !*(_DWORD *)(a1 + 52) || !*(_DWORD *)(a1 + 56);
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x1C,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)v5,
    (bool)"Stack has not provided a mandatory policy value: m_usageChangeWnf",
    v33);
  v6 = *(_DWORD *)(a1 + 40);
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(a2);
  v36 = 2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LegacyBaseline>::GetImpl'::`2'::impl) )
    std::wstring::operator=(*(_QWORD *)a2 + 8LL, a1 + 8);
  Windows::Internal::CapabilityAccess::Private::ModernPolicy::InitializeToBaseline(a2, v6);
  *(_DWORD *)(*(_QWORD *)a2 + 500LL) = 1;
  v36 = 1;
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(v38);
  std::wstring::operator=(*(_QWORD *)a2 + 8LL, a1 + 8);
  *(_QWORD *)(*(_QWORD *)a2 + 156LL) = *(_QWORD *)(a1 + 44);
  *(_QWORD *)(*(_QWORD *)a2 + 492LL) = *(_QWORD *)(a1 + 52);
  v7 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
         &v34,
         a2);
  v8(a1, v7);
  if ( *(_QWORD *)(a1 + 80) )
  {
    Windows::Internal::CapabilityAccess::Private::CapabilityHandler::Create(&v34);
    v9 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 64);
    v10 = (_BYTE *)v34;
    v11 = CLSIDFromString(v9, (LPCLSID)(v34 + 20));
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
        (const char *)(unsigned int)v11,
        v29);
    v10[12] = *(_BYTE *)(a1 + 96);
    v10[13] = *(_BYTE *)(a1 + 97);
    v10[14] = *(_BYTE *)(a1 + 98);
    v10[15] = *(_BYTE *)(a1 + 99);
    v10[16] = *(_BYTE *)(a1 + 100);
    v12 = *(_QWORD *)(*(_QWORD *)a2 + 368LL);
    if ( v12 == *(_QWORD *)(*(_QWORD *)a2 + 376LL) )
    {
      std::vector<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsent>>::_Emplace_reallocate<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsent> const &>(
        *(_QWORD *)a2 + 360LL,
        *(_QWORD *)(*(_QWORD *)a2 + 368LL),
        &v34);
    }
    else
    {
      std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
        v12,
        &v34);
      *(_QWORD *)(v13 + 368) += 16LL;
    }
    if ( v35 )
      std::_Ref_count_base::_Decref(v35);
  }
  v14 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                    &v34,
                    a2);
  Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(v14);
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(v15, v40);
  v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40);
  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
    (unsigned int)&v34,
    v16,
    v16 + 2 * v41,
    v16,
    *(__int64 *)&_o_towlower);
  if ( !(unsigned int)std::wstring::compare(v40, L"zh") )
    *(_BYTE *)(*(_QWORD *)a2 + 49LL) = 0;
  v17 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v34,
          a2);
  v18(a1, v40, v17);
  v19 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v34,
          a2);
  v20(a1, v19);
  v21 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v34,
          a2);
  v22(a1, v21);
  v23 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v34,
          a2);
  v24(a1, v23);
  v25 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v34,
          a2);
  v26(a1, v25);
  v27 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                    &v34,
                    a2);
  Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(v27);
  std::wstring::_Tidy_deallocate(v40);
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  return a2;
}

```

## disassembly

```asm
0x180085568  mov     [rsp-8+arg_10], rbx
0x18008556d  push    rbp
0x18008556e  push    rsi
0x18008556f  push    rdi
0x180085570  push    r12
0x180085572  push    r14
0x180085574  lea     rbp, [rsp-37h]
0x180085579  sub     rsp, 90h
0x180085580  mov     rax, cs:__security_cookie
0x180085587  xor     rax, rsp
0x18008558a  mov     [rbp+57h+var_30], rax
0x18008558e  mov     rdi, rdx
0x180085591  mov     rbx, rcx
0x180085594  mov     [rbp+57h+var_68], rdx
0x180085598  mov     [rbp+57h+var_70], 0
0x18008559f  cmp     qword ptr [rcx+18h], 0
0x1800855a4  setz    al
0x1800855a7  mov     rcx, [rbp+5Fh]; this
0x1800855ab  lea     rdx, aStackHasNotPro; "Stack has not provided a mandatory poli"...
0x1800855b2  mov     qword ptr [rsp+0B0h+var_90], rdx; bool
0x1800855b7  movzx   r9d, al; char *
0x1800855bb  lea     r12, aOnecoreBaseDev_17; "onecore\\base\\devices\\cam\\policy\\fa"...
0x1800855c2  mov     r8, r12; unsigned int
0x1800855c5  mov     edx, 19h; void *
0x1800855ca  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x1800855cf  cmp     dword ptr [rbx+28h], 0
0x1800855d3  setz    al
0x1800855d6  mov     rcx, [rbp+5Fh]; this
0x1800855da  lea     rdx, aStackHasNotPro_0; "Stack has not provided a mandatory poli"...
0x1800855e1  mov     qword ptr [rsp+0B0h+var_90], rdx; bool
0x1800855e6  movzx   r9d, al; char *
0x1800855ea  mov     r8, r12; unsigned int
0x1800855ed  mov     edx, 1Ah; void *
0x1800855f2  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x1800855f7  cmp     dword ptr [rbx+2Ch], 0
0x1800855fb  jz      short loc_180085607
0x1800855fd  cmp     dword ptr [rbx+30h], 0
0x180085601  jz      short loc_180085607
0x180085603  xor     eax, eax
0x180085605  jmp     short loc_180085609
0x180085607  mov     al, 1
0x180085609  mov     rcx, [rbp+5Fh]; this
0x18008560d  lea     rdx, aStackHasNotPro_2; "Stack has not provided a mandatory poli"...
0x180085614  mov     qword ptr [rsp+0B0h+var_90], rdx; bool
0x180085619  movzx   r9d, al; char *
0x18008561d  mov     r8, r12; unsigned int
0x180085620  mov     edx, 1Bh; void *
0x180085625  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18008562a  cmp     dword ptr [rbx+34h], 0
0x18008562e  jz      short loc_18008563A
0x180085630  cmp     dword ptr [rbx+38h], 0
0x180085634  jz      short loc_18008563A
0x180085636  xor     eax, eax
0x180085638  jmp     short loc_18008563C
0x18008563a  mov     al, 1
0x18008563c  mov     rcx, [rbp+5Fh]; this
0x180085640  lea     rdx, aStackHasNotPro_1; "Stack has not provided a mandatory poli"...
0x180085647  mov     qword ptr [rsp+0B0h+var_90], rdx; int
0x18008564c  movzx   r9d, al; char *
0x180085650  mov     r8, r12; unsigned int
0x180085653  mov     edx, 1Ch; void *
0x180085658  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18008565d  mov     r14d, [rbx+28h]
0x180085661  mov     rcx, rdi
0x180085664  call    ?Create@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(void)
0x180085669  mov     [rbp+57h+var_70], 2
0x180085670  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LegacyBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline> `wil::Feature<__WilFeatureTraits_Feature_LegacyBaseline>::GetImpl(void)'::`2'::impl
0x180085677  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::__private_IsEnabled(void)
0x18008567c  test    al, al
0x18008567e  jz      short loc_180085690
0x180085680  mov     rcx, [rdi]
0x180085683  add     rcx, 8
0x180085687  lea     rdx, [rbx+8]
0x18008568b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180085690  mov     edx, r14d
0x180085693  mov     rcx, rdi
0x180085696  call    ?InitializeToBaseline@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXAEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@W4Baseline@12345@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::InitializeToBaseline(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &,Windows::Internal::CapabilityAccess::Private::ModernPolicy::Baseline)
0x18008569b  mov     rax, [rdi]
0x18008569e  mov     dword ptr [rax+1F4h], 1
0x1800856a8  mov     [rbp+57h+var_70], 1
0x1800856af  lea     rcx, [rbp+57h+var_60]
0x1800856b3  call    ?Instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(void)
0x1800856b8  nop
0x1800856b9  mov     rcx, [rdi]
0x1800856bc  add     rcx, 8
0x1800856c0  lea     rdx, [rbx+8]
0x1800856c4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800856c9  mov     rcx, [rdi]
0x1800856cc  mov     rax, [rbx+2Ch]
0x1800856d0  mov     [rcx+9Ch], rax
0x1800856d7  mov     rcx, [rdi]
0x1800856da  mov     rax, [rbx+34h]
0x1800856de  mov     [rcx+1ECh], rax
0x1800856e5  mov     rax, [rbx]
0x1800856e8  mov     r8, [rax+8]
0x1800856ec  mov     rdx, rdi
0x1800856ef  lea     rcx, [rbp+57h+var_80]
0x1800856f3  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800856f8  mov     rdx, rax
0x1800856fb  mov     rcx, rbx
0x1800856fe  mov     rax, r8
0x180085701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085706  cmp     qword ptr [rbx+50h], 0
0x18008570b  jz      loc_1800857A7
0x180085711  lea     rcx, [rbp+57h+var_80]
0x180085715  call    ?Create@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::Create(void)
0x18008571a  nop
0x18008571b  lea     rcx, [rbx+40h]
0x18008571f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085724  mov     rsi, [rbp+57h+var_80]
0x180085728  lea     rdx, [rsi+14h]; pclsid
0x18008572c  mov     rcx, rax; lpsz
0x18008572f  call    cs:__imp_CLSIDFromString
0x180085735  mov     rcx, [rbp+5Fh]; this
0x180085739  test    eax, eax
0x18008573b  js      loc_180085908
0x180085741  mov     al, [rbx+60h]
0x180085744  mov     [rsi+0Ch], al
0x180085747  mov     al, [rbx+61h]
0x18008574a  mov     [rsi+0Dh], al
0x18008574d  mov     al, [rbx+62h]
0x180085750  mov     [rsi+0Eh], al
0x180085753  mov     al, [rbx+63h]
0x180085756  mov     [rsi+0Fh], al
0x180085759  mov     al, [rbx+64h]
0x18008575c  mov     [rsi+10h], al
0x18008575f  mov     r9, [rdi]
0x180085762  mov     rcx, [r9+170h]
0x180085769  cmp     rcx, [r9+178h]
0x180085770  jz      short loc_180085785
0x180085772  lea     rdx, [rbp+57h+var_80]
0x180085776  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18008577b  add     qword ptr [r9+170h], 10h
0x180085783  jmp     short loc_180085799
0x180085785  lea     r8, [rbp+57h+var_80]
0x180085789  mov     rdx, rcx
0x18008578c  lea     rcx, [r9+168h]
0x180085793  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VCapabilityConsent@Private@CapabilityAccess@Internal@Windows@@@std@@@?$vector@V?$shared_ptr@VCapabilityConsent@Private@CapabilityAccess@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VCapabilityConsent@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VCapabilityConsent@Private@CapabilityAccess@Internal@Windows@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsent>>::_Emplace_reallocate<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsent> const &>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsent> * const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsent> const &)
0x180085798  nop
0x180085799  mov     rcx, [rbp+57h+var_78]; this
0x18008579d  test    rcx, rcx
0x1800857a0  jz      short loc_1800857A7
0x1800857a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800857a7  mov     rdx, rdi
0x1800857aa  lea     rcx, [rbp+57h+var_80]
0x1800857ae  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800857b3  mov     rcx, rax
0x1800857b6  call    ?AddPresentEditionPolicy@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)
0x1800857bb  lea     rdx, [rbp+57h+var_50]
0x1800857bf  call    ?ReadActivePolicyCode@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(void)
0x1800857c4  nop
0x1800857c5  lea     rcx, [rbp+57h+var_50]
0x1800857c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800857ce  mov     rdx, rax
0x1800857d1  mov     rax, [rbp+57h+var_40]
0x1800857d5  lea     r8, [rdx+rax*2]
0x1800857d9  mov     rax, cs:__imp__o_towlower
0x1800857e0  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800857e5  mov     r9, rdx
0x1800857e8  lea     rcx, [rbp+57h+var_80]
0x1800857ec  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1800857f1  lea     rdx, aZh; "zh"
0x1800857f8  lea     rcx, [rbp+57h+var_50]
0x1800857fc  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180085801  test    eax, eax
0x180085803  jnz     short loc_18008580C
0x180085805  mov     rax, [rdi]
0x180085808  mov     byte ptr [rax+31h], 0
0x18008580c  mov     rax, [rbx]
0x18008580f  mov     r9, [rax+10h]
0x180085813  mov     rdx, rdi
0x180085816  lea     rcx, [rbp+57h+var_80]
0x18008581a  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18008581f  mov     r8, rax
0x180085822  lea     rdx, [rbp+57h+var_50]
0x180085826  mov     rcx, rbx
0x180085829  mov     rax, r9
0x18008582c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085831  mov     rax, [rbx]
0x180085834  mov     r8, [rax+18h]
0x180085838  mov     rdx, rdi
0x18008583b  lea     rcx, [rbp+57h+var_80]
0x18008583f  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180085844  mov     rdx, rax
0x180085847  mov     rcx, rbx
0x18008584a  mov     rax, r8
0x18008584d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085852  mov     rax, [rbx]
0x180085855  mov     r8, [rax+20h]
0x180085859  mov     rdx, rdi
0x18008585c  lea     rcx, [rbp+57h+var_80]
0x180085860  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180085865  mov     rdx, rax
0x180085868  mov     rcx, rbx
0x18008586b  mov     rax, r8
0x18008586e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085873  mov     rax, [rbx]
0x180085876  mov     r8, [rax+28h]
0x18008587a  mov     rdx, rdi
0x18008587d  lea     rcx, [rbp+57h+var_80]
0x180085881  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180085886  mov     rdx, rax
0x180085889  mov     rcx, rbx
0x18008588c  mov     rax, r8
0x18008588f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085894  mov     rax, [rbx]
0x180085897  mov     r8, [rax+30h]
0x18008589b  mov     rdx, rdi
0x18008589e  lea     rcx, [rbp+57h+var_80]
0x1800858a2  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800858a7  mov     rdx, rax
0x1800858aa  mov     rcx, rbx
0x1800858ad  mov     rax, r8
0x1800858b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858b5  mov     rdx, rdi
0x1800858b8  lea     rcx, [rbp+57h+var_80]
0x1800858bc  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800858c1  mov     rcx, rax
0x1800858c4  call    ?AddLegacyRegistryOverrides@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)
0x1800858c9  nop
0x1800858ca  lea     rcx, [rbp+57h+var_50]
0x1800858ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800858d3  nop
0x1800858d4  mov     rcx, [rbp+57h+var_58]; this
0x1800858d8  test    rcx, rcx
0x1800858db  jz      short loc_1800858E2
0x1800858dd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800858e2  mov     rax, rdi
0x1800858e5  mov     rcx, [rbp+57h+var_30]
0x1800858e9  xor     rcx, rsp; StackCookie
0x1800858ec  call    __security_check_cookie
0x1800858f1  mov     rbx, [rsp+0B0h+arg_10]
0x1800858f9  add     rsp, 90h
0x180085900  pop     r14
0x180085902  pop     r12
0x180085904  pop     rdi
0x180085905  pop     rsi
0x180085906  pop     rbp
0x180085907  retn
0x180085908  mov     r9d, eax; char *
0x18008590b  mov     r8, r12; unsigned int
0x18008590e  mov     edx, 33h ; '3'; void *
0x180085913  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

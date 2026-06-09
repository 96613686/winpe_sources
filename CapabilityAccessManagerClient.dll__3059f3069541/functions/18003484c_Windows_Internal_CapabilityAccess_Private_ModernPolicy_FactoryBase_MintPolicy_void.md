# Windows::Internal::CapabilityAccess::Private::ModernPolicy::FactoryBase::MintPolicy(void)

- ea: `0x18003484c`
- end: `0x180034bfd`
- name: `?MintPolicy@FactoryBase@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ`
- size: `945`
- prototype: ``
- caller_count: `19`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032df0`
- `0x180032ec8`
- `0x180032fa0`
- `0x180033078`
- `0x180033150`
- `0x180033228`
- `0x180033300`
- `0x1800333d8`
- `0x1800334b0`
- `0x1800335b0`
- `0x1800336b0`
- `0x1800337ac`
- `0x180033884`
- `0x18003395c`
- `0x180033a34`
- `0x180033b34`
- `0x180033c34`
- `0x180033d0c`
- `0x180033de4`

## callees

- `0x180003c80`
- `0x18000f9e4`
- `0x18001b444`
- `0x18001b5ac`
- `0x18001c330`
- `0x180021204`
- `0x180021638`
- `0x180022f38`
- `0x180025200`
- `0x180028580`
- `0x180028800`
- `0x18002960c`
- `0x180029664`
- `0x18002a164`
- `0x180034790`
- `0x18003480c`
- `0x18003484c`
- `0x180034c3c`
- `0x180034dfc`
- `0x180035308`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180034abd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180034a13`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180034a13`

## string_xrefs

- `0x1800348f1`: `Stack has not provided a mandatory policy value: m_accessChangeWnf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::ModernPolicy::FactoryBase::MintPolicy(
        __int64 a1,
        _QWORD *a2)
{
  bool v4; // al
  bool v5; // al
  unsigned int v6; // r14d
  _QWORD *v7; // rax
  void (__fastcall *v8)(__int64, _QWORD *); // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  const OLECHAR *v12; // rax
  _BYTE *v13; // rsi
  HRESULT v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // r9
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // eax
  _QWORD *v23; // rax
  void (__fastcall *v24)(__int64, _BYTE *, _QWORD *); // r9
  _QWORD *v25; // rax
  void (__fastcall *v26)(__int64, _QWORD *); // r8
  _QWORD *v27; // rax
  void (__fastcall *v28)(__int64, _QWORD *); // r8
  _QWORD *v29; // rax
  void (__fastcall *v30)(__int64, _QWORD *); // r8
  _QWORD *v31; // rax
  void (__fastcall *v32)(__int64, _QWORD *); // r8
  _QWORD *v33; // rax
  int v35; // [rsp+20h] [rbp-39h]
  const char *v36; // [rsp+28h] [rbp-31h]
  const char *v37; // [rsp+28h] [rbp-31h]
  const char *v38; // [rsp+28h] [rbp-31h]
  const char *v39; // [rsp+28h] [rbp-31h]
  __int64 v40; // [rsp+30h] [rbp-29h] BYREF
  std::_Ref_count_base *v41; // [rsp+38h] [rbp-21h]
  int v42; // [rsp+40h] [rbp-19h]
  _QWORD *v43; // [rsp+48h] [rbp-11h]
  _BYTE v44[8]; // [rsp+50h] [rbp-9h] BYREF
  std::_Ref_count_base *v45; // [rsp+58h] [rbp-1h]
  _BYTE v46[16]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v47; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v43 = a2;
  v42 = 0;
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x19,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)(*(_QWORD *)(a1 + 24) == 0),
    (bool)"Stack has not provided a mandatory policy value: m_capability",
    v36);
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x1A,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)(*(_DWORD *)(a1 + 40) == 0),
    (bool)"Stack has not provided a mandatory policy value: m_baseline",
    v37);
  v4 = !*(_DWORD *)(a1 + 44) || !*(_DWORD *)(a1 + 48);
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x1B,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)v4,
    (bool)"Stack has not provided a mandatory policy value: m_accessChangeWnf",
    v38);
  v5 = !*(_DWORD *)(a1 + 52) || !*(_DWORD *)(a1 + 56);
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x1C,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
    (const char *)v5,
    (bool)"Stack has not provided a mandatory policy value: m_usageChangeWnf",
    v39);
  v6 = *(_DWORD *)(a1 + 40);
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(a2);
  v42 = 2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LegacyBaseline>::GetImpl'::`2'::impl) )
    std::wstring::operator=(*a2 + 8LL, a1 + 8);
  Windows::Internal::CapabilityAccess::Private::ModernPolicy::InitializeToBaseline(a2, v6);
  *(_DWORD *)(*a2 + 500LL) = 1;
  v42 = 1;
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(v44);
  std::wstring::operator=(*a2 + 8LL, a1 + 8);
  *(_QWORD *)(*a2 + 156LL) = *(_QWORD *)(a1 + 44);
  *(_QWORD *)(*a2 + 492LL) = *(_QWORD *)(a1 + 52);
  v7 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
         &v40,
         a2);
  v8(a1, v7);
  if ( *(_QWORD *)(a1 + 80) )
  {
    Windows::Internal::CapabilityAccess::Private::CapabilityHandler::Create(&v40);
    v12 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 64, v9, v10, v11);
    v13 = (_BYTE *)v40;
    v14 = CLSIDFromString(v12, (LPCLSID)(v40 + 20));
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\devices\\cam\\policy\\factorybase.cpp",
        (const char *)(unsigned int)v14,
        v35);
    v13[12] = *(_BYTE *)(a1 + 96);
    v13[13] = *(_BYTE *)(a1 + 97);
    v13[14] = *(_BYTE *)(a1 + 98);
    v13[15] = *(_BYTE *)(a1 + 99);
    v13[16] = *(_BYTE *)(a1 + 100);
    v15 = *(_QWORD **)(*a2 + 368LL);
    if ( v15 == *(_QWORD **)(*a2 + 376LL) )
    {
      std::vector<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>>::_Emplace_reallocate<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &>(
        (_QWORD *)(*a2 + 360LL),
        *(_QWORD *)(*a2 + 368LL));
    }
    else
    {
      std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
        v15,
        &v40);
      *(_QWORD *)(v16 + 368) += 16LL;
    }
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
  }
  v17 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
          &v40,
          a2);
  Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(v17);
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(v18, v46);
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46, v19, v20, v21);
  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
    (unsigned int)&v40,
    v22,
    v22 + 2 * v47,
    v22,
    _o_towlower);
  if ( !(unsigned int)std::wstring::compare(v46, L"zh") )
    *(_BYTE *)(*a2 + 49LL) = 0;
  v23 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
          &v40,
          a2);
  v24(a1, v46, v23);
  v25 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
          &v40,
          a2);
  v26(a1, v25);
  v27 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
          &v40,
          a2);
  v28(a1, v27);
  v29 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
          &v40,
          a2);
  v30(a1, v29);
  v31 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
          &v40,
          a2);
  v32(a1, v31);
  v33 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(
          &v40,
          a2);
  Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(v33);
  std::wstring::_Tidy_deallocate(v46);
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  return a2;
}

```

## disassembly

```asm
0x18003484c  mov     [rsp-8+arg_10], rbx
0x180034851  push    rbp
0x180034852  push    rsi
0x180034853  push    rdi
0x180034854  push    r12
0x180034856  push    r14
0x180034858  lea     rbp, [rsp-37h]
0x18003485d  sub     rsp, 90h
0x180034864  mov     rax, cs:__security_cookie
0x18003486b  xor     rax, rsp
0x18003486e  mov     [rbp+57h+var_30], rax
0x180034872  mov     rdi, rdx
0x180034875  mov     rbx, rcx
0x180034878  mov     [rbp+57h+var_68], rdx
0x18003487c  mov     [rbp+57h+var_70], 0
0x180034883  cmp     qword ptr [rcx+18h], 0
0x180034888  setz    al
0x18003488b  mov     rcx, [rbp+5Fh]; this
0x18003488f  lea     rdx, aStackHasNotPro; "Stack has not provided a mandatory poli"...
0x180034896  mov     qword ptr [rsp+0B0h+var_90], rdx; bool
0x18003489b  movzx   r9d, al; char *
0x18003489f  lea     r12, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\policy\\fa"...
0x1800348a6  mov     r8, r12; unsigned int
0x1800348a9  mov     edx, 19h; void *
0x1800348ae  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x1800348b3  cmp     dword ptr [rbx+28h], 0
0x1800348b7  setz    al
0x1800348ba  mov     rcx, [rbp+5Fh]; this
0x1800348be  lea     rdx, aStackHasNotPro_0; "Stack has not provided a mandatory poli"...
0x1800348c5  mov     qword ptr [rsp+0B0h+var_90], rdx; bool
0x1800348ca  movzx   r9d, al; char *
0x1800348ce  mov     r8, r12; unsigned int
0x1800348d1  mov     edx, 1Ah; void *
0x1800348d6  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x1800348db  cmp     dword ptr [rbx+2Ch], 0
0x1800348df  jz      short loc_1800348EB
0x1800348e1  cmp     dword ptr [rbx+30h], 0
0x1800348e5  jz      short loc_1800348EB
0x1800348e7  xor     eax, eax
0x1800348e9  jmp     short loc_1800348ED
0x1800348eb  mov     al, 1
0x1800348ed  mov     rcx, [rbp+5Fh]; this
0x1800348f1  lea     rdx, aStackHasNotPro_2; "Stack has not provided a mandatory poli"...
0x1800348f8  mov     qword ptr [rsp+0B0h+var_90], rdx; bool
0x1800348fd  movzx   r9d, al; char *
0x180034901  mov     r8, r12; unsigned int
0x180034904  mov     edx, 1Bh; void *
0x180034909  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18003490e  cmp     dword ptr [rbx+34h], 0
0x180034912  jz      short loc_18003491E
0x180034914  cmp     dword ptr [rbx+38h], 0
0x180034918  jz      short loc_18003491E
0x18003491a  xor     eax, eax
0x18003491c  jmp     short loc_180034920
0x18003491e  mov     al, 1
0x180034920  mov     rcx, [rbp+5Fh]; this
0x180034924  lea     rdx, aStackHasNotPro_1; "Stack has not provided a mandatory poli"...
0x18003492b  mov     qword ptr [rsp+0B0h+var_90], rdx; int
0x180034930  movzx   r9d, al; char *
0x180034934  mov     r8, r12; unsigned int
0x180034937  mov     edx, 1Ch; void *
0x18003493c  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x180034941  mov     r14d, [rbx+28h]
0x180034945  mov     rcx, rdi
0x180034948  call    ?Create@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(void)
0x18003494d  mov     [rbp+57h+var_70], 2
0x180034954  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LegacyBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline> `wil::Feature<__WilFeatureTraits_Feature_LegacyBaseline>::GetImpl(void)'::`2'::impl
0x18003495b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::__private_IsEnabled(void)
0x180034960  test    al, al
0x180034962  jz      short loc_180034974
0x180034964  mov     rcx, [rdi]
0x180034967  add     rcx, 8
0x18003496b  lea     rdx, [rbx+8]
0x18003496f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180034974  mov     edx, r14d
0x180034977  mov     rcx, rdi
0x18003497a  call    ?InitializeToBaseline@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXAEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@W4Baseline@12345@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::InitializeToBaseline(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &,Windows::Internal::CapabilityAccess::Private::ModernPolicy::Baseline)
0x18003497f  mov     rax, [rdi]
0x180034982  mov     dword ptr [rax+1F4h], 1
0x18003498c  mov     [rbp+57h+var_70], 1
0x180034993  lea     rcx, [rbp+57h+var_60]
0x180034997  call    ?Instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(void)
0x18003499c  nop
0x18003499d  mov     rcx, [rdi]
0x1800349a0  add     rcx, 8
0x1800349a4  lea     rdx, [rbx+8]
0x1800349a8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800349ad  mov     rcx, [rdi]
0x1800349b0  mov     rax, [rbx+2Ch]
0x1800349b4  mov     [rcx+9Ch], rax
0x1800349bb  mov     rcx, [rdi]
0x1800349be  mov     rax, [rbx+34h]
0x1800349c2  mov     [rcx+1ECh], rax
0x1800349c9  mov     rax, [rbx]
0x1800349cc  mov     r8, [rax+8]
0x1800349d0  mov     rdx, rdi
0x1800349d3  lea     rcx, [rbp+57h+var_80]
0x1800349d7  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x1800349dc  mov     rdx, rax
0x1800349df  mov     rcx, rbx
0x1800349e2  mov     rax, r8
0x1800349e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349ea  cmp     qword ptr [rbx+50h], 0
0x1800349ef  jz      loc_180034A8B
0x1800349f5  lea     rcx, [rbp+57h+var_80]
0x1800349f9  call    ?Create@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::Create(void)
0x1800349fe  nop
0x1800349ff  lea     rcx, [rbx+40h]
0x180034a03  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034a08  mov     rsi, [rbp+57h+var_80]
0x180034a0c  lea     rdx, [rsi+14h]; pclsid
0x180034a10  mov     rcx, rax; lpsz
0x180034a13  call    cs:__imp_CLSIDFromString
0x180034a19  mov     rcx, [rbp+5Fh]; this
0x180034a1d  test    eax, eax
0x180034a1f  js      loc_180034BEC
0x180034a25  mov     al, [rbx+60h]
0x180034a28  mov     [rsi+0Ch], al
0x180034a2b  mov     al, [rbx+61h]
0x180034a2e  mov     [rsi+0Dh], al
0x180034a31  mov     al, [rbx+62h]
0x180034a34  mov     [rsi+0Eh], al
0x180034a37  mov     al, [rbx+63h]
0x180034a3a  mov     [rsi+0Fh], al
0x180034a3d  mov     al, [rbx+64h]
0x180034a40  mov     [rsi+10h], al
0x180034a43  mov     r9, [rdi]
0x180034a46  mov     rcx, [r9+170h]
0x180034a4d  cmp     rcx, [r9+178h]
0x180034a54  jz      short loc_180034A69
0x180034a56  lea     rdx, [rbp+57h+var_80]
0x180034a5a  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034a5f  add     qword ptr [r9+170h], 10h
0x180034a67  jmp     short loc_180034A7D
0x180034a69  lea     r8, [rbp+57h+var_80]
0x180034a6d  mov     rdx, rcx
0x180034a70  lea     rcx, [r9+168h]
0x180034a77  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@@?$vector@V?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>>::_Emplace_reallocate<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> * const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034a7c  nop
0x180034a7d  mov     rcx, [rbp+57h+var_78]; this
0x180034a81  test    rcx, rcx
0x180034a84  jz      short loc_180034A8B
0x180034a86  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034a8b  mov     rdx, rdi
0x180034a8e  lea     rcx, [rbp+57h+var_80]
0x180034a92  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034a97  mov     rcx, rax
0x180034a9a  call    ?AddPresentEditionPolicy@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)
0x180034a9f  lea     rdx, [rbp+57h+var_50]
0x180034aa3  call    ?ReadActivePolicyCode@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(void)
0x180034aa8  nop
0x180034aa9  lea     rcx, [rbp+57h+var_50]
0x180034aad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034ab2  mov     rdx, rax
0x180034ab5  mov     rax, [rbp+57h+var_40]
0x180034ab9  lea     r8, [rdx+rax*2]
0x180034abd  mov     rax, cs:__imp__o_towlower
0x180034ac4  mov     qword ptr [rsp+0B0h+var_90], rax
0x180034ac9  mov     r9, rdx
0x180034acc  lea     rcx, [rbp+57h+var_80]
0x180034ad0  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x180034ad5  lea     rdx, aZh; "zh"
0x180034adc  lea     rcx, [rbp+57h+var_50]
0x180034ae0  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180034ae5  test    eax, eax
0x180034ae7  jnz     short loc_180034AF0
0x180034ae9  mov     rax, [rdi]
0x180034aec  mov     byte ptr [rax+31h], 0
0x180034af0  mov     rax, [rbx]
0x180034af3  mov     r9, [rax+10h]
0x180034af7  mov     rdx, rdi
0x180034afa  lea     rcx, [rbp+57h+var_80]
0x180034afe  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034b03  mov     r8, rax
0x180034b06  lea     rdx, [rbp+57h+var_50]
0x180034b0a  mov     rcx, rbx
0x180034b0d  mov     rax, r9
0x180034b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b15  mov     rax, [rbx]
0x180034b18  mov     r8, [rax+18h]
0x180034b1c  mov     rdx, rdi
0x180034b1f  lea     rcx, [rbp+57h+var_80]
0x180034b23  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034b28  mov     rdx, rax
0x180034b2b  mov     rcx, rbx
0x180034b2e  mov     rax, r8
0x180034b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b36  mov     rax, [rbx]
0x180034b39  mov     r8, [rax+20h]
0x180034b3d  mov     rdx, rdi
0x180034b40  lea     rcx, [rbp+57h+var_80]
0x180034b44  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034b49  mov     rdx, rax
0x180034b4c  mov     rcx, rbx
0x180034b4f  mov     rax, r8
0x180034b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b57  mov     rax, [rbx]
0x180034b5a  mov     r8, [rax+28h]
0x180034b5e  mov     rdx, rdi
0x180034b61  lea     rcx, [rbp+57h+var_80]
0x180034b65  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034b6a  mov     rdx, rax
0x180034b6d  mov     rcx, rbx
0x180034b70  mov     rax, r8
0x180034b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b78  mov     rax, [rbx]
0x180034b7b  mov     r8, [rax+30h]
0x180034b7f  mov     rdx, rdi
0x180034b82  lea     rcx, [rbp+57h+var_80]
0x180034b86  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034b8b  mov     rdx, rax
0x180034b8e  mov     rcx, rbx
0x180034b91  mov     rax, r8
0x180034b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b99  mov     rdx, rdi
0x180034b9c  lea     rcx, [rbp+57h+var_80]
0x180034ba0  call    ??0?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &)
0x180034ba5  mov     rcx, rax
0x180034ba8  call    ?AddLegacyRegistryOverrides@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)
0x180034bad  nop
0x180034bae  lea     rcx, [rbp+57h+var_50]
0x180034bb2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034bb7  nop
0x180034bb8  mov     rcx, [rbp+57h+var_58]; this
0x180034bbc  test    rcx, rcx
0x180034bbf  jz      short loc_180034BC6
0x180034bc1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034bc6  mov     rax, rdi
0x180034bc9  mov     rcx, [rbp+57h+var_30]
0x180034bcd  xor     rcx, rsp; StackCookie
0x180034bd0  call    __security_check_cookie
0x180034bd5  mov     rbx, [rsp+0B0h+arg_10]
0x180034bdd  add     rsp, 90h
0x180034be4  pop     r14
0x180034be6  pop     r12
0x180034be8  pop     rdi
0x180034be9  pop     rsi
0x180034bea  pop     rbp
0x180034beb  retn
0x180034bec  mov     r9d, eax; char *
0x180034bef  mov     r8, r12; unsigned int
0x180034bf2  mov     edx, 33h ; '3'; void *
0x180034bf7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

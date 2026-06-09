# _lambda_6ac006fb6aed2ed0911b9dc4b09ff962_::operator()

- ea: `0x180048784`
- end: `0x180049016`
- name: `_lambda_6ac006fb6aed2ed0911b9dc4b09ff962_::operator()`
- size: `2194`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180047380`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001f5f4`
- `0x180020fcc`
- `0x1800210d4`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x18003684c`
- `0x180036f0c`
- `0x180040930`
- `0x1800417e0`
- `0x1800467c8`
- `0x18004694c`
- `0x180048784`
- `0x1800493d4`
- `0x18004d0ac`
- `0x18004fb64`
- `0x180050bf0`
- `0x18005b214`
- `0x180064090`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180048c72`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180048c72`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048848`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048848`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x1800487cd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x1800487cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall lambda_6ac006fb6aed2ed0911b9dc4b09ff962_::operator()(__int64 a1)
{
  __int64 v2; // rax
  int v3; // eax
  __int64 v4; // rbx
  int ActivationFactory; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64, __int64); // r12
  __int64 AppSelector; // rax
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, double *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, double *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, double *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, double *); // rbx
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, double *); // rbx
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, double *); // rbx
  int v31; // eax
  __int64 UsageFrequency; // rdi
  __int64 v33; // r13
  int v34; // esi
  int v35; // r12d
  int v36; // eax
  unsigned int v37; // edi
  __int64 v38; // rcx
  const unsigned __int16 *v39; // rax
  const unsigned __int16 *v40; // rdx
  const unsigned __int16 *v41; // rax
  const unsigned __int16 *v42; // r8
  const unsigned __int16 *v43; // r9
  __int64 result; // rax
  const char *v45; // r9
  int v46; // [rsp+20h] [rbp-168h]
  unsigned __int16 *v47; // [rsp+28h] [rbp-160h]
  __int64 v48; // [rsp+50h] [rbp-138h] BYREF
  __int64 v49; // [rsp+58h] [rbp-130h] BYREF
  __int64 v50; // [rsp+60h] [rbp-128h] BYREF
  __int64 v51; // [rsp+68h] [rbp-120h] BYREF
  double v52; // [rsp+70h] [rbp-118h] BYREF
  double v53; // [rsp+78h] [rbp-110h] BYREF
  __int64 v54; // [rsp+80h] [rbp-108h] BYREF
  double v55; // [rsp+88h] [rbp-100h] BYREF
  double v56; // [rsp+90h] [rbp-F8h] BYREF
  double v57; // [rsp+98h] [rbp-F0h] BYREF
  double v58[2]; // [rsp+A0h] [rbp-E8h] BYREF
  struct _GUID v59; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 v60; // [rsp+C0h] [rbp-C8h]
  __int128 hstringHeader; // [rsp+C8h] [rbp-C0h] BYREF
  __m128i hstringHeader_16; // [rsp+D8h] [rbp-B0h]
  __int128 v63; // [rsp+E8h] [rbp-A0h] BYREF
  __m128i v64; // [rsp+F8h] [rbp-90h]
  struct _SYSTEMTIME v65; // [rsp+110h] [rbp-78h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+130h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v51 = 0;
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v3 = UMgrQueryUserContextFromSid(v2, &v51);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6F4,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)(unsigned int)v3,
      v46);
    v51 = 0;
  }
  v50 = 0;
  hstringHeader_16.m128i_i64[1] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&hstringHeader,
    L"Windows.Internal.Shell.ConsentUx.ConsentUxManager",
    0x32u,
    0x31u);
  v4 = hstringHeader_16.m128i_i64[1];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_f072e044_d067_49bf_a95c_8f889dcce584, &v50);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6FC,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v46);
    v49 = 0;
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"Windows.Internal.Shell.ConsentUx.ConsentUxRequestContext",
      0x39u,
      0x38u);
    v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IConsentUxRequestContext>>(
           hstringHeader_16.m128i_i64[1],
           &v49);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6FF,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v6,
        v46);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 56LL))(v49, v51);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x700,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v7,
        v46);
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 88LL))(v49, *(unsigned int *)(a1 + 116));
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x701,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v8,
        v46);
    v48 = 0;
    v9 = v50;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v50 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    AppSelector = Windows::Internal::CapabilityAccess::Private::GetAppSelector(
                    (__int64)&v65,
                    a1 + 80,
                    *(_DWORD *)(a1 + 112),
                    *(_DWORD *)(a1 + 116));
    v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(AppSelector);
    v12 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v63, &v54) + 24);
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"[\"IsUnlocked\", \"TicksSinceLastSessionInput\"]",
      0x2Du,
      0x2Cu);
    v13 = v10(v9, v49, hstringHeader_16.m128i_i64[1], v12);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x705,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v13,
        10);
    hstringHeader_16.m128i_i64[1] = 0;
    v64.m128i_i64[1] = 0;
    std::wstring::_Tidy_deallocate(&v65);
    v53 = 0.0;
    v14 = v48;
    v15 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v48 + 48LL);
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"IsUnlocked",
      0xBu,
      0xAu);
    v16 = v15(v14, hstringHeader_16.m128i_i64[1], &v53);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x709,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v16,
        10);
    v52 = 0.0;
    v17 = v48;
    v18 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v48 + 48LL);
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"TicksSinceLastSessionInput",
      0x1Bu,
      0x1Au);
    v19 = v18(v17, hstringHeader_16.m128i_i64[1], &v52);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v19,
        10);
    v56 = 0.0;
    v20 = v48;
    v21 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v48 + 48LL);
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"CurrentlyInFocus",
      0x11u,
      0x10u);
    v22 = v21(v20, hstringHeader_16.m128i_i64[1], &v56);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x711,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v22,
        10);
    v55 = 0.0;
    v23 = v48;
    v24 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v48 + 48LL);
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"UserInput",
      0xAu,
      9u);
    v25 = v24(v23, hstringHeader_16.m128i_i64[1], &v55);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x715,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v25,
        10);
    v58[0] = 0.0;
    v26 = v48;
    v27 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v48 + 48LL);
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&hstringHeader, L"InFocus", 8u, 7u);
    v28 = v27(v26, hstringHeader_16.m128i_i64[1], v58);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x719,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v28,
        10);
    v57 = 0.0;
    v29 = v48;
    v30 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v48 + 48LL);
    hstringHeader_16.m128i_i64[1] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&hstringHeader,
      L"DisplayRequired",
      0x10u,
      0xFu);
    v31 = v30(v29, hstringHeader_16.m128i_i64[1], &v57);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v31,
        10);
    UsageFrequency = Windows::Internal::CapabilityAccess::Private::SQL::GetUsageFrequency(
                       (Windows::Internal::CapabilityAccess::Private::SQL *)a1,
                       a1 + 32,
                       a1 + 80,
                       *(_DWORD *)(a1 + 112),
                       10);
    v60 = UsageFrequency;
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    v65 = SystemTime;
    v59 = *(struct _GUID *)(a1 + 120);
    CapabilityAccessTelemetry::LogCapabilityAccessFeatures(
      &v59,
      UsageFrequency,
      v53 != 0.0,
      (int)v52,
      v56 != 0.0,
      v55,
      v58[0],
      v57,
      &v65);
    v33 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::Globals::SuspiciousRuleManagerGlobal::GetSuspiciousRuleManager();
    v54 = (unsigned int)(int)v52;
    LOBYTE(UsageFrequency) = v53 != 0.0;
    v34 = *(_DWORD *)(a1 + 112);
    *(_QWORD *)&v59.Data1 = &hstringHeader;
    v35 = std::wstring::wstring(&hstringHeader, a1 + 80);
    v36 = std::wstring::wstring(&v63, a1 + 32);
    v37 = Windows::Internal::CapabilityAccess::Private::SuspiciousRuleManager::Evaluate(
            v33,
            v36,
            v35,
            v34,
            v60,
            UsageFrequency,
            v54);
    if ( v37 )
    {
      Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(&v59);
      LODWORD(v47) = 0;
      Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetLastUserAnnotatedLabel(
        v38,
        a1,
        a1 + 32,
        a1 + 80,
        *(_DWORD *)(a1 + 112),
        v47);
      if ( *(_DWORD *)(a1 + 112) == 1 )
      {
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
        v39 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 80);
        v65 = *(struct _SYSTEMTIME *)(a1 + 120);
        CapabilityAccessTelemetry::SendSuspiciousToastTelemetry(v39, 0, 0, (struct _GUID *)&v65, v40, v37, 0);
      }
      else
      {
        hstringHeader = 0;
        hstringHeader_16 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(hstringHeader) = 0;
        v63 = 0;
        v64 = hstringHeader_16;
        LOWORD(v63) = 0;
        Windows::Internal::CapabilityAccess::Private::GetFileProgramIDByBinaryFullPath(a1 + 80, &hstringHeader, &v63);
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
        v65 = *(struct _SYSTEMTIME *)(a1 + 120);
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v63);
        v41 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
        CapabilityAccessTelemetry::SendSuspiciousToastTelemetry(0, v41, v42, (struct _GUID *)&v65, v43, v37, 0);
        std::wstring::_Tidy_deallocate(&v63);
        std::wstring::_Tidy_deallocate(&hstringHeader);
      }
      if ( *(_QWORD *)v59.Data4 )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v59.Data4);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    result = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x74D,
             (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
             v45);
  }
  return result;
}

```

## disassembly

```asm
0x180048784  mov     rax, rsp
0x180048787  mov     [rax+10h], rbx
0x18004878b  mov     [rax+18h], rsi
0x18004878f  push    rdi
0x180048790  push    r12
0x180048792  push    r13
0x180048794  push    r14
0x180048796  push    r15
0x180048798  sub     rsp, 160h
0x18004879f  movaps  xmmword ptr [rax-38h], xmm6
0x1800487a3  mov     rax, cs:__security_cookie
0x1800487aa  xor     rax, rsp
0x1800487ad  mov     [rsp+188h+var_48], rax
0x1800487b5  mov     r14, rcx
0x1800487b8  xor     r13d, r13d
0x1800487bb  mov     [rsp+188h+var_120], r13
0x1800487c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800487c5  lea     rdx, [rsp+188h+var_120]
0x1800487ca  mov     rcx, rax
0x1800487cd  call    cs:__imp_UMgrQueryUserContextFromSid
0x1800487d3  mov     rcx, [rsp+188h]; this
0x1800487db  lea     rsi, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800487e2  test    eax, eax
0x1800487e4  jns     short loc_1800487FB
0x1800487e6  mov     r9d, eax; char *
0x1800487e9  mov     r8, rsi; unsigned int
0x1800487ec  mov     edx, 6F4h; void *
0x1800487f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800487f6  mov     [rsp+188h+var_120], r13
0x1800487fb  mov     [rsp+188h+var_128], r13
0x180048800  mov     [rsp+188h+var_A8], r13
0x180048808  mov     r9d, 31h ; '1'; unsigned int
0x18004880e  lea     r8d, [r9+1]; unsigned int
0x180048812  lea     rdx, ?RuntimeClass_Windows_Internal_Shell_ConsentUx_ConsentUxManager@@3QBGB; "Windows.Internal.Shell.ConsentUx.Consen"...
0x180048819  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048821  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048826  nop
0x180048827  mov     rbx, [rsp+188h+var_A8]
0x18004882f  lea     rcx, [rsp+188h+var_128]
0x180048834  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048839  lea     r8, [rsp+188h+var_128]
0x18004883e  lea     rdx, _GUID_f072e044_d067_49bf_a95c_8f889dcce584
0x180048845  mov     rcx, rbx
0x180048848  call    cs:__imp_RoGetActivationFactory
0x18004884e  mov     rcx, [rsp+188h]; this
0x180048856  test    eax, eax
0x180048858  js      loc_180048F5B
0x18004885e  mov     [rsp+188h+var_130], r13
0x180048863  mov     [rsp+188h+var_A8], r13
0x18004886b  mov     r9d, 38h ; '8'; unsigned int
0x180048871  lea     r8d, [r9+1]; unsigned int
0x180048875  lea     rdx, ?RuntimeClass_Windows_Internal_Shell_ConsentUx_ConsentUxRequestContext@@3QBGB; "Windows.Internal.Shell.ConsentUx.Consen"...
0x18004887c  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048884  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048889  nop
0x18004888a  lea     rdx, [rsp+188h+var_130]
0x18004888f  mov     rcx, [rsp+188h+var_A8]
0x180048897  call    ??$ActivateInstance@V?$ComPtr@UIConsentUxRequestContext@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIConsentUxRequestContext@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IConsentUxRequestContext>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IConsentUxRequestContext>>)
0x18004889c  mov     rcx, [rsp+188h]; this
0x1800488a4  test    eax, eax
0x1800488a6  js      loc_180048F6C
0x1800488ac  mov     rcx, [rsp+188h+var_130]
0x1800488b1  mov     rax, [rcx]
0x1800488b4  mov     rdx, [rsp+188h+var_120]
0x1800488b9  mov     rax, [rax+38h]
0x1800488bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488c2  mov     rcx, [rsp+188h]; this
0x1800488ca  test    eax, eax
0x1800488cc  js      loc_180048F7D
0x1800488d2  mov     rcx, [rsp+188h+var_130]
0x1800488d7  mov     rax, [rcx]
0x1800488da  mov     edx, [r14+74h]
0x1800488de  mov     rax, [rax+58h]
0x1800488e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488e7  mov     rcx, [rsp+188h]; this
0x1800488ef  test    eax, eax
0x1800488f1  js      loc_180048F8D
0x1800488f7  mov     [rsp+188h+var_138], r13
0x1800488fc  mov     rdi, [rsp+188h+var_128]
0x180048901  mov     rax, [rdi]
0x180048904  mov     r12, [rax+40h]
0x180048908  lea     rcx, [rsp+188h+var_138]
0x18004890d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048912  lea     r15, [r14+50h]
0x180048916  mov     r9d, [r14+74h]
0x18004891a  mov     r8d, [r14+70h]
0x18004891e  mov     rdx, r15
0x180048921  lea     rcx, [rsp+188h+var_78]
0x180048929  call    ?GetAppSelector@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@W4AppIdType@1234@K@Z; Windows::Internal::CapabilityAccess::Private::GetAppSelector(std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType,ulong)
0x18004892e  nop
0x18004892f  mov     rcx, rax
0x180048932  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048937  mov     [rsp+188h+var_108], rax
0x18004893f  lea     rdx, [rsp+188h+var_108]
0x180048947  lea     rcx, [rsp+188h+var_A0]
0x18004894f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180048954  nop
0x180048955  mov     rbx, [rax+18h]
0x180048959  mov     [rsp+188h+var_A8], r13
0x180048961  mov     r9d, 2Ch ; ','; unsigned int
0x180048967  lea     r8d, [r9+1]; unsigned int
0x18004896b  lea     rdx, aIsunlockedTick; "[\"IsUnlocked\", \"TicksSinceLastSessio"...
0x180048972  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x18004897a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004897f  nop
0x180048980  lea     rax, [rsp+188h+var_138]
0x180048985  mov     qword ptr [rsp+188h+var_160], rax
0x18004898a  mov     dword ptr [rsp+188h+var_168], 0Ah; int
0x180048992  mov     r9, rbx
0x180048995  mov     r8, [rsp+188h+var_A8]
0x18004899d  mov     rdx, [rsp+188h+var_130]
0x1800489a2  mov     rcx, rdi
0x1800489a5  mov     rax, r12
0x1800489a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489ad  mov     rcx, [rsp+188h]; this
0x1800489b5  test    eax, eax
0x1800489b7  js      loc_180048F9E
0x1800489bd  mov     [rsp+188h+var_A8], r13
0x1800489c5  mov     [rsp+188h+var_88], r13
0x1800489cd  lea     rcx, [rsp+188h+var_78]
0x1800489d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800489da  xorps   xmm6, xmm6
0x1800489dd  movsd   [rsp+188h+var_110], xmm6
0x1800489e3  mov     rdi, [rsp+188h+var_138]
0x1800489e8  mov     rax, [rdi]
0x1800489eb  mov     rbx, [rax+30h]
0x1800489ef  mov     [rsp+188h+var_A8], r13
0x1800489f7  mov     r9d, 0Ah; unsigned int
0x1800489fd  lea     r8d, [r9+1]; unsigned int
0x180048a01  lea     rdx, aIsunlocked; "IsUnlocked"
0x180048a08  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048a10  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048a15  nop
0x180048a16  lea     r8, [rsp+188h+var_110]
0x180048a1b  mov     rdx, [rsp+188h+var_A8]
0x180048a23  mov     rcx, rdi
0x180048a26  mov     rax, rbx
0x180048a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a2e  mov     rcx, [rsp+188h]; this
0x180048a36  test    eax, eax
0x180048a38  js      loc_180048FAF
0x180048a3e  movsd   [rsp+188h+var_118], xmm6
0x180048a44  mov     rdi, [rsp+188h+var_138]
0x180048a49  mov     rax, [rdi]
0x180048a4c  mov     rbx, [rax+30h]
0x180048a50  mov     [rsp+188h+var_A8], r13
0x180048a58  mov     r9d, 1Ah; unsigned int
0x180048a5e  lea     r8d, [r9+1]; unsigned int
0x180048a62  lea     rdx, aTickssincelast; "TicksSinceLastSessionInput"
0x180048a69  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048a71  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048a76  nop
0x180048a77  lea     r8, [rsp+188h+var_118]
0x180048a7c  mov     rdx, [rsp+188h+var_A8]
0x180048a84  mov     rcx, rdi
0x180048a87  mov     rax, rbx
0x180048a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a8f  mov     rcx, [rsp+188h]; this
0x180048a97  test    eax, eax
0x180048a99  js      loc_180048FC0
0x180048a9f  movsd   [rsp+188h+var_F8], xmm6
0x180048aa8  mov     rdi, [rsp+188h+var_138]
0x180048aad  mov     rax, [rdi]
0x180048ab0  mov     rbx, [rax+30h]
0x180048ab4  mov     [rsp+188h+var_A8], r13
0x180048abc  mov     r12d, 10h
0x180048ac2  mov     r9d, r12d; unsigned int
0x180048ac5  lea     r8d, [r12+1]; unsigned int
0x180048aca  lea     rdx, aCurrentlyinfoc; "CurrentlyInFocus"
0x180048ad1  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048ad9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048ade  nop
0x180048adf  lea     r8, [rsp+188h+var_F8]
0x180048ae7  mov     rdx, [rsp+188h+var_A8]
0x180048aef  mov     rcx, rdi
0x180048af2  mov     rax, rbx
0x180048af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048afa  mov     rcx, [rsp+188h]; this
0x180048b02  test    eax, eax
0x180048b04  js      loc_180048FD1
0x180048b0a  movsd   [rsp+188h+var_100], xmm6
0x180048b13  mov     rdi, [rsp+188h+var_138]
0x180048b18  mov     rax, [rdi]
0x180048b1b  mov     rbx, [rax+30h]
0x180048b1f  mov     [rsp+188h+var_A8], r13
0x180048b27  mov     r9d, 9; unsigned int
0x180048b2d  lea     r8d, [r9+1]; unsigned int
0x180048b31  lea     rdx, aUserinput; "UserInput"
0x180048b38  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048b40  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048b45  nop
0x180048b46  lea     r8, [rsp+188h+var_100]
0x180048b4e  mov     rdx, [rsp+188h+var_A8]
0x180048b56  mov     rcx, rdi
0x180048b59  mov     rax, rbx
0x180048b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b61  mov     rcx, [rsp+188h]; this
0x180048b69  test    eax, eax
0x180048b6b  js      loc_180048FE2
0x180048b71  movsd   [rsp+188h+var_E8], xmm6
0x180048b7a  mov     rdi, [rsp+188h+var_138]
0x180048b7f  mov     rax, [rdi]
0x180048b82  mov     rbx, [rax+30h]
0x180048b86  mov     [rsp+188h+var_A8], r13
0x180048b8e  mov     r9d, 7; unsigned int
0x180048b94  lea     r8d, [r9+1]; unsigned int
0x180048b98  lea     rdx, aInfocus; "InFocus"
0x180048b9f  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048ba7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048bac  nop
0x180048bad  lea     r8, [rsp+188h+var_E8]
0x180048bb5  mov     rdx, [rsp+188h+var_A8]
0x180048bbd  mov     rcx, rdi
0x180048bc0  mov     rax, rbx
0x180048bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bc8  mov     rcx, [rsp+188h]; this
0x180048bd0  test    eax, eax
0x180048bd2  js      loc_180048FF3
0x180048bd8  movsd   [rsp+188h+var_F0], xmm6
0x180048be1  mov     rdi, [rsp+188h+var_138]
0x180048be6  mov     rax, [rdi]
0x180048be9  mov     rbx, [rax+30h]
0x180048bed  mov     [rsp+188h+var_A8], r13
0x180048bf5  mov     r9d, 0Fh; unsigned int
0x180048bfb  mov     r8d, r12d; unsigned int
0x180048bfe  lea     rdx, aDisplayrequire; "DisplayRequired"
0x180048c05  lea     rcx, [rsp+188h+hstringHeader]; hstringHeader
0x180048c0d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048c12  nop
0x180048c13  lea     r8, [rsp+188h+var_F0]
0x180048c1b  mov     rdx, [rsp+188h+var_A8]
0x180048c23  mov     rcx, rdi
0x180048c26  mov     rax, rbx
0x180048c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c2e  mov     rcx, [rsp+188h]; this
0x180048c36  test    eax, eax
0x180048c38  js      loc_180049004
0x180048c3e  lea     rbx, [r14+20h]
0x180048c42  mov     r9d, [r14+70h]
0x180048c46  mov     r8, r15
0x180048c49  mov     rdx, rbx
0x180048c4c  mov     rcx, r14
0x180048c4f  call    ?GetUsageFrequency@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4AppIdType@2345@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetUsageFrequency(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType,uint)
0x180048c54  mov     rdi, rax
0x180048c57  mov     [rsp+188h+var_C8], rax
0x180048c5f  xorps   xmm0, xmm0
0x180048c62  movups  xmmword ptr [rsp+188h+SystemTime.wYear], xmm0
0x180048c6a  lea     rcx, [rsp+188h+SystemTime]; lpSystemTime
0x180048c72  call    cs:__imp_GetLocalTime
0x180048c78  movsd   xmm2, [rsp+188h+var_100]
0x180048c81  movsd   xmm0, [rsp+188h+var_F8]
0x180048c8a  ucomisd xmm0, xmm6
0x180048c8e  jp      short loc_180048C95
0x180048c90  mov     al, r13b
0x180048c93  jz      short loc_180048C97
0x180048c95  mov     al, 1
0x180048c97  cvttsd2si r9, [rsp+188h+var_118]; unsigned int
0x180048c9e  movsd   xmm0, [rsp+188h+var_110]
0x180048ca4  ucomisd xmm0, xmm6
0x180048ca8  jp      short loc_180048CAF
0x180048caa  mov     r8b, r13b
0x180048cad  jz      short loc_180048CB2
0x180048caf  mov     r8b, 1; bool
0x180048cb2  movaps  xmm0, xmmword ptr [rsp+188h+SystemTime.wYear]
0x180048cba  movdqa  xmmword ptr [rsp+188h+var_78.wYear], xmm0
0x180048cc3  movups  xmm0, xmmword ptr [r14+78h]
0x180048cc8  movdqu  xmmword ptr [rsp+188h+var_D8.Data1], xmm0
0x180048cd1  lea     rcx, [rsp+188h+var_78]
0x180048cd9  mov     [rsp+188h+var_148], rcx; struct _SYSTEMTIME *
0x180048cde  movsd   xmm0, [rsp+188h+var_F0]
0x180048ce7  movsd   [rsp+188h+var_150], xmm0; double
0x180048ced  movsd   xmm1, [rsp+188h+var_E8]
0x180048cf6  movsd   qword ptr [rsp+188h+var_158], xmm1; double
0x180048cfc  movsd   qword ptr [rsp+188h+var_160], xmm2; double
0x180048d02  mov     byte ptr [rsp+188h+var_168], al; bool
0x180048d06  mov     rdx, rdi; unsigned __int64
0x180048d09  lea     rcx, [rsp+188h+var_D8]; struct _GUID *
0x180048d11  call    ?LogCapabilityAccessFeatures@CapabilityAccessTelemetry@@SAXU_GUID@@_K_NI2NNNU_SYSTEMTIME@@@Z; CapabilityAccessTelemetry::LogCapabilityAccessFeatures(_GUID,unsigned __int64,bool,uint,bool,double,double,double,_SYSTEMTIME)
0x180048d16  call    ?GetSuspiciousRuleManager@SuspiciousRuleManagerGlobal@Globals@Private@CapabilityAccess@Internal@Windows@@SAAEAV?$shared_ptr@$$CBVSuspiciousRuleManager@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::Globals::SuspiciousRuleManagerGlobal::GetSuspiciousRuleManager(void)
0x180048d1b  mov     r13, [rax]
0x180048d1e  cvttsd2si rax, [rsp+188h+var_118]
0x180048d25  mov     [rsp+188h+var_108], rax
0x180048d2d  movsd   xmm0, [rsp+188h+var_110]
0x180048d33  ucomisd xmm0, xmm6
0x180048d37  jp      short loc_180048D3F
0x180048d39  jnz     short loc_180048D3F
0x180048d3b  xor     edi, edi
0x180048d3d  jmp     short loc_180048D42
0x180048d3f  mov     dil, 1
0x180048d42  mov     esi, [r14+70h]
0x180048d46  lea     rax, [rsp+188h+hstringHeader]
0x180048d4e  mov     qword ptr [rsp+188h+var_D8.Data1], rax
0x180048d56  mov     rdx, r15
0x180048d59  lea     rcx, [rsp+188h+hstringHeader]
0x180048d61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180048d66  mov     r12, rax
0x180048d69  mov     rdx, rbx
0x180048d6c  lea     rcx, [rsp+188h+var_A0]
0x180048d74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180048d79  nop
  ... truncated ...
```

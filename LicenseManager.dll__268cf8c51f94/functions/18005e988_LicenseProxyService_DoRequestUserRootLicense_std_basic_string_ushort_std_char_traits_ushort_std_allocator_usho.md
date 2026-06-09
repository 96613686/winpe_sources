# LicenseProxyService::DoRequestUserRootLicense(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,TraceLoggingCorrelationVector *,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &,ushort const *)

- ea: `0x18005e988`
- end: `0x18005eeaa`
- name: `?DoRequestUserRootLicense@LicenseProxyService@@AEAA?AV?$ComPtr@VLicenseResponse@LicenseProxyService@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVTraceLoggingCorrelationVector@@AEBV?$ComPtr@UILicenseIdentityContext@@@34@PEBG@Z`
- size: `1314`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005e530`

## callees

- `0x180004738`
- `0x180006b08`
- `0x180006b38`
- `0x180006cec`
- `0x180007704`
- `0x180007c78`
- `0x18000a0e4`
- `0x18000a110`
- `0x180012dc0`
- `0x180013b50`
- `0x18001b7f8`
- `0x180036394`
- `0x180040b08`
- `0x1800593bc`
- `0x18005b730`
- `0x18005ce98`
- `0x18005d47c`
- `0x18005e988`
- `0x18005eeb0`
- `0x18005f014`
- `0x18005fe10`
- `0x180075e60`
- `0x180076eb8`
- `0x18007b210`
- `0x18007b370`
- `0x18007b630`
- `0x18007c1c0`
- `0x18007cca0`
- `0x18009bf58`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eb1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eca6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eb1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005eca6`
- `ext-ms-win-core-licensemanager-l1-1-1!GetLicenseProtocolVersion` at `0x18005ea24`
- `ext-ms-win-core-licensemanager-l1-1-1!GetLicenseProtocolVersion` at `0x18005ea24`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ec61`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ec61`

## string_xrefs

- `0x18005ebc3`: `LicenseProxyService::DoRequestUserRootLicense`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall LicenseProxyService::DoRequestUserRootLicense(
        __int64 a1,
        __int64 a2,
        unsigned __int16 **a3,
        TraceLoggingCorrelationVector *a4,
        __int64 a5,
        __int64 a6)
{
  TraceLoggingCorrelationVector *v6; // r13
  unsigned __int16 **v7; // r15
  __int64 v8; // r14
  unsigned __int16 *v9; // rsi
  __int64 v10; // r12
  int LicenseProtocolVersion; // eax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  unsigned __int16 *v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  ContentIdString *v21; // rax
  __int64 v22; // rax
  ULONGLONG v23; // rbx
  unsigned int v24; // eax
  const unsigned __int16 *v25; // rdx
  const unsigned __int16 *v26; // r8
  unsigned __int64 v27; // rbx
  wil *v28; // rcx
  char v29; // bl
  int v30; // eax
  unsigned int v31; // eax
  unsigned int v33; // eax
  int Format; // [rsp+20h] [rbp-358h]
  int Formata; // [rsp+20h] [rbp-358h]
  int Formatb; // [rsp+20h] [rbp-358h]
  char v37; // [rsp+50h] [rbp-328h]
  char v38[7]; // [rsp+51h] [rbp-327h] BYREF
  __int64 v39; // [rsp+58h] [rbp-320h] BYREF
  __int64 v40; // [rsp+60h] [rbp-318h] BYREF
  __int64 v41; // [rsp+68h] [rbp-310h] BYREF
  unsigned int v42; // [rsp+70h] [rbp-308h] BYREF
  ULONGLONG TickCount64; // [rsp+78h] [rbp-300h] BYREF
  __int64 v44; // [rsp+80h] [rbp-2F8h] BYREF
  _QWORD v45[2]; // [rsp+88h] [rbp-2F0h] BYREF
  __int64 v46; // [rsp+98h] [rbp-2E0h]
  __int64 v47; // [rsp+A0h] [rbp-2D8h]
  unsigned __int16 *v48; // [rsp+A8h] [rbp-2D0h]
  TraceLoggingCorrelationVector *v49; // [rsp+B0h] [rbp-2C8h]
  __int64 v50; // [rsp+B8h] [rbp-2C0h]
  _BYTE v51[40]; // [rsp+C8h] [rbp-2B0h] BYREF
  int v52[4]; // [rsp+F0h] [rbp-288h] BYREF
  __m128i si128; // [rsp+100h] [rbp-278h]
  int v54; // [rsp+110h] [rbp-268h]
  void **v55; // [rsp+118h] [rbp-260h]
  __int64 v56; // [rsp+120h] [rbp-258h]
  __int64 v57; // [rsp+128h] [rbp-250h]
  __int64 v58; // [rsp+130h] [rbp-248h]
  int v59[8]; // [rsp+140h] [rbp-238h] BYREF
  _QWORD v60[30]; // [rsp+160h] [rbp-218h] BYREF
  char v61[80]; // [rsp+250h] [rbp-128h] BYREF
  char v62[144]; // [rsp+2A0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  v6 = a4;
  v7 = a3;
  v8 = a2;
  v45[0] = a1;
  v46 = a1;
  v47 = a2;
  v9 = (unsigned __int16 *)a3;
  v48 = (unsigned __int16 *)a3;
  v49 = a4;
  v41 = a5;
  v10 = a6;
  v50 = a6;
  web::json::value::value((web::json::value *)&v44);
  v42 = 4;
  if ( (unsigned __int8)IsGetLicenseProtocolVersionPresent() )
  {
    LicenseProtocolVersion = GetLicenseProtocolVersion(&v42);
    if ( LicenseProtocolVersion < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9CD,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)LicenseProtocolVersion,
        Format);
  }
  v12 = web::json::value::number(&TickCount64, v42);
  std::wstring::wstring(v51, L"licenseVersion");
  v13 = web::json::value::operator[](&v44, v51);
  web::json::value::operator=(v13, v12);
  ContentIdString::~ContentIdString((ContentIdString *)v51);
  web::json::value::~value((web::json::value *)&TickCount64);
  *(_OWORD *)v52 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v52[0]) = 0;
  v54 = 0;
  v55 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  v56 = 0;
  v57 = 0;
  v58 = 0;
  web::json::value::value((web::json::value *)&v39);
  v37 = 0;
  LicenseProxyService::GetSnapshotFromIdentity(&v40, v41);
  TickCount64 = GetTickCount64();
  v14 = v45[0];
  while ( 2 )
  {
    TraceLoggingCorrelationVector::Increment(v6, v62);
    try
    {
      LicenseProxyService::CreateUserRootRequest((HttpRequest *)v59, v9, (__int64)v62, (__int64)&v44);
      if ( *((_QWORD *)v9 + 3) <= 7u )
        v15 = v9;
      else
        v15 = *v7;
      v16 = v60;
      if ( v60[3] > 7u )
        v16 = (_QWORD *)v60[0];
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        0x9DFu,
        "LicenseProxyService::DoRequestUserRootLicense",
        (wchar_t *)L"Requesting user root for %s at %s (%s) (Corr: %hs)",
        v10,
        v16,
        v15,
        v62);
      v17 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 48LL))(v40);
      v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 32LL))(*v17);
      ThreadTokenScope::ThreadTokenScope(v38, v18);
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 40LL))(v40);
      v20 = LicenseProxyService::SendRequestAndWaitForResponse(v14, v61, v9, v19, v59);
      HttpResponse::operator=(v52, v20);
      HttpResponse::~HttpResponse((HttpResponse *)v61);
      RevertToSelf();
      v21 = (ContentIdString *)HttpResponse::Body(v52, v51);
      v22 = LicenseProxyService::ParseJsonResponse((web::json::value *)v45, v21);
      web::json::value::operator=(&v39, v22);
      web::json::value::~value((web::json::value *)v45);
      v23 = GetTickCount64();
      v24 = HttpResponse::StatusCode((HttpResponse *)v52);
      v27 = v23 - TickCount64;
      if ( v24 - 200 > 0x63 )
      {
        v33 = LicenseProxyService::HandleFault(
                (int)v62,
                (int)L"RequestUserRoot",
                0,
                (int)v59,
                (HttpResponse *)v52,
                (__int64)&v39,
                v27,
                (__int64)&v40);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9EB,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)v33,
          Formatb);
      }
      LogRequestUserRootSuccess(
        v62,
        v25,
        v26,
        (const struct HttpRequest *)v59,
        (const struct HttpResponse *)v52,
        (const struct web::json::value *)&v39,
        v27);
      HttpRequest::~HttpRequest((HttpRequest *)v59);
    }
    catch ( ... )
    {
      if ( !v37 && (unsigned int)wil::ResultFromCaughtException(v28) == -2147024891 )
      {
        v41 = 0;
        if ( (int)Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot>::As<ILicenseIdentityContextSnapshotRemediation>(
                    &v40,
                    &v41) >= 0
          && (*(int (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41) >= 0 )
        {
          v37 = 1;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
          v14 = v46;
          v8 = v47;
          v9 = v48;
          v6 = v49;
          v10 = v50;
          v7 = (unsigned __int16 **)v48;
          continue;
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      }
      throw;
    }
    break;
  }
  std::wstring::wstring(v51, L"satisfactionFailure");
  v29 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v39 + 8LL))(v39, v51);
  ContentIdString::~ContentIdString((ContentIdString *)v51);
  if ( v29 )
  {
    std::wstring::wstring(v51, L"satisfactionFailure");
    v30 = web::json::value::at(&v39, v51);
    v31 = LicenseProxyService::HandleSatisfactionFailure(
            (unsigned int)v62,
            (unsigned int)v52,
            v30,
            (unsigned int)&v40,
            0,
            0,
            0);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA03,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)v31,
      Formata);
  }
  LicenseProxyService::ParseUserRootResponse(v8, &v39);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  web::json::value::~value((web::json::value *)&v39);
  HttpResponse::~HttpResponse((HttpResponse *)v52);
  web::json::value::~value((web::json::value *)&v44);
  return v8;
}

```

## disassembly

```asm
0x18005e988  push    rbx
0x18005e98a  push    rsi
0x18005e98b  push    rdi
0x18005e98c  push    r12
0x18005e98e  push    r13
0x18005e990  push    r14
0x18005e992  push    r15
0x18005e994  sub     rsp, 340h
0x18005e99b  mov     rax, cs:__security_cookie
0x18005e9a2  xor     rax, rsp
0x18005e9a5  mov     [rsp+378h+var_48], rax
0x18005e9ad  mov     r13, r9
0x18005e9b0  mov     r15, r8
0x18005e9b3  mov     r14, rdx
0x18005e9b6  mov     [rsp+378h+var_2F0], rcx
0x18005e9be  mov     [rsp+378h+var_2E0], rcx
0x18005e9c6  mov     [rsp+378h+var_2D8], rdx
0x18005e9ce  mov     rsi, r8
0x18005e9d1  mov     [rsp+378h+var_2D0], r8
0x18005e9d9  mov     [rsp+378h+var_2C8], r9
0x18005e9e1  mov     rax, [rsp+378h+arg_20]
0x18005e9e9  mov     [rsp+378h+var_310], rax
0x18005e9ee  mov     r12, [rsp+378h+arg_28]
0x18005e9f6  mov     [rsp+378h+var_2C0], r12
0x18005e9fe  xor     edi, edi
0x18005ea00  lea     rcx, [rsp+378h+var_2F8]; this
0x18005ea08  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x18005ea0d  nop
0x18005ea0e  mov     [rsp+378h+var_308], 4
0x18005ea16  call    IsGetLicenseProtocolVersionPresent
0x18005ea1b  test    al, al
0x18005ea1d  jz      short loc_18005EA4B
0x18005ea1f  lea     rcx, [rsp+378h+var_308]
0x18005ea24  call    cs:__imp_GetLicenseProtocolVersion
0x18005ea2a  mov     rcx, [rsp+378h]; this
0x18005ea32  test    eax, eax
0x18005ea34  jns     short loc_18005EA4B
0x18005ea36  mov     r9d, eax; char *
0x18005ea39  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005ea40  mov     edx, 9CDh; void *
0x18005ea45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ea4b  mov     edx, [rsp+378h+var_308]
0x18005ea4f  lea     rcx, [rsp+378h+var_300]
0x18005ea54  call    ?number@value@json@web@@SA?AV123@H@Z; web::json::value::number(int)
0x18005ea59  mov     rbx, rax
0x18005ea5c  lea     rdx, aLicenseversion; "licenseVersion"
0x18005ea63  lea     rcx, [rsp+378h+var_2B0]
0x18005ea6b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ea70  nop
0x18005ea71  lea     rdx, [rsp+378h+var_2B0]
0x18005ea79  lea     rcx, [rsp+378h+var_2F8]
0x18005ea81  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18005ea86  mov     rcx, rax
0x18005ea89  mov     rdx, rbx
0x18005ea8c  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x18005ea91  nop
0x18005ea92  lea     rcx, [rsp+378h+var_2B0]; this
0x18005ea9a  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005ea9f  nop
0x18005eaa0  lea     rcx, [rsp+378h+var_300]; this
0x18005eaa5  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x18005eaaa  xorps   xmm0, xmm0
0x18005eaad  movups  xmmword ptr [rsp+378h+var_288], xmm0
0x18005eab5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005eabd  movdqa  [rsp+378h+var_278], xmm1
0x18005eac6  mov     word ptr [rsp+378h+var_288], di
0x18005eace  mov     [rsp+378h+var_268], edi
0x18005ead5  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x18005eadc  mov     [rsp+378h+var_260], rax
0x18005eae4  mov     [rsp+378h+var_258], rdi
0x18005eaec  mov     [rsp+378h+var_250], rdi
0x18005eaf4  mov     [rsp+378h+var_248], rdi
0x18005eafc  lea     rcx, [rsp+378h+var_320]; this
0x18005eb01  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x18005eb06  nop
0x18005eb07  mov     [rsp+378h+var_328], dil
0x18005eb0c  mov     rdx, [rsp+378h+var_310]
0x18005eb11  lea     rcx, [rsp+378h+var_318]
0x18005eb16  call    ?GetSnapshotFromIdentity@LicenseProxyService@@CA?AV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@AEBV?$ComPtr@UILicenseIdentityContext@@@34@@Z; LicenseProxyService::GetSnapshotFromIdentity(Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &)
0x18005eb1b  nop
0x18005eb1c  call    cs:__imp_GetTickCount64
0x18005eb22  mov     [rsp+378h+var_300], rax
0x18005eb27  mov     rbx, [rsp+378h+var_2F0]
0x18005eb2f  lea     rdx, [rsp+378h+var_D8]; char *
0x18005eb37  mov     rcx, r13; this
0x18005eb3a  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18005eb3f  lea     rax, [rsp+378h+var_2F8]
0x18005eb47  mov     [rsp+378h+var_350], rax; __int64
0x18005eb4c  lea     rax, [rsp+378h+var_D8]
0x18005eb54  mov     [rsp+378h+Format], rax; __int64
0x18005eb59  lea     r9, [rsp+378h+var_318]
0x18005eb5e  mov     r8, r12
0x18005eb61  mov     rdx, rsi; unsigned __int16 *
0x18005eb64  lea     rcx, [rsp+378h+var_238]; this
0x18005eb6c  call    ?CreateUserRootRequest@LicenseProxyService@@CA?AVHttpRequest@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@PEBDAEBVvalue@json@web@@@Z; LicenseProxyService::CreateUserRootRequest(std::wstring const &,ushort const *,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &,char const *,web::json::value const &)
0x18005eb71  nop
0x18005eb72  cmp     qword ptr [rsi+18h], 7
0x18005eb77  jbe     short loc_18005EB7E
0x18005eb79  mov     rcx, [r15]
0x18005eb7c  jmp     short loc_18005EB81
0x18005eb7e  mov     rcx, rsi
0x18005eb81  lea     rax, [rsp+378h+var_218]
0x18005eb89  cmp     [rsp+378h+var_200], 7
0x18005eb92  cmova   rax, [rsp+378h+var_218]
0x18005eb9b  lea     rdx, [rsp+378h+var_D8]
0x18005eba3  mov     [rsp+378h+var_338], rdx
0x18005eba8  mov     [rsp+378h+var_340], rcx
0x18005ebad  mov     [rsp+378h+var_348], rax
0x18005ebb2  mov     [rsp+378h+var_350], r12
0x18005ebb7  lea     rax, aRequestingUser; "Requesting user root for %s at %s (%s) "...
0x18005ebbe  mov     [rsp+378h+Format], rax; Format
0x18005ebc3  lea     r9, aLicenseproxyse_12; "LicenseProxyService::DoRequestUserRootL"...
0x18005ebca  mov     r8d, 9DFh; unsigned int
0x18005ebd0  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005ebd7  mov     ecx, 3; unsigned int
0x18005ebdc  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005ebe1  mov     rcx, [rsp+378h+var_318]
0x18005ebe6  mov     rax, [rcx]
0x18005ebe9  mov     rax, [rax+30h]
0x18005ebed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ebf2  mov     rcx, [rax]
0x18005ebf5  mov     rax, [rcx]
0x18005ebf8  mov     rax, [rax+20h]
0x18005ebfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec01  mov     rdx, rax
0x18005ec04  lea     rcx, [rsp+378h+var_327]
0x18005ec09  call    ??0ThreadTokenScope@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; ThreadTokenScope::ThreadTokenScope(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18005ec0e  nop
0x18005ec0f  mov     rcx, [rsp+378h+var_318]
0x18005ec14  mov     rax, [rcx]
0x18005ec17  mov     rax, [rax+28h]
0x18005ec1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec20  lea     rcx, [rsp+378h+var_238]
0x18005ec28  mov     [rsp+378h+Format], rcx
0x18005ec2d  mov     r9, rax
0x18005ec30  mov     r8, rsi
0x18005ec33  lea     rdx, [rsp+378h+var_128]
0x18005ec3b  mov     rcx, rbx
0x18005ec3e  call    ?SendRequestAndWaitForResponse@LicenseProxyService@@AEAA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z; LicenseProxyService::SendRequestAndWaitForResponse(std::wstring const &,ProxySettings const &,HttpRequest &)
0x18005ec43  mov     rdx, rax
0x18005ec46  lea     rcx, [rsp+378h+var_288]
0x18005ec4e  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x18005ec53  lea     rcx, [rsp+378h+var_128]; this
0x18005ec5b  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x18005ec60  nop
0x18005ec61  call    cs:__imp_RevertToSelf
0x18005ec67  lea     rdx, [rsp+378h+var_2B0]
0x18005ec6f  lea     rcx, [rsp+378h+var_288]
0x18005ec77  call    ?Body@HttpResponse@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HttpResponse::Body(void)
0x18005ec7c  mov     rdx, rax; ContentIdString *
0x18005ec7f  lea     rcx, [rsp+378h+var_2F0]; this
0x18005ec87  call    ?ParseJsonResponse@LicenseProxyService@@SA?AVvalue@json@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LicenseProxyService::ParseJsonResponse(std::wstring)
0x18005ec8c  mov     rdx, rax
0x18005ec8f  lea     rcx, [rsp+378h+var_320]
0x18005ec94  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x18005ec99  lea     rcx, [rsp+378h+var_2F0]; this
0x18005eca1  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x18005eca6  call    cs:__imp_GetTickCount64
0x18005ecac  mov     rbx, rax
0x18005ecaf  lea     rcx, [rsp+378h+var_288]; this
0x18005ecb7  call    ?StatusCode@HttpResponse@@QEBAKXZ; HttpResponse::StatusCode(void)
0x18005ecbc  add     eax, 0FFFFFF38h
0x18005ecc1  sub     rbx, [rsp+378h+var_300]
0x18005ecc6  lea     r9, [rsp+378h+var_238]; int
0x18005ecce  lea     rcx, [rsp+378h+var_D8]; int
0x18005ecd6  cmp     eax, 63h ; 'c'
0x18005ecd9  ja      loc_18005EE25
0x18005ecdf  mov     [rsp+378h+var_348], rbx; unsigned __int64
0x18005ece4  lea     rax, [rsp+378h+var_320]
0x18005ece9  mov     [rsp+378h+var_350], rax; struct web::json::value *
0x18005ecee  lea     rax, [rsp+378h+var_288]
0x18005ecf6  mov     [rsp+378h+Format], rax; struct HttpResponse *
0x18005ecfb  call    ?LogRequestUserRootSuccess@@YAXPEBDPEBG1AEBVHttpRequest@@AEBVHttpResponse@@AEBVvalue@json@web@@_K@Z; LogRequestUserRootSuccess(char const *,ushort const *,ushort const *,HttpRequest const &,HttpResponse const &,web::json::value const &,unsigned __int64)
0x18005ed00  nop
0x18005ed01  lea     rcx, [rsp+378h+var_238]; this
0x18005ed09  call    ??1HttpRequest@@QEAA@XZ; HttpRequest::~HttpRequest(void)
0x18005ed0e  nop
0x18005ed0f  lea     rdx, aSatisfactionfa; "satisfactionFailure"
0x18005ed16  lea     rcx, [rsp+378h+var_2B0]
0x18005ed1e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ed23  nop
0x18005ed24  mov     rcx, [rsp+378h+var_320]
0x18005ed29  mov     rax, [rcx]
0x18005ed2c  lea     rdx, [rsp+378h+var_2B0]
0x18005ed34  mov     rax, [rax+8]
0x18005ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed3d  mov     bl, al
0x18005ed3f  lea     rcx, [rsp+378h+var_2B0]; this
0x18005ed47  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005ed4c  test    bl, bl
0x18005ed4e  jz      short loc_18005EDC0
0x18005ed50  lea     rdx, aSatisfactionfa; "satisfactionFailure"
0x18005ed57  lea     rcx, [rsp+378h+var_2B0]
0x18005ed5f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ed64  nop
0x18005ed65  lea     rdx, [rsp+378h+var_2B0]
0x18005ed6d  lea     rcx, [rsp+378h+var_320]
0x18005ed72  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18005ed77  mov     r8, rax
0x18005ed7a  mov     byte ptr [rsp+378h+var_348], dil
0x18005ed7f  mov     [rsp+378h+var_350], rdi
0x18005ed84  mov     [rsp+378h+Format], rdi; int
0x18005ed89  lea     r9, [rsp+378h+var_318]
0x18005ed8e  lea     rdx, [rsp+378h+var_288]
0x18005ed96  lea     rcx, [rsp+378h+var_D8]
0x18005ed9e  call    ?HandleSatisfactionFailure@LicenseProxyService@@CAJPEBDAEBVHttpResponse@@AEBVvalue@json@web@@AEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@PEBG4_N@Z; LicenseProxyService::HandleSatisfactionFailure(char const *,HttpResponse const &,web::json::value const &,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &,ushort const *,ushort const *,bool)
0x18005eda3  mov     rcx, [rsp+378h]; this
0x18005edab  mov     r9d, eax; char *
0x18005edae  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005edb5  mov     edx, 0A03h; void *
0x18005edba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005edc0  lea     rdx, [rsp+378h+var_320]
0x18005edc5  mov     rcx, r14
0x18005edc8  call    ?ParseUserRootResponse@LicenseProxyService@@CA?AV?$ComPtr@VLicenseResponse@LicenseProxyService@@@WRL@Microsoft@@AEBVvalue@json@web@@@Z; LicenseProxyService::ParseUserRootResponse(web::json::value const &)
0x18005edcd  nop
0x18005edce  lea     rcx, [rsp+378h+var_318]
0x18005edd3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005edd8  nop
0x18005edd9  lea     rcx, [rsp+378h+var_320]; this
0x18005edde  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x18005ede3  nop
0x18005ede4  lea     rcx, [rsp+378h+var_288]; this
0x18005edec  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x18005edf1  nop
0x18005edf2  lea     rcx, [rsp+378h+var_2F8]; this
0x18005edfa  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x18005edff  mov     rax, r14
0x18005ee02  mov     rcx, [rsp+378h+var_48]
0x18005ee0a  xor     rcx, rsp; StackCookie
0x18005ee0d  call    __security_check_cookie
0x18005ee12  add     rsp, 340h
0x18005ee19  pop     r15
0x18005ee1b  pop     r14
0x18005ee1d  pop     r13
0x18005ee1f  pop     r12
0x18005ee21  pop     rdi
0x18005ee22  pop     rsi
0x18005ee23  pop     rbx
0x18005ee24  retn
0x18005ee25  lea     rax, [rsp+378h+var_318]
0x18005ee2a  mov     [rsp+378h+var_340], rax; __int64
0x18005ee2f  mov     [rsp+378h+var_348], rbx; int
0x18005ee34  lea     rax, [rsp+378h+var_320]
0x18005ee39  mov     [rsp+378h+var_350], rax; __int64
0x18005ee3e  lea     rax, [rsp+378h+var_288]
0x18005ee46  mov     [rsp+378h+Format], rax; int
0x18005ee4b  xor     r8d, r8d; int
0x18005ee4e  lea     rdx, aRequestuserroo; "RequestUserRoot"
0x18005ee55  call    ?HandleFault@LicenseProxyService@@CAJPEBDPEBG1AEBVHttpRequest@@AEBVHttpResponse@@AEBVvalue@json@web@@_KAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@J@Z; LicenseProxyService::HandleFault(char const *,ushort const *,ushort const *,HttpRequest const &,HttpResponse const &,web::json::value const &,unsigned __int64,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &,long)
0x18005ee5a  mov     rcx, [rsp+378h]; this
0x18005ee62  mov     r9d, eax; char *
0x18005ee65  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005ee6c  mov     edx, 9EBh; void *
0x18005ee71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ee77  xor     edi, edi
0x18005ee79  mov     rbx, [rsp+378h+var_2E0]
0x18005ee81  mov     r14, [rsp+378h+var_2D8]
0x18005ee89  mov     rsi, [rsp+378h+var_2D0]
0x18005ee91  mov     r13, [rsp+378h+var_2C8]
0x18005ee99  mov     r12, [rsp+378h+var_2C0]
0x18005eea1  mov     r15, rsi
0x18005eea4  jmp     loc_18005EB2F
```

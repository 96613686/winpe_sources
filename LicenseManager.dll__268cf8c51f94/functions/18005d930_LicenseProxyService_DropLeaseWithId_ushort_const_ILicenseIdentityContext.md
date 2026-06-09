# LicenseProxyService::DropLeaseWithId(ushort const *,ILicenseIdentityContext *)

- ea: `0x18005d930`
- end: `0x18005e03d`
- name: `?DropLeaseWithId@LicenseProxyService@@UEAAJPEBGPEAUILicenseIdentityContext@@@Z`
- size: `1805`
- prototype: `__int64 __fastcall(LicenseProxyService *__hidden this, const unsigned __int16 *, struct ILicenseIdentityContext *)`
- caller_count: `0`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800046e8`
- `0x180004738`
- `0x180006b08`
- `0x180006b38`
- `0x180006cec`
- `0x18000737c`
- `0x180007704`
- `0x180007c78`
- `0x18000a0e4`
- `0x18000a110`
- `0x18000b7fc`
- `0x180012dc0`
- `0x180013b50`
- `0x180017230`
- `0x180017654`
- `0x18001b7f8`
- `0x180028160`
- `0x180033a5c`
- `0x180036394`
- `0x1800363ec`
- `0x1800369e4`
- `0x18003e33c`
- `0x18003ffbc`
- `0x180040b08`
- `0x1800454b8`
- `0x18005815c`
- `0x1800593bc`
- `0x18005b730`
- `0x18005c038`
- `0x18005c1ec`
- `0x18005d6e8`
- `0x18005d930`
- `0x18005eeb0`
- `0x18005f014`
- `0x180075e60`
- `0x18007e710`
- `0x180099c90`
- `0x18009b288`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ddec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005dece`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005ddec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005dece`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005dec8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005dec8`

## string_xrefs

- `0x18005dac3`: `application/json`
- `0x18005d9f4`: `/v7.0/licenses/leases/remove`
- `0x18005dd82`: `LicenseProxyService::DropLeaseWithId`
- `0x18005db37`: `User-Agent`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
__int64 __fastcall LicenseProxyService::DropLeaseWithId(
        LicenseProxyService *this,
        const unsigned __int16 *a2,
        struct ILicenseIdentityContext *a3)
{
  struct ILicenseIdentityContext *v3; // r14
  const unsigned __int16 *v4; // r12
  LicenseProxyService *v5; // rsi
  unsigned int v6; // r13d
  unsigned __int16 *v7; // rbx
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 OsVersionHeader; // rbx
  __int64 v14; // rax
  const WCHAR *v15; // rdx
  WinStoreAuth::AuthenticationInternal *v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  _QWORD *v20; // rdx
  void *v21; // rbx
  const WCHAR *v22; // rax
  __int64 (__fastcall *v23)(struct ILicenseIdentityContext *, GUID *, __int64 *); // rbx
  int v24; // eax
  ULONGLONG TickCount64; // r15
  __int64 v26; // rax
  __int64 v27; // r14
  char *v28; // rbx
  __int64 v29; // rax
  unsigned __int64 v30; // rbx
  ContentIdString *v31; // rax
  unsigned int v32; // eax
  wil *v33; // rcx
  unsigned int v35; // ebx
  const char *v36; // r9
  wchar_t *Format; // [rsp+20h] [rbp-368h]
  int Formata; // [rsp+20h] [rbp-368h]
  int Formatb; // [rsp+20h] [rbp-368h]
  int Formatc; // [rsp+20h] [rbp-368h]
  char v41; // [rsp+50h] [rbp-338h]
  struct ILicenseIdentityContext *v42; // [rsp+58h] [rbp-330h] BYREF
  unsigned int v43; // [rsp+60h] [rbp-328h]
  _BYTE v44[4]; // [rsp+64h] [rbp-324h] BYREF
  __int64 v45; // [rsp+68h] [rbp-320h] BYREF
  __int64 v46; // [rsp+70h] [rbp-318h] BYREF
  _BYTE v47[8]; // [rsp+78h] [rbp-310h] BYREF
  __int64 v48; // [rsp+80h] [rbp-308h] BYREF
  LicenseProxyService *v49; // [rsp+88h] [rbp-300h]
  struct ILicenseIdentityContext *v50; // [rsp+90h] [rbp-2F8h]
  const unsigned __int16 *v51; // [rsp+98h] [rbp-2F0h]
  _QWORD v52[4]; // [rsp+A0h] [rbp-2E8h] BYREF
  _BYTE v53[32]; // [rsp+C0h] [rbp-2C8h] BYREF
  int v54[4]; // [rsp+E0h] [rbp-2A8h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-298h]
  int v56; // [rsp+100h] [rbp-288h]
  void **v57; // [rsp+108h] [rbp-280h]
  __int64 v58; // [rsp+110h] [rbp-278h]
  __int64 v59; // [rsp+118h] [rbp-270h]
  __int64 v60; // [rsp+120h] [rbp-268h]
  _BYTE v61[32]; // [rsp+130h] [rbp-258h] BYREF
  int v62[8]; // [rsp+150h] [rbp-238h] BYREF
  _QWORD v63[27]; // [rsp+170h] [rbp-218h] BYREF
  _BYTE v64[24]; // [rsp+248h] [rbp-140h] BYREF
  char v65[80]; // [rsp+260h] [rbp-128h] BYREF
  char v66[144]; // [rsp+2B0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  v49 = this;
  v51 = a2;
  v50 = a3;
  v6 = 0;
  LicenseProxyService::InitializeIfNeeded(this);
  TraceLoggingCorrelationVector::Increment((LicenseProxyService *)((char *)v5 + 72), v66);
  v42 = v3;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v42);
  LicenseProxyService::GetSnapshotFromIdentity(&v45, &v42);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  LicenseProxyService::CreateDropLeaseBody(v47, v4, &v45);
  v41 = 0;
  while ( 2 )
  {
    try
    {
      v7 = (unsigned __int16 *)*((_QWORD *)v5 + 6);
      Nexus::InitializeIfNecessary(v7);
      v8 = v7 + 12;
      if ( *((_QWORD *)v7 + 6) > 7u )
        v8 = *(const unsigned __int16 **)v8;
      HttpRequest::HttpRequest((HttpRequest *)v62, v8, L"/v7.0/licenses/leases/remove", L"POST", Format);
      std::string::string(v52, v66);
      v9 = ConvertToWide(v53, v52, 0);
      std::wstring::wstring(v61, L"MS-CV");
      v10 = std::map<std::wstring,std::wstring>::operator[](v64, v61);
      std::wstring::operator=(v10, v9);
      ContentIdString::~ContentIdString((ContentIdString *)v61);
      ContentIdString::~ContentIdString((ContentIdString *)v53);
      std::string::_Tidy_deallocate(v52);
      std::wstring::wstring(v52, L"Content-Type");
      v11 = std::map<std::wstring,std::wstring>::operator[](v64, v52);
      std::wstring::assign(v11, L"application/json");
      ContentIdString::~ContentIdString((ContentIdString *)v52);
      std::wstring::wstring(v52, L"From");
      v12 = std::map<std::wstring,std::wstring>::operator[](v64, v52);
      std::wstring::assign(v12, L"WindowsLicenseManager");
      ContentIdString::~ContentIdString((ContentIdString *)v52);
      OsVersionHeader = LicenseProxyService::GetOsVersionHeader(v53);
      std::wstring::wstring(v52, L"User-Agent");
      v14 = std::map<std::wstring,std::wstring>::operator[](v64, v52);
      std::wstring::operator=(v14, OsVersionHeader);
      ContentIdString::~ContentIdString((ContentIdString *)v52);
      ContentIdString::~ContentIdString((ContentIdString *)v53);
      v15 = (const WCHAR *)web::json::value::serialize(v47, v53);
      HttpRequest::SetBody((__int64)v62, v15);
      ContentIdString::~ContentIdString((ContentIdString *)v53);
      if ( WinStoreAuth::AuthenticationInternal::UseXToken(v16) )
      {
        v20 = v63;
        if ( v63[3] > 7u )
          v20 = (_QWORD *)v63[0];
        std::wstring::wstring(v61, v20);
        v21 = (void *)*((_QWORD *)v5 + 6);
        Nexus::InitializeIfNecessary(v21);
        std::wstring::wstring(v52, L"POST");
        v22 = (const WCHAR *)web::json::value::serialize(v47, v53);
        LicenseProxyService::AddXTokenAndSignRequest(
          (__int64)v62,
          v22,
          v52,
          (__int64)v21 + 24,
          (__int64)v61,
          L"*",
          &v45);
        ContentIdString::~ContentIdString((ContentIdString *)v53);
        ContentIdString::~ContentIdString((ContentIdString *)v52);
        ContentIdString::~ContentIdString((ContentIdString *)v61);
      }
      else
      {
        v42 = 0;
        v17 = Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot>::As<ILicenseSingleUserIdentityInternal>(
                &v45,
                &v42);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x223,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v17,
            Formata);
        v18 = (*(__int64 (__fastcall **)(struct ILicenseIdentityContext *))(*(_QWORD *)v42 + 24LL))(v42);
        std::wstring::wstring(v52, L"authorization");
        v19 = std::map<std::wstring,std::wstring>::operator[](v64, v52);
        std::wstring::operator=(v19, v18);
        ContentIdString::~ContentIdString((ContentIdString *)v52);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      }
      Nexus::InitializeIfNecessary(*((PVOID *)v5 + 6));
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        0x233u,
        "LicenseProxyService::DropLeaseWithId",
        (wchar_t *)L"Dropping lease %s at %s (%s) (Corr: %hs)");
      v46 = 0;
      v23 = **(__int64 (__fastcall ***)(struct ILicenseIdentityContext *, GUID *, __int64 *))v3;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      v24 = v23(v3, &GUID_fdcb647b_ecff_4acd_9914_35745005c7f9, &v46);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x236,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v24,
          Formatb);
      TickCount64 = GetTickCount64();
      *(_OWORD *)v54 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v54[0]) = 0;
      v56 = 0;
      v57 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 32LL))(v46);
      ThreadTokenScope::ThreadTokenScope((__int64)v44, v26);
      v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 40LL))(v45);
      v28 = (char *)*((_QWORD *)v5 + 6);
      Nexus::InitializeIfNecessary(v28);
      v29 = LicenseProxyService::SendRequestAndWaitForResponse(v5, v65, v28 + 24, v27, v62);
      HttpResponse::operator=(v54, v29);
      HttpResponse::~HttpResponse((HttpResponse *)v65);
      RevertToSelf();
      v30 = GetTickCount64() - TickCount64;
      if ( HttpResponse::StatusCode((HttpResponse *)v54) - 200 > 0x63 )
      {
        v31 = (ContentIdString *)HttpResponse::Body((__int64)v54, (__int64)v53);
        LicenseProxyService::ParseJsonResponse((web::json::value *)&v48, v31);
        v32 = LicenseProxyService::HandleFault(
                (int)v66,
                (int)L"DropLease",
                (int)v4,
                (int)v62,
                (HttpResponse *)v54,
                (__int64)&v48,
                v30,
                (__int64)&v45);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)v32,
          Formatc);
      }
      LogDropLeaseSuccess(v66, v4, (const struct HttpRequest *)v62, (const struct HttpResponse *)v54, v30);
      HttpResponse::~HttpResponse((HttpResponse *)v54);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      HttpRequest::~HttpRequest((HttpRequest *)v62);
    }
    catch ( ... )
    {
      v35 = wil::ResultFromCaughtException(v33);
      v43 = v35;
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x24D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        v36);
      if ( !v41 && v35 == -2147024891 )
      {
        v42 = 0;
        if ( (int)Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot>::As<ILicenseIdentityContextSnapshotRemediation>(
                    &v45,
                    &v42) >= 0
          && (*(int (__fastcall **)(struct ILicenseIdentityContext *))(*(_QWORD *)v42 + 24LL))(v42) >= 0 )
        {
          v41 = 1;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
          v6 = 0;
          v5 = v49;
          v3 = v50;
          v4 = v51;
          continue;
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      }
      v6 = v43;
    }
    break;
  }
  web::json::value::~value((web::json::value *)v47);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  return v6;
}

```

## disassembly

```asm
0x18005d930  push    rbx
0x18005d932  push    rsi
0x18005d933  push    rdi
0x18005d934  push    r12
0x18005d936  push    r13
0x18005d938  push    r14
0x18005d93a  push    r15
0x18005d93c  sub     rsp, 350h
0x18005d943  mov     rax, cs:__security_cookie
0x18005d94a  xor     rax, rsp
0x18005d94d  mov     [rsp+388h+var_48], rax
0x18005d955  mov     r14, r8
0x18005d958  mov     r12, rdx
0x18005d95b  mov     rsi, rcx
0x18005d95e  mov     [rsp+388h+var_300], rcx
0x18005d966  mov     [rsp+388h+var_2F0], rdx
0x18005d96e  mov     [rsp+388h+var_2F8], r8
0x18005d976  xor     edi, edi
0x18005d978  mov     r13d, edi
0x18005d97b  call    ?InitializeIfNeeded@LicenseProxyService@@AEAAXXZ; LicenseProxyService::InitializeIfNeeded(void)
0x18005d980  lea     rcx, [rsi+48h]; this
0x18005d984  lea     rdx, [rsp+388h+var_D8]; char *
0x18005d98c  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18005d991  mov     [rsp+388h+var_330], r14
0x18005d996  lea     rcx, [rsp+388h+var_330]
0x18005d99b  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18005d9a0  nop
0x18005d9a1  lea     rdx, [rsp+388h+var_330]
0x18005d9a6  lea     rcx, [rsp+388h+var_320]
0x18005d9ab  call    ?GetSnapshotFromIdentity@LicenseProxyService@@CA?AV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@AEBV?$ComPtr@UILicenseIdentityContext@@@34@@Z; LicenseProxyService::GetSnapshotFromIdentity(Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &)
0x18005d9b0  nop
0x18005d9b1  lea     rcx, [rsp+388h+var_330]
0x18005d9b6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005d9bb  lea     r8, [rsp+388h+var_320]
0x18005d9c0  mov     rdx, r12
0x18005d9c3  lea     rcx, [rsp+388h+var_310]
0x18005d9c8  call    ?CreateDropLeaseBody@LicenseProxyService@@CA?AVvalue@json@web@@PEBGAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@@Z; LicenseProxyService::CreateDropLeaseBody(ushort const *,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &)
0x18005d9cd  nop
0x18005d9ce  mov     [rsp+388h+var_338], dil
0x18005d9d3  mov     rbx, [rsi+30h]
0x18005d9d7  mov     rcx, rbx; Parameter
0x18005d9da  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005d9df  lea     rdx, [rbx+18h]
0x18005d9e3  cmp     qword ptr [rbx+30h], 7
0x18005d9e8  jbe     short loc_18005D9ED
0x18005d9ea  mov     rdx, [rdx]; unsigned __int16 *
0x18005d9ed  lea     r9, aPost; "POST"
0x18005d9f4  lea     r8, aV70LicensesLea_0; "/v7.0/licenses/leases/remove"
0x18005d9fb  lea     rcx, [rsp+388h+var_238]; this
0x18005da03  call    ??0HttpRequest@@QEAA@PEBG000@Z; HttpRequest::HttpRequest(ushort const *,ushort const *,ushort const *,ushort const *)
0x18005da08  nop
0x18005da09  lea     rdx, [rsp+388h+var_D8]
0x18005da11  lea     rcx, [rsp+388h+var_2E8]
0x18005da19  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005da1e  nop
0x18005da1f  xor     r8d, r8d
0x18005da22  lea     rdx, [rsp+388h+var_2E8]
0x18005da2a  lea     rcx, [rsp+388h+var_2C8]
0x18005da32  call    ?ConvertToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@I@Z; ConvertToWide(std::string const &,uint)
0x18005da37  mov     rbx, rax
0x18005da3a  lea     rdx, aMsCv; "MS-CV"
0x18005da41  lea     rcx, [rsp+388h+var_258]
0x18005da49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005da4e  nop
0x18005da4f  lea     rdx, [rsp+388h+var_258]
0x18005da57  lea     rcx, [rsp+388h+var_140]
0x18005da5f  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005da64  mov     rdx, rbx
0x18005da67  mov     rcx, rax
0x18005da6a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005da6f  nop
0x18005da70  lea     rcx, [rsp+388h+var_258]; this
0x18005da78  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005da7d  nop
0x18005da7e  lea     rcx, [rsp+388h+var_2C8]; this
0x18005da86  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005da8b  nop
0x18005da8c  lea     rcx, [rsp+388h+var_2E8]
0x18005da94  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005da99  lea     rdx, aContentType; "Content-Type"
0x18005daa0  lea     rcx, [rsp+388h+var_2E8]
0x18005daa8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005daad  nop
0x18005daae  lea     rdx, [rsp+388h+var_2E8]
0x18005dab6  lea     rcx, [rsp+388h+var_140]
0x18005dabe  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005dac3  lea     rdx, aApplicationJso; "application/json"
0x18005daca  mov     rcx, rax
0x18005dacd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18005dad2  nop
0x18005dad3  lea     rcx, [rsp+388h+var_2E8]; this
0x18005dadb  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005dae0  lea     rdx, aFrom; "From"
0x18005dae7  lea     rcx, [rsp+388h+var_2E8]
0x18005daef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005daf4  nop
0x18005daf5  lea     rdx, [rsp+388h+var_2E8]
0x18005dafd  lea     rcx, [rsp+388h+var_140]
0x18005db05  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005db0a  lea     rdx, aWindowslicense; "WindowsLicenseManager"
0x18005db11  mov     rcx, rax
0x18005db14  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18005db19  nop
0x18005db1a  lea     rcx, [rsp+388h+var_2E8]; this
0x18005db22  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005db27  lea     rcx, [rsp+388h+var_2C8]
0x18005db2f  call    ?GetOsVersionHeader@LicenseProxyService@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; LicenseProxyService::GetOsVersionHeader(void)
0x18005db34  mov     rbx, rax
0x18005db37  lea     rdx, aUserAgent; "User-Agent"
0x18005db3e  lea     rcx, [rsp+388h+var_2E8]
0x18005db46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005db4b  nop
0x18005db4c  lea     rdx, [rsp+388h+var_2E8]
0x18005db54  lea     rcx, [rsp+388h+var_140]
0x18005db5c  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005db61  mov     rdx, rbx
0x18005db64  mov     rcx, rax
0x18005db67  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005db6c  nop
0x18005db6d  lea     rcx, [rsp+388h+var_2E8]; this
0x18005db75  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005db7a  nop
0x18005db7b  lea     rcx, [rsp+388h+var_2C8]; this
0x18005db83  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005db88  lea     rdx, [rsp+388h+var_2C8]
0x18005db90  lea     rcx, [rsp+388h+var_310]
0x18005db95  call    ?serialize@value@json@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::serialize(void)
0x18005db9a  nop
0x18005db9b  mov     rdx, rax
0x18005db9e  lea     rcx, [rsp+388h+var_238]
0x18005dba6  call    ?SetBody@HttpRequest@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; HttpRequest::SetBody(std::wstring const &,bool)
0x18005dbab  nop
0x18005dbac  lea     rcx, [rsp+388h+var_2C8]; this
0x18005dbb4  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005dbb9  call    ?UseXToken@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::UseXToken(void)
0x18005dbbe  test    al, al
0x18005dbc0  jnz     loc_18005DC61
0x18005dbc6  mov     [rsp+388h+var_330], rdi
0x18005dbcb  lea     rdx, [rsp+388h+var_330]
0x18005dbd0  lea     rcx, [rsp+388h+var_320]
0x18005dbd5  call    ??$As@UILicenseSingleUserIdentityInternal@@@?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILicenseSingleUserIdentityInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot>::As<ILicenseSingleUserIdentityInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILicenseSingleUserIdentityInternal>>)
0x18005dbda  mov     rcx, [rsp+388h]; this
0x18005dbe2  test    eax, eax
0x18005dbe4  jns     short loc_18005DBFA
0x18005dbe6  mov     r9d, eax; char *
0x18005dbe9  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005dbf0  mov     edx, 223h; void *
0x18005dbf5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005dbfa  mov     rcx, [rsp+388h+var_330]
0x18005dbff  mov     rax, [rcx]
0x18005dc02  mov     rax, [rax+18h]
0x18005dc06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc0b  mov     rbx, rax
0x18005dc0e  lea     rdx, aAuthorization; "authorization"
0x18005dc15  lea     rcx, [rsp+388h+var_2E8]
0x18005dc1d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005dc22  nop
0x18005dc23  lea     rdx, [rsp+388h+var_2E8]
0x18005dc2b  lea     rcx, [rsp+388h+var_140]
0x18005dc33  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005dc38  mov     rdx, rbx
0x18005dc3b  mov     rcx, rax
0x18005dc3e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005dc43  nop
0x18005dc44  lea     rcx, [rsp+388h+var_2E8]; this
0x18005dc4c  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005dc51  nop
0x18005dc52  lea     rcx, [rsp+388h+var_330]
0x18005dc57  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005dc5c  jmp     loc_18005DD26
0x18005dc61  lea     rdx, [rsp+388h+var_218]
0x18005dc69  cmp     [rsp+388h+var_200], 7
0x18005dc72  cmova   rdx, [rsp+388h+var_218]
0x18005dc7b  lea     rcx, [rsp+388h+var_258]
0x18005dc83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005dc88  nop
0x18005dc89  mov     rbx, [rsi+30h]
0x18005dc8d  mov     rcx, rbx; Parameter
0x18005dc90  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005dc95  lea     rdx, aPost; "POST"
0x18005dc9c  lea     rcx, [rsp+388h+var_2E8]
0x18005dca4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005dca9  nop
0x18005dcaa  lea     rdx, [rsp+388h+var_2C8]
0x18005dcb2  lea     rcx, [rsp+388h+var_310]
0x18005dcb7  call    ?serialize@value@json@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::serialize(void)
0x18005dcbc  nop
0x18005dcbd  lea     r9, [rbx+18h]
0x18005dcc1  lea     rcx, [rsp+388h+var_320]
0x18005dcc6  mov     qword ptr [rsp+388h+var_358], rcx
0x18005dccb  lea     rcx, asc_1800D00D4; "*"
0x18005dcd2  mov     [rsp+388h+var_360], rcx
0x18005dcd7  lea     rcx, [rsp+388h+var_258]
0x18005dcdf  mov     [rsp+388h+Format], rcx
0x18005dce4  lea     r8, [rsp+388h+var_2E8]
0x18005dcec  mov     rdx, rax
0x18005dcef  lea     rcx, [rsp+388h+var_238]
0x18005dcf7  call    ?AddXTokenAndSignRequest@LicenseProxyService@@CAXAEAVHttpRequest@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111PEBGAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@@Z; LicenseProxyService::AddXTokenAndSignRequest(HttpRequest &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,ushort const *,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &)
0x18005dcfc  nop
0x18005dcfd  lea     rcx, [rsp+388h+var_2C8]; this
0x18005dd05  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005dd0a  nop
0x18005dd0b  lea     rcx, [rsp+388h+var_2E8]; this
0x18005dd13  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005dd18  nop
0x18005dd19  lea     rcx, [rsp+388h+var_258]; this
0x18005dd21  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005dd26  mov     rbx, [rsi+30h]
0x18005dd2a  mov     rcx, rbx; Parameter
0x18005dd2d  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005dd32  lea     rcx, [rbx+18h]
0x18005dd36  cmp     qword ptr [rbx+30h], 7
0x18005dd3b  jbe     short loc_18005DD40
0x18005dd3d  mov     rcx, [rcx]
0x18005dd40  lea     rax, [rsp+388h+var_218]
0x18005dd48  cmp     [rsp+388h+var_200], 7
0x18005dd51  cmova   rax, [rsp+388h+var_218]
0x18005dd5a  lea     rdx, [rsp+388h+var_D8]
0x18005dd62  mov     [rsp+388h+var_348], rdx
0x18005dd67  mov     [rsp+388h+var_350], rcx
0x18005dd6c  mov     qword ptr [rsp+388h+var_358], rax
0x18005dd71  mov     [rsp+388h+var_360], r12
0x18005dd76  lea     rax, aDroppingLeaseS; "Dropping lease %s at %s (%s) (Corr: %hs"...
0x18005dd7d  mov     [rsp+388h+Format], rax; int
0x18005dd82  lea     r9, aLicenseproxyse_9; "LicenseProxyService::DropLeaseWithId"
0x18005dd89  mov     r8d, 233h; unsigned int
0x18005dd8f  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005dd96  mov     ecx, 3; unsigned int
0x18005dd9b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005dda0  mov     [rsp+388h+var_318], rdi
0x18005dda5  mov     rax, [r14]
0x18005dda8  mov     rbx, [rax]
0x18005ddab  lea     rcx, [rsp+388h+var_318]
0x18005ddb0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005ddb5  lea     r8, [rsp+388h+var_318]
0x18005ddba  lea     rdx, _GUID_fdcb647b_ecff_4acd_9914_35745005c7f9
0x18005ddc1  mov     rcx, r14
0x18005ddc4  mov     rax, rbx
0x18005ddc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ddcc  mov     rcx, [rsp+388h]; this
0x18005ddd4  test    eax, eax
0x18005ddd6  jns     short loc_18005DDEC
0x18005ddd8  mov     r9d, eax; char *
0x18005dddb  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005dde2  mov     edx, 236h; void *
0x18005dde7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ddec  call    cs:__imp_GetTickCount64
0x18005ddf2  mov     r15, rax
0x18005ddf5  xorps   xmm0, xmm0
0x18005ddf8  movups  xmmword ptr [rsp+388h+var_2A8], xmm0
0x18005de00  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005de08  movdqa  [rsp+388h+var_298], xmm1
0x18005de11  mov     word ptr [rsp+388h+var_2A8], di
0x18005de19  mov     [rsp+388h+var_288], edi
0x18005de20  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x18005de27  mov     [rsp+388h+var_280], rax
0x18005de2f  mov     [rsp+388h+var_278], rdi
0x18005de37  mov     [rsp+388h+var_270], rdi
0x18005de3f  mov     [rsp+388h+var_268], rdi
0x18005de47  mov     rcx, [rsp+388h+var_318]
0x18005de4c  mov     rax, [rcx]
0x18005de4f  mov     rax, [rax+20h]
0x18005de53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de58  mov     rdx, rax
0x18005de5b  lea     rcx, [rsp+388h+var_324]
0x18005de60  call    ??0ThreadTokenScope@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; ThreadTokenScope::ThreadTokenScope(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18005de65  nop
0x18005de66  mov     rcx, [rsp+388h+var_320]
0x18005de6b  mov     rax, [rcx]
0x18005de6e  mov     rax, [rax+28h]
0x18005de72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de77  mov     r14, rax
0x18005de7a  mov     rbx, [rsi+30h]
0x18005de7e  mov     rcx, rbx; Parameter
0x18005de81  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005de86  lea     r8, [rbx+18h]
0x18005de8a  lea     rax, [rsp+388h+var_238]
0x18005de92  mov     [rsp+388h+Format], rax
0x18005de97  mov     r9, r14
0x18005de9a  lea     rdx, [rsp+388h+var_128]
0x18005dea2  mov     rcx, rsi
0x18005dea5  call    ?SendRequestAndWaitForResponse@LicenseProxyService@@AEAA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z; LicenseProxyService::SendRequestAndWaitForResponse(std::wstring const &,ProxySettings const &,HttpRequest &)
0x18005deaa  mov     rdx, rax
0x18005dead  lea     rcx, [rsp+388h+var_2A8]
0x18005deb5  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x18005deba  lea     rcx, [rsp+388h+var_128]; this
0x18005dec2  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x18005dec7  nop
0x18005dec8  call    cs:__imp_RevertToSelf
0x18005dece  call    cs:__imp_GetTickCount64
0x18005ded4  mov     rbx, rax
0x18005ded7  lea     rcx, [rsp+388h+var_2A8]; this
0x18005dedf  call    ?StatusCode@HttpResponse@@QEBAKXZ; HttpResponse::StatusCode(void)
0x18005dee4  add     eax, 0FFFFFF38h
0x18005dee9  cmp     eax, 63h ; 'c'
0x18005deec  setnbe  al
0x18005deef  sub     rbx, r15
0x18005def2  test    al, al
0x18005def4  jz      loc_18005DF85
0x18005defa  lea     rdx, [rsp+388h+var_2C8]
  ... truncated ...
```

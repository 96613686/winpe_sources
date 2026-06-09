# LicenseProxyService::RegisterUrisForWns(ushort const *,ushort const * *,uint,ILicenseIdentityContext *,ushort * * *,uint *)

- ea: `0x18005b840`
- end: `0x18005bff7`
- name: `?RegisterUrisForWns@LicenseProxyService@@UEAAJPEBGPEAPEBGIPEAUILicenseIdentityContext@@PEAPEAPEAGPEAI@Z`
- size: `1975`
- prototype: `__int64 __fastcall(LicenseProxyService *__hidden this, const unsigned __int16 *, const unsigned __int16 **, unsigned int, struct ILicenseIdentityContext *, unsigned __int16 ***, unsigned int *)`
- caller_count: `0`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

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
- `0x18005b840`
- `0x18005c038`
- `0x18005c1ec`
- `0x18005d6e8`
- `0x18005eeb0`
- `0x18005f014`
- `0x180071e78`
- `0x180075e60`
- `0x18007e710`
- `0x180099f50`
- `0x18009c2d0`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bd42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005be4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bd42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005be4a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005be1e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005be1e`

## string_xrefs

- `0x18005ba12`: `application/json`
- `0x18005bcd8`: `LicenseProxyService::RegisterUrisForWns`
- `0x18005bf1c`: `RegisterUrisForWns`
- `0x18005ba86`: `User-Agent`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=2
__int64 __fastcall LicenseProxyService::RegisterUrisForWns(
        PVOID *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        struct ILicenseIdentityContext *a5,
        unsigned __int16 ***a6,
        unsigned int *a7)
{
  unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 OsVersionHeader; // rbx
  __int64 v17; // rax
  const WCHAR *v18; // rdx
  WinStoreAuth::AuthenticationInternal *v19; // rcx
  int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rax
  _QWORD *v23; // rdx
  PVOID v24; // rbx
  const WCHAR *v25; // rax
  __int64 (__fastcall *v26)(struct ILicenseIdentityContext *, GUID *, __int64 *); // rbx
  int v27; // eax
  ULONGLONG TickCount64; // r14
  __int64 v29; // rax
  __int64 v30; // rdi
  char *v31; // rbx
  __int64 v32; // rax
  ContentIdString *v33; // rax
  unsigned __int64 v34; // rbx
  const struct HttpResponse *v35; // rdx
  const char *v36; // rcx
  unsigned int v37; // ebx
  wchar_t *Format; // [rsp+20h] [rbp-388h]
  int Formata; // [rsp+20h] [rbp-388h]
  int Formatb; // [rsp+20h] [rbp-388h]
  struct ILicenseIdentityContext *v43; // [rsp+58h] [rbp-350h] BYREF
  _BYTE v44[8]; // [rsp+60h] [rbp-348h] BYREF
  unsigned int v45; // [rsp+68h] [rbp-340h]
  __int64 v46; // [rsp+70h] [rbp-338h] BYREF
  __int64 v47; // [rsp+78h] [rbp-330h] BYREF
  __int64 v48; // [rsp+80h] [rbp-328h] BYREF
  _BYTE v49[8]; // [rsp+88h] [rbp-320h] BYREF
  unsigned int *v50; // [rsp+90h] [rbp-318h]
  PVOID *v51; // [rsp+98h] [rbp-310h]
  const unsigned __int16 *v52; // [rsp+A0h] [rbp-308h]
  struct ILicenseIdentityContext *v53; // [rsp+A8h] [rbp-300h]
  unsigned __int16 ***v54; // [rsp+B0h] [rbp-2F8h]
  _QWORD v55[4]; // [rsp+B8h] [rbp-2F0h] BYREF
  _BYTE v56[40]; // [rsp+D8h] [rbp-2D0h] BYREF
  _OWORD v57[2]; // [rsp+100h] [rbp-2A8h] BYREF
  int v58; // [rsp+120h] [rbp-288h]
  void **v59; // [rsp+128h] [rbp-280h]
  __int64 v60; // [rsp+130h] [rbp-278h]
  __int64 v61; // [rsp+138h] [rbp-270h]
  __int64 v62; // [rsp+140h] [rbp-268h]
  _BYTE v63[32]; // [rsp+150h] [rbp-258h] BYREF
  int v64[8]; // [rsp+170h] [rbp-238h] BYREF
  _QWORD v65[27]; // [rsp+190h] [rbp-218h] BYREF
  _BYTE v66[24]; // [rsp+268h] [rbp-140h] BYREF
  char v67[80]; // [rsp+280h] [rbp-128h] BYREF
  char v68[144]; // [rsp+2D0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v51 = this;
  v52 = a2;
  v45 = a4;
  v53 = a5;
  v54 = a6;
  v50 = a7;
  *a6 = 0;
  *a7 = 0;
  LicenseProxyService::InitializeIfNeeded((LicenseProxyService *)this);
  TraceLoggingCorrelationVector::Increment((TraceLoggingCorrelationVector *)(this + 9), v68);
  v43 = a5;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v43);
  LicenseProxyService::GetSnapshotFromIdentity(&v46, &v43);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  LicenseProxyService::CreateWnsRegistrationBody(v49, a2, a3, a4);
  v10 = (unsigned __int16 *)this[6];
  Nexus::InitializeIfNecessary(v10);
  v11 = v10 + 12;
  if ( *((_QWORD *)v10 + 6) > 7u )
    v11 = *(const unsigned __int16 **)v11;
  HttpRequest::HttpRequest((HttpRequest *)v64, v11, L"/v7.0/licenses/leases/callback", L"POST", Format);
  std::string::string(v55, v68);
  v12 = ConvertToWide(v56, v55, 0);
  std::wstring::wstring(v63, L"MS-CV");
  v13 = std::map<std::wstring,std::wstring>::operator[](v66, v63);
  std::wstring::operator=(v13, v12);
  ContentIdString::~ContentIdString((ContentIdString *)v63);
  ContentIdString::~ContentIdString((ContentIdString *)v56);
  std::string::_Tidy_deallocate(v55);
  std::wstring::wstring(v55, L"Content-Type");
  v14 = std::map<std::wstring,std::wstring>::operator[](v66, v55);
  std::wstring::assign(v14, L"application/json");
  ContentIdString::~ContentIdString((ContentIdString *)v55);
  std::wstring::wstring(v55, L"From");
  v15 = std::map<std::wstring,std::wstring>::operator[](v66, v55);
  std::wstring::assign(v15, L"WindowsLicenseManager");
  ContentIdString::~ContentIdString((ContentIdString *)v55);
  OsVersionHeader = LicenseProxyService::GetOsVersionHeader(v56);
  std::wstring::wstring(v55, L"User-Agent");
  v17 = std::map<std::wstring,std::wstring>::operator[](v66, v55);
  std::wstring::operator=(v17, OsVersionHeader);
  ContentIdString::~ContentIdString((ContentIdString *)v55);
  ContentIdString::~ContentIdString((ContentIdString *)v56);
  v18 = (const WCHAR *)web::json::value::serialize(v49, v56);
  HttpRequest::SetBody((__int64)v64, v18);
  ContentIdString::~ContentIdString((ContentIdString *)v56);
  if ( WinStoreAuth::AuthenticationInternal::UseXToken(v19) )
  {
    v23 = v65;
    if ( v65[3] > 7u )
      v23 = (_QWORD *)v65[0];
    std::wstring::wstring(v63, v23);
    v24 = this[6];
    Nexus::InitializeIfNecessary(v24);
    std::wstring::wstring(v55, L"POST");
    v25 = (const WCHAR *)web::json::value::serialize(v49, v56);
    LicenseProxyService::AddXTokenAndSignRequest((__int64)v64, v25, v55, (__int64)v24 + 24, (__int64)v63, 0, &v46);
    ContentIdString::~ContentIdString((ContentIdString *)v56);
    ContentIdString::~ContentIdString((ContentIdString *)v55);
    ContentIdString::~ContentIdString((ContentIdString *)v63);
  }
  else
  {
    v43 = 0;
    v20 = Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot>::As<ILicenseSingleUserIdentityInternal>(&v46, &v43);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x421,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v20,
        Formata);
    v21 = (*(__int64 (__fastcall **)(struct ILicenseIdentityContext *))(*(_QWORD *)v43 + 24LL))(v43);
    std::wstring::wstring(v55, L"authorization");
    v22 = std::map<std::wstring,std::wstring>::operator[](v66, v55);
    std::wstring::operator=(v22, v21);
    ContentIdString::~ContentIdString((ContentIdString *)v55);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  }
  Nexus::InitializeIfNecessary(this[6]);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
    0x431u,
    "LicenseProxyService::RegisterUrisForWns",
    (wchar_t *)L"Registering %d leases for WNS channel %s at %s (%s) (Corr: %hs)");
  v47 = 0;
  v26 = **(__int64 (__fastcall ***)(struct ILicenseIdentityContext *, GUID *, __int64 *))a5;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  v27 = v26(a5, &GUID_fdcb647b_ecff_4acd_9914_35745005c7f9, &v47);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v27,
      Formatb);
  TickCount64 = GetTickCount64();
  v57[0] = 0;
  v57[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v57[0]) = 0;
  v58 = 0;
  v59 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 32LL))(v47);
  ThreadTokenScope::ThreadTokenScope((__int64)v44, v29);
  v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 40LL))(v46);
  v31 = (char *)this[6];
  Nexus::InitializeIfNecessary(v31);
  v32 = LicenseProxyService::SendRequestAndWaitForResponse(this, v67, v31 + 24, v30, v64);
  HttpResponse::operator=(v57, v32);
  HttpResponse::~HttpResponse((HttpResponse *)v67);
  RevertToSelf();
  v33 = (ContentIdString *)HttpResponse::Body((__int64)v57, (__int64)v56);
  LicenseProxyService::ParseJsonResponse((web::json::value *)&v48, v33);
  v34 = GetTickCount64() - TickCount64;
  if ( HttpResponse::StatusCode((HttpResponse *)v57) - 200 > 0x63 )
  {
    v37 = LicenseProxyService::HandleFault(
            (int)v68,
            (int)L"RegisterUrisForWns",
            (int)a2,
            (int)v64,
            (HttpResponse *)v57,
            (__int64)&v48,
            v34,
            (__int64)&v46);
    web::json::value::~value((web::json::value *)&v48);
    HttpResponse::~HttpResponse((HttpResponse *)v57);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    HttpRequest::~HttpRequest((HttpRequest *)v64);
    web::json::value::~value((web::json::value *)v49);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    return v37;
  }
  else
  {
    LogWnsCallbackRegistrationSuccess(
      v68,
      a4,
      a2,
      (const struct HttpRequest *)v64,
      (const struct HttpResponse *)v57,
      v34);
    LicenseProxyService::HandleWnsRegistrationResponse(v36, v35, (const struct web::json::value *)&v48, a6, v50);
    web::json::value::~value((web::json::value *)&v48);
    HttpResponse::~HttpResponse((HttpResponse *)v57);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    HttpRequest::~HttpRequest((HttpRequest *)v64);
    web::json::value::~value((web::json::value *)v49);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    return 0;
  }
}

```

## disassembly

```asm
0x18005b840  push    rbx
0x18005b842  push    rsi
0x18005b843  push    rdi
0x18005b844  push    r12
0x18005b846  push    r13
0x18005b848  push    r14
0x18005b84a  push    r15
0x18005b84c  sub     rsp, 370h
0x18005b853  mov     rax, cs:__security_cookie
0x18005b85a  xor     rax, rsp
0x18005b85d  mov     [rsp+3A8h+var_48], rax
0x18005b865  mov     eax, r9d
0x18005b868  mov     [rsp+3A8h+var_354], eax
0x18005b86c  mov     rbx, r8
0x18005b86f  mov     r15, rdx
0x18005b872  mov     rsi, rcx
0x18005b875  mov     [rsp+3A8h+var_310], rcx
0x18005b87d  mov     [rsp+3A8h+var_308], rdx
0x18005b885  mov     [rsp+3A8h+var_340], eax
0x18005b889  mov     r14, [rsp+3A8h+arg_20]
0x18005b891  mov     [rsp+3A8h+var_300], r14
0x18005b899  mov     r13, [rsp+3A8h+arg_28]
0x18005b8a1  mov     [rsp+3A8h+var_2F8], r13
0x18005b8a9  mov     rax, [rsp+3A8h+arg_30]
0x18005b8b1  mov     [rsp+3A8h+var_318], rax
0x18005b8b9  xor     edi, edi
0x18005b8bb  mov     [r13+0], rdi
0x18005b8bf  mov     [rax], edi
0x18005b8c1  mov     r12d, edi
0x18005b8c4  call    ?InitializeIfNeeded@LicenseProxyService@@AEAAXXZ; LicenseProxyService::InitializeIfNeeded(void)
0x18005b8c9  lea     rcx, [rsi+48h]; this
0x18005b8cd  lea     rdx, [rsp+3A8h+var_D8]; char *
0x18005b8d5  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18005b8da  mov     [rsp+3A8h+var_350], r14
0x18005b8df  lea     rcx, [rsp+3A8h+var_350]
0x18005b8e4  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18005b8e9  nop
0x18005b8ea  lea     rdx, [rsp+3A8h+var_350]
0x18005b8ef  lea     rcx, [rsp+3A8h+var_338]
0x18005b8f4  call    ?GetSnapshotFromIdentity@LicenseProxyService@@CA?AV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@AEBV?$ComPtr@UILicenseIdentityContext@@@34@@Z; LicenseProxyService::GetSnapshotFromIdentity(Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &)
0x18005b8f9  nop
0x18005b8fa  lea     rcx, [rsp+3A8h+var_350]
0x18005b8ff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005b904  mov     r9d, [rsp+3A8h+var_354]
0x18005b909  mov     r8, rbx
0x18005b90c  mov     rdx, r15
0x18005b90f  lea     rcx, [rsp+3A8h+var_320]
0x18005b917  call    ?CreateWnsRegistrationBody@LicenseProxyService@@CA?AVvalue@json@web@@PEBGPEAPEBGI@Z; LicenseProxyService::CreateWnsRegistrationBody(ushort const *,ushort const * *,uint)
0x18005b91c  nop
0x18005b91d  mov     [rsp+3A8h+var_358], dil
0x18005b922  mov     rbx, [rsi+30h]
0x18005b926  mov     rcx, rbx; Parameter
0x18005b929  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005b92e  lea     rdx, [rbx+18h]
0x18005b932  cmp     qword ptr [rbx+30h], 7
0x18005b937  jbe     short loc_18005B93C
0x18005b939  mov     rdx, [rdx]; unsigned __int16 *
0x18005b93c  lea     r9, aPost; "POST"
0x18005b943  lea     r8, aV70LicensesLea; "/v7.0/licenses/leases/callback"
0x18005b94a  lea     rcx, [rsp+3A8h+var_238]; this
0x18005b952  call    ??0HttpRequest@@QEAA@PEBG000@Z; HttpRequest::HttpRequest(ushort const *,ushort const *,ushort const *,ushort const *)
0x18005b957  nop
0x18005b958  lea     rdx, [rsp+3A8h+var_D8]
0x18005b960  lea     rcx, [rsp+3A8h+var_2F0]
0x18005b968  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005b96d  nop
0x18005b96e  xor     r8d, r8d
0x18005b971  lea     rdx, [rsp+3A8h+var_2F0]
0x18005b979  lea     rcx, [rsp+3A8h+var_2D0]
0x18005b981  call    ?ConvertToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@I@Z; ConvertToWide(std::string const &,uint)
0x18005b986  mov     rbx, rax
0x18005b989  lea     rdx, aMsCv; "MS-CV"
0x18005b990  lea     rcx, [rsp+3A8h+var_258]
0x18005b998  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005b99d  nop
0x18005b99e  lea     rdx, [rsp+3A8h+var_258]
0x18005b9a6  lea     rcx, [rsp+3A8h+var_140]
0x18005b9ae  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005b9b3  mov     rdx, rbx
0x18005b9b6  mov     rcx, rax
0x18005b9b9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005b9be  nop
0x18005b9bf  lea     rcx, [rsp+3A8h+var_258]; this
0x18005b9c7  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005b9cc  nop
0x18005b9cd  lea     rcx, [rsp+3A8h+var_2D0]; this
0x18005b9d5  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005b9da  nop
0x18005b9db  lea     rcx, [rsp+3A8h+var_2F0]
0x18005b9e3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005b9e8  lea     rdx, aContentType; "Content-Type"
0x18005b9ef  lea     rcx, [rsp+3A8h+var_2F0]
0x18005b9f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005b9fc  nop
0x18005b9fd  lea     rdx, [rsp+3A8h+var_2F0]
0x18005ba05  lea     rcx, [rsp+3A8h+var_140]
0x18005ba0d  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005ba12  lea     rdx, aApplicationJso; "application/json"
0x18005ba19  mov     rcx, rax
0x18005ba1c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18005ba21  nop
0x18005ba22  lea     rcx, [rsp+3A8h+var_2F0]; this
0x18005ba2a  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005ba2f  lea     rdx, aFrom; "From"
0x18005ba36  lea     rcx, [rsp+3A8h+var_2F0]
0x18005ba3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ba43  nop
0x18005ba44  lea     rdx, [rsp+3A8h+var_2F0]
0x18005ba4c  lea     rcx, [rsp+3A8h+var_140]
0x18005ba54  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005ba59  lea     rdx, aWindowslicense; "WindowsLicenseManager"
0x18005ba60  mov     rcx, rax
0x18005ba63  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18005ba68  nop
0x18005ba69  lea     rcx, [rsp+3A8h+var_2F0]; this
0x18005ba71  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005ba76  lea     rcx, [rsp+3A8h+var_2D0]
0x18005ba7e  call    ?GetOsVersionHeader@LicenseProxyService@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; LicenseProxyService::GetOsVersionHeader(void)
0x18005ba83  mov     rbx, rax
0x18005ba86  lea     rdx, aUserAgent; "User-Agent"
0x18005ba8d  lea     rcx, [rsp+3A8h+var_2F0]
0x18005ba95  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ba9a  nop
0x18005ba9b  lea     rdx, [rsp+3A8h+var_2F0]
0x18005baa3  lea     rcx, [rsp+3A8h+var_140]
0x18005baab  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005bab0  mov     rdx, rbx
0x18005bab3  mov     rcx, rax
0x18005bab6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005babb  nop
0x18005babc  lea     rcx, [rsp+3A8h+var_2F0]; this
0x18005bac4  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005bac9  nop
0x18005baca  lea     rcx, [rsp+3A8h+var_2D0]; this
0x18005bad2  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005bad7  lea     rdx, [rsp+3A8h+var_2D0]
0x18005badf  lea     rcx, [rsp+3A8h+var_320]
0x18005bae7  call    ?serialize@value@json@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::serialize(void)
0x18005baec  nop
0x18005baed  mov     rdx, rax
0x18005baf0  lea     rcx, [rsp+3A8h+var_238]
0x18005baf8  call    ?SetBody@HttpRequest@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; HttpRequest::SetBody(std::wstring const &,bool)
0x18005bafd  nop
0x18005bafe  lea     rcx, [rsp+3A8h+var_2D0]; this
0x18005bb06  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005bb0b  call    ?UseXToken@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::UseXToken(void)
0x18005bb10  test    al, al
0x18005bb12  jnz     loc_18005BBB3
0x18005bb18  mov     [rsp+3A8h+var_350], rdi
0x18005bb1d  lea     rdx, [rsp+3A8h+var_350]
0x18005bb22  lea     rcx, [rsp+3A8h+var_338]
0x18005bb27  call    ??$As@UILicenseSingleUserIdentityInternal@@@?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILicenseSingleUserIdentityInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot>::As<ILicenseSingleUserIdentityInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILicenseSingleUserIdentityInternal>>)
0x18005bb2c  mov     rcx, [rsp+3A8h]; this
0x18005bb34  test    eax, eax
0x18005bb36  jns     short loc_18005BB4C
0x18005bb38  mov     r9d, eax; char *
0x18005bb3b  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005bb42  mov     edx, 421h; void *
0x18005bb47  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bb4c  mov     rcx, [rsp+3A8h+var_350]
0x18005bb51  mov     rax, [rcx]
0x18005bb54  mov     rax, [rax+18h]
0x18005bb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb5d  mov     rbx, rax
0x18005bb60  lea     rdx, aAuthorization; "authorization"
0x18005bb67  lea     rcx, [rsp+3A8h+var_2F0]
0x18005bb6f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bb74  nop
0x18005bb75  lea     rdx, [rsp+3A8h+var_2F0]
0x18005bb7d  lea     rcx, [rsp+3A8h+var_140]
0x18005bb85  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18005bb8a  mov     rdx, rbx
0x18005bb8d  mov     rcx, rax
0x18005bb90  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005bb95  nop
0x18005bb96  lea     rcx, [rsp+3A8h+var_2F0]; this
0x18005bb9e  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005bba3  nop
0x18005bba4  lea     rcx, [rsp+3A8h+var_350]
0x18005bba9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005bbae  jmp     loc_18005BC74
0x18005bbb3  lea     rdx, [rsp+3A8h+var_218]
0x18005bbbb  cmp     [rsp+3A8h+var_200], 7
0x18005bbc4  cmova   rdx, [rsp+3A8h+var_218]
0x18005bbcd  lea     rcx, [rsp+3A8h+var_258]
0x18005bbd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bbda  nop
0x18005bbdb  mov     rbx, [rsi+30h]
0x18005bbdf  mov     rcx, rbx; Parameter
0x18005bbe2  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005bbe7  lea     rdx, aPost; "POST"
0x18005bbee  lea     rcx, [rsp+3A8h+var_2F0]
0x18005bbf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bbfb  nop
0x18005bbfc  lea     rdx, [rsp+3A8h+var_2D0]
0x18005bc04  lea     rcx, [rsp+3A8h+var_320]
0x18005bc0c  call    ?serialize@value@json@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::serialize(void)
0x18005bc11  nop
0x18005bc12  lea     r9, [rbx+18h]
0x18005bc16  lea     rcx, [rsp+3A8h+var_338]
0x18005bc1b  mov     qword ptr [rsp+3A8h+var_378], rcx
0x18005bc20  mov     [rsp+3A8h+var_380], rdi
0x18005bc25  lea     rcx, [rsp+3A8h+var_258]
0x18005bc2d  mov     [rsp+3A8h+Format], rcx
0x18005bc32  lea     r8, [rsp+3A8h+var_2F0]
0x18005bc3a  mov     rdx, rax
0x18005bc3d  lea     rcx, [rsp+3A8h+var_238]
0x18005bc45  call    ?AddXTokenAndSignRequest@LicenseProxyService@@CAXAEAVHttpRequest@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111PEBGAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@@Z; LicenseProxyService::AddXTokenAndSignRequest(HttpRequest &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,ushort const *,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &)
0x18005bc4a  nop
0x18005bc4b  lea     rcx, [rsp+3A8h+var_2D0]; this
0x18005bc53  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005bc58  nop
0x18005bc59  lea     rcx, [rsp+3A8h+var_2F0]; this
0x18005bc61  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005bc66  nop
0x18005bc67  lea     rcx, [rsp+3A8h+var_258]; this
0x18005bc6f  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18005bc74  mov     rbx, [rsi+30h]
0x18005bc78  mov     rcx, rbx; Parameter
0x18005bc7b  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005bc80  lea     rcx, [rbx+18h]
0x18005bc84  cmp     qword ptr [rbx+30h], 7
0x18005bc89  jbe     short loc_18005BC8E
0x18005bc8b  mov     rcx, [rcx]
0x18005bc8e  lea     rax, [rsp+3A8h+var_218]
0x18005bc96  cmp     [rsp+3A8h+var_200], 7
0x18005bc9f  cmova   rax, [rsp+3A8h+var_218]
0x18005bca8  lea     rdx, [rsp+3A8h+var_D8]
0x18005bcb0  mov     [rsp+3A8h+var_360], rdx
0x18005bcb5  mov     [rsp+3A8h+var_368], rcx
0x18005bcba  mov     [rsp+3A8h+var_370], rax
0x18005bcbf  mov     qword ptr [rsp+3A8h+var_378], r15
0x18005bcc4  mov     eax, [rsp+3A8h+var_354]
0x18005bcc8  mov     dword ptr [rsp+3A8h+var_380], eax
0x18005bccc  lea     rax, aRegisteringDLe; "Registering %d leases for WNS channel %"...
0x18005bcd3  mov     [rsp+3A8h+Format], rax; int
0x18005bcd8  lea     r9, aLicenseproxyse_4; "LicenseProxyService::RegisterUrisForWns"
0x18005bcdf  mov     r8d, 431h; unsigned int
0x18005bce5  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005bcec  mov     ecx, 3; unsigned int
0x18005bcf1  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005bcf6  mov     [rsp+3A8h+var_330], rdi
0x18005bcfb  mov     rax, [r14]
0x18005bcfe  mov     rbx, [rax]
0x18005bd01  lea     rcx, [rsp+3A8h+var_330]
0x18005bd06  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005bd0b  lea     r8, [rsp+3A8h+var_330]
0x18005bd10  lea     rdx, _GUID_fdcb647b_ecff_4acd_9914_35745005c7f9
0x18005bd17  mov     rcx, r14
0x18005bd1a  mov     rax, rbx
0x18005bd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd22  mov     rcx, [rsp+3A8h]; this
0x18005bd2a  test    eax, eax
0x18005bd2c  jns     short loc_18005BD42
0x18005bd2e  mov     r9d, eax; char *
0x18005bd31  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005bd38  mov     edx, 434h; void *
0x18005bd3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bd42  call    cs:__imp_GetTickCount64
0x18005bd48  mov     r14, rax
0x18005bd4b  xorps   xmm0, xmm0
0x18005bd4e  movups  [rsp+3A8h+var_2A8], xmm0
0x18005bd56  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005bd5e  movdqa  [rsp+3A8h+var_298], xmm1
0x18005bd67  mov     word ptr [rsp+3A8h+var_2A8], di
0x18005bd6f  mov     [rsp+3A8h+var_288], edi
0x18005bd76  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x18005bd7d  mov     [rsp+3A8h+var_280], rax
0x18005bd85  mov     [rsp+3A8h+var_278], rdi
0x18005bd8d  mov     [rsp+3A8h+var_270], rdi
0x18005bd95  mov     [rsp+3A8h+var_268], rdi
0x18005bd9d  mov     rcx, [rsp+3A8h+var_330]
0x18005bda2  mov     rax, [rcx]
0x18005bda5  mov     rax, [rax+20h]
0x18005bda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdae  mov     rdx, rax
0x18005bdb1  lea     rcx, [rsp+3A8h+var_348]
0x18005bdb6  call    ??0ThreadTokenScope@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; ThreadTokenScope::ThreadTokenScope(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18005bdbb  nop
0x18005bdbc  mov     rcx, [rsp+3A8h+var_338]
0x18005bdc1  mov     rax, [rcx]
0x18005bdc4  mov     rax, [rax+28h]
0x18005bdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdcd  mov     rdi, rax
0x18005bdd0  mov     rbx, [rsi+30h]
0x18005bdd4  mov     rcx, rbx; Parameter
0x18005bdd7  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18005bddc  lea     r8, [rbx+18h]
0x18005bde0  lea     rax, [rsp+3A8h+var_238]
0x18005bde8  mov     [rsp+3A8h+Format], rax
0x18005bded  mov     r9, rdi
0x18005bdf0  lea     rdx, [rsp+3A8h+var_128]
0x18005bdf8  mov     rcx, rsi
0x18005bdfb  call    ?SendRequestAndWaitForResponse@LicenseProxyService@@AEAA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z; LicenseProxyService::SendRequestAndWaitForResponse(std::wstring const &,ProxySettings const &,HttpRequest &)
0x18005be00  mov     rdx, rax
0x18005be03  lea     rcx, [rsp+3A8h+var_2A8]
0x18005be0b  call    ??4HttpResponse@@QEAAAEAV0@$$QEAV0@@Z; HttpResponse::operator=(HttpResponse &&)
0x18005be10  lea     rcx, [rsp+3A8h+var_128]; this
0x18005be18  call    ??1HttpResponse@@QEAA@XZ; HttpResponse::~HttpResponse(void)
0x18005be1d  nop
  ... truncated ...
```

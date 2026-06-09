# LicenseProxyService::AddXTokenAndSignRequest(HttpRequest &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &)

- ea: `0x18005815c`
- end: `0x1800588ab`
- name: `?AddXTokenAndSignRequest@LicenseProxyService@@CAXAEAVHttpRequest@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111PEBGAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@@Z`
- size: `1871`
- prototype: ``
- caller_count: `6`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000781c`
- `0x18005abc0`
- `0x18005b840`
- `0x18005d47c`
- `0x18005d930`
- `0x18005e260`

## callees

- `0x180004738`
- `0x1800061e0`
- `0x18000a110`
- `0x18000a200`
- `0x18000b7fc`
- `0x180012dc0`
- `0x180013b50`
- `0x180017230`
- `0x180026914`
- `0x180028528`
- `0x18002aae8`
- `0x18003b570`
- `0x18003dbc0`
- `0x1800454b8`
- `0x180056dc4`
- `0x18005815c`
- `0x1800593bc`
- `0x18005c1ec`
- `0x1800629dc`
- `0x180062a40`
- `0x180075e60`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058307`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180058307`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800583e5`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800583e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005845a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800587d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800587fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005845a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800587d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800587fe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058286`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058286`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058237`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058237`

## string_xrefs

- `0x180058547`: `LicenseProxyService::AddXTokenAndSignRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall LicenseProxyService::AddXTokenAndSignRequest(
        __int64 a1,
        const WCHAR *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        const WCHAR *lpString2,
        _QWORD *a7)
{
  int v11; // eax
  HRESULT Instance; // eax
  HRESULT v13; // eax
  __int64 v14; // r13
  bool v15; // al
  HRESULT (__stdcall *v16)(IUnknown *, const IID *const, void **); // r11
  int *v17; // rdx
  int v18; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v20; // eax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  int *v22; // rdx
  int v23; // eax
  ULONG (__stdcall *v24)(IUnknown *); // r15
  int *v25; // rdx
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  int (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  ULONG (__stdcall *AddRef)(IUnknown *); // r15
  int *v33; // rdx
  int v34; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  int ppvd; // [rsp+20h] [rbp-E0h]
  int ppve; // [rsp+20h] [rbp-E0h]
  int ppvf; // [rsp+20h] [rbp-E0h]
  LPVOID v42; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  IUnknown *pProxy; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  int (__fastcall ****v51)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-50h]
  _BYTE v52[16]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v53[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v54[6]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v55; // [rsp+100h] [rbp+0h]
  _QWORD Src[3]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v57[32]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v51 = (int (__fastcall ****)(_QWORD, GUID *, __int64 *))a7;
  v50 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a7 + 48LL))(*a7);
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v50);
  v49 = 0;
  v11 = Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::As<ILicenseIdentityContext>(&v50, &v49);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x62C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  ImpersonationScope<LicenseIdentityContextTraits>::ImpersonationScope<LicenseIdentityContextTraits>(v52, v49);
  pProxy = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
  Instance = CoCreateInstance(
               &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
               0,
               0x17u,
               &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
               (LPVOID *)&pProxy);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x630,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v13 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x631,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)(unsigned int)v13,
      ppvb);
  v14 = a1 + 248;
  FlattenHeaders(Src);
  ConvertWideToUtf8(v53, a2);
  std::wstring::wstring(v54, a4);
  std::wstring::append(v54);
  if ( lpString2 )
    v15 = CompareStringOrdinal(L"*", -1, lpString2, -1, 1) == 2;
  else
    v15 = 0;
  v42 = 0;
  pv = 0;
  if ( v15 )
  {
    v45 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v45, 0);
    if ( v45 == 5 || (unsigned int)(v45 - 11) <= 1 )
    {
      AddRef = pProxy->lpVtbl[4].AddRef;
      pv = 0;
      v42 = 0;
      v33 = v54;
      if ( v55 > 7 )
        LODWORD(v33) = v54[0];
      if ( a3[3] > 7u )
        a3 = (_QWORD *)*a3;
      ppvf = (int)v33;
      v34 = ((__int64 (__fastcall *)(IUnknown *, const WCHAR *, _QWORD, _QWORD *))AddRef)(pProxy, lpString2, 0, a3);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x65C,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v34,
          ppvf);
    }
    else
    {
      v48 = 0;
      v46 = 0;
      lpVtbl = pProxy->lpVtbl;
      v46 = 0;
      v48 = 0;
      v20 = ((__int64 (__fastcall *)(IUnknown *, __int64 *, __int64 *))lpVtbl[18].Release)(pProxy, &v48, &v46);
      if ( v20 < 0 )
      {
        if ( v20 == -2015559639 )
          LogMessage(
            2u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            0x674u,
            "LicenseProxyService::AddXTokenAndSignRequest",
            (wchar_t *)L"No gamer account in xbox app, things may not work out well.");
        v24 = pProxy->lpVtbl[4].AddRef;
        pv = 0;
        v42 = 0;
        v25 = v54;
        if ( v55 > 7 )
          LODWORD(v25) = v54[0];
        if ( a3[3] > 7u )
          a3 = (_QWORD *)*a3;
        ppve = (int)v25;
        v26 = ((__int64 (__fastcall *)(IUnknown *, const WCHAR *, _QWORD, _QWORD *))v24)(pProxy, lpString2, 0, a3);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x680,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v26,
            ppve);
      }
      else
      {
        QueryInterface = pProxy->lpVtbl[5].QueryInterface;
        pv = 0;
        v42 = 0;
        v22 = v54;
        if ( v55 > 7 )
          LODWORD(v22) = v54[0];
        if ( a3[3] > 7u )
          a3 = (_QWORD *)*a3;
        ppvd = (int)v22;
        v23 = ((__int64 (__fastcall *)(IUnknown *, __int64, _QWORD, _QWORD *))QueryInterface)(pProxy, v46, 0, a3);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x66E,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v23,
            ppvd);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v46);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v48);
    }
  }
  else
  {
    v16 = pProxy->lpVtbl[5].QueryInterface;
    pv = 0;
    v42 = 0;
    v17 = v54;
    if ( v55 > 7 )
      LODWORD(v17) = v54[0];
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    ppvc = (int)v17;
    v18 = ((__int64 (__fastcall *)(IUnknown *, const WCHAR *, _QWORD, _QWORD *))v16)(pProxy, lpString2, 0, a3);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x646,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v18,
        ppvc);
  }
  std::wstring::wstring(v57, L"authorization");
  v27 = std::map<std::wstring,std::wstring>::operator[](v14, v57);
  std::wstring::assign(v27, v42);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  std::wstring::wstring(v57, L"Signature");
  v28 = std::map<std::wstring,std::wstring>::operator[](v14, v57);
  std::wstring::assign(v28, pv);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  v47 = 0;
  v29 = *v51;
  v30 = ***v51;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  if ( v30(v29, &GUID_43f68466_d582_45da_ba61_dd66856d6a99, &v47) >= 0 )
    (*(void (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v47 + 24LL))(v47, v42);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
  ContentIdString::~ContentIdString((ContentIdString *)v54);
  std::string::_Tidy_deallocate(v53);
  ContentIdString::~ContentIdString((ContentIdString *)Src);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
  ImpersonationScope<LicenseIdentityContextTraits>::~ImpersonationScope<LicenseIdentityContextTraits>(v52);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  return Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
}

```

## disassembly

```asm
0x18005815c  push    rbp
0x18005815e  push    rbx
0x18005815f  push    rsi
0x180058160  push    rdi
0x180058161  push    r12
0x180058163  push    r13
0x180058165  push    r14
0x180058167  push    r15
0x180058169  lea     rbp, [rsp-58h]
0x18005816e  sub     rsp, 158h
0x180058175  mov     rax, cs:__security_cookie
0x18005817c  xor     rax, rsp
0x18005817f  mov     [rbp+90h+var_48], rax
0x180058183  mov     r15, r9
0x180058186  mov     rbx, r8
0x180058189  mov     rsi, rdx
0x18005818c  mov     rdi, rcx
0x18005818f  mov     rax, [rbp+90h+arg_30]
0x180058196  mov     [rbp+90h+var_E0], rax
0x18005819a  mov     r12, [rbp+90h+arg_20]
0x1800581a1  mov     r14, [rbp+90h+lpString2]
0x1800581a8  mov     rcx, [rax]
0x1800581ab  mov     rax, [rcx]
0x1800581ae  mov     rax, [rax+30h]
0x1800581b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581b7  mov     rcx, [rax]
0x1800581ba  mov     [rbp+90h+var_E8], rcx
0x1800581be  lea     rcx, [rbp+90h+var_E8]
0x1800581c2  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x1800581c7  nop
0x1800581c8  xor     r13d, r13d
0x1800581cb  mov     [rbp+90h+var_F0], r13
0x1800581cf  lea     rdx, [rbp+90h+var_F0]
0x1800581d3  lea     rcx, [rbp+90h+var_E8]
0x1800581d7  call    ??$As@UILicenseIdentityContext@@@?$ComPtr@UILicenseIdentityInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::As<ILicenseIdentityContext>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILicenseIdentityContext>>)
0x1800581dc  mov     rcx, [rbp+98h]; this
0x1800581e3  test    eax, eax
0x1800581e5  jns     short loc_1800581FC
0x1800581e7  mov     r9d, eax; char *
0x1800581ea  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800581f1  mov     edx, 62Ch; void *
0x1800581f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800581fc  mov     rdx, [rbp+90h+var_F0]
0x180058200  lea     rcx, [rbp+90h+var_D8]
0x180058204  call    ??0?$ImpersonationScope@ULicenseIdentityContextTraits@@@@QEAA@PEAUILicenseIdentityContext@@@Z; ImpersonationScope<LicenseIdentityContextTraits>::ImpersonationScope<LicenseIdentityContextTraits>(ILicenseIdentityContext *)
0x180058209  nop
0x18005820a  mov     [rsp+190h+pProxy], r13
0x18005820f  lea     rcx, [rsp+190h+pProxy]
0x180058214  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180058219  lea     rax, [rsp+190h+pProxy]
0x18005821e  mov     [rsp+190h+ppv], rax; int
0x180058223  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x18005822a  xor     edx, edx; pUnkOuter
0x18005822c  lea     r8d, [rdx+17h]; dwClsContext
0x180058230  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x180058237  call    cs:__imp_CoCreateInstance
0x18005823d  mov     rcx, [rbp+98h]; this
0x180058244  test    eax, eax
0x180058246  jns     short loc_18005825D
0x180058248  mov     r9d, eax; char *
0x18005824b  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058252  mov     edx, 630h; void *
0x180058257  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005825d  mov     [rsp+190h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180058265  mov     [rsp+190h+pAuthInfo], r13; pAuthInfo
0x18005826a  mov     [rsp+190h+dwImpLevel], 3; dwImpLevel
0x180058272  mov     dword ptr [rsp+190h+ppv], r13d; int
0x180058277  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18005827b  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18005827e  mov     r8d, edx; dwAuthzSvc
0x180058281  mov     rcx, [rsp+190h+pProxy]; pProxy
0x180058286  call    cs:__imp_CoSetProxyBlanket
0x18005828c  mov     rcx, [rbp+98h]; this
0x180058293  test    eax, eax
0x180058295  jns     short loc_1800582AC
0x180058297  mov     r9d, eax; char *
0x18005829a  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800582a1  mov     edx, 631h; void *
0x1800582a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800582ac  lea     r13, [rdi+0F8h]
0x1800582b3  mov     rdx, r13
0x1800582b6  lea     rcx, [rbp+90h+Src]; Src
0x1800582ba  call    ?FlattenHeaders@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@@Z; FlattenHeaders(std::map<std::wstring,std::wstring> const &)
0x1800582bf  nop
0x1800582c0  mov     rdx, rsi; lpWideCharStr
0x1800582c3  lea     rcx, [rbp+90h+var_C8]; Src
0x1800582c7  call    ?ConvertWideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; ConvertWideToUtf8(std::wstring const &)
0x1800582cc  nop
0x1800582cd  mov     rdx, r15
0x1800582d0  lea     rcx, [rbp+90h+var_A8]
0x1800582d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800582d9  nop
0x1800582da  mov     rdx, r12
0x1800582dd  lea     rcx, [rbp+90h+var_A8]; Src
0x1800582e1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800582e6  xor     r12d, r12d
0x1800582e9  test    r14, r14
0x1800582ec  jz      short loc_180058315
0x1800582ee  mov     dword ptr [rsp+190h+ppv], 1; bIgnoreCase
0x1800582f6  or      r9d, 0FFFFFFFFh; cchCount2
0x1800582fa  mov     r8, r14; lpString2
0x1800582fd  or      edx, r9d; cchCount1
0x180058300  lea     rcx, asc_1800D00D4; "*"
0x180058307  call    cs:__imp_CompareStringOrdinal
0x18005830d  cmp     eax, 2
0x180058310  setz    al
0x180058313  jmp     short loc_180058318
0x180058315  mov     al, r12b
0x180058318  mov     [rsp+190h+var_130], r12
0x18005831d  mov     [rsp+190h+pv], r12
0x180058322  test    al, al
0x180058324  jnz     loc_1800583D8
0x18005832a  mov     r10, [rsp+190h+pProxy]
0x18005832f  mov     rax, [r10]
0x180058332  mov     r11, [rax+78h]
0x180058336  mov     [rsp+190h+pv], r12
0x18005833b  mov     [rsp+190h+var_130], r12
0x180058340  mov     r8d, [rbp+90h+var_B8]
0x180058344  lea     rax, [rbp+90h+var_C8]
0x180058348  cmp     [rbp+90h+var_B0], 0Fh
0x18005834d  cmova   rax, [rbp+90h+var_C8]
0x180058352  lea     rcx, [rbp+90h+Src]
0x180058356  cmp     [rbp+90h+var_70], 7
0x18005835b  cmova   rcx, [rbp+90h+Src]
0x180058360  lea     rdx, [rbp+90h+var_A8]
0x180058364  cmp     [rbp+90h+var_90], 7
0x180058369  cmova   rdx, qword ptr [rbp+90h+var_A8]
0x18005836e  cmp     qword ptr [rbx+18h], 7
0x180058373  jbe     short loc_180058378
0x180058375  mov     rbx, [rbx]
0x180058378  lea     r9, [rsp+190h+pv]
0x18005837d  mov     [rsp+190h+var_148], r9
0x180058382  lea     r9, [rsp+190h+var_130]
0x180058387  mov     [rsp+190h+var_150], r9
0x18005838c  mov     [rsp+190h+dwCapabilities], r8d
0x180058391  mov     [rsp+190h+pAuthInfo], rax
0x180058396  mov     qword ptr [rsp+190h+dwImpLevel], rcx
0x18005839b  mov     [rsp+190h+ppv], rdx; int
0x1800583a0  mov     r9, rbx
0x1800583a3  xor     r8d, r8d
0x1800583a6  mov     rdx, r14
0x1800583a9  mov     rcx, r10
0x1800583ac  mov     rax, r11
0x1800583af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583b4  mov     rcx, [rbp+98h]; this
0x1800583bb  test    eax, eax
0x1800583bd  jns     loc_180058670
0x1800583c3  mov     r9d, eax; char *
0x1800583c6  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800583cd  mov     edx, 646h; void *
0x1800583d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800583d8  mov     [rbp+90h+var_110], r12d
0x1800583dc  xor     r8d, r8d
0x1800583df  lea     rdx, [rbp+90h+var_110]
0x1800583e3  xor     ecx, ecx
0x1800583e5  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800583eb  mov     eax, [rbp+90h+var_110]
0x1800583ee  cmp     eax, 5
0x1800583f1  jz      loc_1800587AF
0x1800583f7  add     eax, 0FFFFFFF5h
0x1800583fa  cmp     eax, 1
0x1800583fd  jbe     loc_1800587AF
0x180058403  mov     [rbp+90h+var_F8], r12
0x180058407  mov     [rbp+90h+var_108], r12
0x18005840b  mov     rcx, [rsp+190h+pProxy]
0x180058410  mov     rax, [rcx]
0x180058413  mov     [rbp+90h+var_108], r12
0x180058417  mov     [rbp+90h+var_F8], r12
0x18005841b  lea     r8, [rbp+90h+var_108]
0x18005841f  lea     rdx, [rbp+90h+var_F8]
0x180058423  mov     rax, [rax+1C0h]
0x18005842a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005842f  test    eax, eax
0x180058431  js      loc_180058534
0x180058437  mov     rsi, [rsp+190h+pProxy]
0x18005843c  mov     rax, [rsi]
0x18005843f  mov     r14, [rax+78h]
0x180058443  mov     rdi, [rsp+190h+pv]
0x180058448  test    rdi, rdi
0x18005844b  jz      short loc_18005846A
0x18005844d  lea     rcx, [rsp+190h+var_120]; this
0x180058452  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180058457  mov     rcx, rdi; pv
0x18005845a  call    cs:__imp_CoTaskMemFree
0x180058460  lea     rcx, [rsp+190h+var_120]; this
0x180058465  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005846a  mov     [rsp+190h+pv], r12
0x18005846f  mov     rdi, [rsp+190h+var_130]
0x180058474  test    rdi, rdi
0x180058477  jz      short loc_180058496
0x180058479  lea     rcx, [rsp+190h+var_120]; this
0x18005847e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180058483  mov     rcx, rdi; pv
0x180058486  call    cs:__imp_CoTaskMemFree
0x18005848c  lea     rcx, [rsp+190h+var_120]; this
0x180058491  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180058496  mov     [rsp+190h+var_130], r12
0x18005849b  mov     r8d, [rbp+90h+var_B8]
0x18005849f  lea     rax, [rbp+90h+var_C8]
0x1800584a3  cmp     [rbp+90h+var_B0], 0Fh
0x1800584a8  cmova   rax, [rbp+90h+var_C8]
0x1800584ad  lea     rcx, [rbp+90h+Src]
0x1800584b1  cmp     [rbp+90h+var_70], 7
0x1800584b6  cmova   rcx, [rbp+90h+Src]
0x1800584bb  lea     rdx, [rbp+90h+var_A8]
0x1800584bf  cmp     [rbp+90h+var_90], 7
0x1800584c4  cmova   rdx, qword ptr [rbp+90h+var_A8]
0x1800584c9  cmp     qword ptr [rbx+18h], 7
0x1800584ce  jbe     short loc_1800584D3
0x1800584d0  mov     rbx, [rbx]
0x1800584d3  lea     r9, [rsp+190h+pv]
0x1800584d8  mov     [rsp+190h+var_148], r9
0x1800584dd  lea     r9, [rsp+190h+var_130]
0x1800584e2  mov     [rsp+190h+var_150], r9
0x1800584e7  mov     [rsp+190h+dwCapabilities], r8d
0x1800584ec  mov     [rsp+190h+pAuthInfo], rax
0x1800584f1  mov     qword ptr [rsp+190h+dwImpLevel], rcx
0x1800584f6  mov     [rsp+190h+ppv], rdx; int
0x1800584fb  mov     r9, rbx
0x1800584fe  xor     r8d, r8d
0x180058501  mov     rdx, [rbp+90h+var_108]
0x180058505  mov     rcx, rsi
0x180058508  mov     rax, r14
0x18005850b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058510  mov     rcx, [rbp+98h]; this
0x180058517  test    eax, eax
0x180058519  jns     loc_18005865D
0x18005851f  mov     r9d, eax; char *
0x180058522  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058529  mov     edx, 66Eh; void *
0x18005852e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058534  cmp     eax, 87DD0029h
0x180058539  jnz     short loc_180058565
0x18005853b  lea     rax, aNoGamerAccount; "No gamer account in xbox app, things ma"...
0x180058542  mov     [rsp+190h+ppv], rax; Format
0x180058547  lea     r9, aLicenseproxyse; "LicenseProxyService::AddXTokenAndSignRe"...
0x18005854e  mov     r8d, 674h; unsigned int
0x180058554  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005855b  mov     ecx, 2; unsigned int
0x180058560  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180058565  mov     rsi, [rsp+190h+pProxy]
0x18005856a  mov     rax, [rsi]
0x18005856d  mov     r15, [rax+68h]
0x180058571  mov     rdi, [rsp+190h+pv]
0x180058576  test    rdi, rdi
0x180058579  jz      short loc_180058598
0x18005857b  lea     rcx, [rsp+190h+var_120]; this
0x180058580  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180058585  mov     rcx, rdi; pv
0x180058588  call    cs:__imp_CoTaskMemFree
0x18005858e  lea     rcx, [rsp+190h+var_120]; this
0x180058593  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180058598  mov     [rsp+190h+pv], r12
0x18005859d  mov     rdi, [rsp+190h+var_130]
0x1800585a2  test    rdi, rdi
0x1800585a5  jz      short loc_1800585C4
0x1800585a7  lea     rcx, [rsp+190h+var_120]; this
0x1800585ac  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800585b1  mov     rcx, rdi; pv
0x1800585b4  call    cs:__imp_CoTaskMemFree
0x1800585ba  lea     rcx, [rsp+190h+var_120]; this
0x1800585bf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800585c4  mov     [rsp+190h+var_130], r12
0x1800585c9  mov     r8d, [rbp+90h+var_B8]
0x1800585cd  lea     rax, [rbp+90h+var_C8]
0x1800585d1  cmp     [rbp+90h+var_B0], 0Fh
0x1800585d6  cmova   rax, [rbp+90h+var_C8]
0x1800585db  lea     rcx, [rbp+90h+Src]
0x1800585df  cmp     [rbp+90h+var_70], 7
0x1800585e4  cmova   rcx, [rbp+90h+Src]
0x1800585e9  lea     rdx, [rbp+90h+var_A8]
0x1800585ed  cmp     [rbp+90h+var_90], 7
0x1800585f2  cmova   rdx, qword ptr [rbp+90h+var_A8]
0x1800585f7  cmp     qword ptr [rbx+18h], 7
0x1800585fc  jbe     short loc_180058601
0x1800585fe  mov     rbx, [rbx]
0x180058601  lea     r9, [rsp+190h+pv]
0x180058606  mov     [rsp+190h+var_148], r9
0x18005860b  lea     r9, [rsp+190h+var_130]
0x180058610  mov     [rsp+190h+var_150], r9
0x180058615  mov     [rsp+190h+dwCapabilities], r8d
0x18005861a  mov     [rsp+190h+pAuthInfo], rax
0x18005861f  mov     qword ptr [rsp+190h+dwImpLevel], rcx
0x180058624  mov     [rsp+190h+ppv], rdx; int
0x180058629  mov     r9, rbx
0x18005862c  xor     r8d, r8d
0x18005862f  mov     rdx, r14
0x180058632  mov     rcx, rsi
0x180058635  mov     rax, r15
0x180058638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005863d  mov     rcx, [rbp+98h]; this
0x180058644  test    eax, eax
0x180058646  jns     short loc_18005865D
0x180058648  mov     r9d, eax; char *
0x18005864b  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058652  mov     edx, 680h; void *
0x180058657  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005865d  lea     rcx, [rbp+90h+var_108]
0x180058661  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180058666  nop
  ... truncated ...
```

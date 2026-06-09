# GetRequestForOSRemediation(Microsoft::WRL::ComPtr<IStoredKeyDocument> const &,char const *,Nexus const &,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &)

- ea: `0x18006624c`
- end: `0x180066887`
- name: `?GetRequestForOSRemediation@@YA?AVHttpRequest@@AEBV?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@PEBDAEBVNexus@@AEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@34@@Z`
- size: `1595`
- prototype: `__int64 __usercall@<rax>(HttpRequest *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005c424`

## callees

- `0x1800046e8`
- `0x180004738`
- `0x1800061e0`
- `0x18000737c`
- `0x18000a0e4`
- `0x18000a110`
- `0x180012dc0`
- `0x180017230`
- `0x180017654`
- `0x180028160`
- `0x1800363ec`
- `0x1800369e4`
- `0x18003e33c`
- `0x18003ffbc`
- `0x18003ffe0`
- `0x1800454b8`
- `0x1800593bc`
- `0x18005c038`
- `0x18005c1ec`
- `0x18006624c`
- `0x180066890`
- `0x180066a28`
- `0x180075e60`
- `0x18007b210`
- `0x18007b370`
- `0x18007b630`
- `0x18007be60`
- `0x18007d1d0`
- `0x18007e710`
- `0x180081360`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066434`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066452`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066452`

## string_xrefs

- `0x18006681d`: `application/json`
- `0x180066666`: `tokenItem`
- `0x180066377`: `tokenType`
- `0x1800663d6`: `tokenValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
HttpRequest *__fastcall GetRequestForOSRemediation(
        HttpRequest *this,
        _QWORD *a2,
        __int64 a3,
        unsigned __int16 *a4,
        _QWORD *a5)
{
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  int LastError; // eax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  OLECHAR *Guid; // rax
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // rbx
  __int64 v40; // rax
  WinStoreAuth::AuthenticationInternal *v41; // rcx
  int v42; // eax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  const WCHAR *v46; // rax
  const unsigned __int16 *v48; // [rsp+20h] [rbp-A1h]
  int v49; // [rsp+20h] [rbp-A1h]
  _BYTE v50[8]; // [rsp+30h] [rbp-91h] BYREF
  _BYTE v51[8]; // [rsp+38h] [rbp-89h] BYREF
  __int64 v52; // [rsp+40h] [rbp-81h] BYREF
  int v53; // [rsp+48h] [rbp-79h] BYREF
  _BYTE v54[8]; // [rsp+50h] [rbp-71h] BYREF
  int v55; // [rsp+58h] [rbp-69h]
  HttpRequest *v56; // [rsp+60h] [rbp-61h]
  _BYTE v57[32]; // [rsp+70h] [rbp-51h] BYREF
  void **v58; // [rsp+90h] [rbp-31h] BYREF
  _QWORD v59[3]; // [rsp+98h] [rbp-29h] BYREF
  OLECHAR Src[16]; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v56 = this;
  v55 = 0;
  web::json::value::value((web::json::value *)v51);
  web::json::value::value((web::json::value *)&v52);
  v9 = std::wstring::wstring(v57, L"LicenseManager");
  v10 = web::json::value::string(&v53, v9);
  std::wstring::wstring(&v58, L"client");
  v11 = web::json::value::operator[](&v52, &v58);
  web::json::value::operator=(v11, v10);
  ContentIdString::~ContentIdString((ContentIdString *)&v58);
  web::json::value::~value((web::json::value *)&v53);
  web::json::value::value((web::json::value *)v54);
  v53 = 0;
  v58 = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
  v59[0] = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD *))(*(_QWORD *)*a2 + 40LL))(*a2, &v53, v59);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\purchase.cpp",
      (const char *)(unsigned int)v12,
      (int)v48);
  v13 = std::wstring::wstring(Src, L"TSL");
  v14 = web::json::value::string(v50, v13);
  std::wstring::wstring(v57, L"tokenType");
  v15 = web::json::value::operator[](v54, v57);
  web::json::value::operator=(v15, v14);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v50);
  v16 = _to_base64(Src);
  v17 = web::json::value::string(v50, v16);
  std::wstring::wstring(v57, L"tokenValue");
  v18 = web::json::value::operator[](v54, v57);
  web::json::value::operator=(v18, v17);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v50);
  v58 = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
  if ( v59[0] && !Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose((__int64)&v58) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  std::wstring::wstring(v57, L"clientContext");
  v20 = web::json::value::operator[](v51, v57);
  web::json::value::operator=(v20, &v52);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  v21 = web::json::value::array(v50);
  std::wstring::wstring(v57, L"items");
  v22 = web::json::value::operator[](v51, v57);
  web::json::value::operator=(v22, v21);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v50);
  v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a5 + 24LL))(*a5);
  v24 = std::wstring::wstring(Src, v23);
  v25 = web::json::value::string(v50, v24);
  std::wstring::wstring(v57, L"language");
  v26 = web::json::value::operator[](v51, v57);
  web::json::value::operator=(v26, v25);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v50);
  v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a5 + 56LL))(*a5);
  v28 = std::wstring::wstring(Src, v27);
  v29 = web::json::value::string(v50, v28);
  std::wstring::wstring(v57, L"market");
  v30 = web::json::value::operator[](v51, v57);
  web::json::value::operator=(v30, v29);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v50);
  Guid = CreateGuid(Src);
  v32 = web::json::value::string(v50, Guid);
  std::wstring::wstring(v57, L"orderId");
  v33 = web::json::value::operator[](v51, v57);
  web::json::value::operator=(v33, v32);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v50);
  v34 = std::wstring::wstring(Src, L"Purchased");
  v35 = web::json::value::string(v50, v34);
  std::wstring::wstring(v57, L"orderState");
  v36 = web::json::value::operator[](v51, v57);
  web::json::value::operator=(v36, v35);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v50);
  std::wstring::wstring(v57, L"tokenItem");
  v37 = web::json::value::operator[](v51, v57);
  web::json::value::operator=(v37, v54);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  web::json::value::~value((web::json::value *)v54);
  web::json::value::~value((web::json::value *)&v52);
  Nexus::InitializeIfNecessary(a4);
  v38 = a4 + 124;
  if ( *((_QWORD *)a4 + 34) > 7u )
    v38 = *(const unsigned __int16 **)v38;
  HttpRequest::HttpRequest(this, v38, L"/v7.0/users/me/orders", L"POST", v48);
  v55 = 1;
  std::string::string(&v58, a3);
  v39 = ConvertToWide(Src, &v58, 0);
  std::wstring::wstring(v57, L"MS-CV");
  v40 = std::map<std::wstring,std::wstring>::operator[]((char *)this + 248, v57);
  std::wstring::operator=(v40, v39);
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  ContentIdString::~ContentIdString((ContentIdString *)Src);
  std::string::_Tidy_deallocate(&v58);
  if ( !WinStoreAuth::AuthenticationInternal::UseXToken(v41) )
  {
    v52 = 0;
    v42 = Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot>::As<ILicenseSingleUserIdentityInternal>(a5, &v52);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\purchase.cpp",
        (const char *)(unsigned int)v42,
        v49);
    v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 24LL))(v52);
    std::operator+<unsigned short>(&v58, L"MSAHW1.0=", v43);
    std::wstring::wstring(v57, L"authorization");
    v44 = std::map<std::wstring,std::wstring>::operator[]((char *)this + 248, v57);
    std::wstring::operator=(v44, &v58);
    ContentIdString::~ContentIdString((ContentIdString *)v57);
    ContentIdString::~ContentIdString((ContentIdString *)&v58);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
  }
  std::wstring::wstring(v57, L"Content-Type");
  v45 = std::map<std::wstring,std::wstring>::operator[]((char *)this + 248, v57);
  std::wstring::assign(v45, L"application/json");
  ContentIdString::~ContentIdString((ContentIdString *)v57);
  v46 = (const WCHAR *)web::json::value::serialize(v51, Src);
  HttpRequest::SetBody((__int64)this, v46);
  ContentIdString::~ContentIdString((ContentIdString *)Src);
  web::json::value::~value((web::json::value *)v51);
  return this;
}

```

## disassembly

```asm
0x18006624c  push    rbp
0x18006624e  push    rbx
0x18006624f  push    rsi
0x180066250  push    rdi
0x180066251  push    r13
0x180066253  push    r14
0x180066255  push    r15
0x180066257  lea     rbp, [rsp-1Fh]
0x18006625c  sub     rsp, 0E0h
0x180066263  mov     rax, cs:__security_cookie
0x18006626a  xor     rax, rsp
0x18006626d  mov     [rbp+4Fh+var_40], rax
0x180066271  mov     r13, r9
0x180066274  mov     r15, r8
0x180066277  mov     rdi, rdx
0x18006627a  mov     rsi, rcx
0x18006627d  mov     [rbp+4Fh+var_B0], rcx
0x180066281  mov     r14, [rbp+4Fh+arg_20]
0x180066285  mov     [rbp+4Fh+var_B8], 0
0x18006628c  lea     rcx, [rsp+110h+var_D8]; this
0x180066291  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180066296  nop
0x180066297  lea     rcx, [rsp+110h+var_D0]; this
0x18006629c  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x1800662a1  nop
0x1800662a2  lea     rdx, aLicensemanager_16; "LicenseManager"
0x1800662a9  lea     rcx, [rbp+4Fh+var_A0]
0x1800662ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800662b2  mov     rdx, rax
0x1800662b5  lea     rcx, [rbp+4Fh+var_C8]
0x1800662b9  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800662be  mov     rbx, rax
0x1800662c1  lea     rdx, aClient; "client"
0x1800662c8  lea     rcx, [rbp+4Fh+var_80]
0x1800662cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800662d1  nop
0x1800662d2  lea     rdx, [rbp+4Fh+var_80]
0x1800662d6  lea     rcx, [rsp+110h+var_D0]
0x1800662db  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800662e0  mov     rcx, rax
0x1800662e3  mov     rdx, rbx
0x1800662e6  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800662eb  nop
0x1800662ec  lea     rcx, [rbp+4Fh+var_80]; this
0x1800662f0  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800662f5  nop
0x1800662f6  lea     rcx, [rbp+4Fh+var_C8]; this
0x1800662fa  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x1800662ff  lea     rcx, [rbp+4Fh+var_C0]; this
0x180066303  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180066308  nop
0x180066309  mov     [rbp+4Fh+var_C8], 0
0x180066310  lea     rax, ??_7?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable'
0x180066317  mov     [rbp+4Fh+var_80], rax
0x18006631b  mov     [rbp+4Fh+var_78], 0
0x180066323  mov     rcx, [rdi]
0x180066326  mov     rax, [rcx]
0x180066329  lea     r8, [rbp+4Fh+var_78]
0x18006632d  lea     rdx, [rbp+4Fh+var_C8]
0x180066331  mov     rax, [rax+28h]
0x180066335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006633a  mov     rcx, [rbp+57h]; this
0x18006633e  test    eax, eax
0x180066340  jns     short loc_180066357
0x180066342  mov     r9d, eax; char *
0x180066345  lea     r8, aOnecoreuapEndu_19; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006634c  mov     edx, 77h ; 'w'; void *
0x180066351  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066357  lea     rdx, aTsl; "TSL"
0x18006635e  lea     rcx, [rbp+4Fh+Src]
0x180066362  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066367  mov     rdx, rax
0x18006636a  lea     rcx, [rsp+110h+var_E0]
0x18006636f  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x180066374  mov     rbx, rax
0x180066377  lea     rdx, aTokentype; "tokenType"
0x18006637e  lea     rcx, [rbp+4Fh+var_A0]
0x180066382  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066387  nop
0x180066388  lea     rdx, [rbp+4Fh+var_A0]
0x18006638c  lea     rcx, [rbp+4Fh+var_C0]
0x180066390  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180066395  mov     rcx, rax
0x180066398  mov     rdx, rbx
0x18006639b  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800663a0  nop
0x1800663a1  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800663a5  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800663aa  nop
0x1800663ab  lea     rcx, [rsp+110h+var_E0]; this
0x1800663b0  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x1800663b5  mov     r8d, [rbp+4Fh+var_C8]
0x1800663b9  mov     rdx, [rbp+4Fh+var_78]
0x1800663bd  lea     rcx, [rbp+4Fh+Src]; Src
0x1800663c1  call    ?_to_base64@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBE_K@Z; _to_base64(uchar const *,unsigned __int64)
0x1800663c6  mov     rdx, rax
0x1800663c9  lea     rcx, [rsp+110h+var_E0]
0x1800663ce  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800663d3  mov     rbx, rax
0x1800663d6  lea     rdx, aTokenvalue; "tokenValue"
0x1800663dd  lea     rcx, [rbp+4Fh+var_A0]
0x1800663e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800663e6  nop
0x1800663e7  lea     rdx, [rbp+4Fh+var_A0]
0x1800663eb  lea     rcx, [rbp+4Fh+var_C0]
0x1800663ef  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800663f4  mov     rcx, rax
0x1800663f7  mov     rdx, rbx
0x1800663fa  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800663ff  nop
0x180066400  lea     rcx, [rbp+4Fh+var_A0]; this
0x180066404  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180066409  nop
0x18006640a  lea     rcx, [rsp+110h+var_E0]; this
0x18006640f  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x180066414  nop
0x180066415  lea     rax, ??_7?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable'
0x18006641c  mov     [rbp+4Fh+var_80], rax
0x180066420  cmp     [rbp+4Fh+var_78], 0
0x180066425  jz      short loc_180066459
0x180066427  lea     rcx, [rbp+4Fh+var_80]
0x18006642b  call    ?InternalClose@?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose(void)
0x180066430  test    al, al
0x180066432  jnz     short loc_180066459
0x180066434  call    cs:__imp_GetLastError
0x18006643a  test    eax, eax
0x18006643c  jle     short loc_180066446
0x18006643e  movzx   eax, ax
0x180066441  or      eax, 80070000h
0x180066446  xor     r9d, r9d; lpArguments
0x180066449  xor     r8d, r8d; nNumberOfArguments
0x18006644c  lea     edx, [r9+1]; dwExceptionFlags
0x180066450  mov     ecx, eax; dwExceptionCode
0x180066452  call    cs:__imp_RaiseException
0x180066458  int     3; Trap to Debugger
0x180066459  lea     rdx, aClientcontext; "clientContext"
0x180066460  lea     rcx, [rbp+4Fh+var_A0]
0x180066464  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066469  nop
0x18006646a  lea     rdx, [rbp+4Fh+var_A0]
0x18006646e  lea     rcx, [rsp+110h+var_D8]
0x180066473  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180066478  mov     rcx, rax
0x18006647b  lea     rdx, [rsp+110h+var_D0]
0x180066480  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180066485  nop
0x180066486  lea     rcx, [rbp+4Fh+var_A0]; this
0x18006648a  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18006648f  lea     rcx, [rsp+110h+var_E0]
0x180066494  call    ?array@value@json@web@@SA?AV123@XZ; web::json::value::array(void)
0x180066499  mov     rbx, rax
0x18006649c  lea     rdx, aItems; "items"
0x1800664a3  lea     rcx, [rbp+4Fh+var_A0]
0x1800664a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800664ac  nop
0x1800664ad  lea     rdx, [rbp+4Fh+var_A0]
0x1800664b1  lea     rcx, [rsp+110h+var_D8]
0x1800664b6  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800664bb  mov     rcx, rax
0x1800664be  mov     rdx, rbx
0x1800664c1  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800664c6  nop
0x1800664c7  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800664cb  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800664d0  nop
0x1800664d1  lea     rcx, [rsp+110h+var_E0]; this
0x1800664d6  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x1800664db  mov     rcx, [r14]
0x1800664de  mov     rax, [rcx]
0x1800664e1  mov     rax, [rax+18h]
0x1800664e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664ea  mov     rdx, rax
0x1800664ed  lea     rcx, [rbp+4Fh+Src]
0x1800664f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800664f6  mov     rdx, rax
0x1800664f9  lea     rcx, [rsp+110h+var_E0]
0x1800664fe  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x180066503  mov     rbx, rax
0x180066506  lea     rdx, aLanguage; "language"
0x18006650d  lea     rcx, [rbp+4Fh+var_A0]
0x180066511  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066516  nop
0x180066517  lea     rdx, [rbp+4Fh+var_A0]
0x18006651b  lea     rcx, [rsp+110h+var_D8]
0x180066520  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180066525  mov     rcx, rax
0x180066528  mov     rdx, rbx
0x18006652b  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180066530  nop
0x180066531  lea     rcx, [rbp+4Fh+var_A0]; this
0x180066535  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18006653a  nop
0x18006653b  lea     rcx, [rsp+110h+var_E0]; this
0x180066540  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x180066545  mov     rcx, [r14]
0x180066548  mov     rax, [rcx]
0x18006654b  mov     rax, [rax+38h]
0x18006654f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066554  mov     rdx, rax
0x180066557  lea     rcx, [rbp+4Fh+Src]
0x18006655b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180066560  mov     rdx, rax
0x180066563  lea     rcx, [rsp+110h+var_E0]
0x180066568  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x18006656d  mov     rbx, rax
0x180066570  lea     rdx, aMarket; "market"
0x180066577  lea     rcx, [rbp+4Fh+var_A0]
0x18006657b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066580  nop
0x180066581  lea     rdx, [rbp+4Fh+var_A0]
0x180066585  lea     rcx, [rsp+110h+var_D8]
0x18006658a  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18006658f  mov     rcx, rax
0x180066592  mov     rdx, rbx
0x180066595  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x18006659a  nop
0x18006659b  lea     rcx, [rbp+4Fh+var_A0]; this
0x18006659f  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800665a4  nop
0x1800665a5  lea     rcx, [rsp+110h+var_E0]; this
0x1800665aa  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x1800665af  lea     rcx, [rbp+4Fh+Src]; int
0x1800665b3  call    CreateGuid
0x1800665b8  mov     rdx, rax
0x1800665bb  lea     rcx, [rsp+110h+var_E0]
0x1800665c0  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800665c5  mov     rbx, rax
0x1800665c8  lea     rdx, aOrderid; "orderId"
0x1800665cf  lea     rcx, [rbp+4Fh+var_A0]
0x1800665d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800665d8  nop
0x1800665d9  lea     rdx, [rbp+4Fh+var_A0]
0x1800665dd  lea     rcx, [rsp+110h+var_D8]
0x1800665e2  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800665e7  mov     rcx, rax
0x1800665ea  mov     rdx, rbx
0x1800665ed  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800665f2  nop
0x1800665f3  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800665f7  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800665fc  nop
0x1800665fd  lea     rcx, [rsp+110h+var_E0]; this
0x180066602  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x180066607  lea     rdx, aPurchased; "Purchased"
0x18006660e  lea     rcx, [rbp+4Fh+Src]
0x180066612  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066617  mov     rdx, rax
0x18006661a  lea     rcx, [rsp+110h+var_E0]
0x18006661f  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x180066624  mov     rbx, rax
0x180066627  lea     rdx, aOrderstate; "orderState"
0x18006662e  lea     rcx, [rbp+4Fh+var_A0]
0x180066632  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066637  nop
0x180066638  lea     rdx, [rbp+4Fh+var_A0]
0x18006663c  lea     rcx, [rsp+110h+var_D8]
0x180066641  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180066646  mov     rcx, rax
0x180066649  mov     rdx, rbx
0x18006664c  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180066651  nop
0x180066652  lea     rcx, [rbp+4Fh+var_A0]; this
0x180066656  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18006665b  nop
0x18006665c  lea     rcx, [rsp+110h+var_E0]; this
0x180066661  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x180066666  lea     rdx, aTokenitem; "tokenItem"
0x18006666d  lea     rcx, [rbp+4Fh+var_A0]
0x180066671  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066676  nop
0x180066677  lea     rdx, [rbp+4Fh+var_A0]
0x18006667b  lea     rcx, [rsp+110h+var_D8]
0x180066680  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180066685  mov     rcx, rax
0x180066688  lea     rdx, [rbp+4Fh+var_C0]
0x18006668c  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180066691  nop
0x180066692  lea     rcx, [rbp+4Fh+var_A0]; this
0x180066696  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18006669b  nop
0x18006669c  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800666a0  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x1800666a5  nop
0x1800666a6  lea     rcx, [rsp+110h+var_D0]; this
0x1800666ab  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x1800666b0  mov     rcx, r13; Parameter
0x1800666b3  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x1800666b8  lea     rdx, [r13+0F8h]
0x1800666bf  cmp     qword ptr [rdx+18h], 7
0x1800666c4  jbe     short loc_1800666C9
0x1800666c6  mov     rdx, [rdx]; unsigned __int16 *
0x1800666c9  lea     r9, aPost; "POST"
0x1800666d0  lea     r8, aV70UsersMeOrde; "/v7.0/users/me/orders"
0x1800666d7  mov     rcx, rsi; this
0x1800666da  call    ??0HttpRequest@@QEAA@PEBG000@Z; HttpRequest::HttpRequest(ushort const *,ushort const *,ushort const *,ushort const *)
0x1800666df  mov     [rbp+4Fh+var_B8], 1
0x1800666e6  mov     rdx, r15
0x1800666e9  lea     rcx, [rbp+4Fh+var_80]
0x1800666ed  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800666f2  nop
  ... truncated ...
```

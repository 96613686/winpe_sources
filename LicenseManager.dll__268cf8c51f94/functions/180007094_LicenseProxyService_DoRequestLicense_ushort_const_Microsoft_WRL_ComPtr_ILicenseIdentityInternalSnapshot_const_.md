# LicenseProxyService::DoRequestLicense(ushort const *,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &,char const *,web::json::value const &,bool,HttpResponse *,web::json::value *)

- ea: `0x180007094`
- end: `0x180007374`
- name: `?DoRequestLicense@LicenseProxyService@@AEAAXPEBGAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@PEBDAEBVvalue@json@web@@_NPEAVHttpResponse@@PEAV567@@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180032010`

## callees

- `0x180006b38`
- `0x180006cec`
- `0x180007094`
- `0x18000737c`
- `0x180007704`
- `0x1800077c0`
- `0x18000781c`
- `0x180007c78`
- `0x18000a0e4`
- `0x18000a98c`
- `0x180012dc0`
- `0x180013b50`
- `0x18004883c`
- `0x1800593bc`
- `0x18005f014`
- `0x180075e60`
- `0x18007b210`
- `0x18007b370`
- `0x180080ec0`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000719f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000719f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007169`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800072cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007169`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800072cb`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180007282`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180007282`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007267`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007267`

## string_xrefs

- `0x18000714b`: `LicenseProxyService::DoRequestLicense`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LicenseProxyService::DoRequestLicense(
        __int64 a1,
        unsigned __int16 *a2,
        _QWORD *a3,
        const char *a4,
        __int64 a5,
        char a6,
        HttpResponse *a7,
        struct web::json::value *a8)
{
  _QWORD *v12; // rbx
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // rdi
  char *v19; // rbx
  __int64 v20; // rdi
  ContentIdString *v21; // rbx
  __int64 v22; // rcx
  unsigned __int64 v23; // rbx
  const unsigned __int16 *v24; // rdx
  unsigned int v25; // eax
  int Format; // [rsp+20h] [rbp-E0h]
  _BYTE v27[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-A8h]
  ULONGLONG TickCount64; // [rsp+60h] [rbp-A0h]
  ContentIdString *v30; // [rsp+68h] [rbp-98h]
  _BYTE v31[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[40]; // [rsp+90h] [rbp-70h] BYREF
  void **v33; // [rsp+B8h] [rbp-48h] BYREF
  int v34[8]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v35[31]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v28 = a2;
  LicenseProxyService::CreateContentLicenseRequest(a1, v34, a4, a5, a3, a6);
  v12 = *(_QWORD **)(a1 + 48);
  Nexus::InitializeIfNecessary(v12);
  v13 = v12 + 3;
  if ( v13[3] > 7u )
    v13 = (_QWORD *)*v13;
  v14 = v35;
  if ( v35[3] > 7u )
    v14 = (_QWORD *)v35[0];
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
    0x7F0u,
    "LicenseProxyService::DoRequestLicense",
    (wchar_t *)L"Requesting license for %s at %s (%s) (Corr: %hs)",
    a2,
    v14,
    v13,
    a4);
  TickCount64 = GetTickCount64();
  v15 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 48LL))(*a3);
  v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 32LL))(*v15);
  if ( !SetThreadToken(0, *(HANDLE *)(v16 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
      v17);
  v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 40LL))(*a3);
  v19 = *(char **)(a1 + 48);
  Nexus::InitializeIfNecessary(v19);
  v20 = LicenseProxyService::SendRequestAndWaitForResponse(a1, v32, v19 + 24, v18, v34);
  Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close((char *)a7 + 40);
  *((_QWORD *)a7 + 6) = *(_QWORD *)(v20 + 48);
  *(_QWORD *)(v20 + 48) = 0;
  if ( a7 != (HttpResponse *)v20 )
  {
    std::wstring::_Tidy_deallocate(a7);
    *(_OWORD *)a7 = *(_OWORD *)v20;
    *((_OWORD *)a7 + 1) = *(_OWORD *)(v20 + 16);
    *(_QWORD *)(v20 + 16) = 0;
    *(_QWORD *)(v20 + 24) = 7;
    *(_WORD *)v20 = 0;
  }
  *((_DWORD *)a7 + 8) = *(_DWORD *)(v20 + 32);
  v33 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(&v33);
  ContentIdString::~ContentIdString((ContentIdString *)v32);
  RevertToSelf();
  v21 = (ContentIdString *)HttpResponse::Body(a7, v31);
  v30 = v21;
  if ( !(unsigned int)XblaIsConsole(v22) || *((_QWORD *)v21 + 2) )
    web::json::value::parse(v27, v21);
  else
    web::json::value::value((web::json::value *)v27);
  ContentIdString::~ContentIdString(v21);
  web::json::value::operator=(a8, v27);
  web::json::value::~value((web::json::value *)v27);
  v23 = GetTickCount64() - TickCount64;
  if ( HttpResponse::StatusCode(a7) - 200 > 0x63 )
  {
    v25 = LicenseProxyService::HandleFault(
            (int)a4,
            (int)L"RequestLicense",
            (int)v28,
            (int)v34,
            a7,
            (__int64)a8,
            v23,
            (__int64)a3);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7FE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      (const char *)v25,
      Format);
  }
  LogRequestLicenseSuccess(a4, v24, v28, (const struct HttpRequest *)v34, a7, a8, v23);
  HttpRequest::~HttpRequest((HttpRequest *)v34);
}

```

## disassembly

```asm
0x180007094  push    rbp
0x180007096  push    rbx
0x180007097  push    rsi
0x180007098  push    rdi
0x180007099  push    r12
0x18000709b  push    r13
0x18000709d  push    r14
0x18000709f  push    r15
0x1800070a1  lea     rbp, [rsp-108h]
0x1800070a9  sub     rsp, 208h
0x1800070b0  mov     rax, cs:__security_cookie
0x1800070b7  xor     rax, rsp
0x1800070ba  mov     [rbp+140h+var_48], rax
0x1800070c1  mov     r15, r9
0x1800070c4  mov     r12, r8
0x1800070c7  mov     rdi, rdx
0x1800070ca  mov     [rsp+240h+var_1E8], rdx
0x1800070cf  mov     r13, rcx
0x1800070d2  mov     r9, [rbp+140h+arg_20]
0x1800070d9  mov     rsi, [rbp+140h+arg_30]
0x1800070e0  mov     r14, [rbp+140h+arg_38]
0x1800070e7  mov     al, [rbp+140h+arg_28]
0x1800070ed  mov     byte ptr [rsp+240h+var_218], al
0x1800070f1  mov     [rsp+240h+Format], r8
0x1800070f6  mov     r8, r15
0x1800070f9  lea     rdx, [rbp+140h+var_160]
0x1800070fd  call    ?CreateContentLicenseRequest@LicenseProxyService@@AEAA?AVHttpRequest@@PEBDAEBVvalue@json@web@@AEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@_N@Z; LicenseProxyService::CreateContentLicenseRequest(char const *,web::json::value const &,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &,bool)
0x180007102  nop
0x180007103  mov     rbx, [r13+30h]
0x180007107  mov     rcx, rbx; Parameter
0x18000710a  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x18000710f  add     rbx, 18h
0x180007113  cmp     qword ptr [rbx+18h], 7
0x180007118  jbe     short loc_18000711D
0x18000711a  mov     rbx, [rbx]
0x18000711d  lea     rax, [rbp+140h+var_140]
0x180007121  cmp     [rbp+140h+var_128], 7
0x180007126  cmova   rax, [rbp+140h+var_140]
0x18000712b  mov     [rsp+240h+var_200], r15
0x180007130  mov     [rsp+240h+var_208], rbx
0x180007135  mov     [rsp+240h+var_210], rax
0x18000713a  mov     [rsp+240h+var_218], rdi
0x18000713f  lea     rax, aRequestingLice; "Requesting license for %s at %s (%s) (C"...
0x180007146  mov     [rsp+240h+Format], rax; Format
0x18000714b  lea     r9, aLicenseproxyse_10; "LicenseProxyService::DoRequestLicense"
0x180007152  mov     r8d, 7F0h; unsigned int
0x180007158  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000715f  mov     ecx, 3; unsigned int
0x180007164  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180007169  call    cs:__imp_GetTickCount64
0x18000716f  mov     [rsp+240h+var_1E0], rax
0x180007174  mov     rdx, [r12]
0x180007178  mov     rcx, [rdx]
0x18000717b  mov     rax, [rcx+30h]
0x18000717f  mov     rcx, rdx
0x180007182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007187  mov     rdx, [rax]
0x18000718a  mov     rcx, [rdx]
0x18000718d  mov     rax, [rcx+20h]
0x180007191  mov     rcx, rdx
0x180007194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007199  mov     rdx, [rax+8]; Token
0x18000719d  xor     ecx, ecx; Thread
0x18000719f  call    cs:__imp_SetThreadToken
0x1800071a5  mov     rcx, [rbp+148h]; this
0x1800071ac  test    eax, eax
0x1800071ae  jnz     short loc_1800071C2
0x1800071b0  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800071b7  mov     edx, 221h; void *
0x1800071bc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800071c2  mov     rcx, [r12]
0x1800071c6  mov     rax, [rcx]
0x1800071c9  mov     rax, [rax+28h]
0x1800071cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d2  mov     rdi, rax
0x1800071d5  mov     rbx, [r13+30h]
0x1800071d9  mov     rcx, rbx; Parameter
0x1800071dc  call    ?InitializeIfNecessary@Nexus@@QEBAXXZ; Nexus::InitializeIfNecessary(void)
0x1800071e1  lea     r8, [rbx+18h]
0x1800071e5  lea     rax, [rbp+140h+var_160]
0x1800071e9  mov     [rsp+240h+Format], rax
0x1800071ee  mov     r9, rdi
0x1800071f1  lea     rdx, [rbp+140h+var_1B0]
0x1800071f5  mov     rcx, r13
0x1800071f8  call    ?SendRequestAndWaitForResponse@LicenseProxyService@@AEAA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z; LicenseProxyService::SendRequestAndWaitForResponse(std::wstring const &,ProxySettings const &,HttpRequest &)
0x1800071fd  mov     rdi, rax
0x180007200  lea     rcx, [rsi+28h]
0x180007204  call    ?Close@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(void)
0x180007209  mov     rcx, [rdi+30h]
0x18000720d  mov     [rsi+30h], rcx
0x180007211  xor     r13d, r13d
0x180007214  mov     [rdi+30h], r13
0x180007218  cmp     rsi, rdi
0x18000721b  jz      short loc_180007243
0x18000721d  mov     rcx, rsi
0x180007220  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007225  movups  xmm0, xmmword ptr [rdi]
0x180007228  movups  xmmword ptr [rsi], xmm0
0x18000722b  movups  xmm1, xmmword ptr [rdi+10h]
0x18000722f  movups  xmmword ptr [rsi+10h], xmm1
0x180007233  mov     [rdi+10h], r13
0x180007237  mov     qword ptr [rdi+18h], 7
0x18000723f  mov     [rdi], r13w
0x180007243  mov     eax, [rdi+20h]
0x180007246  mov     [rsi+20h], eax
0x180007249  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x180007250  mov     [rbp+140h+var_188], rax
0x180007254  lea     rcx, [rbp+140h+var_188]
0x180007258  call    ?Close@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::Close(void)
0x18000725d  lea     rcx, [rbp+140h+var_1B0]; this
0x180007261  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180007266  nop
0x180007267  call    cs:__imp_RevertToSelf
0x18000726d  lea     rdx, [rsp+240h+var_1D0]
0x180007272  mov     rcx, rsi
0x180007275  call    ?Body@HttpResponse@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HttpResponse::Body(void)
0x18000727a  mov     rbx, rax
0x18000727d  mov     [rsp+240h+var_1D8], rax
0x180007282  call    cs:__imp_XblaIsConsole
0x180007288  test    eax, eax
0x18000728a  jz      short loc_18000729E
0x18000728c  cmp     [rbx+10h], r13
0x180007290  jnz     short loc_18000729E
0x180007292  lea     rcx, [rsp+240h+var_1F0]; this
0x180007297  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x18000729c  jmp     short loc_1800072AC
0x18000729e  mov     rdx, rbx
0x1800072a1  lea     rcx, [rsp+240h+var_1F0]
0x1800072a6  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x1800072ab  nop
0x1800072ac  mov     rcx, rbx; this
0x1800072af  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800072b4  lea     rdx, [rsp+240h+var_1F0]
0x1800072b9  mov     rcx, r14
0x1800072bc  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800072c1  lea     rcx, [rsp+240h+var_1F0]; this
0x1800072c6  call    ??1value@json@web@@QEAA@XZ; web::json::value::~value(void)
0x1800072cb  call    cs:__imp_GetTickCount64
0x1800072d1  mov     rbx, rax
0x1800072d4  sub     rbx, [rsp+240h+var_1E0]
0x1800072d9  mov     rcx, rsi; this
0x1800072dc  call    ?StatusCode@HttpResponse@@QEBAKXZ; HttpResponse::StatusCode(void)
0x1800072e1  add     eax, 0FFFFFF38h
0x1800072e6  lea     r9, [rbp+140h+var_160]; struct HttpRequest *
0x1800072ea  mov     r8, [rsp+240h+var_1E8]; unsigned __int16 *
0x1800072ef  mov     rcx, r15; char *
0x1800072f2  cmp     eax, 63h ; 'c'
0x1800072f5  jbe     short loc_180007333
0x1800072f7  mov     [rsp+240h+var_208], r12; __int64
0x1800072fc  mov     [rsp+240h+var_210], rbx; int
0x180007301  mov     [rsp+240h+var_218], r14; __int64
0x180007306  mov     [rsp+240h+Format], rsi; int
0x18000730b  lea     rdx, aRequestlicense; "RequestLicense"
0x180007312  call    ?HandleFault@LicenseProxyService@@CAJPEBDPEBG1AEBVHttpRequest@@AEBVHttpResponse@@AEBVvalue@json@web@@_KAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@J@Z; LicenseProxyService::HandleFault(char const *,ushort const *,ushort const *,HttpRequest const &,HttpResponse const &,web::json::value const &,unsigned __int64,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &,long)
0x180007317  mov     rcx, [rbp+148h]; this
0x18000731e  mov     r9d, eax; char *
0x180007321  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180007328  mov     edx, 7FEh; void *
0x18000732d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007333  mov     [rsp+240h+var_210], rbx; unsigned __int64
0x180007338  mov     [rsp+240h+var_218], r14; struct web::json::value *
0x18000733d  mov     [rsp+240h+Format], rsi; struct HttpResponse *
0x180007342  call    ?LogRequestLicenseSuccess@@YAXPEBDPEBG1AEBVHttpRequest@@AEBVHttpResponse@@AEBVvalue@json@web@@_K@Z; LogRequestLicenseSuccess(char const *,ushort const *,ushort const *,HttpRequest const &,HttpResponse const &,web::json::value const &,unsigned __int64)
0x180007347  nop
0x180007348  lea     rcx, [rbp+140h+var_160]; this
0x18000734c  call    ??1HttpRequest@@QEAA@XZ; HttpRequest::~HttpRequest(void)
0x180007351  mov     rcx, [rbp+140h+var_48]
0x180007358  xor     rcx, rsp; StackCookie
0x18000735b  call    __security_check_cookie
0x180007360  add     rsp, 208h
0x180007367  pop     r15
0x180007369  pop     r14
0x18000736b  pop     r13
0x18000736d  pop     r12
0x18000736f  pop     rdi
0x180007370  pop     rsi
0x180007371  pop     rbx
0x180007372  pop     rbp
0x180007373  retn
```

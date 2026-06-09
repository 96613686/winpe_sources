# FetchUriResponseWithAuthTicket(TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,Windows::Data::Json::IJsonObject *,Http_Verb,bool,ushort const *,ushort const *,HSTRING__ * *)

- ea: `0x18007e714`
- end: `0x18007eea2`
- name: `?FetchUriResponseWithAuthTicket@@YAJPEAVTraceLoggingCorrelationVector@@PEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@PEAUIJsonObject@Json@Data@4@W4Http_Verb@@_NPEBG6PEAPEAU5@@Z`
- size: `1934`
- prototype: `int __high(struct TraceLoggingCorrelationVector *, struct Windows::Foundation::IUriRuntimeClass *, HSTRING, struct Windows::Data::Json::IJsonObject *, enum Http_Verb, bool, const unsigned __int16 *, const unsigned __int16 *, HSTRING *)`
- caller_count: `8`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003e698`
- `0x18007ca8c`
- `0x18007d288`
- `0x180080cb0`
- `0x1800b70e4`
- `0x1800b8010`
- `0x1800c9f54`
- `0x180191948`

## callees

- `0x180009ea0`
- `0x18001c108`
- `0x18001c414`
- `0x18001c964`
- `0x180020868`
- `0x180022298`
- `0x18002ec2c`
- `0x180034874`
- `0x1800364c0`
- `0x180037880`
- `0x18003814c`
- `0x18003f884`
- `0x18007e094`
- `0x18007e19c`
- `0x18007e234`
- `0x18007e264`
- `0x18007e2d8`
- `0x18007e714`
- `0x18007f7d8`
- `0x18007f9e4`
- `0x1800d5fa8`
- `0x1801483a4`
- `0x1801dbdac`
- `0x1801dc14c`
- `0x1801dc2b8`
- `0x1801dc454`
- `0x1801dd7ec`
- `0x1801ddbbc`
- `0x1801dde18`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007e77d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ee32`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007e77d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ee32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007ed88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007ed88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e835`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e984`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ea03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007eca5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007edc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ee04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e835`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e984`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ea03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007eca5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007edc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ee04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18007ec94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18007ec94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e9c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007eb5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ebca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ec0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e9c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007eb5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ebca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ec0b`

## string_xrefs

- `0x18007e7f8`: `onecoreuap\enduser\winstore\installservice\lib\httphelpers.cpp`
- `0x18007e863`: `onecoreuap\enduser\winstore\installservice\lib\httphelpers.cpp`
- `0x18007e9ab`: `onecoreuap\enduser\winstore\installservice\lib\httphelpers.cpp`
- `0x18007ed16`: `onecoreuap\enduser\winstore\installservice\lib\httphelpers.cpp`
- `0x18007ed9d`: `onecoreuap\enduser\winstore\installservice\lib\httphelpers.cpp`
- `0x18007e896`: `Install Service`
- `0x18007e95b`: `Install Service`
- `0x18007e7eb`: `FetchUriResponseWithAuthTicket`
- `0x18007ed09`: `FetchUriResponseWithAuthTicket`
- `0x18007eade`: `application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall FetchUriResponseWithAuthTicket(
        TraceLoggingCorrelationVector *a1,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        HSTRING a3,
        struct IInspectable *a4,
        int a5,
        char a6,
        __int64 a7,
        unsigned __int16 *a8,
        HSTRING *a9)
{
  const unsigned __int16 *v12; // r14
  __int64 (__fastcall *v13)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v14; // eax
  __int64 OsVersionHeader; // rax
  char v16; // bl
  const unsigned __int16 *v17; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v19; // rax
  int v20; // eax
  PCWSTR v21; // rax
  TraceLoggingCorrelationVector *v22; // r15
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r8
  PCWSTR v28; // rbx
  __int64 v29; // rax
  __int64 v30; // r8
  PCWSTR v31; // rdx
  PCWSTR v32; // rdx
  unsigned int v33; // eax
  unsigned int v34; // ecx
  unsigned int v35; // eax
  unsigned int v36; // esi
  HSTRING v37; // rbx
  UINT32 v38; // edi
  __int64 v39; // rax
  HRESULT v40; // eax
  const char *v41; // r9
  struct Windows::Foundation::IUriRuntimeClass *v42; // rbx
  ULONGLONG v43; // rax
  const char *v44; // r9
  unsigned int v46; // [rsp+20h] [rbp-398h]
  unsigned int v47; // [rsp+20h] [rbp-398h]
  unsigned int v48; // [rsp+28h] [rbp-390h]
  const char *v49; // [rsp+28h] [rbp-390h]
  HSTRING newString; // [rsp+50h] [rbp-368h] BYREF
  HSTRING string; // [rsp+58h] [rbp-360h] BYREF
  UINT32 v52; // [rsp+60h] [rbp-358h]
  const unsigned __int16 *v53; // [rsp+68h] [rbp-350h]
  TraceLoggingCorrelationVector *v54; // [rsp+70h] [rbp-348h]
  HSTRING *v55; // [rsp+78h] [rbp-340h]
  struct Windows::Foundation::IUriRuntimeClass *v56; // [rsp+80h] [rbp-338h]
  TraceLoggingCorrelationVector *v57; // [rsp+88h] [rbp-330h]
  struct Windows::Foundation::IUriRuntimeClass *v58; // [rsp+90h] [rbp-328h]
  ULONGLONG TickCount64; // [rsp+98h] [rbp-320h]
  _BYTE v60[32]; // [rsp+A0h] [rbp-318h] BYREF
  _BYTE v61[32]; // [rsp+C0h] [rbp-2F8h] BYREF
  _BYTE v62[32]; // [rsp+E0h] [rbp-2D8h] BYREF
  unsigned __int16 *v63[4]; // [rsp+100h] [rbp-2B8h] BYREF
  _BYTE v64[80]; // [rsp+120h] [rbp-298h] BYREF
  _BYTE v65[96]; // [rsp+170h] [rbp-248h] BYREF
  _BYTE v66[248]; // [rsp+1D0h] [rbp-1E8h] BYREF
  char v67[24]; // [rsp+2C8h] [rbp-F0h] BYREF
  char v68[144]; // [rsp+2E0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  v56 = a2;
  v54 = a1;
  v57 = a1;
  v58 = a2;
  v55 = a9;
  LODWORD(newString) = 0;
  *a9 = 0;
  TickCount64 = GetTickCount64();
  v52 = 0;
  v68[0] = 0;
  switch ( a5 )
  {
    case 0:
      v12 = L"GET";
      goto LABEL_8;
    case 1:
      v12 = L"POST";
      goto LABEL_8;
    case 2:
      v12 = L"PUT";
LABEL_8:
      v53 = v12;
      goto LABEL_9;
  }
  v12 = 0;
  v53 = 0;
  LogMessage(
    1u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\httphelpers.cpp",
    0xBEu,
    "FetchUriResponseWithAuthTicket",
    -1,
    L"Assert (%s): %s",
    0,
    0);
LABEL_9:
  string = 0;
  v13 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  try
  {
    string = 0;
    v14 = v13(a2, &string);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\httphelpers.cpp",
        (const char *)(unsigned int)v14,
        v46);
    if ( a6 )
    {
      OsVersionHeader = _GetOsVersionHeader(v61);
      v16 = 1;
    }
    else
    {
      OsVersionHeader = std::wstring::wstring(v60, L"Install Service");
      v16 = 2;
    }
    std::wstring::wstring(v63, OsVersionHeader);
    if ( (v16 & 2) != 0 )
    {
      v16 &= ~2u;
      std::wstring::_Tidy_deallocate(v60);
    }
    if ( (v16 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v61);
    v17 = (const unsigned __int16 *)v63;
    if ( v63[3] > (unsigned __int16 *)7 )
      v17 = v63[0];
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    HttpRequest::HttpRequest((HttpRequest *)v66, StringRawBuffer, v12, v17);
    if ( a6 )
    {
      std::wstring::wstring(v61, L"From");
      v19 = std::map<std::wstring,std::wstring>::operator[](v67, v61);
      std::wstring::_Assign<unsigned short>(v19, L"Install Service");
      std::wstring::_Tidy_deallocate(v61);
    }
    if ( a5 )
    {
      WindowsDeleteString(0);
      newString = 0;
      v20 = Json_Stringify(a4, &newString);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\httphelpers.cpp",
          (const char *)(unsigned int)v20,
          v46);
      v21 = WindowsGetStringRawBuffer(newString, 0);
      std::wstring::wstring(v61, v21);
      HttpRequest::SetBody((HttpRequest *)v66);
      std::wstring::_Tidy_deallocate(v61);
      WindowsDeleteString(newString);
    }
    v22 = v54;
    TraceLoggingCorrelationVector::Increment(v54, v68);
    std::string::string(v60, v68);
    v23 = ConvertToWide(v62, v60, 0);
    std::wstring::wstring(v61, L"MS-CV");
    v24 = std::map<std::wstring,std::wstring>::operator[](v67, v61);
    std::wstring::operator=(v24, v23);
    std::wstring::_Tidy_deallocate(v61);
    std::wstring::_Tidy_deallocate(v62);
    std::string::~string(v60);
    std::wstring::wstring(v60, L"Content-Type");
    v25 = std::map<std::wstring,std::wstring>::operator[](v67, v60);
    std::wstring::_Assign<unsigned short>(v25, L"application/json");
    std::wstring::_Tidy_deallocate(v60);
    if ( a7 )
    {
      std::wstring::wstring(v60, L"MS-CallerApplicationId");
      v26 = std::map<std::wstring,std::wstring>::operator[](v67, v60);
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)(a7 + 2 * v27) );
      std::wstring::_Assign<unsigned short>(v26, a7);
      std::wstring::_Tidy_deallocate(v60);
    }
    if ( a3 )
    {
      v28 = WindowsGetStringRawBuffer(a3, 0);
      std::wstring::wstring(v60, L"authorization");
      v29 = std::map<std::wstring,std::wstring>::operator[](v67, v60);
      v30 = -1;
      do
        ++v30;
      while ( v28[v30] );
      std::wstring::_Assign<unsigned short>(v29, v28);
      std::wstring::_Tidy_deallocate(v60);
    }
    ProxySettings::ProxySettings((ProxySettings *)v65);
    v31 = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v60, v31);
    ProxySettings::Capture(v65, v60);
    std::wstring::_Tidy_deallocate(v60);
    v32 = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v60, v32);
    SendRequestAndWaitForResponse((HttpResponse *)v64);
    std::wstring::_Tidy_deallocate(v60);
    v33 = HttpResponse::StatusCode((HttpResponse *)v64);
    v34 = v33 - 200;
    v35 = v33 | 0x80190000;
    v36 = 0;
    if ( v34 > 0x63 )
      v36 = v35;
    v37 = 0;
    v54 = 0;
    newString = 0;
    if ( WindowsSubstringWithSpecifiedLength(string, 8u, 8u, &newString) >= 0 )
    {
      v37 = newString;
      WindowsDeleteString(0);
      v54 = (TraceLoggingCorrelationVector *)v37;
    }
    if ( StringHelpers::Equal(v37, L"purchase", 1) )
    {
      HttpResponse::Body(v64, v62);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\httphelpers.cpp",
        0xFFu,
        "FetchUriResponseWithAuthTicket",
        -1,
        L"Purchase response body = %s",
        0,
        0);
      std::wstring::_Tidy_deallocate(v62);
    }
    v38 = *(_DWORD *)(HttpResponse::Body(v64, v62) + 16);
    v52 = v38;
    std::wstring::_Tidy_deallocate(v62);
    v39 = HttpResponse::Body(v64, v62);
    if ( *(_QWORD *)(v39 + 24) > 7u )
      v39 = *(_QWORD *)v39;
    v40 = WindowsCreateString((PCNZWCH)v39, v38, v55);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\httphelpers.cpp",
        (const char *)(unsigned int)v40,
        v46);
    std::wstring::_Tidy_deallocate(v62);
    WindowsDeleteString(v37);
    HttpResponse::~HttpResponse((HttpResponse *)v64);
    ProxySettings::~ProxySettings((ProxySettings *)v65);
    HttpRequest::~HttpRequest((HttpRequest *)v66);
    std::wstring::_Tidy_deallocate(v63);
    WindowsDeleteString(string);
    v42 = v56;
  }
  catch ( ... )
  {
    LODWORD(newString) = wil::details::in1diag3::Log_CaughtException(
                           retaddr,
                           (void *)0x107,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\httphelpers.cpp",
                           v41);
    v36 = (unsigned int)newString;
    v38 = v52;
    v12 = v53;
    v22 = v57;
    v42 = v58;
  }
  v43 = GetTickCount64();
  WindowsUpdate::CommonTelemetry::LogGetProductData(
    v42,
    v22,
    (struct TraceLoggingCorrelationVector *)(v43 - TickCount64),
    v36,
    v38,
    v48);
  _LogHttpResultHelper(v42, v12, v36, v44, v47, v49, v68, a8);
  return v36;
}

```

## disassembly

```asm
0x18007e714  push    rbx
0x18007e716  push    rsi
0x18007e717  push    rdi
0x18007e718  push    r12
0x18007e71a  push    r13
0x18007e71c  push    r14
0x18007e71e  push    r15
0x18007e720  sub     rsp, 380h
0x18007e727  mov     rax, cs:__security_cookie
0x18007e72e  xor     rax, rsp
0x18007e731  mov     [rsp+3B8h+var_48], rax
0x18007e739  mov     r15, r9
0x18007e73c  mov     r13, r8
0x18007e73f  mov     rdi, rdx
0x18007e742  mov     [rsp+3B8h+var_338], rdx
0x18007e74a  mov     [rsp+3B8h+var_348], rcx
0x18007e74f  mov     r12, [rsp+3B8h+arg_30]
0x18007e757  mov     [rsp+3B8h+var_330], rcx
0x18007e75f  mov     [rsp+3B8h+var_328], rdx
0x18007e767  mov     rax, [rsp+3B8h+arg_40]
0x18007e76f  mov     [rsp+3B8h+var_340], rax
0x18007e774  xor     ebx, ebx
0x18007e776  mov     dword ptr [rsp+3B8h+newString], ebx
0x18007e77a  mov     [rax], rbx
0x18007e77d  call    cs:__imp_GetTickCount64
0x18007e783  mov     [rsp+3B8h+var_320], rax
0x18007e78b  mov     [rsp+3B8h+var_358], ebx
0x18007e78f  mov     [rsp+3B8h+var_D8], bl
0x18007e796  mov     esi, [rsp+3B8h+arg_20]
0x18007e79d  mov     edx, esi
0x18007e79f  test    esi, esi
0x18007e7a1  jz      short loc_18007E81B
0x18007e7a3  sub     edx, 1
0x18007e7a6  jz      short loc_18007E812
0x18007e7a8  cmp     edx, 1
0x18007e7ab  jz      short loc_18007E809
0x18007e7ad  mov     r14d, ebx
0x18007e7b0  mov     [rsp+3B8h+var_350], rbx
0x18007e7b5  lea     rax, aFailed_1; "Failed"
0x18007e7bc  mov     [rsp+3B8h+var_370], rax
0x18007e7c1  lea     rax, aUnsupportedHtt; "!\"Unsupported Http_Verb - please add\""
0x18007e7c8  mov     [rsp+3B8h+var_378], rax
0x18007e7cd  mov     [rsp+3B8h+var_380], rbx; unsigned __int16 *
0x18007e7d2  mov     [rsp+3B8h+var_388], rbx; char *
0x18007e7d7  lea     rax, aAssertSS; "Assert (%s): %s"
0x18007e7de  mov     [rsp+3B8h+var_390], rax; unsigned __int16 *
0x18007e7e3  mov     [rsp+3B8h+var_398], 0FFFFFFFFh; int
0x18007e7eb  lea     r9, aFetchurirespon; "FetchUriResponseWithAuthTicket"
0x18007e7f2  mov     r8d, 0BEh; unsigned int
0x18007e7f8  lea     rdx, aOnecoreuapEndu_62; "onecoreuap\\enduser\\winstore\\installs"...
0x18007e7ff  lea     ecx, [rbx+1]; unsigned int
0x18007e802  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18007e807  jmp     short loc_18007E827
0x18007e809  lea     r14, aPut; "PUT"
0x18007e810  jmp     short loc_18007E822
0x18007e812  lea     r14, aPost; "POST"
0x18007e819  jmp     short loc_18007E822
0x18007e81b  lea     r14, aGet; "GET"
0x18007e822  mov     [rsp+3B8h+var_350], r14
0x18007e827  mov     [rsp+3B8h+string], rbx
0x18007e82c  mov     rax, [rdi]
0x18007e82f  mov     rbx, [rax+30h]
0x18007e833  xor     ecx, ecx; string
0x18007e835  call    cs:__imp_WindowsDeleteString
0x18007e83b  mov     [rsp+3B8h+string], 0
0x18007e844  lea     rdx, [rsp+3B8h+string]
0x18007e849  mov     rcx, rdi
0x18007e84c  mov     rax, rbx
0x18007e84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e854  mov     rcx, [rsp+3B8h]; this
0x18007e85c  test    eax, eax
0x18007e85e  jns     short loc_18007E874
0x18007e860  mov     r9d, eax; char *
0x18007e863  lea     r8, aOnecoreuapEndu_62; "onecoreuap\\enduser\\winstore\\installs"...
0x18007e86a  mov     edx, 0C6h; void *
0x18007e86f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e874  mov     dil, [rsp+3B8h+arg_28]
0x18007e87c  test    dil, dil
0x18007e87f  jz      short loc_18007E896
0x18007e881  lea     rcx, [rsp+3B8h+var_2F8]
0x18007e889  call    ?_GetOsVersionHeader@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; _GetOsVersionHeader(void)
0x18007e88e  nop
0x18007e88f  mov     ebx, 1
0x18007e894  jmp     short loc_18007E8AF
0x18007e896  lea     rdx, aInstallService; "Install Service"
0x18007e89d  lea     rcx, [rsp+3B8h+var_318]
0x18007e8a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007e8aa  mov     ebx, 2
0x18007e8af  mov     rdx, rax
0x18007e8b2  lea     rcx, [rsp+3B8h+var_2B8]
0x18007e8ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18007e8bf  nop
0x18007e8c0  test    bl, 2
0x18007e8c3  jz      short loc_18007E8D6
0x18007e8c5  and     ebx, 0FFFFFFFDh
0x18007e8c8  lea     rcx, [rsp+3B8h+var_318]
0x18007e8d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e8d5  nop
0x18007e8d6  test    bl, 1
0x18007e8d9  jz      short loc_18007E8E8
0x18007e8db  lea     rcx, [rsp+3B8h+var_2F8]
0x18007e8e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e8e8  lea     rbx, [rsp+3B8h+var_2B8]
0x18007e8f0  cmp     [rsp+3B8h+var_2A0], 7
0x18007e8f9  cmova   rbx, [rsp+3B8h+var_2B8]
0x18007e902  xor     edx, edx; length
0x18007e904  mov     rcx, [rsp+3B8h+string]; string
0x18007e909  call    cs:__imp_WindowsGetStringRawBuffer
0x18007e90f  mov     r9, rbx; unsigned __int16 *
0x18007e912  mov     r8, r14; unsigned __int16 *
0x18007e915  mov     rdx, rax; unsigned __int16 *
0x18007e918  lea     rcx, [rsp+3B8h+var_1E8]; this
0x18007e920  call    ??0HttpRequest@@QEAA@PEBG00@Z; HttpRequest::HttpRequest(ushort const *,ushort const *,ushort const *)
0x18007e925  nop
0x18007e926  test    dil, dil
0x18007e929  jz      short loc_18007E978
0x18007e92b  lea     rdx, aFrom; "From"
0x18007e932  lea     rcx, [rsp+3B8h+var_2F8]
0x18007e93a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007e93f  nop
0x18007e940  lea     rdx, [rsp+3B8h+var_2F8]
0x18007e948  lea     rcx, [rsp+3B8h+var_F0]
0x18007e950  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18007e955  mov     r8d, 0Fh
0x18007e95b  lea     rdx, aInstallService; "Install Service"
0x18007e962  mov     rcx, rax
0x18007e965  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007e96a  nop
0x18007e96b  lea     rcx, [rsp+3B8h+var_2F8]
0x18007e973  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e978  xor     edi, edi
0x18007e97a  test    esi, esi
0x18007e97c  jz      loc_18007EA09
0x18007e982  xor     ecx, ecx; string
0x18007e984  call    cs:__imp_WindowsDeleteString
0x18007e98a  mov     [rsp+3B8h+newString], rdi
0x18007e98f  lea     rdx, [rsp+3B8h+newString]; HSTRING *
0x18007e994  mov     rcx, r15; struct IInspectable *
0x18007e997  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x18007e99c  mov     rcx, [rsp+3B8h]; this
0x18007e9a4  test    eax, eax
0x18007e9a6  jns     short loc_18007E9BC
0x18007e9a8  mov     r9d, eax; char *
0x18007e9ab  lea     r8, aOnecoreuapEndu_62; "onecoreuap\\enduser\\winstore\\installs"...
0x18007e9b2  mov     edx, 0D9h; void *
0x18007e9b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e9bc  xor     edx, edx; length
0x18007e9be  mov     rcx, [rsp+3B8h+newString]; string
0x18007e9c3  call    cs:__imp_WindowsGetStringRawBuffer
0x18007e9c9  mov     rdx, rax
0x18007e9cc  lea     rcx, [rsp+3B8h+var_2F8]
0x18007e9d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007e9d9  nop
0x18007e9da  lea     rdx, [rsp+3B8h+var_2F8]
0x18007e9e2  lea     rcx, [rsp+3B8h+var_1E8]
0x18007e9ea  call    ?SetBody@HttpRequest@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; HttpRequest::SetBody(std::wstring const &,bool)
0x18007e9ef  nop
0x18007e9f0  lea     rcx, [rsp+3B8h+var_2F8]
0x18007e9f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e9fd  nop
0x18007e9fe  mov     rcx, [rsp+3B8h+newString]; string
0x18007ea03  call    cs:__imp_WindowsDeleteString
0x18007ea09  lea     rdx, [rsp+3B8h+var_D8]; char *
0x18007ea11  mov     r15, [rsp+3B8h+var_348]
0x18007ea16  mov     rcx, r15; this
0x18007ea19  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18007ea1e  lea     rdx, [rsp+3B8h+var_D8]
0x18007ea26  lea     rcx, [rsp+3B8h+var_318]
0x18007ea2e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007ea33  nop
0x18007ea34  xor     r8d, r8d
0x18007ea37  lea     rdx, [rsp+3B8h+var_318]
0x18007ea3f  lea     rcx, [rsp+3B8h+var_2D8]
0x18007ea47  call    ?ConvertToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@I@Z; ConvertToWide(std::string const &,uint)
0x18007ea4c  mov     rbx, rax
0x18007ea4f  lea     rdx, aMsCv; "MS-CV"
0x18007ea56  lea     rcx, [rsp+3B8h+var_2F8]
0x18007ea5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007ea63  nop
0x18007ea64  lea     rdx, [rsp+3B8h+var_2F8]
0x18007ea6c  lea     rcx, [rsp+3B8h+var_F0]
0x18007ea74  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18007ea79  mov     rdx, rbx
0x18007ea7c  mov     rcx, rax
0x18007ea7f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007ea84  nop
0x18007ea85  lea     rcx, [rsp+3B8h+var_2F8]
0x18007ea8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ea92  nop
0x18007ea93  lea     rcx, [rsp+3B8h+var_2D8]
0x18007ea9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007eaa0  nop
0x18007eaa1  lea     rcx, [rsp+3B8h+var_318]
0x18007eaa9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18007eaae  lea     rdx, aContentType; "Content-Type"
0x18007eab5  lea     rcx, [rsp+3B8h+var_318]
0x18007eabd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007eac2  nop
0x18007eac3  lea     rdx, [rsp+3B8h+var_318]
0x18007eacb  lea     rcx, [rsp+3B8h+var_F0]
0x18007ead3  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18007ead8  mov     r8d, 10h
0x18007eade  lea     rdx, aApplicationJso; "application/json"
0x18007eae5  mov     rcx, rax
0x18007eae8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007eaed  nop
0x18007eaee  lea     rcx, [rsp+3B8h+var_318]
0x18007eaf6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007eafb  test    r12, r12
0x18007eafe  jz      short loc_18007EB51
0x18007eb00  lea     rdx, aMsCallerapplic; "MS-CallerApplicationId"
0x18007eb07  lea     rcx, [rsp+3B8h+var_318]
0x18007eb0f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007eb14  nop
0x18007eb15  lea     rdx, [rsp+3B8h+var_318]
0x18007eb1d  lea     rcx, [rsp+3B8h+var_F0]
0x18007eb25  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18007eb2a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007eb2e  inc     r8
0x18007eb31  cmp     [r12+r8*2], di
0x18007eb36  jnz     short loc_18007EB2E
0x18007eb38  mov     rdx, r12
0x18007eb3b  mov     rcx, rax
0x18007eb3e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007eb43  nop
0x18007eb44  lea     rcx, [rsp+3B8h+var_318]
0x18007eb4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007eb51  test    r13, r13
0x18007eb54  jz      short loc_18007EBB5
0x18007eb56  xor     edx, edx; length
0x18007eb58  mov     rcx, r13; string
0x18007eb5b  call    cs:__imp_WindowsGetStringRawBuffer
0x18007eb61  mov     rbx, rax
0x18007eb64  lea     rdx, aAuthorization; "authorization"
0x18007eb6b  lea     rcx, [rsp+3B8h+var_318]
0x18007eb73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007eb78  nop
0x18007eb79  lea     rdx, [rsp+3B8h+var_318]
0x18007eb81  lea     rcx, [rsp+3B8h+var_F0]
0x18007eb89  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18007eb8e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007eb92  inc     r8
0x18007eb95  cmp     [rbx+r8*2], di
0x18007eb9a  jnz     short loc_18007EB92
0x18007eb9c  mov     rdx, rbx
0x18007eb9f  mov     rcx, rax
0x18007eba2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007eba7  nop
0x18007eba8  lea     rcx, [rsp+3B8h+var_318]
0x18007ebb0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ebb5  lea     rcx, [rsp+3B8h+var_248]; this
0x18007ebbd  call    ??0ProxySettings@@QEAA@XZ; ProxySettings::ProxySettings(void)
0x18007ebc2  nop
0x18007ebc3  xor     edx, edx; length
0x18007ebc5  mov     rcx, [rsp+3B8h+string]; string
0x18007ebca  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ebd0  mov     rdx, rax
0x18007ebd3  lea     rcx, [rsp+3B8h+var_318]
0x18007ebdb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007ebe0  nop
0x18007ebe1  lea     rdx, [rsp+3B8h+var_318]
0x18007ebe9  lea     rcx, [rsp+3B8h+var_248]
0x18007ebf1  call    ?Capture@ProxySettings@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProxySettings::Capture(std::wstring const &)
0x18007ebf6  nop
0x18007ebf7  lea     rcx, [rsp+3B8h+var_318]
0x18007ebff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ec04  xor     edx, edx; length
0x18007ec06  mov     rcx, [rsp+3B8h+string]; string
0x18007ec0b  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ec11  mov     rdx, rax
0x18007ec14  lea     rcx, [rsp+3B8h+var_318]
0x18007ec1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007ec21  nop
0x18007ec22  lea     r9, [rsp+3B8h+var_1E8]
0x18007ec2a  lea     r8, [rsp+3B8h+var_248]
0x18007ec32  lea     rdx, [rsp+3B8h+var_318]
0x18007ec3a  lea     rcx, [rsp+3B8h+var_298]; this
0x18007ec42  call    ?SendRequestAndWaitForResponse@@YA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z; SendRequestAndWaitForResponse(std::wstring const &,ProxySettings const &,HttpRequest &)
0x18007ec47  nop
0x18007ec48  lea     rcx, [rsp+3B8h+var_318]
0x18007ec50  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ec55  lea     rcx, [rsp+3B8h+var_298]; this
0x18007ec5d  call    ?StatusCode@HttpResponse@@QEBAKXZ; HttpResponse::StatusCode(void)
0x18007ec62  lea     ecx, [rax-0C8h]
0x18007ec68  or      eax, 80190000h
0x18007ec6d  mov     esi, edi
0x18007ec6f  cmp     ecx, 63h ; 'c'
0x18007ec72  cmova   esi, eax
0x18007ec75  mov     rbx, rdi
0x18007ec78  mov     [rsp+3B8h+var_348], rbx
0x18007ec7d  mov     [rsp+3B8h+newString], rdi
0x18007ec82  lea     r9, [rsp+3B8h+newString]; newString
0x18007ec87  mov     edx, 8; startIndex
0x18007ec8c  mov     r8d, edx; length
0x18007ec8f  mov     rcx, [rsp+3B8h+string]; string
0x18007ec94  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18007ec9a  test    eax, eax
0x18007ec9c  js      short loc_18007ECB0
0x18007ec9e  mov     rbx, [rsp+3B8h+newString]
0x18007eca3  xor     ecx, ecx; string
  ... truncated ...
```

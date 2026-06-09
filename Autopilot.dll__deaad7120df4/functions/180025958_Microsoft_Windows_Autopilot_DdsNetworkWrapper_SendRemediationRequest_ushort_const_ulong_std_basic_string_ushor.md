# Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendRemediationRequest(ushort const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *)

- ea: `0x180025958`
- end: `0x180025e6d`
- name: `?SendRemediationRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@@Z`
- size: `1301`
- prototype: `__int64 __fastcall(HINTERNET *this, LPCWSTR pwszObjectName, DWORD dwFlags, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180024878`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010744`
- `0x180010764`
- `0x180018678`
- `0x18001f030`
- `0x18001ff1c`
- `0x1800215e4`
- `0x180022fa0`
- `0x180025958`
- `0x180025f90`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025cb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800259ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800259ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025bee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025bee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025bb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025cfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025bb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025cfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025e1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ce6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025dba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025c3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ce6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025dba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e05`
- `WINHTTP!WinHttpCloseHandle` at `0x1800259de`
- `WINHTTP!WinHttpCloseHandle` at `0x1800259de`
- `WINHTTP!WinHttpOpenRequest` at `0x1800259b5`
- `WINHTTP!WinHttpOpenRequest` at `0x1800259b5`
- `WINHTTP!WinHttpSendRequest` at `0x180025ca3`
- `WINHTTP!WinHttpSendRequest` at `0x180025ca3`
- `DMCmnUtils!UnicodeToMB` at `0x180025c0a`
- `DMCmnUtils!UnicodeToMB` at `0x180025c0a`

## string_xrefs

- `0x180025a9d`: `Windows.Data.Json.JsonObject`
- `0x180025a2b`: `X-Device-Token`
- `0x180025a08`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025a45`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025aef`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025b4a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025b99`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025c23`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025d2a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025d9f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025c98`: `content-type:application/json; charset=utf-8`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendRemediationRequest(
        HINTERNET *this,
        LPCWSTR pwszObjectName,
        DWORD dwFlags,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  const unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // r14
  const char *v10; // r9
  HINTERNET v11; // r12
  void *v12; // r13
  DWORD LastError; // ebx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  HRESULT v17; // eax
  int v18; // eax
  struct Windows::Data::Json::IJsonObject *v19; // rcx
  int v20; // eax
  struct Windows::Data::Json::IJsonObject *v21; // rcx
  int v22; // eax
  struct Windows::Data::Json::IJsonObject *v23; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  int v25; // eax
  struct Windows::Data::Json::IJsonObject *v26; // rcx
  signed int v27; // eax
  struct Windows::Data::Json::IJsonObject *v28; // rcx
  struct Windows::Data::Json::IJsonObject *v29; // rdx
  int v30; // eax
  struct Windows::Data::Json::IJsonObject *v31; // rcx
  struct Windows::Data::Json::IJsonObject *v32; // rcx
  struct Windows::Data::Json::IJsonObject *v33; // [rsp+40h] [rbp-51h] BYREF
  HSTRING v34; // [rsp+48h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-41h] BYREF
  DWORD dwOptionalLength; // [rsp+58h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-31h] BYREF
  HSTRING string; // [rsp+78h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v8 = a6;
  v9 = a5;
  v11 = WinHttpOpenRequest(this[9], L"PATCH", pwszObjectName, 0, 0, 0, dwFlags);
  v12 = this[10];
  if ( v12 )
  {
    LastError = GetLastError();
    WinHttpCloseHandle(v12);
    SetLastError(LastError);
  }
  this[10] = v11;
  if ( !v11 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x213,
             (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v10);
  if ( *((_QWORD *)a4 + 3) > 7u )
    a4 = *(unsigned __int16 **)a4;
  v15 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(this, L"X-Device-Token", a4);
  if ( (v15 & 0x80000000) != 0 )
  {
    v16 = 534;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)v15);
    return v15;
  }
  if ( *((_QWORD *)a5 + 3) > 7u )
    v9 = *(const unsigned __int16 **)a5;
  v15 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(this, L"MS-CV", v9);
  if ( (v15 & 0x80000000) != 0 )
  {
    v16 = 537;
    goto LABEL_9;
  }
  v33 = 0;
  string = 0;
  v17 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17);
    JUMPOUT(0x180025E6CLL);
  }
  v18 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)string, &v33);
  v15 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x226,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v18);
    v19 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return v15;
  }
  if ( *((_QWORD *)a6 + 3) > 7u )
    v8 = *(const unsigned __int16 **)a6;
  v20 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v33, L"HardwareMismatchRemediationData", v8);
  v15 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x227,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v20);
    v21 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v15;
  }
  v34 = 0;
  v22 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v33, &v34);
  v15 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v22);
    if ( v34 )
      WindowsDeleteString(v34);
    v23 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v15;
  }
  dwOptionalLength = 0;
  hMem = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
  v25 = UnicodeToMB(StringRawBuffer, 0xFDE9u, (char **)&hMem, &dwOptionalLength);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v25);
    if ( hMem )
      LocalFree(hMem);
    if ( v34 )
      WindowsDeleteString(v34);
    v26 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return v15;
  }
  if ( !WinHttpSendRequest(
          this[10],
          L"content-type:application/json; charset=utf-8",
          0xFFFFFFFF,
          hMem,
          dwOptionalLength,
          dwOptionalLength,
          0) )
  {
    v27 = GetLastError();
    v15 = v27;
    if ( v27 > 0 )
      v15 = (unsigned __int16)v27 | 0x80070000;
    if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v15) )
    {
      if ( hMem )
        LocalFree(hMem);
      if ( v34 )
        WindowsDeleteString(v34);
      v28 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    else
    {
      if ( (v15 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23E,
          (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
          (const char *)v15);
      if ( hMem )
        LocalFree(hMem);
      if ( v34 )
        WindowsDeleteString(v34);
      v29 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v29 + 16LL))(v29);
      }
    }
    return v15;
  }
  v30 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this);
  v15 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v30);
    if ( hMem )
      LocalFree(hMem);
    if ( v34 )
      WindowsDeleteString(v34);
    v31 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return v15;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v34 )
    WindowsDeleteString(v34);
  v32 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return 0;
}

```

## disassembly

```asm
0x180025958  push    rbp
0x18002595a  push    rbx
0x18002595b  push    rsi
0x18002595c  push    rdi
0x18002595d  push    r12
0x18002595f  push    r13
0x180025961  push    r14
0x180025963  push    r15
0x180025965  lea     rbp, [rsp-7]
0x18002596a  sub     rsp, 98h
0x180025971  mov     rax, cs:__security_cookie
0x180025978  xor     rax, rsp
0x18002597b  mov     [rbp+3Fh+var_50], rax
0x18002597f  mov     r15, r9
0x180025982  mov     rdi, rcx
0x180025985  mov     rsi, [rbp+3Fh+arg_28]
0x180025989  mov     r14, [rbp+3Fh+arg_20]
0x18002598d  mov     [rsp+0D0h+dwFlags], r8d; dwFlags
0x180025992  mov     [rsp+0D0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18002599b  mov     [rsp+0D0h+pwszReferrer], 0; int
0x1800259a4  xor     r9d, r9d; pwszVersion
0x1800259a7  mov     r8, rdx; pwszObjectName
0x1800259aa  lea     rdx, pwszVerb; "PATCH"
0x1800259b1  mov     rcx, [rcx+48h]; hConnect
0x1800259b5  call    cs:__imp_WinHttpOpenRequest
0x1800259bc  nop     dword ptr [rax+rax+00h]
0x1800259c1  mov     r12, rax
0x1800259c4  mov     r13, [rdi+50h]
0x1800259c8  test    r13, r13
0x1800259cb  jz      short loc_1800259F8
0x1800259cd  call    cs:__imp_GetLastError
0x1800259d4  nop     dword ptr [rax+rax+00h]
0x1800259d9  mov     ebx, eax
0x1800259db  mov     rcx, r13; hInternet
0x1800259de  call    cs:__imp_WinHttpCloseHandle
0x1800259e5  nop     dword ptr [rax+rax+00h]
0x1800259ea  mov     ecx, ebx; dwErrCode
0x1800259ec  call    cs:__imp_SetLastError
0x1800259f3  nop     dword ptr [rax+rax+00h]
0x1800259f8  mov     [rdi+50h], r12
0x1800259fc  xor     r13d, r13d
0x1800259ff  test    r12, r12
0x180025a02  jnz     short loc_180025A1E
0x180025a04  mov     rcx, [rbp+47h]; this
0x180025a08  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025a0f  mov     edx, 213h; void *
0x180025a14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025a19  jmp     loc_180025E44
0x180025a1e  cmp     qword ptr [r15+18h], 7
0x180025a23  jbe     short loc_180025A28
0x180025a25  mov     r15, [r15]
0x180025a28  mov     r8, r15; unsigned __int16 *
0x180025a2b  lea     rdx, aXDeviceToken; "X-Device-Token"
0x180025a32  mov     rcx, rdi; this
0x180025a35  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x180025a3a  mov     ebx, eax
0x180025a3c  test    eax, eax
0x180025a3e  jns     short loc_180025A5F
0x180025a40  mov     edx, 216h; void *
0x180025a45  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025a4c  mov     r9d, ebx; char *
0x180025a4f  mov     rcx, [rbp+47h]; this
0x180025a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025a58  mov     eax, ebx
0x180025a5a  jmp     loc_180025E44
0x180025a5f  cmp     qword ptr [r14+18h], 7
0x180025a64  jbe     short loc_180025A69
0x180025a66  mov     r14, [r14]
0x180025a69  mov     r8, r14; unsigned __int16 *
0x180025a6c  lea     rdx, aMsCv; "MS-CV"
0x180025a73  mov     rcx, rdi; this
0x180025a76  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x180025a7b  mov     ebx, eax
0x180025a7d  test    eax, eax
0x180025a7f  jns     short loc_180025A88
0x180025a81  mov     edx, 219h
0x180025a86  jmp     short loc_180025A45
0x180025a88  mov     [rbp+3Fh+var_90], r13
0x180025a8c  mov     [rbp+3Fh+string], r13
0x180025a90  lea     r9, [rbp+3Fh+string]; string
0x180025a94  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x180025a98  mov     edx, 1Ch; length
0x180025a9d  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180025aa4  call    cs:__imp_WindowsCreateStringReference
0x180025aab  nop     dword ptr [rax+rax+00h]
0x180025ab0  test    eax, eax
0x180025ab2  js      loc_180025E65
0x180025ab8  mov     rbx, [rbp+3Fh+string]
0x180025abc  mov     rcx, [rbp+3Fh+var_90]
0x180025ac0  test    rcx, rcx
0x180025ac3  jz      short loc_180025AD6
0x180025ac5  mov     [rbp+3Fh+var_90], r13
0x180025ac9  mov     rax, [rcx]
0x180025acc  mov     rax, [rax+10h]
0x180025ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ad5  nop
0x180025ad6  lea     rdx, [rbp+3Fh+var_90]
0x180025ada  mov     rcx, rbx
0x180025add  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180025ae2  mov     ebx, eax
0x180025ae4  test    eax, eax
0x180025ae6  jns     short loc_180025B20
0x180025ae8  mov     rcx, [rbp+47h]; this
0x180025aec  mov     r9d, eax; char *
0x180025aef  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025af6  mov     edx, 226h; void *
0x180025afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b00  nop
0x180025b01  mov     rcx, [rbp+3Fh+var_90]
0x180025b05  test    rcx, rcx
0x180025b08  jz      short loc_180025B1B
0x180025b0a  mov     [rbp+3Fh+var_90], r13
0x180025b0e  mov     rax, [rcx]
0x180025b11  mov     rax, [rax+10h]
0x180025b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b1a  nop
0x180025b1b  jmp     loc_180025A58
0x180025b20  cmp     qword ptr [rsi+18h], 7
0x180025b25  jbe     short loc_180025B2A
0x180025b27  mov     rsi, [rsi]
0x180025b2a  mov     r8, rsi; unsigned __int16 *
0x180025b2d  lea     rdx, aHardwaremismat; "HardwareMismatchRemediationData"
0x180025b34  mov     rcx, [rbp+3Fh+var_90]; struct Windows::Data::Json::IJsonObject *
0x180025b38  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180025b3d  mov     ebx, eax
0x180025b3f  test    eax, eax
0x180025b41  jns     short loc_180025B7B
0x180025b43  mov     rcx, [rbp+47h]; this
0x180025b47  mov     r9d, eax; char *
0x180025b4a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025b51  mov     edx, 227h; void *
0x180025b56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b5b  nop
0x180025b5c  mov     rcx, [rbp+3Fh+var_90]
0x180025b60  test    rcx, rcx
0x180025b63  jz      short loc_180025B76
0x180025b65  mov     [rbp+3Fh+var_90], r13
0x180025b69  mov     rax, [rcx]
0x180025b6c  mov     rax, [rax+10h]
0x180025b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b75  nop
0x180025b76  jmp     loc_180025A58
0x180025b7b  mov     [rbp+3Fh+var_88], r13
0x180025b7f  lea     rdx, [rbp+3Fh+var_88]
0x180025b83  mov     rcx, [rbp+3Fh+var_90]
0x180025b87  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180025b8c  mov     ebx, eax
0x180025b8e  test    eax, eax
0x180025b90  jns     short loc_180025BE0
0x180025b92  mov     rcx, [rbp+47h]; this
0x180025b96  mov     r9d, eax; char *
0x180025b99  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025ba0  mov     edx, 22Ah; void *
0x180025ba5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025baa  nop
0x180025bab  mov     rcx, [rbp+3Fh+var_88]; string
0x180025baf  test    rcx, rcx
0x180025bb2  jz      short loc_180025BC1
0x180025bb4  call    cs:__imp_WindowsDeleteString
0x180025bbb  nop     dword ptr [rax+rax+00h]
0x180025bc0  nop
0x180025bc1  mov     rcx, [rbp+3Fh+var_90]
0x180025bc5  test    rcx, rcx
0x180025bc8  jz      short loc_180025BDB
0x180025bca  mov     [rbp+3Fh+var_90], r13
0x180025bce  mov     rax, [rcx]
0x180025bd1  mov     rax, [rax+10h]
0x180025bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bda  nop
0x180025bdb  jmp     loc_180025A58
0x180025be0  mov     [rbp+3Fh+dwOptionalLength], r13d
0x180025be4  mov     [rbp+3Fh+hMem], r13
0x180025be8  xor     edx, edx; length
0x180025bea  mov     rcx, [rbp+3Fh+var_88]; string
0x180025bee  call    cs:__imp_WindowsGetStringRawBuffer
0x180025bf5  nop     dword ptr [rax+rax+00h]
0x180025bfa  lea     r9, [rbp+3Fh+dwOptionalLength]
0x180025bfe  lea     r8, [rbp+3Fh+hMem]
0x180025c02  mov     edx, 0FDE9h
0x180025c07  mov     rcx, rax
0x180025c0a  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180025c11  nop     dword ptr [rax+rax+00h]
0x180025c16  mov     ebx, eax
0x180025c18  test    eax, eax
0x180025c1a  jns     short loc_180025C80
0x180025c1c  mov     rcx, [rbp+47h]; this
0x180025c20  mov     r9d, eax; char *
0x180025c23  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025c2a  mov     edx, 232h; void *
0x180025c2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c34  nop
0x180025c35  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180025c39  test    rcx, rcx
0x180025c3c  jz      short loc_180025C4B
0x180025c3e  call    cs:__imp_LocalFree
0x180025c45  nop     dword ptr [rax+rax+00h]
0x180025c4a  nop
0x180025c4b  mov     rcx, [rbp+3Fh+var_88]; string
0x180025c4f  test    rcx, rcx
0x180025c52  jz      short loc_180025C61
0x180025c54  call    cs:__imp_WindowsDeleteString
0x180025c5b  nop     dword ptr [rax+rax+00h]
0x180025c60  nop
0x180025c61  mov     rcx, [rbp+3Fh+var_90]
0x180025c65  test    rcx, rcx
0x180025c68  jz      short loc_180025C7B
0x180025c6a  mov     [rbp+3Fh+var_90], r13
0x180025c6e  mov     rax, [rcx]
0x180025c71  mov     rax, [rax+10h]
0x180025c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c7a  nop
0x180025c7b  jmp     loc_180025A58
0x180025c80  mov     eax, [rbp+3Fh+dwOptionalLength]
0x180025c83  mov     qword ptr [rsp+0D0h+dwFlags], r13; dwContext
0x180025c88  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], eax; dwTotalLength
0x180025c8c  mov     dword ptr [rsp+0D0h+pwszReferrer], eax; int
0x180025c90  mov     r9, [rbp+3Fh+hMem]; lpOptional
0x180025c94  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180025c98  lea     rdx, szHeaders; "content-type:application/json; charset="...
0x180025c9f  mov     rcx, [rdi+50h]; hRequest
0x180025ca3  call    cs:__imp_WinHttpSendRequest
0x180025caa  nop     dword ptr [rax+rax+00h]
0x180025caf  test    eax, eax
0x180025cb1  jnz     loc_180025D8A
0x180025cb7  call    cs:__imp_GetLastError
0x180025cbe  nop     dword ptr [rax+rax+00h]
0x180025cc3  mov     ebx, eax
0x180025cc5  test    eax, eax
0x180025cc7  jle     short loc_180025CD2
0x180025cc9  movzx   ebx, ax
0x180025ccc  or      ebx, 80070000h
0x180025cd2  mov     ecx, ebx; int
0x180025cd4  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180025cd9  test    al, al
0x180025cdb  jz      short loc_180025D1F
0x180025cdd  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180025ce1  test    rcx, rcx
0x180025ce4  jz      short loc_180025CF3
0x180025ce6  call    cs:__imp_LocalFree
0x180025ced  nop     dword ptr [rax+rax+00h]
0x180025cf2  nop
0x180025cf3  mov     rcx, [rbp+3Fh+var_88]; string
0x180025cf7  test    rcx, rcx
0x180025cfa  jz      short loc_180025D09
0x180025cfc  call    cs:__imp_WindowsDeleteString
0x180025d03  nop     dword ptr [rax+rax+00h]
0x180025d08  nop
0x180025d09  mov     rcx, [rbp+3Fh+var_90]
0x180025d0d  test    rcx, rcx
0x180025d10  jz      short loc_180025D85
0x180025d12  mov     [rbp+3Fh+var_90], r13
0x180025d16  mov     rax, [rcx]
0x180025d19  mov     rax, [rax+10h]
0x180025d1d  jmp     short loc_180025D7F
0x180025d1f  test    ebx, ebx
0x180025d21  jns     short loc_180025D3C
0x180025d23  mov     rcx, [rbp+47h]; this
0x180025d27  mov     r9d, ebx; char *
0x180025d2a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025d31  mov     edx, 23Eh; void *
0x180025d36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025d3b  nop
0x180025d3c  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180025d40  test    rcx, rcx
0x180025d43  jz      short loc_180025D52
0x180025d45  call    cs:__imp_LocalFree
0x180025d4c  nop     dword ptr [rax+rax+00h]
0x180025d51  nop
0x180025d52  mov     rcx, [rbp+3Fh+var_88]; string
0x180025d56  test    rcx, rcx
0x180025d59  jz      short loc_180025D68
0x180025d5b  call    cs:__imp_WindowsDeleteString
0x180025d62  nop     dword ptr [rax+rax+00h]
0x180025d67  nop
0x180025d68  mov     rdx, [rbp+3Fh+var_90]
0x180025d6c  test    rdx, rdx
0x180025d6f  jz      short loc_180025D85
0x180025d71  mov     [rbp+3Fh+var_90], r13
0x180025d75  mov     rcx, [rdx]
0x180025d78  mov     rax, [rcx+10h]
0x180025d7c  mov     rcx, rdx
0x180025d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d84  nop
0x180025d85  jmp     loc_180025A58
0x180025d8a  mov     rcx, rdi; this
0x180025d8d  call    ?VerifyResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(void)
0x180025d92  mov     ebx, eax
0x180025d94  test    eax, eax
0x180025d96  jns     short loc_180025DFC
0x180025d98  mov     rcx, [rbp+47h]; this
0x180025d9c  mov     r9d, eax; char *
0x180025d9f  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025da6  mov     edx, 241h; void *
0x180025dab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025db0  nop
0x180025db1  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180025db5  test    rcx, rcx
0x180025db8  jz      short loc_180025DC7
0x180025dba  call    cs:__imp_LocalFree
0x180025dc1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

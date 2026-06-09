# Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendRemediationRequest(ushort const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *)

- ea: `0x180024c34`
- end: `0x1800250d0`
- name: `?SendRemediationRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this, LPCWSTR pwszObjectName, DWORD dwFlags, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180023cb0`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105d4`
- `0x1800105f4`
- `0x180018120`
- `0x18001e7b4`
- `0x18001f638`
- `0x180020bd0`
- `0x1800224d4`
- `0x180024c34`
- `0x1800251d0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024cb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ea6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ea6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024efa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025085`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024efa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025085`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025075`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025075`
- `WINHTTP!WinHttpCloseHandle` at `0x180024cae`
- `WINHTTP!WinHttpCloseHandle` at `0x180024cae`
- `WINHTTP!WinHttpOpenRequest` at `0x180024c91`
- `WINHTTP!WinHttpOpenRequest` at `0x180024c91`
- `WINHTTP!WinHttpSendRequest` at `0x180024f43`
- `WINHTTP!WinHttpSendRequest` at `0x180024f43`
- `DMCmnUtils!UnicodeToMB` at `0x180024ebc`
- `DMCmnUtils!UnicodeToMB` at `0x180024ebc`

## string_xrefs

- `0x180024d61`: `Windows.Data.Json.JsonObject`
- `0x180024cef`: `X-Device-Token`
- `0x180024ccc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024d09`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024dad`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024e08`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024e57`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024ecf`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024fb2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18002501b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024f38`: `content-type:application/json; charset=utf-8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  int v18; // edx
  unsigned int v19; // r8d
  int v20; // eax
  struct Windows::Data::Json::IJsonObject *v21; // rcx
  int v22; // eax
  struct Windows::Data::Json::IJsonObject *v23; // rcx
  int v24; // eax
  struct Windows::Data::Json::IJsonObject *v25; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  int v27; // eax
  struct Windows::Data::Json::IJsonObject *v28; // rcx
  signed int v29; // eax
  struct Windows::Data::Json::IJsonObject *v30; // rcx
  struct Windows::Data::Json::IJsonObject *v31; // rdx
  int v32; // eax
  struct Windows::Data::Json::IJsonObject *v33; // rcx
  struct Windows::Data::Json::IJsonObject *v34; // rcx
  int pwszReferrer; // [rsp+20h] [rbp-71h]
  int pwszReferrera; // [rsp+20h] [rbp-71h]
  struct Windows::Data::Json::IJsonObject *v37; // [rsp+40h] [rbp-51h] BYREF
  HSTRING v38; // [rsp+48h] [rbp-49h] BYREF
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
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v10);
  if ( *((_QWORD *)a4 + 3) > 7u )
    a4 = *(unsigned __int16 **)a4;
  v15 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"X-Device-Token",
          a4);
  if ( (v15 & 0x80000000) != 0 )
  {
    v16 = 534;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)v15,
      pwszReferrer);
    return v15;
  }
  if ( *((_QWORD *)a5 + 3) > 7u )
    v9 = *(const unsigned __int16 **)a5;
  v15 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"MS-CV",
          v9);
  if ( (v15 & 0x80000000) != 0 )
  {
    v16 = 537;
    goto LABEL_9;
  }
  v37 = 0;
  string = 0;
  v17 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
    JUMPOUT(0x1800250CFLL);
  }
  v20 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(string, &v37);
  v15 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x226,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v20,
      pwszReferrer);
    v21 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v15;
  }
  if ( *((_QWORD *)a6 + 3) > 7u )
    v8 = *(const unsigned __int16 **)a6;
  v22 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v37, L"HardwareMismatchRemediationData", v8);
  v15 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x227,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v22,
      pwszReferrer);
    v23 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v15;
  }
  v38 = 0;
  v24 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v37, &v38);
  v15 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v24,
      pwszReferrer);
    if ( v38 )
      WindowsDeleteString(v38);
    v25 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return v15;
  }
  dwOptionalLength = 0;
  hMem = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
  v27 = UnicodeToMB(StringRawBuffer, 0xFDE9u, (char **)&hMem, &dwOptionalLength);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v27,
      pwszReferrer);
    if ( hMem )
      LocalFree(hMem);
    if ( v38 )
      WindowsDeleteString(v38);
    v28 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v28 + 16LL))(v28);
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
    v29 = GetLastError();
    v15 = v29;
    if ( v29 > 0 )
      v15 = (unsigned __int16)v29 | 0x80070000;
    if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v15) )
    {
      if ( hMem )
        LocalFree(hMem);
      if ( v38 )
        WindowsDeleteString(v38);
      v30 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v30 + 16LL))(v30);
      }
    }
    else
    {
      if ( (v15 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
          (const char *)v15,
          pwszReferrera);
      if ( hMem )
        LocalFree(hMem);
      if ( v38 )
        WindowsDeleteString(v38);
      v31 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v31 + 16LL))(v31);
      }
    }
    return v15;
  }
  v32 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this);
  v15 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v32,
      pwszReferrera);
    if ( hMem )
      LocalFree(hMem);
    if ( v38 )
      WindowsDeleteString(v38);
    v33 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return v15;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v38 )
    WindowsDeleteString(v38);
  v34 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x180024c34  push    rbp
0x180024c36  push    rbx
0x180024c37  push    rsi
0x180024c38  push    rdi
0x180024c39  push    r12
0x180024c3b  push    r13
0x180024c3d  push    r14
0x180024c3f  push    r15
0x180024c41  lea     rbp, [rsp-7]
0x180024c46  sub     rsp, 98h
0x180024c4d  mov     rax, cs:__security_cookie
0x180024c54  xor     rax, rsp
0x180024c57  mov     [rbp+3Fh+var_50], rax
0x180024c5b  mov     r15, r9
0x180024c5e  mov     rdi, rcx
0x180024c61  mov     rsi, [rbp+3Fh+arg_28]
0x180024c65  mov     r14, [rbp+3Fh+arg_20]
0x180024c69  mov     [rsp+0D0h+dwFlags], r8d; dwFlags
0x180024c6e  mov     [rsp+0D0h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x180024c77  mov     [rsp+0D0h+pwszReferrer], 0; int
0x180024c80  xor     r9d, r9d; pwszVersion
0x180024c83  mov     r8, rdx; pwszObjectName
0x180024c86  lea     rdx, pwszVerb; "PATCH"
0x180024c8d  mov     rcx, [rcx+48h]; hConnect
0x180024c91  call    cs:__imp_WinHttpOpenRequest
0x180024c97  mov     r12, rax
0x180024c9a  mov     r13, [rdi+50h]
0x180024c9e  test    r13, r13
0x180024ca1  jz      short loc_180024CBC
0x180024ca3  call    cs:__imp_GetLastError
0x180024ca9  mov     ebx, eax
0x180024cab  mov     rcx, r13; hInternet
0x180024cae  call    cs:__imp_WinHttpCloseHandle
0x180024cb4  mov     ecx, ebx; dwErrCode
0x180024cb6  call    cs:__imp_SetLastError
0x180024cbc  mov     [rdi+50h], r12
0x180024cc0  xor     r13d, r13d
0x180024cc3  test    r12, r12
0x180024cc6  jnz     short loc_180024CE2
0x180024cc8  mov     rcx, [rbp+47h]; this
0x180024ccc  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024cd3  mov     edx, 213h; void *
0x180024cd8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024cdd  jmp     loc_1800250A8
0x180024ce2  cmp     qword ptr [r15+18h], 7
0x180024ce7  jbe     short loc_180024CEC
0x180024ce9  mov     r15, [r15]
0x180024cec  mov     r8, r15; unsigned __int16 *
0x180024cef  lea     rdx, aXDeviceToken; "X-Device-Token"
0x180024cf6  mov     rcx, rdi; this
0x180024cf9  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x180024cfe  mov     ebx, eax
0x180024d00  test    eax, eax
0x180024d02  jns     short loc_180024D23
0x180024d04  mov     edx, 216h; void *
0x180024d09  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024d10  mov     r9d, ebx; char *
0x180024d13  mov     rcx, [rbp+47h]; this
0x180024d17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d1c  mov     eax, ebx
0x180024d1e  jmp     loc_1800250A8
0x180024d23  cmp     qword ptr [r14+18h], 7
0x180024d28  jbe     short loc_180024D2D
0x180024d2a  mov     r14, [r14]
0x180024d2d  mov     r8, r14; unsigned __int16 *
0x180024d30  lea     rdx, aMsCv; "MS-CV"
0x180024d37  mov     rcx, rdi; this
0x180024d3a  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x180024d3f  mov     ebx, eax
0x180024d41  test    eax, eax
0x180024d43  jns     short loc_180024D4C
0x180024d45  mov     edx, 219h
0x180024d4a  jmp     short loc_180024D09
0x180024d4c  mov     [rbp+3Fh+var_90], r13
0x180024d50  mov     [rbp+3Fh+string], r13
0x180024d54  lea     r9, [rbp+3Fh+string]; string
0x180024d58  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x180024d5c  mov     edx, 1Ch; length
0x180024d61  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180024d68  call    cs:__imp_WindowsCreateStringReference
0x180024d6e  test    eax, eax
0x180024d70  js      loc_1800250C8
0x180024d76  mov     rbx, [rbp+3Fh+string]
0x180024d7a  mov     rcx, [rbp+3Fh+var_90]
0x180024d7e  test    rcx, rcx
0x180024d81  jz      short loc_180024D94
0x180024d83  mov     [rbp+3Fh+var_90], r13
0x180024d87  mov     rax, [rcx]
0x180024d8a  mov     rax, [rax+10h]
0x180024d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d93  nop
0x180024d94  lea     rdx, [rbp+3Fh+var_90]
0x180024d98  mov     rcx, rbx
0x180024d9b  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180024da0  mov     ebx, eax
0x180024da2  test    eax, eax
0x180024da4  jns     short loc_180024DDE
0x180024da6  mov     rcx, [rbp+47h]; this
0x180024daa  mov     r9d, eax; char *
0x180024dad  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024db4  mov     edx, 226h; void *
0x180024db9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024dbe  nop
0x180024dbf  mov     rcx, [rbp+3Fh+var_90]
0x180024dc3  test    rcx, rcx
0x180024dc6  jz      short loc_180024DD9
0x180024dc8  mov     [rbp+3Fh+var_90], r13
0x180024dcc  mov     rax, [rcx]
0x180024dcf  mov     rax, [rax+10h]
0x180024dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dd8  nop
0x180024dd9  jmp     loc_180024D1C
0x180024dde  cmp     qword ptr [rsi+18h], 7
0x180024de3  jbe     short loc_180024DE8
0x180024de5  mov     rsi, [rsi]
0x180024de8  mov     r8, rsi; unsigned __int16 *
0x180024deb  lea     rdx, aHardwaremismat; "HardwareMismatchRemediationData"
0x180024df2  mov     rcx, [rbp+3Fh+var_90]; struct Windows::Data::Json::IJsonObject *
0x180024df6  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180024dfb  mov     ebx, eax
0x180024dfd  test    eax, eax
0x180024dff  jns     short loc_180024E39
0x180024e01  mov     rcx, [rbp+47h]; this
0x180024e05  mov     r9d, eax; char *
0x180024e08  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024e0f  mov     edx, 227h; void *
0x180024e14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e19  nop
0x180024e1a  mov     rcx, [rbp+3Fh+var_90]
0x180024e1e  test    rcx, rcx
0x180024e21  jz      short loc_180024E34
0x180024e23  mov     [rbp+3Fh+var_90], r13
0x180024e27  mov     rax, [rcx]
0x180024e2a  mov     rax, [rax+10h]
0x180024e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e33  nop
0x180024e34  jmp     loc_180024D1C
0x180024e39  mov     [rbp+3Fh+var_88], r13
0x180024e3d  lea     rdx, [rbp+3Fh+var_88]
0x180024e41  mov     rcx, [rbp+3Fh+var_90]
0x180024e45  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180024e4a  mov     ebx, eax
0x180024e4c  test    eax, eax
0x180024e4e  jns     short loc_180024E98
0x180024e50  mov     rcx, [rbp+47h]; this
0x180024e54  mov     r9d, eax; char *
0x180024e57  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024e5e  mov     edx, 22Ah; void *
0x180024e63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e68  nop
0x180024e69  mov     rcx, [rbp+3Fh+var_88]; string
0x180024e6d  test    rcx, rcx
0x180024e70  jz      short loc_180024E79
0x180024e72  call    cs:__imp_WindowsDeleteString
0x180024e78  nop
0x180024e79  mov     rcx, [rbp+3Fh+var_90]
0x180024e7d  test    rcx, rcx
0x180024e80  jz      short loc_180024E93
0x180024e82  mov     [rbp+3Fh+var_90], r13
0x180024e86  mov     rax, [rcx]
0x180024e89  mov     rax, [rax+10h]
0x180024e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e92  nop
0x180024e93  jmp     loc_180024D1C
0x180024e98  mov     [rbp+3Fh+dwOptionalLength], r13d
0x180024e9c  mov     [rbp+3Fh+hMem], r13
0x180024ea0  xor     edx, edx; length
0x180024ea2  mov     rcx, [rbp+3Fh+var_88]; string
0x180024ea6  call    cs:__imp_WindowsGetStringRawBuffer
0x180024eac  lea     r9, [rbp+3Fh+dwOptionalLength]
0x180024eb0  lea     r8, [rbp+3Fh+hMem]
0x180024eb4  mov     edx, 0FDE9h
0x180024eb9  mov     rcx, rax
0x180024ebc  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180024ec2  mov     ebx, eax
0x180024ec4  test    eax, eax
0x180024ec6  jns     short loc_180024F20
0x180024ec8  mov     rcx, [rbp+47h]; this
0x180024ecc  mov     r9d, eax; char *
0x180024ecf  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024ed6  mov     edx, 232h; void *
0x180024edb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024ee0  nop
0x180024ee1  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180024ee5  test    rcx, rcx
0x180024ee8  jz      short loc_180024EF1
0x180024eea  call    cs:__imp_LocalFree
0x180024ef0  nop
0x180024ef1  mov     rcx, [rbp+3Fh+var_88]; string
0x180024ef5  test    rcx, rcx
0x180024ef8  jz      short loc_180024F01
0x180024efa  call    cs:__imp_WindowsDeleteString
0x180024f00  nop
0x180024f01  mov     rcx, [rbp+3Fh+var_90]
0x180024f05  test    rcx, rcx
0x180024f08  jz      short loc_180024F1B
0x180024f0a  mov     [rbp+3Fh+var_90], r13
0x180024f0e  mov     rax, [rcx]
0x180024f11  mov     rax, [rax+10h]
0x180024f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f1a  nop
0x180024f1b  jmp     loc_180024D1C
0x180024f20  mov     eax, [rbp+3Fh+dwOptionalLength]
0x180024f23  mov     qword ptr [rsp+0D0h+dwFlags], r13; dwContext
0x180024f28  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], eax; dwTotalLength
0x180024f2c  mov     dword ptr [rsp+0D0h+pwszReferrer], eax; int
0x180024f30  mov     r9, [rbp+3Fh+hMem]; lpOptional
0x180024f34  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180024f38  lea     rdx, szHeaders; "content-type:application/json; charset="...
0x180024f3f  mov     rcx, [rdi+50h]; hRequest
0x180024f43  call    cs:__imp_WinHttpSendRequest
0x180024f49  test    eax, eax
0x180024f4b  jnz     loc_180025006
0x180024f51  call    cs:__imp_GetLastError
0x180024f57  mov     ebx, eax
0x180024f59  test    eax, eax
0x180024f5b  jle     short loc_180024F66
0x180024f5d  movzx   ebx, ax
0x180024f60  or      ebx, 80070000h
0x180024f66  mov     ecx, ebx; int
0x180024f68  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180024f6d  test    al, al
0x180024f6f  jz      short loc_180024FA7
0x180024f71  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180024f75  test    rcx, rcx
0x180024f78  jz      short loc_180024F81
0x180024f7a  call    cs:__imp_LocalFree
0x180024f80  nop
0x180024f81  mov     rcx, [rbp+3Fh+var_88]; string
0x180024f85  test    rcx, rcx
0x180024f88  jz      short loc_180024F91
0x180024f8a  call    cs:__imp_WindowsDeleteString
0x180024f90  nop
0x180024f91  mov     rcx, [rbp+3Fh+var_90]
0x180024f95  test    rcx, rcx
0x180024f98  jz      short loc_180025001
0x180024f9a  mov     [rbp+3Fh+var_90], r13
0x180024f9e  mov     rax, [rcx]
0x180024fa1  mov     rax, [rax+10h]
0x180024fa5  jmp     short loc_180024FFB
0x180024fa7  test    ebx, ebx
0x180024fa9  jns     short loc_180024FC4
0x180024fab  mov     rcx, [rbp+47h]; this
0x180024faf  mov     r9d, ebx; char *
0x180024fb2  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024fb9  mov     edx, 23Eh; void *
0x180024fbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024fc3  nop
0x180024fc4  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180024fc8  test    rcx, rcx
0x180024fcb  jz      short loc_180024FD4
0x180024fcd  call    cs:__imp_LocalFree
0x180024fd3  nop
0x180024fd4  mov     rcx, [rbp+3Fh+var_88]; string
0x180024fd8  test    rcx, rcx
0x180024fdb  jz      short loc_180024FE4
0x180024fdd  call    cs:__imp_WindowsDeleteString
0x180024fe3  nop
0x180024fe4  mov     rdx, [rbp+3Fh+var_90]
0x180024fe8  test    rdx, rdx
0x180024feb  jz      short loc_180025001
0x180024fed  mov     [rbp+3Fh+var_90], r13
0x180024ff1  mov     rcx, [rdx]
0x180024ff4  mov     rax, [rcx+10h]
0x180024ff8  mov     rcx, rdx
0x180024ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025000  nop
0x180025001  jmp     loc_180024D1C
0x180025006  mov     rcx, rdi; this
0x180025009  call    ?VerifyResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(void)
0x18002500e  mov     ebx, eax
0x180025010  test    eax, eax
0x180025012  jns     short loc_18002506C
0x180025014  mov     rcx, [rbp+47h]; this
0x180025018  mov     r9d, eax; char *
0x18002501b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025022  mov     edx, 241h; void *
0x180025027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002502c  nop
0x18002502d  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180025031  test    rcx, rcx
0x180025034  jz      short loc_18002503D
0x180025036  call    cs:__imp_LocalFree
0x18002503c  nop
0x18002503d  mov     rcx, [rbp+3Fh+var_88]; string
0x180025041  test    rcx, rcx
0x180025044  jz      short loc_18002504D
0x180025046  call    cs:__imp_WindowsDeleteString
0x18002504c  nop
0x18002504d  mov     rcx, [rbp+3Fh+var_90]
0x180025051  test    rcx, rcx
0x180025054  jz      short loc_180025067
0x180025056  mov     [rbp+3Fh+var_90], r13
0x18002505a  mov     rax, [rcx]
0x18002505d  mov     rax, [rax+10h]
0x180025061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025066  nop
0x180025067  jmp     loc_180024D1C
0x18002506c  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180025070  test    rcx, rcx
  ... truncated ...
```

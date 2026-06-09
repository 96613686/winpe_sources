# FSSendEventAction::Run(void)

- ea: `0x1800a8b90`
- end: `0x1800a8f68`
- name: `?Run@FSSendEventAction@@UEAAJXZ`
- size: `984`
- prototype: `__int64 __fastcall(FSSendEventAction *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x180013da0`
- `0x1800168c8`
- `0x1800177bc`
- `0x18009bc4c`
- `0x1800a579c`
- `0x1800a89b0`
- `0x1800a8a40`
- `0x1800a8b90`
- `0x1800a8fcc`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a8c4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a8d50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a8dc3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a8c4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a8d50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a8dc3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a8bf8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a8bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a8c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a8c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8c3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8db3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8ef5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8c3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8db3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8ef5`

## string_xrefs

- `0x1800a8c9b`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fssendeventaction.cpp`
- `0x1800a8e57`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fssendeventaction.cpp`
- `0x1800a8f33`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fssendeventaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FSSendEventAction::Run(FSSendEventAction *this)
{
  char *v1; // rsi
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, HSTRING, HSTRING *); // r14
  unsigned __int64 v4; // rcx
  int inited; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, HSTRING *); // rbx
  HSTRING *v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  HSTRING *v14; // rcx
  const unsigned __int16 *v15; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  __int64 v18; // rcx
  FlightSettingsAPITelemetryClass *v19; // rax
  HSTRING *v20; // rcx
  PCWSTR v21; // rax
  unsigned __int64 v22; // rdx
  unsigned __int8 v23; // cl
  __int64 v24; // r9
  __int64 v25; // rcx
  FlightSettingsAPITelemetryClass *v26; // rax
  PCWSTR v27; // rax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING, HSTRING *); // rbx
  HSTRING *v30; // rax
  int v31; // eax
  __int64 v32; // rdx
  PCWSTR v33; // rax
  __int64 v34; // rcx
  __int64 *v35; // rdx
  UINT32 length; // [rsp+20h] [rbp-58h] BYREF
  int v38; // [rsp+24h] [rbp-54h] BYREF
  HSTRING v39; // [rsp+28h] [rbp-50h] BYREF
  HSTRING v40; // [rsp+30h] [rbp-48h] BYREF
  HSTRING v41; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v40 = 0;
  v1 = (char *)this + 64;
  v2 = *((_QWORD *)this + 8);
  v3 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v2 + 80LL);
  length = 0;
  v4 = -1;
  do
    ++v4;
  while ( FSSendEventAction::s_eventNameInternalTag[v4] );
  if ( (int)ULongLongToUInt(v4, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSSendEventAction::s_eventNameInternalTag, length, &hstringHeader, &string);
  inited = v3(v2, string, &v40);
  v6 = inited;
  if ( inited < 0 )
  {
    v7 = 60;
LABEL_21:
    v24 = (unsigned int)inited;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fssendeventaction.cpp",
      (const char *)v24,
      length);
    goto LABEL_51;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v40, 0);
  if ( (unsigned int)_o__wcsicmp(StringRawBuffer, L"FSPolicyError") )
  {
    v21 = WindowsGetStringRawBuffer(v40, 0);
    if ( !(unsigned int)_o__wcsicmp(v21, L"MDMPolicyEnforcementSuccess") )
    {
      v38 = 0;
      inited = FSServiceDrivenAction::InitDwordFromJson(v1, L"hr", &v38);
      v6 = inited;
      if ( inited < 0 )
      {
        v7 = 78;
        goto LABEL_21;
      }
      if ( FlightSettingsAPITelemetryClass::IsEnabled(v23, v22) )
      {
        v26 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                   v25,
                                                   _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
        FlightSettingsAPITelemetryClass::MDMPolicyEnforcementSuccess_(v26, v38);
      }
LABEL_48:
      Windows::Internal::String::~String((Windows::Internal::String *)&v40);
      return 0;
    }
    v27 = WindowsGetStringRawBuffer(v40, 0);
    if ( (unsigned int)_o__wcsicmp(v27, L"MDMPolicyError") )
    {
      v6 = -2146698720;
      v24 = 2148268576LL;
      v7 = 113;
      goto LABEL_50;
    }
    v39 = 0;
    v28 = *(_QWORD *)v1;
    v29 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(**(_QWORD **)v1 + 80LL);
    v30 = Windows::Internal::StringReference::StringReference(&string, L"message");
    v31 = v29(v28, *v30, &v39);
    v6 = v31;
    if ( v31 < 0 )
    {
      v32 = 85;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fssendeventaction.cpp",
        (const char *)(unsigned int)v31,
        length);
      v14 = &v39;
      goto LABEL_32;
    }
    length = 0;
    v31 = FSServiceDrivenAction::InitDwordFromJson(v1, L"result", &length);
    v6 = v31;
    if ( v31 < 0 )
    {
      v32 = 88;
      goto LABEL_31;
    }
    v38 = 0;
    v31 = FSServiceDrivenAction::InitDwordFromJson(v1, L"behavior", &v38);
    v6 = v31;
    if ( v31 < 0 )
    {
      v32 = 91;
      goto LABEL_31;
    }
    if ( v38 )
    {
      switch ( v38 )
      {
        case 1:
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
          {
            v33 = WindowsGetStringRawBuffer(v39, 0);
            v35 = PreviewBuildsInformational;
            goto LABEL_45;
          }
          goto LABEL_46;
        case 2:
          if ( (byte_18011D601 & 0x40) != 0 )
          {
            v33 = WindowsGetStringRawBuffer(v39, 0);
            v35 = PreviewBuildsWarning;
            goto LABEL_45;
          }
LABEL_46:
          v20 = &v39;
LABEL_47:
          Windows::Internal::String::~String((Windows::Internal::String *)v20);
          goto LABEL_48;
        case 3:
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
          {
            v33 = WindowsGetStringRawBuffer(v39, 0);
            v35 = PreviewBuildsError;
LABEL_45:
            McTemplateU0zd_EventWriteTransfer(v34, v35, v33, length);
            goto LABEL_46;
          }
          goto LABEL_46;
      }
    }
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      v33 = WindowsGetStringRawBuffer(v39, 0);
      v35 = PreviewBuildsDebug;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  v41 = 0;
  v9 = *(_QWORD *)v1;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(**(_QWORD **)v1 + 80LL);
  v11 = Windows::Internal::StringReference::StringReference(&string, L"message");
  v12 = v10(v9, *v11, &v41);
  v6 = v12;
  if ( v12 >= 0 )
  {
    v38 = 0;
    v12 = FSServiceDrivenAction::InitDwordFromJson(v1, L"result", &v38);
    v6 = v12;
    if ( v12 < 0 )
    {
      v13 = 68;
      goto LABEL_10;
    }
    length = 0;
    v12 = FSServiceDrivenAction::InitDwordFromJson(v1, L"behavior", &length);
    v6 = v12;
    if ( v12 < 0 )
    {
      v13 = 71;
      goto LABEL_10;
    }
    v15 = WindowsGetStringRawBuffer(v41, 0);
    if ( FlightSettingsAPITelemetryClass::IsEnabled(v17, v16) )
    {
      v19 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v18,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::PolicyError_(v19, v15, v38, length);
    }
    v20 = &v41;
    goto LABEL_47;
  }
  v13 = 65;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fssendeventaction.cpp",
    (const char *)(unsigned int)v12,
    length);
  v14 = &v41;
LABEL_32:
  Windows::Internal::String::~String((Windows::Internal::String *)v14);
LABEL_51:
  Windows::Internal::String::~String((Windows::Internal::String *)&v40);
  return v6;
}

```

## disassembly

```asm
0x1800a8b90  push    rbp
0x1800a8b92  push    rbx
0x1800a8b93  push    rsi
0x1800a8b94  push    rdi
0x1800a8b95  push    r14
0x1800a8b97  push    r15
0x1800a8b99  mov     rbp, rsp
0x1800a8b9c  sub     rsp, 78h
0x1800a8ba0  mov     rax, cs:__security_cookie
0x1800a8ba7  xor     rax, rsp
0x1800a8baa  mov     [rbp+var_18], rax
0x1800a8bae  xor     r15d, r15d
0x1800a8bb1  mov     [rbp+var_48], r15
0x1800a8bb5  lea     rsi, [rcx+40h]
0x1800a8bb9  mov     rdi, [rsi]
0x1800a8bbc  mov     rax, [rdi]
0x1800a8bbf  mov     r14, [rax+50h]
0x1800a8bc3  mov     rbx, cs:?s_eventNameInternalTag@FSSendEventAction@@0QEBGEB; ushort const * const FSSendEventAction::s_eventNameInternalTag
0x1800a8bca  mov     [rbp+length], r15d
0x1800a8bce  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a8bd2  inc     rcx; unsigned __int64
0x1800a8bd5  cmp     [rbx+rcx*2], r15w
0x1800a8bda  jnz     short loc_1800A8BD2
0x1800a8bdc  lea     rdx, [rbp+length]; unsigned int *
0x1800a8be0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a8be5  test    eax, eax
0x1800a8be7  jns     short loc_1800A8BFE
0x1800a8be9  xor     r9d, r9d; lpArguments
0x1800a8bec  xor     r8d, r8d; nNumberOfArguments
0x1800a8bef  lea     edx, [r9+1]; dwExceptionFlags
0x1800a8bf3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a8bf8  call    cs:__imp_RaiseException
0x1800a8bfe  lea     r9, [rbp+string]; string
0x1800a8c02  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800a8c06  mov     edx, [rbp+length]; length
0x1800a8c09  mov     rcx, rbx; sourceString
0x1800a8c0c  call    cs:__imp_WindowsCreateStringReference
0x1800a8c12  lea     r8, [rbp+var_48]
0x1800a8c16  mov     rdx, [rbp+string]
0x1800a8c1a  mov     rcx, rdi
0x1800a8c1d  mov     rax, r14
0x1800a8c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8c25  mov     ebx, eax
0x1800a8c27  test    eax, eax
0x1800a8c29  jns     short loc_1800A8C35
0x1800a8c2b  mov     edx, 3Ch ; '<'
0x1800a8c30  jmp     loc_1800A8D7C
0x1800a8c35  xor     edx, edx; length
0x1800a8c37  mov     rcx, [rbp+var_48]; string
0x1800a8c3b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8c41  lea     rdx, aFspolicyerror; "FSPolicyError"
0x1800a8c48  mov     rcx, rax
0x1800a8c4b  call    cs:__imp__o__wcsicmp
0x1800a8c51  test    eax, eax
0x1800a8c53  jnz     loc_1800A8D3A
0x1800a8c59  mov     [rbp+var_40], r15
0x1800a8c5d  mov     rdi, [rsi]
0x1800a8c60  mov     rax, [rdi]
0x1800a8c63  mov     rbx, [rax+50h]
0x1800a8c67  lea     rdx, aMessage_0; "message"
0x1800a8c6e  lea     rcx, [rbp+string]; string
0x1800a8c72  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x1800a8c77  lea     r8, [rbp+var_40]
0x1800a8c7b  mov     rdx, [rax]
0x1800a8c7e  mov     rcx, rdi
0x1800a8c81  mov     rax, rbx
0x1800a8c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8c89  mov     ebx, eax
0x1800a8c8b  test    eax, eax
0x1800a8c8d  jns     short loc_1800A8CB1
0x1800a8c8f  mov     edx, 41h ; 'A'; void *
0x1800a8c94  mov     rcx, [rbp+30h]; this
0x1800a8c98  mov     r9d, eax; char *
0x1800a8c9b  lea     r8, aOnecoreBaseFli_1; "onecore\\base\\flighting\\flightsetting"...
0x1800a8ca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8ca7  nop
0x1800a8ca8  lea     rcx, [rbp+var_40]
0x1800a8cac  jmp     loc_1800A8E6C
0x1800a8cb1  mov     [rbp+var_54], r15d
0x1800a8cb5  lea     r8, [rbp+var_54]
0x1800a8cb9  lea     rdx, aResult; "result"
0x1800a8cc0  mov     rcx, rsi
0x1800a8cc3  call    ?InitDwordFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; FSServiceDrivenAction::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x1800a8cc8  mov     ebx, eax
0x1800a8cca  test    eax, eax
0x1800a8ccc  jns     short loc_1800A8CD5
0x1800a8cce  mov     edx, 44h ; 'D'
0x1800a8cd3  jmp     short loc_1800A8C94
0x1800a8cd5  mov     [rbp+length], r15d
0x1800a8cd9  lea     r8, [rbp+length]
0x1800a8cdd  lea     rdx, aBehavior; "behavior"
0x1800a8ce4  mov     rcx, rsi
0x1800a8ce7  call    ?InitDwordFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; FSServiceDrivenAction::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x1800a8cec  mov     ebx, eax
0x1800a8cee  test    eax, eax
0x1800a8cf0  jns     short loc_1800A8CF9
0x1800a8cf2  mov     edx, 47h ; 'G'
0x1800a8cf7  jmp     short loc_1800A8C94
0x1800a8cf9  xor     edx, edx; length
0x1800a8cfb  mov     rcx, [rbp+var_40]; string
0x1800a8cff  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8d05  mov     rbx, rax
0x1800a8d08  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a8d0d  test    al, al
0x1800a8d0f  jz      short loc_1800A8D31
0x1800a8d11  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a8d18  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a8d1d  mov     r9d, [rbp+length]; unsigned int
0x1800a8d21  mov     r8d, [rbp+var_54]; int
0x1800a8d25  mov     rdx, rbx; unsigned __int16 *
0x1800a8d28  mov     rcx, rax; this
0x1800a8d2b  call    ?PolicyError_@FlightSettingsAPITelemetryClass@@QEAAXPEBGJK@Z; FlightSettingsAPITelemetryClass::PolicyError_(ushort const *,long,ulong)
0x1800a8d30  nop
0x1800a8d31  lea     rcx, [rbp+var_40]
0x1800a8d35  jmp     loc_1800A8F13
0x1800a8d3a  xor     edx, edx; length
0x1800a8d3c  mov     rcx, [rbp+var_48]; string
0x1800a8d40  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8d46  lea     rdx, aMdmpolicyenfor; "MDMPolicyEnforcementSuccess"
0x1800a8d4d  mov     rcx, rax
0x1800a8d50  call    cs:__imp__o__wcsicmp
0x1800a8d56  test    eax, eax
0x1800a8d58  jnz     short loc_1800A8DAD
0x1800a8d5a  mov     [rbp+var_54], r15d
0x1800a8d5e  lea     r8, [rbp+var_54]
0x1800a8d62  lea     rdx, aHr; "hr"
0x1800a8d69  mov     rcx, rsi
0x1800a8d6c  call    ?InitDwordFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; FSServiceDrivenAction::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x1800a8d71  mov     ebx, eax
0x1800a8d73  test    eax, eax
0x1800a8d75  jns     short loc_1800A8D84
0x1800a8d77  mov     edx, 4Eh ; 'N'
0x1800a8d7c  mov     r9d, eax
0x1800a8d7f  jmp     loc_1800A8F33
0x1800a8d84  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a8d89  test    al, al
0x1800a8d8b  jz      loc_1800A8F19
0x1800a8d91  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a8d98  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a8d9d  mov     edx, [rbp+var_54]; int
0x1800a8da0  mov     rcx, rax; this
0x1800a8da3  call    ?MDMPolicyEnforcementSuccess_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::MDMPolicyEnforcementSuccess_(long)
0x1800a8da8  jmp     loc_1800A8F19
0x1800a8dad  xor     edx, edx; length
0x1800a8daf  mov     rcx, [rbp+var_48]; string
0x1800a8db3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8db9  lea     rdx, aMdmpolicyerror; "MDMPolicyError"
0x1800a8dc0  mov     rcx, rax
0x1800a8dc3  call    cs:__imp__o__wcsicmp
0x1800a8dc9  test    eax, eax
0x1800a8dcb  jnz     loc_1800A8F26
0x1800a8dd1  mov     [rbp+var_50], r15
0x1800a8dd5  mov     rdi, [rsi]
0x1800a8dd8  mov     rax, [rdi]
0x1800a8ddb  mov     rbx, [rax+50h]
0x1800a8ddf  lea     rdx, aMessage_0; "message"
0x1800a8de6  lea     rcx, [rbp+string]; string
0x1800a8dea  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x1800a8def  lea     r8, [rbp+var_50]
0x1800a8df3  mov     rdx, [rax]
0x1800a8df6  mov     rcx, rdi
0x1800a8df9  mov     rax, rbx
0x1800a8dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8e01  mov     ebx, eax
0x1800a8e03  test    eax, eax
0x1800a8e05  jns     short loc_1800A8E0E
0x1800a8e07  mov     edx, 55h ; 'U'
0x1800a8e0c  jmp     short loc_1800A8E54
0x1800a8e0e  mov     [rbp+length], r15d
0x1800a8e12  lea     r8, [rbp+length]
0x1800a8e16  lea     rdx, aResult; "result"
0x1800a8e1d  mov     rcx, rsi
0x1800a8e20  call    ?InitDwordFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; FSServiceDrivenAction::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x1800a8e25  mov     ebx, eax
0x1800a8e27  test    eax, eax
0x1800a8e29  jns     short loc_1800A8E32
0x1800a8e2b  mov     edx, 58h ; 'X'
0x1800a8e30  jmp     short loc_1800A8E54
0x1800a8e32  mov     [rbp+var_54], r15d
0x1800a8e36  lea     r8, [rbp+var_54]
0x1800a8e3a  lea     rdx, aBehavior; "behavior"
0x1800a8e41  mov     rcx, rsi
0x1800a8e44  call    ?InitDwordFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; FSServiceDrivenAction::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x1800a8e49  mov     ebx, eax
0x1800a8e4b  test    eax, eax
0x1800a8e4d  jns     short loc_1800A8E76
0x1800a8e4f  mov     edx, 5Bh ; '['; void *
0x1800a8e54  mov     r9d, eax; char *
0x1800a8e57  lea     r8, aOnecoreBaseFli_1; "onecore\\base\\flighting\\flightsetting"...
0x1800a8e5e  mov     rcx, [rbp+30h]; this
0x1800a8e62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8e67  nop
0x1800a8e68  lea     rcx, [rbp+var_50]; this
0x1800a8e6c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a8e71  jmp     loc_1800A8F44
0x1800a8e76  mov     ecx, [rbp+var_54]
0x1800a8e79  test    ecx, ecx
0x1800a8e7b  jz      short loc_1800A8EE6
0x1800a8e7d  sub     ecx, 1
0x1800a8e80  jz      short loc_1800A8EC8
0x1800a8e82  sub     ecx, 1
0x1800a8e85  jz      short loc_1800A8EAA
0x1800a8e87  cmp     ecx, 1
0x1800a8e8a  jnz     short loc_1800A8EE6
0x1800a8e8c  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800a8e93  jz      short loc_1800A8F0F
0x1800a8e95  xor     edx, edx; length
0x1800a8e97  mov     rcx, [rbp+var_50]; string
0x1800a8e9b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8ea1  lea     rdx, PreviewBuildsError
0x1800a8ea8  jmp     short loc_1800A8F02
0x1800a8eaa  test    cs:byte_18011D601, 40h
0x1800a8eb1  jz      short loc_1800A8F0F
0x1800a8eb3  xor     edx, edx; length
0x1800a8eb5  mov     rcx, [rbp+var_50]; string
0x1800a8eb9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8ebf  lea     rdx, PreviewBuildsWarning
0x1800a8ec6  jmp     short loc_1800A8F02
0x1800a8ec8  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x1800a8ecf  jz      short loc_1800A8F0F
0x1800a8ed1  xor     edx, edx; length
0x1800a8ed3  mov     rcx, [rbp+var_50]; string
0x1800a8ed7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8edd  lea     rdx, PreviewBuildsInformational
0x1800a8ee4  jmp     short loc_1800A8F02
0x1800a8ee6  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x1800a8eed  jz      short loc_1800A8F0F
0x1800a8eef  xor     edx, edx; length
0x1800a8ef1  mov     rcx, [rbp+var_50]; string
0x1800a8ef5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8efb  lea     rdx, PreviewBuildsDebug
0x1800a8f02  mov     r9d, [rbp+length]
0x1800a8f06  mov     r8, rax
0x1800a8f09  call    McTemplateU0zd_EventWriteTransfer
0x1800a8f0e  nop
0x1800a8f0f  lea     rcx, [rbp+var_50]; this
0x1800a8f13  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a8f18  nop
0x1800a8f19  lea     rcx, [rbp+var_48]; this
0x1800a8f1d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a8f22  xor     eax, eax
0x1800a8f24  jmp     short loc_1800A8F4F
0x1800a8f26  mov     ebx, 800BFA20h
0x1800a8f2b  mov     r9d, ebx; char *
0x1800a8f2e  mov     edx, 71h ; 'q'; void *
0x1800a8f33  lea     r8, aOnecoreBaseFli_1; "onecore\\base\\flighting\\flightsetting"...
0x1800a8f3a  mov     rcx, [rbp+30h]; this
0x1800a8f3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8f43  nop
0x1800a8f44  lea     rcx, [rbp+var_48]; this
0x1800a8f48  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a8f4d  mov     eax, ebx
0x1800a8f4f  mov     rcx, [rbp+var_18]
0x1800a8f53  xor     rcx, rsp; StackCookie
0x1800a8f56  call    __security_check_cookie
0x1800a8f5b  add     rsp, 78h
0x1800a8f5f  pop     r15
0x1800a8f61  pop     r14
0x1800a8f63  pop     rdi
0x1800a8f64  pop     rsi
0x1800a8f65  pop     rbx
0x1800a8f66  pop     rbp
0x1800a8f67  retn
```

# FSServiceDrivenAction::InitializeAttributes(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800a5a7c`
- end: `0x1800a5e84`
- name: `?InitializeAttributes@FSServiceDrivenAction@@IEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1032`
- prototype: `__int64 __fastcall(_DWORD *, __int64 *)`
- caller_count: `11`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009e0d8`
- `0x18009e76c`
- `0x18009eb74`
- `0x18009eca8`
- `0x18009ede0`
- `0x18009ef20`
- `0x18009f320`
- `0x1800a35e0`
- `0x1800a7e70`
- `0x1800ac8bc`
- `0x1800aca1c`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x180013da0`
- `0x1800168c8`
- `0x1800177bc`
- `0x18001ec78`
- `0x18003290c`
- `0x1800349c0`
- `0x1800a5a7c`
- `0x1800a5e8c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5b2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5bd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5c63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5d9c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5b2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5bd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5c63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a5d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5be5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5db0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5be5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a5db0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5d2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5d2a`

## string_xrefs

- `0x1800a5b70`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenaction.cpp`
- `0x1800a5cd0`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenaction.cpp`
- `0x1800a5d0c`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenaction.cpp`
- `0x1800a5dfd`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FSServiceDrivenAction::InitializeAttributes(_DWORD *a1, __int64 *a2)
{
  __int64 v4; // rax
  UINT32 v5; // r9d
  int *v6; // rsi
  double v7; // rbx
  __int64 v8; // r12
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int8 v14; // cl
  __int64 v15; // r12
  unsigned __int64 v16; // rcx
  const ULONG_PTR *v17; // r9
  __int64 v18; // r12
  unsigned __int64 v19; // rcx
  const ULONG_PTR *v20; // r9
  int v21; // eax
  __int64 v22; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v24; // r12
  __int64 (__fastcall *v25)(__int64, HSTRING, __int64 *); // r13
  const ULONG_PTR *v26; // r9
  __int64 v27; // rdx
  const unsigned __int16 *v28; // r14
  __int64 v29; // rcx
  FlightSettingsAPITelemetryClass *v30; // rax
  UINT32 length; // [rsp+28h] [rbp-79h] BYREF
  int v33; // [rsp+2Ch] [rbp-75h] BYREF
  __int64 v34; // [rsp+30h] [rbp-71h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-69h] BYREF
  __int64 v36; // [rsp+40h] [rbp-61h] BYREF
  __int64 (__fastcall *v37)(__int64, HSTRING, double *); // [rsp+48h] [rbp-59h]
  double v38; // [rsp+50h] [rbp-51h] BYREF
  double v39; // [rsp+58h] [rbp-49h] BYREF
  double v40[3]; // [rsp+60h] [rbp-41h] BYREF
  char v41; // [rsp+78h] [rbp-29h]
  _BYTE v42[16]; // [rsp+80h] [rbp-21h] BYREF
  HSTRING string; // [rsp+90h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v33 = 0;
  v4 = _lambda_af06e9d9b41286567a29afe0dcb44c45_::_lambda_af06e9d9b41286567a29afe0dcb44c45_(v42, &v33, a1);
  v6 = *(int **)v4;
  v40[1] = *(double *)v4;
  v7 = *(double *)(v4 + 8);
  v40[2] = v7;
  v41 = 1;
  v38 = 0.0;
  v8 = *a2;
  v37 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)*a2 + 88LL);
  length = v5;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( FSServiceDrivenAction::s_actionIdTag[v10] != (_WORD)v5 );
  if ( (int)ULongLongToUInt(v10, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSServiceDrivenAction::s_actionIdTag, length, &hstringHeader, &string);
  v11 = v37(v8, string, &v38);
  v33 = v11;
  if ( v11 < 0 )
  {
    v12 = 25;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenaction.cpp",
      (const char *)(unsigned int)v11,
      length);
    goto LABEL_39;
  }
  a1[4] = (int)v38;
  v39 = 0.0;
  v15 = *a2;
  v37 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)*a2 + 88LL);
  length = 0;
  v16 = -1;
  do
    ++v16;
  while ( FSServiceDrivenAction::s_orderTag[v16] );
  if ( (int)ULongLongToUInt(v16, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v17);
  WindowsCreateStringReference(FSServiceDrivenAction::s_orderTag, length, &hstringHeader, &string);
  v11 = v37(v15, string, &v39);
  v33 = v11;
  if ( v11 < 0 )
  {
    v12 = 30;
    goto LABEL_7;
  }
  a1[5] = (int)v39;
  v40[0] = 0.0;
  v18 = *a2;
  v37 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)*a2 + 88LL);
  length = 0;
  v19 = -1;
  do
    ++v19;
  while ( FSServiceDrivenAction::s_onErrorTag[v19] );
  if ( (int)ULongLongToUInt(v19, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v20);
  WindowsCreateStringReference(FSServiceDrivenAction::s_onErrorTag, length, &hstringHeader, &string);
  v11 = v37(v18, string, v40);
  v33 = v11;
  if ( v11 < 0 )
  {
    v12 = 35;
    goto LABEL_7;
  }
  a1[6] = (int)v40[0];
  v34 = 0;
  v21 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(a2, &v34);
  v11 = v21;
  v33 = v21;
  if ( v21 >= 0 )
  {
    v35 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 56LL))(v34, &v35);
    v33 = v11;
    if ( v11 < 0 )
    {
      v22 = 42;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenaction.cpp",
        (const char *)(unsigned int)v11,
        length);
LABEL_37:
      Windows::Internal::String::~String((Windows::Internal::String *)&v35);
      goto LABEL_38;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
    v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            a1 + 8,
            StringRawBuffer,
            -1);
    v33 = v11;
    if ( v11 < 0 )
    {
      v22 = 43;
      goto LABEL_24;
    }
    v36 = 0;
    v24 = *a2;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*a2 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    length = 0;
    do
      ++v9;
    while ( FSServiceDrivenAction::s_parametersTag[v9] );
    if ( (int)ULongLongToUInt(v9, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v26);
    WindowsCreateStringReference(FSServiceDrivenAction::s_parametersTag, length, &hstringHeader, &string);
    v11 = v25(v24, string, &v36);
    v33 = v11;
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_DWORD *, __int64 *))(*(_QWORD *)a1 + 96LL))(a1, &v36);
      v33 = v11;
      if ( v11 >= 0 )
      {
LABEL_36:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
        goto LABEL_37;
      }
      v27 = 49;
    }
    else
    {
      v27 = 48;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenaction.cpp",
      (const char *)(unsigned int)v11,
      length);
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenaction.cpp",
    (const char *)(unsigned int)v21,
    length);
LABEL_38:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
LABEL_39:
  v28 = *(const unsigned __int16 **)(*(_QWORD *)&v7 + 32LL);
  if ( FlightSettingsAPITelemetryClass::IsEnabled(v14, v13) )
  {
    v30 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v29,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::ServiceDrivenActionInitialize_(v30, *v6, *(_DWORD *)(*(_QWORD *)&v7 + 16LL), v28);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a5a7c  mov     rax, rsp
0x1800a5a7f  mov     [rax+18h], rbx
0x1800a5a83  push    rbp
0x1800a5a84  push    rsi
0x1800a5a85  push    rdi
0x1800a5a86  push    r12
0x1800a5a88  push    r13
0x1800a5a8a  push    r14
0x1800a5a8c  push    r15
0x1800a5a8e  lea     rbp, [rax-5Fh]
0x1800a5a92  sub     rsp, 0C0h
0x1800a5a99  movaps  xmmword ptr [rax-48h], xmm6
0x1800a5a9d  mov     rax, cs:__security_cookie
0x1800a5aa4  xor     rax, rsp
0x1800a5aa7  mov     [rbp+57h+var_48], rax
0x1800a5aab  mov     r13, rdx
0x1800a5aae  mov     r15, rcx
0x1800a5ab1  xor     r9d, r9d
0x1800a5ab4  mov     [rbp+57h+var_CC], r9d
0x1800a5ab8  mov     r8, rcx
0x1800a5abb  lea     rdx, [rbp+57h+var_CC]
0x1800a5abf  lea     rcx, [rbp+57h+var_78]
0x1800a5ac3  call    ??0_lambda_af06e9d9b41286567a29afe0dcb44c45_@@QEAA@PEAV?$SimpleVectorIterator@UPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@Internal@Windows@@V?$Vector@UPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@Internal@Windows@@UPreviewFeatureUpdateEquality@@UPodLifetimeTraits@XWinRT@@U?$DefaultVectorOptions@UPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@Internal@Windows@@@4Collections@Foundation@5@@4Collections@Foundation@5@UPodLifetimeTraits@XWinRT@@UIntVersionTag@XWinRT@@$0A@@Internal@Collections@Foundation@Windows@@AEAPEAUPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@25@@Z; _lambda_af06e9d9b41286567a29afe0dcb44c45_::_lambda_af06e9d9b41286567a29afe0dcb44c45_(Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate,PreviewFeatureUpdateEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate>>,XWinRT::PodLifetimeTraits,XWinRT::IntVersionTag,0> *,Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate * &)
0x1800a5ac8  mov     rsi, [rax]
0x1800a5acb  mov     [rbp+57h+var_90], rsi
0x1800a5acf  mov     rbx, [rax+8]
0x1800a5ad3  mov     [rbp+57h+var_88], rbx
0x1800a5ad7  mov     [rbp+57h+var_80], 1
0x1800a5adb  xorps   xmm6, xmm6
0x1800a5ade  movsd   [rbp+57h+var_A8], xmm6
0x1800a5ae3  mov     r12, [r13+0]
0x1800a5ae7  mov     rax, [r12]
0x1800a5aeb  mov     rax, [rax+58h]
0x1800a5aef  mov     [rbp+57h+var_B0], rax
0x1800a5af3  mov     rdi, cs:?s_actionIdTag@FSServiceDrivenAction@@0QEBGEB; ushort const * const FSServiceDrivenAction::s_actionIdTag
0x1800a5afa  mov     [rbp+57h+length], r9d
0x1800a5afe  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800a5b02  mov     rcx, r14
0x1800a5b05  inc     rcx; unsigned __int64
0x1800a5b08  cmp     [rdi+rcx*2], r9w
0x1800a5b0d  jnz     short loc_1800A5B05
0x1800a5b0f  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800a5b13  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a5b18  test    eax, eax
0x1800a5b1a  jns     short loc_1800A5B31
0x1800a5b1c  xor     r9d, r9d; lpArguments
0x1800a5b1f  xor     r8d, r8d; nNumberOfArguments
0x1800a5b22  lea     edx, [r9+1]; dwExceptionFlags
0x1800a5b26  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a5b2b  call    cs:__imp_RaiseException
0x1800a5b31  lea     r9, [rbp+57h+string]; string
0x1800a5b35  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a5b39  mov     edx, [rbp+57h+length]; length
0x1800a5b3c  mov     rcx, rdi; sourceString
0x1800a5b3f  call    cs:__imp_WindowsCreateStringReference
0x1800a5b45  lea     r8, [rbp+57h+var_A8]
0x1800a5b49  mov     rdx, [rbp+57h+string]
0x1800a5b4d  mov     rcx, r12
0x1800a5b50  mov     rax, [rbp+57h+var_B0]
0x1800a5b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5b59  mov     edi, eax
0x1800a5b5b  mov     [rbp+57h+var_CC], eax
0x1800a5b5e  xor     r9d, r9d
0x1800a5b61  test    eax, eax
0x1800a5b63  jns     short loc_1800A5B81
0x1800a5b65  lea     edx, [r9+19h]; void *
0x1800a5b69  mov     rcx, [rbp+5Fh]; this
0x1800a5b6d  mov     r9d, edi; char *
0x1800a5b70  lea     r8, aOnecoreBaseFli_80; "onecore\\base\\flighting\\flightsetting"...
0x1800a5b77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5b7c  jmp     loc_1800A5E2C
0x1800a5b81  cvttsd2si rax, [rbp+57h+var_A8]
0x1800a5b87  mov     [r15+10h], eax
0x1800a5b8b  movsd   [rbp+57h+var_A0], xmm6
0x1800a5b90  mov     r12, [r13+0]
0x1800a5b94  mov     rax, [r12]
0x1800a5b98  mov     rax, [rax+58h]
0x1800a5b9c  mov     [rbp+57h+var_B0], rax
0x1800a5ba0  mov     rdi, cs:?s_orderTag@FSServiceDrivenAction@@0QEBGEB; ushort const * const FSServiceDrivenAction::s_orderTag
0x1800a5ba7  mov     [rbp+57h+length], r9d
0x1800a5bab  mov     rcx, r14
0x1800a5bae  inc     rcx; unsigned __int64
0x1800a5bb1  cmp     [rdi+rcx*2], r9w
0x1800a5bb6  jnz     short loc_1800A5BAE
0x1800a5bb8  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800a5bbc  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a5bc1  test    eax, eax
0x1800a5bc3  jns     short loc_1800A5BD7
0x1800a5bc5  xor     r8d, r8d; nNumberOfArguments
0x1800a5bc8  lea     edx, [r8+1]; dwExceptionFlags
0x1800a5bcc  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a5bd1  call    cs:__imp_RaiseException
0x1800a5bd7  lea     r9, [rbp+57h+string]; string
0x1800a5bdb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a5bdf  mov     edx, [rbp+57h+length]; length
0x1800a5be2  mov     rcx, rdi; sourceString
0x1800a5be5  call    cs:__imp_WindowsCreateStringReference
0x1800a5beb  lea     r8, [rbp+57h+var_A0]
0x1800a5bef  mov     rdx, [rbp+57h+string]
0x1800a5bf3  mov     rcx, r12
0x1800a5bf6  mov     rax, [rbp+57h+var_B0]
0x1800a5bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5bff  mov     edi, eax
0x1800a5c01  mov     [rbp+57h+var_CC], eax
0x1800a5c04  xor     r9d, r9d
0x1800a5c07  test    eax, eax
0x1800a5c09  jns     short loc_1800A5C14
0x1800a5c0b  lea     edx, [r9+1Eh]
0x1800a5c0f  jmp     loc_1800A5B69
0x1800a5c14  cvttsd2si eax, [rbp+57h+var_A0]
0x1800a5c19  mov     [r15+14h], eax
0x1800a5c1d  movsd   [rbp+57h+var_98], xmm6
0x1800a5c22  mov     r12, [r13+0]
0x1800a5c26  mov     rax, [r12]
0x1800a5c2a  mov     rax, [rax+58h]
0x1800a5c2e  mov     [rbp+57h+var_B0], rax
0x1800a5c32  mov     rdi, cs:?s_onErrorTag@FSServiceDrivenAction@@0QEBGEB; ushort const * const FSServiceDrivenAction::s_onErrorTag
0x1800a5c39  mov     [rbp+57h+length], r9d
0x1800a5c3d  mov     rcx, r14
0x1800a5c40  inc     rcx; unsigned __int64
0x1800a5c43  cmp     [rdi+rcx*2], r9w
0x1800a5c48  jnz     short loc_1800A5C40
0x1800a5c4a  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800a5c4e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a5c53  test    eax, eax
0x1800a5c55  jns     short loc_1800A5C69
0x1800a5c57  xor     r8d, r8d; nNumberOfArguments
0x1800a5c5a  lea     edx, [r8+1]; dwExceptionFlags
0x1800a5c5e  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a5c63  call    cs:__imp_RaiseException
0x1800a5c69  lea     r9, [rbp+57h+string]; string
0x1800a5c6d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a5c71  mov     edx, [rbp+57h+length]; length
0x1800a5c74  mov     rcx, rdi; sourceString
0x1800a5c77  call    cs:__imp_WindowsCreateStringReference
0x1800a5c7d  lea     r8, [rbp+57h+var_98]
0x1800a5c81  mov     rdx, [rbp+57h+string]
0x1800a5c85  mov     rcx, r12
0x1800a5c88  mov     rax, [rbp+57h+var_B0]
0x1800a5c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c91  mov     edi, eax
0x1800a5c93  mov     [rbp+57h+var_CC], eax
0x1800a5c96  xor     r12d, r12d
0x1800a5c99  test    eax, eax
0x1800a5c9b  jns     short loc_1800A5CA7
0x1800a5c9d  lea     edx, [r12+23h]
0x1800a5ca2  jmp     loc_1800A5B69
0x1800a5ca7  cvttsd2si eax, [rbp+57h+var_98]
0x1800a5cac  mov     [r15+18h], eax
0x1800a5cb0  mov     [rbp+57h+var_C8], r12
0x1800a5cb4  lea     rdx, [rbp+57h+var_C8]
0x1800a5cb8  mov     rcx, r13
0x1800a5cbb  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800a5cc0  mov     edi, eax
0x1800a5cc2  mov     [rbp+57h+var_CC], eax
0x1800a5cc5  test    eax, eax
0x1800a5cc7  jns     short loc_1800A5CE6
0x1800a5cc9  mov     rcx, [rbp+5Fh]; this
0x1800a5ccd  mov     r9d, eax; char *
0x1800a5cd0  lea     r8, aOnecoreBaseFli_80; "onecore\\base\\flighting\\flightsetting"...
0x1800a5cd7  mov     edx, 28h ; '('; void *
0x1800a5cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5ce1  jmp     loc_1800A5E22
0x1800a5ce6  mov     [rbp+57h+var_C0], r12
0x1800a5cea  mov     rcx, [rbp+57h+var_C8]
0x1800a5cee  mov     rax, [rcx]
0x1800a5cf1  lea     rdx, [rbp+57h+var_C0]
0x1800a5cf5  mov     rax, [rax+38h]
0x1800a5cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5cfe  mov     edi, eax
0x1800a5d00  mov     [rbp+57h+var_CC], eax
0x1800a5d03  test    eax, eax
0x1800a5d05  jns     short loc_1800A5D24
0x1800a5d07  mov     edx, 2Ah ; '*'; void *
0x1800a5d0c  lea     r8, aOnecoreBaseFli_80; "onecore\\base\\flighting\\flightsetting"...
0x1800a5d13  mov     r9d, edi; char *
0x1800a5d16  mov     rcx, [rbp+5Fh]; this
0x1800a5d1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5d1f  jmp     loc_1800A5E18
0x1800a5d24  xor     edx, edx; length
0x1800a5d26  mov     rcx, [rbp+57h+var_C0]; string
0x1800a5d2a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a5d30  lea     rcx, [r15+20h]
0x1800a5d34  mov     r8, r14
0x1800a5d37  mov     rdx, rax
0x1800a5d3a  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800a5d3f  mov     edi, eax
0x1800a5d41  mov     [rbp+57h+var_CC], eax
0x1800a5d44  test    eax, eax
0x1800a5d46  jns     short loc_1800A5D4F
0x1800a5d48  mov     edx, 2Bh ; '+'
0x1800a5d4d  jmp     short loc_1800A5D0C
0x1800a5d4f  mov     [rbp+57h+var_B8], r12
0x1800a5d53  mov     r12, [r13+0]
0x1800a5d57  mov     rax, [r12]
0x1800a5d5b  mov     r13, [rax+40h]
0x1800a5d5f  lea     rcx, [rbp+57h+var_B8]
0x1800a5d63  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a5d68  mov     rdi, cs:?s_parametersTag@FSServiceDrivenAction@@0QEBGEB; ushort const * const FSServiceDrivenAction::s_parametersTag
0x1800a5d6f  xor     r9d, r9d
0x1800a5d72  mov     [rbp+57h+length], r9d
0x1800a5d76  inc     r14
0x1800a5d79  cmp     [rdi+r14*2], r9w
0x1800a5d7e  jnz     short loc_1800A5D76
0x1800a5d80  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800a5d84  mov     rcx, r14; unsigned __int64
0x1800a5d87  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a5d8c  test    eax, eax
0x1800a5d8e  jns     short loc_1800A5DA2
0x1800a5d90  xor     r8d, r8d; nNumberOfArguments
0x1800a5d93  lea     edx, [r8+1]; dwExceptionFlags
0x1800a5d97  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a5d9c  call    cs:__imp_RaiseException
0x1800a5da2  lea     r9, [rbp+57h+string]; string
0x1800a5da6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a5daa  mov     edx, [rbp+57h+length]; length
0x1800a5dad  mov     rcx, rdi; sourceString
0x1800a5db0  call    cs:__imp_WindowsCreateStringReference
0x1800a5db6  lea     r8, [rbp+57h+var_B8]
0x1800a5dba  mov     rdx, [rbp+57h+string]
0x1800a5dbe  mov     rcx, r12
0x1800a5dc1  mov     rax, r13
0x1800a5dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5dc9  mov     edi, eax
0x1800a5dcb  mov     [rbp+57h+var_CC], eax
0x1800a5dce  test    eax, eax
0x1800a5dd0  jns     short loc_1800A5DD9
0x1800a5dd2  mov     edx, 30h ; '0'
0x1800a5dd7  jmp     short loc_1800A5DFA
0x1800a5dd9  mov     rax, [r15]
0x1800a5ddc  lea     rdx, [rbp+57h+var_B8]
0x1800a5de0  mov     rcx, r15
0x1800a5de3  mov     rax, [rax+60h]
0x1800a5de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5dec  mov     edi, eax
0x1800a5dee  mov     [rbp+57h+var_CC], eax
0x1800a5df1  test    eax, eax
0x1800a5df3  jns     short loc_1800A5E0E
0x1800a5df5  mov     edx, 31h ; '1'; void *
0x1800a5dfa  mov     r9d, edi; char *
0x1800a5dfd  lea     r8, aOnecoreBaseFli_80; "onecore\\base\\flighting\\flightsetting"...
0x1800a5e04  mov     rcx, [rbp+5Fh]; this
0x1800a5e08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5e0d  nop
0x1800a5e0e  lea     rcx, [rbp+57h+var_B8]
0x1800a5e12  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a5e17  nop
0x1800a5e18  lea     rcx, [rbp+57h+var_C0]; this
0x1800a5e1c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a5e21  nop
0x1800a5e22  lea     rcx, [rbp+57h+var_C8]
0x1800a5e26  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a5e2b  nop
0x1800a5e2c  mov     r14, [rbx+20h]
0x1800a5e30  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a5e35  test    al, al
0x1800a5e37  jz      short loc_1800A5E56
0x1800a5e39  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a5e40  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a5e45  mov     r9, r14; unsigned __int16 *
0x1800a5e48  mov     r8d, [rbx+10h]; int
0x1800a5e4c  mov     edx, [rsi]; int
0x1800a5e4e  mov     rcx, rax; this
0x1800a5e51  call    ?ServiceDrivenActionInitialize_@FlightSettingsAPITelemetryClass@@QEAAXJHPEBG@Z; FlightSettingsAPITelemetryClass::ServiceDrivenActionInitialize_(long,int,ushort const *)
0x1800a5e56  mov     eax, edi
0x1800a5e58  mov     rcx, [rbp+57h+var_48]
0x1800a5e5c  xor     rcx, rsp; StackCookie
0x1800a5e5f  call    __security_check_cookie
0x1800a5e64  lea     r11, [rsp+0F0h+var_30]
0x1800a5e6c  mov     rbx, [r11+50h]
0x1800a5e70  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a5e75  mov     rsp, r11
0x1800a5e78  pop     r15
0x1800a5e7a  pop     r14
0x1800a5e7c  pop     r13
0x1800a5e7e  pop     r12
0x1800a5e80  pop     rdi
0x1800a5e81  pop     rsi
0x1800a5e82  pop     rbp
0x1800a5e83  retn
```

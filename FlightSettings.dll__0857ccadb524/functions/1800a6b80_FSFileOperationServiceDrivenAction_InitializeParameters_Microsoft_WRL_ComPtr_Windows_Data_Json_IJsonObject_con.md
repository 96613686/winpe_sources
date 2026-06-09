# FSFileOperationServiceDrivenAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800a6b80`
- end: `0x1800a6e36`
- name: `?InitializeParameters@FSFileOperationServiceDrivenAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(__int64, struct Windows::Data::Json::IJsonObject **)`
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001c6f4`
- `0x180022a58`
- `0x180087a1c`
- `0x18008907c`
- `0x18009bc98`
- `0x1800a40fc`
- `0x1800a4194`
- `0x1800a6b80`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6bf4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6cbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6da7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6bf4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6cbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a6da7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a6d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6c45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6c45`

## string_xrefs

- `0x1800a6c62`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a6dec`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a6d87`: `DELETEDIR`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FSFileOperationServiceDrivenAction::InitializeParameters(
        __int64 a1,
        struct Windows::Data::Json::IJsonObject **a2)
{
  struct Windows::Data::Json::IJsonObject *v4; // r15
  __int64 (__fastcall *v5)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r12
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const WCHAR *StringRawBuffer; // rax
  struct Windows::Data::Json::IJsonObject *v12; // r15
  __int64 (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, HSTRING, __int64 *); // r12
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  const struct Windows::Internal::String *v17; // rax
  const unsigned __int16 *v18; // rdx
  const struct Windows::Internal::String *v19; // rax
  UINT32 length; // [rsp+20h] [rbp-40h] BYREF
  __int64 v22; // [rsp+28h] [rbp-38h] BYREF
  HSTRING v23; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v23 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  length = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( FSFileOperationServiceDrivenAction::s_fullPathTag[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSFileOperationServiceDrivenAction::s_fullPathTag, length, &hstringHeader, &string);
  v8 = v5(v4, string, &v23);
  v9 = v8;
  if ( v8 >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1 + 56);
    *(_QWORD *)(a1 + 64) = -1;
    *(_QWORD *)(a1 + 72) = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
    v8 = FlightSettingsAPICommon::ExpandEnvironmentPath(StringRawBuffer, (unsigned __int16 **)(a1 + 56));
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 45;
      goto LABEL_9;
    }
    v22 = 0;
    v12 = *a2;
    v13 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, __int64 *))(*(_QWORD *)*a2 + 80LL);
    length = 0;
    do
      ++v6;
    while ( FSFileOperationServiceDrivenAction::s_operationTag[v6] );
    if ( (int)ULongLongToUInt(v6, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSFileOperationServiceDrivenAction::s_operationTag, length, &hstringHeader, &string);
    v14 = v13(v12, string, &v22);
    v9 = v14;
    if ( v14 < 0 )
    {
      v15 = (unsigned int)v14;
      v16 = 48;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
        (const char *)v15,
        length);
      Windows::Internal::String::~String((Windows::Internal::String *)&v22);
      goto LABEL_27;
    }
    v17 = (const struct Windows::Internal::String *)Windows::Internal::StringReference::StringReference(
                                                      &string,
                                                      L"DOWNLOAD");
    if ( (unsigned int)Windows::Internal::String::CompareOrdinal((Windows::Internal::String *)&v22, v17) )
    {
      v19 = (const struct Windows::Internal::String *)Windows::Internal::StringReference::StringReference(
                                                        &string,
                                                        (const unsigned __int16 (*)[7])v18);
      if ( (unsigned int)Windows::Internal::String::CompareOrdinal((Windows::Internal::String *)&v22, v19) )
      {
        if ( WindowsCreateStringReference(L"DELETEDIR", 9u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                             (Windows::Internal::String *)&v22,
                             (const struct Windows::Internal::String *)&string) )
        {
          v9 = -2146698740;
          v15 = 2148268556LL;
          v16 = 63;
          goto LABEL_26;
        }
        *(_DWORD *)(a1 + 152) = 2;
      }
      else
      {
        *(_DWORD *)(a1 + 152) = 1;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 152) = 0;
      string = (HSTRING)(a1 + 128);
      hstringHeader.Reserved.Reserved1 = 0;
      hstringHeader.Reserved.Reserved2[8] = 1;
      FSCommonUtils::GetFileContent(*a2, v18, (unsigned __int8 **)&hstringHeader, (unsigned int *)(a1 + 136));
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>>(&string);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&v22);
    Windows::Internal::String::~String((Windows::Internal::String *)&v23);
    return 0;
  }
  v10 = 44;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
    (const char *)(unsigned int)v8,
    length);
LABEL_27:
  Windows::Internal::String::~String((Windows::Internal::String *)&v23);
  return v9;
}

```

## disassembly

```asm
0x1800a6b80  mov     [rsp-38h+arg_10], rbx
0x1800a6b85  push    rbp
0x1800a6b86  push    rsi
0x1800a6b87  push    rdi
0x1800a6b88  push    r12
0x1800a6b8a  push    r13
0x1800a6b8c  push    r14
0x1800a6b8e  push    r15
0x1800a6b90  mov     rbp, rsp
0x1800a6b93  sub     rsp, 60h
0x1800a6b97  mov     rax, cs:__security_cookie
0x1800a6b9e  xor     rax, rsp
0x1800a6ba1  mov     [rbp+var_8], rax
0x1800a6ba5  mov     r14, rdx
0x1800a6ba8  mov     rdi, rcx
0x1800a6bab  xor     r13d, r13d
0x1800a6bae  mov     [rbp+var_30], r13
0x1800a6bb2  mov     r15, [rdx]
0x1800a6bb5  mov     rax, [r15]
0x1800a6bb8  mov     r12, [rax+50h]
0x1800a6bbc  mov     rbx, cs:?s_fullPathTag@FSFileOperationServiceDrivenAction@@0QEBGEB; ushort const * const FSFileOperationServiceDrivenAction::s_fullPathTag
0x1800a6bc3  mov     [rbp+length], r13d
0x1800a6bc7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a6bcb  mov     rcx, rsi
0x1800a6bce  inc     rcx; unsigned __int64
0x1800a6bd1  cmp     [rbx+rcx*2], r13w
0x1800a6bd6  jnz     short loc_1800A6BCE
0x1800a6bd8  lea     rdx, [rbp+length]; unsigned int *
0x1800a6bdc  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a6be1  test    eax, eax
0x1800a6be3  jns     short loc_1800A6BFA
0x1800a6be5  xor     r9d, r9d; lpArguments
0x1800a6be8  xor     r8d, r8d; nNumberOfArguments
0x1800a6beb  lea     edx, [r9+1]; dwExceptionFlags
0x1800a6bef  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a6bf4  call    cs:__imp_RaiseException
0x1800a6bfa  lea     r9, [rbp+string]; string
0x1800a6bfe  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800a6c02  mov     edx, [rbp+length]; length
0x1800a6c05  mov     rcx, rbx; sourceString
0x1800a6c08  call    cs:__imp_WindowsCreateStringReference
0x1800a6c0e  lea     r8, [rbp+var_30]
0x1800a6c12  mov     rdx, [rbp+string]
0x1800a6c16  mov     rcx, r15
0x1800a6c19  mov     rax, r12
0x1800a6c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c21  mov     ebx, eax
0x1800a6c23  test    eax, eax
0x1800a6c25  jns     short loc_1800A6C2E
0x1800a6c27  mov     edx, 2Ch ; ','
0x1800a6c2c  jmp     short loc_1800A6C62
0x1800a6c2e  lea     rcx, [rdi+38h]
0x1800a6c32  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a6c37  mov     [rdi+40h], rsi
0x1800a6c3b  mov     [rdi+48h], rsi
0x1800a6c3f  xor     edx, edx; length
0x1800a6c41  mov     rcx, [rbp+var_30]; string
0x1800a6c45  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a6c4b  lea     rdx, [rdi+38h]; unsigned __int16 **
0x1800a6c4f  mov     rcx, rax; lpSrc
0x1800a6c52  call    ?ExpandEnvironmentPath@FlightSettingsAPICommon@@SAJPEBGPEAPEAG@Z; FlightSettingsAPICommon::ExpandEnvironmentPath(ushort const *,ushort * *)
0x1800a6c57  mov     ebx, eax
0x1800a6c59  test    eax, eax
0x1800a6c5b  jns     short loc_1800A6C7A
0x1800a6c5d  mov     edx, 2Dh ; '-'; void *
0x1800a6c62  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a6c69  mov     r9d, eax; char *
0x1800a6c6c  mov     rcx, [rbp+38h]; this
0x1800a6c70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c75  jmp     loc_1800A6E07
0x1800a6c7a  mov     [rbp+var_38], r13
0x1800a6c7e  mov     r15, [r14]
0x1800a6c81  mov     rax, [r15]
0x1800a6c84  mov     r12, [rax+50h]
0x1800a6c88  mov     rbx, cs:?s_operationTag@FSFileOperationServiceDrivenAction@@0QEBGEB; ushort const * const FSFileOperationServiceDrivenAction::s_operationTag
0x1800a6c8f  mov     [rbp+length], r13d
0x1800a6c93  inc     rsi
0x1800a6c96  cmp     [rbx+rsi*2], r13w
0x1800a6c9b  jnz     short loc_1800A6C93
0x1800a6c9d  lea     rdx, [rbp+length]; unsigned int *
0x1800a6ca1  mov     rcx, rsi; unsigned __int64
0x1800a6ca4  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a6ca9  test    eax, eax
0x1800a6cab  jns     short loc_1800A6CC2
0x1800a6cad  xor     r9d, r9d; lpArguments
0x1800a6cb0  xor     r8d, r8d; nNumberOfArguments
0x1800a6cb3  lea     edx, [r9+1]; dwExceptionFlags
0x1800a6cb7  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a6cbc  call    cs:__imp_RaiseException
0x1800a6cc2  lea     r9, [rbp+string]; string
0x1800a6cc6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800a6cca  mov     edx, [rbp+length]; length
0x1800a6ccd  mov     rcx, rbx; sourceString
0x1800a6cd0  call    cs:__imp_WindowsCreateStringReference
0x1800a6cd6  lea     r8, [rbp+var_38]
0x1800a6cda  mov     rdx, [rbp+string]
0x1800a6cde  mov     rcx, r15
0x1800a6ce1  mov     rax, r12
0x1800a6ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ce9  mov     ebx, eax
0x1800a6ceb  test    eax, eax
0x1800a6ced  jns     short loc_1800A6CFC
0x1800a6cef  mov     r9d, eax
0x1800a6cf2  mov     edx, 30h ; '0'
0x1800a6cf7  jmp     loc_1800A6DEC
0x1800a6cfc  lea     rdx, aDownload; "DOWNLOAD"
0x1800a6d03  lea     rcx, [rbp+string]; string
0x1800a6d07  call    ??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[9])
0x1800a6d0c  mov     rdx, rax; struct Windows::Internal::String *
0x1800a6d0f  lea     rcx, [rbp+var_38]; this
0x1800a6d13  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800a6d18  test    eax, eax
0x1800a6d1a  jnz     short loc_1800A6D55
0x1800a6d1c  mov     [rdi+98h], r13d
0x1800a6d23  lea     rax, [rdi+80h]
0x1800a6d2a  mov     [rbp+string], rax
0x1800a6d2e  mov     qword ptr [rbp+hstringHeader.Reserved], r13
0x1800a6d32  mov     byte ptr [rbp+hstringHeader.Reserved+8], 1
0x1800a6d36  lea     r9, [rdi+88h]; unsigned int *
0x1800a6d3d  lea     r8, [rbp+hstringHeader]; unsigned __int8 **
0x1800a6d41  mov     rcx, [r14]; struct Windows::Data::Json::IJsonObject *
0x1800a6d44  call    ?GetFileContent@FSCommonUtils@@SAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAPEAEPEAK@Z; FSCommonUtils::GetFileContent(Windows::Data::Json::IJsonObject *,ushort const *,uchar * *,ulong *)
0x1800a6d49  nop
0x1800a6d4a  lea     rcx, [rbp+string]
0x1800a6d4e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>>::~out_param_t<wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>>(void)
0x1800a6d53  jmp     short loc_1800A6DC8
0x1800a6d55  lea     rcx, [rbp+string]; string
0x1800a6d59  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x1800a6d5e  mov     rdx, rax; struct Windows::Internal::String *
0x1800a6d61  lea     rcx, [rbp+var_38]; this
0x1800a6d65  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800a6d6a  test    eax, eax
0x1800a6d6c  jnz     short loc_1800A6D7A
0x1800a6d6e  mov     dword ptr [rdi+98h], 1
0x1800a6d78  jmp     short loc_1800A6DC8
0x1800a6d7a  lea     r9, [rbp+string]; string
0x1800a6d7e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800a6d82  mov     edx, 9; length
0x1800a6d87  lea     rcx, aDeletedir; "DELETEDIR"
0x1800a6d8e  call    cs:__imp_WindowsCreateStringReference
0x1800a6d94  test    eax, eax
0x1800a6d96  jns     short loc_1800A6DAD
0x1800a6d98  xor     r9d, r9d; lpArguments
0x1800a6d9b  xor     r8d, r8d; nNumberOfArguments
0x1800a6d9e  lea     edx, [r9+1]; dwExceptionFlags
0x1800a6da2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a6da7  call    cs:__imp_RaiseException
0x1800a6dad  lea     rdx, [rbp+string]; struct Windows::Internal::String *
0x1800a6db1  lea     rcx, [rbp+var_38]; this
0x1800a6db5  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800a6dba  test    eax, eax
0x1800a6dbc  jnz     short loc_1800A6DDF
0x1800a6dbe  mov     dword ptr [rdi+98h], 2
0x1800a6dc8  lea     rcx, [rbp+var_38]; this
0x1800a6dcc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a6dd1  nop
0x1800a6dd2  lea     rcx, [rbp+var_30]; this
0x1800a6dd6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a6ddb  xor     eax, eax
0x1800a6ddd  jmp     short loc_1800A6E12
0x1800a6ddf  mov     ebx, 800BFA0Ch
0x1800a6de4  mov     r9d, ebx; char *
0x1800a6de7  mov     edx, 3Fh ; '?'; void *
0x1800a6dec  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a6df3  mov     rcx, [rbp+38h]; this
0x1800a6df7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6dfc  nop
0x1800a6dfd  lea     rcx, [rbp+var_38]; this
0x1800a6e01  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a6e06  nop
0x1800a6e07  lea     rcx, [rbp+var_30]; this
0x1800a6e0b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a6e10  mov     eax, ebx
0x1800a6e12  mov     rcx, [rbp+var_8]
0x1800a6e16  xor     rcx, rsp; StackCookie
0x1800a6e19  call    __security_check_cookie
0x1800a6e1e  mov     rbx, [rsp+60h+arg_10]
0x1800a6e26  add     rsp, 60h
0x1800a6e2a  pop     r15
0x1800a6e2c  pop     r14
0x1800a6e2e  pop     r13
0x1800a6e30  pop     r12
0x1800a6e32  pop     rdi
0x1800a6e33  pop     rsi
0x1800a6e34  pop     rbp
0x1800a6e35  retn
```

# FSAllowlistPrivilegedAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800acf30`
- end: `0x1800ad290`
- name: `?InitializeParameters@FSAllowlistPrivilegedAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `864`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001ec78`
- `0x1800acf30`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acfa4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad05e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad122`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad201`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acfa4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad05e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad122`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800acfb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800acfb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ad215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800acfe4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad0be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad159`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800acfe4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad0be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad159`

## string_xrefs

- `0x1800ad19e`: `Replace`
- `0x1800ad004`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsallowlistprivilegedaction.cpp`
- `0x1800ad096`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsallowlistprivilegedaction.cpp`
- `0x1800ad180`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsallowlistprivilegedaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FSAllowlistPrivilegedAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, HSTRING, HSTRING *); // r12
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, HSTRING, HSTRING *); // r12
  unsigned __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  PCWSTR v17; // rax
  __int64 v18; // rsi
  int (__fastcall *v19)(__int64, HSTRING, HSTRING *); // r12
  unsigned __int64 v20; // rcx
  PCWSTR v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, HSTRING, double *); // r14
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v28; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v29; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+38h] [rbp-38h] BYREF
  double v31; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v30 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  length = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( FSAllowlistPrivilegedAction::s_valueTag[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSAllowlistPrivilegedAction::s_valueTag, length, &hstringHeader, &string);
  v8 = v5(v4, string, &v30);
  v9 = v8;
  if ( v8 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v30, 0);
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           a1 + 56,
           StringRawBuffer,
           -1);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 47;
      goto LABEL_9;
    }
    v28 = 0;
    v12 = *a2;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
    length = 0;
    v14 = -1;
    do
      ++v14;
    while ( FSAllowlistPrivilegedAction::s_typeTag[v14] );
    if ( (int)ULongLongToUInt(v14, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSAllowlistPrivilegedAction::s_typeTag, length, &hstringHeader, &string);
    v15 = v13(v12, string, &v28);
    v9 = v15;
    if ( v15 < 0 )
    {
      v16 = 51;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsallowlistprivilegedaction.cpp",
        (const char *)(unsigned int)v15,
        length);
LABEL_17:
      Windows::Internal::String::~String((Windows::Internal::String *)&v28);
      goto LABEL_37;
    }
    v17 = WindowsGetStringRawBuffer(v28, 0);
    v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            a1 + 80,
            v17,
            -1);
    v9 = v15;
    if ( v15 < 0 )
    {
      v16 = 52;
      goto LABEL_16;
    }
    v29 = 0;
    v18 = *a2;
    v19 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
    length = 0;
    v20 = -1;
    do
      ++v20;
    while ( FSAllowlistPrivilegedAction::s_commandTag[v20] );
    if ( (int)ULongLongToUInt(v20, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSAllowlistPrivilegedAction::s_commandTag, length, &hstringHeader, &string);
    if ( v19(v18, string, &v29) < 0 )
    {
      v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              a1 + 104,
              L"Replace",
              -1);
      v9 = v22;
      if ( v22 < 0 )
      {
        v23 = 63;
        goto LABEL_27;
      }
    }
    else
    {
      v21 = WindowsGetStringRawBuffer(v29, 0);
      v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              a1 + 104,
              v21,
              -1);
      v9 = v22;
      if ( v22 < 0 )
      {
        v23 = 58;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsallowlistprivilegedaction.cpp",
          (const char *)(unsigned int)v22,
          length);
        Windows::Internal::String::~String((Windows::Internal::String *)&v29);
        goto LABEL_17;
      }
    }
    v31 = 0.0;
    v24 = *a2;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)*a2 + 88LL);
    length = 0;
    do
      ++v6;
    while ( FSAllowlistPrivilegedAction::s_versionTag[v6] );
    if ( (int)ULongLongToUInt(v6, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSAllowlistPrivilegedAction::s_versionTag, length, &hstringHeader, &string);
    v22 = v25(v24, string, &v31);
    v9 = v22;
    if ( v22 >= 0 )
    {
      *(_DWORD *)(a1 + 128) = (int)v31;
      Windows::Internal::String::~String((Windows::Internal::String *)&v29);
      Windows::Internal::String::~String((Windows::Internal::String *)&v28);
      v9 = 0;
      goto LABEL_37;
    }
    v23 = 68;
    goto LABEL_27;
  }
  v10 = 46;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsallowlistprivilegedaction.cpp",
    (const char *)(unsigned int)v8,
    length);
LABEL_37:
  Windows::Internal::String::~String((Windows::Internal::String *)&v30);
  return v9;
}

```

## disassembly

```asm
0x1800acf30  mov     [rsp-38h+arg_10], rbx
0x1800acf35  push    rbp
0x1800acf36  push    rsi
0x1800acf37  push    rdi
0x1800acf38  push    r12
0x1800acf3a  push    r13
0x1800acf3c  push    r14
0x1800acf3e  push    r15
0x1800acf40  mov     rbp, rsp
0x1800acf43  sub     rsp, 70h
0x1800acf47  mov     rax, cs:__security_cookie
0x1800acf4e  xor     rax, rsp
0x1800acf51  mov     [rbp+var_8], rax
0x1800acf55  mov     r14, rdx
0x1800acf58  mov     r15, rcx
0x1800acf5b  xor     r13d, r13d
0x1800acf5e  mov     [rbp+var_38], r13
0x1800acf62  mov     rsi, [rdx]
0x1800acf65  mov     rax, [rsi]
0x1800acf68  mov     r12, [rax+50h]
0x1800acf6c  mov     rbx, cs:?s_valueTag@FSAllowlistPrivilegedAction@@0QEBGEB; ushort const * const FSAllowlistPrivilegedAction::s_valueTag
0x1800acf73  mov     [rbp+length], r13d
0x1800acf77  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800acf7b  mov     rcx, rdi
0x1800acf7e  inc     rcx; unsigned __int64
0x1800acf81  cmp     [rbx+rcx*2], r13w
0x1800acf86  jnz     short loc_1800ACF7E
0x1800acf88  lea     rdx, [rbp+length]; unsigned int *
0x1800acf8c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800acf91  test    eax, eax
0x1800acf93  jns     short loc_1800ACFAA
0x1800acf95  xor     r9d, r9d; lpArguments
0x1800acf98  xor     r8d, r8d; nNumberOfArguments
0x1800acf9b  lea     edx, [r9+1]; dwExceptionFlags
0x1800acf9f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800acfa4  call    cs:__imp_RaiseException
0x1800acfaa  lea     r9, [rbp+string]; string
0x1800acfae  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800acfb2  mov     edx, [rbp+length]; length
0x1800acfb5  mov     rcx, rbx; sourceString
0x1800acfb8  call    cs:__imp_WindowsCreateStringReference
0x1800acfbe  lea     r8, [rbp+var_38]
0x1800acfc2  mov     rdx, [rbp+string]
0x1800acfc6  mov     rcx, rsi
0x1800acfc9  mov     rax, r12
0x1800acfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acfd1  mov     ebx, eax
0x1800acfd3  test    eax, eax
0x1800acfd5  jns     short loc_1800ACFDE
0x1800acfd7  mov     edx, 2Eh ; '.'
0x1800acfdc  jmp     short loc_1800AD004
0x1800acfde  xor     edx, edx; length
0x1800acfe0  mov     rcx, [rbp+var_38]; string
0x1800acfe4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800acfea  lea     rcx, [r15+38h]
0x1800acfee  mov     r8, rdi
0x1800acff1  mov     rdx, rax
0x1800acff4  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800acff9  mov     ebx, eax
0x1800acffb  test    eax, eax
0x1800acffd  jns     short loc_1800AD01C
0x1800acfff  mov     edx, 2Fh ; '/'; void *
0x1800ad004  lea     r8, aOnecoreBaseFli_42; "onecore\\base\\flighting\\flightsetting"...
0x1800ad00b  mov     r9d, eax; char *
0x1800ad00e  mov     rcx, [rbp+38h]; this
0x1800ad012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad017  jmp     loc_1800AD261
0x1800ad01c  mov     [rbp+var_48], r13
0x1800ad020  mov     rsi, [r14]
0x1800ad023  mov     rax, [rsi]
0x1800ad026  mov     r12, [rax+50h]
0x1800ad02a  mov     rbx, cs:?s_typeTag@FSAllowlistPrivilegedAction@@0QEBGEB; ushort const * const FSAllowlistPrivilegedAction::s_typeTag
0x1800ad031  mov     [rbp+length], r13d
0x1800ad035  mov     rcx, rdi
0x1800ad038  inc     rcx; unsigned __int64
0x1800ad03b  cmp     [rbx+rcx*2], r13w
0x1800ad040  jnz     short loc_1800AD038
0x1800ad042  lea     rdx, [rbp+length]; unsigned int *
0x1800ad046  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ad04b  test    eax, eax
0x1800ad04d  jns     short loc_1800AD064
0x1800ad04f  xor     r9d, r9d; lpArguments
0x1800ad052  xor     r8d, r8d; nNumberOfArguments
0x1800ad055  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad059  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ad05e  call    cs:__imp_RaiseException
0x1800ad064  lea     r9, [rbp+string]; string
0x1800ad068  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ad06c  mov     edx, [rbp+length]; length
0x1800ad06f  mov     rcx, rbx; sourceString
0x1800ad072  call    cs:__imp_WindowsCreateStringReference
0x1800ad078  lea     r8, [rbp+var_48]
0x1800ad07c  mov     rdx, [rbp+string]
0x1800ad080  mov     rcx, rsi
0x1800ad083  mov     rax, r12
0x1800ad086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad08b  mov     ebx, eax
0x1800ad08d  test    eax, eax
0x1800ad08f  jns     short loc_1800AD0B8
0x1800ad091  mov     edx, 33h ; '3'; void *
0x1800ad096  lea     r8, aOnecoreBaseFli_42; "onecore\\base\\flighting\\flightsetting"...
0x1800ad09d  mov     r9d, eax; char *
0x1800ad0a0  mov     rcx, [rbp+38h]; this
0x1800ad0a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad0a9  nop
0x1800ad0aa  lea     rcx, [rbp+var_48]; this
0x1800ad0ae  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad0b3  jmp     loc_1800AD261
0x1800ad0b8  xor     edx, edx; length
0x1800ad0ba  mov     rcx, [rbp+var_48]; string
0x1800ad0be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad0c4  lea     rcx, [r15+50h]
0x1800ad0c8  mov     r8, rdi
0x1800ad0cb  mov     rdx, rax
0x1800ad0ce  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ad0d3  mov     ebx, eax
0x1800ad0d5  test    eax, eax
0x1800ad0d7  jns     short loc_1800AD0E0
0x1800ad0d9  mov     edx, 34h ; '4'
0x1800ad0de  jmp     short loc_1800AD096
0x1800ad0e0  mov     [rbp+var_40], r13
0x1800ad0e4  mov     rsi, [r14]
0x1800ad0e7  mov     rax, [rsi]
0x1800ad0ea  mov     r12, [rax+50h]
0x1800ad0ee  mov     rbx, cs:?s_commandTag@FSAllowlistPrivilegedAction@@0QEBGEB; ushort const * const FSAllowlistPrivilegedAction::s_commandTag
0x1800ad0f5  mov     [rbp+length], r13d
0x1800ad0f9  mov     rcx, rdi
0x1800ad0fc  inc     rcx; unsigned __int64
0x1800ad0ff  cmp     [rbx+rcx*2], r13w
0x1800ad104  jnz     short loc_1800AD0FC
0x1800ad106  lea     rdx, [rbp+length]; unsigned int *
0x1800ad10a  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ad10f  test    eax, eax
0x1800ad111  jns     short loc_1800AD128
0x1800ad113  xor     r9d, r9d; lpArguments
0x1800ad116  xor     r8d, r8d; nNumberOfArguments
0x1800ad119  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad11d  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ad122  call    cs:__imp_RaiseException
0x1800ad128  lea     r9, [rbp+string]; string
0x1800ad12c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ad130  mov     edx, [rbp+length]; length
0x1800ad133  mov     rcx, rbx; sourceString
0x1800ad136  call    cs:__imp_WindowsCreateStringReference
0x1800ad13c  lea     r8, [rbp+var_40]
0x1800ad140  mov     rdx, [rbp+string]
0x1800ad144  mov     rcx, rsi
0x1800ad147  mov     rax, r12
0x1800ad14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad14f  test    eax, eax
0x1800ad151  js      short loc_1800AD19B
0x1800ad153  xor     edx, edx; length
0x1800ad155  mov     rcx, [rbp+var_40]; string
0x1800ad159  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad15f  mov     r8, rdi
0x1800ad162  mov     rdx, rax
0x1800ad165  lea     rcx, [r15+68h]
0x1800ad169  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ad16e  mov     ebx, eax
0x1800ad170  test    eax, eax
0x1800ad172  jns     short loc_1800AD1BB
0x1800ad174  mov     edx, 3Ah ; ':'; void *
0x1800ad179  mov     rcx, [rbp+38h]; this
0x1800ad17d  mov     r9d, eax; char *
0x1800ad180  lea     r8, aOnecoreBaseFli_42; "onecore\\base\\flighting\\flightsetting"...
0x1800ad187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad18c  nop
0x1800ad18d  lea     rcx, [rbp+var_40]; this
0x1800ad191  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad196  jmp     loc_1800AD0AA
0x1800ad19b  mov     r8, rdi
0x1800ad19e  lea     rdx, aReplace; "Replace"
0x1800ad1a5  lea     rcx, [r15+68h]
0x1800ad1a9  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ad1ae  mov     ebx, eax
0x1800ad1b0  test    eax, eax
0x1800ad1b2  jns     short loc_1800AD1BB
0x1800ad1b4  mov     edx, 3Fh ; '?'
0x1800ad1b9  jmp     short loc_1800AD179
0x1800ad1bb  xorps   xmm0, xmm0
0x1800ad1be  movsd   [rbp+var_30], xmm0
0x1800ad1c3  mov     rsi, [r14]
0x1800ad1c6  mov     rax, [rsi]
0x1800ad1c9  mov     r14, [rax+58h]
0x1800ad1cd  mov     rbx, cs:?s_versionTag@FSAllowlistPrivilegedAction@@0QEBGEB; ushort const * const FSAllowlistPrivilegedAction::s_versionTag
0x1800ad1d4  mov     [rbp+length], r13d
0x1800ad1d8  inc     rdi
0x1800ad1db  cmp     [rbx+rdi*2], r13w
0x1800ad1e0  jnz     short loc_1800AD1D8
0x1800ad1e2  lea     rdx, [rbp+length]; unsigned int *
0x1800ad1e6  mov     rcx, rdi; unsigned __int64
0x1800ad1e9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ad1ee  test    eax, eax
0x1800ad1f0  jns     short loc_1800AD207
0x1800ad1f2  xor     r9d, r9d; lpArguments
0x1800ad1f5  xor     r8d, r8d; nNumberOfArguments
0x1800ad1f8  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad1fc  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ad201  call    cs:__imp_RaiseException
0x1800ad207  lea     r9, [rbp+string]; string
0x1800ad20b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ad20f  mov     edx, [rbp+length]; length
0x1800ad212  mov     rcx, rbx; sourceString
0x1800ad215  call    cs:__imp_WindowsCreateStringReference
0x1800ad21b  lea     r8, [rbp+var_30]
0x1800ad21f  mov     rdx, [rbp+string]
0x1800ad223  mov     rcx, rsi
0x1800ad226  mov     rax, r14
0x1800ad229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad22e  mov     ebx, eax
0x1800ad230  test    eax, eax
0x1800ad232  jns     short loc_1800AD23E
0x1800ad234  mov     edx, 44h ; 'D'
0x1800ad239  jmp     loc_1800AD179
0x1800ad23e  cvttsd2si rax, [rbp+var_30]
0x1800ad244  mov     [r15+80h], eax
0x1800ad24b  lea     rcx, [rbp+var_40]; this
0x1800ad24f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad254  nop
0x1800ad255  lea     rcx, [rbp+var_48]; this
0x1800ad259  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad25e  mov     ebx, r13d
0x1800ad261  lea     rcx, [rbp+var_38]; this
0x1800ad265  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ad26a  mov     eax, ebx
0x1800ad26c  mov     rcx, [rbp+var_8]
0x1800ad270  xor     rcx, rsp; StackCookie
0x1800ad273  call    __security_check_cookie
0x1800ad278  mov     rbx, [rsp+70h+arg_10]
0x1800ad280  add     rsp, 70h
0x1800ad284  pop     r15
0x1800ad286  pop     r14
0x1800ad288  pop     r13
0x1800ad28a  pop     r12
0x1800ad28c  pop     rdi
0x1800ad28d  pop     rsi
0x1800ad28e  pop     rbp
0x1800ad28f  retn
```

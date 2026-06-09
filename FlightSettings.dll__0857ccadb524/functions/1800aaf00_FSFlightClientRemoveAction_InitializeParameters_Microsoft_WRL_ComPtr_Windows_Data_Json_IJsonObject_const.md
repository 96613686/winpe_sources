# FSFlightClientRemoveAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800aaf00`
- end: `0x1800ab19a`
- name: `?InitializeParameters@FSFlightClientRemoveAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `666`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001ec78`
- `0x1800aaf00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aaf74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab029`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab0e3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aaf74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab029`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab0e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aaf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab0f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aaf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab0f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aafab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aafab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab123`

## string_xrefs

- `0x1800aafd1`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsflightclientremoveaction.cpp`
- `0x1800ab061`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsflightclientremoveaction.cpp`
- `0x1800ab146`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsflightclientremoveaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FSFlightClientRemoveAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // rsi
  int (__fastcall *v5)(__int64, HSTRING, HSTRING *); // r15
  unsigned __int64 v6; // rcx
  PCWSTR v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, HSTRING, HSTRING *); // r15
  unsigned __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING, HSTRING *); // rsi
  unsigned __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  PCWSTR v21; // rax
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v24; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v25; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v26; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v26 = 0;
  v4 = *a2;
  v5 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  length = 0;
  v6 = -1;
  do
    ++v6;
  while ( FSFlightClientRemoveAction::s_flightIdTag[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSFlightClientRemoveAction::s_flightIdTag, length, &hstringHeader, &string);
  if ( v5(v4, string, &v26) < 0 )
  {
    v24 = 0;
    v10 = *a2;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)*a2 + 80LL);
    length = 0;
    v12 = -1;
    do
      ++v12;
    while ( FSFlightClientRemoveAction::s_flightTypeTag[v12] );
    if ( (int)ULongLongToUInt(v12, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSFlightClientRemoveAction::s_flightTypeTag, length, &hstringHeader, &string);
    v13 = v11(v10, string, &v24);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 30;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsflightclientremoveaction.cpp",
        (const char *)(unsigned int)v13,
        length);
LABEL_27:
      Windows::Internal::String::~String((Windows::Internal::String *)&v24);
      goto LABEL_28;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v24, 0);
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            a1 + 56,
            StringRawBuffer,
            -1);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 31;
      goto LABEL_14;
    }
    v25 = 0;
    v16 = *a2;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v16 + 80LL);
    length = 0;
    v18 = -1;
    do
      ++v18;
    while ( FSFlightClientRemoveAction::s_uniqueIdTag[v18] );
    if ( (int)ULongLongToUInt(v18, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSFlightClientRemoveAction::s_uniqueIdTag, length, &hstringHeader, &string);
    v19 = v17(v16, string, &v25);
    v9 = v19;
    if ( v19 >= 0 )
    {
      v21 = WindowsGetStringRawBuffer(v25, 0);
      v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              a1 + 104,
              v21,
              -1);
      v9 = v19;
      if ( v19 >= 0 )
      {
LABEL_26:
        Windows::Internal::String::~String((Windows::Internal::String *)&v25);
        goto LABEL_27;
      }
      v20 = 36;
    }
    else
    {
      v20 = 35;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsflightclientremoveaction.cpp",
      (const char *)(unsigned int)v19,
      length);
    goto LABEL_26;
  }
  v7 = WindowsGetStringRawBuffer(v26, 0);
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(a1 + 80, v7, -1);
  v9 = v8;
  if ( v8 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsflightclientremoveaction.cpp",
      (const char *)(unsigned int)v8,
      length);
LABEL_28:
  Windows::Internal::String::~String((Windows::Internal::String *)&v26);
  return v9;
}

```

## disassembly

```asm
0x1800aaf00  mov     [rsp-38h+arg_10], rbx
0x1800aaf05  push    rbp
0x1800aaf06  push    rsi
0x1800aaf07  push    rdi
0x1800aaf08  push    r12
0x1800aaf0a  push    r13
0x1800aaf0c  push    r14
0x1800aaf0e  push    r15
0x1800aaf10  mov     rbp, rsp
0x1800aaf13  sub     rsp, 70h
0x1800aaf17  mov     rax, cs:__security_cookie
0x1800aaf1e  xor     rax, rsp
0x1800aaf21  mov     [rbp+var_10], rax
0x1800aaf25  mov     rdi, rdx
0x1800aaf28  mov     r14, rcx
0x1800aaf2b  xor     r12d, r12d
0x1800aaf2e  mov     [rbp+var_38], r12
0x1800aaf32  mov     rsi, [rdx]
0x1800aaf35  mov     rax, [rsi]
0x1800aaf38  mov     r15, [rax+50h]
0x1800aaf3c  mov     rbx, cs:?s_flightIdTag@FSFlightClientRemoveAction@@0QEBGEB; ushort const * const FSFlightClientRemoveAction::s_flightIdTag
0x1800aaf43  mov     [rbp+length], r12d
0x1800aaf47  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800aaf4b  mov     rcx, r13
0x1800aaf4e  inc     rcx; unsigned __int64
0x1800aaf51  cmp     [rbx+rcx*2], r12w
0x1800aaf56  jnz     short loc_1800AAF4E
0x1800aaf58  lea     rdx, [rbp+length]; unsigned int *
0x1800aaf5c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800aaf61  test    eax, eax
0x1800aaf63  jns     short loc_1800AAF7A
0x1800aaf65  xor     r9d, r9d; lpArguments
0x1800aaf68  xor     r8d, r8d; nNumberOfArguments
0x1800aaf6b  lea     edx, [r9+1]; dwExceptionFlags
0x1800aaf6f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800aaf74  call    cs:__imp_RaiseException
0x1800aaf7a  lea     r9, [rbp+string]; string
0x1800aaf7e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800aaf82  mov     edx, [rbp+length]; length
0x1800aaf85  mov     rcx, rbx; sourceString
0x1800aaf88  call    cs:__imp_WindowsCreateStringReference
0x1800aaf8e  lea     r8, [rbp+var_38]
0x1800aaf92  mov     rdx, [rbp+string]
0x1800aaf96  mov     rcx, rsi
0x1800aaf99  mov     rax, r15
0x1800aaf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aafa1  test    eax, eax
0x1800aafa3  js      short loc_1800AAFE7
0x1800aafa5  xor     edx, edx; length
0x1800aafa7  mov     rcx, [rbp+var_38]; string
0x1800aafab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aafb1  lea     rcx, [r14+50h]
0x1800aafb5  mov     r8, r13
0x1800aafb8  mov     rdx, rax
0x1800aafbb  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800aafc0  mov     ebx, eax
0x1800aafc2  test    eax, eax
0x1800aafc4  jns     loc_1800AB16B
0x1800aafca  mov     rcx, [rbp+38h]; this
0x1800aafce  mov     r9d, eax; char *
0x1800aafd1  lea     r8, aOnecoreBaseFli_51; "onecore\\base\\flighting\\flightsetting"...
0x1800aafd8  mov     edx, 19h; void *
0x1800aafdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aafe2  jmp     loc_1800AB16B
0x1800aafe7  mov     [rbp+var_48], r12
0x1800aafeb  mov     rsi, [rdi]
0x1800aafee  mov     rax, [rsi]
0x1800aaff1  mov     r15, [rax+50h]
0x1800aaff5  mov     rbx, cs:?s_flightTypeTag@FSFlightClientRemoveAction@@0QEBGEB; ushort const * const FSFlightClientRemoveAction::s_flightTypeTag
0x1800aaffc  mov     [rbp+length], r12d
0x1800ab000  mov     rcx, r13
0x1800ab003  inc     rcx; unsigned __int64
0x1800ab006  cmp     [rbx+rcx*2], r12w
0x1800ab00b  jnz     short loc_1800AB003
0x1800ab00d  lea     rdx, [rbp+length]; unsigned int *
0x1800ab011  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ab016  test    eax, eax
0x1800ab018  jns     short loc_1800AB02F
0x1800ab01a  xor     r9d, r9d; lpArguments
0x1800ab01d  xor     r8d, r8d; nNumberOfArguments
0x1800ab020  lea     edx, [r9+1]; dwExceptionFlags
0x1800ab024  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ab029  call    cs:__imp_RaiseException
0x1800ab02f  lea     r9, [rbp+string]; string
0x1800ab033  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ab037  mov     edx, [rbp+length]; length
0x1800ab03a  mov     rcx, rbx; sourceString
0x1800ab03d  call    cs:__imp_WindowsCreateStringReference
0x1800ab043  lea     r8, [rbp+var_48]
0x1800ab047  mov     rdx, [rbp+string]
0x1800ab04b  mov     rcx, rsi
0x1800ab04e  mov     rax, r15
0x1800ab051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab056  mov     ebx, eax
0x1800ab058  test    eax, eax
0x1800ab05a  jns     short loc_1800AB079
0x1800ab05c  mov     edx, 1Eh; void *
0x1800ab061  lea     r8, aOnecoreBaseFli_51; "onecore\\base\\flighting\\flightsetting"...
0x1800ab068  mov     r9d, eax; char *
0x1800ab06b  mov     rcx, [rbp+38h]; this
0x1800ab06f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab074  jmp     loc_1800AB161
0x1800ab079  xor     edx, edx; length
0x1800ab07b  mov     rcx, [rbp+var_48]; string
0x1800ab07f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ab085  lea     rcx, [r14+38h]
0x1800ab089  mov     r8, r13
0x1800ab08c  mov     rdx, rax
0x1800ab08f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ab094  mov     ebx, eax
0x1800ab096  test    eax, eax
0x1800ab098  jns     short loc_1800AB0A1
0x1800ab09a  mov     edx, 1Fh
0x1800ab09f  jmp     short loc_1800AB061
0x1800ab0a1  mov     [rbp+var_40], r12
0x1800ab0a5  mov     rdi, [rdi]
0x1800ab0a8  mov     rax, [rdi]
0x1800ab0ab  mov     rsi, [rax+50h]
0x1800ab0af  mov     rbx, cs:?s_uniqueIdTag@FSFlightClientRemoveAction@@0QEBGEB; ushort const * const FSFlightClientRemoveAction::s_uniqueIdTag
0x1800ab0b6  mov     [rbp+length], r12d
0x1800ab0ba  mov     rcx, r13
0x1800ab0bd  inc     rcx; unsigned __int64
0x1800ab0c0  cmp     [rbx+rcx*2], r12w
0x1800ab0c5  jnz     short loc_1800AB0BD
0x1800ab0c7  lea     rdx, [rbp+length]; unsigned int *
0x1800ab0cb  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ab0d0  test    eax, eax
0x1800ab0d2  jns     short loc_1800AB0E9
0x1800ab0d4  xor     r9d, r9d; lpArguments
0x1800ab0d7  xor     r8d, r8d; nNumberOfArguments
0x1800ab0da  lea     edx, [r9+1]; dwExceptionFlags
0x1800ab0de  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ab0e3  call    cs:__imp_RaiseException
0x1800ab0e9  lea     r9, [rbp+string]; string
0x1800ab0ed  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ab0f1  mov     edx, [rbp+length]; length
0x1800ab0f4  mov     rcx, rbx; sourceString
0x1800ab0f7  call    cs:__imp_WindowsCreateStringReference
0x1800ab0fd  lea     r8, [rbp+var_40]
0x1800ab101  mov     rdx, [rbp+string]
0x1800ab105  mov     rcx, rdi
0x1800ab108  mov     rax, rsi
0x1800ab10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab110  mov     ebx, eax
0x1800ab112  test    eax, eax
0x1800ab114  jns     short loc_1800AB11D
0x1800ab116  mov     edx, 23h ; '#'
0x1800ab11b  jmp     short loc_1800AB143
0x1800ab11d  xor     edx, edx; length
0x1800ab11f  mov     rcx, [rbp+var_40]; string
0x1800ab123  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ab129  lea     rcx, [r14+68h]
0x1800ab12d  mov     r8, r13
0x1800ab130  mov     rdx, rax
0x1800ab133  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ab138  mov     ebx, eax
0x1800ab13a  test    eax, eax
0x1800ab13c  jns     short loc_1800AB157
0x1800ab13e  mov     edx, 24h ; '$'; void *
0x1800ab143  mov     r9d, eax; char *
0x1800ab146  lea     r8, aOnecoreBaseFli_51; "onecore\\base\\flighting\\flightsetting"...
0x1800ab14d  mov     rcx, [rbp+38h]; this
0x1800ab151  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab156  nop
0x1800ab157  lea     rcx, [rbp+var_40]; this
0x1800ab15b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ab160  nop
0x1800ab161  lea     rcx, [rbp+var_48]; this
0x1800ab165  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ab16a  nop
0x1800ab16b  lea     rcx, [rbp+var_38]; this
0x1800ab16f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ab174  mov     eax, ebx
0x1800ab176  mov     rcx, [rbp+var_10]
0x1800ab17a  xor     rcx, rsp; StackCookie
0x1800ab17d  call    __security_check_cookie
0x1800ab182  mov     rbx, [rsp+70h+arg_10]
0x1800ab18a  add     rsp, 70h
0x1800ab18e  pop     r15
0x1800ab190  pop     r14
0x1800ab192  pop     r13
0x1800ab194  pop     r12
0x1800ab196  pop     rdi
0x1800ab197  pop     rsi
0x1800ab198  pop     rbp
0x1800ab199  retn
```

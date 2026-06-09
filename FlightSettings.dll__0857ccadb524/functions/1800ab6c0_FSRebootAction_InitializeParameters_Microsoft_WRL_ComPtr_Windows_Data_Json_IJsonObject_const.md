# FSRebootAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800ab6c0`
- end: `0x1800ab918`
- name: `?InitializeParameters@FSRebootAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `600`
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
- `0x1800ab6c0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab73f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab7d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab856`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab73f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab7d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ab856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab7e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab86a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab7e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ab86a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab896`

## string_xrefs

- `0x1800ab777`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrebootaction.cpp`
- `0x1800ab8b6`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrebootaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FSRebootAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // r14
  __int64 (__fastcall *v5)(__int64, HSTRING, double *); // r15
  unsigned __int64 v6; // rcx
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, HSTRING, double *); // r15
  unsigned __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, HSTRING, HSTRING *); // r14
  unsigned __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  PCWSTR StringRawBuffer; // rax
  UINT32 length; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v20; // [rsp+28h] [rbp-58h] BYREF
  double v21; // [rsp+30h] [rbp-50h] BYREF
  double v22; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v21 = 0.0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)*a2 + 88LL);
  length = 0;
  v6 = -1;
  do
    ++v6;
  while ( FSRebootAction::s_timeoutTag[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSRebootAction::s_timeoutTag, length, &hstringHeader, &string);
  v7 = v5(v4, string, &v21);
  if ( v7 >= 0 )
  {
    v22 = 0.0;
    v9 = *a2;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)*a2 + 88LL);
    length = 0;
    v11 = -1;
    do
      ++v11;
    while ( FSRebootAction::s_reasonTag[v11] );
    if ( (int)ULongLongToUInt(v11, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSRebootAction::s_reasonTag, length, &hstringHeader, &string);
    v7 = v10(v9, string, &v22);
    if ( v7 < 0 )
    {
      v8 = 36;
      goto LABEL_7;
    }
    v20 = 0;
    v12 = *a2;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v12 + 80LL);
    length = 0;
    v14 = -1;
    do
      ++v14;
    while ( FSRebootAction::s_messageTag[v14] );
    if ( (int)ULongLongToUInt(v14, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSRebootAction::s_messageTag, length, &hstringHeader, &string);
    v15 = v13(v12, string, &v20);
    v7 = v15;
    if ( v15 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v20, 0);
      v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              a1 + 64,
              StringRawBuffer,
              -1);
      v7 = v15;
      if ( v15 >= 0 )
      {
        *(_DWORD *)(a1 + 56) = (int)v21;
        *(_DWORD *)(a1 + 60) = (int)v22;
        v7 = 0;
        goto LABEL_24;
      }
      v16 = 42;
    }
    else
    {
      v16 = 40;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrebootaction.cpp",
      (const char *)(unsigned int)v15,
      length);
LABEL_24:
    Windows::Internal::String::~String((Windows::Internal::String *)&v20);
    return (unsigned int)v7;
  }
  v8 = 32;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrebootaction.cpp",
    (const char *)(unsigned int)v7,
    length);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ab6c0  mov     [rsp-28h+arg_10], rbx
0x1800ab6c5  mov     [rsp-28h+arg_18], rsi
0x1800ab6ca  push    rbp
0x1800ab6cb  push    rdi
0x1800ab6cc  push    r12
0x1800ab6ce  push    r14
0x1800ab6d0  push    r15
0x1800ab6d2  mov     rbp, rsp
0x1800ab6d5  sub     rsp, 80h
0x1800ab6dc  movaps  [rsp+80h+var_10], xmm6
0x1800ab6e1  mov     rax, cs:__security_cookie
0x1800ab6e8  xor     rax, rsp
0x1800ab6eb  mov     [rbp+var_20], rax
0x1800ab6ef  mov     rsi, rdx
0x1800ab6f2  mov     rdi, rcx
0x1800ab6f5  xorps   xmm6, xmm6
0x1800ab6f8  movsd   [rbp+var_50], xmm6
0x1800ab6fd  mov     r14, [rdx]
0x1800ab700  mov     rax, [r14]
0x1800ab703  mov     r15, [rax+58h]
0x1800ab707  mov     rbx, cs:?s_timeoutTag@FSRebootAction@@0QEBGEB; ushort const * const FSRebootAction::s_timeoutTag
0x1800ab70e  xor     r12d, r12d
0x1800ab711  mov     [rbp+length], r12d
0x1800ab715  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ab719  inc     rcx; unsigned __int64
0x1800ab71c  cmp     [rbx+rcx*2], r12w
0x1800ab721  jnz     short loc_1800AB719
0x1800ab723  lea     rdx, [rbp+length]; unsigned int *
0x1800ab727  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ab72c  test    eax, eax
0x1800ab72e  jns     short loc_1800AB745
0x1800ab730  xor     r9d, r9d; lpArguments
0x1800ab733  xor     r8d, r8d; nNumberOfArguments
0x1800ab736  lea     edx, [r9+1]; dwExceptionFlags
0x1800ab73a  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ab73f  call    cs:__imp_RaiseException
0x1800ab745  lea     r9, [rbp+string]; string
0x1800ab749  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ab74d  mov     edx, [rbp+length]; length
0x1800ab750  mov     rcx, rbx; sourceString
0x1800ab753  call    cs:__imp_WindowsCreateStringReference
0x1800ab759  lea     r8, [rbp+var_50]
0x1800ab75d  mov     rdx, [rbp+string]
0x1800ab761  mov     rcx, r14
0x1800ab764  mov     rax, r15
0x1800ab767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab76c  mov     ebx, eax
0x1800ab76e  test    eax, eax
0x1800ab770  jns     short loc_1800AB78F
0x1800ab772  mov     edx, 20h ; ' '; void *
0x1800ab777  lea     r8, aOnecoreBaseFli_98; "onecore\\base\\flighting\\flightsetting"...
0x1800ab77e  mov     r9d, ebx; char *
0x1800ab781  mov     rcx, [rbp+28h]; this
0x1800ab785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab78a  jmp     loc_1800AB8E9
0x1800ab78f  movsd   [rbp+var_48], xmm6
0x1800ab794  mov     r14, [rsi]
0x1800ab797  mov     rax, [r14]
0x1800ab79a  mov     r15, [rax+58h]
0x1800ab79e  mov     rbx, cs:?s_reasonTag@FSRebootAction@@0QEBGEB; ushort const * const FSRebootAction::s_reasonTag
0x1800ab7a5  mov     [rbp+length], r12d
0x1800ab7a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ab7ad  inc     rcx; unsigned __int64
0x1800ab7b0  cmp     [rbx+rcx*2], r12w
0x1800ab7b5  jnz     short loc_1800AB7AD
0x1800ab7b7  lea     rdx, [rbp+length]; unsigned int *
0x1800ab7bb  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ab7c0  test    eax, eax
0x1800ab7c2  jns     short loc_1800AB7D9
0x1800ab7c4  xor     r9d, r9d; lpArguments
0x1800ab7c7  xor     r8d, r8d; nNumberOfArguments
0x1800ab7ca  lea     edx, [r9+1]; dwExceptionFlags
0x1800ab7ce  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ab7d3  call    cs:__imp_RaiseException
0x1800ab7d9  lea     r9, [rbp+string]; string
0x1800ab7dd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ab7e1  mov     edx, [rbp+length]; length
0x1800ab7e4  mov     rcx, rbx; sourceString
0x1800ab7e7  call    cs:__imp_WindowsCreateStringReference
0x1800ab7ed  lea     r8, [rbp+var_48]
0x1800ab7f1  mov     rdx, [rbp+string]
0x1800ab7f5  mov     rcx, r14
0x1800ab7f8  mov     rax, r15
0x1800ab7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab800  mov     ebx, eax
0x1800ab802  test    eax, eax
0x1800ab804  jns     short loc_1800AB810
0x1800ab806  mov     edx, 24h ; '$'
0x1800ab80b  jmp     loc_1800AB777
0x1800ab810  mov     [rbp+var_58], r12
0x1800ab814  mov     rsi, [rsi]
0x1800ab817  mov     rax, [rsi]
0x1800ab81a  mov     r14, [rax+50h]
0x1800ab81e  mov     rbx, cs:?s_messageTag@FSRebootAction@@0QEBGEB; ushort const * const FSRebootAction::s_messageTag
0x1800ab825  mov     [rbp+length], r12d
0x1800ab829  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ab82d  mov     rcx, r15
0x1800ab830  inc     rcx; unsigned __int64
0x1800ab833  cmp     [rbx+rcx*2], r12w
0x1800ab838  jnz     short loc_1800AB830
0x1800ab83a  lea     rdx, [rbp+length]; unsigned int *
0x1800ab83e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ab843  test    eax, eax
0x1800ab845  jns     short loc_1800AB85C
0x1800ab847  xor     r9d, r9d; lpArguments
0x1800ab84a  xor     r8d, r8d; nNumberOfArguments
0x1800ab84d  lea     edx, [r9+1]; dwExceptionFlags
0x1800ab851  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ab856  call    cs:__imp_RaiseException
0x1800ab85c  lea     r9, [rbp+string]; string
0x1800ab860  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ab864  mov     edx, [rbp+length]; length
0x1800ab867  mov     rcx, rbx; sourceString
0x1800ab86a  call    cs:__imp_WindowsCreateStringReference
0x1800ab870  lea     r8, [rbp+var_58]
0x1800ab874  mov     rdx, [rbp+string]
0x1800ab878  mov     rcx, rsi
0x1800ab87b  mov     rax, r14
0x1800ab87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab883  mov     ebx, eax
0x1800ab885  test    eax, eax
0x1800ab887  jns     short loc_1800AB890
0x1800ab889  mov     edx, 28h ; '('
0x1800ab88e  jmp     short loc_1800AB8B6
0x1800ab890  xor     edx, edx; length
0x1800ab892  mov     rcx, [rbp+var_58]; string
0x1800ab896  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ab89c  lea     rcx, [rdi+40h]
0x1800ab8a0  mov     r8, r15
0x1800ab8a3  mov     rdx, rax
0x1800ab8a6  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ab8ab  mov     ebx, eax
0x1800ab8ad  test    eax, eax
0x1800ab8af  jns     short loc_1800AB8CB
0x1800ab8b1  mov     edx, 2Ah ; '*'; void *
0x1800ab8b6  lea     r8, aOnecoreBaseFli_98; "onecore\\base\\flighting\\flightsetting"...
0x1800ab8bd  mov     r9d, eax; char *
0x1800ab8c0  mov     rcx, [rbp+28h]; this
0x1800ab8c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab8c9  jmp     short loc_1800AB8E0
0x1800ab8cb  cvttsd2si rax, [rbp+var_50]
0x1800ab8d1  mov     [rdi+38h], eax
0x1800ab8d4  cvttsd2si rax, [rbp+var_48]
0x1800ab8da  mov     [rdi+3Ch], eax
0x1800ab8dd  mov     ebx, r12d
0x1800ab8e0  lea     rcx, [rbp+var_58]; this
0x1800ab8e4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ab8e9  mov     eax, ebx
0x1800ab8eb  mov     rcx, [rbp+var_20]
0x1800ab8ef  xor     rcx, rsp; StackCookie
0x1800ab8f2  call    __security_check_cookie
0x1800ab8f7  lea     r11, [rsp+80h+var_s0]
0x1800ab8ff  mov     rbx, [r11+40h]
0x1800ab903  mov     rsi, [r11+48h]
0x1800ab907  movaps  xmm6, [rsp+80h+var_10]
0x1800ab90c  mov     rsp, r11
0x1800ab90f  pop     r15
0x1800ab911  pop     r14
0x1800ab913  pop     r12
0x1800ab915  pop     rdi
0x1800ab916  pop     rbp
0x1800ab917  retn
```

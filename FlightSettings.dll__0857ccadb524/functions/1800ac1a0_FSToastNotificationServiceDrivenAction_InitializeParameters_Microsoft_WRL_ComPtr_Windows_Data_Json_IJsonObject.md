# FSToastNotificationServiceDrivenAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800ac1a0`
- end: `0x1800ac3f5`
- name: `?InitializeParameters@FSToastNotificationServiceDrivenAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `597`
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
- `0x1800ac1a0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac21f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac2bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac349`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac21f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac2bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac349`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac2d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac35d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac2d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac35d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac389`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac389`

## string_xrefs

- `0x1800ac257`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fstoastnotificationservicedrivenaction.cpp`
- `0x1800ac3ac`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fstoastnotificationservicedrivenaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FSToastNotificationServiceDrivenAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, HSTRING, double *); // r15
  unsigned __int64 v6; // rcx
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, HSTRING, double *); // r15
  unsigned __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, HSTRING *); // rsi
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
  while ( FSToastNotificationServiceDrivenAction::s_reasonToToastHRTag[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(
    FSToastNotificationServiceDrivenAction::s_reasonToToastHRTag,
    length,
    &hstringHeader,
    &string);
  v7 = v5(v4, string, &v21);
  if ( v7 >= 0 )
  {
    *(_DWORD *)(a1 + 56) = (int)v21;
    v22 = 0.0;
    v9 = *a2;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)*a2 + 88LL);
    length = 0;
    v11 = -1;
    do
      ++v11;
    while ( FSToastNotificationServiceDrivenAction::s_numToastsUntilSuppressionTag[v11] );
    if ( (int)ULongLongToUInt(v11, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(
      FSToastNotificationServiceDrivenAction::s_numToastsUntilSuppressionTag,
      length,
      &hstringHeader,
      &string);
    v7 = v10(v9, string, &v22);
    if ( v7 < 0 )
    {
      v8 = 24;
      goto LABEL_7;
    }
    *(_DWORD *)(a1 + 60) = (int)v22;
    v20 = 0;
    v12 = *a2;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v12 + 80LL);
    length = 0;
    v14 = -1;
    do
      ++v14;
    while ( FSToastNotificationServiceDrivenAction::s_toastXmlTag[v14] );
    if ( (int)ULongLongToUInt(v14, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSToastNotificationServiceDrivenAction::s_toastXmlTag, length, &hstringHeader, &string);
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
LABEL_23:
        Windows::Internal::String::~String((Windows::Internal::String *)&v20);
        return (unsigned int)v7;
      }
      v16 = 30;
    }
    else
    {
      v16 = 29;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fstoastnotificationservicedrivenaction.cpp",
      (const char *)(unsigned int)v15,
      length);
    goto LABEL_23;
  }
  v8 = 19;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fstoastnotificationservicedrivenaction.cpp",
    (const char *)(unsigned int)v7,
    length);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ac1a0  mov     [rsp-28h+arg_10], rbx
0x1800ac1a5  mov     [rsp-28h+arg_18], rsi
0x1800ac1aa  push    rbp
0x1800ac1ab  push    rdi
0x1800ac1ac  push    r12
0x1800ac1ae  push    r14
0x1800ac1b0  push    r15
0x1800ac1b2  mov     rbp, rsp
0x1800ac1b5  sub     rsp, 80h
0x1800ac1bc  movaps  [rsp+80h+var_10], xmm6
0x1800ac1c1  mov     rax, cs:__security_cookie
0x1800ac1c8  xor     rax, rsp
0x1800ac1cb  mov     [rbp+var_20], rax
0x1800ac1cf  mov     rdi, rdx
0x1800ac1d2  mov     r14, rcx
0x1800ac1d5  xorps   xmm6, xmm6
0x1800ac1d8  movsd   [rbp+var_50], xmm6
0x1800ac1dd  mov     rsi, [rdx]
0x1800ac1e0  mov     rax, [rsi]
0x1800ac1e3  mov     r15, [rax+58h]
0x1800ac1e7  mov     rbx, cs:?s_reasonToToastHRTag@FSToastNotificationServiceDrivenAction@@0QEBGEB; ushort const * const FSToastNotificationServiceDrivenAction::s_reasonToToastHRTag
0x1800ac1ee  xor     r12d, r12d
0x1800ac1f1  mov     [rbp+length], r12d
0x1800ac1f5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ac1f9  inc     rcx; unsigned __int64
0x1800ac1fc  cmp     [rbx+rcx*2], r12w
0x1800ac201  jnz     short loc_1800AC1F9
0x1800ac203  lea     rdx, [rbp+length]; unsigned int *
0x1800ac207  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ac20c  test    eax, eax
0x1800ac20e  jns     short loc_1800AC225
0x1800ac210  xor     r9d, r9d; lpArguments
0x1800ac213  xor     r8d, r8d; nNumberOfArguments
0x1800ac216  lea     edx, [r9+1]; dwExceptionFlags
0x1800ac21a  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ac21f  call    cs:__imp_RaiseException
0x1800ac225  lea     r9, [rbp+string]; string
0x1800ac229  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ac22d  mov     edx, [rbp+length]; length
0x1800ac230  mov     rcx, rbx; sourceString
0x1800ac233  call    cs:__imp_WindowsCreateStringReference
0x1800ac239  lea     r8, [rbp+var_50]
0x1800ac23d  mov     rdx, [rbp+string]
0x1800ac241  mov     rcx, rsi
0x1800ac244  mov     rax, r15
0x1800ac247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac24c  mov     ebx, eax
0x1800ac24e  test    eax, eax
0x1800ac250  jns     short loc_1800AC26F
0x1800ac252  mov     edx, 13h; void *
0x1800ac257  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\flightsetting"...
0x1800ac25e  mov     r9d, ebx; char *
0x1800ac261  mov     rcx, [rbp+28h]; this
0x1800ac265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac26a  jmp     loc_1800AC3C6
0x1800ac26f  cvttsd2si eax, [rbp+var_50]
0x1800ac274  mov     [r14+38h], eax
0x1800ac278  movsd   [rbp+var_48], xmm6
0x1800ac27d  mov     rsi, [rdi]
0x1800ac280  mov     rax, [rsi]
0x1800ac283  mov     r15, [rax+58h]
0x1800ac287  mov     rbx, cs:?s_numToastsUntilSuppressionTag@FSToastNotificationServiceDrivenAction@@0QEBGEB; ushort const * const FSToastNotificationServiceDrivenAction::s_numToastsUntilSuppressionTag
0x1800ac28e  mov     [rbp+length], r12d
0x1800ac292  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ac296  inc     rcx; unsigned __int64
0x1800ac299  cmp     [rbx+rcx*2], r12w
0x1800ac29e  jnz     short loc_1800AC296
0x1800ac2a0  lea     rdx, [rbp+length]; unsigned int *
0x1800ac2a4  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ac2a9  test    eax, eax
0x1800ac2ab  jns     short loc_1800AC2C2
0x1800ac2ad  xor     r9d, r9d; lpArguments
0x1800ac2b0  xor     r8d, r8d; nNumberOfArguments
0x1800ac2b3  lea     edx, [r9+1]; dwExceptionFlags
0x1800ac2b7  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ac2bc  call    cs:__imp_RaiseException
0x1800ac2c2  lea     r9, [rbp+string]; string
0x1800ac2c6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ac2ca  mov     edx, [rbp+length]; length
0x1800ac2cd  mov     rcx, rbx; sourceString
0x1800ac2d0  call    cs:__imp_WindowsCreateStringReference
0x1800ac2d6  lea     r8, [rbp+var_48]
0x1800ac2da  mov     rdx, [rbp+string]
0x1800ac2de  mov     rcx, rsi
0x1800ac2e1  mov     rax, r15
0x1800ac2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac2e9  mov     ebx, eax
0x1800ac2eb  test    eax, eax
0x1800ac2ed  jns     short loc_1800AC2F9
0x1800ac2ef  mov     edx, 18h
0x1800ac2f4  jmp     loc_1800AC257
0x1800ac2f9  cvttsd2si rax, [rbp+var_48]
0x1800ac2ff  mov     [r14+3Ch], eax
0x1800ac303  mov     [rbp+var_58], r12
0x1800ac307  mov     rdi, [rdi]
0x1800ac30a  mov     rax, [rdi]
0x1800ac30d  mov     rsi, [rax+50h]
0x1800ac311  mov     rbx, cs:?s_toastXmlTag@FSToastNotificationServiceDrivenAction@@0QEBGEB; ushort const * const FSToastNotificationServiceDrivenAction::s_toastXmlTag
0x1800ac318  mov     [rbp+length], r12d
0x1800ac31c  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ac320  mov     rcx, r15
0x1800ac323  inc     rcx; unsigned __int64
0x1800ac326  cmp     [rbx+rcx*2], r12w
0x1800ac32b  jnz     short loc_1800AC323
0x1800ac32d  lea     rdx, [rbp+length]; unsigned int *
0x1800ac331  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ac336  test    eax, eax
0x1800ac338  jns     short loc_1800AC34F
0x1800ac33a  xor     r9d, r9d; lpArguments
0x1800ac33d  xor     r8d, r8d; nNumberOfArguments
0x1800ac340  lea     edx, [r9+1]; dwExceptionFlags
0x1800ac344  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ac349  call    cs:__imp_RaiseException
0x1800ac34f  lea     r9, [rbp+string]; string
0x1800ac353  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ac357  mov     edx, [rbp+length]; length
0x1800ac35a  mov     rcx, rbx; sourceString
0x1800ac35d  call    cs:__imp_WindowsCreateStringReference
0x1800ac363  lea     r8, [rbp+var_58]
0x1800ac367  mov     rdx, [rbp+string]
0x1800ac36b  mov     rcx, rdi
0x1800ac36e  mov     rax, rsi
0x1800ac371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac376  mov     ebx, eax
0x1800ac378  test    eax, eax
0x1800ac37a  jns     short loc_1800AC383
0x1800ac37c  mov     edx, 1Dh
0x1800ac381  jmp     short loc_1800AC3A9
0x1800ac383  xor     edx, edx; length
0x1800ac385  mov     rcx, [rbp+var_58]; string
0x1800ac389  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ac38f  lea     rcx, [r14+40h]
0x1800ac393  mov     r8, r15
0x1800ac396  mov     rdx, rax
0x1800ac399  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800ac39e  mov     ebx, eax
0x1800ac3a0  test    eax, eax
0x1800ac3a2  jns     short loc_1800AC3BD
0x1800ac3a4  mov     edx, 1Eh; void *
0x1800ac3a9  mov     r9d, eax; char *
0x1800ac3ac  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\flightsetting"...
0x1800ac3b3  mov     rcx, [rbp+28h]; this
0x1800ac3b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac3bc  nop
0x1800ac3bd  lea     rcx, [rbp+var_58]; this
0x1800ac3c1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ac3c6  mov     eax, ebx
0x1800ac3c8  mov     rcx, [rbp+var_20]
0x1800ac3cc  xor     rcx, rsp; StackCookie
0x1800ac3cf  call    __security_check_cookie
0x1800ac3d4  lea     r11, [rsp+80h+var_s0]
0x1800ac3dc  mov     rbx, [r11+40h]
0x1800ac3e0  mov     rsi, [r11+48h]
0x1800ac3e4  movaps  xmm6, [rsp+80h+var_10]
0x1800ac3e9  mov     rsp, r11
0x1800ac3ec  pop     r15
0x1800ac3ee  pop     r14
0x1800ac3f0  pop     r12
0x1800ac3f2  pop     rdi
0x1800ac3f3  pop     rbp
0x1800ac3f4  retn
```

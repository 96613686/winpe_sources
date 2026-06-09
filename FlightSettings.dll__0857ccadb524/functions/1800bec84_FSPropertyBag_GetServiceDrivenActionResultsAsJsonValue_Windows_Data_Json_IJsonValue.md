# FSPropertyBag::GetServiceDrivenActionResultsAsJsonValue(Windows::Data::Json::IJsonValue * *)

- ea: `0x1800bec84`
- end: `0x1800beeac`
- name: `?GetServiceDrivenActionResultsAsJsonValue@FSPropertyBag@@AEAAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(FSPropertyBag *__hidden this, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bc3b4`
- `0x1800be044`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001c6f4`
- `0x180032640`
- `0x1800334b4`
- `0x180085a24`
- `0x1800bec84`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bedb0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bee16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bedb0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bee16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bedc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bee2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bedc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bee2e`

## string_xrefs

- `0x1800bece4`: `ServiceDrivenActionResults`
- `0x1800bee27`: `ServiceDrivenActionResults`
- `0x1800bed11`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bed4f`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bee54`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FSPropertyBag::GetServiceDrivenActionResultsAsJsonValue(
        FSPropertyBag *this,
        struct Windows::Data::Json::IJsonValue **a2)
{
  unsigned __int64 v3; // rsi
  int FlightingRegString; // eax
  const unsigned __int16 *v5; // rdx
  unsigned int v6; // edi
  unsigned int v7; // ebx
  __int64 *v8; // rax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // r14
  const WCHAR *v12; // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, HSTRING, struct Windows::Data::Json::IJsonValue **); // rdi
  int v17; // ecx
  UINT32 length[2]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v20; // [rsp+28h] [rbp-58h] BYREF
  __int64 v21; // [rsp+30h] [rbp-50h] BYREF
  PCWSTR sourceString; // [rsp+38h] [rbp-48h] BYREF
  __int64 v23; // [rsp+40h] [rbp-40h]
  __int64 v24; // [rsp+48h] [rbp-38h]
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a2 = 0;
  sourceString = 0;
  v23 = 0;
  v24 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  v3 = -1;
  v23 = -1;
  v24 = -1;
  *(_QWORD *)length = -2147483646;
  FlightingRegString = FSRegUtils::GetFlightingRegString(
                         (HKEY *)length,
                         1u,
                         L"ServiceDrivenActionResults",
                         (unsigned __int16 **)&sourceString);
  v6 = FlightingRegString;
  v7 = -2147024894;
  if ( FlightingRegString != -2147024894 )
  {
    if ( FlightingRegString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69F,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)FlightingRegString,
        length[0]);
      v7 = v6;
      goto LABEL_19;
    }
    v21 = 0;
    v8 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[29])v5);
    v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
           *v8,
           (__int64)&v21);
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A2,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v9,
        length[0]);
LABEL_18:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
      goto LABEL_19;
    }
    v20 = 0;
    v10 = v21;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v21 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
    v12 = sourceString;
    length[0] = 0;
    do
      ++v3;
    while ( sourceString[v3] );
    if ( (int)ULongLongToUInt(v3, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(v12, length[0], &hstringHeader, &string);
    v13 = v11(v10, string, &v20);
    v7 = v13;
    if ( v13 >= 0 )
    {
      v15 = v20;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)v20 + 48LL);
      length[0] = 0;
      if ( (int)ULongLongToUInt(0x1Au, length) < 0 )
        RaiseException(0xC000000D, v17 - 25, 0, 0);
      WindowsCreateStringReference(L"ServiceDrivenActionResults", length[0], &hstringHeader, &string);
      v13 = v16(v15, string, a2);
      v7 = v13;
      if ( v13 >= 0 )
        goto LABEL_17;
      v14 = 1705;
    }
    else
    {
      v14 = 1702;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v13,
      length[0]);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
    goto LABEL_18;
  }
LABEL_19:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  return v7;
}

```

## disassembly

```asm
0x1800bec84  mov     [rsp-28h+arg_0], rbx
0x1800bec89  mov     [rsp-28h+arg_10], rsi
0x1800bec8e  push    rbp
0x1800bec8f  push    rdi
0x1800bec90  push    r12
0x1800bec92  push    r14
0x1800bec94  push    r15
0x1800bec96  mov     rbp, rsp
0x1800bec99  sub     rsp, 80h
0x1800beca0  mov     rax, cs:__security_cookie
0x1800beca7  xor     rax, rsp
0x1800becaa  mov     [rbp+var_10], rax
0x1800becae  mov     r15, rdx
0x1800becb1  xor     r12d, r12d
0x1800becb4  mov     [rdx], r12
0x1800becb7  mov     [rbp+sourceString], r12
0x1800becbb  mov     [rbp+var_40], r12
0x1800becbf  mov     [rbp+var_38], r12
0x1800becc3  lea     rcx, [rbp+sourceString]
0x1800becc7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800beccc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800becd0  mov     [rbp+var_40], rsi
0x1800becd4  mov     [rbp+var_38], rsi
0x1800becd8  mov     qword ptr [rbp+length], 0FFFFFFFF80000002h
0x1800bece0  lea     r9, [rbp+sourceString]
0x1800bece4  lea     r8, aServicedrivena_0; "ServiceDrivenActionResults"
0x1800beceb  lea     edx, [rsi+2]
0x1800becee  lea     rcx, [rbp+length]
0x1800becf2  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x1800becf7  mov     edi, eax
0x1800becf9  mov     ebx, 80070002h
0x1800becfe  cmp     eax, ebx
0x1800bed00  jz      loc_1800BEE79
0x1800bed06  test    eax, eax
0x1800bed08  jns     short loc_1800BED29
0x1800bed0a  mov     rcx, [rbp+28h]; this
0x1800bed0e  mov     r9d, eax; char *
0x1800bed11  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bed18  mov     edx, 69Fh; void *
0x1800bed1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bed22  mov     ebx, edi
0x1800bed24  jmp     loc_1800BEE79
0x1800bed29  mov     [rbp+var_50], r12
0x1800bed2d  lea     rcx, [rbp+string]; string
0x1800bed31  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800bed36  lea     rdx, [rbp+var_50]
0x1800bed3a  mov     rcx, [rax]
0x1800bed3d  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x1800bed42  mov     ebx, eax
0x1800bed44  test    eax, eax
0x1800bed46  jns     short loc_1800BED65
0x1800bed48  mov     rcx, [rbp+28h]; this
0x1800bed4c  mov     r9d, eax; char *
0x1800bed4f  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bed56  mov     edx, 6A2h; void *
0x1800bed5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bed60  jmp     loc_1800BEE6F
0x1800bed65  mov     [rbp+var_58], r12
0x1800bed69  mov     rdi, [rbp+var_50]
0x1800bed6d  mov     rax, [rdi]
0x1800bed70  mov     r14, [rax+30h]
0x1800bed74  lea     rcx, [rbp+var_58]
0x1800bed78  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bed7d  mov     rbx, [rbp+sourceString]
0x1800bed81  mov     [rbp+length], r12d
0x1800bed85  inc     rsi
0x1800bed88  cmp     [rbx+rsi*2], r12w
0x1800bed8d  jnz     short loc_1800BED85
0x1800bed8f  lea     rdx, [rbp+length]; unsigned int *
0x1800bed93  mov     rcx, rsi; unsigned __int64
0x1800bed96  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bed9b  mov     esi, 0C000000Dh
0x1800beda0  test    eax, eax
0x1800beda2  jns     short loc_1800BEDB6
0x1800beda4  xor     r9d, r9d; lpArguments
0x1800beda7  xor     r8d, r8d; nNumberOfArguments
0x1800bedaa  lea     edx, [r9+1]; dwExceptionFlags
0x1800bedae  mov     ecx, esi; dwExceptionCode
0x1800bedb0  call    cs:__imp_RaiseException
0x1800bedb6  lea     r9, [rbp+string]; string
0x1800bedba  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800bedbe  mov     edx, [rbp+length]; length
0x1800bedc1  mov     rcx, rbx; sourceString
0x1800bedc4  call    cs:__imp_WindowsCreateStringReference
0x1800bedca  lea     r8, [rbp+var_58]
0x1800bedce  mov     rdx, [rbp+string]
0x1800bedd2  mov     rcx, rdi
0x1800bedd5  mov     rax, r14
0x1800bedd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beddd  mov     ebx, eax
0x1800beddf  test    eax, eax
0x1800bede1  jns     short loc_1800BEDEA
0x1800bede3  mov     edx, 6A6h
0x1800bede8  jmp     short loc_1800BEE51
0x1800bedea  mov     rbx, [rbp+var_58]
0x1800bedee  mov     rax, [rbx]
0x1800bedf1  mov     rdi, [rax+30h]
0x1800bedf5  mov     [rbp+length], r12d
0x1800bedf9  lea     rdx, [rbp+length]; unsigned int *
0x1800bedfd  mov     ecx, 1Ah; unsigned __int64
0x1800bee02  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bee07  test    eax, eax
0x1800bee09  jns     short loc_1800BEE1C
0x1800bee0b  xor     r9d, r9d; lpArguments
0x1800bee0e  xor     r8d, r8d; nNumberOfArguments
0x1800bee11  lea     edx, [rcx-19h]; dwExceptionFlags
0x1800bee14  mov     ecx, esi; dwExceptionCode
0x1800bee16  call    cs:__imp_RaiseException
0x1800bee1c  lea     r9, [rbp+string]; string
0x1800bee20  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800bee24  mov     edx, [rbp+length]; length
0x1800bee27  lea     rcx, aServicedrivena_0; "ServiceDrivenActionResults"
0x1800bee2e  call    cs:__imp_WindowsCreateStringReference
0x1800bee34  mov     r8, r15
0x1800bee37  mov     rdx, [rbp+string]
0x1800bee3b  mov     rcx, rbx
0x1800bee3e  mov     rax, rdi
0x1800bee41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bee46  mov     ebx, eax
0x1800bee48  test    eax, eax
0x1800bee4a  jns     short loc_1800BEE65
0x1800bee4c  mov     edx, 6A9h; void *
0x1800bee51  mov     r9d, eax; char *
0x1800bee54  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bee5b  mov     rcx, [rbp+28h]; this
0x1800bee5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bee64  nop
0x1800bee65  lea     rcx, [rbp+var_58]
0x1800bee69  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bee6e  nop
0x1800bee6f  lea     rcx, [rbp+var_50]
0x1800bee73  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bee78  nop
0x1800bee79  lea     rcx, [rbp+sourceString]
0x1800bee7d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800bee82  mov     eax, ebx
0x1800bee84  mov     rcx, [rbp+var_10]
0x1800bee88  xor     rcx, rsp; StackCookie
0x1800bee8b  call    __security_check_cookie
0x1800bee90  lea     r11, [rsp+80h+var_s0]
0x1800bee98  mov     rbx, [r11+30h]
0x1800bee9c  mov     rsi, [r11+40h]
0x1800beea0  mov     rsp, r11
0x1800beea3  pop     r15
0x1800beea5  pop     r14
0x1800beea7  pop     r12
0x1800beea9  pop     rdi
0x1800beeaa  pop     rbp
0x1800beeab  retn
```

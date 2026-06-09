# FSServiceDrivenActionResultsSave::SaveToRegistry(void)

- ea: `0x18009c084`
- end: `0x18009c29e`
- name: `?SaveToRegistry@FSServiceDrivenActionResultsSave@@QEAAJXZ`
- size: `538`
- prototype: `__int64 __fastcall(FSServiceDrivenActionResultsSave *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008df40`
- `0x18008e0b8`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x180032640`
- `0x1800327e4`
- `0x18003290c`
- `0x180086944`
- `0x18009c084`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009c148`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009c148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009c12f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009c12f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009c1c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009c20a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009c1c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009c20a`

## string_xrefs

- `0x18009c0fb`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionresultssave.cpp`
- `0x18009c24d`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionresultssave.cpp`
- `0x18009c128`: `ServiceDrivenActionResults`
- `0x18009c1d9`: `ServiceDrivenActionResults`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FSServiceDrivenActionResultsSave::SaveToRegistry(FSServiceDrivenActionResultsSave *this)
{
  int v2; // eax
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 *v6; // rax
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64); // r14
  __int64 v9; // rsi
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  const unsigned __int16 *v14; // rax
  int v15; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v17; // eax
  HSTRING v19; // [rsp+20h] [rbp-50h] BYREF
  __int64 v20; // [rsp+28h] [rbp-48h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-40h] BYREF
  __int64 v22; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v21 = 0;
  v20 = 0;
  v2 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 4,
         (__int64)&v20);
  v4 = v2;
  if ( v2 >= 0 )
  {
    v6 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[29])v3);
    v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v6, &v21);
    v4 = v2;
    if ( v2 < 0 )
    {
      v5 = 51;
      goto LABEL_5;
    }
    v7 = v21;
    v8 = (*v21)[7];
    v9 = v20;
    if ( WindowsCreateStringReference(L"ServiceDrivenActionResults", 0x1Au, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v2 = v8(v7, (GUID *)string, v9);
    v4 = v2;
    if ( v2 < 0 )
    {
      v5 = 52;
      goto LABEL_5;
    }
    v19 = 0;
    v10 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v21,
            (__int64)&v20);
    v4 = v10;
    if ( v10 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 56LL))(v20, &v19);
      v4 = v13;
      if ( v13 >= 0 )
      {
        if ( *((_DWORD *)this + 4) )
        {
          if ( *((_DWORD *)this + 4) != 1 )
          {
            v4 = -2147024809;
            v11 = 2147942487LL;
            v12 = 70;
            goto LABEL_21;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(v19, 0);
          v22 = -2147483646;
          v17 = FSRegUtils::SetFlightingRegString((HKEY *)&v22, 1u, L"ErrorActionResults", StringRawBuffer);
          v4 = v17;
          if ( v17 < 0 )
          {
            v11 = (unsigned int)v17;
            v12 = 66;
            goto LABEL_21;
          }
        }
        else
        {
          v14 = WindowsGetStringRawBuffer(v19, 0);
          v22 = -2147483646;
          v15 = FSRegUtils::SetFlightingRegString((HKEY *)&v22, 1u, L"ServiceDrivenActionResults", v14);
          v4 = v15;
          if ( v15 < 0 )
          {
            v11 = (unsigned int)v15;
            v12 = 62;
            goto LABEL_21;
          }
        }
LABEL_22:
        Windows::Internal::String::~String((Windows::Internal::String *)&v19);
        goto LABEL_23;
      }
      v11 = (unsigned int)v13;
      v12 = 57;
    }
    else
    {
      v11 = (unsigned int)v10;
      v12 = 56;
    }
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionresultssave.cpp",
      (const char *)v11,
      (int)v19);
    goto LABEL_22;
  }
  v5 = 50;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionresultssave.cpp",
    (const char *)(unsigned int)v2,
    (int)v19);
LABEL_23:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  return v4;
}

```

## disassembly

```asm
0x18009c084  mov     [rsp-18h+arg_8], rbx
0x18009c089  mov     [rsp-18h+arg_10], rsi
0x18009c08e  push    rbp
0x18009c08f  push    rdi
0x18009c090  push    r14
0x18009c092  mov     rbp, rsp
0x18009c095  sub     rsp, 70h
0x18009c099  mov     rax, cs:__security_cookie
0x18009c0a0  xor     rax, rsp
0x18009c0a3  mov     [rbp+var_10], rax
0x18009c0a7  mov     rdi, rcx
0x18009c0aa  mov     [rbp+var_40], 0
0x18009c0b2  mov     [rbp+var_48], 0
0x18009c0ba  add     rcx, 20h ; ' '
0x18009c0be  lea     rdx, [rbp+var_48]
0x18009c0c2  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18009c0c7  mov     ebx, eax
0x18009c0c9  test    eax, eax
0x18009c0cb  jns     short loc_18009C0D4
0x18009c0cd  mov     edx, 32h ; '2'
0x18009c0d2  jmp     short loc_18009C0F4
0x18009c0d4  lea     rcx, [rbp+string]; string
0x18009c0d8  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x18009c0dd  lea     rdx, [rbp+var_40]
0x18009c0e1  mov     rcx, [rax]
0x18009c0e4  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18009c0e9  mov     ebx, eax
0x18009c0eb  test    eax, eax
0x18009c0ed  jns     short loc_18009C10C
0x18009c0ef  mov     edx, 33h ; '3'; void *
0x18009c0f4  mov     rcx, [rbp+18h]; this
0x18009c0f8  mov     r9d, eax; char *
0x18009c0fb  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\flightsetting"...
0x18009c102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c107  jmp     loc_18009C268
0x18009c10c  mov     rbx, [rbp+var_40]
0x18009c110  mov     rax, [rbx]
0x18009c113  mov     r14, [rax+38h]
0x18009c117  mov     rsi, [rbp+var_48]
0x18009c11b  lea     r9, [rbp+string]; string
0x18009c11f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18009c123  mov     edx, 1Ah; length
0x18009c128  lea     rcx, aServicedrivena_0; "ServiceDrivenActionResults"
0x18009c12f  call    cs:__imp_WindowsCreateStringReference
0x18009c135  test    eax, eax
0x18009c137  jns     short loc_18009C14E
0x18009c139  xor     r9d, r9d; lpArguments
0x18009c13c  xor     r8d, r8d; nNumberOfArguments
0x18009c13f  lea     edx, [r9+1]; dwExceptionFlags
0x18009c143  mov     ecx, 0C000000Dh; dwExceptionCode
0x18009c148  call    cs:__imp_RaiseException
0x18009c14e  mov     r8, rsi
0x18009c151  mov     rdx, [rbp+string]
0x18009c155  mov     rcx, rbx
0x18009c158  mov     rax, r14
0x18009c15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c160  mov     ebx, eax
0x18009c162  test    eax, eax
0x18009c164  jns     short loc_18009C16D
0x18009c166  mov     edx, 34h ; '4'
0x18009c16b  jmp     short loc_18009C0F4
0x18009c16d  mov     [rbp+var_50], 0
0x18009c175  lea     rdx, [rbp+var_48]
0x18009c179  lea     rcx, [rbp+var_40]
0x18009c17d  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18009c182  mov     ebx, eax
0x18009c184  test    eax, eax
0x18009c186  jns     short loc_18009C195
0x18009c188  mov     r9d, eax
0x18009c18b  mov     edx, 38h ; '8'
0x18009c190  jmp     loc_18009C24D
0x18009c195  mov     rcx, [rbp+var_48]
0x18009c199  mov     rax, [rcx]
0x18009c19c  lea     rdx, [rbp+var_50]
0x18009c1a0  mov     rax, [rax+38h]
0x18009c1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c1a9  mov     ebx, eax
0x18009c1ab  test    eax, eax
0x18009c1ad  jns     short loc_18009C1BC
0x18009c1af  mov     r9d, eax
0x18009c1b2  mov     edx, 39h ; '9'
0x18009c1b7  jmp     loc_18009C24D
0x18009c1bc  cmp     dword ptr [rdi+10h], 0
0x18009c1c0  jnz     short loc_18009C1FE
0x18009c1c2  xor     edx, edx; length
0x18009c1c4  mov     rcx, [rbp+var_50]; string
0x18009c1c8  call    cs:__imp_WindowsGetStringRawBuffer
0x18009c1ce  mov     [rbp+var_38], 0FFFFFFFF80000002h
0x18009c1d6  mov     r9, rax
0x18009c1d9  lea     r8, aServicedrivena_0; "ServiceDrivenActionResults"
0x18009c1e0  mov     edx, 1
0x18009c1e5  lea     rcx, [rbp+var_38]
0x18009c1e9  call    ?SetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBG2@Z; FSRegUtils::SetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort const *)
0x18009c1ee  mov     ebx, eax
0x18009c1f0  test    eax, eax
0x18009c1f2  jns     short loc_18009C25E
0x18009c1f4  mov     r9d, eax
0x18009c1f7  mov     edx, 3Eh ; '>'
0x18009c1fc  jmp     short loc_18009C24D
0x18009c1fe  cmp     dword ptr [rdi+10h], 1
0x18009c202  jnz     short loc_18009C240
0x18009c204  xor     edx, edx; length
0x18009c206  mov     rcx, [rbp+var_50]; string
0x18009c20a  call    cs:__imp_WindowsGetStringRawBuffer
0x18009c210  mov     [rbp+var_38], 0FFFFFFFF80000002h
0x18009c218  mov     r9, rax
0x18009c21b  lea     r8, aErroractionres; "ErrorActionResults"
0x18009c222  mov     edx, 1
0x18009c227  lea     rcx, [rbp+var_38]
0x18009c22b  call    ?SetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBG2@Z; FSRegUtils::SetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort const *)
0x18009c230  mov     ebx, eax
0x18009c232  test    eax, eax
0x18009c234  jns     short loc_18009C25E
0x18009c236  mov     r9d, eax
0x18009c239  mov     edx, 42h ; 'B'
0x18009c23e  jmp     short loc_18009C24D
0x18009c240  mov     ebx, 80070057h
0x18009c245  mov     r9d, ebx; char *
0x18009c248  mov     edx, 46h ; 'F'; void *
0x18009c24d  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\flightsetting"...
0x18009c254  mov     rcx, [rbp+18h]; this
0x18009c258  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c25d  nop
0x18009c25e  lea     rcx, [rbp+var_50]; this
0x18009c262  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18009c267  nop
0x18009c268  lea     rcx, [rbp+var_48]
0x18009c26c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009c271  nop
0x18009c272  lea     rcx, [rbp+var_40]
0x18009c276  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009c27b  mov     eax, ebx
0x18009c27d  mov     rcx, [rbp+var_10]
0x18009c281  xor     rcx, rsp; StackCookie
0x18009c284  call    __security_check_cookie
0x18009c289  lea     r11, [rsp+70h+var_s0]
0x18009c28e  mov     rbx, [r11+28h]
0x18009c292  mov     rsi, [r11+30h]
0x18009c296  mov     rsp, r11
0x18009c299  pop     r14
0x18009c29b  pop     rdi
0x18009c29c  pop     rbp
0x18009c29d  retn
```

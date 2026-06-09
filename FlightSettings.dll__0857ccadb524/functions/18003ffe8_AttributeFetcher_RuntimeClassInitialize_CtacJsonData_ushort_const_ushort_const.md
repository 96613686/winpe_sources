# AttributeFetcher::RuntimeClassInitialize(CtacJsonData *,ushort const *,ushort const *)

- ea: `0x18003ffe8`
- end: `0x18004037f`
- name: `?RuntimeClassInitialize@AttributeFetcher@@QEAAJPEAVCtacJsonData@@PEBG1@Z`
- size: `919`
- prototype: `__int64 __fastcall(AttributeFetcher *__hidden this, struct CtacJsonData *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800335c4`
- `0x180040388`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800107b0`
- `0x1800175b4`
- `0x18001c6f4`
- `0x18001d0f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x1800325f4`
- `0x1800334f0`
- `0x18003b5bc`
- `0x18003d678`
- `0x18003d9ac`
- `0x18003f670`
- `0x18003ffe8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800400b6`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800400b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800400e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800401a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800401e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004021a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800400e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800401a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800401e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004021a`

## string_xrefs

- `0x18004002b`: `Windows.Data.Json.JsonValue`
- `0x180040054`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x1800401c7`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x1800401fa`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x180040231`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x180040296`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x1800402f0`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18004034c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AttributeFetcher::RuntimeClassInitialize(
        AttributeFetcher *this,
        struct CtacJsonData *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char *v6; // r12
  __int64 *v7; // rax
  int v8; // eax
  int v9; // ebx
  unsigned __int64 i; // r14
  int v11; // eax
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64); // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // eax
  __int64 v25; // rdx
  char *v26; // rcx
  int CallingProcessName; // eax
  char *v28; // rcx
  int CallingProcessVer; // eax
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  __int64 v31; // [rsp+28h] [rbp-51h] BYREF
  __int64 v32; // [rsp+30h] [rbp-49h] BYREF
  const unsigned __int16 *v33; // [rsp+38h] [rbp-41h] BYREF
  const unsigned __int16 *v34; // [rsp+40h] [rbp-39h]
  LPWSTR lpsz; // [rsp+48h] [rbp-31h] BYREF
  DWORD cchLength[2]; // [rsp+50h] [rbp-29h]
  __int64 v37; // [rsp+58h] [rbp-21h]
  _BYTE v38[32]; // [rsp+68h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v34 = a4;
  v6 = (char *)this + 16;
  Microsoft::WRL::ComPtr<CtacJsonData>::operator=((char *)this + 16, a2);
  v32 = 0;
  v7 = (__int64 *)Windows::Internal::StringReference::StringReference((HSTRING *)&lpsz, L"Windows.Data.Json.JsonValue");
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
         *v7,
         (__int64)&v32);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    return (unsigned int)v9;
  }
  for ( i = 0; i < 2; ++i )
  {
    lpsz = 0;
    *(_QWORD *)cchLength = 0;
    v37 = 0;
    v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &lpsz,
            (&AttributeFetcher::s_aKnownAttributes)[i],
            -1);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
        (const char *)(unsigned int)v11,
        (int)string);
      goto LABEL_14;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
    CharLowerBuffW(lpsz, cchLength[0]);
    v33 = AttributeFetcher::ParseNamespace(lpsz, 0);
    string = 0;
    v12 = *(_QWORD *)(*(_QWORD *)v6 + 120LL);
    v13 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v12 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v38, &v33);
    if ( v13(v12, *(_QWORD *)(v14 + 24), &string) < 0 )
    {
      v31 = 0;
      v15 = v32;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 80LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
      v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              v38,
              &(&AttributeFetcher::s_aKnownAttributes)[i]);
      v18 = v16(v15, *(_QWORD *)(v17 + 24), &v31);
      v9 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v18,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_14;
      }
      v19 = *(_QWORD *)(*(_QWORD *)v6 + 120LL);
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v19 + 56LL);
      v21 = v31;
      v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v38, &v33);
      v23 = v20(v19, *(_QWORD *)(v22 + 24), v21);
      v9 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v23,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
        WindowsDeleteString(string);
        string = 0;
LABEL_14:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
        goto LABEL_15;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    }
    WindowsDeleteString(string);
    string = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  v33 = *(const unsigned __int16 **)v6;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 24);
  v9 = Microsoft::WRL::Details::MakeAndInitialize<ProviderManager,ProviderManager,CtacJsonData *>(
         (char *)this + 24,
         &v33);
  if ( v9 < 0 )
  {
    v25 = 130;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
    return (unsigned int)v9;
  }
  v26 = (char *)this + 32;
  if ( a3 )
  {
    v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v26, a3, -1);
    if ( v9 < 0 )
    {
      v25 = 135;
      goto LABEL_19;
    }
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v26);
    *((_QWORD *)this + 5) = -1;
    *((_QWORD *)this + 6) = -1;
    CallingProcessName = AttributeFetcher::GetCallingProcessName((unsigned __int16 **)this + 4);
    if ( CallingProcessName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
        (const char *)(unsigned int)CallingProcessName,
        (int)string);
  }
  v28 = (char *)this + 56;
  if ( v34 )
  {
    v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v28, v34, -1);
    if ( v9 < 0 )
    {
      v25 = 148;
      goto LABEL_19;
    }
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v28);
    *((_QWORD *)this + 8) = -1;
    *((_QWORD *)this + 9) = -1;
    CallingProcessVer = AttributeFetcher::GetCallingProcessVer((unsigned __int16 **)this + 7);
    if ( CallingProcessVer < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
        (const char *)(unsigned int)CallingProcessVer,
        (int)string);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ffe8  push    rbp
0x18003ffea  push    rbx
0x18003ffeb  push    rsi
0x18003ffec  push    rdi
0x18003ffed  push    r12
0x18003ffef  push    r13
0x18003fff1  push    r14
0x18003fff3  push    r15
0x18003fff5  lea     rbp, [rsp-1Fh]
0x18003fffa  sub     rsp, 98h
0x180040001  mov     rax, cs:__security_cookie
0x180040008  xor     rax, rsp
0x18004000b  mov     [rbp+57h+var_48], rax
0x18004000f  mov     [rbp+57h+var_90], r9
0x180040013  mov     r13, r8
0x180040016  mov     r15, rcx
0x180040019  lea     r12, [rcx+10h]
0x18004001d  mov     rcx, r12
0x180040020  call    ??4?$ComPtr@VCtacJsonData@@@WRL@Microsoft@@QEAAAEAV012@PEAVCtacJsonData@@@Z; Microsoft::WRL::ComPtr<CtacJsonData>::operator=(CtacJsonData *)
0x180040025  xor     edi, edi
0x180040027  mov     [rbp+57h+var_A0], rdi
0x18004002b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180040032  lea     rcx, [rbp+57h+lpsz]; string
0x180040036  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x18004003b  lea     rdx, [rbp+57h+var_A0]
0x18004003f  mov     rcx, [rax]
0x180040042  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x180040047  mov     ebx, eax
0x180040049  test    eax, eax
0x18004004b  jns     short loc_180040068
0x18004004d  mov     rcx, [rbp+5Fh]; this
0x180040051  mov     r9d, eax; char *
0x180040054  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18004005b  lea     edx, [rdi+5Fh]; void *
0x18004005e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040063  jmp     loc_18004024D
0x180040068  mov     r14, rdi
0x18004006b  cmp     r14, 2
0x18004006f  jnb     loc_18004025D
0x180040075  mov     [rbp+57h+lpsz], rdi
0x180040079  mov     qword ptr [rbp+57h+cchLength], rdi
0x18004007d  mov     [rbp+57h+var_78], rdi
0x180040081  lea     rax, ?s_aKnownAttributes@AttributeFetcher@@0QBQEBGB; ushort const * const near * const AttributeFetcher::s_aKnownAttributes
0x180040088  lea     rsi, [rax+r14*8]
0x18004008c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040090  mov     rdx, [rsi]
0x180040093  lea     rcx, [rbp+57h+lpsz]
0x180040097  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004009c  mov     ebx, eax
0x18004009e  test    eax, eax
0x1800400a0  js      loc_18004022A
0x1800400a6  lea     rcx, [rbp+57h+lpsz]
0x1800400aa  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800400af  mov     edx, [rbp+57h+cchLength]; cchLength
0x1800400b2  mov     rcx, [rbp+57h+lpsz]; lpsz
0x1800400b6  call    cs:__imp_CharLowerBuffW
0x1800400bc  xor     edx, edx; unsigned __int16 *
0x1800400be  mov     rcx, [rbp+57h+lpsz]; unsigned __int16 *
0x1800400c2  call    ?ParseNamespace@AttributeFetcher@@CAPEBGPEBGPEAG@Z; AttributeFetcher::ParseNamespace(ushort const *,ushort *)
0x1800400c7  mov     [rbp+57h+var_98], rax
0x1800400cb  mov     [rbp+57h+string], rdi
0x1800400cf  mov     rax, [r12]
0x1800400d3  mov     rdi, [rax+78h]
0x1800400d7  mov     rax, [rdi]
0x1800400da  mov     rbx, [rax+50h]
0x1800400de  xor     ecx, ecx; string
0x1800400e0  call    cs:__imp_WindowsDeleteString
0x1800400e6  mov     [rbp+57h+string], 0
0x1800400ee  lea     rdx, [rbp+57h+var_98]
0x1800400f2  lea     rcx, [rbp+57h+var_68]
0x1800400f6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800400fb  nop
0x1800400fc  lea     r8, [rbp+57h+string]
0x180040100  mov     rdx, [rax+18h]
0x180040104  mov     rcx, rdi
0x180040107  mov     rax, rbx
0x18004010a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004010f  nop
0x180040110  xor     edi, edi
0x180040112  test    eax, eax
0x180040114  jns     loc_1800401A1
0x18004011a  mov     [rbp+57h+var_A8], rdi
0x18004011e  mov     rdi, [rbp+57h+var_A0]
0x180040122  mov     rax, [rdi]
0x180040125  mov     rbx, [rax+50h]
0x180040129  lea     rcx, [rbp+57h+var_A8]
0x18004012d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180040132  mov     rdx, rsi
0x180040135  lea     rcx, [rbp+57h+var_68]
0x180040139  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004013e  nop
0x18004013f  lea     r8, [rbp+57h+var_A8]
0x180040143  mov     rdx, [rax+18h]
0x180040147  mov     rcx, rdi
0x18004014a  mov     rax, rbx
0x18004014d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040152  mov     ebx, eax
0x180040154  test    eax, eax
0x180040156  js      loc_1800401F3
0x18004015c  mov     rax, [r12]
0x180040160  mov     rsi, [rax+78h]
0x180040164  mov     rax, [rsi]
0x180040167  mov     rdi, [rax+38h]
0x18004016b  mov     rbx, [rbp+57h+var_A8]
0x18004016f  lea     rdx, [rbp+57h+var_98]
0x180040173  lea     rcx, [rbp+57h+var_68]
0x180040177  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004017c  nop
0x18004017d  mov     r8, rbx
0x180040180  mov     rdx, [rax+18h]
0x180040184  mov     rcx, rsi
0x180040187  mov     rax, rdi
0x18004018a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004018f  mov     ebx, eax
0x180040191  xor     edi, edi
0x180040193  test    eax, eax
0x180040195  js      short loc_1800401C0
0x180040197  lea     rcx, [rbp+57h+var_A8]
0x18004019b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800401a0  nop
0x1800401a1  mov     rcx, [rbp+57h+string]; string
0x1800401a5  call    cs:__imp_WindowsDeleteString
0x1800401ab  mov     [rbp+57h+string], rdi
0x1800401af  lea     rcx, [rbp+57h+lpsz]
0x1800401b3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800401b8  inc     r14
0x1800401bb  jmp     loc_18004006B
0x1800401c0  mov     rcx, [rbp+5Fh]; this
0x1800401c4  mov     r9d, eax; char *
0x1800401c7  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x1800401ce  mov     edx, 7Ah ; 'z'; void *
0x1800401d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800401d8  nop
0x1800401d9  lea     rcx, [rbp+57h+var_A8]
0x1800401dd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800401e2  nop
0x1800401e3  mov     rcx, [rbp+57h+string]; string
0x1800401e7  call    cs:__imp_WindowsDeleteString
0x1800401ed  mov     [rbp+57h+string], rdi
0x1800401f1  jmp     short loc_180040243
0x1800401f3  mov     rcx, [rbp+5Fh]; this
0x1800401f7  mov     r9d, eax; char *
0x1800401fa  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x180040201  mov     edx, 76h ; 'v'; void *
0x180040206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004020b  nop
0x18004020c  lea     rcx, [rbp+57h+var_A8]
0x180040210  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180040215  nop
0x180040216  mov     rcx, [rbp+57h+string]; string
0x18004021a  call    cs:__imp_WindowsDeleteString
0x180040220  mov     [rbp+57h+string], 0
0x180040228  jmp     short loc_180040243
0x18004022a  mov     rcx, [rbp+5Fh]; this
0x18004022e  mov     r9d, eax; char *
0x180040231  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x180040238  mov     edx, 69h ; 'i'; void *
0x18004023d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040242  nop
0x180040243  lea     rcx, [rbp+57h+lpsz]
0x180040247  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004024c  nop
0x18004024d  lea     rcx, [rbp+57h+var_A0]
0x180040251  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180040256  mov     eax, ebx
0x180040258  jmp     loc_18004035F
0x18004025d  lea     rcx, [rbp+57h+var_A0]
0x180040261  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180040266  mov     rax, [r12]
0x18004026a  mov     [rbp+57h+var_98], rax
0x18004026e  lea     rcx, [r15+18h]
0x180040272  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180040277  lea     rdx, [rbp+57h+var_98]
0x18004027b  lea     rcx, [r15+18h]
0x18004027f  call    ??$MakeAndInitialize@VProviderManager@@V1@PEAVCtacJsonData@@@Details@WRL@Microsoft@@YAJPEAPEAVProviderManager@@$$QEAPEAVCtacJsonData@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ProviderManager,ProviderManager,CtacJsonData *>(ProviderManager * *,CtacJsonData * &&)
0x180040284  mov     ebx, eax
0x180040286  test    eax, eax
0x180040288  jns     short loc_1800402A4
0x18004028a  mov     edx, 82h; void *
0x18004028f  mov     rcx, [rbp+5Fh]; this
0x180040293  mov     r9d, ebx; char *
0x180040296  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18004029d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800402a2  jmp     short loc_180040256
0x1800402a4  lea     rbx, [r15+20h]
0x1800402a8  mov     rcx, rbx
0x1800402ab  test    r13, r13
0x1800402ae  jz      short loc_1800402CC
0x1800402b0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800402b4  mov     r8, rsi
0x1800402b7  mov     rdx, r13
0x1800402ba  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800402bf  mov     ebx, eax
0x1800402c1  test    eax, eax
0x1800402c3  jns     short loc_180040301
0x1800402c5  mov     edx, 87h
0x1800402ca  jmp     short loc_18004028F
0x1800402cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800402d1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800402d5  mov     [rbx+8], rsi
0x1800402d9  mov     [rbx+10h], rsi
0x1800402dd  mov     rcx, rbx; unsigned __int16 **
0x1800402e0  call    ?GetCallingProcessName@AttributeFetcher@@CAJPEAPEAG@Z; AttributeFetcher::GetCallingProcessName(ushort * *)
0x1800402e5  test    eax, eax
0x1800402e7  jns     short loc_180040301
0x1800402e9  mov     rcx, [rbp+5Fh]; this
0x1800402ed  mov     r9d, eax; char *
0x1800402f0  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x1800402f7  mov     edx, 8Eh; void *
0x1800402fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040301  lea     rbx, [r15+38h]
0x180040305  mov     rdi, [rbp+57h+var_90]
0x180040309  mov     rcx, rbx
0x18004030c  test    rdi, rdi
0x18004030f  jz      short loc_18004032C
0x180040311  mov     r8, rsi
0x180040314  mov     rdx, rdi
0x180040317  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004031c  mov     ebx, eax
0x18004031e  test    eax, eax
0x180040320  jns     short loc_18004035D
0x180040322  mov     edx, 94h
0x180040327  jmp     loc_18004028F
0x18004032c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180040331  mov     [rbx+8], rsi
0x180040335  mov     [rbx+10h], rsi
0x180040339  mov     rcx, rbx; unsigned __int16 **
0x18004033c  call    ?GetCallingProcessVer@AttributeFetcher@@CAJPEAPEAG@Z; AttributeFetcher::GetCallingProcessVer(ushort * *)
0x180040341  test    eax, eax
0x180040343  jns     short loc_18004035D
0x180040345  mov     rcx, [rbp+5Fh]; this
0x180040349  mov     r9d, eax; char *
0x18004034c  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x180040353  mov     edx, 9Bh; void *
0x180040358  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004035d  xor     eax, eax
0x18004035f  mov     rcx, [rbp+57h+var_48]
0x180040363  xor     rcx, rsp; StackCookie
0x180040366  call    __security_check_cookie
0x18004036b  add     rsp, 98h
0x180040372  pop     r15
0x180040374  pop     r14
0x180040376  pop     r13
0x180040378  pop     r12
0x18004037a  pop     rdi
0x18004037b  pop     rsi
0x18004037c  pop     rbx
0x18004037d  pop     rbp
0x18004037e  retn
```

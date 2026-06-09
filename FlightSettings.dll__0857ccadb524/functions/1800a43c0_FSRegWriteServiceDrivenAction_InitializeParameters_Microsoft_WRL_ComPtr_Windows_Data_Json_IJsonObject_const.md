# FSRegWriteServiceDrivenAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800a43c0`
- end: `0x1800a4839`
- name: `?InitializeParameters@FSRegWriteServiceDrivenAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1145`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001d244`
- `0x180020c2c`
- `0x18009bc00`
- `0x1800a40fc`
- `0x1800a4148`
- `0x1800a4194`
- `0x1800a43c0`
- `0x1800a596c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4434`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4736`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4434`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4736`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a47bd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a47bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a474a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a474a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a479f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a479f`

## string_xrefs

- `0x1800a45d5`: `HKEY_CURRENT_CONFIG`
- `0x1800a4540`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a4591`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a4770`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a47f8`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a44ee`: `DELETE_KEY`
- `0x1800a44c5`: `CREATE_KEY`
- `0x1800a4471`: `WRITE`
- `0x1800a4640`: `FullPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FSRegWriteServiceDrivenAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // r14
  __int64 (__fastcall *v5)(__int64, HSTRING, __int64 *); // r15
  unsigned __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  HSTRING *v10; // rax
  const unsigned __int16 *v11; // rdx
  HSTRING *v12; // rax
  HSTRING *v13; // rax
  HSTRING *v14; // rax
  int inited; // eax
  int v16; // r14d
  unsigned __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, HSTRING, HSTRING *); // r14
  unsigned __int64 v20; // rcx
  int v21; // eax
  const WCHAR *StringRawBuffer; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  UINT32 length; // [rsp+30h] [rbp-40h] BYREF
  __int64 v26; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v27; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v26 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*a2 + 80LL);
  length = 0;
  v6 = -1;
  do
    ++v6;
  while ( FSRegWriteServiceDrivenAction::s_operationTag[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSRegWriteServiceDrivenAction::s_operationTag, length, &hstringHeader, &string);
  v7 = v5(v4, string, &v26);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 27;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
    goto LABEL_46;
  }
  v10 = Windows::Internal::StringReference::StringReference(&string, L"WRITE");
  if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                       (Windows::Internal::String *)&v26,
                       (const struct Windows::Internal::String *)v10) )
  {
    v12 = Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[7])v11);
    if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                         (Windows::Internal::String *)&v26,
                         (const struct Windows::Internal::String *)v12) )
    {
      v13 = Windows::Internal::StringReference::StringReference(&string, L"CREATE_KEY");
      if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                           (Windows::Internal::String *)&v26,
                           (const struct Windows::Internal::String *)v13) )
      {
        v14 = Windows::Internal::StringReference::StringReference(&string, L"DELETE_KEY");
        if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                             (Windows::Internal::String *)&v26,
                             (const struct Windows::Internal::String *)v14) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2E,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
            (const char *)0x800BFA0CLL,
            bIgnoreCase);
          Windows::Internal::String::~String((Windows::Internal::String *)&v26);
          return 2148268556LL;
        }
        *(_DWORD *)(a1 + 280) = 3;
      }
      else
      {
        *(_DWORD *)(a1 + 280) = 2;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 280) = 1;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 280) = 0;
  }
  inited = FSServiceDrivenAction::InitStringFromJson(a2, L"HKey", a1 + 88);
  v16 = inited;
  if ( inited < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
      (const char *)(unsigned int)inited,
      bIgnoreCase);
    v8 = v16;
LABEL_46:
    Windows::Internal::String::~String((Windows::Internal::String *)&v26);
    return v8;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a1 + 88,
                       L"HKEY_CURRENT_USER",
                       -1) == 2 )
  {
    v7 = FSServiceDrivenAction::InitStringFromJson(a2, L"User", a1 + 208);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 54;
      goto LABEL_20;
    }
    v17 = -2147483647;
    goto LABEL_30;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a1 + 88,
                       L"HKEY_CLASSES_ROOT",
                       -1) == 2 )
  {
    v17 = 0xFFFFFFFF80000000uLL;
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      a1 + 272,
      v17);
    goto LABEL_31;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a1 + 88,
                       L"HKEY_CURRENT_CONFIG",
                       -1) == 2 )
  {
    v17 = -2147483643;
    goto LABEL_30;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a1 + 88,
                       L"HKEY_LOCAL_MACHINE",
                       -1) == 2 )
  {
    v17 = -2147483646;
    goto LABEL_30;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a1 + 88,
                       L"HKEY_USERS",
                       -1) == 2 )
  {
    v17 = -2147483645;
    goto LABEL_30;
  }
LABEL_31:
  v7 = FSServiceDrivenAction::InitStringFromJson(a2, L"FullPath", a1 + 112);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 75;
    goto LABEL_20;
  }
  FSServiceDrivenAction::InitStringFromJson(a2, L"RedirectionID", a1 + 232);
  if ( *(_DWORD *)(a1 + 280) <= 1u )
  {
    v7 = FSServiceDrivenAction::InitStringFromJson(a2, L"ValueName", a1 + 136);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 84;
      goto LABEL_20;
    }
    v7 = FSServiceDrivenAction::InitStringFromJson(a2, L"Value", a1 + 160);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 87;
      goto LABEL_20;
    }
    v7 = FSServiceDrivenAction::InitStringFromJson(a2, L"RegValueType", a1 + 184);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 90;
      goto LABEL_20;
    }
    v27 = 0;
    v18 = *a2;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v18 + 80LL);
    length = 0;
    v20 = -1;
    do
      ++v20;
    while ( FSJsonParsingRegistryStrings::s_hide[v20] );
    if ( (int)ULongLongToUInt(v20, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSJsonParsingRegistryStrings::s_hide, length, &hstringHeader, &string);
    v21 = v19(v18, string, &v27);
    v8 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
      Windows::Internal::String::~String((Windows::Internal::String *)&v27);
      goto LABEL_46;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
    *(_BYTE *)(a1 + 256) = CompareStringOrdinal(StringRawBuffer, -1, L"TRUE", -1, 1) == 2;
    Windows::Internal::String::~String((Windows::Internal::String *)&v27);
  }
  *(_DWORD *)(a1 + 284) = 0;
  Windows::Internal::String::~String((Windows::Internal::String *)&v26);
  return 0;
}

```

## disassembly

```asm
0x1800a43c0  mov     [rsp-38h+arg_10], rbx
0x1800a43c5  push    rbp
0x1800a43c6  push    rsi
0x1800a43c7  push    rdi
0x1800a43c8  push    r12
0x1800a43ca  push    r13
0x1800a43cc  push    r14
0x1800a43ce  push    r15
0x1800a43d0  mov     rbp, rsp
0x1800a43d3  sub     rsp, 70h
0x1800a43d7  mov     rax, cs:__security_cookie
0x1800a43de  xor     rax, rsp
0x1800a43e1  mov     [rbp+var_8], rax
0x1800a43e5  mov     rsi, rdx
0x1800a43e8  mov     rbx, rcx
0x1800a43eb  xor     r12d, r12d
0x1800a43ee  mov     [rbp+var_38], r12
0x1800a43f2  mov     r14, [rdx]
0x1800a43f5  mov     rax, [r14]
0x1800a43f8  mov     r15, [rax+50h]
0x1800a43fc  mov     rdi, cs:?s_operationTag@FSRegWriteServiceDrivenAction@@0QEBGEB; ushort const * const FSRegWriteServiceDrivenAction::s_operationTag
0x1800a4403  mov     [rbp+length], r12d
0x1800a4407  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800a440b  mov     rcx, r13
0x1800a440e  inc     rcx; unsigned __int64
0x1800a4411  cmp     [rdi+rcx*2], r12w
0x1800a4416  jnz     short loc_1800A440E
0x1800a4418  lea     rdx, [rbp+length]; unsigned int *
0x1800a441c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a4421  test    eax, eax
0x1800a4423  jns     short loc_1800A443A
0x1800a4425  xor     r9d, r9d; lpArguments
0x1800a4428  xor     r8d, r8d; nNumberOfArguments
0x1800a442b  lea     edx, [r9+1]; dwExceptionFlags
0x1800a442f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a4434  call    cs:__imp_RaiseException
0x1800a443a  lea     r9, [rbp+string]; string
0x1800a443e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800a4442  mov     edx, [rbp+length]; length
0x1800a4445  mov     rcx, rdi; sourceString
0x1800a4448  call    cs:__imp_WindowsCreateStringReference
0x1800a444e  lea     r8, [rbp+var_38]
0x1800a4452  mov     rdx, [rbp+string]
0x1800a4456  mov     rcx, r14
0x1800a4459  mov     rax, r15
0x1800a445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4461  mov     edi, eax
0x1800a4463  test    eax, eax
0x1800a4465  jns     short loc_1800A4471
0x1800a4467  mov     edx, 1Bh
0x1800a446c  jmp     loc_1800A4591
0x1800a4471  lea     rdx, aWrite; "WRITE"
0x1800a4478  lea     rcx, [rbp+string]; string
0x1800a447c  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x1800a4481  mov     rdx, rax; struct Windows::Internal::String *
0x1800a4484  lea     rcx, [rbp+var_38]; this
0x1800a4488  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800a448d  mov     r15d, 2
0x1800a4493  test    eax, eax
0x1800a4495  jnz     short loc_1800A44A0
0x1800a4497  mov     [rbx+118h], r12d
0x1800a449e  jmp     short loc_1800A451C
0x1800a44a0  lea     rcx, [rbp+string]; string
0x1800a44a4  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x1800a44a9  mov     rdx, rax; struct Windows::Internal::String *
0x1800a44ac  lea     rcx, [rbp+var_38]; this
0x1800a44b0  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800a44b5  test    eax, eax
0x1800a44b7  jnz     short loc_1800A44C5
0x1800a44b9  mov     dword ptr [rbx+118h], 1
0x1800a44c3  jmp     short loc_1800A451C
0x1800a44c5  lea     rdx, aCreateKey; "CREATE_KEY"
0x1800a44cc  lea     rcx, [rbp+string]; string
0x1800a44d0  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x1800a44d5  mov     rdx, rax; struct Windows::Internal::String *
0x1800a44d8  lea     rcx, [rbp+var_38]; this
0x1800a44dc  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800a44e1  test    eax, eax
0x1800a44e3  jnz     short loc_1800A44EE
0x1800a44e5  mov     [rbx+118h], r15d
0x1800a44ec  jmp     short loc_1800A451C
0x1800a44ee  lea     rdx, aDeleteKey; "DELETE_KEY"
0x1800a44f5  lea     rcx, [rbp+string]; string
0x1800a44f9  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x1800a44fe  mov     rdx, rax; struct Windows::Internal::String *
0x1800a4501  lea     rcx, [rbp+var_38]; this
0x1800a4505  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800a450a  test    eax, eax
0x1800a450c  jnz     loc_1800A47EC
0x1800a4512  mov     dword ptr [rbx+118h], 3
0x1800a451c  lea     rdi, [rbx+58h]
0x1800a4520  mov     r8, rdi
0x1800a4523  lea     rdx, aHkey; "HKey"
0x1800a452a  mov     rcx, rsi
0x1800a452d  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a4532  mov     r14d, eax
0x1800a4535  test    eax, eax
0x1800a4537  jns     short loc_1800A4559
0x1800a4539  mov     rcx, [rbp+38h]; this
0x1800a453d  mov     r9d, eax; char *
0x1800a4540  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a4547  mov     edx, 32h ; '2'; void *
0x1800a454c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4551  mov     edi, r14d
0x1800a4554  jmp     loc_1800A478C
0x1800a4559  mov     r8, r13
0x1800a455c  lea     rdx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800a4563  mov     rcx, rdi
0x1800a4566  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a456b  cmp     eax, r15d
0x1800a456e  jnz     short loc_1800A45B2
0x1800a4570  lea     r8, [rbx+0D0h]
0x1800a4577  lea     rdx, aUser; "User"
0x1800a457e  mov     rcx, rsi
0x1800a4581  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a4586  mov     edi, eax
0x1800a4588  test    eax, eax
0x1800a458a  jns     short loc_1800A45A9
0x1800a458c  mov     edx, 36h ; '6'; void *
0x1800a4591  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a4598  mov     r9d, eax; char *
0x1800a459b  mov     rcx, [rbp+38h]; this
0x1800a459f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a45a4  jmp     loc_1800A478C
0x1800a45a9  mov     rdx, 0FFFFFFFF80000001h
0x1800a45b0  jmp     short loc_1800A4630
0x1800a45b2  mov     r8, r13
0x1800a45b5  lea     rdx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x1800a45bc  mov     rcx, rdi
0x1800a45bf  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a45c4  cmp     eax, r15d
0x1800a45c7  jnz     short loc_1800A45D2
0x1800a45c9  mov     rdx, 0FFFFFFFF80000000h
0x1800a45d0  jmp     short loc_1800A4630
0x1800a45d2  mov     r8, r13
0x1800a45d5  lea     rdx, aHkeyCurrentCon; "HKEY_CURRENT_CONFIG"
0x1800a45dc  mov     rcx, rdi
0x1800a45df  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a45e4  cmp     eax, r15d
0x1800a45e7  jnz     short loc_1800A45F2
0x1800a45e9  mov     rdx, 0FFFFFFFF80000005h
0x1800a45f0  jmp     short loc_1800A4630
0x1800a45f2  mov     r8, r13
0x1800a45f5  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x1800a45fc  mov     rcx, rdi
0x1800a45ff  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a4604  cmp     eax, r15d
0x1800a4607  jnz     short loc_1800A4612
0x1800a4609  mov     rdx, 0FFFFFFFF80000002h
0x1800a4610  jmp     short loc_1800A4630
0x1800a4612  mov     r8, r13
0x1800a4615  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x1800a461c  mov     rcx, rdi
0x1800a461f  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a4624  cmp     eax, r15d
0x1800a4627  jnz     short loc_1800A463C
0x1800a4629  mov     rdx, 0FFFFFFFF80000003h
0x1800a4630  lea     rcx, [rbx+110h]
0x1800a4637  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a463c  lea     r8, [rbx+70h]
0x1800a4640  lea     rdx, aFullpath; "FullPath"
0x1800a4647  mov     rcx, rsi
0x1800a464a  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a464f  mov     edi, eax
0x1800a4651  test    eax, eax
0x1800a4653  jns     short loc_1800A465F
0x1800a4655  mov     edx, 4Bh ; 'K'
0x1800a465a  jmp     loc_1800A4591
0x1800a465f  lea     r8, [rbx+0E8h]
0x1800a4666  lea     rdx, aRedirectionid; "RedirectionID"
0x1800a466d  mov     rcx, rsi
0x1800a4670  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a4675  cmp     dword ptr [rbx+118h], 1
0x1800a467c  ja      loc_1800A47D8
0x1800a4682  lea     r8, [rbx+88h]
0x1800a4689  lea     rdx, aValuename; "ValueName"
0x1800a4690  mov     rcx, rsi
0x1800a4693  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a4698  mov     edi, eax
0x1800a469a  test    eax, eax
0x1800a469c  jns     short loc_1800A46A8
0x1800a469e  mov     edx, 54h ; 'T'
0x1800a46a3  jmp     loc_1800A4591
0x1800a46a8  lea     r8, [rbx+0A0h]
0x1800a46af  lea     rdx, aValue_1; "Value"
0x1800a46b6  mov     rcx, rsi
0x1800a46b9  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a46be  mov     edi, eax
0x1800a46c0  test    eax, eax
0x1800a46c2  jns     short loc_1800A46CE
0x1800a46c4  mov     edx, 57h ; 'W'
0x1800a46c9  jmp     loc_1800A4591
0x1800a46ce  lea     r8, [rbx+0B8h]
0x1800a46d5  lea     rdx, aRegvaluetype; "RegValueType"
0x1800a46dc  mov     rcx, rsi
0x1800a46df  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a46e4  mov     edi, eax
0x1800a46e6  test    eax, eax
0x1800a46e8  jns     short loc_1800A46F4
0x1800a46ea  mov     edx, 5Ah ; 'Z'
0x1800a46ef  jmp     loc_1800A4591
0x1800a46f4  mov     [rbp+var_30], r12
0x1800a46f8  mov     rsi, [rsi]
0x1800a46fb  mov     rax, [rsi]
0x1800a46fe  mov     r14, [rax+50h]
0x1800a4702  mov     rdi, cs:?s_hide@FSJsonParsingRegistryStrings@@2QEBGEB; ushort const * const FSJsonParsingRegistryStrings::s_hide
0x1800a4709  mov     [rbp+length], r12d
0x1800a470d  mov     rcx, r13
0x1800a4710  inc     rcx; unsigned __int64
0x1800a4713  cmp     [rdi+rcx*2], r12w
0x1800a4718  jnz     short loc_1800A4710
0x1800a471a  lea     rdx, [rbp+length]; unsigned int *
0x1800a471e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a4723  test    eax, eax
0x1800a4725  jns     short loc_1800A473C
0x1800a4727  xor     r9d, r9d; lpArguments
0x1800a472a  xor     r8d, r8d; nNumberOfArguments
0x1800a472d  lea     edx, [r9+1]; dwExceptionFlags
0x1800a4731  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a4736  call    cs:__imp_RaiseException
0x1800a473c  lea     r9, [rbp+string]; string
0x1800a4740  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800a4744  mov     edx, [rbp+length]; length
0x1800a4747  mov     rcx, rdi; sourceString
0x1800a474a  call    cs:__imp_WindowsCreateStringReference
0x1800a4750  lea     r8, [rbp+var_30]
0x1800a4754  mov     rdx, [rbp+string]
0x1800a4758  mov     rcx, rsi
0x1800a475b  mov     rax, r14
0x1800a475e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4763  mov     edi, eax
0x1800a4765  test    eax, eax
0x1800a4767  jns     short loc_1800A4799
0x1800a4769  mov     rcx, [rbp+38h]; this
0x1800a476d  mov     r9d, eax; char *
0x1800a4770  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a4777  mov     edx, 5Eh ; '^'; void *
0x1800a477c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4781  nop
0x1800a4782  lea     rcx, [rbp+var_30]; this
0x1800a4786  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a478b  nop
0x1800a478c  lea     rcx, [rbp+var_38]; this
0x1800a4790  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a4795  mov     eax, edi
0x1800a4797  jmp     short loc_1800A4815
0x1800a4799  xor     edx, edx; length
0x1800a479b  mov     rcx, [rbp+var_30]; string
0x1800a479f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a47a5  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x1800a47ad  mov     r9d, r13d; cchCount2
0x1800a47b0  lea     r8, aTrue_0; "TRUE"
0x1800a47b7  mov     edx, r13d; cchCount1
0x1800a47ba  mov     rcx, rax; lpString1
0x1800a47bd  call    cs:__imp_CompareStringOrdinal
0x1800a47c3  cmp     eax, r15d
0x1800a47c6  setz    al
0x1800a47c9  mov     [rbx+100h], al
0x1800a47cf  lea     rcx, [rbp+var_30]; this
0x1800a47d3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a47d8  mov     [rbx+11Ch], r12d
0x1800a47df  lea     rcx, [rbp+var_38]; this
0x1800a47e3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a47e8  xor     eax, eax
0x1800a47ea  jmp     short loc_1800A4815
0x1800a47ec  mov     rcx, [rbp+38h]; this
0x1800a47f0  mov     ebx, 800BFA0Ch
0x1800a47f5  mov     r9d, ebx; char *
0x1800a47f8  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a47ff  mov     edx, 2Eh ; '.'; void *
0x1800a4804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4809  nop
0x1800a480a  lea     rcx, [rbp+var_38]; this
0x1800a480e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a4813  mov     eax, ebx
0x1800a4815  mov     rcx, [rbp+var_8]
0x1800a4819  xor     rcx, rsp; StackCookie
0x1800a481c  call    __security_check_cookie
0x1800a4821  mov     rbx, [rsp+70h+arg_10]
0x1800a4829  add     rsp, 70h
0x1800a482d  pop     r15
0x1800a482f  pop     r14
0x1800a4831  pop     r13
0x1800a4833  pop     r12
0x1800a4835  pop     rdi
0x1800a4836  pop     rsi
0x1800a4837  pop     rbp
0x1800a4838  retn
```

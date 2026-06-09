# StoreApplication::GetStoreAppLanguageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)

- ea: `0x1800db168`
- end: `0x1800db65e`
- name: `?GetStoreAppLanguageSr@StoreApplication@@SAKAEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `1270`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dd87c`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000edf0`
- `0x18001c5f0`
- `0x1800231f0`
- `0x1800252b0`
- `0x1800c97f0`
- `0x1800c9810`
- `0x1800d8a9c`
- `0x1800db168`
- `0x1800dbff4`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800db1fe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800db1fe`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800db59d`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800db59d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db5ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db5ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800db1e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800db1e6`

## string_xrefs

- `0x1800db1df`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x1800db225`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db273`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db2e0`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db333`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db3a3`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db3c7`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db403`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db47d`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db4a1`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db4ec`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db53b`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 StoreApplication::GetStoreAppLanguageSr()
{
  int v0; // eax
  __int64 (__fastcall ***v1)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v2)(_QWORD, GUID *, __int64 *); // rdi
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64); // rbx
  _QWORD *v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  const char *v15; // r9
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  int v19; // eax
  const char *v20; // r9
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, __int64 *); // rdi
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v28; // r8
  const WCHAR *p_lpName; // rcx
  __int64 v30; // rcx
  signed int LastError; // eax
  unsigned int v33; // edx
  const char *v34; // rcx
  int v35; // [rsp+20h] [rbp-E8h]
  HSTRING v36; // [rsp+30h] [rbp-D8h] BYREF
  LCID v37; // [rsp+38h] [rbp-D0h]
  __int64 v38; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v39; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-98h] BYREF
  _QWORD *v45; // [rsp+78h] [rbp-90h] BYREF
  void **v46; // [rsp+80h] [rbp-88h] BYREF
  const char *v47; // [rsp+88h] [rbp-80h] BYREF
  HSTRING string; // [rsp+98h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-68h] BYREF
  __int128 lpName; // [rsp+B8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-40h]
  _QWORD v52[4]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v37 = 1033;
  lpName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpName) = 0;
  try
  {
    StoreApplication::GetStoreAppManifestXmlSr();
    v43 = 0;
    v42 = 0;
    if ( WindowsCreateStringReference(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v0 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(
           string,
           &v43);
    if ( v0 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x295,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v0,
        v35);
    v1 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
    v2 = **v43;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    v3 = v2(v1, &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637, &v42);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v3,
        v35);
    v4 = v42;
    v5 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 48LL);
    v6 = v52;
    if ( v52[3] > 7u )
      v6 = (_QWORD *)v52[0];
    v45 = v6;
    v7 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &v45) + 24);
    v8 = v5(v4, v7);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x298,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v8,
        v35);
    v41 = 0;
    v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
    v10 = **v43;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v11 = v10(v9, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v41);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x29B,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v11,
        v35);
    v44 = 0;
    v12 = v41;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL);
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&string,
      L"/*[local-name()='Package']/*[local-name()='Resources']/*[local-name()='Resource'][1]",
      0x55u,
      0x54u);
    v14 = v13(v12, *(_QWORD *)&hstringHeader.Reserved.Reserved2[16], &v44);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x29F,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v14,
        v35);
    if ( !v44 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x2A0,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        v15);
    v40 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 128LL))(v44, &v40);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2A3,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v16,
        v35);
    v39 = 0;
    v17 = v40;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&string, L"Language", 9u, 8u);
    v19 = v18(v17, *(_QWORD *)&hstringHeader.Reserved.Reserved2[16], &v39);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2A7,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v19,
        v35);
    v21 = v39;
    if ( !v39 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x2A8,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        v20);
    v38 = 0;
    v36 = 0;
    v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v23 = v22(v21, &v38);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2AC,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v23,
        v35);
    v24 = v38;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 152LL);
    WindowsDeleteString(v36);
    v36 = 0;
    v26 = v25(v24, &v36);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2AD,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v26,
        v35);
    StringRawBuffer = WindowsGetStringRawBuffer(v36, 0);
    v28 = -1;
    do
      ++v28;
    while ( StringRawBuffer[v28] );
    std::wstring::_Assign<unsigned short>(&lpName, StringRawBuffer);
    if ( si128.m128i_i64[0] )
    {
      p_lpName = (const WCHAR *)&lpName;
      if ( si128.m128i_i64[1] > 7uLL )
        p_lpName = (const WCHAR *)lpName;
      v37 = LocaleNameToLCID(p_lpName, 0);
    }
    WindowsDeleteString(v36);
    v36 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v30 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    std::wstring::_Tidy_deallocate(v52);
    std::wstring::_Tidy_deallocate(&lpName);
  }
  catch ( std::exception v46 )
  {
    LastError = GetLastError();
    v33 = LastError;
    if ( LastError > 0 )
      v33 = (unsigned __int16)LastError | 0x80070000;
    v34 = "Unknown exception";
    if ( v47 )
      v34 = v47;
    AslLogCallPrintf(3, "StoreApplication::GetStoreAppLanguageSr", 697, "Exception: 0x%08x %s", v33, v34);
    v46 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v47);
    return v37;
  }
  catch ( ... )
  {
    AslLogCallPrintf(3, "StoreApplication::GetStoreAppLanguageSr", 702, "Exception: [0x%08x]", -2147024322);
  }
  return v37;
}

```

## disassembly

```asm
0x1800db168  mov     r11, rsp
0x1800db16b  mov     [r11+10h], rbx
0x1800db16f  mov     [r11+18h], rsi
0x1800db173  push    rdi
0x1800db174  sub     rsp, 100h
0x1800db17b  mov     rax, cs:__security_cookie
0x1800db182  xor     rax, rsp
0x1800db185  mov     [rsp+108h+var_10], rax
0x1800db18d  mov     [rsp+108h+var_D0], 409h
0x1800db195  xorps   xmm0, xmm0
0x1800db198  movups  xmmword ptr [r11-50h], xmm0
0x1800db19d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800db1a5  movdqu  xmmword ptr [r11-40h], xmm1
0x1800db1ab  xor     esi, esi
0x1800db1ad  mov     [r11-50h], si
0x1800db1b2  mov     r8b, 1
0x1800db1b5  mov     rdx, rcx
0x1800db1b8  lea     rcx, [r11-30h]
0x1800db1bc  call    ?GetStoreAppManifestXmlSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@_N@Z; StoreApplication::GetStoreAppManifestXmlSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,bool)
0x1800db1c1  nop
0x1800db1c2  mov     [rsp+108h+var_A0], rsi
0x1800db1c7  mov     [rsp+108h+var_A8], rsi
0x1800db1cc  lea     r9, [rsp+108h+string]; string
0x1800db1d4  lea     r8, [rsp+108h+hstringHeader]; hstringHeader
0x1800db1dc  lea     edx, [rsi+20h]; length
0x1800db1df  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x1800db1e6  call    cs:__imp_WindowsCreateStringReference
0x1800db1ec  test    eax, eax
0x1800db1ee  jns     short loc_1800DB204
0x1800db1f0  xor     r9d, r9d; lpArguments
0x1800db1f3  xor     r8d, r8d; nNumberOfArguments
0x1800db1f6  lea     edx, [rsi+1]; dwExceptionFlags
0x1800db1f9  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800db1fe  call    cs:__imp_RaiseException
0x1800db204  lea     rdx, [rsp+108h+var_A0]
0x1800db209  mov     rcx, [rsp+108h+string]
0x1800db211  call    ??$ActivateInstance@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>)
0x1800db216  mov     rcx, [rsp+108h]; this
0x1800db21e  test    eax, eax
0x1800db220  jns     short loc_1800DB237
0x1800db222  mov     r9d, eax; char *
0x1800db225  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db22c  mov     edx, 295h; void *
0x1800db231  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db237  mov     rbx, [rsp+108h+var_A0]
0x1800db23c  mov     rax, [rbx]
0x1800db23f  mov     rdi, [rax]
0x1800db242  lea     rcx, [rsp+108h+var_A8]
0x1800db247  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db24c  lea     r8, [rsp+108h+var_A8]
0x1800db251  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x1800db258  mov     rcx, rbx
0x1800db25b  mov     rax, rdi
0x1800db25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db263  nop
0x1800db264  mov     rcx, [rsp+108h]; this
0x1800db26c  test    eax, eax
0x1800db26e  jns     short loc_1800DB284
0x1800db270  mov     r9d, eax; char *
0x1800db273  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db27a  mov     edx, 297h; void *
0x1800db27f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db284  mov     rdi, [rsp+108h+var_A8]
0x1800db289  mov     rax, [rdi]
0x1800db28c  mov     rbx, [rax+30h]
0x1800db290  lea     rdx, [rsp+108h+var_30]
0x1800db298  cmp     [rsp+108h+var_18], 7
0x1800db2a1  cmova   rdx, [rsp+108h+var_30]
0x1800db2aa  mov     [rsp+108h+var_90], rdx
0x1800db2af  lea     rdx, [rsp+108h+var_90]
0x1800db2b4  lea     rcx, [rsp+108h+string]
0x1800db2bc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800db2c1  nop
0x1800db2c2  mov     rdx, [rax+18h]
0x1800db2c6  mov     rcx, rdi
0x1800db2c9  mov     rax, rbx
0x1800db2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db2d1  mov     rcx, [rsp+108h]; this
0x1800db2d9  test    eax, eax
0x1800db2db  jns     short loc_1800DB2F2
0x1800db2dd  mov     r9d, eax; char *
0x1800db2e0  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db2e7  mov     edx, 298h; void *
0x1800db2ec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db2f2  mov     [rsp+108h+var_B0], rsi
0x1800db2f7  mov     rbx, [rsp+108h+var_A0]
0x1800db2fc  mov     rax, [rbx]
0x1800db2ff  mov     rdi, [rax]
0x1800db302  lea     rcx, [rsp+108h+var_B0]
0x1800db307  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db30c  lea     r8, [rsp+108h+var_B0]
0x1800db311  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x1800db318  mov     rcx, rbx
0x1800db31b  mov     rax, rdi
0x1800db31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db323  nop
0x1800db324  mov     rcx, [rsp+108h]; this
0x1800db32c  test    eax, eax
0x1800db32e  jns     short loc_1800DB344
0x1800db330  mov     r9d, eax; char *
0x1800db333  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db33a  mov     edx, 29Bh; void *
0x1800db33f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db344  mov     [rsp+108h+var_98], rsi
0x1800db349  mov     rdi, [rsp+108h+var_B0]
0x1800db34e  mov     rax, [rdi]
0x1800db351  mov     rbx, [rax+30h]
0x1800db355  mov     qword ptr [rsp+108h+hstringHeader.Reserved+10h], rsi
0x1800db35d  mov     r9d, 54h ; 'T'; unsigned int
0x1800db363  lea     r8d, [r9+1]; unsigned int
0x1800db367  lea     rdx, aLocalNamePacka; "/*[local-name()='Package']/*[local-name"...
0x1800db36e  lea     rcx, [rsp+108h+string]; hstringHeader
0x1800db376  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800db37b  nop
0x1800db37c  lea     r8, [rsp+108h+var_98]
0x1800db381  mov     rdx, qword ptr [rsp+108h+hstringHeader.Reserved+10h]
0x1800db389  mov     rcx, rdi
0x1800db38c  mov     rax, rbx
0x1800db38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db394  mov     rcx, [rsp+108h]; this
0x1800db39c  test    eax, eax
0x1800db39e  jns     short loc_1800DB3B5
0x1800db3a0  mov     r9d, eax; char *
0x1800db3a3  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db3aa  mov     edx, 29Fh; void *
0x1800db3af  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db3b5  mov     rax, [rsp+108h]
0x1800db3bd  mov     rcx, [rsp+108h+var_98]
0x1800db3c2  test    rcx, rcx
0x1800db3c5  jnz     short loc_1800DB3DB
0x1800db3c7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db3ce  mov     edx, 2A0h; void *
0x1800db3d3  mov     rcx, rax; this
0x1800db3d6  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800db3db  mov     [rsp+108h+var_B8], rsi
0x1800db3e0  mov     rax, [rcx]
0x1800db3e3  lea     rdx, [rsp+108h+var_B8]
0x1800db3e8  mov     rax, [rax+80h]
0x1800db3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db3f4  mov     rcx, [rsp+108h]; this
0x1800db3fc  test    eax, eax
0x1800db3fe  jns     short loc_1800DB414
0x1800db400  mov     r9d, eax; char *
0x1800db403  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db40a  mov     edx, 2A3h; void *
0x1800db40f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db414  mov     [rsp+108h+var_C0], rsi
0x1800db419  mov     rdi, [rsp+108h+var_B8]
0x1800db41e  mov     rax, [rdi]
0x1800db421  mov     rbx, [rax+40h]
0x1800db425  lea     rcx, [rsp+108h+var_C0]
0x1800db42a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db42f  mov     qword ptr [rsp+108h+hstringHeader.Reserved+10h], rsi
0x1800db437  mov     r9d, 8; unsigned int
0x1800db43d  lea     r8d, [r9+1]; unsigned int
0x1800db441  lea     rdx, aLanguage; "Language"
0x1800db448  lea     rcx, [rsp+108h+string]; hstringHeader
0x1800db450  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800db455  nop
0x1800db456  lea     r8, [rsp+108h+var_C0]
0x1800db45b  mov     rdx, qword ptr [rsp+108h+hstringHeader.Reserved+10h]
0x1800db463  mov     rcx, rdi
0x1800db466  mov     rax, rbx
0x1800db469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db46e  mov     rcx, [rsp+108h]; this
0x1800db476  test    eax, eax
0x1800db478  jns     short loc_1800DB48F
0x1800db47a  mov     r9d, eax; char *
0x1800db47d  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db484  mov     edx, 2A7h; void *
0x1800db489  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db48f  mov     rcx, [rsp+108h]; this
0x1800db497  mov     rbx, [rsp+108h+var_C0]
0x1800db49c  test    rbx, rbx
0x1800db49f  jnz     short loc_1800DB4B2
0x1800db4a1  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db4a8  mov     edx, 2A8h; void *
0x1800db4ad  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800db4b2  mov     [rsp+108h+var_C8], rsi
0x1800db4b7  mov     [rsp+108h+var_D8], rsi
0x1800db4bc  mov     rax, [rbx]
0x1800db4bf  mov     rdi, [rax+30h]
0x1800db4c3  lea     rcx, [rsp+108h+var_C8]
0x1800db4c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db4cd  lea     rdx, [rsp+108h+var_C8]
0x1800db4d2  mov     rcx, rbx
0x1800db4d5  mov     rax, rdi
0x1800db4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db4dd  mov     rcx, [rsp+108h]; this
0x1800db4e5  test    eax, eax
0x1800db4e7  jns     short loc_1800DB4FD
0x1800db4e9  mov     r9d, eax; char *
0x1800db4ec  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db4f3  mov     edx, 2ACh; void *
0x1800db4f8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db4fd  mov     rdi, [rsp+108h+var_C8]
0x1800db502  mov     rax, [rdi]
0x1800db505  mov     rbx, [rax+98h]
0x1800db50c  mov     rcx, [rsp+108h+var_D8]; string
0x1800db511  call    cs:__imp_WindowsDeleteString
0x1800db517  mov     [rsp+108h+var_D8], rsi
0x1800db51c  lea     rdx, [rsp+108h+var_D8]
0x1800db521  mov     rcx, rdi
0x1800db524  mov     rax, rbx
0x1800db527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db52c  mov     rcx, [rsp+108h]; this
0x1800db534  test    eax, eax
0x1800db536  jns     short loc_1800DB54C
0x1800db538  mov     r9d, eax; char *
0x1800db53b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db542  mov     edx, 2ADh; void *
0x1800db547  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db54c  xor     edx, edx; length
0x1800db54e  mov     rcx, [rsp+108h+var_D8]; string
0x1800db553  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db559  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800db55d  inc     r8
0x1800db560  cmp     [rax+r8*2], si
0x1800db565  jnz     short loc_1800DB55D
0x1800db567  mov     rdx, rax
0x1800db56a  lea     rcx, [rsp+108h+lpName]
0x1800db572  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800db577  cmp     [rsp+108h+var_40], rsi
0x1800db57f  jbe     short loc_1800DB5A7
0x1800db581  lea     rcx, [rsp+108h+lpName]
0x1800db589  cmp     [rsp+108h+var_38], 7
0x1800db592  cmova   rcx, qword ptr [rsp+108h+lpName]; lpName
0x1800db59b  xor     edx, edx; dwFlags
0x1800db59d  call    cs:__imp_LocaleNameToLCID
0x1800db5a3  mov     [rsp+108h+var_D0], eax
0x1800db5a7  mov     rcx, [rsp+108h+var_D8]; string
0x1800db5ac  call    cs:__imp_WindowsDeleteString
0x1800db5b2  mov     [rsp+108h+var_D8], rsi
0x1800db5b7  lea     rcx, [rsp+108h+var_C8]
0x1800db5bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db5c1  nop
0x1800db5c2  lea     rcx, [rsp+108h+var_C0]
0x1800db5c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db5cc  nop
0x1800db5cd  mov     rcx, [rsp+108h+var_B8]
0x1800db5d2  test    rcx, rcx
0x1800db5d5  jz      short loc_1800DB5E9
0x1800db5d7  mov     [rsp+108h+var_B8], rsi
0x1800db5dc  mov     rax, [rcx]
0x1800db5df  mov     rax, [rax+10h]
0x1800db5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db5e8  nop
0x1800db5e9  lea     rcx, [rsp+108h+var_98]
0x1800db5ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db5f3  nop
0x1800db5f4  lea     rcx, [rsp+108h+var_B0]
0x1800db5f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db5fe  nop
0x1800db5ff  lea     rcx, [rsp+108h+var_A8]
0x1800db604  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db609  nop
0x1800db60a  lea     rcx, [rsp+108h+var_A0]
0x1800db60f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db614  nop
0x1800db615  lea     rcx, [rsp+108h+var_30]
0x1800db61d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800db622  nop
0x1800db623  lea     rcx, [rsp+108h+lpName]
0x1800db62b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800db630  nop
0x1800db631  jmp     short loc_1800DB635
0x1800db633  jmp     short $+2
0x1800db635  mov     eax, [rsp+108h+var_D0]
0x1800db639  mov     rcx, [rsp+108h+var_10]
0x1800db641  xor     rcx, rsp; StackCookie
0x1800db644  call    __security_check_cookie
0x1800db649  lea     r11, [rsp+108h+var_8]
0x1800db651  mov     rbx, [r11+18h]
0x1800db655  mov     rsi, [r11+20h]
0x1800db659  mov     rsp, r11
0x1800db65c  pop     rdi
0x1800db65d  retn
```

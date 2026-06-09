# Windows::Internal::CapabilityAccess::Private::SuspiciousRuleManager::Create(void)

- ea: `0x180063ac8`
- end: `0x180064089`
- name: `?Create@SuspiciousRuleManager@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@$$CBVSuspiciousRuleManager@Private@CapabilityAccess@Internal@Windows@@@std@@XZ`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005b214`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001f5f4`
- `0x18002392c`
- `0x18002aa28`
- `0x18003afa0`
- `0x1800467c8`
- `0x1800493d4`
- `0x180063424`
- `0x180063470`
- `0x180063510`
- `0x18006362c`
- `0x1800638c8`
- `0x18006393c`
- `0x180063a18`
- `0x180063ac8`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063b59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063b59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ddc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063f2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ddc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063f2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063e4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063e4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::SuspiciousRuleManager::Create(_QWORD *a1)
{
  unsigned int v2; // esi
  int v3; // r12d
  const unsigned __int16 (*v4)[29]; // rdx
  __int64 *v5; // rax
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  HSTRING v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *, _BYTE *); // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, _QWORD); // rbx
  int v16; // eax
  int v17; // eax
  HSTRING v18; // rcx
  unsigned int v19; // r15d
  __int64 v20; // r13
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, HSTRING *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64, _QWORD); // rbx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, _QWORD, __int64 *); // rbx
  int v34; // eax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  int v37; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v39; // rax
  PCWSTR v40; // rax
  __int64 v41; // rax
  int v43; // [rsp+20h] [rbp-E0h]
  _BYTE v44[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v45; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v46; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v47; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v56; // [rsp+88h] [rbp-78h] BYREF
  int v57; // [rsp+90h] [rbp-70h]
  _QWORD v58[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v59[16]; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-30h]
  HSTRING v62[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v63; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v64; // [rsp+108h] [rbp+8h]
  _BYTE v65[24]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v56 = a1;
  v2 = 0;
  v3 = 0;
  v57 = 0;
  std::make_shared<Windows::Internal::CapabilityAccess::Private::SuspiciousRuleManager,>(v58);
  v51 = 0;
  v5 = (__int64 *)Windows::Internal::StringReference::StringReference(v62, v4);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v5, &v51);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
      (const char *)(unsigned int)v6,
      v43);
  v55 = 0;
  v8 = *Windows::Internal::StringReference::StringReference(v62, (const unsigned __int16 (*)[29])v7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v55);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v43);
  v44[0] = 0;
  v10 = v55;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _BYTE *))(*(_QWORD *)v55 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v62, off_1800CC718);
  v13 = v11(v10, *(_QWORD *)(v12 + 24), &v51, v44);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
      (const char *)(unsigned int)v13,
      v43);
  v50 = 0;
  v14 = v51;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v51 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v61 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Rows", 5u, 4u);
  v16 = v15(v14, v61, &v50);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
      (const char *)(unsigned int)v16,
      v43);
  v56 = 0;
  v17 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
          &v50,
          (__int64)&v56);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
      (const char *)(unsigned int)v17,
      v43);
  v46 = 0;
  (*(void (__fastcall **)(_QWORD *, unsigned int *))(*v56 + 56LL))(v56, &v46);
  v49 = 0;
  string = 0;
  v54 = 0;
  v53 = 0;
  v45 = 0;
  v52 = 0;
  v18 = 0;
  v47 = 0;
  v19 = 0;
  v20 = v58[0];
  if ( v46 )
  {
    do
    {
      v21 = v50;
      v22 = (*v50)[7];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      v23 = v22(v21, (GUID *)v19, (__int64)&v49);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
          (const char *)(unsigned int)v23,
          v43);
      v24 = v49;
      v25 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v49 + 64LL);
      WindowsDeleteString(string);
      string = 0;
      v26 = v25(v24, 0, &string);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
          (const char *)(unsigned int)v26,
          v43);
      v27 = v49;
      v28 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      v29 = v28(v27, 1, &v54);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
          (const char *)(unsigned int)v29,
          v43);
      v30 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
              &v54,
              (__int64)&v53);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x40,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
          (const char *)(unsigned int)v30,
          v43);
      v31 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v53 + 56LL))(v53, &v45);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x41,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
          (const char *)(unsigned int)v31,
          v43);
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      if ( v45 )
      {
        do
        {
          v32 = v53;
          v33 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          v34 = v33(v32, v2, &v52);
          if ( v34 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x47,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
              (const char *)(unsigned int)v34,
              v43);
          v35 = v52;
          v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 64LL);
          WindowsDeleteString(v47);
          v47 = 0;
          v37 = v36(v35, &v47);
          if ( v37 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x48,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\suspiciousrulemanager.cpp",
              (const char *)(unsigned int)v37,
              v43);
          StringRawBuffer = WindowsGetStringRawBuffer(v47, 0);
          v39 = std::wstring::wstring(v62, StringRawBuffer);
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&hstringHeader, v39);
          std::wstring::_Tidy_deallocate(v62);
          ++v2;
        }
        while ( v2 < v45 );
      }
      v40 = WindowsGetStringRawBuffer(string, 0);
      v41 = std::wstring::wstring(v62, v40);
      v63 = 0;
      v64 = 0;
      v63 = *(_OWORD *)v41;
      v64 = *(_OWORD *)(v41 + 16);
      v2 = 0;
      *(_QWORD *)(v41 + 16) = 0;
      *(_QWORD *)(v41 + 24) = 7;
      *(_WORD *)v41 = 0;
      std::vector<std::wstring>::vector<std::wstring>(v65, &hstringHeader);
      v3 |= 2u;
      std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Emplace<std::pair<std::wstring,std::vector<std::wstring>>>(
        v20 + 8,
        v59,
        &v63);
      TerminateAppData::~TerminateAppData((TerminateAppData *)&v63);
      std::wstring::_Tidy_deallocate(v62);
      std::vector<std::wstring>::_Tidy(&hstringHeader);
      ++v19;
    }
    while ( v19 < v46 );
    v18 = v47;
  }
  *a1 = v20;
  a1[1] = v58[1];
  WindowsDeleteString(v18);
  v47 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  return a1;
}

```

## disassembly

```asm
0x180063ac8  push    rbp
0x180063aca  push    rbx
0x180063acb  push    rsi
0x180063acc  push    rdi
0x180063acd  push    r12
0x180063acf  push    r13
0x180063ad1  push    r14
0x180063ad3  push    r15
0x180063ad5  lea     rbp, [rsp-48h]
0x180063ada  sub     rsp, 148h
0x180063ae1  mov     rax, cs:__security_cookie
0x180063ae8  xor     rax, rsp
0x180063aeb  mov     [rbp+80h+var_50], rax
0x180063aef  mov     r14, rcx
0x180063af2  mov     [rbp+80h+var_F8], rcx
0x180063af6  xor     esi, esi
0x180063af8  mov     r12d, esi
0x180063afb  mov     [rbp+80h+var_F0], esi
0x180063afe  lea     rcx, [rbp+80h+var_E8]
0x180063b02  call    ??$make_shared@VSuspiciousRuleManager@Private@CapabilityAccess@Internal@Windows@@$$V@std@@YA?AV?$shared_ptr@VSuspiciousRuleManager@Private@CapabilityAccess@Internal@Windows@@@0@XZ; std::make_shared<Windows::Internal::CapabilityAccess::Private::SuspiciousRuleManager,>(void)
0x180063b07  nop
0x180063b08  mov     [rsp+180h+var_120], rsi
0x180063b0d  lea     rcx, [rbp+80h+var_A8]; string
0x180063b11  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x180063b16  lea     rdx, [rsp+180h+var_120]
0x180063b1b  mov     rcx, [rax]
0x180063b1e  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180063b23  mov     rcx, [rbp+88h]; this
0x180063b2a  test    eax, eax
0x180063b2c  js      loc_180063FB7
0x180063b32  mov     [rbp+80h+var_100], rsi
0x180063b36  lea     rcx, [rbp+80h+var_A8]; string
0x180063b3a  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x180063b3f  mov     rbx, [rax]
0x180063b42  lea     rcx, [rbp+80h+var_100]
0x180063b46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063b4b  lea     r8, [rbp+80h+var_100]
0x180063b4f  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180063b56  mov     rcx, rbx
0x180063b59  call    cs:__imp_RoGetActivationFactory
0x180063b5f  mov     rcx, [rbp+88h]; this
0x180063b66  test    eax, eax
0x180063b68  js      loc_180063FCC
0x180063b6e  mov     [rsp+180h+var_150], sil
0x180063b73  mov     rdi, [rbp+80h+var_100]
0x180063b77  mov     rax, [rdi]
0x180063b7a  mov     rbx, [rax+38h]
0x180063b7e  lea     rcx, [rsp+180h+var_120]
0x180063b83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063b88  lea     rdx, off_1800CC718; "{\"Rows\":[[\"!isre1.exe\", [\"micropho"...
0x180063b8f  lea     rcx, [rbp+80h+var_A8]
0x180063b93  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180063b98  nop
0x180063b99  lea     r9, [rsp+180h+var_150]
0x180063b9e  lea     r8, [rsp+180h+var_120]
0x180063ba3  mov     rdx, [rax+18h]
0x180063ba7  mov     rcx, rdi
0x180063baa  mov     rax, rbx
0x180063bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063bb2  mov     rcx, [rbp+88h]; this
0x180063bb9  test    eax, eax
0x180063bbb  js      loc_180063FE1
0x180063bc1  mov     [rsp+180h+var_128], rsi
0x180063bc6  mov     rdi, [rsp+180h+var_120]
0x180063bcb  mov     rax, [rdi]
0x180063bce  mov     rbx, [rax+48h]
0x180063bd2  lea     rcx, [rsp+180h+var_128]
0x180063bd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063bdc  mov     [rbp+80h+var_B0], rsi
0x180063be0  lea     r9d, [rsi+4]; unsigned int
0x180063be4  lea     r8d, [rsi+5]; unsigned int
0x180063be8  lea     rdx, aRows; "Rows"
0x180063bef  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x180063bf3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180063bf8  nop
0x180063bf9  lea     r8, [rsp+180h+var_128]
0x180063bfe  mov     rdx, [rbp+80h+var_B0]
0x180063c02  mov     rcx, rdi
0x180063c05  mov     rax, rbx
0x180063c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c0d  mov     rcx, [rbp+88h]; this
0x180063c14  test    eax, eax
0x180063c16  js      loc_180063FF6
0x180063c1c  mov     [rbp+80h+var_F8], rsi
0x180063c20  lea     rdx, [rbp+80h+var_F8]
0x180063c24  lea     rcx, [rsp+180h+var_128]
0x180063c29  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180063c2e  mov     rcx, [rbp+88h]; this
0x180063c35  test    eax, eax
0x180063c37  js      loc_18006400B
0x180063c3d  mov     [rsp+180h+var_148], esi
0x180063c41  mov     rcx, [rbp+80h+var_F8]
0x180063c45  mov     rax, [rcx]
0x180063c48  lea     rdx, [rsp+180h+var_148]
0x180063c4d  mov     rax, [rax+38h]
0x180063c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c56  mov     [rsp+180h+var_130], rsi
0x180063c5b  mov     [rsp+180h+string], rsi
0x180063c60  mov     [rsp+180h+var_108], rsi
0x180063c65  mov     [rsp+180h+var_110], rsi
0x180063c6a  mov     [rsp+180h+var_14C], esi
0x180063c6e  mov     [rsp+180h+var_118], rsi
0x180063c73  mov     ecx, esi
0x180063c75  mov     [rsp+180h+var_140], rcx
0x180063c7a  mov     r15d, esi
0x180063c7d  mov     r13, [rbp+80h+var_E8]
0x180063c81  cmp     [rsp+180h+var_148], esi
0x180063c85  jbe     loc_180063EEE
0x180063c8b  mov     rdi, [rsp+180h+var_128]
0x180063c90  mov     rax, [rdi]
0x180063c93  mov     rbx, [rax+38h]
0x180063c97  lea     rcx, [rsp+180h+var_130]
0x180063c9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063ca1  lea     r8, [rsp+180h+var_130]
0x180063ca6  mov     edx, r15d
0x180063ca9  mov     rcx, rdi
0x180063cac  mov     rax, rbx
0x180063caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cb4  mov     rcx, [rbp+88h]; this
0x180063cbb  test    eax, eax
0x180063cbd  js      loc_180063FA2
0x180063cc3  mov     rdi, [rsp+180h+var_130]
0x180063cc8  mov     rax, [rdi]
0x180063ccb  mov     rbx, [rax+40h]
0x180063ccf  mov     rcx, [rsp+180h+string]; string
0x180063cd4  call    cs:__imp_WindowsDeleteString
0x180063cda  mov     [rsp+180h+string], rsi
0x180063cdf  lea     r8, [rsp+180h+string]
0x180063ce4  xor     edx, edx
0x180063ce6  mov     rcx, rdi
0x180063ce9  mov     rax, rbx
0x180063cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cf1  mov     rcx, [rbp+88h]; this
0x180063cf8  test    eax, eax
0x180063cfa  js      loc_180063F8D
0x180063d00  mov     rdi, [rsp+180h+var_130]
0x180063d05  mov     rax, [rdi]
0x180063d08  mov     rbx, [rax+38h]
0x180063d0c  lea     rcx, [rsp+180h+var_108]
0x180063d11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063d16  lea     r8, [rsp+180h+var_108]
0x180063d1b  mov     edx, 1
0x180063d20  mov     rcx, rdi
0x180063d23  mov     rax, rbx
0x180063d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d2b  mov     rcx, [rbp+88h]; this
0x180063d32  test    eax, eax
0x180063d34  js      loc_180064074
0x180063d3a  lea     rdx, [rsp+180h+var_110]
0x180063d3f  lea     rcx, [rsp+180h+var_108]
0x180063d44  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180063d49  mov     rcx, [rbp+88h]; this
0x180063d50  test    eax, eax
0x180063d52  js      loc_18006405F
0x180063d58  mov     rcx, [rsp+180h+var_110]
0x180063d5d  mov     rax, [rcx]
0x180063d60  lea     rdx, [rsp+180h+var_14C]
0x180063d65  mov     rax, [rax+38h]
0x180063d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d6e  mov     rcx, [rbp+88h]; this
0x180063d75  test    eax, eax
0x180063d77  js      loc_18006404A
0x180063d7d  xorps   xmm0, xmm0
0x180063d80  movdqu  xmmword ptr [rbp+80h+hstringHeader.Reserved], xmm0
0x180063d85  mov     qword ptr [rbp+80h+hstringHeader.Reserved+10h], rsi
0x180063d89  cmp     [rsp+180h+var_14C], 0
0x180063d8e  jbe     loc_180063E46
0x180063d94  mov     rdi, [rsp+180h+var_110]
0x180063d99  mov     rax, [rdi]
0x180063d9c  mov     rbx, [rax+30h]
0x180063da0  lea     rcx, [rsp+180h+var_118]
0x180063da5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063daa  lea     r8, [rsp+180h+var_118]
0x180063daf  mov     edx, esi
0x180063db1  mov     rcx, rdi
0x180063db4  mov     rax, rbx
0x180063db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063dbc  mov     rcx, [rbp+88h]; this
0x180063dc3  test    eax, eax
0x180063dc5  js      loc_180064035
0x180063dcb  mov     rdi, [rsp+180h+var_118]
0x180063dd0  mov     rax, [rdi]
0x180063dd3  mov     rbx, [rax+40h]
0x180063dd7  mov     rcx, [rsp+180h+var_140]; string
0x180063ddc  call    cs:__imp_WindowsDeleteString
0x180063de2  mov     [rsp+180h+var_140], 0
0x180063deb  lea     rdx, [rsp+180h+var_140]
0x180063df0  mov     rcx, rdi
0x180063df3  mov     rax, rbx
0x180063df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063dfb  mov     rcx, [rbp+88h]; this
0x180063e02  test    eax, eax
0x180063e04  js      loc_180064020
0x180063e0a  xor     edx, edx; length
0x180063e0c  mov     rcx, [rsp+180h+var_140]; string
0x180063e11  call    cs:__imp_WindowsGetStringRawBuffer
0x180063e17  mov     rdx, rax
0x180063e1a  lea     rcx, [rbp+80h+var_A8]
0x180063e1e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180063e23  nop
0x180063e24  mov     rdx, rax
0x180063e27  lea     rcx, [rbp+80h+hstringHeader]
0x180063e2b  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180063e30  nop
0x180063e31  lea     rcx, [rbp+80h+var_A8]
0x180063e35  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063e3a  inc     esi
0x180063e3c  cmp     esi, [rsp+180h+var_14C]
0x180063e40  jb      loc_180063D94
0x180063e46  xor     edx, edx; length
0x180063e48  mov     rcx, [rsp+180h+string]; string
0x180063e4d  call    cs:__imp_WindowsGetStringRawBuffer
0x180063e53  mov     rdx, rax
0x180063e56  lea     rcx, [rbp+80h+var_A8]
0x180063e5a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180063e5f  mov     rdx, rax
0x180063e62  xorps   xmm0, xmm0
0x180063e65  movups  [rbp+80h+var_88], xmm0
0x180063e69  xorps   xmm1, xmm1
0x180063e6c  movdqu  [rbp+80h+var_78], xmm1
0x180063e71  movups  xmm0, xmmword ptr [rax]
0x180063e74  movdqu  [rbp+80h+var_88], xmm0
0x180063e79  mov     rax, [rax+10h]
0x180063e7d  mov     qword ptr [rbp+80h+var_78], rax
0x180063e81  mov     rax, [rdx+18h]
0x180063e85  mov     qword ptr [rbp+80h+var_78+8], rax
0x180063e89  xor     esi, esi
0x180063e8b  mov     [rdx+10h], rsi
0x180063e8f  mov     qword ptr [rdx+18h], 7
0x180063e97  mov     [rdx], si
0x180063e9a  lea     rdx, [rbp+80h+hstringHeader]
0x180063e9e  lea     rcx, [rbp+80h+var_68]
0x180063ea2  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180063ea7  nop
0x180063ea8  or      r12d, 2
0x180063eac  lea     r8, [rbp+80h+var_88]
0x180063eb0  lea     rdx, [rbp+80h+var_D8]
0x180063eb4  lea     rcx, [r13+8]
0x180063eb8  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Emplace<std::pair<std::wstring,std::vector<std::wstring>>>(std::pair<std::wstring,std::vector<std::wstring>> &&)
0x180063ebd  nop
0x180063ebe  lea     rcx, [rbp+80h+var_88]; this
0x180063ec2  call    ??1TerminateAppData@@QEAA@XZ; TerminateAppData::~TerminateAppData(void)
0x180063ec7  nop
0x180063ec8  lea     rcx, [rbp+80h+var_A8]
0x180063ecc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063ed1  nop
0x180063ed2  lea     rcx, [rbp+80h+hstringHeader]
0x180063ed6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180063edb  inc     r15d
0x180063ede  cmp     r15d, [rsp+180h+var_148]
0x180063ee3  jb      loc_180063C8B
0x180063ee9  mov     rcx, [rsp+180h+var_140]; string
0x180063eee  mov     [r14], r13
0x180063ef1  mov     rax, [rbp+80h+var_E0]
0x180063ef5  mov     [r14+8], rax
0x180063ef9  call    cs:__imp_WindowsDeleteString
0x180063eff  mov     [rsp+180h+var_140], rsi
0x180063f04  lea     rcx, [rsp+180h+var_118]
0x180063f09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f0e  nop
0x180063f0f  lea     rcx, [rsp+180h+var_110]
0x180063f14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f19  nop
0x180063f1a  lea     rcx, [rsp+180h+var_108]
0x180063f1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f24  nop
0x180063f25  mov     rcx, [rsp+180h+string]; string
0x180063f2a  call    cs:__imp_WindowsDeleteString
0x180063f30  mov     [rsp+180h+string], rsi
0x180063f35  lea     rcx, [rsp+180h+var_130]
0x180063f3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f3f  nop
0x180063f40  lea     rcx, [rbp+80h+var_F8]
0x180063f44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f49  nop
0x180063f4a  lea     rcx, [rsp+180h+var_128]
0x180063f4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f54  nop
0x180063f55  lea     rcx, [rbp+80h+var_100]
0x180063f59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f5e  nop
0x180063f5f  lea     rcx, [rsp+180h+var_120]
0x180063f64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063f69  nop
0x180063f6a  mov     rax, r14
0x180063f6d  mov     rcx, [rbp+80h+var_50]
0x180063f71  xor     rcx, rsp; StackCookie
0x180063f74  call    __security_check_cookie
0x180063f79  add     rsp, 148h
0x180063f80  pop     r15
0x180063f82  pop     r14
0x180063f84  pop     r13
0x180063f86  pop     r12
0x180063f88  pop     rdi
0x180063f89  pop     rsi
0x180063f8a  pop     rbx
0x180063f8b  pop     rbp
0x180063f8c  retn
0x180063f8d  mov     r9d, eax; char *
0x180063f90  lea     r8, aOnecoreBaseDev_43; "onecore\\base\\devices\\cam\\core\\susp"...
  ... truncated ...
```

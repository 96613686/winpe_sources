# StoreApplication::GetStoreAppManifestXmlSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,bool)

- ea: `0x1800dbff4`
- end: `0x1800dc487`
- name: `?GetStoreAppManifestXmlSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@_N@Z`
- size: `1171`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800db168`
- `0x1800dd87c`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000edf0`
- `0x18000faf0`
- `0x18001082c`
- `0x1800108a8`
- `0x18001c5f0`
- `0x1800252b0`
- `0x1800c97f0`
- `0x1800d8684`
- `0x1800d94a8`
- `0x1800db8b8`
- `0x1800dbff4`
- `0x1800de91c`
- `0x1800decb8`
- `0x1800dfe24`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc1a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc1a3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800dc0a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800dc0a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dc338`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dc338`

## string_xrefs

- `0x1800dc076`: `Windows.Internal.StateRepository.AppxManifest`
- `0x1800dc0b5`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc0eb`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc145`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc18a`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc349`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc3ca`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_OWORD *__fastcall StoreApplication::GetStoreAppManifestXmlSr(_OWORD *a1, _QWORD *a2, char a3)
{
  __int64 v6; // rbx
  int ActivationFactory; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 StoreAppManifestPathFromPackageSr; // rax
  __int64 XmlFromFileSr; // rax
  __int64 v20; // rax
  _OWORD *v21; // rcx
  __int64 v22; // rax
  HRESULT v23; // eax
  LPVOID v24; // rbx
  void (__fastcall *v25)(LPVOID, __int64, __int16 *); // rdi
  const unsigned __int16 *v26; // rdx
  _bstr_t *v27; // rax
  __int64 v28; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  char v32[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v33; // [rsp+34h] [rbp-CCh] BYREF
  _OWORD *v34; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v39[4]; // [rsp+68h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h]
  _QWORD v42[4]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v43; // [rsp+C8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  _BYTE v45[32]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v34 = a1;
  std::wstring::wstring(v39, &pszFormat);
  std::wstring::wstring(v42, &pszFormat);
  v32[0] = 0;
  string[0] = 0;
  v35 = 0;
  v37 = 0;
  v41 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.AppxManifest",
    0x2Eu,
    0x2Du);
  v6 = v41;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_5fc148b1_ad6b_4d3d_b11d_e881979c15f4, &v35);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x691,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)ActivationFactory,
      ppv);
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v35 + 56LL))(v35, *a2, v32);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x694,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  if ( v32[0] && a3 )
  {
    v9 = v35;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    v11 = v10(v9, *a2, &v37);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x698,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v11,
        ppv);
    v12 = v37;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 80LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      string,
      0);
    v14 = v13(v12, string);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x69A,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v14,
        ppv);
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    v16 = -1;
    do
      ++v16;
    while ( StringRawBuffer[v16] );
    std::wstring::_Assign<unsigned short>(v39, StringRawBuffer);
  }
  else
  {
    v17 = *a2;
    v34 = (_OWORD *)*a2;
    if ( a3 )
    {
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      StoreAppManifestPathFromPackageSr = StoreApplication::GetStoreAppManifestPathFromPackageSr(
                                            &hstringHeader,
                                            &v34,
                                            1);
      std::wstring::operator=(v42, StoreAppManifestPathFromPackageSr);
      std::wstring::_Tidy_deallocate(&hstringHeader);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      XmlFromFileSr = StoreApplication::LoadXmlFromFileSr((__int64)&hstringHeader, v42);
      std::wstring::operator=(v39, XmlFromFileSr);
    }
    else
    {
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      StoreApplication::GetStoreAppManifestPathFromPackageSr(&hstringHeader, &v34, 2);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      v20 = StoreApplication::LoadXmlFromFileSr((__int64)v45, &hstringHeader);
      std::wstring::operator=(v39, v20);
      std::wstring::_Tidy_deallocate(v45);
    }
    std::wstring::_Tidy_deallocate(&hstringHeader);
  }
  if ( v39[2] )
  {
    if ( !v42[2] )
    {
      v21 = (_OWORD *)*a2;
      v34 = v21;
      if ( v21 )
        (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v21 + 8LL))(v21);
      v22 = StoreApplication::GetStoreAppManifestPathFromPackageSr(v45, &v34, 1);
      std::wstring::operator=(v42, v22);
      std::wstring::_Tidy_deallocate(v45);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    }
    v33 = 0;
    v36 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v23 = CoCreateInstance(
            &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
            0,
            1u,
            &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
            &v36);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6B7,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v23,
        ppva);
    v24 = v36;
    v25 = *(void (__fastcall **)(LPVOID, __int64, __int16 *))(*(_QWORD *)v36 + 520LL);
    v26 = (const unsigned __int16 *)v39;
    if ( v39[3] > (unsigned __int16 *)7 )
      v26 = v39[0];
    v27 = _bstr_t::_bstr_t((_bstr_t *)&v34, v26);
    if ( *(_QWORD *)v27 )
      v28 = **(_QWORD **)v27;
    else
      v28 = 0;
    v25(v24, v28, &v33);
    _bstr_t::_Free((_bstr_t *)&v34);
    if ( v33 != -1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6B9,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)0xC00CE225LL,
        ppva);
    StoreApplication::TransformAndLocalizeManifestXml((__int64)&v43, (__int64 *)&v36, (__int64)v42, a3);
    *a1 = v43;
    a1[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v43) = 0;
    std::wstring::_Tidy_deallocate(&v43);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  }
  else
  {
    std::wstring::wstring(a1, &pszFormat);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Windows::Internal::String::~String((Windows::Internal::String *)string);
  std::wstring::_Tidy_deallocate(v42);
  std::wstring::_Tidy_deallocate(v39);
  return a1;
}

```

## disassembly

```asm
0x1800dbff4  mov     [rsp-8+arg_10], rbx
0x1800dbff9  mov     [rsp-8+arg_18], rsi
0x1800dbffe  push    rbp
0x1800dbfff  push    rdi
0x1800dc000  push    r12
0x1800dc002  push    r14
0x1800dc004  push    r15
0x1800dc006  lea     rbp, [rsp-10h]
0x1800dc00b  sub     rsp, 110h
0x1800dc012  mov     rax, cs:__security_cookie
0x1800dc019  xor     rax, rsp
0x1800dc01c  mov     [rbp+30h+var_28], rax
0x1800dc020  mov     r15b, r8b
0x1800dc023  mov     r14, rdx
0x1800dc026  mov     rsi, rcx
0x1800dc029  mov     [rsp+130h+var_F8], rcx
0x1800dc02e  xor     r12d, r12d
0x1800dc031  lea     rdx, pszFormat
0x1800dc038  lea     rcx, [rsp+130h+var_C8]
0x1800dc03d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dc042  nop
0x1800dc043  lea     rdx, pszFormat
0x1800dc04a  lea     rcx, [rbp+30h+var_88]
0x1800dc04e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dc053  nop
0x1800dc054  mov     [rsp+130h+var_100], r12b
0x1800dc059  mov     [rsp+130h+string], r12
0x1800dc05e  mov     [rsp+130h+var_F0], r12
0x1800dc063  mov     [rsp+130h+var_E0], r12
0x1800dc068  mov     [rbp+30h+var_90], r12
0x1800dc06c  lea     r9d, [r12+2Dh]; unsigned int
0x1800dc071  lea     r8d, [r12+2Eh]; unsigned int
0x1800dc076  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_AppxManifest@@3QBGB; "Windows.Internal.StateRepository.AppxMa"...
0x1800dc07d  lea     rcx, [rbp+30h+hstringHeader]; hstringHeader
0x1800dc081  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800dc086  nop
0x1800dc087  mov     rbx, [rbp+30h+var_90]
0x1800dc08b  lea     rcx, [rsp+130h+var_F0]
0x1800dc090  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc095  lea     r8, [rsp+130h+var_F0]
0x1800dc09a  lea     rdx, _GUID_5fc148b1_ad6b_4d3d_b11d_e881979c15f4
0x1800dc0a1  mov     rcx, rbx
0x1800dc0a4  call    cs:__imp_RoGetActivationFactory
0x1800dc0aa  mov     rcx, [rbp+38h]; this
0x1800dc0ae  test    eax, eax
0x1800dc0b0  jns     short loc_1800DC0C7
0x1800dc0b2  mov     r9d, eax; char *
0x1800dc0b5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc0bc  mov     edx, 691h; void *
0x1800dc0c1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc0c7  mov     rcx, [rsp+130h+var_F0]
0x1800dc0cc  mov     rax, [rcx]
0x1800dc0cf  lea     r8, [rsp+130h+var_100]
0x1800dc0d4  mov     rdx, [r14]
0x1800dc0d7  mov     rax, [rax+38h]
0x1800dc0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc0e0  mov     rcx, [rbp+38h]; this
0x1800dc0e4  test    eax, eax
0x1800dc0e6  jns     short loc_1800DC0FD
0x1800dc0e8  mov     r9d, eax; char *
0x1800dc0eb  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc0f2  mov     edx, 694h; void *
0x1800dc0f7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc0fd  cmp     [rsp+130h+var_100], r12b
0x1800dc102  jz      loc_1800DC1C9
0x1800dc108  test    r15b, r15b
0x1800dc10b  jz      loc_1800DC1C9
0x1800dc111  mov     rdi, [rsp+130h+var_F0]
0x1800dc116  mov     rax, [rdi]
0x1800dc119  mov     rbx, [rax+58h]
0x1800dc11d  lea     rcx, [rsp+130h+var_E0]
0x1800dc122  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc127  lea     r8, [rsp+130h+var_E0]
0x1800dc12c  mov     rdx, [r14]
0x1800dc12f  mov     rcx, rdi
0x1800dc132  mov     rax, rbx
0x1800dc135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc13a  mov     rcx, [rbp+38h]; this
0x1800dc13e  test    eax, eax
0x1800dc140  jns     short loc_1800DC157
0x1800dc142  mov     r9d, eax; char *
0x1800dc145  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc14c  mov     edx, 698h; void *
0x1800dc151  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc157  mov     rdi, [rsp+130h+var_E0]
0x1800dc15c  mov     rax, [rdi]
0x1800dc15f  mov     rbx, [rax+50h]
0x1800dc163  xor     edx, edx
0x1800dc165  lea     rcx, [rsp+130h+string]
0x1800dc16a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dc16f  lea     rdx, [rsp+130h+string]
0x1800dc174  mov     rcx, rdi
0x1800dc177  mov     rax, rbx
0x1800dc17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc17f  mov     rcx, [rbp+38h]; this
0x1800dc183  test    eax, eax
0x1800dc185  jns     short loc_1800DC19C
0x1800dc187  mov     r9d, eax; char *
0x1800dc18a  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc191  mov     edx, 69Ah; void *
0x1800dc196  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc19c  xor     edx, edx; length
0x1800dc19e  mov     rcx, [rsp+130h+string]; string
0x1800dc1a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc1a9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800dc1ad  inc     r8
0x1800dc1b0  cmp     [rax+r8*2], r12w
0x1800dc1b5  jnz     short loc_1800DC1AD
0x1800dc1b7  mov     rdx, rax
0x1800dc1ba  lea     rcx, [rsp+130h+var_C8]
0x1800dc1bf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dc1c4  jmp     loc_1800DC296
0x1800dc1c9  mov     rcx, [r14]
0x1800dc1cc  mov     [rsp+130h+var_F8], rcx
0x1800dc1d1  test    r15b, r15b
0x1800dc1d4  jz      short loc_1800DC238
0x1800dc1d6  test    rcx, rcx
0x1800dc1d9  jz      short loc_1800DC1E8
0x1800dc1db  mov     rax, [rcx]
0x1800dc1de  mov     rax, [rax+8]
0x1800dc1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc1e7  nop
0x1800dc1e8  mov     r8d, 1
0x1800dc1ee  lea     rdx, [rsp+130h+var_F8]
0x1800dc1f3  lea     rcx, [rbp+30h+hstringHeader]
0x1800dc1f7  call    ?GetStoreAppManifestPathFromPackageSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,ManifestType)
0x1800dc1fc  mov     rdx, rax
0x1800dc1ff  lea     rcx, [rbp+30h+var_88]
0x1800dc203  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800dc208  lea     rcx, [rbp+30h+hstringHeader]
0x1800dc20c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dc211  nop
0x1800dc212  lea     rcx, [rsp+130h+var_F8]
0x1800dc217  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc21c  lea     rdx, [rbp+30h+var_88]
0x1800dc220  lea     rcx, [rbp+30h+hstringHeader]
0x1800dc224  call    ?LoadXmlFromFileSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; StoreApplication::LoadXmlFromFileSr(std::wstring const &)
0x1800dc229  mov     rdx, rax
0x1800dc22c  lea     rcx, [rsp+130h+var_C8]
0x1800dc231  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800dc236  jmp     short loc_1800DC28D
0x1800dc238  test    rcx, rcx
0x1800dc23b  jz      short loc_1800DC24A
0x1800dc23d  mov     rax, [rcx]
0x1800dc240  mov     rax, [rax+8]
0x1800dc244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc249  nop
0x1800dc24a  mov     r8d, 2
0x1800dc250  lea     rdx, [rsp+130h+var_F8]
0x1800dc255  lea     rcx, [rbp+30h+hstringHeader]
0x1800dc259  call    ?GetStoreAppManifestPathFromPackageSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,ManifestType)
0x1800dc25e  nop
0x1800dc25f  lea     rcx, [rsp+130h+var_F8]
0x1800dc264  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc269  lea     rdx, [rbp+30h+hstringHeader]
0x1800dc26d  lea     rcx, [rbp+30h+var_48]
0x1800dc271  call    ?LoadXmlFromFileSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; StoreApplication::LoadXmlFromFileSr(std::wstring const &)
0x1800dc276  mov     rdx, rax
0x1800dc279  lea     rcx, [rsp+130h+var_C8]
0x1800dc27e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800dc283  lea     rcx, [rbp+30h+var_48]
0x1800dc287  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dc28c  nop
0x1800dc28d  lea     rcx, [rbp+30h+hstringHeader]
0x1800dc291  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dc296  cmp     [rsp+130h+var_B8], r12
0x1800dc29b  jnz     short loc_1800DC2B1
0x1800dc29d  lea     rdx, pszFormat
0x1800dc2a4  mov     rcx, rsi
0x1800dc2a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dc2ac  jmp     loc_1800DC427
0x1800dc2b1  cmp     [rbp+30h+var_78], r12
0x1800dc2b5  jnz     short loc_1800DC305
0x1800dc2b7  mov     rcx, [r14]
0x1800dc2ba  mov     [rsp+130h+var_F8], rcx
0x1800dc2bf  test    rcx, rcx
0x1800dc2c2  jz      short loc_1800DC2D1
0x1800dc2c4  mov     rax, [rcx]
0x1800dc2c7  mov     rax, [rax+8]
0x1800dc2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc2d0  nop
0x1800dc2d1  mov     r8d, 1
0x1800dc2d7  lea     rdx, [rsp+130h+var_F8]
0x1800dc2dc  lea     rcx, [rbp+30h+var_48]
0x1800dc2e0  call    ?GetStoreAppManifestPathFromPackageSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,ManifestType)
0x1800dc2e5  mov     rdx, rax
0x1800dc2e8  lea     rcx, [rbp+30h+var_88]
0x1800dc2ec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800dc2f1  lea     rcx, [rbp+30h+var_48]
0x1800dc2f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dc2fa  nop
0x1800dc2fb  lea     rcx, [rsp+130h+var_F8]
0x1800dc300  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc305  mov     [rsp+130h+var_FC], r12w
0x1800dc30b  mov     [rsp+130h+var_E8], r12
0x1800dc310  lea     rcx, [rsp+130h+var_E8]
0x1800dc315  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc31a  lea     rax, [rsp+130h+var_E8]
0x1800dc31f  mov     qword ptr [rsp+130h+ppv], rax; int
0x1800dc324  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800dc32b  xor     edx, edx; pUnkOuter
0x1800dc32d  lea     r8d, [rdx+1]; dwClsContext
0x1800dc331  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800dc338  call    cs:__imp_CoCreateInstance
0x1800dc33e  mov     rcx, [rbp+38h]; this
0x1800dc342  test    eax, eax
0x1800dc344  jns     short loc_1800DC35B
0x1800dc346  mov     r9d, eax; char *
0x1800dc349  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc350  mov     edx, 6B7h; void *
0x1800dc355  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc35b  mov     rbx, [rsp+130h+var_E8]
0x1800dc360  mov     rax, [rbx]
0x1800dc363  mov     rdi, [rax+208h]
0x1800dc36a  lea     rdx, [rsp+130h+var_C8]
0x1800dc36f  cmp     [rbp+30h+var_B0], 7
0x1800dc374  cmova   rdx, [rsp+130h+var_C8]; unsigned __int16 *
0x1800dc37a  lea     rcx, [rsp+130h+var_F8]; this
0x1800dc37f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800dc384  nop
0x1800dc385  mov     rdx, [rax]
0x1800dc388  test    rdx, rdx
0x1800dc38b  jz      short loc_1800DC392
0x1800dc38d  mov     rdx, [rdx]
0x1800dc390  jmp     short loc_1800DC395
0x1800dc392  mov     rdx, r12
0x1800dc395  lea     r8, [rsp+130h+var_FC]
0x1800dc39a  mov     rcx, rbx
0x1800dc39d  mov     rax, rdi
0x1800dc3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc3a5  nop
0x1800dc3a6  lea     rcx, [rsp+130h+var_F8]; this
0x1800dc3ab  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800dc3b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800dc3b4  cmp     [rsp+130h+var_FC], ax
0x1800dc3b9  setz    al
0x1800dc3bc  mov     rcx, [rbp+38h]; this
0x1800dc3c0  test    al, al
0x1800dc3c2  jnz     short loc_1800DC3DC
0x1800dc3c4  mov     r9d, 0C00CE225h; char *
0x1800dc3ca  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc3d1  mov     edx, 6B9h; void *
0x1800dc3d6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc3dc  mov     r9b, r15b
0x1800dc3df  lea     r8, [rbp+30h+var_88]
0x1800dc3e3  lea     rdx, [rsp+130h+var_E8]
0x1800dc3e8  lea     rcx, [rbp+30h+var_68]
0x1800dc3ec  call    ?TransformAndLocalizeManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV23@_N@Z; StoreApplication::TransformAndLocalizeManifestXml(Microsoft::WRL::ComPtr<IXMLDOMDocument> const &,std::wstring const &,bool)
0x1800dc3f1  movups  xmm0, [rbp+30h+var_68]
0x1800dc3f5  movups  xmmword ptr [rsi], xmm0
0x1800dc3f8  movups  xmm1, [rbp+30h+var_58]
0x1800dc3fc  movups  xmmword ptr [rsi+10h], xmm1
0x1800dc400  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800dc408  movdqu  [rbp+30h+var_58], xmm0
0x1800dc40d  mov     word ptr [rbp+30h+var_68], r12w
0x1800dc412  lea     rcx, [rbp+30h+var_68]
0x1800dc416  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dc41b  nop
0x1800dc41c  lea     rcx, [rsp+130h+var_E8]
0x1800dc421  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc426  nop
0x1800dc427  lea     rcx, [rsp+130h+var_E0]
0x1800dc42c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc431  nop
0x1800dc432  lea     rcx, [rsp+130h+var_F0]
0x1800dc437  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dc43c  nop
0x1800dc43d  lea     rcx, [rsp+130h+string]; this
0x1800dc442  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800dc447  nop
0x1800dc448  lea     rcx, [rbp+30h+var_88]
0x1800dc44c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dc451  nop
0x1800dc452  lea     rcx, [rsp+130h+var_C8]
0x1800dc457  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dc45c  mov     rax, rsi
0x1800dc45f  mov     rcx, [rbp+30h+var_28]
0x1800dc463  xor     rcx, rsp; StackCookie
0x1800dc466  call    __security_check_cookie
0x1800dc46b  lea     r11, [rsp+130h+var_20]
0x1800dc473  mov     rbx, [r11+40h]
0x1800dc477  mov     rsi, [r11+48h]
0x1800dc47b  mov     rsp, r11
0x1800dc47e  pop     r15
0x1800dc480  pop     r14
0x1800dc482  pop     r12
0x1800dc484  pop     rdi
0x1800dc485  pop     rbp
0x1800dc486  retn
```

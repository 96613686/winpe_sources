# Windows::Configuration::GetDeviceInfo(std::unordered_map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> const &)

- ea: `0x18008e3a0`
- end: `0x18008ec1a`
- name: `?GetDeviceInfo@Configuration@Windows@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@4@@Z`
- size: `2170`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800108b4`
- `0x1800112d0`
- `0x180011320`
- `0x180011680`
- `0x18002e698`
- `0x180041e4c`
- `0x18007023c`
- `0x180080c18`
- `0x180083510`
- `0x18008e3a0`
- `0x18008efe0`
- `0x18008f614`
- `0x18008f6cc`
- `0x18008f7ec`
- `0x18008f8d8`
- `0x18008fa18`
- `0x180090af0`
- `0x180092dd8`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e7f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e89b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e903`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e7f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e89b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e903`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ea00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ea00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e4d1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008e4f2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008e4f2`

## string_xrefs

- `0x18008eb6d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18008ebd1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18008ebf3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18008eb58`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008eb92`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008eba7`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008ec08`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008ebbc`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
_QWORD *__fastcall Windows::Configuration::GetDeviceInfo(__int64 a1, _QWORD *a2, __int64 a3)
{
  void (__fastcall ***v5)(_QWORD, __int64 *, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rcx
  HRESULT StringReference; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  int v19; // edi
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, _QWORD **); // r15
  _QWORD *v22; // rcx
  int v23; // eax
  const wchar_t *v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v31; // r8
  __int128 *p_hstringHeader; // rdx
  __int64 v33; // r9
  unsigned __int64 i; // rcx
  PCWSTR v35; // rax
  __int64 v36; // r8
  int v37; // edi
  __int128 *v38; // rdx
  __int64 v39; // r9
  unsigned __int64 j; // rcx
  _QWORD *v41; // rax
  PCWSTR v42; // rax
  __int64 v43; // r8
  __int64 v44; // rcx
  PCWSTR v45; // rax
  __int64 v46; // rcx
  int v47; // eax
  int v48; // eax
  _QWORD *v49; // rcx
  __int64 v50; // rcx
  int v52; // [rsp+20h] [rbp-E0h]
  __int64 v53; // [rsp+28h] [rbp-D8h] BYREF
  int v54; // [rsp+30h] [rbp-D0h]
  int v55; // [rsp+34h] [rbp-CCh]
  __int128 hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int128 hstringHeader_16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v59[2]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v60; // [rsp+70h] [rbp-90h] BYREF
  __int64 v61; // [rsp+78h] [rbp-88h]
  __int128 v62; // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+90h] [rbp-70h]
  __int128 v64; // [rsp+98h] [rbp-68h] BYREF
  __int128 v65; // [rsp+A8h] [rbp-58h]
  _QWORD v66[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v67[2]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v68[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v69; // [rsp+100h] [rbp+0h]
  char v70[8]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v71; // [rsp+110h] [rbp+10h]
  char v72[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE Src[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v74[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v75[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v76[32]; // [rsp+188h] [rbp+88h] BYREF
  char v77[8]; // [rsp+1A8h] [rbp+A8h] BYREF
  HSTRING v78; // [rsp+1B0h] [rbp+B0h] BYREF
  HSTRING v79; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v80; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v81; // [rsp+1C8h] [rbp+C8h] BYREF
  _QWORD *v82; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v83; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 *v84; // [rsp+1E8h] [rbp+E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v69 = a2;
  v62 = 0;
  v63 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(v59, &v62);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v62);
  v80 = 0;
  *((_QWORD *)&hstringHeader + 1) = 0x600000001LL;
  *((_QWORD *)&hstringHeader_16 + 1) = L"+WU_OS";
  *(_QWORD *)&hstringHeader = (char *)&hstringHeader + 8;
  v5 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))v59[0];
  v6 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v59[0] + 104LL))(v59[0], (char *)&hstringHeader + 8);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6);
  v7 = v80;
  v80 = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v53 = 0x5A0B3BFCE2FCC7C1LL;
  v54 = -411914062;
  v55 = 2127286633;
  (**v5)(v5, &v53, &v80);
  v84 = 0;
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.System.Profile.AnalyticsInfo",
                      0x24u,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v9, v10);
LABEL_77:
    wil::details::in1diag3::Throw_Hr(
      v12,
      (void *)0x106,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)ActivationFactory,
      0);
  }
  ActivationFactory = RoGetActivationFactory(
                        *((_QWORD *)&hstringHeader_16 + 1),
                        &GUID_101704ea_a7f9_46d2_ab94_016865afdb25,
                        &v84);
  v12 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_77;
  v83 = 0;
  v13 = *v84;
  v83 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v13 + 48))(v84, v80, &v83);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v14,
      0);
  v15 = v83;
  v58 = 0;
  v16 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(v83);
  if ( v16 >= 0 )
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, &v58);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x719,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v16,
      16);
  v17 = v58;
  v58 = 0;
  v53 = v17;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v79 = 0;
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, HSTRING *))v17)(
          v17,
          &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b,
          &v79);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v18,
      1);
  v19 = 33;
  v52 = 33;
  v78 = v79;
  if ( v79 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v79 + 16LL))(v79);
  v81 = 0;
  v82 = 0;
  wil::iterable_range<ABI::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::begin(
    &v78,
    &v81);
  *(_QWORD *)&v62 = 0;
  *((_QWORD *)&v62 + 1) = 0xFFFFFFFFLL;
  v63 = 0;
  if ( DWORD2(v81) != -1 )
  {
    do
    {
      v20 = v81;
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v81 + 48LL);
      v22 = v82;
      if ( v82 )
      {
        v82 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
      }
      v23 = v21(v20, &v82);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v23,
          v52);
      v24 = L"&";
      if ( !a2[2] )
        v24 = L"E:";
      v25 = -1;
      do
        ++v25;
      while ( v24[v25] );
      std::wstring::append(a2);
      v78 = 0;
      v26 = *v82;
      v78 = 0;
      v27 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v26 + 48))(v82, &v78);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x110,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v27,
          v52);
      v79 = 0;
      v28 = *v82;
      v79 = 0;
      v29 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v28 + 56))(v82, &v79);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x112,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v29,
          v52);
      StringRawBuffer = WindowsGetStringRawBuffer(v78, 0);
      hstringHeader = 0;
      hstringHeader_16 = 0;
      v31 = -1;
      do
        ++v31;
      while ( StringRawBuffer[v31] );
      std::wstring::_Construct<1,wchar_t const *>(&hstringHeader);
      p_hstringHeader = &hstringHeader;
      if ( *((_QWORD *)&hstringHeader_16 + 1) > 7u )
        p_hstringHeader = (__int128 *)hstringHeader;
      v33 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 2 * (__int64)hstringHeader_16; ++i )
        v33 = 0x100000001B3LL * (*((unsigned __int8 *)p_hstringHeader + i) ^ (unsigned __int64)v33);
      if ( *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Find_last<std::wstring>(
                         a3,
                         v72,
                         &hstringHeader,
                         v33,
                         v52)
                     + 8) )
      {
        v35 = WindowsGetStringRawBuffer(v78, 0);
        v64 = 0;
        v65 = 0;
        v36 = -1;
        do
          ++v36;
        while ( v35[v36] );
        std::wstring::_Construct<1,wchar_t const *>(&v64);
        v37 = v19 | 2;
        v38 = &v64;
        if ( *((_QWORD *)&v65 + 1) > 7u )
          v38 = (__int128 *)v64;
        v39 = 0xCBF29CE484222325uLL;
        for ( j = 0; j < 2 * (__int64)v65; ++j )
          v39 = 0x100000001B3LL * (*((unsigned __int8 *)v38 + j) ^ (unsigned __int64)v39);
        std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Find_last<std::wstring>(
          a3,
          v70,
          &v64,
          v39,
          v37);
        if ( !v71 )
          std::_Xout_of_range("invalid unordered_map<K, T> key");
        v41 = (_QWORD *)std::wstring::wstring(v76, v71 + 48);
        v19 = v37 | 4;
      }
      else
      {
        v42 = WindowsGetStringRawBuffer(v79, 0);
        memset(v68, 0, sizeof(v68));
        v43 = -1;
        do
          ++v43;
        while ( v42[v43] );
        std::wstring::_Construct<1,wchar_t const *>(v68);
        v41 = v68;
        v19 |= 8u;
      }
      v52 = v19;
      v44 = v41[2];
      if ( v41[3] > 7u )
        v41 = (_QWORD *)*v41;
      v66[0] = v41;
      v66[1] = v44;
      Windows::Configuration::UrlEscapeString(v44, v75, v66);
      v45 = WindowsGetStringRawBuffer(v78, 0);
      v46 = -1;
      do
        ++v46;
      while ( v45[v46] );
      v67[0] = v45;
      v67[1] = v46;
      Windows::Configuration::UrlEscapeString(v46, v74, v67);
      v60 = L"{}={}";
      v61 = 5;
      std::format<std::wstring,std::wstring>(Src);
      std::wstring::append(a2);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v74);
      std::wstring::~wstring(v75);
      if ( (v19 & 8) != 0 )
      {
        v19 &= ~8u;
        v52 = v19;
        std::wstring::~wstring(v68);
      }
      if ( (v19 & 4) != 0 )
      {
        v19 &= ~4u;
        v52 = v19;
        std::wstring::~wstring(v76);
      }
      if ( (v19 & 2) != 0 )
      {
        v19 &= ~2u;
        v52 = v19;
        std::wstring::~wstring(&v64);
      }
      std::wstring::~wstring(&hstringHeader);
      if ( v79 )
        WindowsDeleteString(v79);
      if ( v78 )
        WindowsDeleteString(v78);
      v77[0] = 0;
      v47 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v81 + 64LL))(v81, v77);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v47,
          v52);
      if ( v77[0] )
        v48 = DWORD2(v81) + 1;
      else
        v48 = -1;
      DWORD2(v81) = v48;
    }
    while ( v48 != -1 );
  }
  v49 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
  }
  v50 = v81;
  if ( (_QWORD)v81 )
  {
    *(_QWORD *)&v81 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v60 = L"Device info with applied overrides: {}";
  v61 = 38;
  SystemInterface::Log<std::wstring &>(&v60, a2);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v83 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  if ( v84 )
    (*(void (__fastcall **)(__int64 *))(*v84 + 16))(v84);
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v59);
  return a2;
}

```

## disassembly

```asm
0x18008e3a0  mov     [rsp-8+arg_0], rbx
0x18008e3a5  push    rbp
0x18008e3a6  push    rsi
0x18008e3a7  push    rdi
0x18008e3a8  push    r12
0x18008e3aa  push    r13
0x18008e3ac  push    r14
0x18008e3ae  push    r15
0x18008e3b0  lea     rbp, [rsp-100h]
0x18008e3b8  sub     rsp, 200h
0x18008e3bf  mov     rax, cs:__security_cookie
0x18008e3c6  xor     rax, rsp
0x18008e3c9  mov     [rbp+130h+var_40], rax
0x18008e3d0  mov     r12, r8
0x18008e3d3  mov     r14, rdx
0x18008e3d6  mov     [rbp+130h+var_130], rdx
0x18008e3da  xor     r13d, r13d
0x18008e3dd  mov     [rsp+230h+var_210], r13d; int
0x18008e3e2  xorps   xmm0, xmm0
0x18008e3e5  movdqu  [rbp+130h+var_1B0], xmm0
0x18008e3ea  mov     [rbp+130h+var_1A0], r13
0x18008e3ee  lea     rdx, [rbp+130h+var_1B0]
0x18008e3f2  lea     rcx, [rsp+230h+var_1D0]
0x18008e3f7  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x18008e3fc  nop
0x18008e3fd  lea     rcx, [rbp+130h+var_1B0]
0x18008e401  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x18008e406  mov     [rbp+130h+var_70], r13
0x18008e40d  mov     dword ptr [rsp+230h+hstringHeader.Reserved+8], 1
0x18008e415  mov     dword ptr [rsp+230h+hstringHeader.Reserved+0Ch], 6
0x18008e41d  lea     rax, aWuOs; "+WU_OS"
0x18008e424  mov     [rsp+230h+string], rax
0x18008e429  lea     rax, [rsp+230h+hstringHeader.Reserved+8]
0x18008e42e  mov     qword ptr [rsp+230h+hstringHeader.Reserved], rax
0x18008e433  mov     rbx, [rsp+230h+var_1D0]
0x18008e438  mov     rax, [rbx]
0x18008e43b  lea     rdx, [rsp+230h+hstringHeader.Reserved+8]
0x18008e440  mov     rcx, rbx
0x18008e443  mov     rax, [rax+68h]
0x18008e447  call    _guard_dispatch_icall
0x18008e44c  test    eax, eax
0x18008e44e  js      loc_18008EB7F
0x18008e454  mov     rcx, [rbp+130h+var_70]
0x18008e45b  mov     [rbp+130h+var_70], r13
0x18008e462  test    rcx, rcx
0x18008e465  jz      short loc_18008E474
0x18008e467  mov     rax, [rcx]
0x18008e46a  mov     rax, [rax+10h]
0x18008e46e  call    _guard_dispatch_icall
0x18008e473  nop
0x18008e474  mov     dword ptr [rsp+230h+var_208], 0E2FCC7C1h
0x18008e47c  mov     dword ptr [rsp+230h+var_208+4], 5A0B3BFCh
0x18008e484  mov     [rsp+230h+var_200], 0E772B0B2h
0x18008e48c  mov     [rsp+230h+var_1FC], 7ECBD169h
0x18008e494  mov     rax, [rbx]
0x18008e497  lea     r8, [rbp+130h+var_70]
0x18008e49e  lea     rdx, [rsp+230h+var_208]
0x18008e4a3  mov     rcx, rbx
0x18008e4a6  mov     rax, [rax]
0x18008e4a9  call    _guard_dispatch_icall
0x18008e4ae  nop
0x18008e4af  mov     [rbp+130h+var_48], r13
0x18008e4b6  mov     [rsp+230h+string], r13
0x18008e4bb  lea     r9, [rsp+230h+string]; string
0x18008e4c0  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x18008e4c5  mov     edx, 24h ; '$'; length
0x18008e4ca  lea     rcx, ?RuntimeClass_Windows_System_Profile_AnalyticsInfo@@3QB_WB; "Windows.System.Profile.AnalyticsInfo"
0x18008e4d1  call    cs:__imp_WindowsCreateStringReference
0x18008e4d7  test    eax, eax
0x18008e4d9  js      loc_18008EB87
0x18008e4df  lea     r8, [rbp+130h+var_48]
0x18008e4e6  lea     rdx, _GUID_101704ea_a7f9_46d2_ab94_016865afdb25
0x18008e4ed  mov     rcx, [rsp+230h+string]
0x18008e4f2  call    cs:__imp_RoGetActivationFactory
0x18008e4f8  mov     rcx, [rbp+138h]
0x18008e4ff  test    eax, eax
0x18008e501  js      loc_18008EB8F
0x18008e507  mov     [rbp+130h+var_50], r13
0x18008e50e  mov     rcx, [rbp+130h+var_48]
0x18008e515  mov     rax, [rcx]
0x18008e518  mov     [rbp+130h+var_50], r13
0x18008e51f  lea     r8, [rbp+130h+var_50]
0x18008e526  mov     rdx, [rbp+130h+var_70]
0x18008e52d  mov     rax, [rax+30h]
0x18008e531  call    _guard_dispatch_icall
0x18008e536  mov     rcx, [rbp+138h]; this
0x18008e53d  test    eax, eax
0x18008e53f  js      loc_18008EBA4
0x18008e545  mov     rbx, [rbp+130h+var_50]
0x18008e54c  mov     [rsp+230h+var_1D8], r13
0x18008e551  mov     [rsp+230h+var_210], 10h; int
0x18008e559  mov     rcx, rbx
0x18008e55c  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18008e561  test    eax, eax
0x18008e563  js      short loc_18008E57A
0x18008e565  mov     rax, [rbx]
0x18008e568  lea     rdx, [rsp+230h+var_1D8]
0x18008e56d  mov     rcx, rbx
0x18008e570  mov     rax, [rax+40h]
0x18008e574  call    _guard_dispatch_icall
0x18008e579  nop
0x18008e57a  mov     rcx, [rbp+138h]; this
0x18008e581  test    eax, eax
0x18008e583  js      loc_18008EBB9
0x18008e589  mov     rbx, [rsp+230h+var_1D8]
0x18008e58e  mov     [rsp+230h+var_1D8], r13
0x18008e593  mov     [rsp+230h+var_208], rbx
0x18008e598  xorps   xmm0, xmm0
0x18008e59b  movups  xmmword ptr [r14], xmm0
0x18008e59f  mov     [r14+10h], r13
0x18008e5a3  mov     qword ptr [r14+18h], 7
0x18008e5ab  mov     [r14], r13w
0x18008e5af  mov     [rsp+230h+var_210], 1; int
0x18008e5b7  mov     [rbp+130h+var_78], r13
0x18008e5be  mov     rax, [rbx]
0x18008e5c1  lea     r8, [rbp+130h+var_78]
0x18008e5c8  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18008e5cf  mov     rcx, rbx
0x18008e5d2  mov     rax, [rax]
0x18008e5d5  call    _guard_dispatch_icall
0x18008e5da  mov     rcx, [rbp+138h]; this
0x18008e5e1  test    eax, eax
0x18008e5e3  js      loc_18008EBCE
0x18008e5e9  mov     edi, 21h ; '!'
0x18008e5ee  mov     [rsp+230h+var_210], edi; int
0x18008e5f2  mov     rcx, [rbp+130h+var_78]
0x18008e5f9  mov     [rbp+130h+var_80], rcx
0x18008e600  test    rcx, rcx
0x18008e603  jz      short loc_18008E612
0x18008e605  mov     rax, [rcx]
0x18008e608  mov     rax, [rax+10h]
0x18008e60c  call    _guard_dispatch_icall
0x18008e611  nop
0x18008e612  xorps   xmm0, xmm0
0x18008e615  xor     eax, eax
0x18008e617  movups  [rbp+130h+var_68], xmm0
0x18008e61e  mov     [rbp+130h+var_58], rax
0x18008e625  lea     rdx, [rbp+130h+var_68]
0x18008e62c  lea     rcx, [rbp+130h+var_80]
0x18008e633  call    ?begin@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@Uerr_exception_policy@wil@@@wil@@QEAA?AViterable_iterator@12@XZ; wil::iterable_range<ABI::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::begin(void)
0x18008e638  nop
0x18008e639  xorps   xmm0, xmm0
0x18008e63c  movups  [rbp+130h+var_1B0], xmm0
0x18008e640  mov     qword ptr [rbp+130h+var_1B0], r13
0x18008e644  mov     dword ptr [rbp+130h+var_1B0+8], 0FFFFFFFFh
0x18008e64b  mov     [rbp+130h+var_1A0], r13
0x18008e64f  cmp     dword ptr [rbp+130h+var_68+8], 0FFFFFFFFh
0x18008e656  jz      loc_18008EA5B
0x18008e65c  mov     rsi, qword ptr [rbp+130h+var_68]
0x18008e663  mov     rax, [rsi]
0x18008e666  mov     r15, [rax+30h]
0x18008e66a  mov     rcx, [rbp+130h+var_58]
0x18008e671  test    rcx, rcx
0x18008e674  jz      short loc_18008E68A
0x18008e676  mov     [rbp+130h+var_58], r13
0x18008e67d  mov     rax, [rcx]
0x18008e680  mov     rax, [rax+10h]
0x18008e684  call    _guard_dispatch_icall
0x18008e689  nop
0x18008e68a  lea     rdx, [rbp+130h+var_58]
0x18008e691  mov     rcx, rsi
0x18008e694  mov     rax, r15
0x18008e697  call    _guard_dispatch_icall
0x18008e69c  mov     rcx, [rbp+138h]; this
0x18008e6a3  test    eax, eax
0x18008e6a5  js      loc_18008EB6A
0x18008e6ab  lea     rax, aE; "E:"
0x18008e6b2  lea     rdx, asc_18012418C; "&"
0x18008e6b9  cmp     [r14+10h], r13
0x18008e6bd  cmovz   rdx, rax
0x18008e6c1  or      r15, 0FFFFFFFFFFFFFFFFh
0x18008e6c5  mov     r8, r15
0x18008e6c8  inc     r8
0x18008e6cb  cmp     [rdx+r8*2], r13w
0x18008e6d0  jnz     short loc_18008E6C8
0x18008e6d2  mov     rcx, r14; Src
0x18008e6d5  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18008e6da  mov     [rbp+130h+var_80], r13
0x18008e6e1  mov     rcx, [rbp+130h+var_58]
0x18008e6e8  mov     rax, [rcx]
0x18008e6eb  mov     [rbp+130h+var_80], r13
0x18008e6f2  lea     rdx, [rbp+130h+var_80]
0x18008e6f9  mov     rax, [rax+30h]
0x18008e6fd  call    _guard_dispatch_icall
0x18008e702  mov     rcx, [rbp+138h]; this
0x18008e709  test    eax, eax
0x18008e70b  js      loc_18008EB55
0x18008e711  mov     [rbp+130h+var_78], r13
0x18008e718  mov     rcx, [rbp+130h+var_58]
0x18008e71f  mov     rax, [rcx]
0x18008e722  mov     [rbp+130h+var_78], r13
0x18008e729  lea     rdx, [rbp+130h+var_78]
0x18008e730  mov     rax, [rax+38h]
0x18008e734  call    _guard_dispatch_icall
0x18008e739  mov     rcx, [rbp+138h]; this
0x18008e740  test    eax, eax
0x18008e742  js      loc_18008EC05
0x18008e748  xor     edx, edx; length
0x18008e74a  mov     rcx, [rbp+130h+var_80]; string
0x18008e751  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e757  xorps   xmm0, xmm0
0x18008e75a  movups  xmmword ptr [rsp+230h+hstringHeader.Reserved], xmm0
0x18008e75f  xorps   xmm1, xmm1
0x18008e762  movdqu  xmmword ptr [rsp+48h], xmm1
0x18008e768  mov     r8, r15
0x18008e76b  inc     r8
0x18008e76e  cmp     [rax+r8*2], r13w
0x18008e773  jnz     short loc_18008E76B
0x18008e775  mov     rdx, rax
0x18008e778  lea     rcx, [rsp+230h+hstringHeader]
0x18008e77d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008e782  nop
0x18008e783  lea     rdx, [rsp+230h+hstringHeader]
0x18008e788  cmp     [rsp+230h+string], 7
0x18008e78e  cmova   rdx, qword ptr [rsp+230h+hstringHeader.Reserved]
0x18008e794  mov     r9, 0CBF29CE484222325h
0x18008e79e  mov     rax, qword ptr [rsp+230h+hstringHeader.Reserved+10h]
0x18008e7a3  lea     r8, [rax+rax]
0x18008e7a7  mov     rcx, r13
0x18008e7aa  mov     rsi, 100000001B3h
0x18008e7b4  test    r8, r8
0x18008e7b7  jz      short loc_18008E7CC
0x18008e7b9  movzx   eax, byte ptr [rdx+rcx]
0x18008e7bd  xor     r9, rax
0x18008e7c0  imul    r9, rsi
0x18008e7c4  inc     rcx
0x18008e7c7  cmp     rcx, r8
0x18008e7ca  jb      short loc_18008E7B9
0x18008e7cc  lea     r8, [rsp+230h+hstringHeader]
0x18008e7d1  lea     rdx, [rbp+130h+var_118]
0x18008e7d5  mov     rcx, r12
0x18008e7d8  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18008e7dd  xor     edx, edx; length
0x18008e7df  cmp     [rax+8], r13
0x18008e7e3  jz      loc_18008E894
0x18008e7e9  mov     rcx, [rbp+130h+var_80]; string
0x18008e7f0  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e7f6  xorps   xmm0, xmm0
0x18008e7f9  movups  [rbp+130h+var_198], xmm0
0x18008e7fd  xorps   xmm1, xmm1
0x18008e800  movdqu  [rbp+130h+var_188], xmm1
0x18008e805  mov     r8, r15
0x18008e808  inc     r8
0x18008e80b  cmp     [rax+r8*2], r13w
0x18008e810  jnz     short loc_18008E808
0x18008e812  mov     rdx, rax
0x18008e815  lea     rcx, [rbp+130h+var_198]
0x18008e819  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008e81e  nop
0x18008e81f  or      edi, 2
0x18008e822  mov     [rsp+230h+var_210], edi
0x18008e826  lea     rdx, [rbp+130h+var_198]
0x18008e82a  cmp     qword ptr [rbp+130h+var_188+8], 7
0x18008e82f  cmova   rdx, qword ptr [rbp+130h+var_198]
0x18008e834  mov     r9, 0CBF29CE484222325h
0x18008e83e  mov     rax, qword ptr [rbp+130h+var_188]
0x18008e842  lea     r8, [rax+rax]
0x18008e846  mov     rcx, r13
0x18008e849  test    r8, r8
0x18008e84c  jz      short loc_18008E861
0x18008e84e  movzx   eax, byte ptr [rdx+rcx]
0x18008e852  xor     r9, rax
0x18008e855  imul    r9, rsi
0x18008e859  inc     rcx
0x18008e85c  cmp     rcx, r8
0x18008e85f  jb      short loc_18008E84E
0x18008e861  lea     r8, [rbp+130h+var_198]
0x18008e865  lea     rdx, [rbp+130h+var_128]
0x18008e869  mov     rcx, r12
0x18008e86c  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@NV?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@N@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,double,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,double>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18008e871  mov     rdx, [rbp+130h+var_120]
0x18008e875  test    rdx, rdx
0x18008e878  jz      loc_18008EBE3
0x18008e87e  add     rdx, 30h ; '0'
0x18008e882  lea     rcx, [rbp+130h+var_A8]
0x18008e889  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008e88e  nop
0x18008e88f  or      edi, 4
0x18008e892  jmp     short loc_18008E8D0
0x18008e894  mov     rcx, [rbp+130h+var_78]; string
0x18008e89b  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e8a1  xorps   xmm0, xmm0
0x18008e8a4  movups  [rbp+130h+var_150], xmm0
0x18008e8a8  xorps   xmm1, xmm1
0x18008e8ab  movdqu  [rbp+130h+var_140], xmm1
0x18008e8b0  mov     r8, r15
0x18008e8b3  inc     r8
0x18008e8b6  cmp     [rax+r8*2], r13w
0x18008e8bb  jnz     short loc_18008E8B3
0x18008e8bd  mov     rdx, rax
0x18008e8c0  lea     rcx, [rbp+130h+var_150]
0x18008e8c4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008e8c9  lea     rax, [rbp+130h+var_150]
0x18008e8cd  or      edi, 8
0x18008e8d0  mov     [rsp+230h+var_210], edi
0x18008e8d4  mov     rcx, [rax+10h]
0x18008e8d8  cmp     qword ptr [rax+18h], 7
0x18008e8dd  jbe     short loc_18008E8E2
0x18008e8df  mov     rax, [rax]
0x18008e8e2  mov     [rbp+130h+var_170], rax
  ... truncated ...
```

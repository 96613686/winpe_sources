# Windows::Configuration::GetDeviceInfo(std::unordered_map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> const &)

- ea: `0x14023eb40`
- end: `0x14023f3ba`
- name: `?GetDeviceInfo@Configuration@Windows@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@4@@Z`
- size: `2170`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140028c4c`
- `0x140041318`
- `0x1400413a8`
- `0x140043284`
- `0x1400447ac`
- `0x140044b18`
- `0x140045404`
- `0x1400574cc`
- `0x1400a3d80`
- `0x1400ad7e4`
- `0x140132118`
- `0x14013e2d4`
- `0x14023eb40`
- `0x14023f780`
- `0x14023fdcc`
- `0x14023feb8`
- `0x140240a74`
- `0x140241c8c`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14023ec92`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14023ec92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023eef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023ef90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023f03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023f0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023eef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023ef90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023f03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023f0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023f18d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023f1a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023f18d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023f1a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14023ec71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14023ec71`

## string_xrefs

- `0x14023f30d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x14023f371`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x14023f393`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x14023f2f8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023f332`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023f347`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023f3a8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023f35c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\winrt.h`

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
      std::wstring::_Construct<1,wchar_t const *>(&hstringHeader, StringRawBuffer);
      p_hstringHeader = &hstringHeader;
      if ( *((_QWORD *)&hstringHeader_16 + 1) > 7u )
        p_hstringHeader = (__int128 *)hstringHeader;
      v33 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 2 * (__int64)hstringHeader_16; ++i )
        v33 = 0x100000001B3LL * (*((unsigned __int8 *)p_hstringHeader + i) ^ (unsigned __int64)v33);
      if ( *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
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
        std::wstring::_Construct<1,wchar_t const *>(&v64, v35);
        v37 = v19 | 2;
        v38 = &v64;
        if ( *((_QWORD *)&v65 + 1) > 7u )
          v38 = (__int128 *)v64;
        v39 = 0xCBF29CE484222325uLL;
        for ( j = 0; j < 2 * (__int64)v65; ++j )
          v39 = 0x100000001B3LL * (*((unsigned __int8 *)v38 + j) ^ (unsigned __int64)v39);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
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
        std::wstring::_Construct<1,wchar_t const *>(v68, v42);
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
      std::format<std::wstring const &,std::wstring const &>(Src);
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
  SystemInterface::Log<std::wstring>(&v60, a2);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v83 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  if ( v84 )
    (*(void (__fastcall **)(__int64 *))(*v84 + 16))(v84);
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(v59);
  return a2;
}

```

## disassembly

```asm
0x14023eb40  mov     [rsp-8+arg_0], rbx
0x14023eb45  push    rbp
0x14023eb46  push    rsi
0x14023eb47  push    rdi
0x14023eb48  push    r12
0x14023eb4a  push    r13
0x14023eb4c  push    r14
0x14023eb4e  push    r15
0x14023eb50  lea     rbp, [rsp-100h]
0x14023eb58  sub     rsp, 200h
0x14023eb5f  mov     rax, cs:__security_cookie
0x14023eb66  xor     rax, rsp
0x14023eb69  mov     [rbp+130h+var_40], rax
0x14023eb70  mov     r12, r8
0x14023eb73  mov     r14, rdx
0x14023eb76  mov     [rbp+130h+var_130], rdx
0x14023eb7a  xor     r13d, r13d
0x14023eb7d  mov     [rsp+230h+var_210], r13d; int
0x14023eb82  xorps   xmm0, xmm0
0x14023eb85  movdqu  [rbp+130h+var_1B0], xmm0
0x14023eb8a  mov     [rbp+130h+var_1A0], r13
0x14023eb8e  lea     rdx, [rbp+130h+var_1B0]
0x14023eb92  lea     rcx, [rsp+230h+var_1D0]
0x14023eb97  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x14023eb9c  nop
0x14023eb9d  lea     rcx, [rbp+130h+var_1B0]
0x14023eba1  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x14023eba6  mov     [rbp+130h+var_70], r13
0x14023ebad  mov     dword ptr [rsp+230h+hstringHeader.Reserved+8], 1
0x14023ebb5  mov     dword ptr [rsp+230h+hstringHeader.Reserved+0Ch], 6
0x14023ebbd  lea     rax, aWuOs; "+WU_OS"
0x14023ebc4  mov     [rsp+230h+string], rax
0x14023ebc9  lea     rax, [rsp+230h+hstringHeader.Reserved+8]
0x14023ebce  mov     qword ptr [rsp+230h+hstringHeader.Reserved], rax
0x14023ebd3  mov     rbx, [rsp+230h+var_1D0]
0x14023ebd8  mov     rax, [rbx]
0x14023ebdb  lea     rdx, [rsp+230h+hstringHeader.Reserved+8]
0x14023ebe0  mov     rcx, rbx
0x14023ebe3  mov     rax, [rax+68h]
0x14023ebe7  call    _guard_dispatch_icall
0x14023ebec  test    eax, eax
0x14023ebee  js      loc_14023F31F
0x14023ebf4  mov     rcx, [rbp+130h+var_70]
0x14023ebfb  mov     [rbp+130h+var_70], r13
0x14023ec02  test    rcx, rcx
0x14023ec05  jz      short loc_14023EC14
0x14023ec07  mov     rax, [rcx]
0x14023ec0a  mov     rax, [rax+10h]
0x14023ec0e  call    _guard_dispatch_icall
0x14023ec13  nop
0x14023ec14  mov     dword ptr [rsp+230h+var_208], 0E2FCC7C1h
0x14023ec1c  mov     dword ptr [rsp+230h+var_208+4], 5A0B3BFCh
0x14023ec24  mov     [rsp+230h+var_200], 0E772B0B2h
0x14023ec2c  mov     [rsp+230h+var_1FC], 7ECBD169h
0x14023ec34  mov     rax, [rbx]
0x14023ec37  lea     r8, [rbp+130h+var_70]
0x14023ec3e  lea     rdx, [rsp+230h+var_208]
0x14023ec43  mov     rcx, rbx
0x14023ec46  mov     rax, [rax]
0x14023ec49  call    _guard_dispatch_icall
0x14023ec4e  nop
0x14023ec4f  mov     [rbp+130h+var_48], r13
0x14023ec56  mov     [rsp+230h+string], r13
0x14023ec5b  lea     r9, [rsp+230h+string]; string
0x14023ec60  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x14023ec65  mov     edx, 24h ; '$'; length
0x14023ec6a  lea     rcx, ?RuntimeClass_Windows_System_Profile_AnalyticsInfo@@3QB_WB; "Windows.System.Profile.AnalyticsInfo"
0x14023ec71  call    cs:__imp_WindowsCreateStringReference
0x14023ec77  test    eax, eax
0x14023ec79  js      loc_14023F327
0x14023ec7f  lea     r8, [rbp+130h+var_48]
0x14023ec86  lea     rdx, _GUID_101704ea_a7f9_46d2_ab94_016865afdb25
0x14023ec8d  mov     rcx, [rsp+230h+string]
0x14023ec92  call    cs:__imp_RoGetActivationFactory
0x14023ec98  mov     rcx, [rbp+138h]
0x14023ec9f  test    eax, eax
0x14023eca1  js      loc_14023F32F
0x14023eca7  mov     [rbp+130h+var_50], r13
0x14023ecae  mov     rcx, [rbp+130h+var_48]
0x14023ecb5  mov     rax, [rcx]
0x14023ecb8  mov     [rbp+130h+var_50], r13
0x14023ecbf  lea     r8, [rbp+130h+var_50]
0x14023ecc6  mov     rdx, [rbp+130h+var_70]
0x14023eccd  mov     rax, [rax+30h]
0x14023ecd1  call    _guard_dispatch_icall
0x14023ecd6  mov     rcx, [rbp+138h]; this
0x14023ecdd  test    eax, eax
0x14023ecdf  js      loc_14023F344
0x14023ece5  mov     rbx, [rbp+130h+var_50]
0x14023ecec  mov     [rsp+230h+var_1D8], r13
0x14023ecf1  mov     [rsp+230h+var_210], 10h; int
0x14023ecf9  mov     rcx, rbx
0x14023ecfc  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x14023ed01  test    eax, eax
0x14023ed03  js      short loc_14023ED1A
0x14023ed05  mov     rax, [rbx]
0x14023ed08  lea     rdx, [rsp+230h+var_1D8]
0x14023ed0d  mov     rcx, rbx
0x14023ed10  mov     rax, [rax+40h]
0x14023ed14  call    _guard_dispatch_icall
0x14023ed19  nop
0x14023ed1a  mov     rcx, [rbp+138h]; this
0x14023ed21  test    eax, eax
0x14023ed23  js      loc_14023F359
0x14023ed29  mov     rbx, [rsp+230h+var_1D8]
0x14023ed2e  mov     [rsp+230h+var_1D8], r13
0x14023ed33  mov     [rsp+230h+var_208], rbx
0x14023ed38  xorps   xmm0, xmm0
0x14023ed3b  movups  xmmword ptr [r14], xmm0
0x14023ed3f  mov     [r14+10h], r13
0x14023ed43  mov     qword ptr [r14+18h], 7
0x14023ed4b  mov     [r14], r13w
0x14023ed4f  mov     [rsp+230h+var_210], 1; int
0x14023ed57  mov     [rbp+130h+var_78], r13
0x14023ed5e  mov     rax, [rbx]
0x14023ed61  lea     r8, [rbp+130h+var_78]
0x14023ed68  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x14023ed6f  mov     rcx, rbx
0x14023ed72  mov     rax, [rax]
0x14023ed75  call    _guard_dispatch_icall
0x14023ed7a  mov     rcx, [rbp+138h]; this
0x14023ed81  test    eax, eax
0x14023ed83  js      loc_14023F36E
0x14023ed89  mov     edi, 21h ; '!'
0x14023ed8e  mov     [rsp+230h+var_210], edi; int
0x14023ed92  mov     rcx, [rbp+130h+var_78]
0x14023ed99  mov     [rbp+130h+var_80], rcx
0x14023eda0  test    rcx, rcx
0x14023eda3  jz      short loc_14023EDB2
0x14023eda5  mov     rax, [rcx]
0x14023eda8  mov     rax, [rax+10h]
0x14023edac  call    _guard_dispatch_icall
0x14023edb1  nop
0x14023edb2  xorps   xmm0, xmm0
0x14023edb5  xor     eax, eax
0x14023edb7  movups  [rbp+130h+var_68], xmm0
0x14023edbe  mov     [rbp+130h+var_58], rax
0x14023edc5  lea     rdx, [rbp+130h+var_68]
0x14023edcc  lea     rcx, [rbp+130h+var_80]
0x14023edd3  call    ?begin@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@Uerr_exception_policy@wil@@@wil@@QEAA?AViterable_iterator@12@XZ; wil::iterable_range<ABI::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::begin(void)
0x14023edd8  nop
0x14023edd9  xorps   xmm0, xmm0
0x14023eddc  movups  [rbp+130h+var_1B0], xmm0
0x14023ede0  mov     qword ptr [rbp+130h+var_1B0], r13
0x14023ede4  mov     dword ptr [rbp+130h+var_1B0+8], 0FFFFFFFFh
0x14023edeb  mov     [rbp+130h+var_1A0], r13
0x14023edef  cmp     dword ptr [rbp+130h+var_68+8], 0FFFFFFFFh
0x14023edf6  jz      loc_14023F1FB
0x14023edfc  mov     rsi, qword ptr [rbp+130h+var_68]
0x14023ee03  mov     rax, [rsi]
0x14023ee06  mov     r15, [rax+30h]
0x14023ee0a  mov     rcx, [rbp+130h+var_58]
0x14023ee11  test    rcx, rcx
0x14023ee14  jz      short loc_14023EE2A
0x14023ee16  mov     [rbp+130h+var_58], r13
0x14023ee1d  mov     rax, [rcx]
0x14023ee20  mov     rax, [rax+10h]
0x14023ee24  call    _guard_dispatch_icall
0x14023ee29  nop
0x14023ee2a  lea     rdx, [rbp+130h+var_58]
0x14023ee31  mov     rcx, rsi
0x14023ee34  mov     rax, r15
0x14023ee37  call    _guard_dispatch_icall
0x14023ee3c  mov     rcx, [rbp+138h]; this
0x14023ee43  test    eax, eax
0x14023ee45  js      loc_14023F30A
0x14023ee4b  lea     rax, aE_0; "E:"
0x14023ee52  lea     rdx, asc_14046FFDC; "&"
0x14023ee59  cmp     [r14+10h], r13
0x14023ee5d  cmovz   rdx, rax
0x14023ee61  or      r15, 0FFFFFFFFFFFFFFFFh
0x14023ee65  mov     r8, r15
0x14023ee68  inc     r8
0x14023ee6b  cmp     [rdx+r8*2], r13w
0x14023ee70  jnz     short loc_14023EE68
0x14023ee72  mov     rcx, r14; Src
0x14023ee75  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14023ee7a  mov     [rbp+130h+var_80], r13
0x14023ee81  mov     rcx, [rbp+130h+var_58]
0x14023ee88  mov     rax, [rcx]
0x14023ee8b  mov     [rbp+130h+var_80], r13
0x14023ee92  lea     rdx, [rbp+130h+var_80]
0x14023ee99  mov     rax, [rax+30h]
0x14023ee9d  call    _guard_dispatch_icall
0x14023eea2  mov     rcx, [rbp+138h]; this
0x14023eea9  test    eax, eax
0x14023eeab  js      loc_14023F2F5
0x14023eeb1  mov     [rbp+130h+var_78], r13
0x14023eeb8  mov     rcx, [rbp+130h+var_58]
0x14023eebf  mov     rax, [rcx]
0x14023eec2  mov     [rbp+130h+var_78], r13
0x14023eec9  lea     rdx, [rbp+130h+var_78]
0x14023eed0  mov     rax, [rax+38h]
0x14023eed4  call    _guard_dispatch_icall
0x14023eed9  mov     rcx, [rbp+138h]; this
0x14023eee0  test    eax, eax
0x14023eee2  js      loc_14023F3A5
0x14023eee8  xor     edx, edx; length
0x14023eeea  mov     rcx, [rbp+130h+var_80]; string
0x14023eef1  call    cs:__imp_WindowsGetStringRawBuffer
0x14023eef7  xorps   xmm0, xmm0
0x14023eefa  movups  xmmword ptr [rsp+230h+hstringHeader.Reserved], xmm0
0x14023eeff  xorps   xmm1, xmm1
0x14023ef02  movdqu  xmmword ptr [rsp+48h], xmm1
0x14023ef08  mov     r8, r15
0x14023ef0b  inc     r8
0x14023ef0e  cmp     [rax+r8*2], r13w
0x14023ef13  jnz     short loc_14023EF0B
0x14023ef15  mov     rdx, rax
0x14023ef18  lea     rcx, [rsp+230h+hstringHeader]
0x14023ef1d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14023ef22  nop
0x14023ef23  lea     rdx, [rsp+230h+hstringHeader]
0x14023ef28  cmp     [rsp+230h+string], 7
0x14023ef2e  cmova   rdx, qword ptr [rsp+230h+hstringHeader.Reserved]
0x14023ef34  mov     r9, 0CBF29CE484222325h
0x14023ef3e  mov     rax, qword ptr [rsp+230h+hstringHeader.Reserved+10h]
0x14023ef43  lea     r8, [rax+rax]
0x14023ef47  mov     rcx, r13
0x14023ef4a  mov     rsi, 100000001B3h
0x14023ef54  test    r8, r8
0x14023ef57  jz      short loc_14023EF6C
0x14023ef59  movzx   eax, byte ptr [rdx+rcx]
0x14023ef5d  xor     r9, rax
0x14023ef60  imul    r9, rsi
0x14023ef64  inc     rcx
0x14023ef67  cmp     rcx, r8
0x14023ef6a  jb      short loc_14023EF59
0x14023ef6c  lea     r8, [rsp+230h+hstringHeader]
0x14023ef71  lea     rdx, [rbp+130h+var_118]
0x14023ef75  mov     rcx, r12
0x14023ef78  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14023ef7d  xor     edx, edx; length
0x14023ef7f  cmp     [rax+8], r13
0x14023ef83  jz      loc_14023F034
0x14023ef89  mov     rcx, [rbp+130h+var_80]; string
0x14023ef90  call    cs:__imp_WindowsGetStringRawBuffer
0x14023ef96  xorps   xmm0, xmm0
0x14023ef99  movups  [rbp+130h+var_198], xmm0
0x14023ef9d  xorps   xmm1, xmm1
0x14023efa0  movdqu  [rbp+130h+var_188], xmm1
0x14023efa5  mov     r8, r15
0x14023efa8  inc     r8
0x14023efab  cmp     [rax+r8*2], r13w
0x14023efb0  jnz     short loc_14023EFA8
0x14023efb2  mov     rdx, rax
0x14023efb5  lea     rcx, [rbp+130h+var_198]
0x14023efb9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14023efbe  nop
0x14023efbf  or      edi, 2
0x14023efc2  mov     [rsp+230h+var_210], edi
0x14023efc6  lea     rdx, [rbp+130h+var_198]
0x14023efca  cmp     qword ptr [rbp+130h+var_188+8], 7
0x14023efcf  cmova   rdx, qword ptr [rbp+130h+var_198]
0x14023efd4  mov     r9, 0CBF29CE484222325h
0x14023efde  mov     rax, qword ptr [rbp+130h+var_188]
0x14023efe2  lea     r8, [rax+rax]
0x14023efe6  mov     rcx, r13
0x14023efe9  test    r8, r8
0x14023efec  jz      short loc_14023F001
0x14023efee  movzx   eax, byte ptr [rdx+rcx]
0x14023eff2  xor     r9, rax
0x14023eff5  imul    r9, rsi
0x14023eff9  inc     rcx
0x14023effc  cmp     rcx, r8
0x14023efff  jb      short loc_14023EFEE
0x14023f001  lea     r8, [rbp+130h+var_198]
0x14023f005  lea     rdx, [rbp+130h+var_128]
0x14023f009  mov     rcx, r12
0x14023f00c  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14023f011  mov     rdx, [rbp+130h+var_120]
0x14023f015  test    rdx, rdx
0x14023f018  jz      loc_14023F383
0x14023f01e  add     rdx, 30h ; '0'
0x14023f022  lea     rcx, [rbp+130h+var_A8]
0x14023f029  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14023f02e  nop
0x14023f02f  or      edi, 4
0x14023f032  jmp     short loc_14023F070
0x14023f034  mov     rcx, [rbp+130h+var_78]; string
0x14023f03b  call    cs:__imp_WindowsGetStringRawBuffer
0x14023f041  xorps   xmm0, xmm0
0x14023f044  movups  [rbp+130h+var_150], xmm0
0x14023f048  xorps   xmm1, xmm1
0x14023f04b  movdqu  [rbp+130h+var_140], xmm1
0x14023f050  mov     r8, r15
0x14023f053  inc     r8
0x14023f056  cmp     [rax+r8*2], r13w
0x14023f05b  jnz     short loc_14023F053
0x14023f05d  mov     rdx, rax
0x14023f060  lea     rcx, [rbp+130h+var_150]
0x14023f064  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14023f069  lea     rax, [rbp+130h+var_150]
0x14023f06d  or      edi, 8
0x14023f070  mov     [rsp+230h+var_210], edi
0x14023f074  mov     rcx, [rax+10h]
0x14023f078  cmp     qword ptr [rax+18h], 7
0x14023f07d  jbe     short loc_14023F082
0x14023f07f  mov     rax, [rax]
0x14023f082  mov     [rbp+130h+var_170], rax
  ... truncated ...
```

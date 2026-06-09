# Windows::Configuration::GetDeviceInfo(wil::basic_zstring_view<wchar_t>)

- ea: `0x18008dc80`
- end: `0x18008e396`
- name: `?GetDeviceInfo@Configuration@Windows@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `1814`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18001171c`
- `0x18001c6b4`
- `0x18002e698`
- `0x180037eac`
- `0x180074844`
- `0x180080c18`
- `0x180083510`
- `0x18008dc80`
- `0x18008efe0`
- `0x18008f614`
- `0x18008f6cc`
- `0x18008f8d8`
- `0x180090af0`
- `0x180092dd8`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008dfa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008dfa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008df38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008df71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e1a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008df38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008df71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e1a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008dd8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008dd8d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008ddab`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008ddab`

## string_xrefs

- `0x18008e2a2`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e2b7`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e2dc`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e2f1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e306`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e31b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e330`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e345`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e35a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e36f`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008e384`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
_QWORD *__fastcall Windows::Configuration::GetDeviceInfo(__int64 a1, _QWORD *a2, __int64 a3)
{
  void (__fastcall ***v5)(_QWORD, wchar_t **, __int64 *); // rbx
  int v6; // eax
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v11; // rcx
  int v12; // eax
  __int64 v13; // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // r14d
  int v20; // eax
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rdi
  int v23; // eax
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rdi
  int v26; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v28; // r8
  const wchar_t *v29; // rcx
  char v30; // bl
  __int64 wformat; // rax
  HSTRING_HEADER *p_hstringHeader; // rcx
  PCWSTR v33; // rax
  __int64 v34; // rcx
  PCWSTR v35; // rax
  __int64 v36; // rcx
  int v37; // eax
  int v39; // [rsp+20h] [rbp-E0h]
  wchar_t *S1[2]; // [rsp+28h] [rbp-D8h] BYREF
  size_t N[2]; // [rsp+38h] [rbp-C8h]
  void (__fastcall ***v42)(_QWORD, wchar_t **, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  __int128 v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h]
  const wchar_t *v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  __int64 v49; // [rsp+98h] [rbp-68h]
  const wchar_t *v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  _QWORD v52[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v53[5]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v54[32]; // [rsp+E8h] [rbp-18h] BYREF
  char v55[8]; // [rsp+108h] [rbp+8h] BYREF
  HSTRING v56; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v57; // [rsp+118h] [rbp+18h] BYREF
  __int64 v58; // [rsp+120h] [rbp+20h] BYREF
  __int64 v59; // [rsp+128h] [rbp+28h] BYREF
  __int64 v60; // [rsp+130h] [rbp+30h] BYREF
  int v61; // [rsp+138h] [rbp+38h] BYREF
  __int64 v62; // [rsp+140h] [rbp+40h] BYREF
  __int64 v63; // [rsp+148h] [rbp+48h] BYREF
  __int64 v64; // [rsp+150h] [rbp+50h] BYREF
  __int64 v65; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v53[4] = a2;
  v45 = 0;
  v46 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v42, &v45);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v45);
  v65 = 0;
  *((_QWORD *)&v45 + 1) = 0x600000001LL;
  v47 = L"+WU_OS";
  *(_QWORD *)&v45 = (char *)&v45 + 8;
  v5 = v42;
  v6 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, wchar_t **, __int64 *), char *))(*v42)[13])(
         v42,
         (char *)&v45 + 8);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6);
  S1[0] = (wchar_t *)0x5A0B3BFCE2FCC7C1LL;
  S1[1] = (wchar_t *)0x7ECBD169E772B0B2LL;
  (**v5)(v5, S1, &v65);
  v64 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.System.Profile.AnalyticsInfo", 0x24u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
LABEL_57:
    wil::details::in1diag3::Throw_Hr(
      v11,
      (void *)0xC5,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)ActivationFactory,
      0);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_101704ea_a7f9_46d2_ab94_016865afdb25, &v64);
  v11 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_57;
  v63 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v64 + 48LL))(v64, v65, &v63);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v12,
      0);
  v60 = 0;
  v13 = v63;
  v14 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(v63);
  if ( v14 >= 0 )
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 64LL))(v13, &v60);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v14,
      0);
  v61 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v60 + 56LL))(v60, &v61);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v15,
      0);
  v62 = 0;
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v60)(
          v60,
          &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b,
          &v62);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v16,
      0);
  v58 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v62 + 48LL))(v62, &v58);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v17,
      0);
  v55[0] = 1;
  v18 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 56LL))(v58, v55);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v18,
      0);
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v19 = 1;
  v39 = 1;
  if ( v55[0] )
  {
    std::wstring::operator=(a2, L"E:");
    while ( v55[0] )
    {
      v59 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 48LL))(v58, &v59);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE2,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v20,
          v39);
      v56 = 0;
      v21 = v59;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 48LL);
      WindowsDeleteString(0);
      v56 = 0;
      v23 = v22(v21, &v56);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v23,
          v39);
      v57 = 0;
      v24 = v59;
      v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 56LL);
      WindowsDeleteString(0);
      v57 = 0;
      v26 = v25(v24, &v57);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v26,
          v39);
      if ( !*(_QWORD *)(a3 + 8) )
        goto LABEL_24;
      StringRawBuffer = WindowsGetStringRawBuffer(v56, 0);
      *(_OWORD *)S1 = 0;
      *(_OWORD *)N = 0;
      v28 = -1;
      do
        ++v28;
      while ( StringRawBuffer[v28] );
      std::wstring::_Construct<1,wchar_t const *>(S1);
      v19 |= 2u;
      v39 = v19;
      v29 = (const wchar_t *)S1;
      if ( N[1] > 7 )
        v29 = S1[0];
      if ( N[0] != 9 || (v30 = 1, wmemcmp(v29, L"OSVersion", 9u)) )
LABEL_24:
        v30 = 0;
      if ( (v19 & 2) != 0 )
      {
        v19 &= ~2u;
        v39 = v19;
        std::wstring::~wstring(S1);
      }
      if ( v30 )
      {
        S1[0] = *(wchar_t **)a3;
        wformat = std::make_wformat_args<wchar_t const *>(&v45, S1);
        v48 = 1;
        v49 = wformat;
        v50 = L"OSVersion={}";
        v51 = 12;
        std::vformat<0>(&hstringHeader);
        v19 |= 4u;
        v39 = v19;
        std::wstring::append(a2);
        p_hstringHeader = &hstringHeader;
      }
      else
      {
        v33 = WindowsGetStringRawBuffer(v57, 0);
        v34 = -1;
        do
          ++v34;
        while ( v33[v34] );
        v52[0] = v33;
        v52[1] = v34;
        Windows::Configuration::UrlEscapeString(v34, v54, v52);
        v35 = WindowsGetStringRawBuffer(v56, 0);
        v36 = -1;
        do
          ++v36;
        while ( v35[v36] );
        v53[0] = v35;
        v53[1] = v36;
        Windows::Configuration::UrlEscapeString(v36, S1, v53);
        v53[2] = L"{}={}";
        v53[3] = 5;
        std::format<std::wstring,std::wstring>(&hstringHeader);
        std::wstring::append(a2);
        std::wstring::~wstring(&hstringHeader);
        std::wstring::~wstring(S1);
        p_hstringHeader = (HSTRING_HEADER *)v54;
      }
      std::wstring::~wstring(p_hstringHeader);
      v37 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 64LL))(v58, v55);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v37,
          v39);
      if ( v55[0] )
        std::wstring::append(a2);
      WindowsDeleteString(v57);
      v57 = 0;
      WindowsDeleteString(v56);
      v56 = 0;
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
  }
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  if ( v62 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v63 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v64 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v65 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
  return a2;
}

```

## disassembly

```asm
0x18008dc80  mov     [rsp-8+arg_0], rbx
0x18008dc85  mov     [rsp-8+arg_10], rsi
0x18008dc8a  mov     [rsp-8+arg_18], rdi
0x18008dc8f  push    rbp
0x18008dc90  push    r12
0x18008dc92  push    r13
0x18008dc94  push    r14
0x18008dc96  push    r15
0x18008dc98  lea     rbp, [rsp-70h]
0x18008dc9d  sub     rsp, 170h
0x18008dca4  mov     rax, cs:__security_cookie
0x18008dcab  xor     rax, rsp
0x18008dcae  mov     [rbp+90h+var_30], rax
0x18008dcb2  mov     r15, r8
0x18008dcb5  mov     rsi, rdx
0x18008dcb8  mov     [rbp+90h+var_B0], rdx
0x18008dcbc  xor     r12d, r12d
0x18008dcbf  mov     [rsp+190h+var_170], r12d; int
0x18008dcc4  xorps   xmm0, xmm0
0x18008dcc7  movdqu  [rsp+190h+var_120], xmm0
0x18008dccd  mov     [rbp+90h+var_110], r12
0x18008dcd1  lea     rdx, [rsp+190h+var_120]
0x18008dcd6  lea     rcx, [rsp+190h+var_148]
0x18008dcdb  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x18008dce0  nop
0x18008dce1  lea     rcx, [rsp+190h+var_120]
0x18008dce6  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x18008dceb  mov     [rbp+90h+var_38], r12
0x18008dcef  lea     r13d, [r12+1]
0x18008dcf4  mov     dword ptr [rsp+190h+var_120+8], r13d
0x18008dcf9  mov     dword ptr [rsp+190h+var_120+0Ch], 6
0x18008dd01  lea     rax, aWuOs; "+WU_OS"
0x18008dd08  mov     [rbp+90h+var_108], rax
0x18008dd0c  lea     rax, [rsp+190h+var_120+8]
0x18008dd11  mov     qword ptr [rsp+190h+var_120], rax
0x18008dd16  mov     rbx, [rsp+190h+var_148]
0x18008dd1b  mov     rax, [rbx]
0x18008dd1e  lea     rdx, [rsp+190h+var_120+8]
0x18008dd23  mov     rcx, rbx
0x18008dd26  mov     rax, [rax+68h]
0x18008dd2a  call    _guard_dispatch_icall
0x18008dd2f  test    eax, eax
0x18008dd31  js      loc_18008E2C9
0x18008dd37  mov     dword ptr [rsp+190h+S1], 0E2FCC7C1h
0x18008dd3f  mov     dword ptr [rsp+190h+S1+4], 5A0B3BFCh
0x18008dd47  mov     dword ptr [rsp+190h+S1+8], 0E772B0B2h
0x18008dd4f  mov     dword ptr [rsp+190h+S1+0Ch], 7ECBD169h
0x18008dd57  mov     rax, [rbx]
0x18008dd5a  lea     r8, [rbp+90h+var_38]
0x18008dd5e  lea     rdx, [rsp+190h+S1]
0x18008dd63  mov     rcx, rbx
0x18008dd66  mov     rax, [rax]
0x18008dd69  call    _guard_dispatch_icall
0x18008dd6e  mov     [rbp+90h+var_40], r12
0x18008dd72  mov     [rsp+190h+string], r12
0x18008dd77  lea     r9, [rsp+190h+string]; string
0x18008dd7c  lea     r8, [rsp+190h+hstringHeader]; hstringHeader
0x18008dd81  lea     edx, [r12+24h]; length
0x18008dd86  lea     rcx, ?RuntimeClass_Windows_System_Profile_AnalyticsInfo@@3QB_WB; "Windows.System.Profile.AnalyticsInfo"
0x18008dd8d  call    cs:__imp_WindowsCreateStringReference
0x18008dd93  test    eax, eax
0x18008dd95  js      loc_18008E2D1
0x18008dd9b  lea     r8, [rbp+90h+var_40]
0x18008dd9f  lea     rdx, _GUID_101704ea_a7f9_46d2_ab94_016865afdb25
0x18008dda6  mov     rcx, [rsp+190h+string]
0x18008ddab  call    cs:__imp_RoGetActivationFactory
0x18008ddb1  mov     rcx, [rbp+98h]
0x18008ddb8  test    eax, eax
0x18008ddba  js      loc_18008E2D9
0x18008ddc0  mov     [rbp+90h+var_48], r12
0x18008ddc4  mov     rcx, [rbp+90h+var_40]
0x18008ddc8  mov     rax, [rcx]
0x18008ddcb  lea     r8, [rbp+90h+var_48]
0x18008ddcf  mov     rdx, [rbp+90h+var_38]
0x18008ddd3  mov     rax, [rax+30h]
0x18008ddd7  call    _guard_dispatch_icall
0x18008dddc  mov     rcx, [rbp+98h]; this
0x18008dde3  test    eax, eax
0x18008dde5  js      loc_18008E2EE
0x18008ddeb  mov     [rbp+90h+var_60], r12
0x18008ddef  mov     rbx, [rbp+90h+var_48]
0x18008ddf3  mov     rcx, rbx
0x18008ddf6  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18008ddfb  test    eax, eax
0x18008ddfd  js      short loc_18008DE13
0x18008ddff  mov     rax, [rbx]
0x18008de02  lea     rdx, [rbp+90h+var_60]
0x18008de06  mov     rcx, rbx
0x18008de09  mov     rax, [rax+40h]
0x18008de0d  call    _guard_dispatch_icall
0x18008de12  nop
0x18008de13  mov     rcx, [rbp+98h]; this
0x18008de1a  test    eax, eax
0x18008de1c  js      loc_18008E303
0x18008de22  mov     [rbp+90h+var_58], r12d
0x18008de26  mov     rcx, [rbp+90h+var_60]
0x18008de2a  mov     rax, [rcx]
0x18008de2d  lea     rdx, [rbp+90h+var_58]
0x18008de31  mov     rax, [rax+38h]
0x18008de35  call    _guard_dispatch_icall
0x18008de3a  mov     rcx, [rbp+98h]; this
0x18008de41  test    eax, eax
0x18008de43  js      loc_18008E318
0x18008de49  mov     [rbp+90h+var_50], r12
0x18008de4d  mov     rcx, [rbp+90h+var_60]
0x18008de51  mov     rax, [rcx]
0x18008de54  lea     r8, [rbp+90h+var_50]
0x18008de58  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18008de5f  mov     rax, [rax]
0x18008de62  call    _guard_dispatch_icall
0x18008de67  mov     rcx, [rbp+98h]; this
0x18008de6e  test    eax, eax
0x18008de70  js      loc_18008E32D
0x18008de76  mov     [rbp+90h+var_70], r12
0x18008de7a  mov     rcx, [rbp+90h+var_50]
0x18008de7e  mov     rax, [rcx]
0x18008de81  lea     rdx, [rbp+90h+var_70]
0x18008de85  mov     rax, [rax+30h]
0x18008de89  call    _guard_dispatch_icall
0x18008de8e  mov     rcx, [rbp+98h]; this
0x18008de95  test    eax, eax
0x18008de97  js      loc_18008E342
0x18008de9d  mov     [rbp+90h+var_88], r13b
0x18008dea1  mov     rcx, [rbp+90h+var_70]
0x18008dea5  mov     rax, [rcx]
0x18008dea8  lea     rdx, [rbp+90h+var_88]
0x18008deac  mov     rax, [rax+38h]
0x18008deb0  call    _guard_dispatch_icall
0x18008deb5  mov     rcx, [rbp+98h]; this
0x18008debc  test    eax, eax
0x18008debe  js      loc_18008E357
0x18008dec4  xorps   xmm0, xmm0
0x18008dec7  movups  xmmword ptr [rsi], xmm0
0x18008deca  mov     [rsi+10h], r12
0x18008dece  mov     qword ptr [rsi+18h], 7
0x18008ded6  mov     [rsi], r12w
0x18008deda  mov     r14d, r13d
0x18008dedd  mov     [rsp+190h+var_170], r13d
0x18008dee2  cmp     [rbp+90h+var_88], r12b
0x18008dee6  jz      loc_18008E1E1
0x18008deec  lea     rdx, aE; "E:"
0x18008def3  mov     rcx, rsi; void *
0x18008def6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x18008defb  jmp     loc_18008E1D7
0x18008df00  mov     [rbp+90h+var_68], r12
0x18008df04  mov     rcx, [rbp+90h+var_70]
0x18008df08  mov     rax, [rcx]
0x18008df0b  lea     rdx, [rbp+90h+var_68]
0x18008df0f  mov     rax, [rax+30h]
0x18008df13  call    _guard_dispatch_icall
0x18008df18  mov     rcx, [rbp+98h]; this
0x18008df1f  test    eax, eax
0x18008df21  js      loc_18008E2B4
0x18008df27  mov     [rbp+90h+var_80], r12
0x18008df2b  mov     rbx, [rbp+90h+var_68]
0x18008df2f  mov     rax, [rbx]
0x18008df32  mov     rdi, [rax+30h]
0x18008df36  xor     ecx, ecx; string
0x18008df38  call    cs:__imp_WindowsDeleteString
0x18008df3e  mov     [rbp+90h+var_80], r12
0x18008df42  lea     rdx, [rbp+90h+var_80]
0x18008df46  mov     rcx, rbx
0x18008df49  mov     rax, rdi
0x18008df4c  call    _guard_dispatch_icall
0x18008df51  mov     rcx, [rbp+98h]; this
0x18008df58  test    eax, eax
0x18008df5a  js      loc_18008E29F
0x18008df60  mov     [rbp+90h+var_78], r12
0x18008df64  mov     rbx, [rbp+90h+var_68]
0x18008df68  mov     rax, [rbx]
0x18008df6b  mov     rdi, [rax+38h]
0x18008df6f  xor     ecx, ecx; string
0x18008df71  call    cs:__imp_WindowsDeleteString
0x18008df77  mov     [rbp+90h+var_78], r12
0x18008df7b  lea     rdx, [rbp+90h+var_78]
0x18008df7f  mov     rcx, rbx
0x18008df82  mov     rax, rdi
0x18008df85  call    _guard_dispatch_icall
0x18008df8a  mov     rcx, [rbp+98h]; this
0x18008df91  test    eax, eax
0x18008df93  js      loc_18008E381
0x18008df99  cmp     [r15+8], r12
0x18008df9d  jz      short loc_18008E00F
0x18008df9f  xor     edx, edx; length
0x18008dfa1  mov     rcx, [rbp+90h+var_80]; string
0x18008dfa5  call    cs:__imp_WindowsGetStringRawBuffer
0x18008dfab  xorps   xmm0, xmm0
0x18008dfae  movups  xmmword ptr [rsp+190h+S1], xmm0
0x18008dfb3  xorps   xmm1, xmm1
0x18008dfb6  movdqu  xmmword ptr [rsp+190h+N], xmm1
0x18008dfbc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008dfc0  inc     r8
0x18008dfc3  cmp     [rax+r8*2], r12w
0x18008dfc8  jnz     short loc_18008DFC0
0x18008dfca  mov     rdx, rax
0x18008dfcd  lea     rcx, [rsp+190h+S1]
0x18008dfd2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008dfd7  or      r14d, 2
0x18008dfdb  mov     [rsp+190h+var_170], r14d
0x18008dfe0  mov     r8, [rsp+190h+N]; N
0x18008dfe5  lea     rcx, [rsp+190h+S1]
0x18008dfea  cmp     [rsp+190h+N+8], 7
0x18008dff0  cmova   rcx, [rsp+190h+S1]; S1
0x18008dff6  cmp     r8, 9
0x18008dffa  jnz     short loc_18008E00F
0x18008dffc  lea     rdx, aOsversion; "OSVersion"
0x18008e003  call    wmemcmp
0x18008e008  test    eax, eax
0x18008e00a  mov     bl, r13b
0x18008e00d  jz      short loc_18008E012
0x18008e00f  mov     bl, r12b
0x18008e012  test    r14b, 2
0x18008e016  jz      short loc_18008E02B
0x18008e018  and     r14d, 0FFFFFFFDh
0x18008e01c  mov     [rsp+190h+var_170], r14d; int
0x18008e021  lea     rcx, [rsp+190h+S1]; void *
0x18008e026  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e02b  test    bl, bl
0x18008e02d  jz      short loc_18008E0A5
0x18008e02f  mov     rax, [r15]
0x18008e032  mov     [rsp+190h+S1], rax
0x18008e037  lea     rdx, [rsp+190h+S1]
0x18008e03c  lea     rcx, [rsp+190h+var_120]
0x18008e041  call    ??$make_wformat_args@PEB_W@std@@YA?A_PAEAPEB_W@Z
0x18008e046  mov     [rbp+90h+var_100], r13
0x18008e04a  mov     [rbp+90h+var_F8], rax
0x18008e04e  lea     rax, aOsversion_0; "OSVersion={}"
0x18008e055  mov     [rbp+90h+var_F0], rax
0x18008e059  mov     [rbp+90h+var_E8], 0Ch
0x18008e061  lea     r8, [rbp+90h+var_100]
0x18008e065  lea     rdx, [rbp+90h+var_F0]
0x18008e069  lea     rcx, [rsp+190h+hstringHeader]; Src
0x18008e06e  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18008e073  or      r14d, 4
0x18008e077  mov     [rsp+190h+var_170], r14d
0x18008e07c  lea     rdx, [rsp+190h+hstringHeader]
0x18008e081  cmp     [rsp+190h+string], 7
0x18008e087  cmova   rdx, qword ptr [rsp+190h+hstringHeader.Reserved]
0x18008e08d  mov     r8, qword ptr [rsp+190h+hstringHeader.Reserved+10h]
0x18008e092  mov     rcx, rsi; Src
0x18008e095  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18008e09a  nop
0x18008e09b  lea     rcx, [rsp+190h+hstringHeader]
0x18008e0a0  jmp     loc_18008E164
0x18008e0a5  xor     edx, edx; length
0x18008e0a7  mov     rcx, [rbp+90h+var_78]; string
0x18008e0ab  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e0b1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008e0b5  inc     rcx
0x18008e0b8  cmp     [rax+rcx*2], r12w
0x18008e0bd  jnz     short loc_18008E0B5
0x18008e0bf  mov     [rbp+90h+var_E0], rax
0x18008e0c3  mov     [rbp+90h+var_D8], rcx
0x18008e0c7  lea     r8, [rbp+90h+var_E0]
0x18008e0cb  lea     rdx, [rbp+90h+var_A8]
0x18008e0cf  call    ?UrlEscapeString@Configuration@Windows@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Configuration::UrlEscapeString(wil::basic_zstring_view<wchar_t>)
0x18008e0d4  mov     rbx, rax
0x18008e0d7  xor     edx, edx; length
0x18008e0d9  mov     rcx, [rbp+90h+var_80]; string
0x18008e0dd  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e0e3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008e0e7  inc     rcx
0x18008e0ea  cmp     [rax+rcx*2], r12w
0x18008e0ef  jnz     short loc_18008E0E7
0x18008e0f1  mov     [rbp+90h+var_D0], rax
0x18008e0f5  mov     [rbp+90h+var_C8], rcx
0x18008e0f9  lea     r8, [rbp+90h+var_D0]
0x18008e0fd  lea     rdx, [rsp+190h+S1]
0x18008e102  call    ?UrlEscapeString@Configuration@Windows@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Configuration::UrlEscapeString(wil::basic_zstring_view<wchar_t>)
0x18008e107  nop
0x18008e108  lea     rcx, asc_180124180; "{}={}"
0x18008e10f  mov     [rbp+90h+var_C0], rcx
0x18008e113  mov     [rbp+90h+var_B8], 5
0x18008e11b  mov     r9, rbx
0x18008e11e  mov     r8, rax
0x18008e121  lea     rdx, [rbp+90h+var_C0]
0x18008e125  lea     rcx, [rsp+190h+hstringHeader]; Src
0x18008e12a  call    ??$format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@0@$$QEAV10@1@Z; std::format<std::wstring,std::wstring>(std::basic_format_string<wchar_t,std::wstring,std::wstring>,std::wstring &&,std::wstring &&)
0x18008e12f  nop
0x18008e130  mov     r8, [rax+10h]
0x18008e134  cmp     qword ptr [rax+18h], 7
0x18008e139  jbe     short loc_18008E13E
0x18008e13b  mov     rax, [rax]
0x18008e13e  mov     rdx, rax
0x18008e141  mov     rcx, rsi; Src
0x18008e144  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18008e149  nop
0x18008e14a  lea     rcx, [rsp+190h+hstringHeader]; void *
0x18008e14f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e154  nop
0x18008e155  lea     rcx, [rsp+190h+S1]; void *
0x18008e15a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e15f  nop
0x18008e160  lea     rcx, [rbp+90h+var_A8]; void *
0x18008e164  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e169  mov     rcx, [rbp+90h+var_70]
0x18008e16d  mov     rax, [rcx]
0x18008e170  lea     rdx, [rbp+90h+var_88]
0x18008e174  mov     rax, [rax+40h]
0x18008e178  call    _guard_dispatch_icall
  ... truncated ...
```

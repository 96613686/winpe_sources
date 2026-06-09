# Windows::Configuration::GetDeviceInfo(wil::basic_zstring_view<wchar_t>)

- ea: `0x14023e440`
- end: `0x14023eb2c`
- name: `?GetDeviceInfo@Configuration@Windows@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `1772`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140041318`
- `0x1400413a8`
- `0x140043284`
- `0x140044b18`
- `0x140045404`
- `0x1400454a0`
- `0x140053618`
- `0x1400a3d80`
- `0x140132118`
- `0x14013e2d4`
- `0x1401e559c`
- `0x14023e440`
- `0x14023f780`
- `0x14023fdcc`
- `0x140240a74`
- `0x140241c8c`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14023e565`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14023e565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023e762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023e842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023e874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023e762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023e842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14023e874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e6f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e72e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e6f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e72e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14023e952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14023e547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14023e547`

## string_xrefs

- `0x14023ea38`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023ea4d`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023ea72`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023ea87`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023ea9c`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023eab1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023eac6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023eadb`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023eaf0`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023eb05`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x14023eb1a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`

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
  _BYTE *v31; // rcx
  PCWSTR v32; // rax
  __int64 v33; // rcx
  PCWSTR v34; // rax
  __int64 v35; // rcx
  int v36; // eax
  int v38; // [rsp+20h] [rbp-E0h]
  wchar_t *S1[2]; // [rsp+28h] [rbp-D8h] BYREF
  size_t N[3]; // [rsp+38h] [rbp-C8h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v43[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v44[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v45[3]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Src[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v47[32]; // [rsp+D8h] [rbp-28h] BYREF
  char v48[8]; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING v49; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v50; // [rsp+108h] [rbp+8h] BYREF
  __int64 v51; // [rsp+110h] [rbp+10h] BYREF
  __int64 v52; // [rsp+118h] [rbp+18h] BYREF
  __int64 v53; // [rsp+120h] [rbp+20h] BYREF
  int v54; // [rsp+128h] [rbp+28h] BYREF
  __int64 v55; // [rsp+130h] [rbp+30h] BYREF
  __int64 v56; // [rsp+138h] [rbp+38h] BYREF
  __int64 v57; // [rsp+140h] [rbp+40h] BYREF
  __int64 v58; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v45[2] = a2;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(v43, &hstringHeader);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&hstringHeader);
  v58 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0x600000001LL;
  string = (HSTRING)L"+WU_OS";
  hstringHeader.Reserved.Reserved1 = &hstringHeader.Reserved.Reserved2[8];
  v5 = (void (__fastcall ***)(_QWORD, wchar_t **, __int64 *))v43[0];
  v6 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v43[0] + 104LL))(
         v43[0],
         &hstringHeader.Reserved.Reserved2[8]);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6);
  S1[0] = (wchar_t *)0x5A0B3BFCE2FCC7C1LL;
  S1[1] = (wchar_t *)0x7ECBD169E772B0B2LL;
  (**v5)(v5, S1, &v58);
  v57 = 0;
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
  ActivationFactory = RoGetActivationFactory(string, &GUID_101704ea_a7f9_46d2_ab94_016865afdb25, &v57);
  v11 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_57;
  v56 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v57 + 48LL))(v57, v58, &v56);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v12,
      0);
  v53 = 0;
  v13 = v56;
  v14 = wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(v56);
  if ( v14 >= 0 )
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 64LL))(v13, &v53);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v14,
      0);
  v54 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 56LL))(v53, &v54);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v15,
      0);
  v55 = 0;
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v53)(
          v53,
          &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b,
          &v55);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v16,
      0);
  v51 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 48LL))(v55, &v51);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      (const char *)(unsigned int)v17,
      0);
  v48[0] = 1;
  v18 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v51 + 56LL))(v51, v48);
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
  v38 = 1;
  if ( v48[0] )
  {
    std::wstring::operator=(a2, L"E:");
    while ( v48[0] )
    {
      v52 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 48LL))(v51, &v52);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE2,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v20,
          v38);
      v49 = 0;
      v21 = v52;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 48LL);
      WindowsDeleteString(0);
      v49 = 0;
      v23 = v22(v21, &v49);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v23,
          v38);
      v50 = 0;
      v24 = v52;
      v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 56LL);
      WindowsDeleteString(0);
      v50 = 0;
      v26 = v25(v24, &v50);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v26,
          v38);
      if ( !*(_QWORD *)(a3 + 8) )
        goto LABEL_24;
      StringRawBuffer = WindowsGetStringRawBuffer(v49, 0);
      *(_OWORD *)S1 = 0;
      *(_OWORD *)N = 0;
      v28 = -1;
      do
        ++v28;
      while ( StringRawBuffer[v28] );
      std::wstring::_Construct<1,wchar_t const *>(S1, StringRawBuffer, v28);
      v19 |= 2u;
      v38 = v19;
      v29 = (const wchar_t *)S1;
      if ( N[1] > 7 )
        v29 = S1[0];
      if ( N[0] != 9 || (v30 = 1, wmemcmp(v29, L"OSVersion", 9u)) )
LABEL_24:
        v30 = 0;
      if ( (v19 & 2) != 0 )
      {
        v19 &= ~2u;
        v38 = v19;
        std::wstring::~wstring(S1);
      }
      if ( v30 )
      {
        S1[0] = *(wchar_t **)a3;
        v43[2] = L"OSVersion={}";
        v43[3] = 12;
        std::format<wchar_t const *>(Src);
        std::wstring::append(a2);
        v31 = Src;
      }
      else
      {
        v32 = WindowsGetStringRawBuffer(v50, 0);
        v33 = -1;
        do
          ++v33;
        while ( v32[v33] );
        v44[0] = v32;
        v44[1] = v33;
        Windows::Configuration::UrlEscapeString(v33, v47, v44);
        v34 = WindowsGetStringRawBuffer(v49, 0);
        v35 = -1;
        do
          ++v35;
        while ( v34[v35] );
        v45[0] = v34;
        v45[1] = v35;
        Windows::Configuration::UrlEscapeString(v35, S1, v45);
        hstringHeader.Reserved.Reserved1 = L"{}={}";
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 5;
        std::format<std::wstring const &,std::wstring const &>(Src);
        std::wstring::append(a2);
        std::wstring::~wstring(Src);
        std::wstring::~wstring(S1);
        v31 = v47;
      }
      std::wstring::~wstring(v31);
      v36 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v51 + 64LL))(v51, v48);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
          (const char *)(unsigned int)v36,
          v38);
      if ( v48[0] )
        std::wstring::append(a2);
      WindowsDeleteString(v50);
      v50 = 0;
      WindowsDeleteString(v49);
      v49 = 0;
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
  }
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(v43);
  return a2;
}

```

## disassembly

```asm
0x14023e440  mov     [rsp-8+arg_0], rbx
0x14023e445  mov     [rsp-8+arg_18], rsi
0x14023e44a  push    rbp
0x14023e44b  push    rdi
0x14023e44c  push    r12
0x14023e44e  push    r14
0x14023e450  push    r15
0x14023e452  lea     rbp, [rsp-60h]
0x14023e457  sub     rsp, 160h
0x14023e45e  mov     rax, cs:__security_cookie
0x14023e465  xor     rax, rsp
0x14023e468  mov     [rbp+80h+var_30], rax
0x14023e46c  mov     r15, r8
0x14023e46f  mov     rsi, rdx
0x14023e472  mov     [rbp+80h+var_D0], rdx
0x14023e476  xor     r12d, r12d
0x14023e479  mov     [rsp+180h+var_160], r12d; int
0x14023e47e  xorps   xmm0, xmm0
0x14023e481  movdqu  xmmword ptr [rsp+180h+hstringHeader.Reserved], xmm0
0x14023e487  mov     qword ptr [rsp+180h+hstringHeader.Reserved+10h], r12
0x14023e48c  lea     rdx, [rsp+180h+hstringHeader]
0x14023e491  lea     rcx, [rsp+180h+var_110]
0x14023e496  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x14023e49b  nop
0x14023e49c  lea     rcx, [rsp+180h+hstringHeader]
0x14023e4a1  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x14023e4a6  mov     [rbp+80h+var_38], r12
0x14023e4aa  mov     dword ptr [rsp+180h+hstringHeader.Reserved+8], 1
0x14023e4b2  mov     dword ptr [rsp+180h+hstringHeader.Reserved+0Ch], 6
0x14023e4ba  lea     rax, aWuOs; "+WU_OS"
0x14023e4c1  mov     [rsp+180h+string], rax
0x14023e4c6  lea     rax, [rsp+180h+hstringHeader.Reserved+8]
0x14023e4cb  mov     qword ptr [rsp+180h+hstringHeader.Reserved], rax
0x14023e4d0  mov     rbx, [rsp+180h+var_110]
0x14023e4d5  mov     rax, [rbx]
0x14023e4d8  lea     rdx, [rsp+180h+hstringHeader.Reserved+8]
0x14023e4dd  mov     rcx, rbx
0x14023e4e0  mov     rax, [rax+68h]
0x14023e4e4  call    _guard_dispatch_icall
0x14023e4e9  test    eax, eax
0x14023e4eb  js      loc_14023EA5F
0x14023e4f1  mov     dword ptr [rsp+180h+S1], 0E2FCC7C1h
0x14023e4f9  mov     dword ptr [rsp+180h+S1+4], 5A0B3BFCh
0x14023e501  mov     dword ptr [rsp+180h+S1+8], 0E772B0B2h
0x14023e509  mov     dword ptr [rsp+180h+S1+0Ch], 7ECBD169h
0x14023e511  mov     rax, [rbx]
0x14023e514  lea     r8, [rbp+80h+var_38]
0x14023e518  lea     rdx, [rsp+180h+S1]
0x14023e51d  mov     rcx, rbx
0x14023e520  mov     rax, [rax]
0x14023e523  call    _guard_dispatch_icall
0x14023e528  mov     [rbp+80h+var_40], r12
0x14023e52c  mov     [rsp+180h+string], r12
0x14023e531  lea     r9, [rsp+180h+string]; string
0x14023e536  lea     r8, [rsp+180h+hstringHeader]; hstringHeader
0x14023e53b  lea     edx, [r12+24h]; length
0x14023e540  lea     rcx, ?RuntimeClass_Windows_System_Profile_AnalyticsInfo@@3QB_WB; "Windows.System.Profile.AnalyticsInfo"
0x14023e547  call    cs:__imp_WindowsCreateStringReference
0x14023e54d  test    eax, eax
0x14023e54f  js      loc_14023EA67
0x14023e555  lea     r8, [rbp+80h+var_40]
0x14023e559  lea     rdx, _GUID_101704ea_a7f9_46d2_ab94_016865afdb25
0x14023e560  mov     rcx, [rsp+180h+string]
0x14023e565  call    cs:__imp_RoGetActivationFactory
0x14023e56b  mov     rcx, [rbp+88h]
0x14023e572  test    eax, eax
0x14023e574  js      loc_14023EA6F
0x14023e57a  mov     [rbp+80h+var_48], r12
0x14023e57e  mov     rcx, [rbp+80h+var_40]
0x14023e582  mov     rax, [rcx]
0x14023e585  lea     r8, [rbp+80h+var_48]
0x14023e589  mov     rdx, [rbp+80h+var_38]
0x14023e58d  mov     rax, [rax+30h]
0x14023e591  call    _guard_dispatch_icall
0x14023e596  mov     rcx, [rbp+88h]; this
0x14023e59d  test    eax, eax
0x14023e59f  js      loc_14023EA84
0x14023e5a5  mov     [rbp+80h+var_60], r12
0x14023e5a9  mov     rbx, [rbp+80h+var_48]
0x14023e5ad  mov     rcx, rbx
0x14023e5b0  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x14023e5b5  test    eax, eax
0x14023e5b7  js      short loc_14023E5CD
0x14023e5b9  mov     rax, [rbx]
0x14023e5bc  lea     rdx, [rbp+80h+var_60]
0x14023e5c0  mov     rcx, rbx
0x14023e5c3  mov     rax, [rax+40h]
0x14023e5c7  call    _guard_dispatch_icall
0x14023e5cc  nop
0x14023e5cd  mov     rcx, [rbp+88h]; this
0x14023e5d4  test    eax, eax
0x14023e5d6  js      loc_14023EA99
0x14023e5dc  mov     [rbp+80h+var_58], r12d
0x14023e5e0  mov     rcx, [rbp+80h+var_60]
0x14023e5e4  mov     rax, [rcx]
0x14023e5e7  lea     rdx, [rbp+80h+var_58]
0x14023e5eb  mov     rax, [rax+38h]
0x14023e5ef  call    _guard_dispatch_icall
0x14023e5f4  mov     rcx, [rbp+88h]; this
0x14023e5fb  test    eax, eax
0x14023e5fd  js      loc_14023EAAE
0x14023e603  mov     [rbp+80h+var_50], r12
0x14023e607  mov     rcx, [rbp+80h+var_60]
0x14023e60b  mov     rax, [rcx]
0x14023e60e  lea     r8, [rbp+80h+var_50]
0x14023e612  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x14023e619  mov     rax, [rax]
0x14023e61c  call    _guard_dispatch_icall
0x14023e621  mov     rcx, [rbp+88h]; this
0x14023e628  test    eax, eax
0x14023e62a  js      loc_14023EAC3
0x14023e630  mov     [rbp+80h+var_70], r12
0x14023e634  mov     rcx, [rbp+80h+var_50]
0x14023e638  mov     rax, [rcx]
0x14023e63b  lea     rdx, [rbp+80h+var_70]
0x14023e63f  mov     rax, [rax+30h]
0x14023e643  call    _guard_dispatch_icall
0x14023e648  mov     rcx, [rbp+88h]; this
0x14023e64f  test    eax, eax
0x14023e651  js      loc_14023EAD8
0x14023e657  mov     [rbp+80h+var_88], 1
0x14023e65b  mov     rcx, [rbp+80h+var_70]
0x14023e65f  mov     rax, [rcx]
0x14023e662  lea     rdx, [rbp+80h+var_88]
0x14023e666  mov     rax, [rax+38h]
0x14023e66a  call    _guard_dispatch_icall
0x14023e66f  mov     rcx, [rbp+88h]; this
0x14023e676  test    eax, eax
0x14023e678  js      loc_14023EAED
0x14023e67e  xorps   xmm0, xmm0
0x14023e681  movups  xmmword ptr [rsi], xmm0
0x14023e684  mov     [rsi+10h], r12
0x14023e688  mov     qword ptr [rsi+18h], 7
0x14023e690  mov     [rsi], r12w
0x14023e694  mov     r14d, 1
0x14023e69a  mov     [rsp+180h+var_160], r14d
0x14023e69f  cmp     [rbp+80h+var_88], r12b
0x14023e6a3  jz      loc_14023E97C
0x14023e6a9  lea     rdx, aE_0; "E:"
0x14023e6b0  mov     rcx, rsi; void *
0x14023e6b3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x14023e6b8  jmp     loc_14023E972
0x14023e6bd  mov     [rbp+80h+var_68], r12
0x14023e6c1  mov     rcx, [rbp+80h+var_70]
0x14023e6c5  mov     rax, [rcx]
0x14023e6c8  lea     rdx, [rbp+80h+var_68]
0x14023e6cc  mov     rax, [rax+30h]
0x14023e6d0  call    _guard_dispatch_icall
0x14023e6d5  mov     rcx, [rbp+88h]; this
0x14023e6dc  test    eax, eax
0x14023e6de  js      loc_14023EA4A
0x14023e6e4  mov     [rbp+80h+var_80], r12
0x14023e6e8  mov     rbx, [rbp+80h+var_68]
0x14023e6ec  mov     rax, [rbx]
0x14023e6ef  mov     rdi, [rax+30h]
0x14023e6f3  xor     ecx, ecx; string
0x14023e6f5  call    cs:__imp_WindowsDeleteString
0x14023e6fb  mov     [rbp+80h+var_80], r12
0x14023e6ff  lea     rdx, [rbp+80h+var_80]
0x14023e703  mov     rcx, rbx
0x14023e706  mov     rax, rdi
0x14023e709  call    _guard_dispatch_icall
0x14023e70e  mov     rcx, [rbp+88h]; this
0x14023e715  test    eax, eax
0x14023e717  js      loc_14023EA35
0x14023e71d  mov     [rbp+80h+var_78], r12
0x14023e721  mov     rbx, [rbp+80h+var_68]
0x14023e725  mov     rax, [rbx]
0x14023e728  mov     rdi, [rax+38h]
0x14023e72c  xor     ecx, ecx; string
0x14023e72e  call    cs:__imp_WindowsDeleteString
0x14023e734  mov     [rbp+80h+var_78], r12
0x14023e738  lea     rdx, [rbp+80h+var_78]
0x14023e73c  mov     rcx, rbx
0x14023e73f  mov     rax, rdi
0x14023e742  call    _guard_dispatch_icall
0x14023e747  mov     rcx, [rbp+88h]; this
0x14023e74e  test    eax, eax
0x14023e750  js      loc_14023EB17
0x14023e756  cmp     [r15+8], r12
0x14023e75a  jz      short loc_14023E7CB
0x14023e75c  xor     edx, edx; length
0x14023e75e  mov     rcx, [rbp+80h+var_80]; string
0x14023e762  call    cs:__imp_WindowsGetStringRawBuffer
0x14023e768  xorps   xmm0, xmm0
0x14023e76b  movups  xmmword ptr [rsp+180h+S1], xmm0
0x14023e770  xorps   xmm1, xmm1
0x14023e773  movdqu  xmmword ptr [rsp+180h+N], xmm1
0x14023e779  or      r8, 0FFFFFFFFFFFFFFFFh
0x14023e77d  inc     r8
0x14023e780  cmp     [rax+r8*2], r12w
0x14023e785  jnz     short loc_14023E77D
0x14023e787  mov     rdx, rax
0x14023e78a  lea     rcx, [rsp+180h+S1]
0x14023e78f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14023e794  or      r14d, 2
0x14023e798  mov     [rsp+180h+var_160], r14d
0x14023e79d  mov     r8, [rsp+180h+N]; N
0x14023e7a2  lea     rcx, [rsp+180h+S1]
0x14023e7a7  cmp     [rsp+180h+N+8], 7
0x14023e7ad  cmova   rcx, [rsp+180h+S1]; S1
0x14023e7b3  cmp     r8, 9
0x14023e7b7  jnz     short loc_14023E7CB
0x14023e7b9  lea     rdx, aOsversion; "OSVersion"
0x14023e7c0  call    wmemcmp
0x14023e7c5  test    eax, eax
0x14023e7c7  mov     bl, 1
0x14023e7c9  jz      short loc_14023E7CE
0x14023e7cb  mov     bl, r12b
0x14023e7ce  test    r14b, 2
0x14023e7d2  jz      short loc_14023E7E7
0x14023e7d4  and     r14d, 0FFFFFFFDh
0x14023e7d8  mov     [rsp+180h+var_160], r14d; int
0x14023e7dd  lea     rcx, [rsp+180h+S1]
0x14023e7e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14023e7e7  test    bl, bl
0x14023e7e9  jz      short loc_14023E83C
0x14023e7eb  mov     rax, [r15]
0x14023e7ee  mov     [rsp+180h+S1], rax
0x14023e7f3  lea     rax, aOsversion_2; "OSVersion={}"
0x14023e7fa  mov     [rbp+80h+var_100], rax
0x14023e7fe  mov     [rbp+80h+var_F8], 0Ch
0x14023e806  lea     r8, [rsp+180h+S1]
0x14023e80b  lea     rdx, [rbp+80h+var_100]
0x14023e80f  lea     rcx, [rbp+80h+Src]; Src
0x14023e813  call    ??$format@PEB_W@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WPEB_W@0@$$QEAPEB_W@Z; std::format<wchar_t const *>(std::basic_format_string<wchar_t,wchar_t const *>,wchar_t const * &&)
0x14023e818  nop
0x14023e819  mov     r8, [rax+10h]
0x14023e81d  cmp     qword ptr [rax+18h], 7
0x14023e822  jbe     short loc_14023E827
0x14023e824  mov     rax, [rax]
0x14023e827  mov     rdx, rax
0x14023e82a  mov     rcx, rsi; Src
0x14023e82d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14023e832  nop
0x14023e833  lea     rcx, [rbp+80h+Src]
0x14023e837  jmp     loc_14023E8FC
0x14023e83c  xor     edx, edx; length
0x14023e83e  mov     rcx, [rbp+80h+var_78]; string
0x14023e842  call    cs:__imp_WindowsGetStringRawBuffer
0x14023e848  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14023e84c  inc     rcx
0x14023e84f  cmp     [rax+rcx*2], r12w
0x14023e854  jnz     short loc_14023E84C
0x14023e856  mov     [rbp+80h+var_F0], rax
0x14023e85a  mov     [rbp+80h+var_E8], rcx
0x14023e85e  lea     r8, [rbp+80h+var_F0]
0x14023e862  lea     rdx, [rbp+80h+var_A8]
0x14023e866  call    ?UrlEscapeString@Configuration@Windows@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Configuration::UrlEscapeString(wil::basic_zstring_view<wchar_t>)
0x14023e86b  mov     rbx, rax
0x14023e86e  xor     edx, edx; length
0x14023e870  mov     rcx, [rbp+80h+var_80]; string
0x14023e874  call    cs:__imp_WindowsGetStringRawBuffer
0x14023e87a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14023e87e  inc     rcx
0x14023e881  cmp     [rax+rcx*2], r12w
0x14023e886  jnz     short loc_14023E87E
0x14023e888  mov     [rbp+80h+var_E0], rax
0x14023e88c  mov     [rbp+80h+var_D8], rcx
0x14023e890  lea     r8, [rbp+80h+var_E0]
0x14023e894  lea     rdx, [rsp+180h+S1]
0x14023e899  call    ?UrlEscapeString@Configuration@Windows@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Configuration::UrlEscapeString(wil::basic_zstring_view<wchar_t>)
0x14023e89e  nop
0x14023e89f  lea     rcx, asc_14046FFD0; "{}={}"
0x14023e8a6  mov     qword ptr [rsp+180h+hstringHeader.Reserved], rcx
0x14023e8ab  mov     qword ptr [rsp+180h+hstringHeader.Reserved+8], 5
0x14023e8b4  mov     r9, rbx
0x14023e8b7  mov     r8, rax
0x14023e8ba  lea     rdx, [rsp+180h+hstringHeader]
0x14023e8bf  lea     rcx, [rbp+80h+Src]; Src
0x14023e8c3  call    ??$format@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV12@@0@AEBV10@1@Z; std::format<std::wstring const &,std::wstring const &>(std::basic_format_string<wchar_t,std::wstring const &,std::wstring const &>,std::wstring const &,std::wstring const &)
0x14023e8c8  nop
0x14023e8c9  mov     r8, [rax+10h]
0x14023e8cd  cmp     qword ptr [rax+18h], 7
0x14023e8d2  jbe     short loc_14023E8D7
0x14023e8d4  mov     rax, [rax]
0x14023e8d7  mov     rdx, rax
0x14023e8da  mov     rcx, rsi; Src
0x14023e8dd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x14023e8e2  nop
0x14023e8e3  lea     rcx, [rbp+80h+Src]
0x14023e8e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14023e8ec  nop
0x14023e8ed  lea     rcx, [rsp+180h+S1]
0x14023e8f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14023e8f7  nop
0x14023e8f8  lea     rcx, [rbp+80h+var_A8]
0x14023e8fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14023e901  mov     rcx, [rbp+80h+var_70]
0x14023e905  mov     rax, [rcx]
0x14023e908  lea     rdx, [rbp+80h+var_88]
0x14023e90c  mov     rax, [rax+40h]
0x14023e910  call    _guard_dispatch_icall
0x14023e915  mov     rcx, [rbp+88h]; this
0x14023e91c  test    eax, eax
0x14023e91e  js      loc_14023EB02
0x14023e924  cmp     [rbp+80h+var_88], r12b
0x14023e928  jz      short loc_14023E940
0x14023e92a  mov     r8d, 1
0x14023e930  lea     rdx, asc_14046FFDC; "&"
  ... truncated ...
```

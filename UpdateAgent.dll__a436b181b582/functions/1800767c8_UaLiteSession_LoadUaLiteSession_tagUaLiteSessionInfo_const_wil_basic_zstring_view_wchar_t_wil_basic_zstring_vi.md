# UaLiteSession::LoadUaLiteSession(tagUaLiteSessionInfo const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x1800767c8`
- end: `0x180076e5a`
- name: `?LoadUaLiteSession@UaLiteSession@@CA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$com_ptr_t@UIDeploymentSession@@Uerr_exception_policy@wil@@@2@@std@@AEBUtagUaLiteSessionInfo@@V?$basic_zstring_view@_W@wil@@11@Z`
- size: `1682`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180021d0c`

## callees

- `0x1800059d0`
- `0x180008ed8`
- `0x180008ef0`
- `0x1800098b4`
- `0x180009934`
- `0x180009960`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x18000dd74`
- `0x18000e010`
- `0x18001031c`
- `0x1800123fc`
- `0x180012460`
- `0x180023b20`
- `0x18003ea30`
- `0x1800486fc`
- `0x1800767c8`
- `0x180094d0c`
- `0x180094d2c`
- `0x180096b60`
- `0x1801def30`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180076994`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180076a7c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180076994`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180076a7c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180076909`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180076909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076e04`

## string_xrefs

- `0x180076833`: `Ualite.dll`
- `0x180076ccb`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x180076ce0`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x180076cf5`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x180076d6c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x180076db1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x180076df2`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x180076e33`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x180076e48`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UaLite\UaLiteSessionImpl.h`
- `0x18007698a`: `CreateOfflineDeploymentSession`
- `0x180076dda`: `Unable to load CreateDeploymentSession function for ualite`
- `0x180076e1b`: `Unable to load CreateDeploymentSession function for ualite`
- `0x180076a72`: `CreateDeploymentSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HMODULE *__fastcall UaLiteSession::LoadUaLiteSession(
        HMODULE *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        const wchar_t **a5)
{
  __int64 v7; // rbx
  const wchar_t *v9; // rcx
  int v10; // eax
  int v11; // edi
  __int64 v12; // rdx
  const WCHAR *v13; // rcx
  __int64 v14; // rdx
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rsi
  void (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // rcx
  int v18; // eax
  int v19; // esi
  __int64 v20; // rdx
  FARPROC v21; // rsi
  void (__fastcall ***v22)(_QWORD, GUID *, _QWORD *); // rcx
  int v23; // eax
  int v24; // esi
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rsi
  int v28; // eax
  const char *v29; // rax
  int v30; // eax
  struct CProgressHandler *v31; // rdx
  int v32; // eax
  struct IDeploymentProgress *v33; // rbx
  int v34; // eax
  void (__fastcall ***v35)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v37; // rcx
  unsigned int v38; // ebx
  __int64 v39; // r10
  signed int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  DWORD LastError; // ebx
  __int64 v45; // rcx
  DWORD v46; // ebx
  __int64 v47; // rcx
  DWORD v48; // ebx
  unsigned int *v49; // [rsp+20h] [rbp-C1h]
  unsigned int *v50; // [rsp+20h] [rbp-C1h]
  unsigned int v51[4]; // [rsp+50h] [rbp-91h] BYREF
  _QWORD v52[3]; // [rsp+68h] [rbp-79h] BYREF
  __int128 v53; // [rsp+80h] [rbp-61h] BYREF
  __int128 v54; // [rsp+90h] [rbp-51h]
  __int128 v55; // [rsp+A0h] [rbp-41h]
  __int64 v56; // [rsp+B0h] [rbp-31h] BYREF
  void (__fastcall ***v57)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp-29h] BYREF
  struct IDeploymentProgress *v58; // [rsp+C0h] [rbp-21h] BYREF
  LPCWSTR lpLibFileName[3]; // [rsp+C8h] [rbp-19h] BYREF
  unsigned __int64 v60; // [rsp+E0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  v52[2] = -2;
  v7 = a2;
  *(_QWORD *)v51 = a1;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LOBYTE(a2) = 1;
    LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      a2,
      1,
      "Loading Ualite session for sandbox [{}]",
      a4);
  }
  v52[0] = L"Ualite.dll";
  v52[1] = 10;
  CreatePath(lpLibFileName, a4, v52);
  LODWORD(v58) = 0;
  v9 = (const wchar_t *)lpLibFileName;
  if ( v60 > 7 )
    v9 = lpLibFileName[0];
  v10 = VerifyFileSignature(v9, (int *)&v58);
  v11 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v56) = v10;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to verify the signature of the UaLite");
      *(_QWORD *)v51 = &v56;
      v49 = v51;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
  }
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
      (const char *)(unsigned int)v11,
      (int)v49);
  if ( !(_DWORD)v58 )
  {
    v38 = EnsureWin32Error(686);
    if ( v39 )
    {
      LogAdapter::Logger::LogPartial<std::wstring>(v37, 3, "The library file for {} is not trusted", lpLibFileName);
      v40 = EnsureNTSTATUS<long>(v38);
      if ( v40 > 0 )
        v40 = (unsigned __int16)v40 | 0x80070000;
      LODWORD(v56) = v40;
      v41 = Windows::WCP::Rtl::FormatNtStatus<long>(v51, &v56);
      LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v42, 3, ": {0}", v41);
    }
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
      (const char *)v38,
      (unsigned int)v49);
  }
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v13 = (const WCHAR *)lpLibFileName;
  if ( v60 > 7 )
    v13 = lpLibFileName[0];
  Library = LoadLibraryExW(v13, 0, 0);
  v52[0] = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::Log<std::wstring>(v43, 3, "Unable to load the library [{}]", lpLibFileName);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
      (const char *)LastError,
      (unsigned int)v49);
  }
  v57 = 0;
  v55 = *(unsigned __int64 *)(v7 + 56);
  *((_QWORD *)&v53 + 1) = *(_QWORD *)(v7 + 32);
  v54 = *(_OWORD *)(v7 + 40);
  *(_QWORD *)&v53 = *(_QWORD *)(v7 + 24);
  if ( *(_QWORD *)(v7 + 72) )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LODWORD(v49) = (_DWORD)a5;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        1,
        "Creating offline deployment session for [{}] with sandbox [{}]");
    }
    ProcAddress = GetProcAddress(Library, "CreateOfflineDeploymentSession");
    if ( !ProcAddress )
    {
      v46 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
        LogAdapter::Logger::Log<>(v45, 3, "Unable to load CreateDeploymentSession function for ualite");
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
        (const char *)v46,
        (unsigned int)v49);
    }
    v17 = v57;
    v57 = 0;
    if ( v17 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v17)[2])(v17);
    *(GUID *)v51 = GUID_NULL;
    v50 = v51;
    v18 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))ProcAddress)(1, *a3, *(_QWORD *)(v7 + 72), 0);
    v19 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v56) = v18;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed creating DeploymentSession for uaLite");
        *(_QWORD *)v51 = &v56;
        v50 = v51;
        LOBYTE(v20) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v20,
          3,
          ": {}");
      }
    }
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
        (const char *)(unsigned int)v19,
        (int)v51);
  }
  else
  {
    v21 = GetProcAddress(Library, "CreateDeploymentSession");
    if ( !v21 )
    {
      v48 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
        LogAdapter::Logger::Log<>(v47, 3, "Unable to load CreateDeploymentSession function for ualite");
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
        (const char *)v48,
        (unsigned int)v49);
    }
    v22 = v57;
    v57 = 0;
    if ( v22 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v22)[2])(v22);
    *(GUID *)v51 = GUID_NULL;
    v50 = (unsigned int *)&v57;
    v23 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned int *, __int128 *))v21)(1, *a3, v51, &v53);
    v24 = v23;
    if ( v23 < 0 )
    {
      LODWORD(v56) = v23;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed creating DeploymentSession for uaLite");
        *(_QWORD *)v51 = &v56;
        v50 = v51;
        LOBYTE(v25) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v25,
          3,
          ": {}");
      }
    }
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
        (const char *)(unsigned int)v24,
        (int)v50);
  }
  v56 = 0;
  (**v57)(v57, &GUID_c6dfaad3_6829_4fef_b8fa_3bb0ada81cbc, &v56);
  v26 = v56;
  if ( v56 )
  {
    v27 = *(_QWORD *)(v7 + 88);
    if ( v27 )
    {
      LODWORD(v58) = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, struct IDeploymentProgress **))(*(_QWORD *)v27 + 24LL))(v27, &v58);
      if ( v28 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(
          2,
          (unsigned int)v28,
          "Unable to query for range request support on IDeploymentInformation");
      v29 = "TRUE";
      if ( !(_DWORD)v58 )
        v29 = "FALSE";
      *(_QWORD *)v51 = v29;
      LogAdapter::TraceAtLevel<char const *>(
        "FALSE",
        "Setting Range Request Support [{}] with Deployment Information on UALite session",
        v51);
      v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v56 + 176LL))(v56, v27);
      if ( v30 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(
          2,
          (unsigned int)v30,
          "Unable to Set Deployment Information on UALite session");
      v26 = v56;
    }
    if ( v26 )
    {
      v31 = *(struct CProgressHandler **)(v7 + 96);
      if ( v31 )
      {
        v58 = 0;
        v32 = CUaLiteProgress::Create(*a5, v31, &v58);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7D,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UaLite\\UaLiteSessionImpl.h",
            (const char *)(unsigned int)v32,
            (int)v50);
        v33 = v58;
        v34 = (*(__int64 (__fastcall **)(__int64, struct IDeploymentProgress *))(*(_QWORD *)v56 + 184LL))(v56, v58);
        if ( v34 < 0 )
          LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v34, "Unable to Set Deployment Progress on UALite session");
        if ( v33 )
          (*(void (__fastcall **)(struct IDeploymentProgress *))(*(_QWORD *)v33 + 16LL))(v33);
        v26 = v56;
      }
    }
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  *a1 = Library;
  v35 = v57;
  v57 = 0;
  a1[1] = (HMODULE)v35;
  std::wstring::~wstring(lpLibFileName);
  return a1;
}

```

## disassembly

```asm
0x1800767c8  push    rbp
0x1800767ca  push    rbx
0x1800767cb  push    rsi
0x1800767cc  push    rdi
0x1800767cd  push    r12
0x1800767cf  push    r13
0x1800767d1  push    r14
0x1800767d3  push    r15
0x1800767d5  lea     rbp, [rsp-17h]
0x1800767da  sub     rsp, 0F8h
0x1800767e1  mov     [rbp+4Fh+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800767e9  mov     rax, cs:__security_cookie
0x1800767f0  xor     rax, rsp
0x1800767f3  mov     [rbp+4Fh+var_48], rax
0x1800767f7  mov     rsi, r9
0x1800767fa  mov     r15, r8
0x1800767fd  mov     rbx, rdx
0x180076800  mov     r14, rcx
0x180076803  mov     qword ptr [rsp+130h+var_E0], rcx
0x180076808  mov     r12, qword ptr [rbp+4Fh+arg_20]
0x18007680c  xor     r13d, r13d
0x18007680f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180076816  test    rcx, rcx
0x180076819  jz      short loc_180076833
0x18007681b  mov     qword ptr [rsp+130h+var_110], r9
0x180076820  lea     r9, aLoadingUaliteS; "Loading Ualite session for sandbox [{}]"
0x180076827  lea     r8d, [r13+1]
0x18007682b  mov     dl, r8b
0x18007682e  call    ??$LogNumObjects@V?$basic_zstring_view@_W@wil@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_zstring_view@_W@wil@@@Z; LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>>(bool,LogAdapter::LogLevel,char const * const,wil::basic_zstring_view<wchar_t> const &)
0x180076833  lea     rax, aUaliteDll_0; "Ualite.dll"
0x18007683a  mov     [rbp+4Fh+var_C8], rax
0x18007683e  mov     [rbp+4Fh+var_C0], 0Ah
0x180076846  lea     r8, [rbp+4Fh+var_C8]
0x18007684a  mov     rdx, rsi
0x18007684d  lea     rcx, [rbp+4Fh+lpLibFileName]
0x180076851  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180076856  nop
0x180076857  mov     dword ptr [rbp+4Fh+var_70], r13d
0x18007685b  lea     rcx, [rbp+4Fh+lpLibFileName]
0x18007685f  cmp     [rbp+4Fh+var_50], 7
0x180076864  cmova   rcx, [rbp+4Fh+lpLibFileName]; wchar_t *
0x180076869  lea     rdx, [rbp+4Fh+var_70]; int *
0x18007686d  call    ?VerifyFileSignature@@YAJPEB_WPEAH@Z; VerifyFileSignature(wchar_t const *,int *)
0x180076872  mov     edi, eax
0x180076874  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007687b  test    eax, eax
0x18007687d  jns     short loc_1800768D1
0x18007687f  mov     dword ptr [rbp+4Fh+var_80], eax
0x180076882  test    r10, r10
0x180076885  jz      short loc_1800768D1
0x180076887  lea     r9, aFailedToVerify; "Failed to verify the signature of the U"...
0x18007688e  xor     edx, edx
0x180076890  lea     r8d, [rdx+3]
0x180076894  mov     rcx, r10
0x180076897  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007689c  lea     rax, [rbp+4Fh+var_80]
0x1800768a0  mov     qword ptr [rsp+130h+var_E0], rax
0x1800768a5  lea     rax, [rsp+130h+var_E0]
0x1800768aa  mov     qword ptr [rsp+130h+var_110], rax; unsigned int
0x1800768af  lea     r9, asc_1802C6678; ": {}"
0x1800768b6  mov     r8d, 3
0x1800768bc  mov     dl, 1
0x1800768be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800768c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800768ca  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800768d1  mov     rcx, [rbp+57h]; this
0x1800768d5  test    edi, edi
0x1800768d7  js      loc_180076CF2
0x1800768dd  cmp     dword ptr [rbp+4Fh+var_70], r13d
0x1800768e1  jz      loc_180076D07
0x1800768e7  xorps   xmm0, xmm0
0x1800768ea  movups  [rbp+4Fh+var_B0], xmm0
0x1800768ee  movups  [rbp+4Fh+var_A0], xmm0
0x1800768f2  movups  [rbp+4Fh+var_90], xmm0
0x1800768f6  lea     rcx, [rbp+4Fh+lpLibFileName]
0x1800768fa  cmp     [rbp+4Fh+var_50], 7
0x1800768ff  cmova   rcx, [rbp+4Fh+lpLibFileName]; lpLibFileName
0x180076904  xor     r8d, r8d; dwFlags
0x180076907  xor     edx, edx; hFile
0x180076909  call    cs:__imp_LoadLibraryExW
0x180076910  nop     dword ptr [rax+rax+00h]
0x180076915  mov     rdi, rax
0x180076918  mov     [rbp+4Fh+var_C8], rax
0x18007691c  test    rax, rax
0x18007691f  jz      loc_180076D7E
0x180076925  mov     [rbp+4Fh+var_78], r13
0x180076929  mov     rax, [rbx+38h]
0x18007692d  mov     qword ptr [rbp+4Fh+var_90], rax
0x180076931  mov     qword ptr [rbp+4Fh+var_90+8], r13
0x180076935  mov     rax, [rbx+20h]
0x180076939  mov     qword ptr [rbp+4Fh+var_B0+8], rax
0x18007693d  mov     rax, [rbx+28h]
0x180076941  mov     qword ptr [rbp+4Fh+var_A0], rax
0x180076945  mov     rax, [rbx+30h]
0x180076949  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x18007694d  mov     rax, [rbx+18h]
0x180076951  mov     qword ptr [rbp+4Fh+var_B0], rax
0x180076955  cmp     [rbx+48h], r13
0x180076959  jz      loc_180076A72
0x18007695f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180076966  test    rcx, rcx
0x180076969  jz      short loc_18007698A
0x18007696b  mov     [rsp+130h+var_108], rsi
0x180076970  mov     qword ptr [rsp+130h+var_110], r12; unsigned int
0x180076975  lea     r9, aCreatingOfflin; "Creating offline deployment session for"...
0x18007697c  mov     r8d, 1
0x180076982  mov     dl, r8b
0x180076985  call    ??$LogNumObjects@V?$basic_zstring_view@_W@wil@@V12@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_zstring_view@_W@wil@@3@Z; LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>>(bool,LogAdapter::LogLevel,char const * const,wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &)
0x18007698a  lea     rdx, aCreateofflined_1; "CreateOfflineDeploymentSession"
0x180076991  mov     rcx, rdi; hModule
0x180076994  call    cs:__imp_GetProcAddress
0x18007699b  nop     dword ptr [rax+rax+00h]
0x1800769a0  mov     rsi, rax
0x1800769a3  test    rax, rax
0x1800769a6  jz      loc_180076DC3
0x1800769ac  mov     rcx, [rbp+4Fh+var_78]
0x1800769b0  mov     [rbp+4Fh+var_78], r13
0x1800769b4  test    rcx, rcx
0x1800769b7  jz      short loc_1800769C6
0x1800769b9  mov     rax, [rcx]
0x1800769bc  mov     rax, [rax+10h]
0x1800769c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800769c5  nop
0x1800769c6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800769cd  movdqu  xmmword ptr [rsp+130h+var_E0], xmm0
0x1800769d3  lea     rax, [rbp+4Fh+var_78]
0x1800769d7  mov     [rsp+130h+var_F8], rax
0x1800769dc  lea     rax, [rbp+4Fh+var_B0]
0x1800769e0  mov     [rsp+130h+var_100], rax
0x1800769e5  mov     ecx, 1
0x1800769ea  mov     dword ptr [rsp+130h+var_108], ecx
0x1800769ee  lea     rax, [rsp+130h+var_E0]
0x1800769f3  mov     qword ptr [rsp+130h+var_110], rax
0x1800769f8  xor     r9d, r9d
0x1800769fb  mov     r8, [rbx+48h]
0x1800769ff  mov     rdx, [r15]
0x180076a02  mov     rax, rsi
0x180076a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a0a  mov     esi, eax
0x180076a0c  test    eax, eax
0x180076a0e  jns     short loc_180076A61
0x180076a10  mov     dword ptr [rbp+4Fh+var_80], eax
0x180076a13  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180076a1a  test    rcx, rcx
0x180076a1d  jz      short loc_180076A61
0x180076a1f  lea     r9, aFailedCreating_5; "Failed creating DeploymentSession for u"...
0x180076a26  mov     r15d, 3
0x180076a2c  mov     r8d, r15d
0x180076a2f  xor     edx, edx
0x180076a31  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180076a36  lea     rax, [rbp+4Fh+var_80]
0x180076a3a  mov     qword ptr [rsp+130h+var_E0], rax
0x180076a3f  lea     rax, [rsp+130h+var_E0]
0x180076a44  mov     qword ptr [rsp+130h+var_110], rax; int
0x180076a49  lea     r9, asc_1802C6678; ": {}"
0x180076a50  mov     r8d, r15d
0x180076a53  mov     dl, 1
0x180076a55  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180076a5c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180076a61  mov     rcx, [rbp+57h]; this
0x180076a65  test    esi, esi
0x180076a67  js      loc_180076CDD
0x180076a6d  jmp     loc_180076B40
0x180076a72  lea     rdx, aCreatedeployme_2; "CreateDeploymentSession"
0x180076a79  mov     rcx, rdi; hModule
0x180076a7c  call    cs:__imp_GetProcAddress
0x180076a83  nop     dword ptr [rax+rax+00h]
0x180076a88  mov     rsi, rax
0x180076a8b  test    rax, rax
0x180076a8e  jz      loc_180076E04
0x180076a94  mov     rcx, [rbp+4Fh+var_78]
0x180076a98  mov     [rbp+4Fh+var_78], r13
0x180076a9c  test    rcx, rcx
0x180076a9f  jz      short loc_180076AAE
0x180076aa1  mov     rax, [rcx]
0x180076aa4  mov     rax, [rax+10h]
0x180076aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076aad  nop
0x180076aae  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180076ab5  movdqu  xmmword ptr [rsp+130h+var_E0], xmm0
0x180076abb  lea     rax, [rbp+4Fh+var_78]
0x180076abf  mov     qword ptr [rsp+130h+var_110], rax
0x180076ac4  lea     r9, [rbp+4Fh+var_B0]
0x180076ac8  lea     r8, [rsp+130h+var_E0]
0x180076acd  mov     rdx, [r15]
0x180076ad0  mov     ecx, 1
0x180076ad5  mov     rax, rsi
0x180076ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076add  mov     esi, eax
0x180076adf  test    eax, eax
0x180076ae1  jns     short loc_180076B34
0x180076ae3  mov     dword ptr [rbp+4Fh+var_80], eax
0x180076ae6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180076aed  test    rcx, rcx
0x180076af0  jz      short loc_180076B34
0x180076af2  lea     r9, aFailedCreating_5; "Failed creating DeploymentSession for u"...
0x180076af9  mov     r15d, 3
0x180076aff  mov     r8d, r15d
0x180076b02  xor     edx, edx
0x180076b04  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180076b09  lea     rax, [rbp+4Fh+var_80]
0x180076b0d  mov     qword ptr [rsp+130h+var_E0], rax
0x180076b12  lea     rax, [rsp+130h+var_E0]
0x180076b17  mov     qword ptr [rsp+130h+var_110], rax; int
0x180076b1c  lea     r9, asc_1802C6678; ": {}"
0x180076b23  mov     r8d, r15d
0x180076b26  mov     dl, 1
0x180076b28  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180076b2f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180076b34  mov     rcx, [rbp+57h]; this
0x180076b38  test    esi, esi
0x180076b3a  js      loc_180076E45
0x180076b40  mov     rcx, [rbp+4Fh+var_78]
0x180076b44  mov     [rbp+4Fh+var_80], r13
0x180076b48  mov     rax, [rcx]
0x180076b4b  lea     r8, [rbp+4Fh+var_80]
0x180076b4f  lea     rdx, _GUID_c6dfaad3_6829_4fef_b8fa_3bb0ada81cbc
0x180076b56  mov     rax, [rax]
0x180076b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b5e  nop
0x180076b5f  mov     rcx, [rbp+4Fh+var_80]
0x180076b63  test    rcx, rcx
0x180076b66  jz      loc_180076C7A
0x180076b6c  mov     rsi, [rbx+58h]
0x180076b70  mov     r15d, 2
0x180076b76  test    rsi, rsi
0x180076b79  jz      loc_180076C06
0x180076b7f  mov     dword ptr [rbp+4Fh+var_70], r13d
0x180076b83  mov     rax, [rsi]
0x180076b86  lea     rdx, [rbp+4Fh+var_70]
0x180076b8a  mov     rcx, rsi
0x180076b8d  mov     rax, [rax+18h]
0x180076b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b96  test    eax, eax
0x180076b98  jns     short loc_180076BAB
0x180076b9a  lea     r8, aUnableToQueryF; "Unable to query for range request suppo"...
0x180076ba1  mov     edx, eax
0x180076ba3  mov     ecx, r15d
0x180076ba6  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180076bab  lea     rax, aTrue_1; "TRUE"
0x180076bb2  lea     rcx, aFalse_1; "FALSE"
0x180076bb9  cmp     dword ptr [rbp+4Fh+var_70], r13d
0x180076bbd  cmovz   rax, rcx
0x180076bc1  mov     qword ptr [rsp+130h+var_E0], rax
0x180076bc6  lea     r8, [rsp+130h+var_E0]
0x180076bcb  lea     rdx, aSettingRangeRe; "Setting Range Request Support [{}] with"...
0x180076bd2  call    ??$TraceAtLevel@PEBD@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEBD@Z; LogAdapter::TraceAtLevel<char const *>(LogAdapter::LogLevel,char const * const,char const * const &)
0x180076bd7  mov     rcx, [rbp+4Fh+var_80]
0x180076bdb  mov     rax, [rcx]
0x180076bde  mov     rdx, rsi
0x180076be1  mov     rax, [rax+0B0h]
0x180076be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076bed  test    eax, eax
0x180076bef  jns     short loc_180076C02
0x180076bf1  lea     r8, aUnableToSetDep; "Unable to Set Deployment Information on"...
0x180076bf8  mov     edx, eax
0x180076bfa  mov     ecx, r15d
0x180076bfd  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180076c02  mov     rcx, [rbp+4Fh+var_80]
0x180076c06  test    rcx, rcx
0x180076c09  jz      short loc_180076C7A
0x180076c0b  mov     rdx, [rbx+60h]; struct CProgressHandler *
0x180076c0f  test    rdx, rdx
0x180076c12  jz      short loc_180076C7A
0x180076c14  mov     [rbp+4Fh+var_70], r13
0x180076c18  lea     r8, [rbp+4Fh+var_70]; struct IDeploymentProgress **
0x180076c1c  mov     rcx, [r12]; wchar_t *
0x180076c20  call    ?Create@CUaLiteProgress@@SAJPEB_WPEAVCProgressHandler@@PEAPEAUIDeploymentProgress@@@Z; CUaLiteProgress::Create(wchar_t const *,CProgressHandler *,IDeploymentProgress * *)
0x180076c25  mov     rcx, [rbp+57h]; this
0x180076c29  test    eax, eax
0x180076c2b  js      loc_180076CC8
0x180076c31  mov     rcx, [rbp+4Fh+var_80]
0x180076c35  mov     rax, [rcx]
0x180076c38  mov     rbx, [rbp+4Fh+var_70]
0x180076c3c  mov     rdx, rbx
0x180076c3f  mov     rax, [rax+0B8h]
0x180076c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c4b  test    eax, eax
0x180076c4d  jns     short loc_180076C61
0x180076c4f  lea     r8, aUnableToSetDep_0; "Unable to Set Deployment Progress on UA"...
0x180076c56  mov     edx, eax
0x180076c58  mov     ecx, r15d
0x180076c5b  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180076c60  nop
0x180076c61  test    rbx, rbx
0x180076c64  jz      short loc_180076C76
0x180076c66  mov     rax, [rbx]
0x180076c69  mov     rcx, rbx
0x180076c6c  mov     rax, [rax+10h]
0x180076c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c75  nop
0x180076c76  mov     rcx, [rbp+4Fh+var_80]
0x180076c7a  test    rcx, rcx
0x180076c7d  jz      short loc_180076C8C
0x180076c7f  mov     rax, [rcx]
0x180076c82  mov     rax, [rax+10h]
0x180076c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c8b  nop
0x180076c8c  mov     [r14], rdi
0x180076c8f  mov     rcx, [rbp+4Fh+var_78]
  ... truncated ...
```

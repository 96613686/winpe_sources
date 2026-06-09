# CPnPClient::Initialize(DeviceContext *)

- ea: `0x18013b5e4`
- end: `0x18013bf78`
- name: `?Initialize@CPnPClient@@QEAAJPEAVDeviceContext@@@Z`
- size: `2452`
- prototype: `int(CPnPClient *__hidden this, struct DeviceContext *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d53c8`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x1800692fc`
- `0x18008b38c`
- `0x18008b3ec`
- `0x1800a76dc`
- `0x18013b5e4`
- `0x1801488f0`
- `0x18014a56c`
- `0x18014b0c8`
- `0x18014b298`
- `0x18014c4c8`
- `0x18017657c`
- `0x1801dcc08`
- `0x1801e19ec`
- `0x1801f250c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bc4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bce7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bd84`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bea1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bc4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bce7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bd84`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013bea1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18013b9ff`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18013bdc5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18013b9ff`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18013bdc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ba21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bcfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013beb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ba21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bcfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013bde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013beb6`

## string_xrefs

- `0x18013b7fe`: `UpdateAPI.dll`
- `0x18013bbad`: `UpdateAPI.dll`
- `0x18013b78f`: `Failed getting windows relative path`
- `0x18013b938`: `Failed getting windows relative path`
- `0x18013bac2`: `Failed getting external stack path`
- `0x18013be03`: `Failed to load UpdateAPI DLL`
- `0x18013b67e`: `Failed to get path to drvservicing.dll`
- `0x18013b652`: `drvservicing.dll`
- `0x18013bb1e`: `drvservicing.dll`
- `0x18013b76a`: `System32\drvservicing.dll`
- `0x18013b90f`: `System32\UpdateAPI.dll`
- `0x18013b826`: `Failed to get path to UpdateAPI.dll`
- `0x18013ba3f`: `Failed to load DrvServicing DLL`
- `0x18013bc79`: `Failed to get proc address for GetInstalledDriverPackageInfo.`
- `0x18013bc40`: `GetInstalledDriverPackageInfo`
- `0x18013bd16`: `Failed to get proc address for FreeInstalledDriverPackageInfo.`
- `0x18013bcdd`: `FreeInstalledDriverPackageInfo`
- `0x18013bed0`: `Failed to get proc address for GetRootPath.`
- `0x18013be97`: `GetRootPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPnPClient::Initialize(CPnPClient *this, struct DeviceContext *a2)
{
  const struct std::nothrow_t *v4; // rdx
  int Win32PathOfSiblingFile; // eax
  __int64 v6; // rdx
  int v7; // ebx
  const struct std::nothrow_t *v8; // rdx
  __int64 v10; // rbx
  int v11; // eax
  unsigned int v12; // r14d
  const struct std::nothrow_t *v13; // rdx
  int WindowsRelativePath; // eax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // edi
  const struct std::nothrow_t *v21; // rdx
  WCHAR *v22; // rcx
  int v23; // eax
  HMODULE Library; // rax
  signed int LastError; // ebx
  unsigned int v26; // eax
  char *v27; // rbx
  char *v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  WCHAR *v35; // rcx
  FARPROC ProcAddress; // rax
  unsigned int v37; // eax
  FARPROC v38; // rax
  unsigned int v39; // eax
  FARPROC v40; // rax
  LPCWSTR v41; // rbx
  HMODULE v42; // rax
  signed int v43; // esi
  unsigned int v44; // eax
  __int64 v45; // rdx
  FARPROC v46; // rax
  unsigned int v47; // eax
  unsigned int v48; // [rsp+20h] [rbp-60h]
  unsigned int v49[2]; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR v50; // [rsp+38h] [rbp-48h] BYREF
  __int128 v51; // [rsp+40h] [rbp-40h] BYREF
  __int64 v52; // [rsp+50h] [rbp-30h]
  __int64 v53; // [rsp+58h] [rbp-28h]
  unsigned int v54; // [rsp+60h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v53 = -2;
  lpLibFileName = 0;
  v50 = 0;
  if ( *((_DWORD *)a2 + 1) )
    return 0;
  if ( InMobile() )
  {
    v51 = 0;
    v52 = 0;
    Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(&byte_1803AC168, L"drvservicing.dll", &v51);
    v7 = Win32PathOfSiblingFile;
    if ( Win32PathOfSiblingFile < 0 )
    {
      v54 = Win32PathOfSiblingFile;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get path to drvservicing.dll");
        *(_QWORD *)v49 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v49);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
        (const char *)(unsigned int)v7,
        v48);
      if ( v52 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v52);
LABEL_8:
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4), v8);
      return (unsigned int)v7;
    }
    v10 = v52;
    if ( (unsigned int)DoesFileExist(v52, v6) )
    {
      v11 = SczAllocFromSz(&lpLibFileName, v10);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)(unsigned int)v11,
          v48);
        if ( v10 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v10);
        goto LABEL_15;
      }
    }
    else
    {
      WindowsRelativePath = DeviceContext::GetWindowsRelativePath(
                              a2,
                              L"System32\\drvservicing.dll",
                              (struct AutoScz *)&lpLibFileName);
      v12 = WindowsRelativePath;
      if ( WindowsRelativePath < 0 )
      {
        v54 = WindowsRelativePath;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting windows relative path");
          *(_QWORD *)v49 = &v54;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v49);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)v12,
          v48);
        if ( v10 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v10);
        goto LABEL_15;
      }
    }
    v15 = Windows::COM::GetWin32PathOfSiblingFile(&byte_1803AC168, L"UpdateAPI.dll", &v51);
    v7 = v15;
    if ( v15 < 0 )
    {
      v54 = v15;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get path to UpdateAPI.dll");
        *(_QWORD *)v49 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v49);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
        (const char *)(unsigned int)v7,
        v48);
      if ( v52 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v52);
      goto LABEL_8;
    }
    v17 = v52;
    if ( (unsigned int)DoesFileExist(v52, v16) )
    {
      v18 = SczAllocFromSz(&v50, v17);
      v20 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)(unsigned int)v18,
          v48);
        if ( v17 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v17);
        if ( !v50 )
          goto LABEL_37;
        v22 = (WCHAR *)(v50 - 4);
        goto LABEL_36;
      }
    }
    else
    {
      v23 = DeviceContext::GetWindowsRelativePath(a2, L"System32\\UpdateAPI.dll", (struct AutoScz *)&v50);
      v12 = v23;
      if ( v23 < 0 )
      {
        v54 = v23;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting windows relative path");
          *(_QWORD *)v49 = &v54;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v49);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)v12,
          v48);
        if ( v17 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v17);
        if ( v50 )
          operator delete((void *)(v50 - 4), v13);
        goto LABEL_15;
      }
    }
    if ( v17 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v17);
    goto LABEL_49;
  }
  if ( !*(_BYTE *)a2 || !*((_QWORD *)a2 + 3) )
    goto LABEL_133;
  v27 = (char *)a2 + 8;
  if ( !(*((_QWORD *)a2 + 4) <= 7u ? (struct DeviceContext *)((char *)a2 + 8) : *(struct DeviceContext **)v27) )
    goto LABEL_133;
  if ( *((_QWORD *)a2 + 4) <= 7u )
    v29 = (char *)a2 + 8;
  else
    v29 = *(char **)v27;
  v30 = SczAllocFromSzAndEnsureBackslash(&lpLibFileName, v29);
  v12 = v30;
  if ( v30 < 0 )
  {
    v54 = v30;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting external stack path");
      *(_QWORD *)v49 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v49);
    }
    v31 = 61;
    goto LABEL_69;
  }
  v12 = SczAllocConcatSz(&lpLibFileName, L"drvservicing.dll");
  if ( (v12 & 0x80000000) != 0 )
  {
    v31 = 63;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
      (const char *)v12,
      v48);
LABEL_15:
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4), v13);
    return v12;
  }
  if ( !(unsigned int)DoesFileExist(lpLibFileName, v32) )
    goto LABEL_133;
  if ( *(_BYTE *)a2 && *((_QWORD *)a2 + 3) )
  {
    if ( *((_QWORD *)a2 + 4) > 7u )
      v27 = *(char **)v27;
  }
  else
  {
    v27 = 0;
  }
  v7 = SczAllocFromSzAndEnsureBackslash(&v50, v27);
  if ( v7 < 0 )
  {
    v33 = 70;
LABEL_80:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
      (const char *)(unsigned int)v7,
      v48);
    goto LABEL_81;
  }
  v7 = SczAllocConcatSz(&v50, L"UpdateAPI.dll");
  if ( v7 < 0 )
  {
    v33 = 72;
    goto LABEL_80;
  }
LABEL_49:
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LOBYTE(v19) = 1;
    LogAdapter::Logger::LogNumObjects<AutoScz>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v19,
      1,
      "Loading drvservicing: {0}",
      &lpLibFileName);
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 8u);
  if ( *(_QWORD *)this )
    goto LABEL_136;
  *(_QWORD *)this = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load DrvServicing DLL");
      if ( LastError > 0 )
        v26 = (unsigned __int16)LastError | 0x80070000;
      else
        v26 = LastError;
      v54 = v26;
      *(_QWORD *)v49 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v49);
    }
    if ( LastError )
    {
      v34 = 85;
LABEL_89:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v34,
             (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
             (const char *)(unsigned int)LastError,
             v48);
LABEL_81:
      if ( v50 )
        operator delete((void *)(v50 - 4), v8);
      goto LABEL_8;
    }
    goto LABEL_90;
  }
  ProcAddress = GetProcAddress(Library, "GetInstalledDriverPackageInfo");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for GetInstalledDriverPackageInfo.");
      if ( LastError > 0 )
        v37 = (unsigned __int16)LastError | 0x80070000;
      else
        v37 = LastError;
      v54 = v37;
      *(_QWORD *)v49 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v49);
    }
    if ( LastError )
    {
      v34 = 89;
      goto LABEL_89;
    }
    goto LABEL_90;
  }
  v38 = GetProcAddress(*(HMODULE *)this, "FreeInstalledDriverPackageInfo");
  *((_QWORD *)this + 2) = v38;
  if ( !v38 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for FreeInstalledDriverPackageInfo.");
      if ( LastError > 0 )
        v39 = (unsigned __int16)LastError | 0x80070000;
      else
        v39 = LastError;
      v54 = v39;
      *(_QWORD *)v49 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v49);
    }
    if ( LastError )
    {
      v34 = 93;
      goto LABEL_89;
    }
LABEL_90:
    if ( !v50 )
      goto LABEL_133;
    v35 = (WCHAR *)(v50 - 4);
    goto LABEL_92;
  }
  v40 = GetProcAddress(*(HMODULE *)this, "SetLogger");
  if ( v40 )
    ((void (__fastcall *)(_QWORD))v40)(*(_QWORD *)&LogAdapter::g_Logger);
  else
    CBSWdsLog(0x4000000, 0, 0, "Failed to get proc address for SetLogger, continuing without DrvServicing logging.");
  v41 = v50;
  v42 = LoadLibraryExW(v50, 0, 8u);
  if ( *((_QWORD *)this + 3) )
  {
LABEL_136:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18013BF77LL);
  }
  *((_QWORD *)this + 3) = v42;
  if ( v42 )
  {
    v46 = GetProcAddress(v42, "GetRootPath");
    *((_QWORD *)this + 4) = v46;
    if ( !v46 )
    {
      v43 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for GetRootPath.");
        if ( v43 > 0 )
          v47 = (unsigned __int16)v43 | 0x80070000;
        else
          v47 = v43;
        v54 = v47;
        *(_QWORD *)v49 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)v49);
      }
      if ( v43 )
      {
        v45 = 109;
        goto LABEL_121;
      }
    }
    goto LABEL_123;
  }
  v43 = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(__int64 *)&LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load UpdateAPI DLL");
    if ( v43 > 0 )
      v44 = (unsigned __int16)v43 | 0x80070000;
    else
      v44 = v43;
    v54 = v44;
    *(_QWORD *)v49 = &v54;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
      (__int64)v49);
  }
  if ( !v43 )
  {
LABEL_123:
    if ( v41 )
    {
      v35 = (WCHAR *)(v41 - 4);
LABEL_92:
      operator delete(v35, v4);
    }
LABEL_133:
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4), v4);
    return 0;
  }
  v45 = 106;
LABEL_121:
  v20 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v45,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)(unsigned int)v43,
          v48);
  if ( !v41 )
    goto LABEL_37;
  v22 = (WCHAR *)(v41 - 4);
LABEL_36:
  operator delete(v22, v21);
LABEL_37:
  if ( lpLibFileName )
    operator delete((void *)(lpLibFileName - 4), v21);
  return v20;
}

```

## disassembly

```asm
0x18013b5e4  mov     rax, rsp
0x18013b5e7  push    rbp
0x18013b5e8  push    rdi
0x18013b5e9  push    r14
0x18013b5eb  mov     rbp, rsp
0x18013b5ee  sub     rsp, 80h
0x18013b5f5  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x18013b5fd  mov     [rax+18h], rbx
0x18013b601  mov     [rax+20h], rsi
0x18013b605  mov     rax, cs:__security_cookie
0x18013b60c  xor     rax, rsp
0x18013b60f  mov     [rbp+var_10], rax
0x18013b613  mov     rdi, rdx
0x18013b616  mov     rsi, rcx
0x18013b619  mov     [rbp+lpLibFileName], 0
0x18013b621  mov     [rbp+var_48], 0
0x18013b629  cmp     dword ptr [rdx+4], 0
0x18013b62d  jz      short loc_18013B634
0x18013b62f  jmp     loc_18013BF46
0x18013b634  call    ?InMobile@@YA_NXZ; InMobile(void)
0x18013b639  test    al, al
0x18013b63b  jz      loc_18013BA64
0x18013b641  xorps   xmm0, xmm0
0x18013b644  xor     eax, eax
0x18013b646  movups  [rbp+var_40], xmm0
0x18013b64a  mov     [rbp+var_30], rax
0x18013b64e  lea     r8, [rbp+var_40]
0x18013b652  lea     rdx, aDrvservicingDl_0; "drvservicing.dll"
0x18013b659  lea     rcx, byte_1803AC168
0x18013b660  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x18013b665  mov     ebx, eax
0x18013b667  test    eax, eax
0x18013b669  jns     loc_18013B6FE
0x18013b66f  mov     [rbp+var_20], eax
0x18013b672  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b679  test    rcx, rcx
0x18013b67c  jz      short loc_18013B6BD
0x18013b67e  lea     r9, aFailedToGetPat_1; "Failed to get path to drvservicing.dll"
0x18013b685  mov     edi, 3
0x18013b68a  mov     r8d, edi
0x18013b68d  xor     edx, edx
0x18013b68f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013b694  lea     rax, [rbp+var_20]
0x18013b698  mov     qword ptr [rbp+var_50], rax
0x18013b69c  lea     rax, [rbp+var_50]
0x18013b6a0  mov     qword ptr [rsp+80h+var_60], rax; int
0x18013b6a5  lea     r9, asc_1802C6678; ": {}"
0x18013b6ac  mov     r8d, edi
0x18013b6af  mov     dl, 1
0x18013b6b1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b6b8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013b6bd  mov     rcx, [rbp+18h]; this
0x18013b6c1  mov     r9d, ebx; char *
0x18013b6c4  lea     r8, aOnecoreBaseSer_29; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x18013b6cb  mov     edx, 1Dh; void *
0x18013b6d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b6d5  nop
0x18013b6d6  mov     rcx, [rbp+var_30]
0x18013b6da  test    rcx, rcx
0x18013b6dd  jz      short loc_18013B6E5
0x18013b6df  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18013b6e4  nop
0x18013b6e5  mov     rcx, [rbp+lpLibFileName]
0x18013b6e9  test    rcx, rcx
0x18013b6ec  jz      short loc_18013B6F7
0x18013b6ee  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18013b6f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013b6f7  mov     eax, ebx
0x18013b6f9  jmp     loc_18013BF48
0x18013b6fe  mov     rbx, [rbp+var_30]
0x18013b702  mov     rcx, rbx
0x18013b705  call    DoesFileExist
0x18013b70a  test    eax, eax
0x18013b70c  jz      short loc_18013B766
0x18013b70e  mov     rdx, rbx
0x18013b711  lea     rcx, [rbp+lpLibFileName]
0x18013b715  call    SczAllocFromSz
0x18013b71a  mov     r14d, eax
0x18013b71d  test    eax, eax
0x18013b71f  jns     loc_18013B7FA
0x18013b725  mov     rcx, [rbp+18h]; this
0x18013b729  mov     r9d, eax; char *
0x18013b72c  lea     r8, aOnecoreBaseSer_29; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x18013b733  mov     edx, 21h ; '!'; void *
0x18013b738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b73d  nop
0x18013b73e  test    rbx, rbx
0x18013b741  jz      short loc_18013B74C
0x18013b743  mov     rcx, rbx
0x18013b746  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18013b74b  nop
0x18013b74c  mov     rcx, [rbp+lpLibFileName]
0x18013b750  test    rcx, rcx
0x18013b753  jz      short loc_18013B75E
0x18013b755  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18013b759  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013b75e  mov     eax, r14d
0x18013b761  jmp     loc_18013BF48
0x18013b766  lea     r8, [rbp+lpLibFileName]; struct AutoScz *
0x18013b76a  lea     rdx, aSystem32Drvser; "System32\\drvservicing.dll"
0x18013b771  mov     rcx, rdi; this
0x18013b774  call    ?GetWindowsRelativePath@DeviceContext@@QEBAJPEB_WPEAVAutoScz@@@Z; DeviceContext::GetWindowsRelativePath(wchar_t const *,AutoScz *)
0x18013b779  mov     r14d, eax
0x18013b77c  test    eax, eax
0x18013b77e  jns     short loc_18013B7FA
0x18013b780  mov     [rbp+var_20], eax
0x18013b783  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b78a  test    rcx, rcx
0x18013b78d  jz      short loc_18013B7CE
0x18013b78f  lea     r9, aFailedGettingW_3; "Failed getting windows relative path"
0x18013b796  mov     edi, 3
0x18013b79b  mov     r8d, edi
0x18013b79e  xor     edx, edx
0x18013b7a0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013b7a5  lea     rax, [rbp+var_20]
0x18013b7a9  mov     qword ptr [rbp+var_50], rax
0x18013b7ad  lea     rax, [rbp+var_50]
0x18013b7b1  mov     qword ptr [rsp+80h+var_60], rax; int
0x18013b7b6  lea     r9, asc_1802C6678; ": {}"
0x18013b7bd  mov     r8d, edi
0x18013b7c0  mov     dl, 1
0x18013b7c2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b7c9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013b7ce  mov     rcx, [rbp+18h]; this
0x18013b7d2  mov     r9d, r14d; char *
0x18013b7d5  lea     r8, aOnecoreBaseSer_29; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x18013b7dc  mov     edx, 26h ; '&'; void *
0x18013b7e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b7e6  nop
0x18013b7e7  test    rbx, rbx
0x18013b7ea  jz      short loc_18013B7F5
0x18013b7ec  mov     rcx, rbx
0x18013b7ef  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18013b7f4  nop
0x18013b7f5  jmp     loc_18013B74C
0x18013b7fa  lea     r8, [rbp+var_40]
0x18013b7fe  lea     rdx, aUpdateapiDll_0; "UpdateAPI.dll"
0x18013b805  lea     rcx, byte_1803AC168
0x18013b80c  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x18013b811  mov     ebx, eax
0x18013b813  test    eax, eax
0x18013b815  jns     short loc_18013B892
0x18013b817  mov     [rbp+var_20], eax
0x18013b81a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b821  test    rcx, rcx
0x18013b824  jz      short loc_18013B865
0x18013b826  lea     r9, aFailedToGetPat_0; "Failed to get path to UpdateAPI.dll"
0x18013b82d  mov     edi, 3
0x18013b832  mov     r8d, edi
0x18013b835  xor     edx, edx
0x18013b837  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013b83c  lea     rax, [rbp+var_20]
0x18013b840  mov     qword ptr [rbp+var_50], rax
0x18013b844  lea     rax, [rbp+var_50]
0x18013b848  mov     qword ptr [rsp+80h+var_60], rax; int
0x18013b84d  lea     r9, asc_1802C6678; ": {}"
0x18013b854  mov     r8d, edi
0x18013b857  mov     dl, 1
0x18013b859  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b860  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013b865  mov     rcx, [rbp+18h]; this
0x18013b869  mov     r9d, ebx; char *
0x18013b86c  lea     r8, aOnecoreBaseSer_29; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x18013b873  mov     edx, 2Eh ; '.'; void *
0x18013b878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b87d  nop
0x18013b87e  mov     rcx, [rbp+var_30]
0x18013b882  test    rcx, rcx
0x18013b885  jz      short loc_18013B88D
0x18013b887  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18013b88c  nop
0x18013b88d  jmp     loc_18013B6E5
0x18013b892  mov     rbx, [rbp+var_30]
0x18013b896  mov     rcx, rbx
0x18013b899  call    DoesFileExist
0x18013b89e  test    eax, eax
0x18013b8a0  jz      short loc_18013B90B
0x18013b8a2  mov     rdx, rbx
0x18013b8a5  lea     rcx, [rbp+var_48]
0x18013b8a9  call    SczAllocFromSz
0x18013b8ae  mov     edi, eax
0x18013b8b0  test    eax, eax
0x18013b8b2  jns     loc_18013B9B9
0x18013b8b8  mov     rcx, [rbp+18h]; this
0x18013b8bc  mov     r9d, eax; char *
0x18013b8bf  lea     r8, aOnecoreBaseSer_29; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x18013b8c6  mov     edx, 32h ; '2'; void *
0x18013b8cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b8d0  nop
0x18013b8d1  test    rbx, rbx
0x18013b8d4  jz      short loc_18013B8DF
0x18013b8d6  mov     rcx, rbx
0x18013b8d9  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18013b8de  nop
0x18013b8df  mov     rcx, [rbp+var_48]
0x18013b8e3  test    rcx, rcx
0x18013b8e6  jz      short loc_18013B8F2
0x18013b8e8  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18013b8ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013b8f1  nop
0x18013b8f2  mov     rcx, [rbp+lpLibFileName]
0x18013b8f6  test    rcx, rcx
0x18013b8f9  jz      short loc_18013B904
0x18013b8fb  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18013b8ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013b904  mov     eax, edi
0x18013b906  jmp     loc_18013BF48
0x18013b90b  lea     r8, [rbp+var_48]; struct AutoScz *
0x18013b90f  lea     rdx, aSystem32Update; "System32\\UpdateAPI.dll"
0x18013b916  mov     rcx, rdi; this
0x18013b919  call    ?GetWindowsRelativePath@DeviceContext@@QEBAJPEB_WPEAVAutoScz@@@Z; DeviceContext::GetWindowsRelativePath(wchar_t const *,AutoScz *)
0x18013b91e  mov     r14d, eax
0x18013b921  test    eax, eax
0x18013b923  jns     loc_18013B9B9
0x18013b929  mov     [rbp+var_20], eax
0x18013b92c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b933  test    rcx, rcx
0x18013b936  jz      short loc_18013B977
0x18013b938  lea     r9, aFailedGettingW_3; "Failed getting windows relative path"
0x18013b93f  mov     edi, 3
0x18013b944  mov     r8d, edi
0x18013b947  xor     edx, edx
0x18013b949  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013b94e  lea     rax, [rbp+var_20]
0x18013b952  mov     qword ptr [rbp+var_50], rax
0x18013b956  lea     rax, [rbp+var_50]
0x18013b95a  mov     qword ptr [rsp+80h+var_60], rax; int
0x18013b95f  lea     r9, asc_1802C6678; ": {}"
0x18013b966  mov     r8d, edi
0x18013b969  mov     dl, 1
0x18013b96b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b972  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013b977  mov     rcx, [rbp+18h]; this
0x18013b97b  mov     r9d, r14d; char *
0x18013b97e  lea     r8, aOnecoreBaseSer_29; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x18013b985  mov     edx, 37h ; '7'; void *
0x18013b98a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b98f  nop
0x18013b990  test    rbx, rbx
0x18013b993  jz      short loc_18013B99E
0x18013b995  mov     rcx, rbx
0x18013b998  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18013b99d  nop
0x18013b99e  mov     rcx, [rbp+var_48]
0x18013b9a2  test    rcx, rcx
0x18013b9a5  jz      loc_18013B74C
0x18013b9ab  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18013b9af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013b9b4  jmp     loc_18013B74C
0x18013b9b9  test    rbx, rbx
0x18013b9bc  jz      short loc_18013B9C7
0x18013b9be  mov     rcx, rbx
0x18013b9c1  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18013b9c6  nop
0x18013b9c7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013b9ce  test    rcx, rcx
0x18013b9d1  jz      short loc_18013B9F1
0x18013b9d3  lea     rax, [rbp+lpLibFileName]
0x18013b9d7  mov     qword ptr [rsp+80h+var_60], rax
0x18013b9dc  lea     r9, aLoadingDrvserv; "Loading drvservicing: {0}"
0x18013b9e3  mov     r8d, 1
0x18013b9e9  mov     dl, r8b
0x18013b9ec  call    ??$LogNumObjects@VAutoScz@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBVAutoScz@@@Z; LogAdapter::Logger::LogNumObjects<AutoScz>(bool,LogAdapter::LogLevel,char const * const,AutoScz const &)
0x18013b9f1  mov     ebx, 8
0x18013b9f6  mov     r8d, ebx; dwFlags
0x18013b9f9  xor     edx, edx; hFile
0x18013b9fb  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18013b9ff  call    cs:__imp_LoadLibraryExW
0x18013ba06  nop     dword ptr [rax+rax+00h]
0x18013ba0b  cmp     qword ptr [rsi], 0
0x18013ba0f  jnz     loc_18013BF6D
0x18013ba15  mov     [rsi], rax
0x18013ba18  test    rax, rax
0x18013ba1b  jnz     loc_18013BC40
0x18013ba21  call    cs:__imp_GetLastError
0x18013ba28  nop     dword ptr [rax+rax+00h]
0x18013ba2d  mov     ebx, eax
0x18013ba2f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013ba36  test    rcx, rcx
0x18013ba39  jz      loc_18013BC02
0x18013ba3f  lea     r9, aFailedToLoadDr; "Failed to load DrvServicing DLL"
0x18013ba46  mov     edi, 3
0x18013ba4b  mov     r8d, edi
0x18013ba4e  xor     edx, edx
0x18013ba50  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013ba55  test    ebx, ebx
0x18013ba57  jg      loc_18013BBCE
0x18013ba5d  mov     eax, ebx
0x18013ba5f  jmp     loc_18013BBD6
0x18013ba64  cmp     byte ptr [rdi], 0
0x18013ba67  jz      loc_18013BF34
0x18013ba6d  cmp     qword ptr [rdi+18h], 0
0x18013ba72  jz      loc_18013BF34
0x18013ba78  lea     rbx, [rdi+8]
0x18013ba7c  cmp     qword ptr [rbx+18h], 7
0x18013ba81  jbe     short loc_18013BA88
0x18013ba83  mov     rax, [rbx]
0x18013ba86  jmp     short loc_18013BA8B
0x18013ba88  mov     rax, rbx
0x18013ba8b  test    rax, rax
  ... truncated ...
```

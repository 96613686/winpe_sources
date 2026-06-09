# CPnPClient::Initialize(DeviceContext *)

- ea: `0x1800e584c`
- end: `0x1800e61e0`
- name: `?Initialize@CPnPClient@@QEAAJPEAVDeviceContext@@@Z`
- size: `2452`
- prototype: `int(CPnPClient *__hidden this, struct DeviceContext *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008aff4`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800296a4`
- `0x18002e3a4`
- `0x1800369c0`
- `0x18003d278`
- `0x18003ddc8`
- `0x18003df98`
- `0x180042764`
- `0x18004d970`
- `0x180050fd0`
- `0x180051984`
- `0x1800e584c`
- `0x1801133b8`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e611e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e611e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e5eb2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e5f4f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e5fec`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e6109`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e5eb2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e5f4f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e5fec`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e6109`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e5c67`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e602d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e5c67`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e602d`

## string_xrefs

- `0x1800e5a66`: `UpdateAPI.dll`
- `0x1800e5e15`: `UpdateAPI.dll`
- `0x1800e60ff`: `GetRootPath`
- `0x1800e5d2a`: `Failed getting external stack path`
- `0x1800e59f7`: `Failed getting windows relative path`
- `0x1800e5ba0`: `Failed getting windows relative path`
- `0x1800e606b`: `Failed to load UpdateAPI DLL`
- `0x1800e59d2`: `System32\drvservicing.dll`
- `0x1800e58e6`: `Failed to get path to drvservicing.dll`
- `0x1800e58ba`: `drvservicing.dll`
- `0x1800e5d86`: `drvservicing.dll`
- `0x1800e5ca7`: `Failed to load DrvServicing DLL`
- `0x1800e5b77`: `System32\UpdateAPI.dll`
- `0x1800e5a8e`: `Failed to get path to UpdateAPI.dll`
- `0x1800e5f7e`: `Failed to get proc address for FreeInstalledDriverPackageInfo.`
- `0x1800e5f45`: `FreeInstalledDriverPackageInfo`
- `0x1800e5ee1`: `Failed to get proc address for GetInstalledDriverPackageInfo.`
- `0x1800e5ea8`: `GetInstalledDriverPackageInfo`
- `0x1800e6138`: `Failed to get proc address for GetRootPath.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPnPClient::Initialize(CPnPClient *this, struct DeviceContext *a2)
{
  int Win32PathOfSiblingFile; // eax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rbx
  int v9; // eax
  unsigned int v10; // r14d
  int WindowsRelativePath; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // edi
  WCHAR *v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  HMODULE Library; // rax
  signed int LastError; // ebx
  __int64 v24; // rdx
  unsigned int v25; // eax
  char *v26; // rbx
  char *v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  WCHAR *v34; // rcx
  FARPROC ProcAddress; // rax
  __int64 v36; // rdx
  unsigned int v37; // eax
  FARPROC v38; // rax
  __int64 v39; // rdx
  unsigned int v40; // eax
  FARPROC v41; // rax
  LPCWSTR v42; // rbx
  HMODULE v43; // rax
  signed int v44; // esi
  __int64 v45; // rdx
  unsigned int v46; // eax
  __int64 v47; // rdx
  FARPROC v48; // rax
  __int64 v49; // rdx
  unsigned int v50; // eax
  unsigned int *v51; // [rsp+20h] [rbp-60h]
  unsigned int v52[2]; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR v53; // [rsp+38h] [rbp-48h] BYREF
  __int128 v54; // [rsp+40h] [rbp-40h] BYREF
  __int64 v55; // [rsp+50h] [rbp-30h]
  __int64 v56; // [rsp+58h] [rbp-28h]
  unsigned int v57; // [rsp+60h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v56 = -2;
  lpLibFileName = 0;
  v53 = 0;
  if ( *((_DWORD *)a2 + 1) )
    return 0;
  if ( InMobile() )
  {
    v54 = 0;
    v55 = 0;
    Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(&byte_18023FAC4, L"drvservicing.dll", &v54);
    v5 = Win32PathOfSiblingFile;
    if ( Win32PathOfSiblingFile < 0 )
    {
      v57 = Win32PathOfSiblingFile;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get path to drvservicing.dll");
        *(_QWORD *)v52 = &v57;
        v51 = v52;
        LOBYTE(v6) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v6,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
        (const char *)(unsigned int)v5,
        (int)v51);
      if ( v55 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v55);
LABEL_8:
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4));
      return (unsigned int)v5;
    }
    v8 = v55;
    if ( (unsigned int)DoesFileExist(v55) )
    {
      v9 = SczAllocFromSz(&lpLibFileName);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)(unsigned int)v9,
          (int)v51);
        if ( v8 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v8);
        goto LABEL_15;
      }
    }
    else
    {
      WindowsRelativePath = DeviceContext::GetWindowsRelativePath(
                              a2,
                              L"System32\\drvservicing.dll",
                              (struct AutoScz *)&lpLibFileName);
      v10 = WindowsRelativePath;
      if ( WindowsRelativePath < 0 )
      {
        v57 = WindowsRelativePath;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed getting windows relative path");
          *(_QWORD *)v52 = &v57;
          v51 = v52;
          LOBYTE(v12) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v12,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)v10,
          (int)v51);
        if ( v8 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v8);
        goto LABEL_15;
      }
    }
    v13 = Windows::COM::GetWin32PathOfSiblingFile(&byte_18023FAC4, L"UpdateAPI.dll", &v54);
    v5 = v13;
    if ( v13 < 0 )
    {
      v57 = v13;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get path to UpdateAPI.dll");
        *(_QWORD *)v52 = &v57;
        v51 = v52;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v14,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
        (const char *)(unsigned int)v5,
        (int)v51);
      if ( v55 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v55);
      goto LABEL_8;
    }
    v15 = v55;
    if ( (unsigned int)DoesFileExist(v55) )
    {
      v16 = SczAllocFromSz(&v53);
      v18 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)(unsigned int)v16,
          (int)v51);
        if ( v15 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v15);
        if ( !v53 )
          goto LABEL_37;
        v19 = (WCHAR *)(v53 - 4);
        goto LABEL_36;
      }
    }
    else
    {
      v20 = DeviceContext::GetWindowsRelativePath(a2, L"System32\\UpdateAPI.dll", (struct AutoScz *)&v53);
      v10 = v20;
      if ( v20 < 0 )
      {
        v57 = v20;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed getting windows relative path");
          *(_QWORD *)v52 = &v57;
          v51 = v52;
          LOBYTE(v21) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v21,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)v10,
          (int)v51);
        if ( v15 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v15);
        if ( v53 )
          operator delete((void *)(v53 - 4));
        goto LABEL_15;
      }
    }
    if ( v15 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v15);
    goto LABEL_49;
  }
  if ( !*(_BYTE *)a2 || !*((_QWORD *)a2 + 3) )
    goto LABEL_133;
  v26 = (char *)a2 + 8;
  if ( !(*((_QWORD *)a2 + 4) <= 7u ? (struct DeviceContext *)((char *)a2 + 8) : *(struct DeviceContext **)v26) )
    goto LABEL_133;
  if ( *((_QWORD *)a2 + 4) <= 7u )
    v28 = (char *)a2 + 8;
  else
    v28 = *(char **)v26;
  v29 = SczAllocFromSzAndEnsureBackslash(&lpLibFileName, v28);
  v10 = v29;
  if ( v29 < 0 )
  {
    v57 = v29;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed getting external stack path");
      *(_QWORD *)v52 = &v57;
      v51 = v52;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v30,
        3,
        ": {}");
    }
    v31 = 61;
    goto LABEL_69;
  }
  v10 = SczAllocConcatSz(&lpLibFileName, L"drvservicing.dll");
  if ( (v10 & 0x80000000) != 0 )
  {
    v31 = 63;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
      (const char *)v10,
      (int)v51);
LABEL_15:
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4));
    return v10;
  }
  if ( !(unsigned int)DoesFileExist(lpLibFileName) )
    goto LABEL_133;
  if ( *(_BYTE *)a2 && *((_QWORD *)a2 + 3) )
  {
    if ( *((_QWORD *)a2 + 4) > 7u )
      v26 = *(char **)v26;
  }
  else
  {
    v26 = 0;
  }
  v5 = SczAllocFromSzAndEnsureBackslash(&v53, v26);
  if ( v5 < 0 )
  {
    v32 = 70;
LABEL_80:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
      (const char *)(unsigned int)v5,
      (int)v51);
    goto LABEL_81;
  }
  v5 = SczAllocConcatSz(&v53, L"UpdateAPI.dll");
  if ( v5 < 0 )
  {
    v32 = 72;
    goto LABEL_80;
  }
LABEL_49:
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LOBYTE(v17) = 1;
    LogAdapter::Logger::LogNumObjects<AutoScz>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v17,
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
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load DrvServicing DLL");
      if ( LastError > 0 )
        v25 = (unsigned __int16)LastError | 0x80070000;
      else
        v25 = LastError;
      v57 = v25;
      *(_QWORD *)v52 = &v57;
      v51 = v52;
      LOBYTE(v24) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v24,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v33 = 85;
LABEL_89:
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v33,
             (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
             (const char *)(unsigned int)LastError,
             (unsigned int)v51);
LABEL_81:
      if ( v53 )
        operator delete((void *)(v53 - 4));
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
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get proc address for GetInstalledDriverPackageInfo.");
      if ( LastError > 0 )
        v37 = (unsigned __int16)LastError | 0x80070000;
      else
        v37 = LastError;
      v57 = v37;
      *(_QWORD *)v52 = &v57;
      v51 = v52;
      LOBYTE(v36) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v36,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v33 = 89;
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
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get proc address for FreeInstalledDriverPackageInfo.");
      if ( LastError > 0 )
        v40 = (unsigned __int16)LastError | 0x80070000;
      else
        v40 = LastError;
      v57 = v40;
      *(_QWORD *)v52 = &v57;
      v51 = v52;
      LOBYTE(v39) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v39,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v33 = 93;
      goto LABEL_89;
    }
LABEL_90:
    if ( !v53 )
      goto LABEL_133;
    v34 = (WCHAR *)(v53 - 4);
    goto LABEL_92;
  }
  v41 = GetProcAddress(*(HMODULE *)this, "SetLogger");
  if ( v41 )
    ((void (__fastcall *)(_QWORD))v41)(*(_QWORD *)&LogAdapter::g_Logger);
  else
    CBSWdsLog(0x4000000, 0, 0, "Failed to get proc address for SetLogger, continuing without DrvServicing logging.");
  v42 = v53;
  v43 = LoadLibraryExW(v53, 0, 8u);
  if ( *((_QWORD *)this + 3) )
  {
LABEL_136:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800E61DFLL);
  }
  *((_QWORD *)this + 3) = v43;
  if ( v43 )
  {
    v48 = GetProcAddress(v43, "GetRootPath");
    *((_QWORD *)this + 4) = v48;
    if ( !v48 )
    {
      v44 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for GetRootPath.");
        if ( v44 > 0 )
          v50 = (unsigned __int16)v44 | 0x80070000;
        else
          v50 = v44;
        v57 = v50;
        *(_QWORD *)v52 = &v57;
        v51 = v52;
        LOBYTE(v49) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v49,
          3,
          ": {0}");
      }
      if ( v44 )
      {
        v47 = 109;
        goto LABEL_121;
      }
    }
    goto LABEL_123;
  }
  v44 = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load UpdateAPI DLL");
    if ( v44 > 0 )
      v46 = (unsigned __int16)v44 | 0x80070000;
    else
      v46 = v44;
    v57 = v46;
    *(_QWORD *)v52 = &v57;
    v51 = v52;
    LOBYTE(v45) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v45,
      3,
      ": {0}");
  }
  if ( !v44 )
  {
LABEL_123:
    if ( v42 )
    {
      v34 = (WCHAR *)(v42 - 4);
LABEL_92:
      operator delete(v34);
    }
LABEL_133:
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4));
    return 0;
  }
  v47 = 106;
LABEL_121:
  v18 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v47,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cpnpclient.cpp",
          (const char *)(unsigned int)v44,
          (unsigned int)v51);
  if ( !v42 )
    goto LABEL_37;
  v19 = (WCHAR *)(v42 - 4);
LABEL_36:
  operator delete(v19);
LABEL_37:
  if ( lpLibFileName )
    operator delete((void *)(lpLibFileName - 4));
  return v18;
}

```

## disassembly

```asm
0x1800e584c  mov     rax, rsp
0x1800e584f  push    rbp
0x1800e5850  push    rdi
0x1800e5851  push    r14
0x1800e5853  mov     rbp, rsp
0x1800e5856  sub     rsp, 80h
0x1800e585d  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x1800e5865  mov     [rax+18h], rbx
0x1800e5869  mov     [rax+20h], rsi
0x1800e586d  mov     rax, cs:__security_cookie
0x1800e5874  xor     rax, rsp
0x1800e5877  mov     [rbp+var_10], rax
0x1800e587b  mov     rdi, rdx
0x1800e587e  mov     rsi, rcx
0x1800e5881  mov     [rbp+lpLibFileName], 0
0x1800e5889  mov     [rbp+var_48], 0
0x1800e5891  cmp     dword ptr [rdx+4], 0
0x1800e5895  jz      short loc_1800E589C
0x1800e5897  jmp     loc_1800E61AE
0x1800e589c  call    ?InMobile@@YA_NXZ; InMobile(void)
0x1800e58a1  test    al, al
0x1800e58a3  jz      loc_1800E5CCC
0x1800e58a9  xorps   xmm0, xmm0
0x1800e58ac  xor     eax, eax
0x1800e58ae  movups  [rbp+var_40], xmm0
0x1800e58b2  mov     [rbp+var_30], rax
0x1800e58b6  lea     r8, [rbp+var_40]
0x1800e58ba  lea     rdx, aDrvservicingDl; "drvservicing.dll"
0x1800e58c1  lea     rcx, byte_18023FAC4
0x1800e58c8  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x1800e58cd  mov     ebx, eax
0x1800e58cf  test    eax, eax
0x1800e58d1  jns     loc_1800E5966
0x1800e58d7  mov     [rbp+var_20], eax
0x1800e58da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e58e1  test    rcx, rcx
0x1800e58e4  jz      short loc_1800E5925
0x1800e58e6  lea     r9, aFailedToGetPat_1; "Failed to get path to drvservicing.dll"
0x1800e58ed  mov     edi, 3
0x1800e58f2  mov     r8d, edi
0x1800e58f5  xor     edx, edx
0x1800e58f7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e58fc  lea     rax, [rbp+var_20]
0x1800e5900  mov     qword ptr [rbp+var_50], rax
0x1800e5904  lea     rax, [rbp+var_50]
0x1800e5908  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800e590d  lea     r9, asc_1801CAFB4; ": {}"
0x1800e5914  mov     r8d, edi
0x1800e5917  mov     dl, 1
0x1800e5919  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5920  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5925  mov     rcx, [rbp+18h]; this
0x1800e5929  mov     r9d, ebx; char *
0x1800e592c  lea     r8, aOnecoreBaseSer_31; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x1800e5933  mov     edx, 1Dh; void *
0x1800e5938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e593d  nop
0x1800e593e  mov     rcx, [rbp+var_30]
0x1800e5942  test    rcx, rcx
0x1800e5945  jz      short loc_1800E594D
0x1800e5947  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e594c  nop
0x1800e594d  mov     rcx, [rbp+lpLibFileName]
0x1800e5951  test    rcx, rcx
0x1800e5954  jz      short loc_1800E595F
0x1800e5956  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800e595a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e595f  mov     eax, ebx
0x1800e5961  jmp     loc_1800E61B0
0x1800e5966  mov     rbx, [rbp+var_30]
0x1800e596a  mov     rcx, rbx
0x1800e596d  call    DoesFileExist
0x1800e5972  test    eax, eax
0x1800e5974  jz      short loc_1800E59CE
0x1800e5976  mov     rdx, rbx
0x1800e5979  lea     rcx, [rbp+lpLibFileName]
0x1800e597d  call    SczAllocFromSz
0x1800e5982  mov     r14d, eax
0x1800e5985  test    eax, eax
0x1800e5987  jns     loc_1800E5A62
0x1800e598d  mov     rcx, [rbp+18h]; this
0x1800e5991  mov     r9d, eax; char *
0x1800e5994  lea     r8, aOnecoreBaseSer_31; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x1800e599b  mov     edx, 21h ; '!'; void *
0x1800e59a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e59a5  nop
0x1800e59a6  test    rbx, rbx
0x1800e59a9  jz      short loc_1800E59B4
0x1800e59ab  mov     rcx, rbx
0x1800e59ae  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e59b3  nop
0x1800e59b4  mov     rcx, [rbp+lpLibFileName]
0x1800e59b8  test    rcx, rcx
0x1800e59bb  jz      short loc_1800E59C6
0x1800e59bd  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800e59c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e59c6  mov     eax, r14d
0x1800e59c9  jmp     loc_1800E61B0
0x1800e59ce  lea     r8, [rbp+lpLibFileName]; struct AutoScz *
0x1800e59d2  lea     rdx, aSystem32Drvser; "System32\\drvservicing.dll"
0x1800e59d9  mov     rcx, rdi; this
0x1800e59dc  call    ?GetWindowsRelativePath@DeviceContext@@QEBAJPEB_WPEAVAutoScz@@@Z; DeviceContext::GetWindowsRelativePath(wchar_t const *,AutoScz *)
0x1800e59e1  mov     r14d, eax
0x1800e59e4  test    eax, eax
0x1800e59e6  jns     short loc_1800E5A62
0x1800e59e8  mov     [rbp+var_20], eax
0x1800e59eb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e59f2  test    rcx, rcx
0x1800e59f5  jz      short loc_1800E5A36
0x1800e59f7  lea     r9, aFailedGettingW_3; "Failed getting windows relative path"
0x1800e59fe  mov     edi, 3
0x1800e5a03  mov     r8d, edi
0x1800e5a06  xor     edx, edx
0x1800e5a08  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5a0d  lea     rax, [rbp+var_20]
0x1800e5a11  mov     qword ptr [rbp+var_50], rax
0x1800e5a15  lea     rax, [rbp+var_50]
0x1800e5a19  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800e5a1e  lea     r9, asc_1801CAFB4; ": {}"
0x1800e5a25  mov     r8d, edi
0x1800e5a28  mov     dl, 1
0x1800e5a2a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a31  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5a36  mov     rcx, [rbp+18h]; this
0x1800e5a3a  mov     r9d, r14d; char *
0x1800e5a3d  lea     r8, aOnecoreBaseSer_31; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x1800e5a44  mov     edx, 26h ; '&'; void *
0x1800e5a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5a4e  nop
0x1800e5a4f  test    rbx, rbx
0x1800e5a52  jz      short loc_1800E5A5D
0x1800e5a54  mov     rcx, rbx
0x1800e5a57  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e5a5c  nop
0x1800e5a5d  jmp     loc_1800E59B4
0x1800e5a62  lea     r8, [rbp+var_40]
0x1800e5a66  lea     rdx, aUpdateapiDll_0; "UpdateAPI.dll"
0x1800e5a6d  lea     rcx, byte_18023FAC4
0x1800e5a74  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x1800e5a79  mov     ebx, eax
0x1800e5a7b  test    eax, eax
0x1800e5a7d  jns     short loc_1800E5AFA
0x1800e5a7f  mov     [rbp+var_20], eax
0x1800e5a82  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5a89  test    rcx, rcx
0x1800e5a8c  jz      short loc_1800E5ACD
0x1800e5a8e  lea     r9, aFailedToGetPat_0; "Failed to get path to UpdateAPI.dll"
0x1800e5a95  mov     edi, 3
0x1800e5a9a  mov     r8d, edi
0x1800e5a9d  xor     edx, edx
0x1800e5a9f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5aa4  lea     rax, [rbp+var_20]
0x1800e5aa8  mov     qword ptr [rbp+var_50], rax
0x1800e5aac  lea     rax, [rbp+var_50]
0x1800e5ab0  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800e5ab5  lea     r9, asc_1801CAFB4; ": {}"
0x1800e5abc  mov     r8d, edi
0x1800e5abf  mov     dl, 1
0x1800e5ac1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5ac8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5acd  mov     rcx, [rbp+18h]; this
0x1800e5ad1  mov     r9d, ebx; char *
0x1800e5ad4  lea     r8, aOnecoreBaseSer_31; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x1800e5adb  mov     edx, 2Eh ; '.'; void *
0x1800e5ae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5ae5  nop
0x1800e5ae6  mov     rcx, [rbp+var_30]
0x1800e5aea  test    rcx, rcx
0x1800e5aed  jz      short loc_1800E5AF5
0x1800e5aef  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e5af4  nop
0x1800e5af5  jmp     loc_1800E594D
0x1800e5afa  mov     rbx, [rbp+var_30]
0x1800e5afe  mov     rcx, rbx
0x1800e5b01  call    DoesFileExist
0x1800e5b06  test    eax, eax
0x1800e5b08  jz      short loc_1800E5B73
0x1800e5b0a  mov     rdx, rbx
0x1800e5b0d  lea     rcx, [rbp+var_48]
0x1800e5b11  call    SczAllocFromSz
0x1800e5b16  mov     edi, eax
0x1800e5b18  test    eax, eax
0x1800e5b1a  jns     loc_1800E5C21
0x1800e5b20  mov     rcx, [rbp+18h]; this
0x1800e5b24  mov     r9d, eax; char *
0x1800e5b27  lea     r8, aOnecoreBaseSer_31; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x1800e5b2e  mov     edx, 32h ; '2'; void *
0x1800e5b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5b38  nop
0x1800e5b39  test    rbx, rbx
0x1800e5b3c  jz      short loc_1800E5B47
0x1800e5b3e  mov     rcx, rbx
0x1800e5b41  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e5b46  nop
0x1800e5b47  mov     rcx, [rbp+var_48]
0x1800e5b4b  test    rcx, rcx
0x1800e5b4e  jz      short loc_1800E5B5A
0x1800e5b50  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800e5b54  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e5b59  nop
0x1800e5b5a  mov     rcx, [rbp+lpLibFileName]
0x1800e5b5e  test    rcx, rcx
0x1800e5b61  jz      short loc_1800E5B6C
0x1800e5b63  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800e5b67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e5b6c  mov     eax, edi
0x1800e5b6e  jmp     loc_1800E61B0
0x1800e5b73  lea     r8, [rbp+var_48]; struct AutoScz *
0x1800e5b77  lea     rdx, aSystem32Update; "System32\\UpdateAPI.dll"
0x1800e5b7e  mov     rcx, rdi; this
0x1800e5b81  call    ?GetWindowsRelativePath@DeviceContext@@QEBAJPEB_WPEAVAutoScz@@@Z; DeviceContext::GetWindowsRelativePath(wchar_t const *,AutoScz *)
0x1800e5b86  mov     r14d, eax
0x1800e5b89  test    eax, eax
0x1800e5b8b  jns     loc_1800E5C21
0x1800e5b91  mov     [rbp+var_20], eax
0x1800e5b94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5b9b  test    rcx, rcx
0x1800e5b9e  jz      short loc_1800E5BDF
0x1800e5ba0  lea     r9, aFailedGettingW_3; "Failed getting windows relative path"
0x1800e5ba7  mov     edi, 3
0x1800e5bac  mov     r8d, edi
0x1800e5baf  xor     edx, edx
0x1800e5bb1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5bb6  lea     rax, [rbp+var_20]
0x1800e5bba  mov     qword ptr [rbp+var_50], rax
0x1800e5bbe  lea     rax, [rbp+var_50]
0x1800e5bc2  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800e5bc7  lea     r9, asc_1801CAFB4; ": {}"
0x1800e5bce  mov     r8d, edi
0x1800e5bd1  mov     dl, 1
0x1800e5bd3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5bda  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800e5bdf  mov     rcx, [rbp+18h]; this
0x1800e5be3  mov     r9d, r14d; char *
0x1800e5be6  lea     r8, aOnecoreBaseSer_31; "onecore\\base\\servicing\\arbiter\\cpnp"...
0x1800e5bed  mov     edx, 37h ; '7'; void *
0x1800e5bf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5bf7  nop
0x1800e5bf8  test    rbx, rbx
0x1800e5bfb  jz      short loc_1800E5C06
0x1800e5bfd  mov     rcx, rbx
0x1800e5c00  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e5c05  nop
0x1800e5c06  mov     rcx, [rbp+var_48]
0x1800e5c0a  test    rcx, rcx
0x1800e5c0d  jz      loc_1800E59B4
0x1800e5c13  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800e5c17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e5c1c  jmp     loc_1800E59B4
0x1800e5c21  test    rbx, rbx
0x1800e5c24  jz      short loc_1800E5C2F
0x1800e5c26  mov     rcx, rbx
0x1800e5c29  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800e5c2e  nop
0x1800e5c2f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5c36  test    rcx, rcx
0x1800e5c39  jz      short loc_1800E5C59
0x1800e5c3b  lea     rax, [rbp+lpLibFileName]
0x1800e5c3f  mov     qword ptr [rsp+80h+var_60], rax
0x1800e5c44  lea     r9, aLoadingDrvserv; "Loading drvservicing: {0}"
0x1800e5c4b  mov     r8d, 1
0x1800e5c51  mov     dl, r8b
0x1800e5c54  call    ??$LogNumObjects@VAutoScz@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBVAutoScz@@@Z; LogAdapter::Logger::LogNumObjects<AutoScz>(bool,LogAdapter::LogLevel,char const * const,AutoScz const &)
0x1800e5c59  mov     ebx, 8
0x1800e5c5e  mov     r8d, ebx; dwFlags
0x1800e5c61  xor     edx, edx; hFile
0x1800e5c63  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800e5c67  call    cs:__imp_LoadLibraryExW
0x1800e5c6e  nop     dword ptr [rax+rax+00h]
0x1800e5c73  cmp     qword ptr [rsi], 0
0x1800e5c77  jnz     loc_1800E61D5
0x1800e5c7d  mov     [rsi], rax
0x1800e5c80  test    rax, rax
0x1800e5c83  jnz     loc_1800E5EA8
0x1800e5c89  call    cs:__imp_GetLastError
0x1800e5c90  nop     dword ptr [rax+rax+00h]
0x1800e5c95  mov     ebx, eax
0x1800e5c97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800e5c9e  test    rcx, rcx
0x1800e5ca1  jz      loc_1800E5E6A
0x1800e5ca7  lea     r9, aFailedToLoadDr; "Failed to load DrvServicing DLL"
0x1800e5cae  mov     edi, 3
0x1800e5cb3  mov     r8d, edi
0x1800e5cb6  xor     edx, edx
0x1800e5cb8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800e5cbd  test    ebx, ebx
0x1800e5cbf  jg      loc_1800E5E36
0x1800e5cc5  mov     eax, ebx
0x1800e5cc7  jmp     loc_1800E5E3E
0x1800e5ccc  cmp     byte ptr [rdi], 0
0x1800e5ccf  jz      loc_1800E619C
0x1800e5cd5  cmp     qword ptr [rdi+18h], 0
0x1800e5cda  jz      loc_1800E619C
0x1800e5ce0  lea     rbx, [rdi+8]
0x1800e5ce4  cmp     qword ptr [rbx+18h], 7
0x1800e5ce9  jbe     short loc_1800E5CF0
0x1800e5ceb  mov     rax, [rbx]
0x1800e5cee  jmp     short loc_1800E5CF3
0x1800e5cf0  mov     rax, rbx
0x1800e5cf3  test    rax, rax
  ... truncated ...
```

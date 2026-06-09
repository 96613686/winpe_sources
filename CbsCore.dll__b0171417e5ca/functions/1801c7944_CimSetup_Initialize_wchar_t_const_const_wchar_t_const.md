# CimSetup::Initialize(wchar_t const * const,wchar_t const *)

- ea: `0x1801c7944`
- end: `0x1801c8abb`
- name: `?Initialize@CimSetup@@QEAAJQEB_WPEB_W@Z`
- size: `4471`
- prototype: `__int64 __fastcall(CimSetup *__hidden this, const wchar_t *const, const wchar_t *)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c9494`
- `0x1800dc9c0`
- `0x1801da358`

## callees

- `0x18000b46c`
- `0x18000e780`
- `0x180011a14`
- `0x180013250`
- `0x1800150c0`
- `0x180015420`
- `0x180023ca8`
- `0x1800261e0`
- `0x180049ec0`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b7304`
- `0x1800eb500`
- `0x1800eb50c`
- `0x1800eb920`
- `0x1800ec920`
- `0x180109588`
- `0x1801252c8`
- `0x180182144`
- `0x1801c098c`
- `0x1801c48dc`
- `0x1801c490c`
- `0x1801c7944`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801c820a`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801c820a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c7d7c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c8029`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c86fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c7d7c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c8029`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801c86fa`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801c7cb8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801c7f67`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801c7cb8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801c7f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c865b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c865b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c8712`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1801c8636`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1801c8636`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1801c7a08`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1801c7a08`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801c82d9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801c82d9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801c843f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1801c843f`

## string_xrefs

- `0x1801c7f00`: `PayloadCimTypes.Length:{} m_cimPaths.GetSize:{} are not equal`
- `0x1801c7f5c`: `cimfs.dll`
- `0x1801c7fa9`: `Failed to load CimFS.dll.`
- `0x1801c8022`: `CimMergeMountImage`
- `0x1801c8064`: `Failed to get proc address for CimMergeMountImage`
- `0x1801c832c`: `Failed to split path for cim file: {}`
- `0x1801c83d6`: `Failed to mount merged cim images.`
- `0x1801c8481`: `Failed to create the target packages path`
- `0x1801c84f8`: `Failed to create the target store path`
- `0x1801c856f`: `Failed to format source store path`
- `0x1801c85e6`: `Failed to format source packages path`
- `0x1801c862f`: `bindfltapi.dll`
- `0x1801c867a`: `Failed to load bindfltapi.dll.`
- `0x1801c7a3b`: `Failed to get system windows directory`
- `0x1801c7b31`: `winsxs\temp`
- `0x1801c89f8`: `Failed to format exception path for {}`
- `0x1801c8999`: `Failed to format exception path`
- `0x1801c7cad`: `turbostack.dll`
- `0x1801c7cfe`: `Failed to load turbostack.dll.`

## pseudocode

```c
__int64 __fastcall CimSetup::Initialize(CimSetup *this, const wchar_t *const a2, const wchar_t *a3)
{
  unsigned __int64 v3; // r15
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 *v8; // r14
  int v9; // eax
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // ebx
  unsigned int v12; // eax
  OLECHAR *v13; // rbx
  __int64 v14; // r9
  __int64 v15; // r8
  int CimPayloadFiles; // eax
  __int64 v17; // rdx
  HMODULE Library; // rax
  signed int v19; // ebx
  unsigned int v20; // eax
  __int64 v21; // rdx
  FARPROC ProcAddress; // rax
  unsigned int v23; // eax
  int v24; // eax
  int v25; // r8d
  __int64 v26; // rdx
  __int64 v27; // rax
  HMODULE v28; // rax
  signed int v29; // ebx
  unsigned int v30; // eax
  __int64 v31; // rdx
  FARPROC v32; // r13
  unsigned int v33; // eax
  _QWORD *v34; // rbx
  __int64 v35; // rax
  int v36; // eax
  const struct std::nothrow_t *v37; // rdx
  unsigned __int64 v38; // rax
  __int64 v39; // r12
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rdx
  HRESULT Guid; // eax
  __int64 v45; // r9
  __int64 v46; // rdx
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  HMODULE LibraryW; // rax
  HMODULE v53; // rcx
  signed int v54; // edi
  unsigned int v55; // eax
  __int64 v56; // rdx
  FARPROC v57; // rax
  __int64 (__fastcall *v58)(_QWORD, _QWORD, _QWORD, _QWORD); // r14
  unsigned int v59; // eax
  const struct std::nothrow_t *v60; // rdx
  int v61; // eax
  int v62; // eax
  const struct std::nothrow_t *v63; // rdx
  __int64 v65; // rdx
  unsigned int DirCount; // [rsp+20h] [rbp-E0h]
  unsigned int v67[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v68[8]; // [rsp+58h] [rbp-A8h] BYREF
  CimSetup *v69; // [rsp+60h] [rbp-A0h]
  HMODULE hModule; // [rsp+68h] [rbp-98h] BYREF
  __int64 v71; // [rsp+70h] [rbp-90h] BYREF
  __int64 v72; // [rsp+78h] [rbp-88h] BYREF
  __int64 v73; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74; // [rsp+88h] [rbp-78h] BYREF
  __int64 v75; // [rsp+90h] [rbp-70h] BYREF
  int v76[2]; // [rsp+98h] [rbp-68h] BYREF
  int v77; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *FullPath; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v80; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v81; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v82; // [rsp+C8h] [rbp-38h]
  _BYTE v83[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v84[24]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v85; // [rsp+128h] [rbp+28h]
  __int64 v86; // [rsp+138h] [rbp+38h]
  _QWORD v87[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v88[2]; // [rsp+160h] [rbp+60h] BYREF
  OLECHAR sz[40]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t Filename[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR Buffer[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+518h]

  v3 = 0;
  *(_QWORD *)v76 = a2;
  v74 = 0;
  v73 = 0;
  v72 = 0;
  v71 = 0;
  hModule = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 124;
    v7 = 2147942487LL;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
      (const char *)v7,
      DirCount);
    goto LABEL_170;
  }
  if ( a3 )
  {
    v8 = (__int64 *)((char *)this + 40);
    v9 = SczAllocFromSz((char *)this + 40, a3);
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = 128;
LABEL_6:
      v7 = (unsigned int)v9;
      goto LABEL_7;
    }
  }
  else
  {
    memset_0(Buffer, 0, 0x208u);
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
    if ( !SystemWindowsDirectoryW )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get system windows directory");
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        else
          v12 = LastError;
        LODWORD(v80) = v12;
        FullPath = (wchar_t *)&v80;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&FullPath);
      }
      if ( LastError )
      {
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x86,
               (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
               (const char *)(unsigned int)LastError,
               DirCount);
        goto LABEL_170;
      }
      goto LABEL_54;
    }
    if ( SystemWindowsDirectoryW >= 0x104 )
    {
      v5 = -2147024774;
      v6 = 135;
      v7 = 2147942522LL;
      goto LABEL_7;
    }
    v8 = (__int64 *)((char *)this + 40);
    v9 = SczAllocFromSz((char *)this + 40, Buffer);
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = 137;
      goto LABEL_6;
    }
  }
  if ( LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (__int64)LogAdapter::g_Logger,
      1,
      1,
      (__int64)"Initializing CimSetup - CimRoot:{} Windows:{}",
      (__int64)v76,
      (__int64)v8);
  CimSetup::Cleanup(this);
  v88[0] = L"winsxs\\FileMaps";
  v88[1] = L"winsxs\\temp";
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v83);
  RemoveTrailingBackslash(*v8);
  v13 = (OLECHAR *)v88;
  do
  {
    v14 = *(_QWORD *)v13;
    v15 = *v8;
    FullPath = 0;
    v5 = SczAllocFormatted(&FullPath, L"%s\\%s", v15, v14);
    if ( (v5 & 0x80000000) != 0 )
    {
      v77 = v5;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to format exception path for {}",
          (__int64)v13);
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v67);
      }
      v65 = 155;
      goto LABEL_168;
    }
    v5 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)v83, FullPath);
    if ( (v5 & 0x80000000) != 0 )
    {
      v77 = v5;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format exception path");
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v67);
      }
      v65 = 157;
LABEL_168:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v65,
        (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
        (const char *)v5,
        DirCount);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&FullPath);
      goto LABEL_169;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&FullPath);
    v13 += 4;
  }
  while ( v13 != sz );
  v68[0] = 1;
  v69 = this;
  v81 = 0;
  v82 = 0;
  CimPayloadFiles = GetCimPayloadFiles(*(_QWORD *)v76, (char *)this + 48);
  v5 = CimPayloadFiles;
  if ( CimPayloadFiles < 0 )
  {
    LODWORD(v80) = CimPayloadFiles;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get the cim payload files");
      FullPath = (wchar_t *)&v80;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&FullPath);
    }
    v17 = 168;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
      (const char *)v5,
      DirCount);
    goto LABEL_31;
  }
  if ( !*((_QWORD *)this + 9) )
  {
    v5 = -2147023728;
    v77 = -2147023728;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No cim payload files found");
      FullPath = (wchar_t *)&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&FullPath);
    }
    v17 = 170;
    goto LABEL_30;
  }
  Library = LoadLibraryExW(L"turbostack.dll", 0, 8u);
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, Library);
  if ( !hModule )
  {
    v19 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load turbostack.dll.");
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      else
        v20 = v19;
      v77 = v20;
      FullPath = (wchar_t *)&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&FullPath);
    }
    if ( v19 )
    {
      v21 = 173;
LABEL_44:
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v21,
             (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
             (const char *)(unsigned int)v19,
             DirCount);
      goto LABEL_31;
    }
    goto LABEL_53;
  }
  ProcAddress = GetProcAddress(hModule, "GenerateProjectionCim");
  if ( !ProcAddress )
  {
    v19 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for GenerateProjectionCim");
      if ( v19 > 0 )
        v23 = (unsigned __int16)v19 | 0x80070000;
      else
        v23 = v19;
      v77 = v23;
      FullPath = (wchar_t *)&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&FullPath);
    }
    if ( v19 )
    {
      v21 = 177;
      goto LABEL_44;
    }
LABEL_53:
    Windows::Auto<Windows::Vector<unsigned char>>::~Auto<Windows::Vector<unsigned char>>(&v81);
    __1__OnBlockExitImpl_V_lambda_1___1__Initialize_CimSetup__QEAAJQEB_WPEB_W_Z__Detail_Windows__QEAA_XZ(v68);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v83);
LABEL_54:
    v5 = 0;
    goto LABEL_170;
  }
  v87[0] = *((_QWORD *)this + 11);
  v87[1] = *((_QWORD *)this + 9);
  v79 = 0;
  v24 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, __int64 *, __int64 *))ProcAddress)(v87, *(_QWORD *)v76, &v81, &v79);
  v5 = v24;
  if ( v24 < 0 )
  {
    v77 = v24;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to generate projection cim");
      FullPath = (wchar_t *)&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&FullPath);
    }
    v26 = 183;
    goto LABEL_59;
  }
  v27 = *((_QWORD *)this + 9);
  if ( v82 != v27 )
  {
    v5 = -2147418113;
    LODWORD(v80) = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      v75 = v27;
      *(_QWORD *)v67 = v82;
      LogAdapter::Logger::LogNumObjects<unsigned __int64,unsigned __int64>(
        (_DWORD)LogAdapter::g_Logger,
        v82,
        v25,
        (unsigned int)"PayloadCimTypes.Length:{} m_cimPaths.GetSize:{} are not equal",
        (__int64)v67,
        (__int64)&v75);
      FullPath = (wchar_t *)&v80;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&FullPath);
    }
    v26 = 190;
    goto LABEL_59;
  }
  v28 = LoadLibraryExW(L"cimfs.dll", 0, 8u);
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(this, v28);
  if ( !*(_QWORD *)this )
  {
    v29 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load CimFS.dll.");
      if ( v29 > 0 )
        v30 = (unsigned __int16)v29 | 0x80070000;
      else
        v30 = v29;
      v77 = v30;
      *(_QWORD *)v67 = &v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v67);
    }
    if ( v29 )
    {
      v31 = 193;
LABEL_73:
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v31,
             (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
             (const char *)(unsigned int)v29,
             DirCount);
      goto LABEL_60;
    }
    goto LABEL_82;
  }
  v32 = GetProcAddress(*(HMODULE *)this, "CimMergeMountImage");
  if ( !v32 )
  {
    v29 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for CimMergeMountImage");
      if ( v29 > 0 )
        v33 = (unsigned __int16)v29 | 0x80070000;
      else
        v33 = v29;
      v77 = v33;
      *(_QWORD *)v67 = &v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v67);
    }
    if ( v29 )
    {
      v31 = 196;
      goto LABEL_73;
    }
LABEL_82:
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v79);
    goto LABEL_53;
  }
  v34 = operator new[](saturated_mul(*((_QWORD *)this + 9) + 1LL, 0x10u));
  if ( !v34 )
  {
    v5 = -2147024882;
    v26 = 199;
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
      (const char *)v5,
      DirCount);
    goto LABEL_60;
  }
  v80 = 0;
  v35 = FileFromPath(v79);
  v36 = SczAllocFromSz(&v80, v35);
  v5 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
      (const char *)(unsigned int)v36,
      DirCount);
    goto LABEL_87;
  }
  *v34 = v79;
  v34[1] = v80;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v84);
  v38 = *((_QWORD *)this + 9);
  v39 = 1;
  if ( !v38 )
  {
LABEL_105:
    Guid = CoCreateGuid((GUID *)((char *)this + 20));
    v5 = Guid;
    if ( Guid < 0 )
    {
      v45 = (unsigned int)Guid;
      v46 = 236;
      goto LABEL_107;
    }
    v47 = ((__int64 (__fastcall *)(_QWORD, _QWORD *, __int64, char *))v32)(
            *((unsigned int *)this + 18),
            v34,
            64,
            (char *)this + 20);
    v5 = v47;
    if ( v47 < 0 )
    {
      v77 = v47;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to mount merged cim images.");
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v67);
      }
      v45 = v5;
      v46 = 243;
      goto LABEL_107;
    }
    *((_BYTE *)this + 16) = 1;
    memset_0(sz, 0, 0x4Eu);
    if ( !StringFromGUID2((const GUID *const)((char *)this + 20), sz, 39) )
    {
      v5 = -2147467259;
      v46 = 247;
      v45 = 2147500037LL;
      goto LABEL_107;
    }
    v48 = SczAllocFormatted(&v73, L"\\\\?\\Volume%ws\\Windows\\Servicing\\Packages", sz);
    v5 = v48;
    if ( v48 < 0 )
    {
      v77 = v48;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create the target packages path");
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v67);
      }
      v45 = v5;
      v46 = 251;
      goto LABEL_107;
    }
    v49 = SczAllocFormatted(&v74, L"\\\\?\\Volume%ws\\Windows\\WinSxs", sz);
    v5 = v49;
    if ( v49 < 0 )
    {
      v77 = v49;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create the target store path");
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v67);
      }
      v45 = v5;
      v46 = 255;
      goto LABEL_107;
    }
    v50 = SczAllocFormatted(&v72, L"%s\\winsxs", *v8);
    v5 = v50;
    if ( v50 < 0 )
    {
      v77 = v50;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format source store path");
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v67);
      }
      v45 = v5;
      v46 = 259;
      goto LABEL_107;
    }
    v51 = SczAllocFormatted(&v71, L"%s\\Servicing\\Packages", *v8);
    v5 = v51;
    if ( v51 < 0 )
    {
      v77 = v51;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to format source packages path");
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v67);
      }
      v45 = v5;
      v46 = 263;
      goto LABEL_107;
    }
    LibraryW = LoadLibraryW(L"bindfltapi.dll");
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership((char *)this + 8, LibraryW);
    v53 = (HMODULE)*((_QWORD *)this + 1);
    if ( v53 )
    {
      v57 = GetProcAddress(v53, "BfSetupFilterEx");
      v58 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v57;
      if ( v57 )
      {
        DirCount = v74;
        v61 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64))v57)(2, 0, 0, v72);
        v5 = v61;
        if ( v61 >= 0 )
        {
          DirCount = v73;
          v62 = v58(2, 0, 0, v71);
          v5 = v62;
          if ( v62 >= 0 )
          {
            *((_BYTE *)this + 17) = 1;
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v80);
            operator delete(v34, v63);
            Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v79);
            Windows::Auto<Windows::Vector<unsigned char>>::~Auto<Windows::Vector<unsigned char>>(&v81);
            __1__OnBlockExitImpl_V_lambda_1___1__Initialize_CimSetup__QEAAJQEB_WPEB_W_Z__Detail_Windows__QEAA_XZ(v68);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v83);
            Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v71);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v73);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
            return 0;
          }
          v77 = v62;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set the bind mapping for Packages");
            *(_QWORD *)v67 = &v77;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v67);
          }
          v45 = v5;
          v46 = 291;
        }
        else
        {
          v77 = v61;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set the bind mapping for WinSxS");
            *(_QWORD *)v67 = &v77;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v67);
          }
          v45 = v5;
          v46 = 280;
        }
LABEL_107:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
          (const char *)v45,
          DirCount);
        goto LABEL_98;
      }
      v54 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for BfSetupFilterEx");
        if ( v54 > 0 )
          v59 = (unsigned __int16)v54 | 0x80070000;
        else
          v59 = v54;
        v77 = v59;
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v67);
      }
      if ( v54 )
      {
        v56 = 269;
        goto LABEL_142;
      }
    }
    else
    {
      v54 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load bindfltapi.dll.");
        if ( v54 > 0 )
          v55 = (unsigned __int16)v54 | 0x80070000;
        else
          v55 = v54;
        v77 = v55;
        *(_QWORD *)v67 = &v77;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v67);
      }
      if ( v54 )
      {
        v56 = 266;
LABEL_142:
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v56,
               (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
               (const char *)(unsigned int)v54,
               DirCount);
        goto LABEL_98;
      }
    }
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v80);
    operator delete(v34, v60);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v79);
    Windows::Auto<Windows::Vector<unsigned char>>::~Auto<Windows::Vector<unsigned char>>(&v81);
    __1__OnBlockExitImpl_V_lambda_1___1__Initialize_CimSetup__QEAAJQEB_WPEB_W_Z__Detail_Windows__QEAA_XZ(v68);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v83);
    v5 = 0;
    goto LABEL_170;
  }
  while ( 2 )
  {
    FullPath = 0;
    if ( v3 >= v38 )
      __fastfail(8u);
    v40 = FileFromPath(*(_QWORD *)(*((_QWORD *)this + 11) + 8 * v3));
    v41 = SczAllocFromSz(&FullPath, v40);
    v5 = v41;
    if ( v41 < 0 )
    {
      v42 = 212;
      goto LABEL_96;
    }
    if ( *(_DWORD *)(v81 + 4 * v3) != 1 )
    {
      v41 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)v84, FullPath);
      v5 = v41;
      if ( v41 < 0 )
      {
        v42 = 228;
        goto LABEL_96;
      }
      goto LABEL_100;
    }
    memset_0(Filename, 0, sizeof(Filename));
    if ( !_wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, 0, 0) )
    {
      v41 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)v84, Filename);
      v5 = v41;
      if ( v41 < 0 )
      {
        v42 = 219;
LABEL_96:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
          (const char *)(unsigned int)v41,
          DirCount);
        goto LABEL_97;
      }
LABEL_100:
      if ( v3 >= *((_QWORD *)this + 9) )
        __fastfail(8u);
      v43 = 2 * v39;
      v34[2 * v39] = *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v3);
      if ( v3 >= v85 )
        __fastfail(8u);
      ++v39;
      v34[v43 + 1] = *(_QWORD *)(v86 + 8 * v3);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&FullPath);
      v38 = *((_QWORD *)this + 9);
      if ( ++v3 >= v38 )
        goto LABEL_105;
      continue;
    }
    break;
  }
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (__int64)"Failed to split path for cim file: {}",
      (__int64)&FullPath);
    *(_QWORD *)v67 = &v77;
    v77 = -2147024883;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)v67);
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xDF,
         (unsigned int)"onecore\\base\\cbs\\util\\inc\\CbsCimHelper.h",
         (const char *)0xD,
         DirCount);
LABEL_97:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&FullPath);
LABEL_98:
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v84);
LABEL_87:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v80);
  operator delete(v34, v37);
LABEL_60:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&v79);
LABEL_31:
  Windows::Auto<Windows::Vector<unsigned char>>::~Auto<Windows::Vector<unsigned char>>(&v81);
  __1__OnBlockExitImpl_V_lambda_1___1__Initialize_CimSetup__QEAAJQEB_WPEB_W_Z__Detail_Windows__QEAA_XZ(v68);
LABEL_169:
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v83);
LABEL_170:
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v71);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v73);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
  return v5;
}

```

## disassembly

```asm
0x1801c7944  mov     [rsp-8+arg_18], rbx
0x1801c7949  push    rbp
0x1801c794a  push    rsi
0x1801c794b  push    rdi
0x1801c794c  push    r12
0x1801c794e  push    r13
0x1801c7950  push    r14
0x1801c7952  push    r15
0x1801c7954  lea     rbp, [rsp-4E0h]
0x1801c795c  sub     rsp, 5E0h
0x1801c7963  mov     rax, cs:__security_cookie
0x1801c796a  xor     rax, rsp
0x1801c796d  mov     [rbp+510h+var_40], rax
0x1801c7974  xor     r15d, r15d
0x1801c7977  mov     qword ptr [rbp+510h+var_578], rdx
0x1801c797b  mov     [rbp+510h+var_588], r15
0x1801c797f  mov     rsi, rcx
0x1801c7982  mov     [rbp+510h+var_590], r15
0x1801c7986  mov     [rsp+610h+var_598], r15
0x1801c798b  mov     [rsp+610h+var_5A0], r15
0x1801c7990  mov     [rsp+610h+hModule], r15
0x1801c7995  test    rdx, rdx
0x1801c7998  jnz     short loc_1801C79A8
0x1801c799a  mov     edi, 80070057h
0x1801c799f  lea     edx, [r15+7Ch]
0x1801c79a3  mov     r9d, edi
0x1801c79a6  jmp     short loc_1801C79CE
0x1801c79a8  test    r8, r8
0x1801c79ab  jz      short loc_1801C79E6
0x1801c79ad  lea     r14, [rcx+28h]
0x1801c79b1  mov     rdx, r8
0x1801c79b4  mov     rcx, r14
0x1801c79b7  call    SczAllocFromSz
0x1801c79bc  mov     edi, eax
0x1801c79be  test    eax, eax
0x1801c79c0  jns     loc_1801C7AEB
0x1801c79c6  mov     edx, 80h; void *
0x1801c79cb  mov     r9d, eax; char *
0x1801c79ce  mov     rcx, [rbp+518h]; this
0x1801c79d5  lea     r8, aOnecoreBaseCbs_158; "onecore\\base\\cbs\\util\\inc\\CbsCimHe"...
0x1801c79dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c79e1  jmp     loc_1801C8A5E
0x1801c79e6  xor     edx, edx; Val
0x1801c79e8  lea     rcx, [rbp+510h+Buffer]; void *
0x1801c79ef  mov     r8d, 208h; Size
0x1801c79f5  call    memset_0
0x1801c79fa  mov     ebx, 104h
0x1801c79ff  lea     rcx, [rbp+510h+Buffer]; lpBuffer
0x1801c7a06  mov     edx, ebx; uSize
0x1801c7a08  call    cs:__imp_GetSystemWindowsDirectoryW
0x1801c7a0f  nop     dword ptr [rax+rax+00h]
0x1801c7a14  test    eax, eax
0x1801c7a16  jnz     loc_1801C7AB2
0x1801c7a1c  call    cs:__imp_GetLastError
0x1801c7a23  nop     dword ptr [rax+rax+00h]
0x1801c7a28  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7a2f  mov     ebx, eax
0x1801c7a31  test    rcx, rcx
0x1801c7a34  jz      short loc_1801C7A88
0x1801c7a36  mov     esi, 3
0x1801c7a3b  lea     r9, aFailedToGetSys; "Failed to get system windows directory"
0x1801c7a42  mov     r8d, esi
0x1801c7a45  xor     edx, edx
0x1801c7a47  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c7a4c  test    ebx, ebx
0x1801c7a4e  jg      short loc_1801C7A54
0x1801c7a50  mov     eax, ebx
0x1801c7a52  jmp     short loc_1801C7A5C
0x1801c7a54  movzx   eax, bx
0x1801c7a57  or      eax, 80070000h
0x1801c7a5c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7a63  lea     r9, a0; ": {0}"
0x1801c7a6a  mov     dword ptr [rbp+510h+var_558], eax
0x1801c7a6d  mov     r8d, esi
0x1801c7a70  lea     rax, [rbp+510h+var_558]
0x1801c7a74  mov     dl, 1
0x1801c7a76  mov     [rbp+510h+FullPath], rax
0x1801c7a7a  lea     rax, [rbp+510h+FullPath]
0x1801c7a7e  mov     [rsp+610h+DirCount], rax; unsigned int
0x1801c7a83  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c7a88  test    ebx, ebx
0x1801c7a8a  jz      loc_1801C7E2A
0x1801c7a90  mov     rcx, [rbp+518h]; this
0x1801c7a97  lea     r8, aOnecoreBaseCbs_158; "onecore\\base\\cbs\\util\\inc\\CbsCimHe"...
0x1801c7a9e  mov     r9d, ebx; char *
0x1801c7aa1  mov     edx, 86h; void *
0x1801c7aa6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801c7aab  mov     edi, eax
0x1801c7aad  jmp     loc_1801C8A5E
0x1801c7ab2  cmp     eax, ebx
0x1801c7ab4  jb      short loc_1801C7AC8
0x1801c7ab6  mov     edi, 8007007Ah
0x1801c7abb  mov     edx, 87h
0x1801c7ac0  mov     r9d, edi
0x1801c7ac3  jmp     loc_1801C79CE
0x1801c7ac8  lea     r14, [rsi+28h]
0x1801c7acc  mov     rcx, r14
0x1801c7acf  lea     rdx, [rbp+510h+Buffer]
0x1801c7ad6  call    SczAllocFromSz
0x1801c7adb  mov     edi, eax
0x1801c7add  test    eax, eax
0x1801c7adf  jns     short loc_1801C7AEB
0x1801c7ae1  mov     edx, 89h
0x1801c7ae6  jmp     loc_1801C79CB
0x1801c7aeb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7af2  test    rcx, rcx
0x1801c7af5  jz      short loc_1801C7B1A
0x1801c7af7  mov     r8d, 1
0x1801c7afd  mov     [rsp+610h+Filename], r14
0x1801c7b02  lea     rax, [rbp+510h+var_578]
0x1801c7b06  mov     dl, r8b
0x1801c7b09  lea     r9, aInitializingCi; "Initializing CimSetup - CimRoot:{} Wind"...
0x1801c7b10  mov     [rsp+610h+DirCount], rax; int
0x1801c7b15  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1801c7b1a  mov     rcx, rsi; this
0x1801c7b1d  call    ?Cleanup@CimSetup@@QEAAXXZ; CimSetup::Cleanup(void)
0x1801c7b22  lea     rax, aWinsxsFilemaps; "winsxs\\FileMaps"
0x1801c7b29  mov     [rbp+510h+var_4B0], rax
0x1801c7b2d  lea     rcx, [rbp+510h+var_540]; this
0x1801c7b31  lea     rax, aWinsxsTemp; "winsxs\\temp"
0x1801c7b38  mov     [rbp+510h+var_4A8], rax
0x1801c7b3c  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x1801c7b41  mov     rcx, [r14]
0x1801c7b44  call    RemoveTrailingBackslash
0x1801c7b49  lea     rbx, [rbp+510h+var_4B0]
0x1801c7b4d  mov     r9, [rbx]
0x1801c7b50  lea     rdx, aSS_0; "%s\\%s"
0x1801c7b57  mov     r8, [r14]
0x1801c7b5a  lea     rcx, [rbp+510h+FullPath]
0x1801c7b5e  mov     [rbp+510h+FullPath], r15
0x1801c7b62  call    SczAllocFormatted
0x1801c7b67  mov     edi, eax
0x1801c7b69  test    eax, eax
0x1801c7b6b  js      loc_1801C89DC
0x1801c7b71  mov     rdx, [rbp+510h+FullPath]; wchar_t *
0x1801c7b75  lea     rcx, [rbp+510h+var_540]; this
0x1801c7b79  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x1801c7b7e  mov     edi, eax
0x1801c7b80  test    eax, eax
0x1801c7b82  js      loc_1801C8985
0x1801c7b88  lea     rcx, [rbp+510h+FullPath]
0x1801c7b8c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801c7b91  lea     rax, [rbp+510h+sz]
0x1801c7b95  add     rbx, 8
0x1801c7b99  cmp     rbx, rax
0x1801c7b9c  jnz     short loc_1801C7B4D
0x1801c7b9e  mov     rcx, qword ptr [rbp+510h+var_578]
0x1801c7ba2  lea     rdx, [rsi+30h]
0x1801c7ba6  mov     [rsp+610h+var_5B8], 1
0x1801c7bab  mov     [rsp+610h+var_5B0], rsi
0x1801c7bb0  mov     [rbp+510h+var_550], r15
0x1801c7bb4  mov     [rbp+510h+var_548], r15
0x1801c7bb8  call    GetCimPayloadFiles
0x1801c7bbd  mov     edi, eax
0x1801c7bbf  test    eax, eax
0x1801c7bc1  jns     loc_1801C7C48
0x1801c7bc7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7bce  mov     dword ptr [rbp+510h+var_558], eax
0x1801c7bd1  test    rcx, rcx
0x1801c7bd4  jz      short loc_1801C7C15
0x1801c7bd6  mov     esi, 3
0x1801c7bdb  lea     r9, aFailedToGetThe_4; "Failed to get the cim payload files"
0x1801c7be2  mov     r8d, esi
0x1801c7be5  xor     edx, edx
0x1801c7be7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c7bec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7bf3  lea     rax, [rbp+510h+var_558]
0x1801c7bf7  mov     [rbp+510h+FullPath], rax
0x1801c7bfb  lea     r9, asc_1802EE7AC; ": {}"
0x1801c7c02  lea     rax, [rbp+510h+FullPath]
0x1801c7c06  mov     r8d, esi
0x1801c7c09  mov     dl, 1
0x1801c7c0b  mov     [rsp+610h+DirCount], rax; int
0x1801c7c10  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c7c15  mov     edx, 0A8h; void *
0x1801c7c1a  mov     rcx, [rbp+518h]; this
0x1801c7c21  lea     r8, aOnecoreBaseCbs_158; "onecore\\base\\cbs\\util\\inc\\CbsCimHe"...
0x1801c7c28  mov     r9d, edi; char *
0x1801c7c2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c7c30  lea     rcx, [rbp+510h+var_550]
0x1801c7c34  call    ??1?$Auto@U?$Vector@E@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<uchar>>::~Auto<Windows::Vector<uchar>>(void)
0x1801c7c39  lea     rcx, [rsp+610h+var_5B8]
0x1801c7c3e  call    ??1?$OnBlockExitImpl@V_lambda_1_@?1??Initialize@CimSetup@@QEAAJQEB_WPEB_W@Z@@Detail@Windows@@QEAA@XZ; Windows::Detail::OnBlockExitImpl<`CimSetup::Initialize(wchar_t const * const,wchar_t const *)'::`2'::_lambda_1_>::~OnBlockExitImpl<`CimSetup::Initialize(wchar_t const * const,wchar_t const *)'::`2'::_lambda_1_>(void)
0x1801c7c43  jmp     loc_1801C8A55
0x1801c7c48  cmp     [rsi+48h], r15
0x1801c7c4c  jnz     short loc_1801C7CAB
0x1801c7c4e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7c55  mov     edi, 80070490h
0x1801c7c5a  mov     [rbp+510h+var_570], edi
0x1801c7c5d  test    rcx, rcx
0x1801c7c60  jz      short loc_1801C7CA1
0x1801c7c62  mov     esi, 3
0x1801c7c67  lea     r9, aNoCimPayloadFi; "No cim payload files found"
0x1801c7c6e  mov     r8d, esi
0x1801c7c71  xor     edx, edx
0x1801c7c73  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c7c78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7c7f  lea     rax, [rbp+510h+var_570]
0x1801c7c83  mov     [rbp+510h+FullPath], rax
0x1801c7c87  lea     r9, asc_1802EE7AC; ": {}"
0x1801c7c8e  lea     rax, [rbp+510h+FullPath]
0x1801c7c92  mov     r8d, esi
0x1801c7c95  mov     dl, 1
0x1801c7c97  mov     [rsp+610h+DirCount], rax
0x1801c7c9c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c7ca1  mov     edx, 0AAh
0x1801c7ca6  jmp     loc_1801C7C1A
0x1801c7cab  xor     edx, edx; hFile
0x1801c7cad  lea     rcx, aTurbostackDll_0; "turbostack.dll"
0x1801c7cb4  lea     r8d, [rdx+8]; dwFlags
0x1801c7cb8  call    cs:__imp_LoadLibraryExW
0x1801c7cbf  nop     dword ptr [rax+rax+00h]
0x1801c7cc4  mov     rdx, rax
0x1801c7cc7  lea     rcx, [rsp+610h+hModule]
0x1801c7ccc  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1801c7cd1  mov     rcx, [rsp+610h+hModule]; hModule
0x1801c7cd6  test    rcx, rcx
0x1801c7cd9  jnz     loc_1801C7D75
0x1801c7cdf  call    cs:__imp_GetLastError
0x1801c7ce6  nop     dword ptr [rax+rax+00h]
0x1801c7ceb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7cf2  mov     ebx, eax
0x1801c7cf4  test    rcx, rcx
0x1801c7cf7  jz      short loc_1801C7D4B
0x1801c7cf9  mov     esi, 3
0x1801c7cfe  lea     r9, aFailedToLoadTu_2; "Failed to load turbostack.dll."
0x1801c7d05  mov     r8d, esi
0x1801c7d08  xor     edx, edx
0x1801c7d0a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c7d0f  test    ebx, ebx
0x1801c7d11  jg      short loc_1801C7D17
0x1801c7d13  mov     eax, ebx
0x1801c7d15  jmp     short loc_1801C7D1F
0x1801c7d17  movzx   eax, bx
0x1801c7d1a  or      eax, 80070000h
0x1801c7d1f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7d26  lea     r9, a0; ": {0}"
0x1801c7d2d  mov     [rbp+510h+var_570], eax
0x1801c7d30  mov     r8d, esi
0x1801c7d33  lea     rax, [rbp+510h+var_570]
0x1801c7d37  mov     dl, 1
0x1801c7d39  mov     [rbp+510h+FullPath], rax
0x1801c7d3d  lea     rax, [rbp+510h+FullPath]
0x1801c7d41  mov     [rsp+610h+DirCount], rax; unsigned int
0x1801c7d46  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c7d4b  test    ebx, ebx
0x1801c7d4d  jz      loc_1801C7E0E
0x1801c7d53  mov     edx, 0ADh; void *
0x1801c7d58  mov     rcx, [rbp+518h]; this
0x1801c7d5f  lea     r8, aOnecoreBaseCbs_158; "onecore\\base\\cbs\\util\\inc\\CbsCimHe"...
0x1801c7d66  mov     r9d, ebx; char *
0x1801c7d69  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801c7d6e  mov     edi, eax
0x1801c7d70  jmp     loc_1801C7C30
0x1801c7d75  lea     rdx, aGenerateprojec; "GenerateProjectionCim"
0x1801c7d7c  call    cs:__imp_GetProcAddress
0x1801c7d83  nop     dword ptr [rax+rax+00h]
0x1801c7d88  mov     r10, rax
0x1801c7d8b  test    rax, rax
0x1801c7d8e  jnz     loc_1801C7E32
0x1801c7d94  call    cs:__imp_GetLastError
0x1801c7d9b  nop     dword ptr [rax+rax+00h]
0x1801c7da0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7da7  mov     ebx, eax
0x1801c7da9  test    rcx, rcx
0x1801c7dac  jz      short loc_1801C7E00
0x1801c7dae  mov     esi, 3
0x1801c7db3  lea     r9, aFailedToGetPro_48; "Failed to get proc address for Generate"...
0x1801c7dba  mov     r8d, esi
0x1801c7dbd  xor     edx, edx
0x1801c7dbf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c7dc4  test    ebx, ebx
0x1801c7dc6  jg      short loc_1801C7DCC
0x1801c7dc8  mov     eax, ebx
0x1801c7dca  jmp     short loc_1801C7DD4
0x1801c7dcc  movzx   eax, bx
0x1801c7dcf  or      eax, 80070000h
0x1801c7dd4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c7ddb  lea     r9, a0; ": {0}"
0x1801c7de2  mov     [rbp+510h+var_570], eax
0x1801c7de5  mov     r8d, esi
0x1801c7de8  lea     rax, [rbp+510h+var_570]
0x1801c7dec  mov     dl, 1
0x1801c7dee  mov     [rbp+510h+FullPath], rax
0x1801c7df2  lea     rax, [rbp+510h+FullPath]
0x1801c7df6  mov     [rsp+610h+DirCount], rax
0x1801c7dfb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c7e00  test    ebx, ebx
0x1801c7e02  jz      short loc_1801C7E0E
0x1801c7e04  mov     edx, 0B1h
0x1801c7e09  jmp     loc_1801C7D58
0x1801c7e0e  lea     rcx, [rbp+510h+var_550]
0x1801c7e12  call    ??1?$Auto@U?$Vector@E@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<uchar>>::~Auto<Windows::Vector<uchar>>(void)
0x1801c7e17  lea     rcx, [rsp+610h+var_5B8]
0x1801c7e1c  call    ??1?$OnBlockExitImpl@V_lambda_1_@?1??Initialize@CimSetup@@QEAAJQEB_WPEB_W@Z@@Detail@Windows@@QEAA@XZ; Windows::Detail::OnBlockExitImpl<`CimSetup::Initialize(wchar_t const * const,wchar_t const *)'::`2'::_lambda_1_>::~OnBlockExitImpl<`CimSetup::Initialize(wchar_t const * const,wchar_t const *)'::`2'::_lambda_1_>(void)
0x1801c7e21  lea     rcx, [rbp+510h+var_540]
0x1801c7e25  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1801c7e2a  mov     edi, r15d
0x1801c7e2d  jmp     loc_1801C8A5E
0x1801c7e32  mov     rax, [rsi+58h]
  ... truncated ...
```

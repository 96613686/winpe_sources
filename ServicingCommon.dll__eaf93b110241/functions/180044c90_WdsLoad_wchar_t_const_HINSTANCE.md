# WdsLoad(wchar_t const *,HINSTANCE__ *)

- ea: `0x180044c90`
- end: `0x180045f1e`
- name: `?WdsLoad@@YAJPEB_WPEAUHINSTANCE__@@@Z`
- size: `4750`
- prototype: `__int64 __fastcall(const wchar_t *, HINSTANCE)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800461b0`

## callees

- `0x18000ea3c`
- `0x18001e51c`
- `0x18001f660`
- `0x180021300`
- `0x180022d80`
- `0x1800239c0`
- `0x180023fa0`
- `0x1800293a0`
- `0x18003d7d4`
- `0x18003e8f8`
- `0x180041a74`
- `0x180041c30`
- `0x180041de8`
- `0x180042434`
- `0x180042464`
- `0x1800424dc`
- `0x180043b00`
- `0x180043f48`
- `0x180043fd0`
- `0x1800443ac`
- `0x180044754`
- `0x180044c10`
- `0x180044c90`
- `0x18004add8`
- `0x18004afd8`
- `0x18004b2e4`
- `0x18004bbb0`
- `0x18004bfc4`
- `0x18004c660`
- `0x18004c9e0`
- `0x18004cca0`
- `0x18004d3a0`
- `0x18004d850`
- `0x18004dc74`
- `0x18004e1d4`
- `0x18004e878`
- `0x18004e938`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044f6c`
- `KERNEL32!GetLastError` at `0x180045045`
- `KERNEL32!GetLastError` at `0x1800450e4`
- `KERNEL32!GetLastError` at `0x180045183`
- `KERNEL32!GetLastError` at `0x180045222`
- `KERNEL32!GetLastError` at `0x1800452c1`
- `KERNEL32!GetLastError` at `0x180045360`
- `KERNEL32!GetLastError` at `0x1800453ff`
- `KERNEL32!GetLastError` at `0x18004592b`
- `KERNEL32!GetLastError` at `0x1800459f1`
- `KERNEL32!GetLastError` at `0x180044f6c`
- `KERNEL32!GetLastError` at `0x180045045`
- `KERNEL32!GetLastError` at `0x1800450e4`
- `KERNEL32!GetLastError` at `0x180045183`
- `KERNEL32!GetLastError` at `0x180045222`
- `KERNEL32!GetLastError` at `0x1800452c1`
- `KERNEL32!GetLastError` at `0x180045360`
- `KERNEL32!GetLastError` at `0x1800453ff`
- `KERNEL32!GetLastError` at `0x18004592b`
- `KERNEL32!GetLastError` at `0x1800459f1`
- `KERNEL32!GetProcAddress` at `0x18004502d`
- `KERNEL32!GetProcAddress` at `0x1800450cc`
- `KERNEL32!GetProcAddress` at `0x18004516b`
- `KERNEL32!GetProcAddress` at `0x18004520a`
- `KERNEL32!GetProcAddress` at `0x1800452a9`
- `KERNEL32!GetProcAddress` at `0x180045348`
- `KERNEL32!GetProcAddress` at `0x1800453e7`
- `KERNEL32!GetProcAddress` at `0x180045d50`
- `KERNEL32!GetProcAddress` at `0x18004502d`
- `KERNEL32!GetProcAddress` at `0x1800450cc`
- `KERNEL32!GetProcAddress` at `0x18004516b`
- `KERNEL32!GetProcAddress` at `0x18004520a`
- `KERNEL32!GetProcAddress` at `0x1800452a9`
- `KERNEL32!GetProcAddress` at `0x180045348`
- `KERNEL32!GetProcAddress` at `0x1800453e7`
- `KERNEL32!GetProcAddress` at `0x180045d50`
- `KERNEL32!GetEnvironmentVariableW` at `0x180045521`
- `KERNEL32!GetEnvironmentVariableW` at `0x180045bd1`
- `KERNEL32!GetEnvironmentVariableW` at `0x180045521`
- `KERNEL32!GetEnvironmentVariableW` at `0x180045bd1`
- `KERNEL32!LoadLibraryW` at `0x180044eae`
- `KERNEL32!LoadLibraryW` at `0x180044f41`
- `KERNEL32!LoadLibraryW` at `0x180044eae`
- `KERNEL32!LoadLibraryW` at `0x180044f41`
- `KERNEL32!MoveFileExW` at `0x180045917`
- `KERNEL32!MoveFileExW` at `0x180045917`
- `KERNEL32!GetSystemTime` at `0x1800458a5`
- `KERNEL32!GetSystemTime` at `0x1800458a5`
- `KERNEL32!GetFileAttributesW` at `0x1800459e0`
- `KERNEL32!GetFileAttributesW` at `0x1800459e0`

## string_xrefs

- `0x18004551a`: `COMPONENT_BASED_SERVICING_LOGFILE`
- `0x180045bca`: `COMPONENT_BASED_SERVICING_LOGLEVEL`
- `0x180044e88`: `wdscore.dll`
- `0x180044f11`: `wdscore.dll`
- `0x180044d19`: `Wds logger is already initialized`
- `0x180044d83`: `No core dll path specified`
- `0x180044dfb`: `Failed to get windows directory for WDSCORE DLL path.`
- `0x180044f18`: `system32\`
- `0x180044faa`: `Failed to load WDSCORE DLL: {}`
- `0x18004559c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x1800455c3`: `LogPath`
- `0x1800455cf`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide\Configuration`
- `0x180045624`: `Failed to get log path from: {}`
- `0x180045780`: `Failed to ensure that logging directory exists: {}`
- `0x180045879`: `System\CurrentControlSet\Services\TrustedInstaller`
- `0x180045981`: `WDS logging is not enabled in the registry, continuing without logging.`
- `0x180045a0d`: `CBSLogCompress`
- `0x180045aab`: `Failed to initialize logging with dll: {}, log directory: {}`
- `0x180045b55`: `Failed to initialize logging with DLL: {}, log file: {}`
- `0x180045d1e`: `Failed to configure logging settings`
- `0x180045e0d`: `Failed to delete extra backup log files.`

## pseudocode

```c
__int64 __fastcall WdsLoad(const wchar_t *a1, HINSTANCE a2)
{
  __int64 v2; // rbx
  int v4; // r14d
  int v5; // edx
  __int64 v6; // r9
  __int64 v7; // rdx
  unsigned int v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  int WindowsDirectory; // eax
  int v13; // edi
  int v14; // edx
  __int64 v15; // rdx
  wchar_t *v16; // rdi
  HMODULE LibraryW; // rax
  HMODULE v18; // rcx
  HMODULE v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  signed int LastError; // ebx
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  unsigned int v26; // eax
  int v27; // edx
  unsigned int v28; // eax
  int v29; // edx
  unsigned int v30; // eax
  int v31; // edx
  unsigned int v32; // eax
  int v33; // edx
  unsigned int v34; // eax
  int v35; // edx
  unsigned int v36; // eax
  int v37; // edx
  unsigned int v38; // eax
  HKEY v39; // rcx
  unsigned int v40; // r8d
  const WCHAR *v41; // rsi
  unsigned int v42; // r13d
  HKEY v43; // rcx
  unsigned int v44; // r8d
  int v45; // eax
  unsigned int v46; // esi
  unsigned int v47; // r15d
  HKEY v48; // rcx
  unsigned int v49; // r8d
  unsigned int v50; // r14d
  int v51; // eax
  int v52; // edx
  __int64 v53; // rcx
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int Directory; // eax
  unsigned int v60; // r15d
  int v61; // edx
  unsigned int v62; // r15d
  unsigned int v63; // r12d
  HKEY v64; // rcx
  unsigned int v65; // r8d
  int v66; // eax
  int v67; // edx
  unsigned int v68; // ecx
  DWORD v69; // eax
  int v70; // ecx
  int v71; // r8d
  int v72; // edx
  DWORD FileAttributesW; // eax
  int Property; // eax
  __int64 v75; // rdx
  int v76; // ecx
  __int64 InitPointer; // rax
  int v78; // edx
  int v79; // r8d
  int v80; // r9d
  __int64 v81; // rax
  int v82; // edx
  int v83; // r8d
  int v84; // r9d
  int v85; // edx
  int v86; // r8d
  int v87; // edx
  int v88; // edx
  int v89; // r8d
  int v90; // edx
  unsigned int v91; // edi
  struct ILogManager *SetupLog; // r14
  int v93; // eax
  FARPROC ProcAddress; // rax
  __int64 v95; // rcx
  const char *v96; // rdx
  int v97; // eax
  int v98; // edx
  wchar_t **v100; // [rsp+20h] [rbp-E0h]
  int wDay; // [rsp+28h] [rbp-D8h]
  int wHour; // [rsp+30h] [rbp-D0h]
  unsigned int v103[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v104[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v105[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpLibFileName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v108; // [rsp+78h] [rbp-88h] BYREF
  __int64 v109; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpNewFileName; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *EndPtr; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v112; // [rsp+98h] [rbp-68h] BYREF
  int v113; // [rsp+A0h] [rbp-60h]
  __int64 v114; // [rsp+A4h] [rbp-5Ch]
  int v115; // [rsp+ACh] [rbp-54h]
  const WCHAR *v116; // [rsp+B0h] [rbp-50h]
  __int64 v117; // [rsp+B8h] [rbp-48h]
  __int64 v118; // [rsp+C0h] [rbp-40h]
  _QWORD v119[7]; // [rsp+C8h] [rbp-38h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+100h] [rbp+0h] BYREF
  WCHAR String[64]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Buffer[512]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5E8h] [rbp+4E8h]

  v2 = 0;
  lpExistingFileName = 0;
  lpNewFileName = 0;
  lpLibFileName = 0;
  v4 = 0;
  v109 = 0;
  LODWORD(EndPtr) = 3;
  v104[0] = 0;
  SystemTime = 0;
  v108 = 0;
  if ( _InterlockedIncrement(&vcWdsLoadOperations) > 1 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Wds logger is already initialized");
      *(_QWORD *)v103 = &EndPtr;
      LODWORD(EndPtr) = -2147023649;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {0}",
        (__int64)v103);
    }
    v6 = 1247;
    v7 = 644;
    goto LABEL_40;
  }
  if ( !a1 )
  {
    v8 = -2147024809;
    LODWORD(EndPtr) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No core dll path specified");
      *(_QWORD *)v103 = &EndPtr;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v103);
    }
    v10 = 647;
LABEL_9:
    v11 = v8;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)v11,
      (int)v100);
LABEL_203:
    vpfnWdsSetupLogInit = 0;
    vpfnWdsGenericSetupLogInit = 0;
    vpfnWdsGetSetupLog = 0;
    vpfnWdsSetupLogDestroy = 0;
    vpfnWdsSetupLogMessageA = 0;
    vpfnConstructPartialMsgVA = 0;
    vpfnCurrentIP = 0;
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&vhWdsDll);
    goto LABEL_207;
  }
  WindowsDirectory = PathGetWindowsDirectory(&v109, a2);
  v13 = WindowsDirectory;
  if ( WindowsDirectory < 0 )
  {
    LODWORD(EndPtr) = WindowsDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to get windows directory for WDSCORE DLL path.");
      *(_QWORD *)v103 = &EndPtr;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)v103);
    }
    v15 = 650;
    goto LABEL_15;
  }
  v13 = SczAllocFromSz(&lpLibFileName, a1);
  if ( v13 < 0 )
  {
    v15 = 652;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v13,
      (int)v100);
    v8 = v13;
    goto LABEL_203;
  }
  v13 = SczEnsureBackslashTerminated(&lpLibFileName);
  if ( v13 < 0 )
  {
    v15 = 653;
    goto LABEL_15;
  }
  v13 = SczAllocConcatSz(&lpLibFileName, L"wdscore.dll");
  if ( v13 < 0 )
  {
    v15 = 654;
    goto LABEL_15;
  }
  v16 = (wchar_t *)lpLibFileName;
  LibraryW = LoadLibraryW(lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(&vhWdsDll, LibraryW);
  v18 = vhWdsDll;
  if ( vhWdsDll )
    goto LABEL_41;
  v13 = SczAllocFromSz(&lpLibFileName, v109);
  if ( v13 < 0 )
  {
    v15 = 659;
    goto LABEL_15;
  }
  v13 = SczEnsureBackslashTerminated(&lpLibFileName);
  if ( v13 < 0 )
  {
    v15 = 660;
    goto LABEL_15;
  }
  v13 = SczAllocConcat2Sz(&lpLibFileName, L"system32\\", L"wdscore.dll");
  if ( v13 < 0 )
  {
    v15 = 661;
    goto LABEL_15;
  }
  v16 = (wchar_t *)lpLibFileName;
  v19 = LoadLibraryW(lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(&vhWdsDll, v19);
  v18 = vhWdsDll;
  if ( vhWdsDll )
  {
LABEL_41:
    vpfnWdsSetupLogInit = (struct ILogManager *(*)(HINSTANCE, unsigned int, const wchar_t *))GetProcAddress(
                                                                                               v18,
                                                                                               "WdsSetupLogInit");
    if ( !vpfnWdsSetupLogInit )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for WdsSetupLogInit.");
        if ( LastError > 0 )
          v26 = (unsigned __int16)LastError | 0x80070000;
        else
          v26 = LastError;
        LODWORD(EndPtr) = v26;
        *(_QWORD *)v103 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v25,
          3,
          (unsigned int)": {0}",
          (__int64)v103);
      }
      if ( LastError )
      {
        v7 = 679;
        goto LABEL_39;
      }
LABEL_97:
      v8 = 0;
      goto LABEL_203;
    }
    vpfnWdsGenericSetupLogInit = (int (*)(const wchar_t *, unsigned int))GetProcAddress(
                                                                           vhWdsDll,
                                                                           "WdsGenericSetupLogInit");
    if ( !vpfnWdsGenericSetupLogInit )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for WdsGenericSetupLogInit.");
        if ( LastError > 0 )
          v28 = (unsigned __int16)LastError | 0x80070000;
        else
          v28 = LastError;
        LODWORD(EndPtr) = v28;
        *(_QWORD *)v103 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v27,
          3,
          (unsigned int)": {0}",
          (__int64)v103);
      }
      if ( LastError )
      {
        v7 = 682;
        goto LABEL_39;
      }
      goto LABEL_97;
    }
    vpfnWdsGetSetupLog = (struct ILogManager *(*)(void))GetProcAddress(vhWdsDll, "WdsGetSetupLog");
    if ( !vpfnWdsGetSetupLog )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for WdsGetSetupLog.");
        if ( LastError > 0 )
          v30 = (unsigned __int16)LastError | 0x80070000;
        else
          v30 = LastError;
        LODWORD(EndPtr) = v30;
        *(_QWORD *)v103 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v29,
          3,
          (unsigned int)": {0}",
          (__int64)v103);
      }
      if ( LastError )
      {
        v7 = 685;
        goto LABEL_39;
      }
      goto LABEL_97;
    }
    vpfnWdsSetupLogDestroy = (void (*)(void))GetProcAddress(vhWdsDll, "WdsSetupLogDestroy");
    if ( !vpfnWdsSetupLogDestroy )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for WdsSetupLogDestroy.");
        if ( LastError > 0 )
          v32 = (unsigned __int16)LastError | 0x80070000;
        else
          v32 = LastError;
        LODWORD(EndPtr) = v32;
        *(_QWORD *)v103 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          3,
          (unsigned int)": {0}",
          (__int64)v103);
      }
      if ( LastError )
      {
        v7 = 689;
        goto LABEL_39;
      }
      goto LABEL_97;
    }
    vpfnWdsSetupLogMessageA = (enum tagLOGRESULT (__high *)(struct tagLOG_PARTIAL_MSG *, unsigned int, const char *, const char *, unsigned int, const char *, const char *, void *, unsigned int, void *, unsigned int))GetProcAddress(vhWdsDll, "WdsSetupLogMessageA");
    if ( !vpfnWdsSetupLogMessageA )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for WdsSetupLogMessageA.");
        if ( LastError > 0 )
          v34 = (unsigned __int16)LastError | 0x80070000;
        else
          v34 = LastError;
        LODWORD(EndPtr) = v34;
        *(_QWORD *)v103 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v33,
          3,
          (unsigned int)": {0}",
          (__int64)v103);
      }
      if ( LastError )
      {
        v7 = 692;
        goto LABEL_39;
      }
      goto LABEL_97;
    }
    vpfnConstructPartialMsgVA = (struct tagLOG_PARTIAL_MSG *(*)(unsigned int, const char *, char *))GetProcAddress(vhWdsDll, "ConstructPartialMsgVA");
    if ( !vpfnConstructPartialMsgVA )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for ConstructPartialMsgVA.");
        if ( LastError > 0 )
          v36 = (unsigned __int16)LastError | 0x80070000;
        else
          v36 = LastError;
        LODWORD(EndPtr) = v36;
        *(_QWORD *)v103 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v35,
          3,
          (unsigned int)": {0}",
          (__int64)v103);
      }
      if ( LastError )
      {
        v7 = 695;
        goto LABEL_39;
      }
      goto LABEL_97;
    }
    vpfnCurrentIP = (void *(*)(void))GetProcAddress(vhWdsDll, "CurrentIP");
    if ( !vpfnCurrentIP )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get proc address for CurrentIP.");
        if ( LastError > 0 )
          v38 = (unsigned __int16)LastError | 0x80070000;
        else
          v38 = LastError;
        LODWORD(EndPtr) = v38;
        *(_QWORD *)v103 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          3,
          (unsigned int)": {0}",
          (__int64)v103);
      }
      if ( LastError )
      {
        v7 = 698;
        goto LABEL_39;
      }
      goto LABEL_97;
    }
    WdsGetSetupLogPath((wchar_t **)&lpExistingFileName);
    v41 = lpExistingFileName;
    if ( lpExistingFileName )
    {
      v104[0] = 0;
      CbsRegQueryDWORDValue(v39, L"SYSTEM\\Setup", v40, L"SystemSetupInProgress", v104);
      v42 = v104[0];
      if ( !v104[0] )
      {
        v104[0] = 0;
        CbsRegQueryDWORDValue(v43, L"SYSTEM\\Setup", v44, L"OOBEInProgress", v104);
        v42 = v104[0];
      }
      v104[0] = v42;
      v4 = v42;
      if ( v42 )
      {
LABEL_107:
        v47 = 0;
        if ( !v4 )
        {
          if ( CbsRegQueryDWORDValue(
                 v43,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
                 v44,
                 L"EnableLog",
                 v104) < 0
            || (v50 = v104[0]) == 0 )
          {
            v8 = -2147467260;
            LODWORD(EndPtr) = -2147467260;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "WDS logging is not enabled in the registry, continuing without logging.");
              *(_QWORD *)v103 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v72,
                3,
                (unsigned int)": {}",
                (__int64)v103);
            }
            v10 = 834;
            goto LABEL_9;
          }
          v104[0] = CbsRegQueryStringValue(
                      v48,
                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration",
                      v49,
                      L"LogPath",
                      (wchar_t **)&lpExistingFileName);
          if ( (v104[0] & 0x80000000) == 0 && (v41 = lpExistingFileName, *lpExistingFileName) )
          {
            v51 = DirectoryFromPath((wchar_t *)lpExistingFileName);
            v8 = v51;
            if ( v51 < 0 )
            {
              LODWORD(EndPtr) = v51;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v103 = v41;
                LogAdapter::Logger::LogNumObjects<wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to get log path from: {}",
                  (__int64)v103);
                *(_QWORD *)v105 = &EndPtr;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v52,
                  3,
                  (unsigned int)": {}",
                  (__int64)v105);
              }
              v10 = 752;
              goto LABEL_9;
            }
            v2 = v108;
            v53 = -1;
            do
              ++v53;
            while ( *(_WORD *)(v108 + 2 * v53) );
            if ( v53 && *(_WORD *)(v108 + 2 * v53 - 2) == 92 )
              *(_WORD *)(v108 + 2 * v53 - 2) = 0;
          }
          else
          {
            v54 = SczAllocFromSz(&lpExistingFileName, v109);
            v8 = v54;
            if ( v54 < 0 )
            {
              v11 = (unsigned int)v54;
              v10 = 765;
              goto LABEL_10;
            }
            v55 = SczEnsureBackslashTerminated(&lpExistingFileName);
            v8 = v55;
            if ( v55 < 0 )
            {
              v11 = (unsigned int)v55;
              v10 = 766;
              goto LABEL_10;
            }
            v56 = SczAllocConcatSz(&lpExistingFileName, L"Logs\\CBS");
            v8 = v56;
            if ( v56 < 0 )
            {
              v11 = (unsigned int)v56;
              v10 = 767;
              goto LABEL_10;
            }
            v57 = SczAllocFromSz(&v108, lpExistingFileName);
            v8 = v57;
            if ( v57 < 0 )
            {
              v11 = (unsigned int)v57;
              v10 = 768;
              goto LABEL_10;
            }
            v58 = SczAllocConcatSz(&lpExistingFileName, L"\\CBS.log");
            v8 = v58;
            if ( v58 < 0 )
            {
              v11 = (unsigned int)v58;
              v10 = 769;
              goto LABEL_10;
            }
            v41 = lpExistingFileName;
            v2 = v108;
          }
          Directory = RecursivelyCreateDirectory(v2, 0);
          v60 = Directory;
          if ( Directory < 0 )
          {
            LODWORD(EndPtr) = Directory;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v103 = v41;
              LogAdapter::Logger::LogNumObjects<wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to ensure that logging directory exists: {}",
                (__int64)v103);
              *(_QWORD *)v105 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v61,
                3,
                (unsigned int)": {}",
                (__int64)v105);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x306,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
              (const char *)v60,
              (int)v100);
            v8 = v60;
            goto LABEL_203;
          }
          v103[0] = 0;
          v105[0] = 0;
          if ( (int)OnlineConfigGetProperty(L"CBSLogMaxInMB", v105) < 0 || (v62 = v105[0], v105[0] > 0x28) )
            v62 = 15;
          if ( (int)OnlineConfigGetProperty(L"CBSLogHardMaxInMB", v103) < 0 || (v63 = v103[0], v103[0] < v62) )
            v63 = 100;
          *(_QWORD *)v103 = 0;
          if ( (int)FileSize(v41, v103) >= 0
            && *(_QWORD *)v103 > (unsigned __int64)(v62 << 20)
            && (CbsRegQueryDWORDValue(
                  v64,
                  L"System\\CurrentControlSet\\Services\\TrustedInstaller",
                  v65,
                  L"Start",
                  (unsigned int *)&EndPtr) < 0
             || (_DWORD)EndPtr != 2
             || *(_QWORD *)v103 > (unsigned __int64)(v63 << 20)) )
          {
            GetSystemTime(&SystemTime);
            wHour = SystemTime.wHour;
            wDay = SystemTime.wDay;
            LODWORD(v100) = SystemTime.wMonth;
            v66 = SczAllocFormatted(
                    &lpNewFileName,
                    L"%ws\\CbsPersist_%02d%02d%02d%02d%02d%02d.log",
                    v2,
                    SystemTime.wYear);
            if ( v66 < 0 )
            {
              *(_QWORD *)v103 = v41;
              LogAdapter::TraceAtLevelHr<long,wchar_t *>(
                0,
                (unsigned int)v66,
                "Could not allocate a backup name for the log file: {}, we'll just continue with our current log file.",
                v103);
            }
            else
            {
              OnlineMaintenanceActionSet(v68, v67);
              *(_QWORD *)v103 = lpNewFileName;
              *(_QWORD *)v105 = v41;
              if ( !MoveFileExW(v41, lpNewFileName, 1u) )
              {
                v69 = GetLastError();
                LogAdapter::TraceAtLevelWin32<unsigned long,wchar_t *,wchar_t *>(
                  v70,
                  v69,
                  v71,
                  (unsigned int)v105,
                  (__int64)v103);
              }
            }
          }
          v47 = v104[0];
          if ( !v50 )
          {
            SetupLog = 0;
            if ( v42 )
              goto LABEL_206;
            goto LABEL_197;
          }
        }
        if ( v41 )
        {
          FileAttributesW = GetFileAttributesW(v41);
          if ( FileAttributesW == -1 )
          {
            GetLastError();
          }
          else if ( (FileAttributesW & 0x10) == 0 )
          {
            goto LABEL_165;
          }
        }
        LODWORD(EndPtr) = 1;
        Property = OnlineConfigGetProperty(L"CBSLogCompress", (unsigned int *)&EndPtr);
        v76 = (int)EndPtr;
        EndPtr = 0;
        if ( Property < 0 )
          v76 = 1;
        if ( v76 )
        {
          InitPointer = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                          &EndPtr,
                          v75);
          CreateCompressedFile((_DWORD)v41, v78, v79, v80, (_DWORD)v100, wDay, wHour, InitPointer);
        }
        else
        {
          v81 = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                  &EndPtr,
                  v75);
          CreateFileWithRetries((_DWORD)v41, v82, v83, v84, (_DWORD)v100, wDay, wHour, v81);
        }
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&EndPtr);
LABEL_165:
        if ( v42 )
        {
          if ( !((__int64 (__fastcall *)(_QWORD, __int64, const WCHAR *))vpfnWdsSetupLogInit)(0, 45056, v41) )
          {
            LODWORD(EndPtr) = -2147418113;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v103 = v41;
              *(_QWORD *)v105 = v16;
              LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                v85,
                v86,
                (unsigned int)"Failed to initialize logging with dll: {}, log directory: {}",
                (__int64)v105,
                (__int64)v103);
              *(_QWORD *)v104 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v87,
                3,
                (unsigned int)": {}",
                (__int64)v104);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x36B,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
              (const char *)0x8000FFFFLL,
              (int)v100);
            v8 = -2147418113;
            goto LABEL_203;
          }
LABEL_206:
          v8 = v47;
          goto LABEL_207;
        }
        if ( !(unsigned int)((__int64 (__fastcall *)(const WCHAR *, __int64))vpfnWdsGenericSetupLogInit)(v41, 0x8000) )
        {
          v8 = -2147467259;
          LODWORD(EndPtr) = -2147467259;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v103 = v41;
            *(_QWORD *)v105 = v16;
            LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              v88,
              v89,
              (unsigned int)"Failed to initialize logging with DLL: {}, log file: {}",
              (__int64)v105,
              (__int64)v103);
            *(_QWORD *)v104 = &EndPtr;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v90,
              3,
              (unsigned int)": {}",
              (__int64)v104);
          }
          v10 = 883;
          goto LABEL_9;
        }
        v91 = 1024;
        memset(String, 0, sizeof(String));
        if ( GetEnvironmentVariableW(L"COMPONENT_BASED_SERVICING_LOGLEVEL", String, 0x40u) - 1 <= 0x3E )
        {
          EndPtr = 0;
          v91 = wcstoul(String, &EndPtr, 16);
          if ( !v91 && *errno() == 34 )
            v91 = 1024;
        }
        SetupLog = vpfnWdsGetSetupLog();
        if ( !SetupLog )
        {
          LogAdapter::TraceAtLevelHr<long,>(0, 2147549183LL, "Failed to acquire log manager");
LABEL_180:
          v8 = 0;
          goto LABEL_207;
        }
        if ( v91 == 256 )
        {
          v93 = 0;
        }
        else if ( v91 == 512 )
        {
          v93 = 0x2000000;
        }
        else
        {
          v93 = 0x4000000;
          if ( v91 != 1024 )
            v93 = 150994944;
        }
        v113 = v93;
        v112 = L"Sev";
        v115 = 0;
        v119[1] = L"Sev";
        v119[0] = L"DT";
        v119[2] = L"Msg";
        v119[3] = L"Err";
        v119[4] = L"Uid";
        v119[5] = 0;
        v116 = v41;
        v117 = 0;
        v114 = 1;
        v118 = 0;
        v100 = (wchar_t **)v119;
        if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, void *, const wchar_t **, void *))SetupLog)(
                SetupLog,
                &unk_1800B0C40,
                &v112,
                &unk_1800B0C50) )
        {
          LogAdapter::TraceAtLevelHr<long,>(0, 2147549183LL, "Failed to configure logging settings");
          vpfnWdsSetupLogDestroy();
          goto LABEL_180;
        }
        ProcAddress = GetProcAddress(vhWdsDll, "WdsLogRegisterProvider");
        if ( ProcAddress
          && ((unsigned int (__fastcall *)(__int128 *, __int64 (__fastcall *)()))ProcAddress)(
               &xmmword_1800B0C30,
               CreateCbsLogMonitorProvider) == 1 )
        {
          v100 = (wchar_t **)v119;
          if ( (**(unsigned int (__fastcall ***)(struct ILogManager *, void *, const wchar_t **, void *))SetupLog)(
                 SetupLog,
                 &unk_1800B0C40,
                 &v112,
                 &unk_1800B0C50) )
          {
            goto LABEL_197;
          }
          v96 = "Unable to add CbsLogMonitor provider";
        }
        else
        {
          v96 = "Unable to register CbsLogMonitor provider";
        }
        LogAdapter::TraceAtLevel<>(v95, v96);
LABEL_197:
        if ( v2 )
        {
          v97 = DeleteOldestLogFiles(v2);
          v8 = v97;
          if ( v97 < 0 )
          {
            LODWORD(EndPtr) = v97;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to delete extra backup log files.");
              *(_QWORD *)v103 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v98,
                3,
                (unsigned int)": {}",
                (__int64)v103);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3CC,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
              (const char *)v8,
              (int)v100);
            if ( SetupLog )
              vpfnWdsSetupLogDestroy();
            goto LABEL_203;
          }
        }
        if ( SetupLog )
          vpfnWdsSetupLogDestroy();
        goto LABEL_206;
      }
    }
    else
    {
      v42 = 0;
    }
    memset(Buffer, 0, sizeof(Buffer));
    if ( GetEnvironmentVariableW(L"COMPONENT_BASED_SERVICING_LOGFILE", Buffer, 0x200u) - 1 <= 0x1FE )
    {
      v45 = SczAllocFromSz(&lpExistingFileName, Buffer);
      v46 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D9,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
          (const char *)(unsigned int)v45,
          (int)v100);
        v8 = v46;
        goto LABEL_203;
      }
      v41 = lpExistingFileName;
      v4 = 1;
      v104[0] = 1;
    }
    goto LABEL_107;
  }
  LastError = GetLastError();
  if ( LastError != 126 )
  {
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v103 = v16;
      LogAdapter::Logger::LogNumObjects<wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to load WDSCORE DLL: {}",
        (__int64)v103);
      if ( LastError > 0 )
        v24 = (unsigned __int16)LastError | 0x80070000;
      else
        v24 = LastError;
      LODWORD(EndPtr) = v24;
      *(_QWORD *)v105 = &EndPtr;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {0}",
        (__int64)v105);
    }
    if ( LastError )
    {
      v7 = 674;
LABEL_39:
      v6 = (unsigned int)LastError;
LABEL_40:
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
             (const char *)v6,
             (unsigned int)v100);
      goto LABEL_203;
    }
    goto LABEL_97;
  }
  EndPtr = v16;
  LogAdapter::TraceAtLevelLastError<wchar_t *>(v21, v20, &EndPtr);
  v8 = 1;
LABEL_207:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v108);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v109);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  return v8;
}

```

## disassembly

```asm
0x180044c90  push    rbp
0x180044c92  push    rbx
0x180044c93  push    rsi
0x180044c94  push    rdi
0x180044c95  push    r12
0x180044c97  push    r13
0x180044c99  push    r14
0x180044c9b  push    r15
0x180044c9d  lea     rbp, [rsp-4A8h]
0x180044ca5  sub     rsp, 5A8h
0x180044cac  mov     rax, cs:__security_cookie
0x180044cb3  xor     rax, rsp
0x180044cb6  mov     [rbp+4E0h+var_50], rax
0x180044cbd  xor     r12d, r12d
0x180044cc0  xorps   xmm0, xmm0
0x180044cc3  mov     ebx, r12d
0x180044cc6  mov     [rsp+5E0h+lpExistingFileName], r12
0x180044ccb  mov     rsi, rcx
0x180044cce  mov     [rbp+4E0h+lpNewFileName], r12
0x180044cd2  mov     [rsp+5E0h+lpLibFileName], r12
0x180044cd7  mov     r14d, r12d
0x180044cda  lea     r15d, [r12+3]
0x180044cdf  mov     [rbp+4E0h+var_560], r12
0x180044ce3  lea     r13d, [r12+1]
0x180044ce8  mov     dword ptr [rbp+4E0h+EndPtr], r15d
0x180044cec  mov     eax, r13d
0x180044cef  mov     [rsp+5E0h+var_588], r12d
0x180044cf4  movups  xmmword ptr [rbp+4E0h+SystemTime.wYear], xmm0
0x180044cf8  mov     [rsp+5E0h+var_568], rbx
0x180044cfd  lock xadd cs:?vcWdsLoadOperations@@3JA, eax; long vcWdsLoadOperations
0x180044d05  add     eax, r13d
0x180044d08  cmp     eax, r13d
0x180044d0b  jle     short loc_180044D6A
0x180044d0d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044d14  test    rcx, rcx
0x180044d17  jz      short loc_180044D5A
0x180044d19  lea     r9, aWdsLoggerIsAlr; "Wds logger is already initialized"
0x180044d20  mov     r8d, r15d
0x180044d23  xor     edx, edx
0x180044d25  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180044d2a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044d31  lea     rax, [rbp+4E0h+EndPtr]
0x180044d35  mov     qword ptr [rsp+5E0h+var_590], rax
0x180044d3a  lea     r9, a0; ": {0}"
0x180044d41  lea     rax, [rsp+5E0h+var_590]
0x180044d46  mov     dword ptr [rbp+4E0h+EndPtr], 800704DFh
0x180044d4d  mov     r8d, r15d
0x180044d50  mov     [rsp+5E0h+var_5C0], rax
0x180044d55  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180044d5a  mov     r9d, 4DFh
0x180044d60  mov     edx, 284h
0x180044d65  jmp     loc_18004500C
0x180044d6a  test    rsi, rsi
0x180044d6d  jnz     short loc_180044DDD
0x180044d6f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044d76  mov     ebx, 80070057h
0x180044d7b  mov     dword ptr [rbp+4E0h+EndPtr], ebx
0x180044d7e  test    rcx, rcx
0x180044d81  jz      short loc_180044DBD
0x180044d83  lea     r9, aNoCoreDllPathS; "No core dll path specified"
0x180044d8a  mov     r8d, r15d
0x180044d8d  xor     edx, edx
0x180044d8f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180044d94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044d9b  lea     rax, [rbp+4E0h+EndPtr]
0x180044d9f  mov     qword ptr [rsp+5E0h+var_590], rax
0x180044da4  lea     r9, asc_1800AFB70; ": {}"
0x180044dab  lea     rax, [rsp+5E0h+var_590]
0x180044db0  mov     r8d, r15d
0x180044db3  mov     [rsp+5E0h+var_5C0], rax; int
0x180044db8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180044dbd  mov     edx, 287h; void *
0x180044dc2  mov     r9d, ebx; char *
0x180044dc5  mov     rcx, [rbp+4E8h]; this
0x180044dcc  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180044dd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044dd8  jmp     loc_180045E75
0x180044ddd  lea     rcx, [rbp+4E0h+var_560]
0x180044de1  call    PathGetWindowsDirectory
0x180044de6  mov     edi, eax
0x180044de8  test    eax, eax
0x180044dea  jns     short loc_180044E57
0x180044dec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044df3  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x180044df6  test    rcx, rcx
0x180044df9  jz      short loc_180044E35
0x180044dfb  lea     r9, aFailedToGetWin; "Failed to get windows directory for WDS"...
0x180044e02  mov     r8d, r15d
0x180044e05  xor     edx, edx
0x180044e07  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180044e0c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044e13  lea     rax, [rbp+4E0h+EndPtr]
0x180044e17  mov     qword ptr [rsp+5E0h+var_590], rax
0x180044e1c  lea     r9, asc_1800AFB70; ": {}"
0x180044e23  lea     rax, [rsp+5E0h+var_590]
0x180044e28  mov     r8d, r15d
0x180044e2b  mov     [rsp+5E0h+var_5C0], rax; int
0x180044e30  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180044e35  mov     edx, 28Ah; void *
0x180044e3a  mov     rcx, [rbp+4E8h]; this
0x180044e41  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180044e48  mov     r9d, edi; char *
0x180044e4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044e50  mov     ebx, edi
0x180044e52  jmp     loc_180045E75
0x180044e57  mov     rdx, rsi
0x180044e5a  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180044e5f  call    SczAllocFromSz
0x180044e64  mov     edi, eax
0x180044e66  test    eax, eax
0x180044e68  jns     short loc_180044E71
0x180044e6a  mov     edx, 28Ch
0x180044e6f  jmp     short loc_180044E3A
0x180044e71  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180044e76  call    SczEnsureBackslashTerminated
0x180044e7b  mov     edi, eax
0x180044e7d  test    eax, eax
0x180044e7f  jns     short loc_180044E88
0x180044e81  mov     edx, 28Dh
0x180044e86  jmp     short loc_180044E3A
0x180044e88  lea     rdx, aWdscoreDll; "wdscore.dll"
0x180044e8f  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180044e94  call    SczAllocConcatSz
0x180044e99  mov     edi, eax
0x180044e9b  test    eax, eax
0x180044e9d  jns     short loc_180044EA6
0x180044e9f  mov     edx, 28Eh
0x180044ea4  jmp     short loc_180044E3A
0x180044ea6  mov     rdi, [rsp+5E0h+lpLibFileName]
0x180044eab  mov     rcx, rdi; lpLibFileName
0x180044eae  call    cs:__imp_LoadLibraryW
0x180044eb5  nop     dword ptr [rax+rax+00h]
0x180044eba  mov     rdx, rax
0x180044ebd  lea     rcx, ?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x180044ec4  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180044ec9  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; hModule
0x180044ed0  test    rcx, rcx
0x180044ed3  jnz     loc_180045026
0x180044ed9  mov     rdx, [rbp+4E0h+var_560]
0x180044edd  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180044ee2  call    SczAllocFromSz
0x180044ee7  mov     edi, eax
0x180044ee9  test    eax, eax
0x180044eeb  jns     short loc_180044EF7
0x180044eed  mov     edx, 293h
0x180044ef2  jmp     loc_180044E3A
0x180044ef7  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180044efc  call    SczEnsureBackslashTerminated
0x180044f01  mov     edi, eax
0x180044f03  test    eax, eax
0x180044f05  jns     short loc_180044F11
0x180044f07  mov     edx, 294h
0x180044f0c  jmp     loc_180044E3A
0x180044f11  lea     r8, aWdscoreDll; "wdscore.dll"
0x180044f18  lea     rdx, aSystem32; "system32\\"
0x180044f1f  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180044f24  call    SczAllocConcat2Sz
0x180044f29  mov     edi, eax
0x180044f2b  test    eax, eax
0x180044f2d  jns     short loc_180044F39
0x180044f2f  mov     edx, 295h
0x180044f34  jmp     loc_180044E3A
0x180044f39  mov     rdi, [rsp+5E0h+lpLibFileName]
0x180044f3e  mov     rcx, rdi; lpLibFileName
0x180044f41  call    cs:__imp_LoadLibraryW
0x180044f48  nop     dword ptr [rax+rax+00h]
0x180044f4d  mov     rdx, rax
0x180044f50  lea     rcx, ?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x180044f57  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180044f5c  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x180044f63  test    rcx, rcx
0x180044f66  jnz     loc_180045026
0x180044f6c  call    cs:__imp_GetLastError
0x180044f73  nop     dword ptr [rax+rax+00h]
0x180044f78  mov     ebx, eax
0x180044f7a  cmp     eax, 7Eh ; '~'
0x180044f7d  jnz     short loc_180044F94
0x180044f7f  lea     r8, [rbp+4E0h+EndPtr]
0x180044f83  mov     [rbp+4E0h+EndPtr], rdi
0x180044f87  call    ??$TraceAtLevelLastError@PEA_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEA_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t *>(LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x180044f8c  mov     ebx, r13d
0x180044f8f  jmp     loc_180045EC8
0x180044f94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044f9b  test    rcx, rcx
0x180044f9e  jz      short loc_180044FFC
0x180044fa0  lea     rax, [rsp+5E0h+var_590]
0x180044fa5  mov     qword ptr [rsp+5E0h+var_590], rdi
0x180044faa  lea     r9, aFailedToLoadWd; "Failed to load WDSCORE DLL: {}"
0x180044fb1  mov     [rsp+5E0h+var_5C0], rax
0x180044fb6  mov     r8d, r15d
0x180044fb9  xor     edx, edx
0x180044fbb  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x180044fc0  test    ebx, ebx
0x180044fc2  jg      short loc_180044FC8
0x180044fc4  mov     eax, ebx
0x180044fc6  jmp     short loc_180044FD0
0x180044fc8  movzx   eax, bx
0x180044fcb  or      eax, 80070000h
0x180044fd0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180044fd7  lea     r9, a0; ": {0}"
0x180044fde  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x180044fe1  mov     r8d, r15d
0x180044fe4  lea     rax, [rbp+4E0h+EndPtr]
0x180044fe8  mov     qword ptr [rsp+5E0h+var_580], rax
0x180044fed  lea     rax, [rsp+5E0h+var_580]
0x180044ff2  mov     [rsp+5E0h+var_5C0], rax; unsigned int
0x180044ff7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180044ffc  test    ebx, ebx
0x180044ffe  jz      loc_180045474
0x180045004  mov     edx, 2A2h; void *
0x180045009  mov     r9d, ebx; char *
0x18004500c  mov     rcx, [rbp+4E8h]; this
0x180045013  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18004501a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004501f  mov     ebx, eax
0x180045021  jmp     loc_180045E75
0x180045026  lea     rdx, aWdssetuplogini; "WdsSetupLogInit"
0x18004502d  call    cs:__imp_GetProcAddress
0x180045034  nop     dword ptr [rax+rax+00h]
0x180045039  mov     cs:?vpfnWdsSetupLogInit@@3P6APEAVILogManager@@PEAUHINSTANCE__@@KPEB_W@ZEA, rax; ILogManager * (*vpfnWdsSetupLogInit)(HINSTANCE__ *,ulong,wchar_t const *)
0x180045040  test    rax, rax
0x180045043  jnz     short loc_1800450BE
0x180045045  call    cs:__imp_GetLastError
0x18004504c  nop     dword ptr [rax+rax+00h]
0x180045051  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045058  mov     ebx, eax
0x18004505a  test    rcx, rcx
0x18004505d  jz      short loc_1800450AC
0x18004505f  lea     r9, aFailedToGetPro_1; "Failed to get proc address for WdsSetup"...
0x180045066  mov     r8d, r15d
0x180045069  xor     edx, edx
0x18004506b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180045070  test    ebx, ebx
0x180045072  jg      short loc_180045078
0x180045074  mov     eax, ebx
0x180045076  jmp     short loc_180045080
0x180045078  movzx   eax, bx
0x18004507b  or      eax, 80070000h
0x180045080  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045087  lea     r9, a0; ": {0}"
0x18004508e  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x180045091  mov     r8d, r15d
0x180045094  lea     rax, [rbp+4E0h+EndPtr]
0x180045098  mov     qword ptr [rsp+5E0h+var_590], rax
0x18004509d  lea     rax, [rsp+5E0h+var_590]
0x1800450a2  mov     [rsp+5E0h+var_5C0], rax
0x1800450a7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800450ac  test    ebx, ebx
0x1800450ae  jz      loc_180045474
0x1800450b4  mov     edx, 2A7h
0x1800450b9  jmp     loc_180045009
0x1800450be  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; hModule
0x1800450c5  lea     rdx, aWdsgenericsetu; "WdsGenericSetupLogInit"
0x1800450cc  call    cs:__imp_GetProcAddress
0x1800450d3  nop     dword ptr [rax+rax+00h]
0x1800450d8  mov     cs:?vpfnWdsGenericSetupLogInit@@3P6AHPEB_WK@ZEA, rax; int (*vpfnWdsGenericSetupLogInit)(wchar_t const *,ulong)
0x1800450df  test    rax, rax
0x1800450e2  jnz     short loc_18004515D
0x1800450e4  call    cs:__imp_GetLastError
0x1800450eb  nop     dword ptr [rax+rax+00h]
0x1800450f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800450f7  mov     ebx, eax
0x1800450f9  test    rcx, rcx
0x1800450fc  jz      short loc_18004514B
0x1800450fe  lea     r9, aFailedToGetPro_4; "Failed to get proc address for WdsGener"...
0x180045105  mov     r8d, r15d
0x180045108  xor     edx, edx
0x18004510a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004510f  test    ebx, ebx
0x180045111  jg      short loc_180045117
0x180045113  mov     eax, ebx
0x180045115  jmp     short loc_18004511F
0x180045117  movzx   eax, bx
0x18004511a  or      eax, 80070000h
0x18004511f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045126  lea     r9, a0; ": {0}"
0x18004512d  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x180045130  mov     r8d, r15d
0x180045133  lea     rax, [rbp+4E0h+EndPtr]
0x180045137  mov     qword ptr [rsp+5E0h+var_590], rax
0x18004513c  lea     rax, [rsp+5E0h+var_590]
0x180045141  mov     [rsp+5E0h+var_5C0], rax
0x180045146  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004514b  test    ebx, ebx
0x18004514d  jz      loc_180045474
0x180045153  mov     edx, 2AAh
0x180045158  jmp     loc_180045009
0x18004515d  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; hModule
0x180045164  lea     rdx, aWdsgetsetuplog; "WdsGetSetupLog"
0x18004516b  call    cs:__imp_GetProcAddress
0x180045172  nop     dword ptr [rax+rax+00h]
0x180045177  mov     cs:?vpfnWdsGetSetupLog@@3P6APEAVILogManager@@XZEA, rax; ILogManager * (*vpfnWdsGetSetupLog)(void)
0x18004517e  test    rax, rax
0x180045181  jnz     short loc_1800451FC
0x180045183  call    cs:__imp_GetLastError
0x18004518a  nop     dword ptr [rax+rax+00h]
0x18004518f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045196  mov     ebx, eax
0x180045198  test    rcx, rcx
0x18004519b  jz      short loc_1800451EA
  ... truncated ...
```

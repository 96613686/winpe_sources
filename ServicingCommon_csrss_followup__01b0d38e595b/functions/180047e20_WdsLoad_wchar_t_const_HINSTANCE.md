# WdsLoad(wchar_t const *,HINSTANCE__ *)

- ea: `0x180047e20`
- end: `0x18004904b`
- name: `?WdsLoad@@YAJPEB_WPEAUHINSTANCE__@@@Z`
- size: `4651`
- prototype: `__int64 __fastcall(const wchar_t *, HINSTANCE)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800492e0`

## callees

- `0x180018df0`
- `0x180020440`
- `0x180020dc0`
- `0x180023664`
- `0x1800242d0`
- `0x180026c90`
- `0x1800278d0`
- `0x180027eb0`
- `0x18002d2b0`
- `0x180046650`
- `0x1800468fc`
- `0x180046ab4`
- `0x180046ca4`
- `0x180047168`
- `0x180047198`
- `0x180047210`
- `0x1800472ac`
- `0x180047334`
- `0x1800474dc`
- `0x180047884`
- `0x180047c5c`
- `0x180047da0`
- `0x180047e20`
- `0x18004def8`
- `0x18004e0f8`
- `0x18004e404`
- `0x18004ecd0`
- `0x18004f0e4`
- `0x18004f780`
- `0x18004fb00`
- `0x18004fdc0`
- `0x1800504d0`
- `0x180050980`
- `0x180050dac`
- `0x18005130c`
- `0x1800519ac`
- `0x180051a6c`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800480f4`
- `KERNEL32!GetLastError` at `0x1800481cd`
- `KERNEL32!GetLastError` at `0x18004826c`
- `KERNEL32!GetLastError` at `0x18004830b`
- `KERNEL32!GetLastError` at `0x1800483aa`
- `KERNEL32!GetLastError` at `0x180048449`
- `KERNEL32!GetLastError` at `0x1800484e8`
- `KERNEL32!GetLastError` at `0x180048587`
- `KERNEL32!GetLastError` at `0x180048a7a`
- `KERNEL32!GetLastError` at `0x180048b36`
- `KERNEL32!GetLastError` at `0x1800480f4`
- `KERNEL32!GetLastError` at `0x1800481cd`
- `KERNEL32!GetLastError` at `0x18004826c`
- `KERNEL32!GetLastError` at `0x18004830b`
- `KERNEL32!GetLastError` at `0x1800483aa`
- `KERNEL32!GetLastError` at `0x180048449`
- `KERNEL32!GetLastError` at `0x1800484e8`
- `KERNEL32!GetLastError` at `0x180048587`
- `KERNEL32!GetLastError` at `0x180048a7a`
- `KERNEL32!GetLastError` at `0x180048b36`
- `KERNEL32!GetProcAddress` at `0x1800481b5`
- `KERNEL32!GetProcAddress` at `0x180048254`
- `KERNEL32!GetProcAddress` at `0x1800482f3`
- `KERNEL32!GetProcAddress` at `0x180048392`
- `KERNEL32!GetProcAddress` at `0x180048431`
- `KERNEL32!GetProcAddress` at `0x1800484d0`
- `KERNEL32!GetProcAddress` at `0x18004856f`
- `KERNEL32!GetProcAddress` at `0x180048e7a`
- `KERNEL32!GetProcAddress` at `0x1800481b5`
- `KERNEL32!GetProcAddress` at `0x180048254`
- `KERNEL32!GetProcAddress` at `0x1800482f3`
- `KERNEL32!GetProcAddress` at `0x180048392`
- `KERNEL32!GetProcAddress` at `0x180048431`
- `KERNEL32!GetProcAddress` at `0x1800484d0`
- `KERNEL32!GetProcAddress` at `0x18004856f`
- `KERNEL32!GetProcAddress` at `0x180048e7a`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800486a5`
- `KERNEL32!GetEnvironmentVariableW` at `0x180048cfd`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800486a5`
- `KERNEL32!GetEnvironmentVariableW` at `0x180048cfd`
- `KERNEL32!LoadLibraryW` at `0x18004802d`
- `KERNEL32!LoadLibraryW` at `0x1800480c9`
- `KERNEL32!LoadLibraryW` at `0x18004802d`
- `KERNEL32!LoadLibraryW` at `0x1800480c9`
- `KERNEL32!MoveFileExW` at `0x180048a66`
- `KERNEL32!MoveFileExW` at `0x180048a66`
- `KERNEL32!GetSystemTime` at `0x1800489f6`
- `KERNEL32!GetSystemTime` at `0x1800489f6`
- `KERNEL32!GetFileAttributesW` at `0x180048b25`
- `KERNEL32!GetFileAttributesW` at `0x180048b25`

## string_xrefs

- `0x18004869e`: `COMPONENT_BASED_SERVICING_LOGFILE`
- `0x180048cf6`: `COMPONENT_BASED_SERVICING_LOGLEVEL`
- `0x180048001`: `wdscore.dll`
- `0x180048096`: `wdscore.dll`
- `0x180047eb1`: `Wds logger is already initialized`
- `0x180047f0b`: `No core dll path specified`
- `0x180047f83`: `Failed to get windows directory for WDSCORE DLL path.`
- `0x18004809d`: `system32\`
- `0x180048132`: `Failed to load WDSCORE DLL: {}`
- `0x18004870a`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x180048731`: `LogPath`
- `0x18004873d`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide\Configuration`
- `0x180048792`: `Failed to get log path from: {}`
- `0x1800488ed`: `Failed to ensure that logging directory exists: {}`
- `0x1800489c8`: `System\CurrentControlSet\Services\TrustedInstaller`
- `0x180048ac7`: `WDS logging is not enabled in the registry, continuing without logging.`
- `0x180048b52`: `CBSLogCompress`
- `0x180048bf4`: `Failed to initialize logging with dll: {}, log directory: {}`
- `0x180048c82`: `Failed to initialize logging with DLL: {}, log file: {}`
- `0x180048e48`: `Failed to configure logging settings`
- `0x180048f38`: `Failed to delete extra backup log files.`

## pseudocode

```c
__int64 __fastcall WdsLoad(const wchar_t *a1, HINSTANCE a2)
{
  unsigned int v2; // r12d
  __int64 v3; // rbx
  int v5; // r15d
  unsigned int v6; // esi
  int v7; // edx
  __int64 v8; // rdx
  int v9; // edx
  unsigned __int64 v10; // r9
  int WindowsDirectory; // eax
  int v12; // edx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  wchar_t *v16; // rdi
  HMODULE LibraryW; // rax
  HMODULE v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  HMODULE v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  signed int LastError; // ebx
  int v26; // edx
  unsigned int v27; // eax
  __int64 v28; // rdx
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
  int v39; // edx
  unsigned int v40; // eax
  int v41; // edx
  unsigned int v42; // eax
  HKEY v43; // rcx
  unsigned int v44; // r8d
  const WCHAR *v45; // r14
  unsigned int v46; // r13d
  HKEY v47; // rcx
  unsigned int v48; // r8d
  int v49; // eax
  HKEY v50; // rcx
  unsigned int v51; // r8d
  unsigned int v52; // r15d
  int v53; // eax
  int v54; // edx
  __int64 v55; // rcx
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int Directory; // eax
  int v62; // edx
  unsigned int v63; // esi
  unsigned int v64; // r12d
  HKEY v65; // rcx
  unsigned int v66; // r8d
  int v67; // eax
  int v68; // edx
  __int64 v69; // rcx
  __int64 v70; // r8
  DWORD v71; // eax
  int v72; // ecx
  int v73; // r8d
  int v74; // edx
  DWORD FileAttributesW; // eax
  int Property; // eax
  __int64 v77; // rdx
  int v78; // ecx
  __int64 InitPointer; // rax
  int v80; // edx
  int v81; // r8d
  int v82; // r9d
  __int64 v83; // rax
  int v84; // edx
  int v85; // r8d
  int v86; // r9d
  int v87; // edx
  int v88; // r8d
  int v89; // edx
  int v90; // edx
  int v91; // r8d
  int v92; // edx
  unsigned int v93; // edi
  struct ILogManager *SetupLog; // r15
  int v95; // eax
  FARPROC ProcAddress; // rax
  __int64 v97; // rcx
  const char *v98; // rdx
  int v99; // eax
  int v100; // edx
  wchar_t **v102; // [rsp+20h] [rbp-E0h]
  int wDay; // [rsp+28h] [rbp-D8h]
  int wHour; // [rsp+30h] [rbp-D0h]
  unsigned int v105[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v106[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v107[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpLibFileName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v110; // [rsp+78h] [rbp-88h] BYREF
  __int64 v111; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpNewFileName; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *EndPtr; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v114; // [rsp+98h] [rbp-68h] BYREF
  int v115; // [rsp+A0h] [rbp-60h]
  __int64 v116; // [rsp+A4h] [rbp-5Ch]
  int v117; // [rsp+ACh] [rbp-54h]
  const WCHAR *v118; // [rsp+B0h] [rbp-50h]
  __int64 v119; // [rsp+B8h] [rbp-48h]
  __int64 v120; // [rsp+C0h] [rbp-40h]
  _QWORD v121[7]; // [rsp+C8h] [rbp-38h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+100h] [rbp+0h] BYREF
  WCHAR String[64]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Buffer[512]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5E8h] [rbp+4E8h]

  v2 = 0;
  v3 = 0;
  lpExistingFileName = 0;
  lpNewFileName = 0;
  lpLibFileName = 0;
  v5 = 0;
  v111 = 0;
  LODWORD(EndPtr) = 3;
  v106[0] = 0;
  SystemTime = 0;
  v110 = 0;
  if ( _InterlockedIncrement(&vcWdsLoadOperations) > 1 )
  {
    v6 = -2147023649;
    LODWORD(EndPtr) = -2147023649;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Wds logger is already initialized");
      *(_QWORD *)v105 = &EndPtr;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    v8 = 644;
LABEL_9:
    v10 = v6;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)v10,
      (int)v102);
LABEL_201:
    vpfnWdsSetupLogInit = 0;
    vpfnWdsGenericSetupLogInit = 0;
    vpfnWdsGetSetupLog = 0;
    vpfnWdsSetupLogDestroy = 0;
    vpfnWdsSetupLogMessageA = 0;
    vpfnConstructPartialMsgVA = 0;
    vpfnCurrentIP = 0;
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&vhWdsDll);
    goto LABEL_205;
  }
  if ( !a1 )
  {
    v6 = -2147024809;
    LODWORD(EndPtr) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No core dll path specified");
      *(_QWORD *)v105 = &EndPtr;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    v8 = 647;
    goto LABEL_9;
  }
  WindowsDirectory = PathGetWindowsDirectory(&v111, a2);
  v6 = WindowsDirectory;
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
      *(_QWORD *)v105 = &EndPtr;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v105);
    }
    v8 = 650;
    goto LABEL_9;
  }
  v13 = SczAllocFromSz(&lpLibFileName, a1);
  v6 = v13;
  if ( v13 < 0 )
  {
    v10 = (unsigned int)v13;
    v8 = 652;
    goto LABEL_10;
  }
  v14 = SczEnsureBackslashTerminated(&lpLibFileName);
  v6 = v14;
  if ( v14 < 0 )
  {
    v10 = (unsigned int)v14;
    v8 = 653;
    goto LABEL_10;
  }
  v15 = SczAllocConcatSz(&lpLibFileName, L"wdscore.dll");
  v6 = v15;
  if ( v15 < 0 )
  {
    v10 = (unsigned int)v15;
    v8 = 654;
    goto LABEL_10;
  }
  v16 = (wchar_t *)lpLibFileName;
  LibraryW = LoadLibraryW(lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(&vhWdsDll, LibraryW);
  v18 = vhWdsDll;
  if ( vhWdsDll )
    goto LABEL_39;
  v19 = SczAllocFromSz(&lpLibFileName, v111);
  v6 = v19;
  if ( v19 < 0 )
  {
    v10 = (unsigned int)v19;
    v8 = 659;
    goto LABEL_10;
  }
  v20 = SczEnsureBackslashTerminated(&lpLibFileName);
  v6 = v20;
  if ( v20 < 0 )
  {
    v10 = (unsigned int)v20;
    v8 = 660;
    goto LABEL_10;
  }
  v21 = SczAllocConcat2Sz(&lpLibFileName, L"system32\\", L"wdscore.dll");
  v6 = v21;
  if ( v21 < 0 )
  {
    v10 = (unsigned int)v21;
    v8 = 661;
    goto LABEL_10;
  }
  v16 = (wchar_t *)lpLibFileName;
  v22 = LoadLibraryW(lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(&vhWdsDll, v22);
  v18 = vhWdsDll;
  if ( vhWdsDll )
  {
LABEL_39:
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
          v30 = (unsigned __int16)LastError | 0x80070000;
        else
          v30 = LastError;
        LODWORD(EndPtr) = v30;
        *(_QWORD *)v105 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v29,
          3,
          (unsigned int)": {0}",
          (__int64)v105);
      }
      if ( LastError )
      {
        v28 = 679;
        goto LABEL_38;
      }
LABEL_95:
      v6 = 0;
      goto LABEL_201;
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
          v32 = (unsigned __int16)LastError | 0x80070000;
        else
          v32 = LastError;
        LODWORD(EndPtr) = v32;
        *(_QWORD *)v105 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          3,
          (unsigned int)": {0}",
          (__int64)v105);
      }
      if ( LastError )
      {
        v28 = 682;
        goto LABEL_38;
      }
      goto LABEL_95;
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
          v34 = (unsigned __int16)LastError | 0x80070000;
        else
          v34 = LastError;
        LODWORD(EndPtr) = v34;
        *(_QWORD *)v105 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v33,
          3,
          (unsigned int)": {0}",
          (__int64)v105);
      }
      if ( LastError )
      {
        v28 = 685;
        goto LABEL_38;
      }
      goto LABEL_95;
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
          v36 = (unsigned __int16)LastError | 0x80070000;
        else
          v36 = LastError;
        LODWORD(EndPtr) = v36;
        *(_QWORD *)v105 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v35,
          3,
          (unsigned int)": {0}",
          (__int64)v105);
      }
      if ( LastError )
      {
        v28 = 689;
        goto LABEL_38;
      }
      goto LABEL_95;
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
          v38 = (unsigned __int16)LastError | 0x80070000;
        else
          v38 = LastError;
        LODWORD(EndPtr) = v38;
        *(_QWORD *)v105 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          3,
          (unsigned int)": {0}",
          (__int64)v105);
      }
      if ( LastError )
      {
        v28 = 692;
        goto LABEL_38;
      }
      goto LABEL_95;
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
          v40 = (unsigned __int16)LastError | 0x80070000;
        else
          v40 = LastError;
        LODWORD(EndPtr) = v40;
        *(_QWORD *)v105 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v39,
          3,
          (unsigned int)": {0}",
          (__int64)v105);
      }
      if ( LastError )
      {
        v28 = 695;
        goto LABEL_38;
      }
      goto LABEL_95;
    }
    vpfnCurrentIP = (void *(*)(void))GetProcAddress(vhWdsDll, "CurrentIP");
    if ( !vpfnCurrentIP )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get proc address for CurrentIP.");
        if ( LastError > 0 )
          v42 = (unsigned __int16)LastError | 0x80070000;
        else
          v42 = LastError;
        LODWORD(EndPtr) = v42;
        *(_QWORD *)v105 = &EndPtr;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v41,
          3,
          (unsigned int)": {0}",
          (__int64)v105);
      }
      if ( LastError )
      {
        v28 = 698;
        goto LABEL_38;
      }
      goto LABEL_95;
    }
    WdsGetSetupLogPath((wchar_t **)&lpExistingFileName);
    v45 = lpExistingFileName;
    if ( lpExistingFileName )
    {
      v106[0] = 0;
      CbsRegQueryDWORDValue(v43, L"SYSTEM\\Setup", v44, L"SystemSetupInProgress", v106);
      v46 = v106[0];
      if ( !v106[0] )
      {
        v106[0] = 0;
        CbsRegQueryDWORDValue(v47, L"SYSTEM\\Setup", v48, L"OOBEInProgress", v106);
        v46 = v106[0];
      }
      v106[0] = v46;
      v5 = v46;
      if ( v46 )
      {
LABEL_105:
        if ( !v5 )
        {
          if ( CbsRegQueryDWORDValue(
                 v47,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
                 v48,
                 L"EnableLog",
                 v106) < 0
            || (v52 = v106[0]) == 0 )
          {
            v6 = -2147467260;
            LODWORD(EndPtr) = -2147467260;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "WDS logging is not enabled in the registry, continuing without logging.");
              *(_QWORD *)v105 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v74,
                3,
                (unsigned int)": {}",
                (__int64)v105);
            }
            v8 = 834;
            goto LABEL_9;
          }
          v106[0] = CbsRegQueryStringValue(
                      v50,
                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration",
                      v51,
                      L"LogPath",
                      (wchar_t **)&lpExistingFileName);
          if ( (v106[0] & 0x80000000) == 0 && (v45 = lpExistingFileName, *lpExistingFileName) )
          {
            v53 = DirectoryFromPath((wchar_t *)lpExistingFileName);
            v6 = v53;
            if ( v53 < 0 )
            {
              LODWORD(EndPtr) = v53;
              if ( LogAdapter::g_Logger )
              {
                *(_QWORD *)v105 = v45;
                LogAdapter::Logger::LogNumObjects<wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to get log path from: {}",
                  (__int64)v105);
                *(_QWORD *)v107 = &EndPtr;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v54,
                  3,
                  (unsigned int)": {}",
                  (__int64)v107);
              }
              v8 = 752;
              goto LABEL_9;
            }
            v3 = v110;
            v55 = -1;
            do
              ++v55;
            while ( *(_WORD *)(v110 + 2 * v55) );
            if ( v55 && *(_WORD *)(v110 + 2 * v55 - 2) == 92 )
              *(_WORD *)(v110 + 2 * v55 - 2) = 0;
          }
          else
          {
            v56 = SczAllocFromSz(&lpExistingFileName, v111);
            v6 = v56;
            if ( v56 < 0 )
            {
              v10 = (unsigned int)v56;
              v8 = 765;
              goto LABEL_10;
            }
            v57 = SczEnsureBackslashTerminated(&lpExistingFileName);
            v6 = v57;
            if ( v57 < 0 )
            {
              v10 = (unsigned int)v57;
              v8 = 766;
              goto LABEL_10;
            }
            v58 = SczAllocConcatSz(&lpExistingFileName, L"Logs\\CBS");
            v6 = v58;
            if ( v58 < 0 )
            {
              v10 = (unsigned int)v58;
              v8 = 767;
              goto LABEL_10;
            }
            v59 = SczAllocFromSz(&v110, lpExistingFileName);
            v6 = v59;
            if ( v59 < 0 )
            {
              v10 = (unsigned int)v59;
              v8 = 768;
              goto LABEL_10;
            }
            v60 = SczAllocConcatSz(&lpExistingFileName, L"\\CBS.log");
            v6 = v60;
            if ( v60 < 0 )
            {
              v10 = (unsigned int)v60;
              v8 = 769;
              goto LABEL_10;
            }
            v45 = lpExistingFileName;
            v3 = v110;
          }
          Directory = RecursivelyCreateDirectory(v3, 0);
          v6 = Directory;
          if ( Directory < 0 )
          {
            LODWORD(EndPtr) = Directory;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v105 = v45;
              LogAdapter::Logger::LogNumObjects<wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to ensure that logging directory exists: {}",
                (__int64)v105);
              *(_QWORD *)v107 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v62,
                3,
                (unsigned int)": {}",
                (__int64)v107);
            }
            v8 = 774;
            goto LABEL_9;
          }
          v105[0] = 0;
          v107[0] = 0;
          if ( (int)OnlineConfigGetProperty(L"CBSLogMaxInMB", v107) < 0 || (v63 = v107[0], v107[0] > 0x28) )
            v63 = 15;
          if ( (int)OnlineConfigGetProperty(L"CBSLogHardMaxInMB", v105) < 0 || (v64 = v105[0], v105[0] < v63) )
            v64 = 100;
          *(_QWORD *)v105 = 0;
          if ( (int)FileSize(v45, v105) >= 0
            && *(_QWORD *)v105 > (unsigned __int64)(v63 << 20)
            && (CbsRegQueryDWORDValue(
                  v65,
                  L"System\\CurrentControlSet\\Services\\TrustedInstaller",
                  v66,
                  L"Start",
                  (unsigned int *)&EndPtr) < 0
             || (_DWORD)EndPtr != 2
             || *(_QWORD *)v105 > (unsigned __int64)(v64 << 20)) )
          {
            GetSystemTime(&SystemTime);
            wHour = SystemTime.wHour;
            wDay = SystemTime.wDay;
            LODWORD(v102) = SystemTime.wMonth;
            v67 = SczAllocFormatted(
                    &lpNewFileName,
                    L"%ws\\CbsPersist_%02d%02d%02d%02d%02d%02d.log",
                    v3,
                    SystemTime.wYear);
            if ( v67 < 0 )
            {
              *(_QWORD *)v105 = v45;
              LogAdapter::TraceAtLevelHr<long,wchar_t *>(v69, (unsigned int)v67, v70, v105);
            }
            else
            {
              OnlineMaintenanceActionSet(v69, v68);
              *(_QWORD *)v105 = lpNewFileName;
              *(_QWORD *)v107 = v45;
              if ( !MoveFileExW(v45, lpNewFileName, 1u) )
              {
                v71 = GetLastError();
                LogAdapter::TraceAtLevelWin32<unsigned long,wchar_t *,wchar_t *>(
                  v72,
                  v71,
                  v73,
                  (unsigned int)v107,
                  (__int64)v105);
              }
            }
          }
          v2 = v106[0];
          if ( !v52 )
          {
            SetupLog = 0;
            if ( v46 )
              goto LABEL_204;
            goto LABEL_195;
          }
        }
        if ( v45 )
        {
          FileAttributesW = GetFileAttributesW(v45);
          if ( FileAttributesW == -1 )
          {
            GetLastError();
          }
          else if ( (FileAttributesW & 0x10) == 0 )
          {
            goto LABEL_163;
          }
        }
        LODWORD(EndPtr) = 1;
        Property = OnlineConfigGetProperty(L"CBSLogCompress", (unsigned int *)&EndPtr);
        v78 = (int)EndPtr;
        EndPtr = 0;
        if ( Property < 0 )
          v78 = 1;
        if ( v78 )
        {
          InitPointer = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                          &EndPtr,
                          v77);
          CreateCompressedFile((_DWORD)v45, v80, v81, v82, (_DWORD)v102, wDay, wHour, InitPointer);
        }
        else
        {
          v83 = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                  &EndPtr,
                  v77);
          CreateFileWithRetries((_DWORD)v45, v84, v85, v86, (_DWORD)v102, wDay, wHour, v83);
        }
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&EndPtr);
LABEL_163:
        if ( v46 )
        {
          if ( !((__int64 (__fastcall *)(_QWORD, __int64, const WCHAR *))vpfnWdsSetupLogInit)(0, 45056, v45) )
          {
            v6 = -2147418113;
            LODWORD(EndPtr) = -2147418113;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v105 = v45;
              *(_QWORD *)v107 = v16;
              LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                (_DWORD)LogAdapter::g_Logger,
                v87,
                v88,
                (unsigned int)"Failed to initialize logging with dll: {}, log directory: {}",
                (__int64)v107,
                (__int64)v105);
              *(_QWORD *)v106 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v89,
                3,
                (unsigned int)": {}",
                (__int64)v106);
            }
            v8 = 875;
            goto LABEL_9;
          }
LABEL_204:
          v6 = v2;
          goto LABEL_205;
        }
        if ( !(unsigned int)((__int64 (__fastcall *)(const WCHAR *, __int64))vpfnWdsGenericSetupLogInit)(v45, 0x8000) )
        {
          v6 = -2147467259;
          LODWORD(EndPtr) = -2147467259;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v105 = v45;
            *(_QWORD *)v107 = v16;
            LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              v90,
              v91,
              (unsigned int)"Failed to initialize logging with DLL: {}, log file: {}",
              (__int64)v107,
              (__int64)v105);
            *(_QWORD *)v106 = &EndPtr;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v92,
              3,
              (unsigned int)": {}",
              (__int64)v106);
          }
          v8 = 883;
          goto LABEL_9;
        }
        v93 = 1024;
        memset(String, 0, sizeof(String));
        if ( GetEnvironmentVariableW(L"COMPONENT_BASED_SERVICING_LOGLEVEL", String, 0x40u) - 1 <= 0x3E )
        {
          EndPtr = 0;
          v93 = wcstoul(String, &EndPtr, 16);
          if ( !v93 && *errno() == 34 )
            v93 = 1024;
        }
        SetupLog = vpfnWdsGetSetupLog();
        if ( !SetupLog )
        {
          LogAdapter::TraceAtLevelHr<long,>(0, 2147549183LL, "Failed to acquire log manager");
LABEL_178:
          v6 = 0;
          goto LABEL_205;
        }
        if ( v93 == 256 )
        {
          v95 = 0;
        }
        else if ( v93 == 512 )
        {
          v95 = 0x2000000;
        }
        else
        {
          v95 = 0x4000000;
          if ( v93 != 1024 )
            v95 = 150994944;
        }
        v115 = v95;
        v114 = L"Sev";
        v117 = 0;
        v121[1] = L"Sev";
        v121[0] = L"DT";
        v121[2] = L"Msg";
        v121[3] = L"Err";
        v121[4] = L"Uid";
        v121[5] = 0;
        v118 = v45;
        v119 = 0;
        v116 = 1;
        v120 = 0;
        v102 = (wchar_t **)v121;
        if ( !(**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *))SetupLog)(
                SetupLog,
                &qword_1800B0688,
                &v114,
                &qword_1800B0698) )
        {
          LogAdapter::TraceAtLevelHr<long,>(0, 2147549183LL, "Failed to configure logging settings");
          vpfnWdsSetupLogDestroy();
          goto LABEL_178;
        }
        ProcAddress = GetProcAddress(vhWdsDll, "WdsLogRegisterProvider");
        if ( ProcAddress
          && ((unsigned int (__fastcall *)(__int128 *, __int64 (__fastcall *)()))ProcAddress)(
               &xmmword_1800B0678,
               CreateCbsLogMonitorProvider) == 1 )
        {
          v102 = (wchar_t **)v121;
          if ( (**(unsigned int (__fastcall ***)(struct ILogManager *, __int64 *, const wchar_t **, __int64 *))SetupLog)(
                 SetupLog,
                 &qword_1800B0688,
                 &v114,
                 &qword_1800B0698) )
          {
            goto LABEL_195;
          }
          v98 = "Unable to add CbsLogMonitor provider";
        }
        else
        {
          v98 = "Unable to register CbsLogMonitor provider";
        }
        LogAdapter::TraceAtLevel<>(v97, v98);
LABEL_195:
        if ( v3 )
        {
          v99 = DeleteOldestLogFiles(v3);
          v6 = v99;
          if ( v99 < 0 )
          {
            LODWORD(EndPtr) = v99;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to delete extra backup log files.");
              *(_QWORD *)v105 = &EndPtr;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v100,
                3,
                (unsigned int)": {}",
                (__int64)v105);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3CC,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
              (const char *)v6,
              (int)v102);
            if ( SetupLog )
              vpfnWdsSetupLogDestroy();
            goto LABEL_201;
          }
        }
        if ( SetupLog )
          vpfnWdsSetupLogDestroy();
        goto LABEL_204;
      }
    }
    else
    {
      v46 = 0;
    }
    memset(Buffer, 0, sizeof(Buffer));
    if ( GetEnvironmentVariableW(L"COMPONENT_BASED_SERVICING_LOGFILE", Buffer, 0x200u) - 1 <= 0x1FE )
    {
      v49 = SczAllocFromSz(&lpExistingFileName, Buffer);
      v6 = v49;
      if ( v49 < 0 )
      {
        v10 = (unsigned int)v49;
        v8 = 729;
        goto LABEL_10;
      }
      v45 = lpExistingFileName;
      v5 = 1;
      v106[0] = 1;
    }
    goto LABEL_105;
  }
  LastError = GetLastError();
  if ( LastError != 126 )
  {
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v105 = v16;
      LogAdapter::Logger::LogNumObjects<wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to load WDSCORE DLL: {}",
        (__int64)v105);
      if ( LastError > 0 )
        v27 = (unsigned __int16)LastError | 0x80070000;
      else
        v27 = LastError;
      LODWORD(EndPtr) = v27;
      *(_QWORD *)v107 = &EndPtr;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v26,
        3,
        (unsigned int)": {0}",
        (__int64)v107);
    }
    if ( LastError )
    {
      v28 = 674;
LABEL_38:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v28,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
             (const char *)(unsigned int)LastError,
             (unsigned int)v102);
      goto LABEL_201;
    }
    goto LABEL_95;
  }
  EndPtr = v16;
  LogAdapter::TraceAtLevelLastError<wchar_t *>(v24, v23, &EndPtr);
  v6 = 1;
LABEL_205:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v110);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v111);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  return v6;
}

```

## disassembly

```asm
0x180047e20  push    rbp
0x180047e22  push    rbx
0x180047e23  push    rsi
0x180047e24  push    rdi
0x180047e25  push    r12
0x180047e27  push    r13
0x180047e29  push    r14
0x180047e2b  push    r15
0x180047e2d  lea     rbp, [rsp-4A8h]
0x180047e35  sub     rsp, 5A8h
0x180047e3c  mov     rax, cs:__security_cookie
0x180047e43  xor     rax, rsp
0x180047e46  mov     [rbp+4E0h+var_50], rax
0x180047e4d  xor     r12d, r12d
0x180047e50  xorps   xmm0, xmm0
0x180047e53  mov     ebx, r12d
0x180047e56  mov     [rsp+5E0h+lpExistingFileName], r12
0x180047e5b  mov     rdi, rcx
0x180047e5e  mov     [rbp+4E0h+lpNewFileName], r12
0x180047e62  mov     [rsp+5E0h+lpLibFileName], r12
0x180047e67  mov     r15d, r12d
0x180047e6a  lea     r14d, [r12+3]
0x180047e6f  mov     [rbp+4E0h+var_560], r12
0x180047e73  lea     r13d, [r12+1]
0x180047e78  mov     dword ptr [rbp+4E0h+EndPtr], r14d
0x180047e7c  mov     eax, r13d
0x180047e7f  mov     [rsp+5E0h+var_588], r12d
0x180047e84  movups  xmmword ptr [rbp+4E0h+SystemTime.wYear], xmm0
0x180047e88  mov     [rsp+5E0h+var_568], rbx
0x180047e8d  lock xadd cs:?vcWdsLoadOperations@@3JA, eax; long vcWdsLoadOperations
0x180047e95  add     eax, r13d
0x180047e98  cmp     eax, r13d
0x180047e9b  jle     short loc_180047EF2
0x180047e9d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047ea4  mov     esi, 800704DFh
0x180047ea9  mov     dword ptr [rbp+4E0h+EndPtr], esi
0x180047eac  test    rcx, rcx
0x180047eaf  jz      short loc_180047EEB
0x180047eb1  lea     r9, aWdsLoggerIsAlr; "Wds logger is already initialized"
0x180047eb8  mov     r8d, r14d
0x180047ebb  xor     edx, edx
0x180047ebd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180047ec2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047ec9  lea     rax, [rbp+4E0h+EndPtr]
0x180047ecd  mov     qword ptr [rsp+5E0h+var_590], rax
0x180047ed2  lea     r9, asc_1800AFAD8; ": {}"
0x180047ed9  lea     rax, [rsp+5E0h+var_590]
0x180047ede  mov     r8d, r14d
0x180047ee1  mov     [rsp+5E0h+var_5C0], rax
0x180047ee6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047eeb  mov     edx, 284h
0x180047ef0  jmp     short loc_180047F4A
0x180047ef2  test    rdi, rdi
0x180047ef5  jnz     short loc_180047F65
0x180047ef7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047efe  mov     esi, 80070057h
0x180047f03  mov     dword ptr [rbp+4E0h+EndPtr], esi
0x180047f06  test    rcx, rcx
0x180047f09  jz      short loc_180047F45
0x180047f0b  lea     r9, aNoCoreDllPathS; "No core dll path specified"
0x180047f12  mov     r8d, r14d
0x180047f15  xor     edx, edx
0x180047f17  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180047f1c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047f23  lea     rax, [rbp+4E0h+EndPtr]
0x180047f27  mov     qword ptr [rsp+5E0h+var_590], rax
0x180047f2c  lea     r9, asc_1800AFAD8; ": {}"
0x180047f33  lea     rax, [rsp+5E0h+var_590]
0x180047f38  mov     r8d, r14d
0x180047f3b  mov     [rsp+5E0h+var_5C0], rax; int
0x180047f40  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047f45  mov     edx, 287h; void *
0x180047f4a  mov     r9d, esi; char *
0x180047f4d  mov     rcx, [rbp+4E8h]; this
0x180047f54  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180047f5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047f60  jmp     loc_180048FA2
0x180047f65  lea     rcx, [rbp+4E0h+var_560]
0x180047f69  call    PathGetWindowsDirectory
0x180047f6e  mov     esi, eax
0x180047f70  test    eax, eax
0x180047f72  jns     short loc_180047FC4
0x180047f74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047f7b  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x180047f7e  test    rcx, rcx
0x180047f81  jz      short loc_180047FBD
0x180047f83  lea     r9, aFailedToGetWin; "Failed to get windows directory for WDS"...
0x180047f8a  mov     r8d, r14d
0x180047f8d  xor     edx, edx
0x180047f8f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180047f94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047f9b  lea     rax, [rbp+4E0h+EndPtr]
0x180047f9f  mov     qword ptr [rsp+5E0h+var_590], rax
0x180047fa4  lea     r9, asc_1800AFAD8; ": {}"
0x180047fab  lea     rax, [rsp+5E0h+var_590]
0x180047fb0  mov     r8d, r14d
0x180047fb3  mov     [rsp+5E0h+var_5C0], rax
0x180047fb8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047fbd  mov     edx, 28Ah
0x180047fc2  jmp     short loc_180047F4A
0x180047fc4  mov     rdx, rdi
0x180047fc7  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180047fcc  call    SczAllocFromSz
0x180047fd1  mov     esi, eax
0x180047fd3  test    eax, eax
0x180047fd5  jns     short loc_180047FE4
0x180047fd7  mov     r9d, eax
0x180047fda  mov     edx, 28Ch
0x180047fdf  jmp     loc_180047F4D
0x180047fe4  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180047fe9  call    SczEnsureBackslashTerminated
0x180047fee  mov     esi, eax
0x180047ff0  test    eax, eax
0x180047ff2  jns     short loc_180048001
0x180047ff4  mov     r9d, eax
0x180047ff7  mov     edx, 28Dh
0x180047ffc  jmp     loc_180047F4D
0x180048001  lea     rdx, aWdscoreDll; "wdscore.dll"
0x180048008  lea     rcx, [rsp+5E0h+lpLibFileName]
0x18004800d  call    SczAllocConcatSz
0x180048012  mov     esi, eax
0x180048014  test    eax, eax
0x180048016  jns     short loc_180048025
0x180048018  mov     r9d, eax
0x18004801b  mov     edx, 28Eh
0x180048020  jmp     loc_180047F4D
0x180048025  mov     rdi, [rsp+5E0h+lpLibFileName]
0x18004802a  mov     rcx, rdi; lpLibFileName
0x18004802d  call    cs:__imp_LoadLibraryW
0x180048034  nop     dword ptr [rax+rax+00h]
0x180048039  mov     rdx, rax
0x18004803c  lea     rcx, ?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x180048043  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x180048048  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; hModule
0x18004804f  test    rcx, rcx
0x180048052  jnz     loc_1800481AE
0x180048058  mov     rdx, [rbp+4E0h+var_560]
0x18004805c  lea     rcx, [rsp+5E0h+lpLibFileName]
0x180048061  call    SczAllocFromSz
0x180048066  mov     esi, eax
0x180048068  test    eax, eax
0x18004806a  jns     short loc_180048079
0x18004806c  mov     r9d, eax
0x18004806f  mov     edx, 293h
0x180048074  jmp     loc_180047F4D
0x180048079  lea     rcx, [rsp+5E0h+lpLibFileName]
0x18004807e  call    SczEnsureBackslashTerminated
0x180048083  mov     esi, eax
0x180048085  test    eax, eax
0x180048087  jns     short loc_180048096
0x180048089  mov     r9d, eax
0x18004808c  mov     edx, 294h
0x180048091  jmp     loc_180047F4D
0x180048096  lea     r8, aWdscoreDll; "wdscore.dll"
0x18004809d  lea     rdx, aSystem32; "system32\\"
0x1800480a4  lea     rcx, [rsp+5E0h+lpLibFileName]
0x1800480a9  call    SczAllocConcat2Sz
0x1800480ae  mov     esi, eax
0x1800480b0  test    eax, eax
0x1800480b2  jns     short loc_1800480C1
0x1800480b4  mov     r9d, eax
0x1800480b7  mov     edx, 295h
0x1800480bc  jmp     loc_180047F4D
0x1800480c1  mov     rdi, [rsp+5E0h+lpLibFileName]
0x1800480c6  mov     rcx, rdi; lpLibFileName
0x1800480c9  call    cs:__imp_LoadLibraryW
0x1800480d0  nop     dword ptr [rax+rax+00h]
0x1800480d5  mov     rdx, rax
0x1800480d8  lea     rcx, ?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x1800480df  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x1800480e4  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x1800480eb  test    rcx, rcx
0x1800480ee  jnz     loc_1800481AE
0x1800480f4  call    cs:__imp_GetLastError
0x1800480fb  nop     dword ptr [rax+rax+00h]
0x180048100  mov     ebx, eax
0x180048102  cmp     eax, 7Eh ; '~'
0x180048105  jnz     short loc_18004811C
0x180048107  lea     r8, [rbp+4E0h+EndPtr]
0x18004810b  mov     [rbp+4E0h+EndPtr], rdi
0x18004810f  call    ??$TraceAtLevelLastError@PEA_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEA_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t *>(LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x180048114  mov     esi, r13d
0x180048117  jmp     loc_180048FF5
0x18004811c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048123  test    rcx, rcx
0x180048126  jz      short loc_180048184
0x180048128  lea     rax, [rsp+5E0h+var_590]
0x18004812d  mov     qword ptr [rsp+5E0h+var_590], rdi
0x180048132  lea     r9, aFailedToLoadWd; "Failed to load WDSCORE DLL: {}"
0x180048139  mov     [rsp+5E0h+var_5C0], rax
0x18004813e  mov     r8d, r14d
0x180048141  xor     edx, edx
0x180048143  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x180048148  test    ebx, ebx
0x18004814a  jg      short loc_180048150
0x18004814c  mov     eax, ebx
0x18004814e  jmp     short loc_180048158
0x180048150  movzx   eax, bx
0x180048153  or      eax, 80070000h
0x180048158  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004815f  lea     r9, a0; ": {0}"
0x180048166  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x180048169  mov     r8d, r14d
0x18004816c  lea     rax, [rbp+4E0h+EndPtr]
0x180048170  mov     qword ptr [rsp+5E0h+var_580], rax
0x180048175  lea     rax, [rsp+5E0h+var_580]
0x18004817a  mov     [rsp+5E0h+var_5C0], rax; unsigned int
0x18004817f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180048184  test    ebx, ebx
0x180048186  jz      loc_1800485FC
0x18004818c  mov     edx, 2A2h; void *
0x180048191  mov     rcx, [rbp+4E8h]; this
0x180048198  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18004819f  mov     r9d, ebx; char *
0x1800481a2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800481a7  mov     esi, eax
0x1800481a9  jmp     loc_180048FA2
0x1800481ae  lea     rdx, aWdssetuplogini; "WdsSetupLogInit"
0x1800481b5  call    cs:__imp_GetProcAddress
0x1800481bc  nop     dword ptr [rax+rax+00h]
0x1800481c1  mov     cs:?vpfnWdsSetupLogInit@@3P6APEAVILogManager@@PEAUHINSTANCE__@@KPEB_W@ZEA, rax; ILogManager * (*vpfnWdsSetupLogInit)(HINSTANCE__ *,ulong,wchar_t const *)
0x1800481c8  test    rax, rax
0x1800481cb  jnz     short loc_180048246
0x1800481cd  call    cs:__imp_GetLastError
0x1800481d4  nop     dword ptr [rax+rax+00h]
0x1800481d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800481e0  mov     ebx, eax
0x1800481e2  test    rcx, rcx
0x1800481e5  jz      short loc_180048234
0x1800481e7  lea     r9, aFailedToGetPro_1; "Failed to get proc address for WdsSetup"...
0x1800481ee  mov     r8d, r14d
0x1800481f1  xor     edx, edx
0x1800481f3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800481f8  test    ebx, ebx
0x1800481fa  jg      short loc_180048200
0x1800481fc  mov     eax, ebx
0x1800481fe  jmp     short loc_180048208
0x180048200  movzx   eax, bx
0x180048203  or      eax, 80070000h
0x180048208  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004820f  lea     r9, a0; ": {0}"
0x180048216  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x180048219  mov     r8d, r14d
0x18004821c  lea     rax, [rbp+4E0h+EndPtr]
0x180048220  mov     qword ptr [rsp+5E0h+var_590], rax
0x180048225  lea     rax, [rsp+5E0h+var_590]
0x18004822a  mov     [rsp+5E0h+var_5C0], rax
0x18004822f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180048234  test    ebx, ebx
0x180048236  jz      loc_1800485FC
0x18004823c  mov     edx, 2A7h
0x180048241  jmp     loc_180048191
0x180048246  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; hModule
0x18004824d  lea     rdx, aWdsgenericsetu; "WdsGenericSetupLogInit"
0x180048254  call    cs:__imp_GetProcAddress
0x18004825b  nop     dword ptr [rax+rax+00h]
0x180048260  mov     cs:?vpfnWdsGenericSetupLogInit@@3P6AHPEB_WK@ZEA, rax; int (*vpfnWdsGenericSetupLogInit)(wchar_t const *,ulong)
0x180048267  test    rax, rax
0x18004826a  jnz     short loc_1800482E5
0x18004826c  call    cs:__imp_GetLastError
0x180048273  nop     dword ptr [rax+rax+00h]
0x180048278  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004827f  mov     ebx, eax
0x180048281  test    rcx, rcx
0x180048284  jz      short loc_1800482D3
0x180048286  lea     r9, aFailedToGetPro_5; "Failed to get proc address for WdsGener"...
0x18004828d  mov     r8d, r14d
0x180048290  xor     edx, edx
0x180048292  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180048297  test    ebx, ebx
0x180048299  jg      short loc_18004829F
0x18004829b  mov     eax, ebx
0x18004829d  jmp     short loc_1800482A7
0x18004829f  movzx   eax, bx
0x1800482a2  or      eax, 80070000h
0x1800482a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800482ae  lea     r9, a0; ": {0}"
0x1800482b5  mov     dword ptr [rbp+4E0h+EndPtr], eax
0x1800482b8  mov     r8d, r14d
0x1800482bb  lea     rax, [rbp+4E0h+EndPtr]
0x1800482bf  mov     qword ptr [rsp+5E0h+var_590], rax
0x1800482c4  lea     rax, [rsp+5E0h+var_590]
0x1800482c9  mov     [rsp+5E0h+var_5C0], rax
0x1800482ce  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800482d3  test    ebx, ebx
0x1800482d5  jz      loc_1800485FC
0x1800482db  mov     edx, 2AAh
0x1800482e0  jmp     loc_180048191
0x1800482e5  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; hModule
0x1800482ec  lea     rdx, aWdsgetsetuplog; "WdsGetSetupLog"
0x1800482f3  call    cs:__imp_GetProcAddress
0x1800482fa  nop     dword ptr [rax+rax+00h]
0x1800482ff  mov     cs:?vpfnWdsGetSetupLog@@3P6APEAVILogManager@@XZEA, rax; ILogManager * (*vpfnWdsGetSetupLog)(void)
0x180048306  test    rax, rax
0x180048309  jnz     short loc_180048384
0x18004830b  call    cs:__imp_GetLastError
0x180048312  nop     dword ptr [rax+rax+00h]
0x180048317  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004831e  mov     ebx, eax
0x180048320  test    rcx, rcx
  ... truncated ...
```

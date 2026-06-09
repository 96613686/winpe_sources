# OnepackageInstallFromSandbox(AutoThreadPriority::PriorityType,bool,wchar_t const *,wchar_t const *,ulong,int *)

- ea: `0x18020dc4c`
- end: `0x18020ecff`
- name: `?OnepackageInstallFromSandbox@@YAJW4PriorityType@AutoThreadPriority@@_NPEB_W2KPEAH@Z`
- size: `4275`
- prototype: `__int64 __fastcall(unsigned int, char, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e7aa4`

## callees

- `0x180010cc0`
- `0x180011a14`
- `0x180013250`
- `0x180023ca8`
- `0x1800261e0`
- `0x18004bca8`
- `0x180059a00`
- `0x18005a548`
- `0x18005dd58`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ae508`
- `0x1800eb920`
- `0x1800ef360`
- `0x18020babc`
- `0x18020c5f4`
- `0x18020dc4c`
- `0x18020ed08`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18020e159`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18020e159`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020ebcd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020ece1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020ebcd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18020ece1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18020e125`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18020e125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020e250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020ea38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020e250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020ea38`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18020e0c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18020e0c7`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x18020def7`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x18020def7`

## string_xrefs

- `0x18020debc`: `updateagent.dll`
- `0x18020e9df`: `Failed to install onepackage from sandbox.`
- `0x18020e77c`: `Failed to convert thread priority to update session priority.`
- `0x18020e14f`: `CreateOfflineDeploymentSession`
- `0x18020e026`: `Failed to remove session object from RoT`
- `0x18020e32c`: `Failed to remove session object from RoT`
- `0x18020e443`: `Failed to remove session object from RoT`
- `0x18020e59b`: `Failed to remove session object from RoT`
- `0x18020eae5`: `Failed to remove session object from RoT`
- `0x18020ebfd`: `Failed to remove session object from RoT`
- `0x18020e7e8`: `UpdatePriority`
- `0x18020e271`: `Failed to copy aggregatedmetadata file to sandbox`
- `0x18020e107`: `Updateagent dll not signed. Continuing because unittest mode is set.`
- `0x18020e527`: `Updateagent dll not signed.`
- `0x18020ea52`: `Failed to load update agent DLL`
- `0x18020dd05`: `No sandbox path specified`

## pseudocode

```c
__int64 __fastcall OnepackageInstallFromSandbox(unsigned int a1, char a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  __int64 v9; // r10
  unsigned int v10; // ebx
  int v11; // edx
  __int64 v12; // rdx
  int v13; // edx
  unsigned __int64 v14; // r9
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  HRESULT RunningObjectTable; // eax
  __int64 v20; // rcx
  int v21; // edx
  int v22; // eax
  __int64 v23; // rdx
  int v24; // edx
  unsigned int v25; // eax
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // rdi
  __int64 v28; // r14
  int v29; // eax
  int v30; // eax
  HMODULE Library; // rax
  HMODULE v32; // r14
  FARPROC ProcAddress; // rax
  int v34; // eax
  int v35; // edx
  __int64 v36; // rdx
  __int64 (*Revoke)(void); // rax
  signed int LastError; // ebx
  int v39; // edx
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  __int64 v43; // rdx
  int v44; // edx
  unsigned int v45; // eax
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v48)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v50; // eax
  int v51; // eax
  int v52; // edx
  __int64 v53; // rdx
  int updated; // eax
  int v55; // edx
  int v56; // eax
  int v57; // edx
  int v58; // eax
  int v59; // edx
  int v60; // eax
  int v61; // edx
  int v62; // edx
  int v63; // eax
  int v64; // edx
  signed int v65; // ebx
  int v66; // edx
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // [rsp+20h] [rbp-E0h]
  HMODULE *v71; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v74; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v76[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v77[2]; // [rsp+78h] [rbp-88h] BYREF
  char v78; // [rsp+88h] [rbp-78h]
  __int128 v79; // [rsp+90h] [rbp-70h]
  __int128 v80; // [rsp+A0h] [rbp-60h]
  __int128 v81; // [rsp+B0h] [rbp-50h]
  __int64 v82; // [rsp+C0h] [rbp-40h]
  LPRUNNINGOBJECTTABLE pprot; // [rsp+C8h] [rbp-38h] BYREF
  __int64 (__fastcall ***v84)(_QWORD, GUID *, __int64); // [rsp+D0h] [rbp-30h]
  __int64 v85; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v86; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v87; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v88; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v89[2]; // [rsp+F8h] [rbp-8h] BYREF
  HMODULE hModule[2]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v91[4]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v92[24]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v93; // [rsp+138h] [rbp+38h]
  __int64 v94; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v89[0] = a1;
  *(_QWORD *)v76 = a6;
  v91[0] = 0;
  hModule[0] = 0;
  v74 = 0;
  lpLibFileName = 0;
  v79 = 0;
  v82 = 0;
  v80 = 0;
  v84 = 0;
  v81 = 0;
  v88 = 0;
  v86 = 0;
  v85 = 0;
  v87 = 0;
  pprot = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v92);
  lpExistingFileName = 0;
  lpNewFileName = 0;
  if ( !a3 )
  {
    v10 = -2147024809;
    LODWORD(hModule[0]) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No sandbox path specified");
      *(_QWORD *)v89 = hModule;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v89);
    }
    v12 = 70;
LABEL_9:
    v14 = v10;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
      (const char *)v14,
      v70);
    goto LABEL_11;
  }
  if ( !v9 )
  {
    v10 = -2147467261;
    LODWORD(hModule[0]) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No require reboot result specified");
      *(_QWORD *)v89 = hModule;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)v89);
    }
    v12 = 71;
    goto LABEL_9;
  }
  v16 = SczAllocFromSzAndEnsureBackslash(&v74, a3);
  v10 = v16;
  if ( v16 < 0 )
  {
    v14 = (unsigned int)v16;
    v12 = 73;
    goto LABEL_10;
  }
  v17 = SczAllocConcatSz(&v74, L"metadata\\");
  v10 = v17;
  if ( v17 < 0 )
  {
    v14 = (unsigned int)v17;
    v12 = 74;
    goto LABEL_10;
  }
  v18 = SczAllocFormatted(&lpLibFileName, L"%ws%ws", v74, L"updateagent.dll");
  v10 = v18;
  if ( v18 < 0 )
  {
    v14 = (unsigned int)v18;
    v12 = 76;
    goto LABEL_10;
  }
  if ( pprot )
    goto LABEL_203;
  RunningObjectTable = GetRunningObjectTable(0, &pprot);
  v10 = RunningObjectTable;
  if ( RunningObjectTable < 0 )
  {
    LODWORD(hModule[0]) = RunningObjectTable;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get the running object table.");
      *(_QWORD *)v89 = hModule;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)v89);
    }
    v12 = 78;
    goto LABEL_9;
  }
  v78 = 1;
  v77[0] = &pprot;
  v77[1] = &a5;
  v22 = CbsEnumFiles(v20, a3, L"*.aggregatedmetadata.cab", v92);
  v10 = v22;
  if ( v22 < 0 )
  {
    LODWORD(hModule[0]) = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting the aggregatedmetadata files.");
      *(_QWORD *)v89 = hModule;
      LOBYTE(v24) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v24,
        3,
        (unsigned int)": {}",
        (__int64)v89);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
      (const char *)v10,
      v70);
    if ( pprot && a5 )
    {
      v25 = ((__int64 (*)(void))pprot->lpVtbl->Revoke)();
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v25, "Failed to remove session object from RoT");
    }
LABEL_11:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v92);
    if ( pprot )
    {
      ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
      pprot = 0;
    }
    if ( v87 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      v87 = 0;
    }
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      v85 = 0;
    }
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    if ( v88 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      v88 = 0;
    }
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
    if ( !v84 )
      goto LABEL_124;
    goto LABEL_123;
  }
  v26 = v93;
  v27 = 0;
  if ( v93 )
  {
    v28 = v94;
    while ( 1 )
    {
      v29 = SczAllocFromSzAndEnsureBackslash(&lpExistingFileName, a3);
      v10 = v29;
      if ( v29 < 0 )
      {
        v43 = 96;
        goto LABEL_90;
      }
      if ( v27 >= v26 )
        __fastfail(8u);
      v29 = SczAllocConcatSz(&lpExistingFileName, *(_QWORD *)(v28 + 8 * v27));
      v10 = v29;
      if ( v29 < 0 )
      {
        v43 = 97;
        goto LABEL_90;
      }
      if ( v27 >= v26 )
        __fastfail(8u);
      v29 = SczAllocFormatted(&lpNewFileName, L"%ws%ws", v74, *(_QWORD *)(v28 + 8 * v27));
      v10 = v29;
      if ( v29 < 0 )
        break;
      if ( !CopyFileW(lpExistingFileName, lpNewFileName, 0) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to copy aggregatedmetadata file to sandbox");
          if ( LastError > 0 )
            v40 = (unsigned __int16)LastError | 0x80070000;
          else
            v40 = LastError;
          LODWORD(hModule[0]) = v40;
          LOBYTE(v39) = 1;
          *(_QWORD *)v89 = hModule;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v39,
            3,
            (unsigned int)": {0}",
            (__int64)v89);
        }
        if ( !LastError )
        {
          if ( pprot && a5 )
          {
            v42 = ((__int64 (*)(void))pprot->lpVtbl->Revoke)();
            LogAdapter::TraceAtLevelIfFailed<long,>(3, v42, "Failed to remove session object from RoT");
          }
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v92);
          if ( pprot )
          {
            ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
            pprot = 0;
          }
          if ( v87 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
            v87 = 0;
          }
          if ( v85 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
            v85 = 0;
          }
          if ( v86 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
            v86 = 0;
          }
          if ( v88 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
            v88 = 0;
          }
          if ( v84 )
          {
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v84)[2])(v84);
            v84 = 0;
          }
          v10 = 0;
          goto LABEL_124;
        }
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x65,
                (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
                (const char *)(unsigned int)LastError,
                v70);
        if ( pprot && a5 )
        {
          v41 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Revoke)(pprot);
LABEL_93:
          LogAdapter::TraceAtLevelIfFailed<long,>(3, v41, "Failed to remove session object from RoT");
          goto LABEL_94;
        }
        goto LABEL_94;
      }
      if ( ++v27 >= v26 )
        goto LABEL_51;
    }
    v43 = 98;
LABEL_90:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
      (const char *)(unsigned int)v29,
      v70);
    if ( pprot && a5 )
    {
      v41 = ((__int64 (*)(void))pprot->lpVtbl->Revoke)();
      goto LABEL_93;
    }
LABEL_94:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v92);
    if ( pprot )
    {
      ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
      pprot = 0;
    }
    if ( v87 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      v87 = 0;
    }
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      v85 = 0;
    }
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    if ( v88 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      v88 = 0;
    }
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
    if ( !v84 )
      goto LABEL_124;
LABEL_123:
    ((void (__fastcall *)(_QWORD))(*v84)[2])(v15);
    v84 = 0;
LABEL_124:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
    return v10;
  }
LABEL_51:
  LOBYTE(v23) = a4 == 0;
  v30 = CbsVerifyFileSignature(lpLibFileName, v23);
  v10 = v30;
  if ( a2 )
  {
    LogAdapter::TraceAtLevelIfFailed<long,>(
      3,
      (unsigned int)v30,
      "Updateagent dll not signed. Continuing because unittest mode is set.");
  }
  else if ( v30 < 0 )
  {
    LODWORD(hModule[0]) = v30;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Updateagent dll not signed.");
      *(_QWORD *)v89 = hModule;
      LOBYTE(v44) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v44,
        3,
        (unsigned int)": {}",
        (__int64)v89);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
      (const char *)v10,
      v70);
    if ( pprot && a5 )
    {
      v45 = ((__int64 (*)(void))pprot->lpVtbl->Revoke)();
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v45, "Failed to remove session object from RoT");
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v92);
    if ( pprot )
    {
      ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
      pprot = 0;
    }
    if ( v87 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      v87 = 0;
    }
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      v85 = 0;
    }
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    if ( v88 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      v88 = 0;
    }
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
    if ( !v84 )
      goto LABEL_124;
    goto LABEL_123;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 8u);
  Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHModuleTraits,Windows::Rtl::AutoHModule>::TakeOwnership(
    hModule,
    Library);
  v32 = hModule[0];
  if ( (unsigned __int64)hModule[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v65 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load update agent DLL");
      if ( v65 > 0 )
        v67 = (unsigned __int16)v65 | 0x80070000;
      else
        v67 = v65;
      v89[0] = v67;
      LOBYTE(v66) = 1;
      *(_QWORD *)v76 = v89;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v66,
        3,
        (unsigned int)": {0}",
        (__int64)v76);
    }
    if ( v65 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
              (const char *)(unsigned int)v65,
              v70);
      if ( !pprot || !a5 )
        goto LABEL_171;
      Revoke = (__int64 (*)(void))pprot->lpVtbl->Revoke;
LABEL_170:
      v68 = Revoke();
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v68, "Failed to remove session object from RoT");
      goto LABEL_171;
    }
    if ( pprot && a5 )
    {
      v69 = ((__int64 (*)(void))pprot->lpVtbl->Revoke)();
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v69, "Failed to remove session object from RoT");
    }
    goto LABEL_188;
  }
  ProcAddress = GetProcAddress(hModule[0], "CreateOfflineDeploymentSession");
  *(_QWORD *)&v79 = L"{\"ModuleID\":\"LocalServicing\"}";
  if ( v84 )
    goto LABEL_203;
  v71 = hModule;
  *(GUID *)hModule = GUID_NULL;
  v34 = ((__int64 (__fastcall *)(__int64, __int64, __int64))ProcAddress)(1, a3, a4);
  v10 = v34;
  if ( v34 < 0 )
  {
    LODWORD(hModule[0]) = v34;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Creation of deployment session failed.");
      *(_QWORD *)v89 = hModule;
      LOBYTE(v35) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v35,
        3,
        (unsigned int)": {}",
        (__int64)v89);
    }
    v36 = 140;
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
      (const char *)v10,
      (int)v71);
    if ( !pprot || !a5 )
      goto LABEL_171;
    Revoke = (__int64 (*)(void))pprot->lpVtbl->Revoke;
    goto LABEL_170;
  }
  v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v84;
  v48 = **v84;
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v88);
  v50 = v48(v47, &GUID_57816c47_d685_423a_89c6_feefbd90ed47, InitPointer);
  if ( v50 >= 0 )
  {
    LODWORD(hModule[0]) = 0;
    updated = ThreadPriorityToUpdateSessionPriority(v89[0], hModule);
    v10 = updated;
    if ( updated < 0 )
    {
      v89[0] = updated;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to convert thread priority to update session priority.");
        hModule[0] = (HMODULE)v89;
        LOBYTE(v55) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v55,
          3,
          (unsigned int)": {}",
          (__int64)hModule);
      }
      v53 = 154;
      goto LABEL_137;
    }
    v56 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)v88 + 168LL))(
            v88,
            0,
            L"UpdatePriority",
            SLODWORD(hModule[0]));
    v10 = v56;
    if ( v56 < 0 )
    {
      v89[0] = v56;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set priority on deployment session.");
        hModule[0] = (HMODULE)v89;
        LOBYTE(v57) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v57,
          3,
          (unsigned int)": {}",
          (__int64)hModule);
      }
      v53 = 158;
      goto LABEL_137;
    }
  }
  else
  {
    LogAdapter::TraceAtLevelHr<long,>(
      1,
      (unsigned int)v50,
      "Unable to query for IDeploymentSession8. Continuing with default priorities.");
  }
  if ( v86 )
    goto LABEL_203;
  v51 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*v84)[4])(v84, &v86);
  v10 = v51;
  if ( v51 < 0 )
  {
    v89[0] = v51;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting the download request.");
      hModule[0] = (HMODULE)v89;
      LOBYTE(v52) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v52,
        3,
        (unsigned int)": {}",
        (__int64)hModule);
    }
    v53 = 161;
LABEL_137:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v53,
      (unsigned int)"onecore\\base\\cbs\\onepackage\\lib\\cbsonepackage.cpp",
      (const char *)v10,
      (int)v71);
    v78 = 0;
    OnepackageInstallFromSandbox_::_2_::_lambda_1_::operator()(v77);
LABEL_171:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v92);
    if ( pprot )
    {
      ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
      pprot = 0;
    }
    if ( v87 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      v87 = 0;
    }
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      v85 = 0;
    }
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    if ( v88 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      v88 = 0;
    }
    if ( v84 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v84)[2])(v84);
      v84 = 0;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
    if ( (unsigned __int64)v32 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      FreeLibrary(v32);
    return v10;
  }
  if ( v85 )
    goto LABEL_203;
  v58 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v86 + 40LL))(v86, &v85);
  v10 = v58;
  if ( v58 < 0 )
  {
    v89[0] = v58;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting the file requests.");
      hModule[0] = (HMODULE)v89;
      LOBYTE(v59) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v59,
        3,
        (unsigned int)": {}",
        (__int64)hModule);
    }
    v53 = 165;
    goto LABEL_137;
  }
  v60 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v85 + 24LL))(v85, v91);
  v10 = v60;
  if ( v60 < 0 )
  {
    v89[0] = v60;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting the file request count.");
      *(_QWORD *)v76 = v89;
      LOBYTE(v61) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v61,
        3,
        (unsigned int)": {}",
        (__int64)v76);
    }
    v53 = 166;
    goto LABEL_137;
  }
  if ( v91[0] )
  {
    v10 = -2147024809;
    LODWORD(hModule[0]) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "The cab does not have all the packages.");
      *(_QWORD *)v76 = hModule;
      LOBYTE(v62) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v62,
        3,
        (unsigned int)": {}",
        (__int64)v76);
    }
    v36 = 168;
    goto LABEL_59;
  }
  if ( v87 )
  {
LABEL_203:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18020ECFELL);
  }
  v63 = (*v84)[5](v84, (GUID *)&v87, *(_QWORD *)v76);
  v10 = v63;
  if ( v63 < 0 )
  {
    v89[0] = v63;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to install onepackage from sandbox.");
      *(_QWORD *)v76 = v89;
      LOBYTE(v64) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v64,
        3,
        (unsigned int)": {}",
        (__int64)v76);
    }
    v53 = 173;
    goto LABEL_137;
  }
  v78 = 0;
  OnepackageInstallFromSandbox_::_2_::_lambda_1_::operator()(v77);
LABEL_188:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v92);
  if ( pprot )
  {
    ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
    pprot = 0;
  }
  if ( v87 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
    v87 = 0;
  }
  if ( v85 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    v85 = 0;
  }
  if ( v86 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    v86 = 0;
  }
  if ( v88 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    v88 = 0;
  }
  if ( v84 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v84)[2])(v84);
    v84 = 0;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
  if ( (unsigned __int64)v32 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    FreeLibrary(v32);
  return 0;
}

```

## disassembly

```asm
0x18020dc4c  mov     [rsp-8+arg_0], rbx
0x18020dc51  push    rbp
0x18020dc52  push    rsi
0x18020dc53  push    rdi
0x18020dc54  push    r12
0x18020dc56  push    r13
0x18020dc58  push    r14
0x18020dc5a  push    r15
0x18020dc5c  lea     rbp, [rsp-70h]
0x18020dc61  sub     rsp, 170h
0x18020dc68  mov     rax, cs:__security_cookie
0x18020dc6f  xor     rax, rsp
0x18020dc72  mov     [rbp+0A0h+var_40], rax
0x18020dc76  mov     r10, [rbp+0A0h+arg_28]
0x18020dc7d  xor     r14d, r14d
0x18020dc80  xorps   xmm0, xmm0
0x18020dc83  mov     [rbp+0A0h+var_A8], ecx
0x18020dc86  xor     eax, eax
0x18020dc88  mov     qword ptr [rsp+1A0h+var_130], r10
0x18020dc8d  lea     rcx, [rbp+0A0h+var_80]; this
0x18020dc91  mov     [rbp+0A0h+var_90], r14d
0x18020dc95  mov     [rbp+0A0h+hModule], r14
0x18020dc99  mov     r13, r9
0x18020dc9c  mov     [rsp+1A0h+var_140], r14
0x18020dca1  mov     r15, r8
0x18020dca4  mov     [rsp+1A0h+lpLibFileName], r14
0x18020dca9  mov     r12b, dl
0x18020dcac  movups  [rbp+0A0h+var_110], xmm0
0x18020dcb0  mov     [rbp+0A0h+var_E0], rax
0x18020dcb4  movups  [rbp+0A0h+var_100], xmm0
0x18020dcb8  mov     [rbp+0A0h+var_D0], r14
0x18020dcbc  movups  [rbp+0A0h+var_F0], xmm0
0x18020dcc0  mov     [rbp+0A0h+var_B0], r14
0x18020dcc4  mov     [rbp+0A0h+var_C0], r14
0x18020dcc8  mov     [rbp+0A0h+var_C8], r14
0x18020dccc  mov     [rbp+0A0h+var_B8], r14
0x18020dcd0  mov     [rbp+0A0h+pprot], r14
0x18020dcd4  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x18020dcd9  mov     [rsp+1A0h+lpExistingFileName], r14
0x18020dcde  mov     [rsp+1A0h+lpNewFileName], r14
0x18020dce3  test    r15, r15
0x18020dce6  jnz     short loc_18020DD41
0x18020dce8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020dcef  mov     ebx, 80070057h
0x18020dcf4  mov     dword ptr [rbp+0A0h+hModule], ebx
0x18020dcf7  test    rcx, rcx
0x18020dcfa  jz      short loc_18020DD3A
0x18020dcfc  lea     esi, [r14+3]
0x18020dd00  xor     edx, edx
0x18020dd02  mov     r8d, esi
0x18020dd05  lea     r9, aNoSandboxPathS; "No sandbox path specified"
0x18020dd0c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020dd11  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020dd18  lea     rax, [rbp+0A0h+hModule]
0x18020dd1c  mov     qword ptr [rbp+0A0h+var_A8], rax
0x18020dd20  lea     r9, asc_1802EE7AC; ": {}"
0x18020dd27  lea     rax, [rbp+0A0h+var_A8]
0x18020dd2b  mov     r8d, esi
0x18020dd2e  mov     dl, 1
0x18020dd30  mov     qword ptr [rsp+1A0h+var_180], rax
0x18020dd35  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020dd3a  mov     edx, 46h ; 'F'
0x18020dd3f  jmp     short loc_18020DDA1
0x18020dd41  test    r10, r10
0x18020dd44  jnz     loc_18020DE73
0x18020dd4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020dd51  mov     ebx, 80004003h
0x18020dd56  mov     dword ptr [rbp+0A0h+hModule], ebx
0x18020dd59  test    rcx, rcx
0x18020dd5c  jz      short loc_18020DD9C
0x18020dd5e  lea     esi, [r10+3]
0x18020dd62  xor     edx, edx
0x18020dd64  mov     r8d, esi
0x18020dd67  lea     r9, aNoRequireReboo; "No require reboot result specified"
0x18020dd6e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020dd73  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020dd7a  lea     rax, [rbp+0A0h+hModule]
0x18020dd7e  mov     qword ptr [rbp+0A0h+var_A8], rax
0x18020dd82  lea     r9, asc_1802EE7AC; ": {}"
0x18020dd89  lea     rax, [rbp+0A0h+var_A8]
0x18020dd8d  mov     r8d, esi
0x18020dd90  mov     dl, 1
0x18020dd92  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18020dd97  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020dd9c  mov     edx, 47h ; 'G'; void *
0x18020dda1  mov     r9d, ebx; char *
0x18020dda4  mov     rcx, [rbp+0A8h]; this
0x18020ddab  lea     r8, aOnecoreBaseCbs_147; "onecore\\base\\cbs\\onepackage\\lib\\cb"...
0x18020ddb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020ddb7  lea     rcx, [rsp+1A0h+lpNewFileName]
0x18020ddbc  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18020ddc1  lea     rcx, [rsp+1A0h+lpExistingFileName]
0x18020ddc6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18020ddcb  lea     rcx, [rbp+0A0h+var_80]
0x18020ddcf  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18020ddd4  mov     rcx, [rbp+0A0h+pprot]
0x18020ddd8  test    rcx, rcx
0x18020dddb  jz      short loc_18020DDED
0x18020dddd  mov     rax, [rcx]
0x18020dde0  mov     rax, [rax+10h]
0x18020dde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020dde9  mov     [rbp+0A0h+pprot], r14
0x18020dded  mov     rcx, [rbp+0A0h+var_B8]
0x18020ddf1  test    rcx, rcx
0x18020ddf4  jz      short loc_18020DE06
0x18020ddf6  mov     rax, [rcx]
0x18020ddf9  mov     rax, [rax+10h]
0x18020ddfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020de02  mov     [rbp+0A0h+var_B8], r14
0x18020de06  mov     rcx, [rbp+0A0h+var_C8]
0x18020de0a  test    rcx, rcx
0x18020de0d  jz      short loc_18020DE1F
0x18020de0f  mov     rax, [rcx]
0x18020de12  mov     rax, [rax+10h]
0x18020de16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020de1b  mov     [rbp+0A0h+var_C8], r14
0x18020de1f  mov     rcx, [rbp+0A0h+var_C0]
0x18020de23  test    rcx, rcx
0x18020de26  jz      short loc_18020DE38
0x18020de28  mov     rax, [rcx]
0x18020de2b  mov     rax, [rax+10h]
0x18020de2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020de34  mov     [rbp+0A0h+var_C0], r14
0x18020de38  mov     rcx, [rbp+0A0h+var_B0]
0x18020de3c  test    rcx, rcx
0x18020de3f  jz      short loc_18020DE51
0x18020de41  mov     rax, [rcx]
0x18020de44  mov     rax, [rax+10h]
0x18020de48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020de4d  mov     [rbp+0A0h+var_B0], r14
0x18020de51  mov     rcx, [rbp+0A0h+var_D0]
0x18020de55  test    rcx, rcx
0x18020de58  jz      loc_18020E65E
0x18020de5e  mov     rax, [rcx]
0x18020de61  mov     rax, [rax+10h]
0x18020de65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020de6a  mov     [rbp+0A0h+var_D0], r14
0x18020de6e  jmp     loc_18020E65E
0x18020de73  mov     rdx, r15
0x18020de76  lea     rcx, [rsp+1A0h+var_140]
0x18020de7b  call    SczAllocFromSzAndEnsureBackslash
0x18020de80  mov     ebx, eax
0x18020de82  test    eax, eax
0x18020de84  jns     short loc_18020DE93
0x18020de86  mov     r9d, eax
0x18020de89  mov     edx, 49h ; 'I'
0x18020de8e  jmp     loc_18020DDA4
0x18020de93  lea     rdx, aMetadata_0; "metadata\\"
0x18020de9a  lea     rcx, [rsp+1A0h+var_140]
0x18020de9f  call    SczAllocConcatSz
0x18020dea4  mov     ebx, eax
0x18020dea6  test    eax, eax
0x18020dea8  jns     short loc_18020DEB7
0x18020deaa  mov     r9d, eax
0x18020dead  mov     edx, 4Ah ; 'J'
0x18020deb2  jmp     loc_18020DDA4
0x18020deb7  mov     r8, [rsp+1A0h+var_140]
0x18020debc  lea     r9, aUpdateagentDll; "updateagent.dll"
0x18020dec3  lea     rdx, aWsWs_1; "%ws%ws"
0x18020deca  lea     rcx, [rsp+1A0h+lpLibFileName]
0x18020decf  call    SczAllocFormatted
0x18020ded4  mov     ebx, eax
0x18020ded6  test    eax, eax
0x18020ded8  jns     short loc_18020DEE7
0x18020deda  mov     r9d, eax
0x18020dedd  mov     edx, 4Ch ; 'L'
0x18020dee2  jmp     loc_18020DDA4
0x18020dee7  cmp     [rbp+0A0h+pprot], r14
0x18020deeb  jnz     loc_18020ECF4
0x18020def1  lea     rdx, [rbp+0A0h+pprot]; pprot
0x18020def5  xor     ecx, ecx; reserved
0x18020def7  call    cs:__imp_GetRunningObjectTable
0x18020defe  nop     dword ptr [rax+rax+00h]
0x18020df03  mov     ebx, eax
0x18020df05  test    eax, eax
0x18020df07  jns     short loc_18020DF61
0x18020df09  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020df10  mov     dword ptr [rbp+0A0h+hModule], eax
0x18020df13  test    rcx, rcx
0x18020df16  jz      short loc_18020DF57
0x18020df18  mov     esi, 3
0x18020df1d  lea     r9, aFailedToGetThe_1; "Failed to get the running object table."
0x18020df24  mov     r8d, esi
0x18020df27  xor     edx, edx
0x18020df29  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020df2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020df35  lea     rax, [rbp+0A0h+hModule]
0x18020df39  mov     qword ptr [rbp+0A0h+var_A8], rax
0x18020df3d  lea     r9, asc_1802EE7AC; ": {}"
0x18020df44  lea     rax, [rbp+0A0h+var_A8]
0x18020df48  mov     r8d, esi
0x18020df4b  mov     dl, 1
0x18020df4d  mov     qword ptr [rsp+1A0h+var_180], rax
0x18020df52  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020df57  mov     edx, 4Eh ; 'N'
0x18020df5c  jmp     loc_18020DDA1
0x18020df61  lea     rax, [rbp+0A0h+pprot]
0x18020df65  mov     [rbp+0A0h+var_118], 1
0x18020df69  mov     [rsp+1A0h+var_128], rax
0x18020df6e  lea     r9, [rbp+0A0h+var_80]
0x18020df72  lea     rax, [rbp+0A0h+arg_20]
0x18020df79  mov     rdx, r15
0x18020df7c  lea     r8, aAggregatedmeta; "*.aggregatedmetadata.cab"
0x18020df83  mov     [rbp+0A0h+var_120], rax
0x18020df87  call    CbsEnumFiles
0x18020df8c  mov     ebx, eax
0x18020df8e  test    eax, eax
0x18020df90  jns     loc_18020E03B
0x18020df96  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020df9d  mov     esi, 3
0x18020dfa2  mov     dword ptr [rbp+0A0h+hModule], eax
0x18020dfa5  test    rcx, rcx
0x18020dfa8  jz      short loc_18020DFE4
0x18020dfaa  lea     r9, aFailedGettingT_3; "Failed getting the aggregatedmetadata f"...
0x18020dfb1  mov     r8d, esi
0x18020dfb4  xor     edx, edx
0x18020dfb6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18020dfbb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020dfc2  lea     rax, [rbp+0A0h+hModule]
0x18020dfc6  mov     qword ptr [rbp+0A0h+var_A8], rax
0x18020dfca  lea     r9, asc_1802EE7AC; ": {}"
0x18020dfd1  lea     rax, [rbp+0A0h+var_A8]
0x18020dfd5  mov     r8d, esi
0x18020dfd8  mov     dl, 1
0x18020dfda  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18020dfdf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18020dfe4  mov     rcx, [rbp+0A8h]; this
0x18020dfeb  lea     r8, aOnecoreBaseCbs_147; "onecore\\base\\cbs\\onepackage\\lib\\cb"...
0x18020dff2  mov     r9d, ebx; char *
0x18020dff5  mov     edx, 5Ch ; '\'; void *
0x18020dffa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020dfff  mov     rcx, [rbp+0A0h+pprot]
0x18020e003  test    rcx, rcx
0x18020e006  jz      loc_18020DDB7
0x18020e00c  mov     edx, [rbp+0A0h+arg_20]
0x18020e012  test    edx, edx
0x18020e014  jz      loc_18020DDB7
0x18020e01a  mov     rax, [rcx]
0x18020e01d  mov     rax, [rax+20h]
0x18020e021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020e026  lea     r8, aFailedToRemove_10; "Failed to remove session object from Ro"...
0x18020e02d  mov     edx, eax
0x18020e02f  mov     ecx, esi
0x18020e031  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18020e036  jmp     loc_18020DDB7
0x18020e03b  mov     rsi, [rbp+0A0h+var_68]
0x18020e03f  mov     rdi, r14
0x18020e042  test    rsi, rsi
0x18020e045  jz      loc_18020E0E7
0x18020e04b  mov     r14, [rbp+0A0h+var_58]
0x18020e04f  mov     rdx, r15
0x18020e052  lea     rcx, [rsp+1A0h+lpExistingFileName]
0x18020e057  call    SczAllocFromSzAndEnsureBackslash
0x18020e05c  mov     ebx, eax
0x18020e05e  test    eax, eax
0x18020e060  js      loc_18020E404
0x18020e066  cmp     rdi, rsi
0x18020e069  jb      short loc_18020E072
0x18020e06b  mov     ecx, 8
0x18020e070  int     29h; Win8: RtlFailFast(ecx)
0x18020e072  mov     rdx, [r14+rdi*8]
0x18020e076  lea     rcx, [rsp+1A0h+lpExistingFileName]
0x18020e07b  call    SczAllocConcatSz
0x18020e080  mov     ebx, eax
0x18020e082  test    eax, eax
0x18020e084  js      loc_18020E3FD
0x18020e08a  cmp     rdi, rsi
0x18020e08d  jb      short loc_18020E096
0x18020e08f  mov     ecx, 8
0x18020e094  int     29h; Win8: RtlFailFast(ecx)
0x18020e096  mov     r9, [r14+rdi*8]
0x18020e09a  lea     rdx, aWsWs_1; "%ws%ws"
0x18020e0a1  mov     r8, [rsp+1A0h+var_140]
0x18020e0a6  lea     rcx, [rsp+1A0h+lpNewFileName]
0x18020e0ab  call    SczAllocFormatted
0x18020e0b0  mov     ebx, eax
0x18020e0b2  test    eax, eax
0x18020e0b4  js      loc_18020E3F6
0x18020e0ba  mov     rdx, [rsp+1A0h+lpNewFileName]; lpNewFileName
0x18020e0bf  xor     r8d, r8d; bFailIfExists
0x18020e0c2  mov     rcx, [rsp+1A0h+lpExistingFileName]; lpExistingFileName
0x18020e0c7  call    cs:__imp_CopyFileW
0x18020e0ce  nop     dword ptr [rax+rax+00h]
0x18020e0d3  test    eax, eax
0x18020e0d5  jz      loc_18020E250
0x18020e0db  inc     rdi
0x18020e0de  cmp     rdi, rsi
0x18020e0e1  jb      loc_18020E04F
0x18020e0e7  mov     rcx, [rsp+1A0h+lpLibFileName]
0x18020e0ec  test    r13, r13
0x18020e0ef  setz    dl
0x18020e0f2  call    CbsVerifyFileSignature
0x18020e0f7  mov     ebx, eax
0x18020e0f9  mov     esi, 3
0x18020e0fe  test    r12b, r12b
0x18020e101  jz      loc_18020E50D
0x18020e107  lea     r8, aUpdateagentDll_0; "Updateagent dll not signed. Continuing "...
0x18020e10e  mov     edx, eax
0x18020e110  mov     ecx, esi
0x18020e112  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
  ... truncated ...
```

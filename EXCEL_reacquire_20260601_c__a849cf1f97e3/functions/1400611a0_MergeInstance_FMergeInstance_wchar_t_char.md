# MergeInstance::FMergeInstance(wchar_t *,char *)

- ea: `0x1400611a0`
- end: `0x140061c38`
- name: `?FMergeInstance@MergeInstance@@SAHPEA_WPEAD@Z`
- size: `2712`
- prototype: `__int64 __fastcall(wchar_t *, char *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140047260`

## callees

- `0x1400463e0`
- `0x14004fdd8`
- `0x140052580`
- `0x140052640`
- `0x140055228`
- `0x140059030`
- `0x1400611a0`
- `0x140069280`
- `0x140075560`
- `0x140075ee0`
- `0x140075fc0`
- `0x140077c80`
- `0x14009a188`
- `0x1400a11f0`
- `0x14020b160`
- `0x1402fd290`
- `0x14030fdf0`
- `0x1408c5b60`
- `0x1408c6d20`
- `0x1408cc450`
- `0x1408cc4b0`
- `0x1408cfe50`
- `0x140f0f000`
- `0x141913f18`
- `0x14270f510`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400618e4`
- `KERNEL32!CloseHandle` at `0x1400618f5`
- `KERNEL32!CloseHandle` at `0x140061bc0`
- `KERNEL32!CloseHandle` at `0x140061bd4`
- `KERNEL32!CloseHandle` at `0x140061be5`
- `KERNEL32!CloseHandle` at `0x1400618e4`
- `KERNEL32!CloseHandle` at `0x1400618f5`
- `KERNEL32!CloseHandle` at `0x140061bc0`
- `KERNEL32!CloseHandle` at `0x140061bd4`
- `KERNEL32!CloseHandle` at `0x140061be5`
- `KERNEL32!Sleep` at `0x14006144f`
- `KERNEL32!Sleep` at `0x14006144f`
- `KERNEL32!GetLastError` at `0x140061894`
- `KERNEL32!GetLastError` at `0x140061980`
- `KERNEL32!GetLastError` at `0x140061894`
- `KERNEL32!GetLastError` at `0x140061980`
- `KERNEL32!CreateEventW` at `0x14006156b`
- `KERNEL32!CreateEventW` at `0x1400615c8`
- `KERNEL32!CreateEventW` at `0x14006156b`
- `KERNEL32!CreateEventW` at `0x1400615c8`
- `KERNEL32!MapViewOfFile` at `0x1400616c2`
- `KERNEL32!MapViewOfFile` at `0x1400616c2`
- `KERNEL32!GetCurrentProcessId` at `0x140061841`
- `KERNEL32!GetCurrentProcessId` at `0x140061841`
- `KERNEL32!GetCurrentProcess` at `0x1400617b7`
- `KERNEL32!GetCurrentProcess` at `0x1400617b7`
- `KERNEL32!GetCommandLineW` at `0x14006130b`
- `KERNEL32!GetCommandLineW` at `0x14006130b`
- `KERNEL32!GlobalAddAtomW` at `0x140061521`
- `KERNEL32!GlobalAddAtomW` at `0x140061720`
- `KERNEL32!GlobalAddAtomW` at `0x140061521`
- `KERNEL32!GlobalAddAtomW` at `0x140061720`
- `KERNEL32!OpenProcess` at `0x140061884`
- `KERNEL32!OpenProcess` at `0x140061884`
- `KERNEL32!GlobalDeleteAtom` at `0x140061ba0`
- `KERNEL32!GlobalDeleteAtom` at `0x140061bae`
- `KERNEL32!GlobalDeleteAtom` at `0x140061ba0`
- `KERNEL32!GlobalDeleteAtom` at `0x140061bae`
- `KERNEL32!CreateFileMappingW` at `0x140061680`
- `KERNEL32!CreateFileMappingW` at `0x140061680`
- `KERNEL32!UnmapViewOfFile` at `0x140061711`
- `KERNEL32!UnmapViewOfFile` at `0x140061711`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x140061835`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x140061835`
- `KERNEL32!Process32FirstW` at `0x140061850`
- `KERNEL32!Process32FirstW` at `0x140061850`
- `KERNEL32!Process32NextW` at `0x140061864`
- `KERNEL32!Process32NextW` at `0x140061864`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140061a00`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140061a00`
- `USER32!GetWindowThreadProcessId` at `0x140061808`
- `USER32!GetWindowThreadProcessId` at `0x140061808`
- `USER32!PostMessageW` at `0x140061927`
- `USER32!PostMessageW` at `0x140061927`
- `USER32!FindWindowExW` at `0x1400617e2`
- `USER32!FindWindowExW` at `0x1400617e2`
- `USER32!AllowSetForegroundWindow` at `0x140061812`
- `USER32!AllowSetForegroundWindow` at `0x140061812`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140061b80`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140061b80`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1400613e1`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1400613e1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140061961`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140061b73`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140061961`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140061b73`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x1400619c0`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x1400619c0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061a95`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061ab5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061ad9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061af8`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b19`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b38`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061a95`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061ab5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061ad9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061af8`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b19`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b38`
- `Mso20Win32Client!__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x14006164b`
- `Mso20Win32Client!__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x14006164b`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x1400619d7`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x1400619d7`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140061a60`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140061a60`
- `Mso20Win32Client!__imp_MsoWaitForMultipleObjects` at `0x140061949`
- `Mso20Win32Client!__imp_MsoWaitForMultipleObjects` at `0x140061949`
- `Mso20Win32Client!__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x1400616a0`
- `Mso20Win32Client!__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x1400616a0`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x14006178d`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x14006178d`
- `Mso20Win32Client!__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z` at `0x1400613c0`
- `Mso20Win32Client!__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z` at `0x1400613c0`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x1400617c5`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x1400618d3`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x1400617c5`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x1400618d3`

## string_xrefs

- `0x1400618a3`: `OpenProcess failed during FSkipPostMergeInstanceMessage. Error: %d`
- `0x140061ac0`: `Created`

## pseudocode

```c
__int64 __fastcall MergeInstance::FMergeInstance(wchar_t *a1, char *a2)
{
  HWND v4; // r15
  ATOM v5; // di
  void *v6; // rsi
  unsigned int v7; // r13d
  LPWSTR CommandLineW; // r12
  bool v9; // zf
  unsigned int v10; // eax
  unsigned int Dw; // eax
  int v12; // ebx
  int v13; // eax
  __int64 v14; // rax
  int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rbx
  ATOM v18; // ax
  __int64 v19; // r13
  __int64 v20; // rdx
  __int64 v21; // rdx
  HANDLE EventW; // rax
  __int64 v23; // rax
  int v24; // edi
  __int64 v25; // rax
  int v26; // ebx
  unsigned int v27; // r12d
  char *v28; // rsi
  unsigned int v29; // r12d
  DWORD LastError; // edi
  Mso::Security *CurrentProcess; // rax
  unsigned int *v32; // r8
  HWND Window; // rax
  HANDLE Toolhelp32Snapshot; // rbx
  DWORD th32ParentProcessID; // r14d
  DWORD CurrentProcessId; // esi
  BOOL i; // eax
  unsigned int v38; // ebx
  HANDLE v39; // rsi
  unsigned int *v40; // r8
  bool v41; // bl
  int v42; // eax
  void *ThreadLocalStoragePointer; // rax
  __int64 v44; // rdx
  int v45; // ebx
  struct Mso::Telemetry::IDataFieldCollection *v46; // rax
  struct Mso::Telemetry::IDataFieldCollection *v47; // rax
  struct Mso::Telemetry::IDataFieldCollection *v48; // rax
  struct Mso::Telemetry::IDataFieldCollection *v49; // rax
  struct Mso::Telemetry::IDataFieldCollection *v50; // rax
  __int64 v51; // r8
  struct Mso::Telemetry::IDataFieldCollection *v52; // rax
  unsigned int v53; // r9d
  const wchar_t *dwMaximumSizeLow; // [rsp+20h] [rbp-E0h]
  DWORD lpName; // [rsp+28h] [rbp-D8h]
  ATOM v57; // [rsp+50h] [rbp-B0h]
  unsigned int v58; // [rsp+54h] [rbp-ACh] BYREF
  int v59; // [rsp+58h] [rbp-A8h]
  unsigned int v60; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE v61[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v62[2]; // [rsp+62h] [rbp-9Eh] BYREF
  _BYTE v63[4]; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwProcessId; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v65; // [rsp+6Ch] [rbp-94h] BYREF
  __int16 v66; // [rsp+70h] [rbp-90h] BYREF
  char v67; // [rsp+72h] [rbp-8Eh]
  void *Src; // [rsp+78h] [rbp-88h]
  HANDLE FileMappingW; // [rsp+80h] [rbp-80h]
  _QWORD v70[2]; // [rsp+88h] [rbp-78h] BYREF
  int v71; // [rsp+98h] [rbp-68h] BYREF
  HANDLE hObject[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES *v73; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v74[8]; // [rsp+B8h] [rbp-48h] BYREF
  void **v75; // [rsp+C0h] [rbp-40h] BYREF
  const char *v76; // [rsp+C8h] [rbp-38h]
  _BYTE v77[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v78[8]; // [rsp+E0h] [rbp-20h] BYREF
  void *v79[5]; // [rsp+E8h] [rbp-18h] BYREF
  PROCESSENTRY32W pe; // [rsp+110h] [rbp+10h] BYREF
  WCHAR String[31]; // [rsp+350h] [rbp+250h] BYREF
  __int128 v82; // [rsp+38Eh] [rbp+28Eh]
  __int128 v83; // [rsp+39Eh] [rbp+29Eh]
  int v84; // [rsp+3AEh] [rbp+2AEh]
  __int16 v85; // [rsp+3B2h] [rbp+2B2h]
  WCHAR Name[37]; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int128 v87; // [rsp+40Ah] [rbp+30Ah]
  __int64 v88; // [rsp+41Ah] [rbp+31Ah]
  __int16 v89; // [rsp+422h] [rbp+322h]

  v60 = 5;
  dwProcessId = 0;
  v4 = 0;
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v79,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  v5 = 0;
  v6 = 0;
  *(_OWORD *)hObject = 0;
  v7 = 0;
  v84 = 0;
  wcscpy(String, L"Local\\ExcelMergeInstanceEvent_");
  v85 = 0;
  v82 = 0;
  v83 = 0;
  v71 = 1;
  wcscpy(Name, L"Local\\ExcelMergeInstanceFileMapping_");
  v87 = 0;
  v73 = 0;
  v59 = 0;
  v88 = 0;
  v89 = 0;
  CommandLineW = GetCommandLineW();
  Src = CommandLineW;
  if ( (unsigned int)FOsrc()
    || (unsigned int)FCmdLineOption(21, 22, a1, a2)
    || (unsigned int)FLoadCmdLineWithMph(a1, a2, &v60, 1, v79, v78, &v71) )
  {
    goto LABEL_91;
  }
  v58 = 0;
  v9 = MsoFOpenCreateEvent(&hEvent, "XL16RunningEvent", 1, 0, (int *)&v58, 0, 0x8022u) == 0;
  v10 = 0;
  if ( !v9 )
    v10 = v58;
  if ( v10 )
    goto LABEL_91;
  Dw = MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelDisableMergeInstance);
  if ( Dw == 2
    || Dw
    && !DelayedMergeInstance::FFilePresent(a1, a2, (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain) )
  {
    goto LABEL_91;
  }
  if ( (unsigned int)FCmdLineOption(40, 41, a1, a2) )
    goto LABEL_91;
  if ( OsrcGetAsyncKeyState(18) < 0 && OsrcGetAsyncKeyState(17) >= 0 )
  {
    Sleep(0x3E8u);
    if ( OsrcGetAsyncKeyState(18) < 0 && OsrcGetAsyncKeyState(17) >= 0 )
    {
      v12 = fForceDlgUp;
      fForceDlgUp = 1;
      v13 = NoYesAlert(655404, 0);
      fForceDlgUp = v12;
      if ( v13 == 6 )
        goto LABEL_91;
    }
  }
  v14 = -1;
  do
    ++v14;
  while ( String[v14] );
  v15 = g_processIdExcel;
  SzHexFromL(g_processIdExcel, 9, &String[(int)v14]);
  v16 = -1;
  do
    ++v16;
  while ( Name[v16] );
  SzHexFromL(v15, 9, &Name[(int)v16]);
  v17 = -1;
  do
    ++v17;
  while ( String[v17] );
  v18 = GlobalAddAtomW(String);
  v19 = v18;
  if ( !v18 )
    goto LABEL_86;
  v20 = -1;
  do
    ++v20;
  while ( szMergeInstanceEventAcceptSuffix[v20] );
  FAppendRgchToSz(szMergeInstanceEventAcceptSuffix, v20, String, 50);
  hObject[0] = CreateEventW(0, 0, 0, String);
  if ( (unsigned __int64)(2LL * (int)v17) >= 0x64 )
    _report_rangecheckfailure();
  String[(int)v17] = 0;
  v21 = -1;
  do
    ++v21;
  while ( szMergeInstanceEventRejectSuffix[v21] );
  FAppendRgchToSz(szMergeInstanceEventRejectSuffix, v21, String, 50);
  EventW = CreateEventW(0, 0, 0, String);
  hObject[1] = EventW;
  if ( !hObject[0] || !EventW )
    goto LABEL_84;
  if ( a2 )
  {
    v23 = -1;
    do
      ++v23;
    while ( a2[v23] );
  }
  else
  {
    LODWORD(v23) = 0;
  }
  v24 = v23 + 1;
  if ( CommandLineW )
  {
    v25 = -1;
    do
      ++v25;
    while ( CommandLineW[v25] );
  }
  else
  {
    LODWORD(v25) = 0;
  }
  v26 = 2 * v25 + 2;
  FCurDirWithMph((struct MaxPathHolder *)v79, 0);
  v27 = 2 * *(unsigned __int16 *)v79[0] + 4;
  if ( !MsoFMNOResolveSecurity(0x8022u, &v73, 4) )
  {
    v5 = 0;
    goto LABEL_84;
  }
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, v24 + v27 + v26, Name);
  v6 = FileMappingW;
  MsoMNOReleaseSecurity(0x8022u, &v73, 4);
  if ( !v6 )
  {
LABEL_83:
    v5 = 0;
    goto LABEL_84;
  }
  v28 = (char *)MapViewOfFile(v6, 2u, 0, 0, 0);
  if ( !v28 )
  {
    v6 = FileMappingW;
    goto LABEL_83;
  }
  BltB(a2, v28, v24);
  BltB(Src, &v28[v24], v26);
  BltB(v79[0], &v28[v24 + (__int64)v26], v27);
  UnmapViewOfFile(v28);
  v57 = GlobalAddAtomW(Name);
  v5 = v57;
  if ( !v57 )
  {
    v6 = FileMappingW;
    goto LABEL_84;
  }
  v29 = 0;
  LastError = 0;
  LODWORD(Src) = 1;
  v60 = 0;
  if ( hEvent )
  {
    v76 = 0;
    v75 = &Mso::Timing::TStopwatch<std::chrono::steady_clock>::`vftable';
    std::chrono::steady_clock::now(v77);
    v75 = &Mso::Timing::TStopwatch<std::chrono::steady_clock>::`vftable';
    v77[8] = 1;
    LODWORD(Src) = MsoWaitForSingleObject(hEvent, 20000);
    v60 = *(_DWORD *)((__int64 (__fastcall *)(void ***, _BYTE *))v75[5])(&v75, v74);
  }
  v65 = 0;
  CurrentProcess = (Mso::Security *)GetCurrentProcess();
  Mso::Security::HrGetProcessIL(CurrentProcess, &v65, v32);
  while ( 1 )
  {
    do
    {
      Window = FindWindowExW(HWND_MESSAGE, v4, L"XL16MERGE", 0);
      v4 = Window;
    }
    while ( Window == hWndNewOwner );
    if ( !Window )
      break;
    ++v29;
    GetWindowThreadProcessId(Window, &dwProcessId);
    AllowSetForegroundWindow(dwProcessId);
    memset_0(&pe.cntUsage, 0, 0x234u);
    pe.dwSize = 568;
    Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
    th32ParentProcessID = 0;
    CurrentProcessId = GetCurrentProcessId();
    for ( i = Process32FirstW(Toolhelp32Snapshot, &pe); i; i = Process32NextW(Toolhelp32Snapshot, &pe) )
    {
      if ( pe.th32ProcessID == CurrentProcessId )
      {
        th32ParentProcessID = pe.th32ParentProcessID;
        break;
      }
    }
    v38 = v65;
    v39 = OpenProcess(0x400u, 0, dwProcessId);
    if ( v39 )
    {
      v58 = 0;
      if ( (int)Mso::Security::HrGetProcessIL((Mso::Security *)v39, &v58, v40) < 0 )
      {
        CloseHandle(v39);
        goto LABEL_60;
      }
      v41 = v58 < v38;
      CloseHandle(v39);
      if ( !v41 )
        goto LABEL_60;
    }
    else
    {
      lpName = GetLastError();
      dwMaximumSizeLow = L"OpenProcess failed during FSkipPostMergeInstanceMessage. Error: %d";
      XlsDiag::SendTraceTag(557176143, 141, 15);
LABEL_60:
      if ( PostMessageW(v4, 0x420u, th32ParentProcessID, v57 | (unsigned __int64)(v19 << 16)) )
      {
        LastError = 0;
        v42 = MsoWaitForMultipleObjects(2, hObject, 0, 5000, dwMaximumSizeLow, lpName);
        if ( !v42 )
        {
          sub_140F0F000(v4);
          if ( !byte_144014A88 )
            _invoke_watson(0, 0, 0, 0, 0);
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          HIBYTE(word_144014A71) = 1;
          if ( *(_BYTE *)(*(_QWORD *)ThreadLocalStoragePointer + 313LL)
            && !MsoFIsRunningRestricted()
            && byte_144118DF0 != 1 )
          {
            LOBYTE(v44) = 1;
            Mso::Telemetry::UngracefulExit::OverrideSessionFlag(4, v44);
            byte_144118DF0 = 1;
          }
          v45 = 1;
          v59 = 1;
          goto LABEL_76;
        }
        if ( v42 == -1 )
        {
          MsoShipAssertTagProc(557176137);
          goto LABEL_64;
        }
      }
      else if ( !LastError )
      {
        LastError = GetLastError();
      }
    }
  }
  v45 = v59;
  if ( !LastError )
    LastError = -2147319765;
LABEL_76:
  v61[1] = 0;
  v66 = 2;
  v67 = 1;
  v62[1] = 0;
  v63[1] = 0;
  BYTE1(v58) = 0;
  Mso::Telemetry::EventFlags::EventFlags(v74, &v58, v63, v62, &v66, v61);
  v75 = (void **)&off_1437A1F10;
  v76 = "MergeInstances";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v70,
    (const struct Mso::Telemetry::EventName *)&v75,
    (const struct Mso::Telemetry::EventFlags *)v74);
  if ( !v45 )
  {
    v46 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v46, "LastError", LastError, 4);
  }
  v47 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v47, "Created", 0, 4);
  v48 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v48, "FoundInstance", v29, 4);
  v49 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v49, "WaitEvent", (unsigned int)Src, 4);
  v50 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
  LOBYTE(v51) = v45;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v50, "Merge", v51, 4);
  v52 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
  Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v52, "WaitForSingleObjectDurationMs", v60, 4);
  if ( v70[0] )
    Mso::Telemetry::SetActivityResultHr((Mso::Telemetry *)v70, 0, 557176136, v53);
  else
    MsoShipAssertTagProc(562177664);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v70);
LABEL_64:
  v6 = FileMappingW;
  v5 = v57;
LABEL_84:
  if ( (_WORD)v19 )
    GlobalDeleteAtom(v19);
LABEL_86:
  if ( v5 )
    GlobalDeleteAtom(v5);
  if ( v6 )
    CloseHandle(v6);
  v7 = v59;
LABEL_91:
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v79);
  return v7;
}

```

## disassembly

```asm
0x1400611a0  mov     [rsp-8+arg_10], rbx
0x1400611a6  push    rbp
0x1400611a7  push    rsi
0x1400611a8  push    rdi
0x1400611a9  push    r12
0x1400611ab  push    r13
0x1400611ad  push    r14
0x1400611af  push    r15
0x1400611b1  lea     rbp, [rsp-340h]
0x1400611b9  sub     rsp, 440h
0x1400611c0  mov     rax, cs:__security_cookie
0x1400611c7  xor     rax, rsp
0x1400611ca  mov     [rbp+370h+var_40], rax
0x1400611d1  mov     r14, rdx
0x1400611d6  mov     [rsp+470h+var_414], 5
0x1400611de  mov     rbx, rcx
0x1400611e1  lea     rdx, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; struct IMemHeap *
0x1400611e8  xor     r12d, r12d
0x1400611eb  lea     rcx, [rbp+370h+var_388]; this
0x1400611ef  xor     r9d, r9d; bool
0x1400611f2  mov     [rsp+470h+dwProcessId], r12d
0x1400611f7  mov     r8d, 103h; int
0x1400611fd  mov     r15d, r12d
0x140061200  call    ??0MaxPathHolder@@QEAA@PEAVIMemHeap@@H_N@Z; MaxPathHolder::MaxPathHolder(IMemHeap *,int,bool)
0x140061205  mov     eax, dword ptr cs:aLocalExcelmerg_0+38h; "t_"
0x14006120b  xorps   xmm0, xmm0
0x14006120e  movups  xmm1, xmmword ptr cs:aLocalExcelmerg_0+10h; "celMergeInstanceEvent_"
0x140061215  mov     [rbp+370h+var_E8], eax
0x14006121b  movzx   edi, r12w
0x14006121f  movzx   eax, word ptr cs:aLocalExcelmerg_0+3Ch; ""
0x140061226  mov     esi, r12d
0x140061229  movdqu  xmmword ptr [rbp+370h+hObject], xmm0
0x14006122e  mov     [rbp+370h+var_E4], ax
0x140061235  xor     eax, eax
0x140061237  movups  xmm0, xmmword ptr cs:aLocalExcelmerg_0; "Local\\ExcelMergeInstanceEvent_"
0x14006123e  mov     r13d, r12d
0x140061241  mov     [rbp+370h+var_C2], eax
0x140061247  movaps  [rbp+370h+var_110], xmm1
0x14006124e  movaps  xmm1, xmmword ptr cs:aLocalExcelmerg+10h; "celMergeInstanceFileMapping_"
0x140061255  movaps  xmmword ptr [rbp+370h+String], xmm0
0x14006125c  movups  xmm0, xmmword ptr cs:aLocalExcelmerg_0+20h; "InstanceEvent_"
0x140061263  mov     [rbp+370h+var_BE], ax
0x14006126a  movzx   eax, word ptr cs:aLocalExcelmerg+48h; ""
0x140061271  movaps  [rbp+370h+var_100], xmm0
0x140061278  movsd   xmm0, qword ptr cs:aLocalExcelmerg_0+30h; "Event_"
0x140061280  movsd   [rbp+370h+var_F0], xmm0
0x140061288  xorps   xmm0, xmm0
0x14006128b  movups  [rbp+370h+var_E2], xmm0
0x140061292  mov     [rbp+370h+var_68], ax
0x140061299  xor     eax, eax
0x14006129b  movups  [rbp+370h+var_D2], xmm0
0x1400612a2  mov     [rbp+370h+var_3D8], 1
0x1400612a9  movaps  xmm0, xmmword ptr cs:aLocalExcelmerg; "Local\\ExcelMergeInstanceFileMapping_"
0x1400612b0  movaps  xmmword ptr [rbp+370h+Name], xmm0
0x1400612b7  movaps  xmm0, xmmword ptr cs:aLocalExcelmerg+20h; "InstanceFileMapping_"
0x1400612be  movaps  [rbp+370h+var_90], xmm0
0x1400612c5  movsd   xmm0, qword ptr cs:aLocalExcelmerg+40h; "ing_"
0x1400612cd  movsd   [rbp+370h+var_70], xmm0
0x1400612d5  xorps   xmm0, xmm0
0x1400612d8  movaps  [rbp+370h+var_A0], xmm1
0x1400612df  movaps  xmm1, xmmword ptr cs:aLocalExcelmerg+30h; "FileMapping_"
0x1400612e6  movups  [rbp+370h+var_66], xmm0
0x1400612ed  mov     [rbp+370h+var_3C0], r12
0x1400612f1  mov     [rsp+470h+var_418], r12d
0x1400612f6  movaps  [rbp+370h+var_80], xmm1
0x1400612fd  mov     [rbp+370h+var_56], rax
0x140061304  mov     [rbp+370h+var_4E], ax
0x14006130b  call    cs:__imp_GetCommandLineW
0x140061311  mov     r12, rax
0x140061314  mov     [rsp+470h+Src], rax
0x140061319  call    ?FOsrc@@YAHXZ; FOsrc(void)
0x14006131e  xchg    ax, ax
0x140061320  test    eax, eax
0x140061322  jnz     loc_140061BCB
0x140061328  mov     r9, r14; char *
0x14006132b  lea     edx, [rsi+16h]; int
0x14006132e  mov     r8, rbx; wchar_t *
0x140061331  lea     ecx, [rsi+15h]; int
0x140061334  call    ?FCmdLineOption@@YAHHHPEA_WPEAD@Z; FCmdLineOption(int,int,wchar_t *,char *)
0x140061339  xor     ecx, ecx
0x140061340  test    eax, eax
0x140061342  jnz     loc_140061BCB
0x140061348  mov     [rsp+470h+var_428], ecx
0x140061351  lea     rax, [rbp+370h+var_3D8]
0x140061355  mov     [rsp+470h+var_430], rcx
0x14006135a  lea     r9d, [rsi+1]
0x14006135e  mov     [rsp+470h+var_440], rax
0x140061363  lea     r8, [rsp+470h+var_414]
0x140061368  lea     rax, [rbp+370h+var_390]
0x14006136c  mov     rdx, r14
0x14006136f  mov     [rsp+470h+lpName], rax
0x140061374  mov     rcx, rbx
0x140061377  lea     rax, [rbp+370h+var_388]
0x14006137b  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax
0x140061380  call    ?FLoadCmdLineWithMph@@YAHPEA_WPEADPEAHW4CmdLineFlags@@PEAVMaxPathHolder@@2200H@Z; FLoadCmdLineWithMph(wchar_t *,char *,int *,CmdLineFlags,MaxPathHolder *,int *,int *,wchar_t *,wchar_t *,int)
0x140061385  xor     ecx, ecx
0x140061387  test    eax, eax
0x140061389  jnz     loc_140061BCB
0x14006138f  mov     dword ptr [rsp+470h+var_440], 8022h
0x140061398  lea     rax, [rsp+470h+var_41C]
0x14006139d  mov     [rsp+470h+lpName], rcx
0x1400613a2  lea     r8d, [rsi+1]
0x1400613a6  mov     [rsp+470h+var_41C], ecx
0x1400613aa  lea     rdx, aXl16runningeve; "XL16RunningEvent"
0x1400613b1  lea     rcx, hEvent
0x1400613b8  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax
0x1400613bd  xor     r9d, r9d
0x1400613c0  call    cs:__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z; MsoFOpenCreateEvent(void * *,char const *,int,int,int *,_SECURITY_ATTRIBUTES *,ulong)
0x1400613c6  xor     ecx, ecx
0x1400613c8  test    eax, eax
0x1400613ca  mov     eax, ecx
0x1400613cc  jz      short loc_1400613D2
0x1400613ce  mov     eax, [rsp+470h+var_41C]
0x1400613d2  test    eax, eax
0x1400613d4  jnz     loc_140061BCB
0x1400613da  lea     rcx, ?vmsoridExcelDisableMergeInstance@@3U_msoreg@@B; _msoreg const vmsoridExcelDisableMergeInstance
0x1400613e1  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1400613e7  mov     ecx, 2
0x1400613ec  cmp     eax, ecx
0x1400613ee  jz      loc_140061BCB
0x1400613f4  test    eax, eax
0x1400613f6  jz      short loc_140061412
0x1400613f8  lea     r8, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; struct IMemHeap *
0x1400613ff  mov     rdx, r14; char *
0x140061402  mov     rcx, rbx; Src
0x140061405  call    ?FFilePresent@DelayedMergeInstance@@SA_NPEB_WPEBDPEAVIMemHeap@@@Z; DelayedMergeInstance::FFilePresent(wchar_t const *,char const *,IMemHeap *)
0x14006140a  test    al, al
0x14006140c  jz      loc_140061BCB
0x140061412  mov     edx, 29h ; ')'; int
0x140061417  mov     r9, r14; char *
0x14006141a  mov     r8, rbx; wchar_t *
0x14006141d  lea     ecx, [rdx-1]; int
0x140061420  call    ?FCmdLineOption@@YAHHHPEA_WPEAD@Z; FCmdLineOption(int,int,wchar_t *,char *)
0x140061425  xor     ebx, ebx
0x140061427  test    eax, eax
0x140061429  jnz     loc_140061BCB
0x14006142f  lea     ecx, [rbx+12h]; int
0x140061432  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x140061437  test    ax, ax
0x14006143a  jns     short loc_14006149F
0x14006143c  lea     ecx, [rbx+11h]; int
0x140061440  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x140061445  test    ax, ax
0x140061448  js      short loc_14006149F
0x14006144a  mov     ecx, 3E8h; dwMilliseconds
0x14006144f  call    cs:__imp_Sleep
0x140061455  lea     ecx, [rbx+12h]; int
0x140061458  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x14006145d  nop     dword ptr [rax]
0x140061460  test    ax, ax
0x140061463  jns     short loc_14006149F
0x140061465  lea     ecx, [rbx+11h]; int
0x140061468  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x14006146d  test    ax, ax
0x140061470  js      short loc_14006149F
0x140061472  mov     ebx, cs:?fForceDlgUp@@3HA; int fForceDlgUp
0x140061478  xor     edx, edx; wchar_t *
0x14006147a  mov     ecx, 0A002Ch; int
0x14006147f  mov     cs:?fForceDlgUp@@3HA, 1; int fForceDlgUp
0x140061489  call    ?NoYesAlert@@YAHHPEB_W@Z; NoYesAlert(int,wchar_t const *)
0x14006148e  mov     cs:?fForceDlgUp@@3HA, ebx; int fForceDlgUp
0x140061494  cmp     eax, 6
0x140061497  jz      loc_140061BCB
0x14006149d  xor     ebx, ebx
0x14006149f  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400614a3  lea     rcx, [rbp+370h+String]
0x1400614aa  mov     rax, r13
0x1400614ad  inc     rax
0x1400614b0  cmp     [rcx+rax*2], bx
0x1400614b4  jnz     short loc_1400614AD
0x1400614b6  mov     ebx, cs:?g_processIdExcel@@3KA; ulong g_processIdExcel
0x1400614bc  lea     r8, [rbp+370h+String]
0x1400614c3  cdqe
0x1400614c5  mov     edx, 9; int
0x1400614ca  mov     ecx, ebx; int
0x1400614cc  lea     r8, [r8+rax*2]; wchar_t *
0x1400614d0  call    ?SzHexFromL@@YAXJHPEA_W@Z; SzHexFromL(long,int,wchar_t *)
0x1400614d5  mov     rax, r13
0x1400614d8  lea     r8, [rbp+370h+Name]
0x1400614df  xor     r13d, r13d
0x1400614e2  inc     rax
0x1400614e5  cmp     [r8+rax*2], r13w
0x1400614ea  jnz     short loc_1400614E2
0x1400614ec  cdqe
0x1400614ee  lea     r8, [rbp+370h+Name]
0x1400614f5  mov     edx, 9; int
0x1400614fa  mov     ecx, ebx; int
0x1400614fc  lea     r8, [r8+rax*2]; wchar_t *
0x140061500  call    ?SzHexFromL@@YAXJHPEA_W@Z; SzHexFromL(long,int,wchar_t *)
0x140061505  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140061509  lea     r8, [rbp+370h+String]
0x140061510  inc     rbx
0x140061513  cmp     [r8+rbx*2], r13w
0x140061518  jnz     short loc_140061510
0x14006151a  lea     rcx, [rbp+370h+String]; lpString
0x140061521  call    cs:__imp_GlobalAddAtomW
0x140061527  movzx   r13d, ax
0x14006152b  xor     eax, eax
0x14006152d  test    r13w, r13w
0x140061531  jz      loc_140061BA6
0x140061537  lea     rcx, ?szMergeInstanceEventAcceptSuffix@@3PA_WA; "_Accept"
0x14006153e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140061542  inc     rdx; int
0x140061545  cmp     [rcx+rdx*2], ax
0x140061549  jnz     short loc_140061542
0x14006154b  mov     r9d, 32h ; '2'; int
0x140061551  lea     r8, [rbp+370h+String]; wchar_t *
0x140061558  call    ?FAppendRgchToSz@@YA_NPEB_WHPEA_WH@Z; FAppendRgchToSz(wchar_t const *,int,wchar_t *,int)
0x14006155d  lea     r9, [rbp+370h+String]; lpName
0x140061564  xor     r8d, r8d; bInitialState
0x140061567  xor     edx, edx; bManualReset
0x140061569  xor     ecx, ecx; lpEventAttributes
0x14006156b  call    cs:__imp_CreateEventW
0x140061571  mov     [rbp-60h], rax
0x14006157a  movsxd  rax, ebx
0x14006157d  add     rax, rax
0x140061580  cmp     rax, 64h ; 'd'
0x140061584  jnb     loc_140061C32
0x14006158a  xor     ebx, ebx
0x14006158c  lea     rcx, ?szMergeInstanceEventRejectSuffix@@3PA_WA; "_Reject"
0x140061593  mov     [rbp+rax+370h+String], bx
0x14006159b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14006159f  inc     rdx; int
0x1400615a2  cmp     [rcx+rdx*2], bx
0x1400615a6  jnz     short loc_14006159F
0x1400615a8  mov     r9d, 32h ; '2'; int
0x1400615ae  lea     r8, [rbp+370h+String]; wchar_t *
0x1400615b5  call    ?FAppendRgchToSz@@YA_NPEB_WHPEA_WH@Z; FAppendRgchToSz(wchar_t const *,int,wchar_t *,int)
0x1400615ba  lea     r9, [rbp+370h+String]; lpName
0x1400615c1  xor     r8d, r8d; bInitialState
0x1400615c4  xor     edx, edx; bManualReset
0x1400615c6  xor     ecx, ecx; lpEventAttributes
0x1400615c8  call    cs:__imp_CreateEventW
0x1400615ce  mov     [rbp+370h+hObject+8], rax
0x1400615d2  cmp     [rbp+370h+hObject], rbx
0x1400615d6  jz      loc_140061B92
0x1400615dc  nop     dword ptr [rax+00h]
0x1400615e0  test    rax, rax
0x1400615e3  jz      loc_140061B92
0x1400615e9  test    r14, r14
0x1400615ec  jz      short loc_1400615FD
0x1400615ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400615f2  inc     rax
0x1400615f5  cmp     [r14+rax], bl
0x1400615f9  jnz     short loc_1400615F2
0x1400615fb  jmp     short loc_140061600
0x1400615fd  mov     rax, rbx
0x140061600  lea     edi, [rax+1]
0x140061603  test    r12, r12
0x140061606  jz      short loc_140061618
0x140061608  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006160c  inc     rax
0x14006160f  cmp     [r12+rax*2], bx
0x140061614  jnz     short loc_14006160C
0x140061616  jmp     short loc_14006161B
0x140061618  mov     rax, rbx
0x14006161b  xor     edx, edx; bool
0x14006161d  lea     rcx, [rbp+370h+var_388]; struct MaxPathHolder *
0x140061621  lea     ebx, ds:2[rax*2]
0x140061628  call    ?FCurDirWithMph@@YA_NPEAVMaxPathHolder@@_N@Z; FCurDirWithMph(MaxPathHolder *,bool)
0x14006162d  mov     rax, [rbp+370h+var_388]
0x140061631  lea     rdx, [rbp+370h+var_3C0]
0x140061635  mov     r8d, 4
0x14006163b  movzx   ecx, word ptr [rax]
0x14006163e  lea     r12d, ds:4[rcx*2]
0x140061646  mov     ecx, 8022h
0x14006164b  call    cs:__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x140061651  xor     ecx, ecx
0x140061653  test    eax, eax
0x140061655  jz      loc_140061C2A
0x14006165b  xor     r9d, r9d; dwMaximumSizeHigh
0x140061660  lea     eax, [r12+rbx]
0x140061664  lea     rcx, [rbp+370h+Name]
0x14006166b  add     eax, edi
0x14006166d  mov     [rsp+470h+lpName], rcx; lpName
0x140061672  xor     edx, edx; lpFileMappingAttributes
0x140061674  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x140061678  mov     [rsp+470h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x14006167c  lea     r8d, [r9+4]; flProtect
0x140061680  call    cs:__imp_CreateFileMappingW
0x140061686  mov     r8d, 4
0x140061690  lea     rdx, [rbp+370h+var_3C0]
0x140061694  mov     ecx, 8022h
0x140061699  mov     [rbp+370h+var_3F0], rax
0x14006169d  mov     rsi, rax
0x1400616a0  call    cs:__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoMNOReleaseSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x1400616a6  xor     eax, eax
0x1400616a8  test    rsi, rsi
0x1400616ab  jz      loc_140061B8F
0x1400616b1  xor     r9d, r9d; dwFileOffsetLow
0x1400616b4  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x1400616b9  xor     r8d, r8d; dwFileOffsetHigh
0x1400616bc  lea     edx, [rax+2]; dwDesiredAccess
0x1400616bf  mov     rcx, rsi; hFileMappingObject
0x1400616c2  call    cs:__imp_MapViewOfFile
0x1400616c8  mov     rsi, rax
0x1400616cb  xor     eax, eax
0x1400616cd  test    rsi, rsi
0x1400616d0  jz      loc_140061B8B
0x1400616d6  movsxd  rdi, edi
  ... truncated ...
```

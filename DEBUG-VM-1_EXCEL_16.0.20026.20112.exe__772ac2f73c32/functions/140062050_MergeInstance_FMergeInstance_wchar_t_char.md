# MergeInstance::FMergeInstance(wchar_t *,char *)

- ea: `0x140062050`
- end: `0x140062af8`
- name: `?FMergeInstance@MergeInstance@@SAHPEA_WPEAD@Z`
- size: `2728`
- prototype: `__int64 __fastcall(wchar_t *, char *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140047920`

## callees

- `0x140046a90`
- `0x1400504d8`
- `0x140052c80`
- `0x140052d40`
- `0x1400559d0`
- `0x1400597c4`
- `0x140062050`
- `0x140069c40`
- `0x140075f40`
- `0x1400768c0`
- `0x1400769a0`
- `0x140078660`
- `0x14009ab40`
- `0x1400a1db0`
- `0x140162cd0`
- `0x140308ad0`
- `0x14030a80c`
- `0x1408c08d0`
- `0x1408ce4f0`
- `0x1408d2b50`
- `0x1408d2bb0`
- `0x1408d6570`
- `0x140f0dc60`
- `0x1418e75d8`
- `0x142727790`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400627a4`
- `KERNEL32!CloseHandle` at `0x1400627b5`
- `KERNEL32!CloseHandle` at `0x140062a80`
- `KERNEL32!CloseHandle` at `0x140062a94`
- `KERNEL32!CloseHandle` at `0x140062aa5`
- `KERNEL32!CloseHandle` at `0x1400627a4`
- `KERNEL32!CloseHandle` at `0x1400627b5`
- `KERNEL32!CloseHandle` at `0x140062a80`
- `KERNEL32!CloseHandle` at `0x140062a94`
- `KERNEL32!CloseHandle` at `0x140062aa5`
- `KERNEL32!Sleep` at `0x1400622f2`
- `KERNEL32!Sleep` at `0x1400622f2`
- `KERNEL32!GetLastError` at `0x140062754`
- `KERNEL32!GetLastError` at `0x140062840`
- `KERNEL32!GetLastError` at `0x140062754`
- `KERNEL32!GetLastError` at `0x140062840`
- `KERNEL32!CreateEventW` at `0x140062420`
- `KERNEL32!CreateEventW` at `0x140062479`
- `KERNEL32!CreateEventW` at `0x140062420`
- `KERNEL32!CreateEventW` at `0x140062479`
- `KERNEL32!MapViewOfFile` at `0x140062580`
- `KERNEL32!MapViewOfFile` at `0x140062580`
- `KERNEL32!GetCurrentProcessId` at `0x140062701`
- `KERNEL32!GetCurrentProcessId` at `0x140062701`
- `KERNEL32!GetCurrentProcess` at `0x140062677`
- `KERNEL32!GetCurrentProcess` at `0x140062677`
- `KERNEL32!GetCommandLineW` at `0x1400621b9`
- `KERNEL32!GetCommandLineW` at `0x1400621b9`
- `KERNEL32!GlobalAddAtomW` at `0x1400623d1`
- `KERNEL32!GlobalAddAtomW` at `0x1400625e0`
- `KERNEL32!GlobalAddAtomW` at `0x1400623d1`
- `KERNEL32!GlobalAddAtomW` at `0x1400625e0`
- `KERNEL32!OpenProcess` at `0x140062744`
- `KERNEL32!OpenProcess` at `0x140062744`
- `KERNEL32!GlobalDeleteAtom` at `0x140062a60`
- `KERNEL32!GlobalDeleteAtom` at `0x140062a6e`
- `KERNEL32!GlobalDeleteAtom` at `0x140062a60`
- `KERNEL32!GlobalDeleteAtom` at `0x140062a6e`
- `KERNEL32!CreateFileMappingW` at `0x140062533`
- `KERNEL32!CreateFileMappingW` at `0x140062533`
- `KERNEL32!UnmapViewOfFile` at `0x1400625cf`
- `KERNEL32!UnmapViewOfFile` at `0x1400625cf`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1400626f5`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1400626f5`
- `KERNEL32!Process32FirstW` at `0x140062710`
- `KERNEL32!Process32FirstW` at `0x140062710`
- `KERNEL32!Process32NextW` at `0x140062724`
- `KERNEL32!Process32NextW` at `0x140062724`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1400628c0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1400628c0`
- `USER32!GetWindowThreadProcessId` at `0x1400626c8`
- `USER32!GetWindowThreadProcessId` at `0x1400626c8`
- `USER32!PostMessageW` at `0x1400627e7`
- `USER32!PostMessageW` at `0x1400627e7`
- `USER32!FindWindowExW` at `0x1400626a2`
- `USER32!FindWindowExW` at `0x1400626a2`
- `USER32!AllowSetForegroundWindow` at `0x1400626d2`
- `USER32!AllowSetForegroundWindow` at `0x1400626d2`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140062a40`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140062a40`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140062284`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140062284`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140062821`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140062a33`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140062821`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140062a33`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x140062880`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x140062880`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140062955`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140062975`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140062999`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1400629b8`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1400629d9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1400629f8`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140062955`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140062975`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140062999`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1400629b8`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1400629d9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1400629f8`
- `Mso20Win32Client!__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x140062500`
- `Mso20Win32Client!__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x140062500`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x140062897`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x140062897`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140062920`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140062920`
- `Mso20Win32Client!__imp_MsoWaitForMultipleObjects` at `0x140062809`
- `Mso20Win32Client!__imp_MsoWaitForMultipleObjects` at `0x140062809`
- `Mso20Win32Client!__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x14006254f`
- `Mso20Win32Client!__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x14006254f`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x14006264d`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x14006264d`
- `Mso20Win32Client!__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z` at `0x140062263`
- `Mso20Win32Client!__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z` at `0x140062263`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140062685`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140062793`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140062685`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140062793`

## string_xrefs

- `0x140062980`: `Created`
- `0x140062763`: `OpenProcess failed during FSkipPostMergeInstanceMessage. Error: %d`

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
  LPCWSTR lpName; // [rsp+28h] [rbp-D8h]
  ATOM v56; // [rsp+50h] [rbp-B0h]
  unsigned int v57; // [rsp+54h] [rbp-ACh] BYREF
  int v58; // [rsp+58h] [rbp-A8h]
  unsigned int v59; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE v60[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v61[2]; // [rsp+62h] [rbp-9Eh] BYREF
  _BYTE v62[4]; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwProcessId; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v64; // [rsp+6Ch] [rbp-94h] BYREF
  __int16 v65; // [rsp+70h] [rbp-90h] BYREF
  char v66; // [rsp+72h] [rbp-8Eh]
  void *Src; // [rsp+78h] [rbp-88h]
  HANDLE FileMappingW; // [rsp+80h] [rbp-80h]
  _QWORD v69[2]; // [rsp+88h] [rbp-78h] BYREF
  int v70; // [rsp+98h] [rbp-68h] BYREF
  HANDLE hObject[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES *v72; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v73[8]; // [rsp+B8h] [rbp-48h] BYREF
  void **v74; // [rsp+C0h] [rbp-40h] BYREF
  const char *v75; // [rsp+C8h] [rbp-38h]
  _BYTE v76[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v77[8]; // [rsp+E0h] [rbp-20h] BYREF
  void *v78[5]; // [rsp+E8h] [rbp-18h] BYREF
  PROCESSENTRY32W pe; // [rsp+110h] [rbp+10h] BYREF
  WCHAR String[31]; // [rsp+350h] [rbp+250h] BYREF
  __int128 v81; // [rsp+38Eh] [rbp+28Eh]
  __int128 v82; // [rsp+39Eh] [rbp+29Eh]
  int v83; // [rsp+3AEh] [rbp+2AEh]
  __int16 v84; // [rsp+3B2h] [rbp+2B2h]
  WCHAR Name[37]; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int128 v86; // [rsp+40Ah] [rbp+30Ah]
  __int64 v87; // [rsp+41Ah] [rbp+31Ah]
  __int16 v88; // [rsp+422h] [rbp+322h]

  v59 = 5;
  dwProcessId = 0;
  v4 = 0;
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v78,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  v5 = 0;
  v6 = 0;
  *(_OWORD *)hObject = 0;
  v7 = 0;
  v83 = 0;
  wcscpy(String, L"Local\\ExcelMergeInstanceEvent_");
  v84 = 0;
  v81 = 0;
  v82 = 0;
  v70 = 1;
  wcscpy(Name, L"Local\\ExcelMergeInstanceFileMapping_");
  v86 = 0;
  v72 = 0;
  v58 = 0;
  v87 = 0;
  v88 = 0;
  CommandLineW = GetCommandLineW();
  Src = CommandLineW;
  if ( (unsigned int)FOsrc()
    || (unsigned int)FCmdLineOption(21, 22, a1, a2)
    || (unsigned int)FLoadCmdLineWithMph(a1, a2, &v59, 1, v78, v77, &v70) )
  {
    goto LABEL_91;
  }
  v57 = 0;
  v9 = MsoFOpenCreateEvent(&hEvent, "XL16RunningEvent", 1, 0, (int *)&v57, 0, 0x8022u) == 0;
  v10 = 0;
  if ( !v9 )
    v10 = v57;
  if ( v10 )
    goto LABEL_91;
  Dw = MsoDwRegGetDw((const struct _msoreg *)&OrapiData::Excel::c_msoridExcelDisableMergeInstance);
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
  FCurDirWithMph((struct MaxPathHolder *)v78, 0);
  v27 = 2 * *(unsigned __int16 *)v78[0] + 4;
  if ( !MsoFMNOResolveSecurity(0x8022u, &v72, 4) )
  {
    v5 = 0;
    goto LABEL_84;
  }
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, v24 + v27 + v26, Name);
  v6 = FileMappingW;
  MsoMNOReleaseSecurity(0x8022u, &v72, 4);
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
  BltB(v78[0], &v28[v24 + (__int64)v26], v27);
  UnmapViewOfFile(v28);
  v56 = GlobalAddAtomW(Name);
  v5 = v56;
  if ( !v56 )
  {
    v6 = FileMappingW;
    goto LABEL_84;
  }
  v29 = 0;
  LastError = 0;
  LODWORD(Src) = 1;
  v59 = 0;
  if ( hEvent )
  {
    v75 = 0;
    v74 = &Mso::Timing::TStopwatch<std::chrono::steady_clock>::`vftable';
    std::chrono::steady_clock::now(v76);
    v74 = &Mso::Timing::TStopwatch<std::chrono::steady_clock>::`vftable';
    v76[8] = 1;
    LODWORD(Src) = MsoWaitForSingleObject(hEvent, 20000);
    v59 = *(_DWORD *)((__int64 (__fastcall *)(void ***, _BYTE *))v74[5])(&v74, v73);
  }
  v64 = 0;
  CurrentProcess = (Mso::Security *)GetCurrentProcess();
  Mso::Security::HrGetProcessIL(CurrentProcess, &v64, v32);
  while ( 1 )
  {
    do
    {
      Window = FindWindowExW(HWND_MESSAGE, v4, L"XL16MERGE", 0);
      v4 = Window;
    }
    while ( Window == hWnd );
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
    v38 = v64;
    v39 = OpenProcess(0x400u, 0, dwProcessId);
    if ( v39 )
    {
      v57 = 0;
      if ( (int)Mso::Security::HrGetProcessIL((Mso::Security *)v39, &v57, v40) < 0 )
      {
        CloseHandle(v39);
        goto LABEL_60;
      }
      v41 = v57 < v38;
      CloseHandle(v39);
      if ( !v41 )
        goto LABEL_60;
    }
    else
    {
      LODWORD(lpName) = GetLastError();
      XlsDiag::SendTraceTag(
        557176143,
        141,
        15,
        4,
        L"OpenProcess failed during FSkipPostMergeInstanceMessage. Error: %d",
        lpName);
LABEL_60:
      if ( PostMessageW(v4, 0x420u, th32ParentProcessID, v56 | (unsigned __int64)(v19 << 16)) )
      {
        LastError = 0;
        v42 = MsoWaitForMultipleObjects(2, hObject, 0, 5000);
        if ( !v42 )
        {
          sub_140F0DC60(v4);
          if ( !byte_144087DF0 )
            _invoke_watson(0, 0, 0, 0, 0);
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          HIBYTE(word_144087DD9) = 1;
          if ( *(_BYTE *)(*(_QWORD *)ThreadLocalStoragePointer + 313LL)
            && !MsoFIsRunningRestricted()
            && byte_14418DCDA != 1 )
          {
            LOBYTE(v44) = 1;
            Mso::Telemetry::UngracefulExit::OverrideSessionFlag(4, v44);
            byte_14418DCDA = 1;
          }
          v45 = 1;
          v58 = 1;
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
  v45 = v58;
  if ( !LastError )
    LastError = -2147319765;
LABEL_76:
  v60[1] = 0;
  v65 = 2;
  v66 = 1;
  v61[1] = 0;
  v62[1] = 0;
  BYTE1(v57) = 0;
  Mso::Telemetry::EventFlags::EventFlags(v73, &v57, v62, v61, &v65, v60);
  v74 = (void **)&off_1438064C0;
  v75 = "MergeInstances";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v69,
    (const struct Mso::Telemetry::EventName *)&v74,
    (const struct Mso::Telemetry::EventFlags *)v73);
  if ( !v45 )
  {
    v46 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v69);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v46, "LastError", LastError, 4);
  }
  v47 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v69);
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v47, "Created", 0, 4);
  v48 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v69);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v48, "FoundInstance", v29, 4);
  v49 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v69);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v49, "WaitEvent", (unsigned int)Src, 4);
  v50 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v69);
  LOBYTE(v51) = v45;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v50, "Merge", v51, 4);
  v52 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v69);
  Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v52, "WaitForSingleObjectDurationMs", v59, 4);
  if ( v69[0] )
    Mso::Telemetry::SetActivityResultHr((Mso::Telemetry *)v69, 0, 557176136, v53);
  else
    MsoShipAssertTagProc(562177664);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v69);
LABEL_64:
  v6 = FileMappingW;
  v5 = v56;
LABEL_84:
  if ( (_WORD)v19 )
    GlobalDeleteAtom(v19);
LABEL_86:
  if ( v5 )
    GlobalDeleteAtom(v5);
  if ( v6 )
    CloseHandle(v6);
  v7 = v58;
LABEL_91:
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v78);
  return v7;
}

```

## disassembly

```asm
0x140062050  mov     [rsp-8+arg_10], rbx
0x140062056  push    rbp
0x140062057  push    rsi
0x140062058  push    rdi
0x140062059  push    r12
0x14006205b  push    r13
0x14006205d  push    r14
0x14006205f  push    r15
0x140062061  lea     rbp, [rsp-340h]
0x140062069  sub     rsp, 440h
0x140062070  mov     rax, cs:__security_cookie
0x140062077  xor     rax, rsp
0x14006207a  mov     [rbp+370h+var_40], rax
0x140062081  mov     r14, rdx
0x140062084  mov     [rsp+470h+var_414], 5
0x14006208c  mov     rbx, rcx
0x14006208f  lea     rdx, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; struct IMemHeap *
0x140062096  xor     r12d, r12d
0x140062099  lea     rcx, [rbp+370h+var_388]; this
0x14006209d  xor     r9d, r9d; bool
0x1400620a0  mov     [rsp+470h+dwProcessId], r12d
0x1400620a5  mov     r8d, 103h; int
0x1400620ab  mov     r15d, r12d
0x1400620ae  call    ??0MaxPathHolder@@QEAA@PEAVIMemHeap@@H_N@Z; MaxPathHolder::MaxPathHolder(IMemHeap *,int,bool)
0x1400620b3  mov     eax, dword ptr cs:aLocalExcelmerg_0+38h; "t_"
0x1400620b9  xorps   xmm0, xmm0
0x1400620bc  movups  xmm1, xmmword ptr cs:aLocalExcelmerg_0+10h; "celMergeInstanceEvent_"
0x1400620c3  mov     [rbp+370h+var_E8], eax
0x1400620c9  movzx   edi, r12w
0x1400620cd  movzx   eax, word ptr cs:aLocalExcelmerg_0+3Ch; ""
0x1400620d4  mov     esi, r12d
0x1400620d7  movdqu  xmmword ptr [rbp+370h+hObject], xmm0
0x1400620dc  mov     [rbp+370h+var_E4], ax
0x1400620e3  xor     eax, eax
0x1400620e5  movups  xmm0, xmmword ptr cs:aLocalExcelmerg_0; "Local\\ExcelMergeInstanceEvent_"
0x1400620ec  mov     r13d, r12d
0x1400620ef  mov     [rbp+370h+var_C2], eax
0x1400620f5  movaps  [rbp+370h+var_110], xmm1
0x1400620fc  movaps  xmm1, xmmword ptr cs:aLocalExcelmerg+10h; "celMergeInstanceFileMapping_"
0x140062103  movaps  xmmword ptr [rbp+370h+String], xmm0
0x14006210a  movups  xmm0, xmmword ptr cs:aLocalExcelmerg_0+20h; "InstanceEvent_"
0x140062111  mov     [rbp+370h+var_BE], ax
0x140062118  movzx   eax, word ptr cs:aLocalExcelmerg+48h; ""
0x14006211f  movaps  [rbp+370h+var_100], xmm0
0x140062126  movsd   xmm0, qword ptr cs:aLocalExcelmerg_0+30h; "Event_"
0x14006212e  movsd   [rbp+370h+var_F0], xmm0
0x140062136  xorps   xmm0, xmm0
0x140062139  movups  [rbp+370h+var_E2], xmm0
0x140062140  mov     [rbp+370h+var_68], ax
0x140062147  xor     eax, eax
0x140062149  movups  [rbp+370h+var_D2], xmm0
0x140062150  mov     [rbp+370h+var_3D8], 1
0x140062157  movaps  xmm0, xmmword ptr cs:aLocalExcelmerg; "Local\\ExcelMergeInstanceFileMapping_"
0x14006215e  movaps  xmmword ptr [rbp+370h+Name], xmm0
0x140062165  movaps  xmm0, xmmword ptr cs:aLocalExcelmerg+20h; "InstanceFileMapping_"
0x14006216c  movaps  [rbp+370h+var_90], xmm0
0x140062173  movsd   xmm0, qword ptr cs:aLocalExcelmerg+40h; "ing_"
0x14006217b  movsd   [rbp+370h+var_70], xmm0
0x140062183  xorps   xmm0, xmm0
0x140062186  movaps  [rbp+370h+var_A0], xmm1
0x14006218d  movaps  xmm1, xmmword ptr cs:aLocalExcelmerg+30h; "FileMapping_"
0x140062194  movups  [rbp+370h+var_66], xmm0
0x14006219b  mov     [rbp+370h+var_3C0], r12
0x14006219f  mov     [rsp+470h+var_418], r12d
0x1400621a4  movaps  [rbp+370h+var_80], xmm1
0x1400621ab  mov     [rbp+370h+var_56], rax
0x1400621b2  mov     [rbp+370h+var_4E], ax
0x1400621b9  call    cs:__imp_GetCommandLineW
0x1400621bf  mov     r12, rax
0x1400621c2  mov     [rsp+470h+Src], rax
0x1400621c7  call    ?FOsrc@@YAHXZ; FOsrc(void)
0x1400621cc  test    eax, eax
0x1400621ce  jnz     loc_140062A8B
0x1400621d4  mov     r9, r14; char *
0x1400621d7  lea     edx, [rsi+16h]; int
0x1400621da  mov     r8, rbx; wchar_t *
0x1400621dd  lea     ecx, [rsi+15h]; int
0x1400621e0  call    ?FCmdLineOption@@YAHHHPEA_WPEAD@Z; FCmdLineOption(int,int,wchar_t *,char *)
0x1400621e5  xor     ecx, ecx
0x1400621e7  test    eax, eax
0x1400621e9  jnz     loc_140062A8B
0x1400621ef  mov     [rsp+470h+var_428], ecx
0x1400621f4  lea     rax, [rbp+370h+var_3D8]
0x1400621f8  mov     [rsp+470h+var_430], rcx
0x1400621fd  lea     r9d, [rsi+1]
0x140062201  mov     [rsp+470h+var_440], rax
0x140062206  lea     r8, [rsp+470h+var_414]
0x14006220b  lea     rax, [rbp+370h+var_390]
0x14006220f  mov     rdx, r14
0x140062212  mov     [rsp+470h+lpName], rax
0x140062217  mov     rcx, rbx
0x14006221a  lea     rax, [rbp+370h+var_388]
0x14006221e  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax
0x140062223  call    ?FLoadCmdLineWithMph@@YAHPEA_WPEADPEAHW4CmdLineFlags@@PEAVMaxPathHolder@@2200H@Z; FLoadCmdLineWithMph(wchar_t *,char *,int *,CmdLineFlags,MaxPathHolder *,int *,int *,wchar_t *,wchar_t *,int)
0x140062228  xor     ecx, ecx
0x14006222a  test    eax, eax
0x14006222c  jnz     loc_140062A8B
0x140062232  mov     dword ptr [rsp+470h+var_440], 8022h
0x14006223b  lea     rax, [rsp+470h+var_41C]
0x140062240  mov     [rsp+470h+lpName], rcx
0x140062245  lea     r8d, [rsi+1]
0x140062249  mov     [rsp+470h+var_41C], ecx
0x14006224d  lea     rdx, aXl16runningeve; "XL16RunningEvent"
0x140062254  lea     rcx, hEvent
0x14006225b  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax
0x140062260  xor     r9d, r9d
0x140062263  call    cs:__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z; MsoFOpenCreateEvent(void * *,char const *,int,int,int *,_SECURITY_ATTRIBUTES *,ulong)
0x140062269  xor     ecx, ecx
0x14006226b  test    eax, eax
0x14006226d  mov     eax, ecx
0x14006226f  jz      short loc_140062275
0x140062271  mov     eax, [rsp+470h+var_41C]
0x140062275  test    eax, eax
0x140062277  jnz     loc_140062A8B
0x14006227d  lea     rcx, ?c_msoridExcelDisableMergeInstance@Excel@OrapiData@@3U_msoreg@@B; _msoreg const OrapiData::Excel::c_msoridExcelDisableMergeInstance
0x140062284  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x14006228a  mov     ecx, 2
0x14006228f  cmp     eax, ecx
0x140062291  jz      loc_140062A8B
0x140062297  test    eax, eax
0x140062299  jz      short loc_1400622B5
0x14006229b  lea     r8, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; struct IMemHeap *
0x1400622a2  mov     rdx, r14; char *
0x1400622a5  mov     rcx, rbx; Src
0x1400622a8  call    ?FFilePresent@DelayedMergeInstance@@SA_NPEB_WPEBDPEAVIMemHeap@@@Z; DelayedMergeInstance::FFilePresent(wchar_t const *,char const *,IMemHeap *)
0x1400622ad  test    al, al
0x1400622af  jz      loc_140062A8B
0x1400622b5  mov     edx, 29h ; ')'; int
0x1400622ba  mov     r9, r14; char *
0x1400622bd  mov     r8, rbx; wchar_t *
0x1400622c0  lea     ecx, [rdx-1]; int
0x1400622c3  call    ?FCmdLineOption@@YAHHHPEA_WPEAD@Z; FCmdLineOption(int,int,wchar_t *,char *)
0x1400622c8  xor     ebx, ebx
0x1400622ca  test    eax, eax
0x1400622cc  jnz     loc_140062A8B
0x1400622d2  lea     ecx, [rbx+12h]; int
0x1400622d5  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x1400622da  test    ax, ax
0x1400622dd  jns     short loc_14006234B
0x1400622df  lea     ecx, [rbx+11h]; int
0x1400622e3  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x1400622e8  test    ax, ax
0x1400622eb  js      short loc_14006234B
0x1400622ed  mov     ecx, 3E8h; dwMilliseconds
0x1400622f2  call    cs:__imp_Sleep
0x1400622f8  lea     ecx, [rbx+12h]; int
0x140062300  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x140062305  test    ax, ax
0x140062308  jns     short loc_14006234B
0x14006230a  lea     ecx, [rbx+11h]; int
0x14006230d  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x140062312  test    ax, ax
0x140062315  js      short loc_14006234B
0x140062317  mov     ebx, cs:?fForceDlgUp@@3HA; int fForceDlgUp
0x14006231d  xor     edx, edx; wchar_t *
0x14006231f  mov     ecx, 0A002Ch; int
0x140062324  mov     cs:?fForceDlgUp@@3HA, 1; int fForceDlgUp
0x14006232e  call    ?NoYesAlert@@YAHHPEB_W@Z; NoYesAlert(int,wchar_t const *)
0x140062333  mov     ?fForceDlgUp@@3HA, ebx; int fForceDlgUp
0x140062340  cmp     eax, 6
0x140062343  jz      loc_140062A8B
0x140062349  xor     ebx, ebx
0x14006234b  or      r13, 0FFFFFFFFFFFFFFFFh
0x14006234f  lea     rcx, [rbp+370h+String]
0x140062356  mov     rax, r13
0x140062359  inc     rax
0x140062360  cmp     [rcx+rax*2], bx
0x140062364  jnz     short loc_140062359
0x140062366  mov     ebx, cs:?g_processIdExcel@@3KA; ulong g_processIdExcel
0x14006236c  lea     r8, [rbp+370h+String]
0x140062373  cdqe
0x140062375  mov     edx, 9; int
0x14006237a  mov     ecx, ebx; int
0x14006237c  lea     r8, [r8+rax*2]; wchar_t *
0x140062380  call    ?SzHexFromL@@YAXJHPEA_W@Z; SzHexFromL(long,int,wchar_t *)
0x140062385  mov     rax, r13
0x140062388  lea     r8, [rbp+370h+Name]
0x14006238f  xor     r13d, r13d
0x140062392  inc     rax
0x140062395  cmp     [r8+rax*2], r13w
0x14006239a  jnz     short loc_140062392
0x14006239c  cdqe
0x14006239e  lea     r8, [rbp+370h+Name]
0x1400623a5  mov     edx, 9; int
0x1400623aa  mov     ecx, ebx; int
0x1400623ac  lea     r8, [r8+rax*2]; wchar_t *
0x1400623b0  call    ?SzHexFromL@@YAXJHPEA_W@Z; SzHexFromL(long,int,wchar_t *)
0x1400623b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400623b9  lea     r8, [rbp+370h+String]
0x1400623c0  inc     rbx
0x1400623c3  cmp     [r8+rbx*2], r13w
0x1400623c8  jnz     short loc_1400623C0
0x1400623ca  lea     rcx, [rbp+370h+String]; lpString
0x1400623d1  call    cs:__imp_GlobalAddAtomW
0x1400623d7  movzx   r13d, ax
0x1400623de  xor     eax, eax
0x1400623e0  test    r13w, r13w
0x1400623e4  jz      loc_140062A66
0x1400623ea  lea     rcx, ?szMergeInstanceEventAcceptSuffix@@3PA_WA; "_Accept"
0x1400623f1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400623f5  inc     rdx; int
0x1400623f8  cmp     [rcx+rdx*2], ax
0x1400623fc  jnz     short loc_1400623F5
0x1400623fe  mov     r9d, 32h ; '2'; int
0x140062404  lea     r8, [rbp+370h+String]; wchar_t *
0x14006240b  call    ?FAppendRgchToSz@@YA_NPEB_WHPEA_WH@Z; FAppendRgchToSz(wchar_t const *,int,wchar_t *,int)
0x140062410  lea     r9, [rbp+370h+String]; lpName
0x140062419  xor     r8d, r8d; bInitialState
0x14006241c  xor     edx, edx; bManualReset
0x14006241e  xor     ecx, ecx; lpEventAttributes
0x140062420  call    cs:__imp_CreateEventW
0x140062426  mov     [rbp-60h], rax
0x14006242b  movsxd  rax, ebx
0x14006242e  add     rax, rax
0x140062431  cmp     rax, 64h ; 'd'
0x140062435  jnb     loc_140062AF2
0x14006243b  xor     ebx, ebx
0x14006243d  lea     rcx, ?szMergeInstanceEventRejectSuffix@@3PA_WA; "_Reject"
0x140062444  mov     [rbp+rax+370h+String], bx
0x14006244c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140062450  inc     rdx; int
0x140062453  cmp     [rcx+rdx*2], bx
0x140062457  jnz     short loc_140062450
0x140062459  mov     r9d, 32h ; '2'; int
0x14006245f  lea     r8, [rbp+370h+String]; wchar_t *
0x140062466  call    ?FAppendRgchToSz@@YA_NPEB_WHPEA_WH@Z; FAppendRgchToSz(wchar_t const *,int,wchar_t *,int)
0x14006246b  lea     r9, [rbp+370h+String]; lpName
0x140062472  xor     r8d, r8d; bInitialState
0x140062475  xor     edx, edx; bManualReset
0x140062477  xor     ecx, ecx; lpEventAttributes
0x140062479  call    cs:__imp_CreateEventW
0x14006247f  mov     [rbp+370h+hObject+8], rax
0x140062483  cmp     [rbp+370h+hObject], rbx
0x140062487  jz      loc_140062A52
0x14006248d  test    rax, rax
0x140062490  jz      loc_140062A52
0x140062496  test    r14, r14
0x140062499  jz      short loc_1400624AA
0x14006249b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006249f  inc     rax
0x1400624a2  cmp     [rax+r14], bl
0x1400624a6  jnz     short loc_14006249F
0x1400624a8  jmp     short loc_1400624AD
0x1400624aa  mov     rax, rbx
0x1400624ad  lea     edi, [rax+1]
0x1400624b0  test    r12, r12
0x1400624b3  jz      short loc_1400624C9
0x1400624b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400624b9  inc     rax
0x1400624c0  cmp     [r12+rax*2], bx
0x1400624c5  jnz     short loc_1400624B9
0x1400624c7  jmp     short loc_1400624CC
0x1400624c9  mov     rax, rbx
0x1400624cc  xor     edx, edx; bool
0x1400624ce  lea     rcx, [rbp+370h+var_388]; struct MaxPathHolder *
0x1400624d2  lea     ebx, ds:2[rax*2]
0x1400624d9  call    ?FCurDirWithMph@@YA_NPEAVMaxPathHolder@@_N@Z; FCurDirWithMph(MaxPathHolder *,bool)
0x1400624de  mov     rax, [rbp-18h]
0x1400624e6  lea     rdx, [rbp+370h+var_3C0]
0x1400624ea  mov     r8d, 4
0x1400624f0  movzx   ecx, word ptr [rax]
0x1400624f3  lea     r12d, ds:4[rcx*2]
0x1400624fb  mov     ecx, 8022h
0x140062500  call    cs:__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x140062506  xor     ecx, ecx
0x140062508  test    eax, eax
0x14006250a  jz      loc_140062AEA
0x140062510  xor     r9d, r9d; dwMaximumSizeHigh
0x140062513  lea     eax, [r12+rbx]
0x140062517  lea     rcx, [rbp+370h+Name]
0x14006251e  add     eax, edi
0x140062520  mov     [rsp+470h+lpName], rcx; lpName
0x140062525  xor     edx, edx; lpFileMappingAttributes
0x140062527  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14006252b  mov     [rsp+470h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x14006252f  lea     r8d, [r9+4]; flProtect
0x140062533  call    cs:__imp_CreateFileMappingW
0x140062539  mov     r8d, 4
0x14006253f  lea     rdx, [rbp+370h+var_3C0]
0x140062543  mov     ecx, 8022h
0x140062548  mov     [rbp+370h+var_3F0], rax
0x14006254c  mov     rsi, rax
0x14006254f  call    cs:__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoMNOReleaseSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x140062555  xor     eax, eax
0x140062560  test    rsi, rsi
0x140062563  jz      loc_140062A4F
0x140062569  xor     r9d, r9d; dwFileOffsetLow
0x140062572  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x140062577  xor     r8d, r8d; dwFileOffsetHigh
0x14006257a  lea     edx, [rax+2]; dwDesiredAccess
0x14006257d  mov     rcx, rsi; hFileMappingObject
0x140062580  call    cs:__imp_MapViewOfFile
0x140062586  mov     rsi, rax
0x140062589  xor     eax, eax
0x14006258b  test    rsi, rsi
0x14006258e  jz      loc_140062A4B
0x140062594  movsxd  rdi, edi
0x140062597  mov     rdx, rsi; void *
0x14006259a  mov     r8, rdi; unsigned __int64
0x14006259d  mov     rcx, r14; Src
  ... truncated ...
```

# MergeInstance::FMergeInstance(wchar_t *,char *)

- ea: `0x140061200`
- end: `0x140061c98`
- name: `?FMergeInstance@MergeInstance@@SAHPEA_WPEAD@Z`
- size: `2712`
- prototype: `__int64 __fastcall(wchar_t *, char *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400472c0`

## callees

- `0x140046440`
- `0x14004fe38`
- `0x1400525e0`
- `0x1400526a0`
- `0x140055288`
- `0x140059090`
- `0x140061200`
- `0x1400692e0`
- `0x1400755c0`
- `0x140075f40`
- `0x140076020`
- `0x140077ce0`
- `0x14009a1e8`
- `0x1400a1250`
- `0x14020b1c0`
- `0x1402fd330`
- `0x14030fe90`
- `0x1408c5c00`
- `0x1408c6dc0`
- `0x1408cc4f0`
- `0x1408cc550`
- `0x1408cfed0`
- `0x140f0ef60`
- `0x141913f18`
- `0x14270f730`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140061944`
- `KERNEL32!CloseHandle` at `0x140061955`
- `KERNEL32!CloseHandle` at `0x140061c20`
- `KERNEL32!CloseHandle` at `0x140061c34`
- `KERNEL32!CloseHandle` at `0x140061c45`
- `KERNEL32!CloseHandle` at `0x140061944`
- `KERNEL32!CloseHandle` at `0x140061955`
- `KERNEL32!CloseHandle` at `0x140061c20`
- `KERNEL32!CloseHandle` at `0x140061c34`
- `KERNEL32!CloseHandle` at `0x140061c45`
- `KERNEL32!Sleep` at `0x1400614af`
- `KERNEL32!Sleep` at `0x1400614af`
- `KERNEL32!GetLastError` at `0x1400618f4`
- `KERNEL32!GetLastError` at `0x1400619e0`
- `KERNEL32!GetLastError` at `0x1400618f4`
- `KERNEL32!GetLastError` at `0x1400619e0`
- `KERNEL32!CreateEventW` at `0x1400615cb`
- `KERNEL32!CreateEventW` at `0x140061628`
- `KERNEL32!CreateEventW` at `0x1400615cb`
- `KERNEL32!CreateEventW` at `0x140061628`
- `KERNEL32!MapViewOfFile` at `0x140061722`
- `KERNEL32!MapViewOfFile` at `0x140061722`
- `KERNEL32!GetCurrentProcessId` at `0x1400618a1`
- `KERNEL32!GetCurrentProcessId` at `0x1400618a1`
- `KERNEL32!GetCurrentProcess` at `0x140061817`
- `KERNEL32!GetCurrentProcess` at `0x140061817`
- `KERNEL32!GetCommandLineW` at `0x14006136b`
- `KERNEL32!GetCommandLineW` at `0x14006136b`
- `KERNEL32!GlobalAddAtomW` at `0x140061581`
- `KERNEL32!GlobalAddAtomW` at `0x140061780`
- `KERNEL32!GlobalAddAtomW` at `0x140061581`
- `KERNEL32!GlobalAddAtomW` at `0x140061780`
- `KERNEL32!OpenProcess` at `0x1400618e4`
- `KERNEL32!OpenProcess` at `0x1400618e4`
- `KERNEL32!GlobalDeleteAtom` at `0x140061c00`
- `KERNEL32!GlobalDeleteAtom` at `0x140061c0e`
- `KERNEL32!GlobalDeleteAtom` at `0x140061c00`
- `KERNEL32!GlobalDeleteAtom` at `0x140061c0e`
- `KERNEL32!CreateFileMappingW` at `0x1400616e0`
- `KERNEL32!CreateFileMappingW` at `0x1400616e0`
- `KERNEL32!UnmapViewOfFile` at `0x140061771`
- `KERNEL32!UnmapViewOfFile` at `0x140061771`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x140061895`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x140061895`
- `KERNEL32!Process32FirstW` at `0x1400618b0`
- `KERNEL32!Process32FirstW` at `0x1400618b0`
- `KERNEL32!Process32NextW` at `0x1400618c4`
- `KERNEL32!Process32NextW` at `0x1400618c4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140061a60`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x140061a60`
- `USER32!GetWindowThreadProcessId` at `0x140061868`
- `USER32!GetWindowThreadProcessId` at `0x140061868`
- `USER32!PostMessageW` at `0x140061987`
- `USER32!PostMessageW` at `0x140061987`
- `USER32!FindWindowExW` at `0x140061842`
- `USER32!FindWindowExW` at `0x140061842`
- `USER32!AllowSetForegroundWindow` at `0x140061872`
- `USER32!AllowSetForegroundWindow` at `0x140061872`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140061be0`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140061be0`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140061441`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140061441`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400619c1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140061bd3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1400619c1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140061bd3`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x140061a20`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x140061a20`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061af5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b15`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b39`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b58`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b79`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b98`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061af5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b15`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b39`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b58`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b79`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140061b98`
- `Mso20Win32Client!__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x1400616ab`
- `Mso20Win32Client!__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x1400616ab`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x140061a37`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x140061a37`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140061ac0`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140061ac0`
- `Mso20Win32Client!__imp_MsoWaitForMultipleObjects` at `0x1400619a9`
- `Mso20Win32Client!__imp_MsoWaitForMultipleObjects` at `0x1400619a9`
- `Mso20Win32Client!__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x140061700`
- `Mso20Win32Client!__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z` at `0x140061700`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x1400617ed`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x1400617ed`
- `Mso20Win32Client!__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z` at `0x140061420`
- `Mso20Win32Client!__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z` at `0x140061420`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140061825`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140061933`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140061825`
- `Mso20Win32Client!__imp_?HrGetProcessIL@Security@Mso@@YAJPEAXPEAK@Z` at `0x140061933`

## string_xrefs

- `0x140061b20`: `Created`
- `0x140061903`: `OpenProcess failed during FSkipPostMergeInstanceMessage. Error: %d`

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
          sub_140F0EF60(v4);
          if ( !byte_144014A78 )
            _invoke_watson(0, 0, 0, 0, 0);
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          HIBYTE(word_144014A61) = 1;
          if ( *(_BYTE *)(*(_QWORD *)ThreadLocalStoragePointer + 313LL)
            && !MsoFIsRunningRestricted()
            && byte_144118D80 != 1 )
          {
            LOBYTE(v44) = 1;
            Mso::Telemetry::UngracefulExit::OverrideSessionFlag(4, v44);
            byte_144118D80 = 1;
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
  v74 = (void **)&off_1437A4C40;
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
0x140061200  mov     [rsp-8+arg_10], rbx
0x140061206  push    rbp
0x140061207  push    rsi
0x140061208  push    rdi
0x140061209  push    r12
0x14006120b  push    r13
0x14006120d  push    r14
0x14006120f  push    r15
0x140061211  lea     rbp, [rsp-340h]
0x140061219  sub     rsp, 440h
0x140061220  mov     rax, cs:__security_cookie
0x140061227  xor     rax, rsp
0x14006122a  mov     [rbp+370h+var_40], rax
0x140061231  mov     r14, rdx
0x140061236  mov     [rsp+470h+var_414], 5
0x14006123e  mov     rbx, rcx
0x140061241  lea     rdx, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; struct IMemHeap *
0x140061248  xor     r12d, r12d
0x14006124b  lea     rcx, [rbp+370h+var_388]; this
0x14006124f  xor     r9d, r9d; bool
0x140061252  mov     [rsp+470h+dwProcessId], r12d
0x140061257  mov     r8d, 103h; int
0x14006125d  mov     r15d, r12d
0x140061260  call    ??0MaxPathHolder@@QEAA@PEAVIMemHeap@@H_N@Z; MaxPathHolder::MaxPathHolder(IMemHeap *,int,bool)
0x140061265  mov     eax, dword ptr cs:aLocalExcelmerg_0+38h; "t_"
0x14006126b  xorps   xmm0, xmm0
0x14006126e  movups  xmm1, xmmword ptr cs:aLocalExcelmerg_0+10h; "celMergeInstanceEvent_"
0x140061275  mov     [rbp+370h+var_E8], eax
0x14006127b  movzx   edi, r12w
0x14006127f  movzx   eax, word ptr cs:aLocalExcelmerg_0+3Ch; ""
0x140061286  mov     esi, r12d
0x140061289  movdqu  xmmword ptr [rbp+370h+hObject], xmm0
0x14006128e  mov     [rbp+370h+var_E4], ax
0x140061295  xor     eax, eax
0x140061297  movups  xmm0, xmmword ptr cs:aLocalExcelmerg_0; "Local\\ExcelMergeInstanceEvent_"
0x14006129e  mov     r13d, r12d
0x1400612a1  mov     [rbp+370h+var_C2], eax
0x1400612a7  movaps  [rbp+370h+var_110], xmm1
0x1400612ae  movaps  xmm1, xmmword ptr cs:aLocalExcelmerg+10h; "celMergeInstanceFileMapping_"
0x1400612b5  movaps  xmmword ptr [rbp+370h+String], xmm0
0x1400612bc  movups  xmm0, xmmword ptr cs:aLocalExcelmerg_0+20h; "InstanceEvent_"
0x1400612c3  mov     [rbp+370h+var_BE], ax
0x1400612ca  movzx   eax, word ptr cs:aLocalExcelmerg+48h; ""
0x1400612d1  movaps  [rbp+370h+var_100], xmm0
0x1400612d8  movsd   xmm0, qword ptr cs:aLocalExcelmerg_0+30h; "Event_"
0x1400612e0  movsd   [rbp+370h+var_F0], xmm0
0x1400612e8  xorps   xmm0, xmm0
0x1400612eb  movups  [rbp+370h+var_E2], xmm0
0x1400612f2  mov     [rbp+370h+var_68], ax
0x1400612f9  xor     eax, eax
0x1400612fb  movups  [rbp+370h+var_D2], xmm0
0x140061302  mov     [rbp+370h+var_3D8], 1
0x140061309  movaps  xmm0, xmmword ptr cs:aLocalExcelmerg; "Local\\ExcelMergeInstanceFileMapping_"
0x140061310  movaps  xmmword ptr [rbp+370h+Name], xmm0
0x140061317  movaps  xmm0, xmmword ptr cs:aLocalExcelmerg+20h; "InstanceFileMapping_"
0x14006131e  movaps  [rbp+370h+var_90], xmm0
0x140061325  movsd   xmm0, qword ptr cs:aLocalExcelmerg+40h; "ing_"
0x14006132d  movsd   [rbp+370h+var_70], xmm0
0x140061335  xorps   xmm0, xmm0
0x140061338  movaps  [rbp+370h+var_A0], xmm1
0x14006133f  movaps  xmm1, xmmword ptr cs:aLocalExcelmerg+30h; "FileMapping_"
0x140061346  movups  [rbp+370h+var_66], xmm0
0x14006134d  mov     [rbp+370h+var_3C0], r12
0x140061351  mov     [rsp+470h+var_418], r12d
0x140061356  movaps  [rbp+370h+var_80], xmm1
0x14006135d  mov     [rbp+370h+var_56], rax
0x140061364  mov     [rbp+370h+var_4E], ax
0x14006136b  call    cs:__imp_GetCommandLineW
0x140061371  mov     r12, rax
0x140061374  mov     [rsp+470h+Src], rax
0x140061379  call    ?FOsrc@@YAHXZ; FOsrc(void)
0x14006137e  xchg    ax, ax
0x140061380  test    eax, eax
0x140061382  jnz     loc_140061C2B
0x140061388  mov     r9, r14; char *
0x14006138b  lea     edx, [rsi+16h]; int
0x14006138e  mov     r8, rbx; wchar_t *
0x140061391  lea     ecx, [rsi+15h]; int
0x140061394  call    ?FCmdLineOption@@YAHHHPEA_WPEAD@Z; FCmdLineOption(int,int,wchar_t *,char *)
0x140061399  xor     ecx, ecx
0x1400613a0  test    eax, eax
0x1400613a2  jnz     loc_140061C2B
0x1400613a8  mov     [rsp+470h+var_428], ecx
0x1400613b1  lea     rax, [rbp+370h+var_3D8]
0x1400613b5  mov     [rsp+470h+var_430], rcx
0x1400613ba  lea     r9d, [rsi+1]
0x1400613be  mov     [rsp+470h+var_440], rax
0x1400613c3  lea     r8, [rsp+470h+var_414]
0x1400613c8  lea     rax, [rbp+370h+var_390]
0x1400613cc  mov     rdx, r14
0x1400613cf  mov     [rsp+470h+lpName], rax
0x1400613d4  mov     rcx, rbx
0x1400613d7  lea     rax, [rbp+370h+var_388]
0x1400613db  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax
0x1400613e0  call    ?FLoadCmdLineWithMph@@YAHPEA_WPEADPEAHW4CmdLineFlags@@PEAVMaxPathHolder@@2200H@Z; FLoadCmdLineWithMph(wchar_t *,char *,int *,CmdLineFlags,MaxPathHolder *,int *,int *,wchar_t *,wchar_t *,int)
0x1400613e5  xor     ecx, ecx
0x1400613e7  test    eax, eax
0x1400613e9  jnz     loc_140061C2B
0x1400613ef  mov     dword ptr [rsp+470h+var_440], 8022h
0x1400613f8  lea     rax, [rsp+470h+var_41C]
0x1400613fd  mov     [rsp+470h+lpName], rcx
0x140061402  lea     r8d, [rsi+1]
0x140061406  mov     [rsp+470h+var_41C], ecx
0x14006140a  lea     rdx, aXl16runningeve; "XL16RunningEvent"
0x140061411  lea     rcx, hEvent
0x140061418  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax
0x14006141d  xor     r9d, r9d
0x140061420  call    cs:__imp_?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z; MsoFOpenCreateEvent(void * *,char const *,int,int,int *,_SECURITY_ATTRIBUTES *,ulong)
0x140061426  xor     ecx, ecx
0x140061428  test    eax, eax
0x14006142a  mov     eax, ecx
0x14006142c  jz      short loc_140061432
0x14006142e  mov     eax, [rsp+470h+var_41C]
0x140061432  test    eax, eax
0x140061434  jnz     loc_140061C2B
0x14006143a  lea     rcx, ?vmsoridExcelDisableMergeInstance@@3U_msoreg@@B; _msoreg const vmsoridExcelDisableMergeInstance
0x140061441  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x140061447  mov     ecx, 2
0x14006144c  cmp     eax, ecx
0x14006144e  jz      loc_140061C2B
0x140061454  test    eax, eax
0x140061456  jz      short loc_140061472
0x140061458  lea     r8, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; struct IMemHeap *
0x14006145f  mov     rdx, r14; char *
0x140061462  mov     rcx, rbx; Src
0x140061465  call    ?FFilePresent@DelayedMergeInstance@@SA_NPEB_WPEBDPEAVIMemHeap@@@Z; DelayedMergeInstance::FFilePresent(wchar_t const *,char const *,IMemHeap *)
0x14006146a  test    al, al
0x14006146c  jz      loc_140061C2B
0x140061472  mov     edx, 29h ; ')'; int
0x140061477  mov     r9, r14; char *
0x14006147a  mov     r8, rbx; wchar_t *
0x14006147d  lea     ecx, [rdx-1]; int
0x140061480  call    ?FCmdLineOption@@YAHHHPEA_WPEAD@Z; FCmdLineOption(int,int,wchar_t *,char *)
0x140061485  xor     ebx, ebx
0x140061487  test    eax, eax
0x140061489  jnz     loc_140061C2B
0x14006148f  lea     ecx, [rbx+12h]; int
0x140061492  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x140061497  test    ax, ax
0x14006149a  jns     short loc_1400614FF
0x14006149c  lea     ecx, [rbx+11h]; int
0x1400614a0  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x1400614a5  test    ax, ax
0x1400614a8  js      short loc_1400614FF
0x1400614aa  mov     ecx, 3E8h; dwMilliseconds
0x1400614af  call    cs:__imp_Sleep
0x1400614b5  lea     ecx, [rbx+12h]; int
0x1400614b8  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x1400614bd  nop     dword ptr [rax]
0x1400614c0  test    ax, ax
0x1400614c3  jns     short loc_1400614FF
0x1400614c5  lea     ecx, [rbx+11h]; int
0x1400614c8  call    ?OsrcGetAsyncKeyState@@YAFH@Z; OsrcGetAsyncKeyState(int)
0x1400614cd  test    ax, ax
0x1400614d0  js      short loc_1400614FF
0x1400614d2  mov     ebx, cs:?fForceDlgUp@@3HA; int fForceDlgUp
0x1400614d8  xor     edx, edx; wchar_t *
0x1400614da  mov     ecx, 0A002Ch; int
0x1400614df  mov     cs:?fForceDlgUp@@3HA, 1; int fForceDlgUp
0x1400614e9  call    ?NoYesAlert@@YAHHPEB_W@Z; NoYesAlert(int,wchar_t const *)
0x1400614ee  mov     cs:?fForceDlgUp@@3HA, ebx; int fForceDlgUp
0x1400614f4  cmp     eax, 6
0x1400614f7  jz      loc_140061C2B
0x1400614fd  xor     ebx, ebx
0x1400614ff  or      r13, 0FFFFFFFFFFFFFFFFh
0x140061503  lea     rcx, [rbp+370h+String]
0x14006150a  mov     rax, r13
0x14006150d  inc     rax
0x140061510  cmp     [rcx+rax*2], bx
0x140061514  jnz     short loc_14006150D
0x140061516  mov     ebx, cs:?g_processIdExcel@@3KA; ulong g_processIdExcel
0x14006151c  lea     r8, [rbp+370h+String]
0x140061523  cdqe
0x140061525  mov     edx, 9; int
0x14006152a  mov     ecx, ebx; int
0x14006152c  lea     r8, [r8+rax*2]; wchar_t *
0x140061530  call    ?SzHexFromL@@YAXJHPEA_W@Z; SzHexFromL(long,int,wchar_t *)
0x140061535  mov     rax, r13
0x140061538  lea     r8, [rbp+370h+Name]
0x14006153f  xor     r13d, r13d
0x140061542  inc     rax
0x140061545  cmp     [r8+rax*2], r13w
0x14006154a  jnz     short loc_140061542
0x14006154c  cdqe
0x14006154e  lea     r8, [rbp+370h+Name]
0x140061555  mov     edx, 9; int
0x14006155a  mov     ecx, ebx; int
0x14006155c  lea     r8, [r8+rax*2]; wchar_t *
0x140061560  call    ?SzHexFromL@@YAXJHPEA_W@Z; SzHexFromL(long,int,wchar_t *)
0x140061565  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140061569  lea     r8, [rbp+370h+String]
0x140061570  inc     rbx
0x140061573  cmp     [r8+rbx*2], r13w
0x140061578  jnz     short loc_140061570
0x14006157a  lea     rcx, [rbp+370h+String]; lpString
0x140061581  call    cs:__imp_GlobalAddAtomW
0x140061587  movzx   r13d, ax
0x14006158b  xor     eax, eax
0x14006158d  test    r13w, r13w
0x140061591  jz      loc_140061C06
0x140061597  lea     rcx, ?szMergeInstanceEventAcceptSuffix@@3PA_WA; "_Accept"
0x14006159e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400615a2  inc     rdx; int
0x1400615a5  cmp     [rcx+rdx*2], ax
0x1400615a9  jnz     short loc_1400615A2
0x1400615ab  mov     r9d, 32h ; '2'; int
0x1400615b1  lea     r8, [rbp+370h+String]; wchar_t *
0x1400615b8  call    ?FAppendRgchToSz@@YA_NPEB_WHPEA_WH@Z; FAppendRgchToSz(wchar_t const *,int,wchar_t *,int)
0x1400615bd  lea     r9, [rbp+370h+String]; lpName
0x1400615c4  xor     r8d, r8d; bInitialState
0x1400615c7  xor     edx, edx; bManualReset
0x1400615c9  xor     ecx, ecx; lpEventAttributes
0x1400615cb  call    cs:__imp_CreateEventW
0x1400615d1  mov     [rbp-60h], rax
0x1400615da  movsxd  rax, ebx
0x1400615dd  add     rax, rax
0x1400615e0  cmp     rax, 64h ; 'd'
0x1400615e4  jnb     loc_140061C92
0x1400615ea  xor     ebx, ebx
0x1400615ec  lea     rcx, ?szMergeInstanceEventRejectSuffix@@3PA_WA; "_Reject"
0x1400615f3  mov     [rbp+rax+370h+String], bx
0x1400615fb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400615ff  inc     rdx; int
0x140061602  cmp     [rcx+rdx*2], bx
0x140061606  jnz     short loc_1400615FF
0x140061608  mov     r9d, 32h ; '2'; int
0x14006160e  lea     r8, [rbp+370h+String]; wchar_t *
0x140061615  call    ?FAppendRgchToSz@@YA_NPEB_WHPEA_WH@Z; FAppendRgchToSz(wchar_t const *,int,wchar_t *,int)
0x14006161a  lea     r9, [rbp+370h+String]; lpName
0x140061621  xor     r8d, r8d; bInitialState
0x140061624  xor     edx, edx; bManualReset
0x140061626  xor     ecx, ecx; lpEventAttributes
0x140061628  call    cs:__imp_CreateEventW
0x14006162e  mov     [rbp+370h+hObject+8], rax
0x140061632  cmp     [rbp+370h+hObject], rbx
0x140061636  jz      loc_140061BF2
0x14006163c  nop     dword ptr [rax+00h]
0x140061640  test    rax, rax
0x140061643  jz      loc_140061BF2
0x140061649  test    r14, r14
0x14006164c  jz      short loc_14006165D
0x14006164e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140061652  inc     rax
0x140061655  cmp     [r14+rax], bl
0x140061659  jnz     short loc_140061652
0x14006165b  jmp     short loc_140061660
0x14006165d  mov     rax, rbx
0x140061660  lea     edi, [rax+1]
0x140061663  test    r12, r12
0x140061666  jz      short loc_140061678
0x140061668  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006166c  inc     rax
0x14006166f  cmp     [r12+rax*2], bx
0x140061674  jnz     short loc_14006166C
0x140061676  jmp     short loc_14006167B
0x140061678  mov     rax, rbx
0x14006167b  xor     edx, edx; bool
0x14006167d  lea     rcx, [rbp+370h+var_388]; struct MaxPathHolder *
0x140061681  lea     ebx, ds:2[rax*2]
0x140061688  call    ?FCurDirWithMph@@YA_NPEAVMaxPathHolder@@_N@Z; FCurDirWithMph(MaxPathHolder *,bool)
0x14006168d  mov     rax, [rbp+370h+var_388]
0x140061691  lea     rdx, [rbp+370h+var_3C0]
0x140061695  mov     r8d, 4
0x14006169b  movzx   ecx, word ptr [rax]
0x14006169e  lea     r12d, ds:4[rcx*2]
0x1400616a6  mov     ecx, 8022h
0x1400616ab  call    cs:__imp_?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x1400616b1  xor     ecx, ecx
0x1400616b3  test    eax, eax
0x1400616b5  jz      loc_140061C8A
0x1400616bb  xor     r9d, r9d; dwMaximumSizeHigh
0x1400616c0  lea     eax, [r12+rbx]
0x1400616c4  lea     rcx, [rbp+370h+Name]
0x1400616cb  add     eax, edi
0x1400616cd  mov     [rsp+470h+lpName], rcx; lpName
0x1400616d2  xor     edx, edx; lpFileMappingAttributes
0x1400616d4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1400616d8  mov     [rsp+470h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x1400616dc  lea     r8d, [r9+4]; flProtect
0x1400616e0  call    cs:__imp_CreateFileMappingW
0x1400616e6  mov     r8d, 4
0x1400616f0  lea     rdx, [rbp+370h+var_3C0]
0x1400616f4  mov     ecx, 8022h
0x1400616f9  mov     [rbp+370h+var_3F0], rax
0x1400616fd  mov     rsi, rax
0x140061700  call    cs:__imp_?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoMNOReleaseSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x140061706  xor     eax, eax
0x140061708  test    rsi, rsi
0x14006170b  jz      loc_140061BEF
0x140061711  xor     r9d, r9d; dwFileOffsetLow
0x140061714  mov     qword ptr [rsp+470h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x140061719  xor     r8d, r8d; dwFileOffsetHigh
0x14006171c  lea     edx, [rax+2]; dwDesiredAccess
0x14006171f  mov     rcx, rsi; hFileMappingObject
0x140061722  call    cs:__imp_MapViewOfFile
0x140061728  mov     rsi, rax
0x14006172b  xor     eax, eax
0x14006172d  test    rsi, rsi
0x140061730  jz      loc_140061BEB
0x140061736  movsxd  rdi, edi
  ... truncated ...
```

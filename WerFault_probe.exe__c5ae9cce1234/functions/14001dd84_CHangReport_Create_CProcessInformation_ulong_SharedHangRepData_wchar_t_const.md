# CHangReport::Create(CProcessInformation *,ulong,SharedHangRepData *,wchar_t const *)

- ea: `0x14001dd84`
- end: `0x14001e99b`
- name: `?Create@CHangReport@@QEAAJPEAVCProcessInformation@@KPEAUSharedHangRepData@@PEB_W@Z`
- size: `3095`
- prototype: `__int64 __usercall@<rax>(CHangReport *__hidden this@<rcx>, struct CProcessInformation *@<rdx>, unsigned int@<r8d>, struct SharedHangRepData *@<r9>, const wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019374`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000b4cc`
- `0x14001211c`
- `0x14001444c`
- `0x140014474`
- `0x140015b40`
- `0x14001a1d4`
- `0x14001ac44`
- `0x14001dd84`
- `0x14001e9a4`
- `0x14001f200`
- `0x14001f610`
- `0x140021f40`
- `0x140045ef4`
- `0x14004655c`
- `0x140046630`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001e09a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001e09a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001e969`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001e969`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001e623`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001e623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dfa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dfa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e916`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001e0e0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001e132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001e17a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001e0e0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001e132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001e17a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001e123`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001e16b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001e123`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001e16b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e0fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e14b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e193`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e0fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e14b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e193`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001df8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001df8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001df65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e0b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001df65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e0b7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001df48`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001e003`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001df48`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001e003`
- `wer!WerpSetReportIsFatal` at `0x14001e6bd`
- `wer!WerpSetReportIsFatal` at `0x14001e6bd`
- `wer!WerpSetCallBack` at `0x14001e580`
- `wer!WerpSetCallBack` at `0x14001e580`
- `wer!WerpGetReportId` at `0x14001e543`
- `wer!WerpGetReportId` at `0x14001e543`
- `wer!WerReportCreate` at `0x14001e500`
- `wer!WerReportCreate` at `0x14001e500`
- `wer!WerpSetProcessTimelines` at `0x14001e675`
- `wer!WerpSetProcessTimelines` at `0x14001e675`
- `wer!WerpSetTelemetryAppParams` at `0x14001e634`
- `wer!WerpSetTelemetryAppParams` at `0x14001e634`
- `wer!WerReportCloseHandle` at `0x14001e48f`
- `wer!WerReportCloseHandle` at `0x14001e4bb`
- `wer!WerReportCloseHandle` at `0x14001e4d9`
- `wer!WerReportCloseHandle` at `0x14001e48f`
- `wer!WerReportCloseHandle` at `0x14001e4bb`
- `wer!WerReportCloseHandle` at `0x14001e4d9`

## string_xrefs

- `0x14001de01`: `CHangReport::Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHangReport::Create(
        CHangReport *this,
        struct CProcessInformation *a2,
        int a3,
        struct SharedHangRepData *a4,
        const wchar_t *a5)
{
  int v9; // r13d
  const wchar_t *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  wchar_t *v13; // r8
  wchar_t v14; // cx
  unsigned int v15; // ebx
  wchar_t *v16; // rcx
  CUserModeHangReport *v17; // rcx
  __int64 v18; // rdx
  bool v19; // zf
  int v20; // eax
  HANDLE v21; // rax
  void *v22; // rcx
  void *v23; // rcx
  signed int v24; // eax
  unsigned int i; // ebx
  DWORD v26; // r8d
  HANDLE v27; // rax
  void *v28; // rcx
  signed int v29; // eax
  HANDLE EventW; // rax
  void *v31; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v33; // rcx
  struct _TP_WAIT *v34; // rcx
  PTP_WAIT v35; // rax
  struct _TP_WAIT *v36; // rcx
  struct _TP_WAIT *v37; // rcx
  PTP_WAIT v38; // rax
  struct _TP_WAIT *v39; // rcx
  int v40; // eax
  __int64 v41; // r9
  __int64 v42; // rax
  struct CProcessInformation *v43; // r12
  __int64 v44; // rbx
  int ApplicationName; // eax
  CUserModeHangReport *v46; // r10
  __int64 v47; // r15
  __int64 v48; // rax
  const wchar_t *v49; // rcx
  WCHAR *wzFriendlyEventName; // rdx
  wchar_t v51; // r8
  WCHAR *v52; // rcx
  __int64 v53; // rax
  const wchar_t *v54; // rcx
  __int64 v55; // rdx
  WCHAR *wzDescription; // r8
  wchar_t v57; // r9
  WCHAR *v58; // rcx
  const wchar_t *v59; // rax
  __int64 v60; // r11
  const wchar_t *v61; // rcx
  __int64 v62; // rdx
  wchar_t *v63; // rax
  wchar_t v64; // r8
  wchar_t *v65; // rcx
  const wchar_t *v66; // rcx
  __int64 v67; // rdx
  wchar_t *v68; // rax
  wchar_t v69; // r8
  wchar_t *v70; // rcx
  __int64 v71; // rax
  _QWORD *v72; // r15
  void *v73; // rcx
  const WCHAR *v74; // rax
  WER_REPORT_TYPE v75; // edx
  int ReportId; // eax
  int v77; // eax
  int v78; // eax
  int IsFatal; // eax
  CUserModeHangReport *v80; // rcx
  void **v81; // r15
  __int64 v82; // rax
  int v83; // ebx
  HINSTANCE v84; // r9
  int v85; // eax
  CPluginList *v86; // rcx
  signed int v87; // eax
  signed int v88; // eax
  signed int v89; // eax
  signed int v90; // eax
  signed int LastError; // eax
  bool v93; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-C8h] BYREF
  char v96; // [rsp+40h] [rbp-C0h]
  _QWORD v97[31]; // [rsp+50h] [rbp-B0h] BYREF
  int v98; // [rsp+148h] [rbp+48h]
  int v99; // [rsp+14Ch] [rbp+4Ch]
  WCHAR *wzApplicationPath; // [rsp+150h] [rbp+50h]
  __int64 v101; // [rsp+158h] [rbp+58h]
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+1B0h] [rbp+B0h] BYREF
  char v103; // [rsp+A50h] [rbp+950h] BYREF
  char v104; // [rsp+AD0h] [rbp+9D0h] BYREF
  void *TokenHandle; // [rsp+B68h] [rbp+A68h] BYREF
  int v107; // [rsp+B70h] [rbp+A70h]

  memset_0(&pReportInformation, 0, 0x9C8u);
  v9 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v10 = a5;
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  CHangReport::Lock(this, &lpCriticalSection, L"CHangReport::Create");
  if ( *((_QWORD *)this + 2988) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_QWORD *)this + 3054) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_QWORD *)this + 3055) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_QWORD *)this + 3094) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_QWORD *)this + 3093) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *((_QWORD *)this + 2988) = a2;
  *((_QWORD *)this + 3054) = a4;
  *((_DWORD *)this + 16) = a3;
  v11 = 2147483646;
  v12 = 260;
  v13 = (wchar_t *)((char *)this + 23912);
  do
  {
    if ( !v11 )
      break;
    v14 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *v13++ = v14;
    --v11;
    --v12;
  }
  while ( v12 );
  v15 = v12 == 0 ? 0x8007007A : 0;
  v16 = v13 - 1;
  if ( v12 )
    v16 = v13;
  *v16 = 0;
  if ( !v12 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 46;
LABEL_204:
      v41 = v15;
      goto LABEL_205;
    }
    goto LABEL_206;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 2988) + 1800LL) & 0x100) != 0
    || (v19 = UtilRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
                L"DisableSnapshots",
                0,
                0,
                v93) == 0,
        v20 = 0,
        !v19) )
  {
    v20 = 1;
  }
  *((_DWORD *)this + 6226) = v20;
  v21 = OpenProcess(0x100C51u, 0, **((_DWORD **)this + 2988));
  v22 = (void *)*((_QWORD *)this + 3090);
  *((_QWORD *)this + 3090) = v21;
  if ( (unsigned __int64)v22 + 1 > 1 )
    CloseHandle(v22);
  v23 = (void *)*((_QWORD *)this + 3090);
  if ( (unsigned __int64)v23 + 1 <= 1 )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 47;
      goto LABEL_204;
    }
    goto LABEL_206;
  }
  if ( !OpenProcessToken(v23, 0xBu, &TokenHandle) )
  {
    v24 = GetLastError();
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)v24);
    }
  }
  for ( i = 0; i < 0xF; ++i )
  {
    v26 = *(_DWORD *)(*((_QWORD *)this + 3054) + 4LL * (int)i + 1164);
    if ( v26 )
    {
      v27 = OpenProcess(0x100C51u, 0, v26);
      v28 = (void *)*((_QWORD *)this + v9 + 3096);
      *((_QWORD *)this + v9 + 3096) = v27;
      if ( (unsigned __int64)v28 + 1 > 1 )
        CloseHandle(v28);
      if ( (unsigned __int64)(*((_QWORD *)this + v9 + 3096) + 1LL) <= 1 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v29 = GetLastError();
          if ( v29 > 0 )
            v29 = (unsigned __int16)v29 | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
            (unsigned int)v29);
        }
      }
      else
      {
        ++v9;
      }
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v31 = (void *)*((_QWORD *)this + 3089);
  *((_QWORD *)this + 3089) = EventW;
  if ( (unsigned __int64)v31 + 1 > 1 )
    CloseHandle(v31);
  if ( (unsigned __int64)(*((_QWORD *)this + 3089) + 1LL) <= 1 )
  {
    v90 = GetLastError();
    v15 = v90;
    if ( v90 > 0 )
      v15 = (unsigned __int16)v90 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 50;
      goto LABEL_204;
    }
    goto LABEL_206;
  }
  ThreadpoolWait = CreateThreadpoolWait(CHangReport::StaticCancelCallback, this, 0);
  v33 = (struct _TP_WAIT *)*((_QWORD *)this + 3094);
  *((_QWORD *)this + 3094) = ThreadpoolWait;
  if ( v33 )
    CloseThreadpoolWait(v33);
  v34 = (struct _TP_WAIT *)*((_QWORD *)this + 3094);
  if ( !v34 )
  {
    v89 = GetLastError();
    v15 = v89;
    if ( v89 > 0 )
      v15 = (unsigned __int16)v89 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 51;
      goto LABEL_204;
    }
    goto LABEL_206;
  }
  SetThreadpoolWait(v34, *(HANDLE *)(*((_QWORD *)this + 3054) + 1736LL), 0);
  v35 = CreateThreadpoolWait(CHangReport::StaticCancelCallback, this, 0);
  v36 = (struct _TP_WAIT *)*((_QWORD *)this + 3093);
  *((_QWORD *)this + 3093) = v35;
  if ( v36 )
    CloseThreadpoolWait(v36);
  v37 = (struct _TP_WAIT *)*((_QWORD *)this + 3093);
  if ( !v37 )
  {
    v88 = GetLastError();
    v15 = v88;
    if ( v88 > 0 )
      v15 = (unsigned __int16)v88 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 52;
      goto LABEL_204;
    }
    goto LABEL_206;
  }
  SetThreadpoolWait(v37, *((HANDLE *)this + 3089), 0);
  v38 = CreateThreadpoolWait(CHangReport::StaticCancelCallback, this, 0);
  v39 = (struct _TP_WAIT *)*((_QWORD *)this + 3092);
  *((_QWORD *)this + 3092) = v38;
  if ( v39 )
    CloseThreadpoolWait(v39);
  if ( !*((_QWORD *)this + 3092) )
  {
    v87 = GetLastError();
    v15 = v87;
    if ( v87 > 0 )
      v15 = (unsigned __int16)v87 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 53;
      goto LABEL_204;
    }
    goto LABEL_206;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 3054) + 1440LL) & 0x10000) != 0 )
    CHangReport::_RegisterLpeNotification(this);
  v40 = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 16LL))(this);
  v15 = v40;
  if ( v40 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_206;
    }
    v18 = 54;
    goto LABEL_69;
  }
  pReportInformation.dwSize = 2504;
  v42 = *((_QWORD *)this + 3054);
  if ( (*(_DWORD *)(v42 + 1440) & 0x1C0) == 0 || *(_QWORD *)(v42 + 1432) )
  {
    v43 = a2;
  }
  else
  {
    v43 = a2;
    if ( *((_DWORD *)this + 6226) )
      goto LABEL_77;
    if ( CHangReport::FindSnapshotForProcess(this, *(_DWORD *)a2) )
    {
      pReportInformation.hProcess = 0;
      goto LABEL_77;
    }
  }
  pReportInformation.hProcess = (HANDLE)*((_QWORD *)this + 3090);
LABEL_77:
  v44 = 128;
  ApplicationName = CProcessInformation::GetApplicationName(
                      *((CProcessInformation **)this + 2988),
                      pReportInformation.wzApplicationName,
                      0x80u);
  if ( ApplicationName < 0 )
  {
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      goto LABEL_82;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
      (unsigned int)ApplicationName);
  }
  v46 = WPP_GLOBAL_Control;
LABEL_82:
  v47 = 2147483646;
  v48 = 2147483646;
  v49 = L"Stopped responding and was closed";
  wzFriendlyEventName = pReportInformation.wzFriendlyEventName;
  do
  {
    if ( !v48 )
      break;
    v51 = *v49;
    if ( !*v49 )
      break;
    ++v49;
    *wzFriendlyEventName++ = v51;
    --v48;
    --v44;
  }
  while ( v44 );
  v52 = wzFriendlyEventName - 1;
  if ( v44 )
    v52 = wzFriendlyEventName;
  *v52 = 0;
  if ( !v44 && v46 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v46 + 2), 56, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, v44 == 0 ? 0x8007007A : 0);
    v46 = WPP_GLOBAL_Control;
  }
  v53 = 2147483646;
  v54 = L"A problem caused this program to stop interacting with Windows.";
  v55 = 512;
  wzDescription = pReportInformation.wzDescription;
  do
  {
    if ( !v53 )
      break;
    v57 = *v54;
    if ( !*v54 )
      break;
    ++v54;
    *wzDescription++ = v57;
    --v53;
    --v55;
  }
  while ( v55 );
  v58 = wzDescription - 1;
  if ( v55 )
    v58 = wzDescription;
  *v58 = 0;
  if ( !v55 && v46 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)v46 + 2), 57, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, v55 == 0 ? 0x8007007A : 0);
  v59 = CProcessInformation::AppFileName(*((CProcessInformation **)this + 2988));
  StringCchCopyW(pReportInformation.wzApplicationPath, 0x104u, v59);
  v60 = 2147483646;
  v61 = L"windows";
  v62 = 64;
  v63 = (wchar_t *)&v103;
  do
  {
    if ( !v60 )
      break;
    v64 = *v61;
    if ( !*v61 )
      break;
    ++v61;
    *v63++ = v64;
    --v60;
    --v62;
  }
  while ( v62 );
  v65 = v63 - 1;
  if ( v62 )
    v65 = v63;
  *v65 = 0;
  v66 = L"windows8";
  v67 = 64;
  v68 = (wchar_t *)&v104;
  do
  {
    if ( !v47 )
      break;
    v69 = *v66;
    if ( !*v66 )
      break;
    ++v66;
    *v68++ = v69;
    --v47;
    --v67;
  }
  while ( v67 );
  v70 = v68 - 1;
  if ( v67 )
    v70 = v68;
  *v70 = 0;
  v107 = 12;
  v71 = *((_QWORD *)this + 3054);
  v72 = (_QWORD *)((char *)this + 24440);
  v73 = (void *)*((_QWORD *)this + 3055);
  if ( *(_DWORD *)(v71 + 1152) == 1 )
  {
    *v72 = 0;
    if ( v73 )
      WerReportCloseHandle(v73);
    v74 = (const WCHAR *)(*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
    v75 = WerReportKernel;
  }
  else
  {
    v19 = (*(_DWORD *)(v71 + 1440) & 1) == 0;
    *v72 = 0;
    if ( v19 )
    {
      if ( v73 )
        WerReportCloseHandle(v73);
      v74 = (const WCHAR *)(*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
      v75 = WerReportApplicationHang;
    }
    else
    {
      if ( v73 )
        WerReportCloseHandle(v73);
      v74 = (const WCHAR *)(*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
      v75 = WerReportCritical;
    }
  }
  v15 = WerReportCreate(v74, v75, &pReportInformation, (HREPORT *)this + 3055);
  if ( (v15 & 0x80000000) == 0 )
  {
    ReportId = WerpGetReportId(*v72, (char *)this + 24448, 64);
    if ( ReportId < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)ReportId);
    }
    v40 = WerpSetCallBack(*v72, CHangReport::StaticWerCallback, this);
    v15 = v40;
    if ( v40 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_206;
      }
      v18 = 60;
      goto LABEL_69;
    }
    v40 = CHangReport::SetIntegratorId(this);
    v15 = v40;
    if ( v40 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_206;
      }
      v18 = 61;
      goto LABEL_69;
    }
    if ( *(_QWORD *)(*((_QWORD *)this + 3054) + 1744LL) )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
      }
      SetEvent(*(HANDLE *)(*((_QWORD *)this + 3054) + 1744LL));
    }
    v77 = WerpSetTelemetryAppParams(*v72, (char *)v43 + 1872);
    if ( v77 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)v77);
    }
    v78 = WerpSetProcessTimelines(*v72, (char *)v43 + 1920, 1);
    if ( v78 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)v78);
    }
    IsFatal = WerpSetReportIsFatal(*v72, (*(_DWORD *)(*((_QWORD *)this + 3054) + 1440LL) & 8) == 0);
    if ( IsFatal < 0 )
    {
      v80 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
      {
LABEL_162:
        v40 = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 24LL))(this);
        v15 = v40;
        if ( v40 >= 0 )
        {
          v81 = (void **)((char *)this + 72);
          v82 = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
          v83 = WerPluginsCreate(v82, (CPluginList **)this + 9);
          if ( v83 < 0 )
          {
            if ( *v81 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                69,
                &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
                (unsigned int)v83);
            }
          }
          else
          {
            memset_0(v97, 0, 0x158u);
            v97[0] = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
            v98 = 0;
            v99 = 2;
            v101 = *((_QWORD *)this + 3090);
            wzApplicationPath = pReportInformation.wzApplicationPath;
            v85 = WerPluginsInitialize(*v81, (struct WER_PLUGIN_INIT_IN *)v97, 0, v84);
            v15 = v85;
            if ( v85 >= 0 )
              goto LABEL_206;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                68,
                &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
                (unsigned int)v85);
            }
            v86 = (CPluginList *)*v81;
            *v81 = 0;
            if ( v86 )
              WerPluginsDestroy(v86);
          }
          v15 = 0;
          goto LABEL_206;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_206;
        }
        v18 = 67;
LABEL_69:
        v41 = (unsigned int)v40;
LABEL_205:
        WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, v41);
        goto LABEL_206;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_159:
        if ( v80 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v80 + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)v80 + 2), 66, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
        goto LABEL_162;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)IsFatal);
    }
    v80 = WPP_GLOBAL_Control;
    goto LABEL_159;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 58;
    goto LABEL_204;
  }
LABEL_206:
  if ( v96 )
    LeaveCriticalSection(lpCriticalSection);
  return v15;
}

```

## disassembly

```asm
0x14001dd84  mov     [rsp-8+arg_10], rbx
0x14001dd89  push    rbp
0x14001dd8a  push    rsi
0x14001dd8b  push    rdi
0x14001dd8c  push    r12
0x14001dd8e  push    r13
0x14001dd90  push    r14
0x14001dd92  push    r15
0x14001dd94  lea     rbp, [rsp-0A90h]
0x14001dd9c  sub     rsp, 0B90h
0x14001dda3  mov     rax, cs:__security_cookie
0x14001ddaa  xor     rax, rsp
0x14001ddad  mov     [rbp+0AC0h+var_40], rax
0x14001ddb4  mov     rsi, r9
0x14001ddb7  mov     r14d, r8d
0x14001ddba  mov     r15, rdx
0x14001ddbd  mov     [rsp+0BC0h+var_B90], rdx
0x14001ddc2  mov     rdi, rcx
0x14001ddc5  xor     edx, edx; Val
0x14001ddc7  mov     r8d, 9C8h; Size
0x14001ddcd  lea     rcx, [rbp+0AC0h+pReportInformation]; void *
0x14001ddd4  call    memset_0
0x14001ddd9  xor     r13d, r13d
0x14001dddc  test    r15, r15
0x14001dddf  jnz     short loc_14001DDE6
0x14001dde1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001dde6  test    rsi, rsi
0x14001dde9  jnz     short loc_14001DDF0
0x14001ddeb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001ddf0  mov     rbx, [rbp+0AC0h+arg_20]
0x14001ddf7  test    rbx, rbx
0x14001ddfa  jnz     short loc_14001DE01
0x14001ddfc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001de01  lea     r8, aChangreportCre; "CHangReport::Create"
0x14001de08  lea     rdx, [rsp+0BC0h+lpCriticalSection]
0x14001de0d  mov     rcx, rdi
0x14001de10  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14001de15  nop
0x14001de16  cmp     [rdi+5D60h], r13
0x14001de1d  jz      short loc_14001DE24
0x14001de1f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001de24  cmp     [rdi+5F70h], r13
0x14001de2b  jz      short loc_14001DE32
0x14001de2d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001de32  cmp     [rdi+5F78h], r13
0x14001de39  jz      short loc_14001DE40
0x14001de3b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001de40  cmp     [rdi+60B0h], r13
0x14001de47  jz      short loc_14001DE4E
0x14001de49  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001de4e  cmp     [rdi+60A8h], r13
0x14001de55  jz      short loc_14001DE5C
0x14001de57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001de5c  mov     [rdi+5D60h], r15
0x14001de63  mov     [rdi+5F70h], rsi
0x14001de6a  mov     [rdi+40h], r14d
0x14001de6e  mov     eax, 7FFFFFFEh
0x14001de73  mov     edx, 104h
0x14001de78  lea     r8, [rdi+5D68h]
0x14001de7f  mov     r12d, 1
0x14001de85  test    rax, rax
0x14001de88  jz      short loc_14001DEA6
0x14001de8a  movzx   ecx, word ptr [rbx]
0x14001de8d  test    cx, cx
0x14001de90  jz      short loc_14001DEA6
0x14001de92  add     rbx, 2
0x14001de96  mov     [r8], cx
0x14001de9a  add     r8, 2
0x14001de9e  sub     rax, r12
0x14001dea1  sub     rdx, r12
0x14001dea4  jnz     short loc_14001DE85
0x14001dea6  mov     rax, rdx
0x14001dea9  neg     rax
0x14001deac  sbb     ebx, ebx
0x14001deae  not     ebx
0x14001deb0  and     ebx, 8007007Ah
0x14001deb6  lea     rcx, [r8-2]
0x14001deba  test    rdx, rdx
0x14001debd  cmovnz  rcx, r8
0x14001dec1  mov     [rcx], r13w
0x14001dec5  jnz     short loc_14001DEF2
0x14001dec7  lea     rsi, WPP_GLOBAL_Control
0x14001dece  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ded5  cmp     rcx, rsi
0x14001ded8  jz      loc_14001E95D
0x14001dede  test    [rcx+1Ch], r12b
0x14001dee2  jz      loc_14001E95D
0x14001dee8  mov     edx, 2Eh ; '.'
0x14001deed  jmp     loc_14001E949
0x14001def2  mov     rax, [rdi+5D60h]
0x14001def9  test    dword ptr [rax+708h], 100h
0x14001df03  jnz     short loc_14001DF2E
0x14001df05  mov     [rsp+0BC0h+var_BA0], r13; bool *
0x14001df0a  xor     r9d, r9d; unsigned int
0x14001df0d  lea     r8, aDisablesnapsho; "DisableSnapshots"
0x14001df14  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x14001df1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001df22  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x14001df27  test    eax, eax
0x14001df29  mov     eax, r13d
0x14001df2c  jz      short loc_14001DF31
0x14001df2e  mov     eax, r12d
0x14001df31  mov     [rdi+6148h], eax
0x14001df37  mov     r8, [rdi+5D60h]
0x14001df3e  mov     r8d, [r8]; dwProcessId
0x14001df41  xor     edx, edx; bInheritHandle
0x14001df43  mov     ecx, 100C51h; dwDesiredAccess
0x14001df48  call    cs:__imp_OpenProcess
0x14001df4e  mov     rcx, [rdi+6090h]; hObject
0x14001df55  mov     [rdi+6090h], rax
0x14001df5c  lea     rax, [rcx+1]
0x14001df60  cmp     rax, r12
0x14001df63  jbe     short loc_14001DF6B
0x14001df65  call    cs:__imp_CloseHandle
0x14001df6b  mov     rcx, [rdi+6090h]; ProcessHandle
0x14001df72  lea     rax, [rcx+1]
0x14001df76  cmp     rax, r12
0x14001df79  jbe     loc_14001E916
0x14001df7f  lea     r8, [rbp+0AC0h+TokenHandle]; TokenHandle
0x14001df86  mov     edx, 0Bh; DesiredAccess
0x14001df8b  call    cs:__imp_OpenProcessToken
0x14001df91  lea     r14, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001df98  lea     rsi, WPP_GLOBAL_Control
0x14001df9f  mov     r15d, 80070000h
0x14001dfa5  test    eax, eax
0x14001dfa7  jnz     short loc_14001DFDF
0x14001dfa9  call    cs:__imp_GetLastError
0x14001dfaf  test    eax, eax
0x14001dfb1  jle     short loc_14001DFB9
0x14001dfb3  movzx   eax, ax
0x14001dfb6  or      eax, r15d
0x14001dfb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dfc0  cmp     rcx, rsi
0x14001dfc3  jz      short loc_14001DFDF
0x14001dfc5  test    byte ptr [rcx+1Ch], 2
0x14001dfc9  jz      short loc_14001DFDF
0x14001dfcb  mov     edx, 30h ; '0'
0x14001dfd0  mov     r9d, eax
0x14001dfd3  mov     r8, r14
0x14001dfd6  mov     rcx, [rcx+10h]
0x14001dfda  call    WPP_SF_d
0x14001dfdf  xor     ebx, ebx
0x14001dfe1  movsxd  rcx, ebx
0x14001dfe4  mov     rax, [rdi+5F70h]
0x14001dfeb  mov     r8d, [rax+rcx*4+48Ch]; dwProcessId
0x14001dff3  test    r8d, r8d
0x14001dff6  jz      loc_14001E084
0x14001dffc  xor     edx, edx; bInheritHandle
0x14001dffe  mov     ecx, 100C51h; dwDesiredAccess
0x14001e003  call    cs:__imp_OpenProcess
0x14001e009  movsxd  r12, r13d
0x14001e00c  mov     rcx, [rdi+r12*8+60C0h]; hObject
0x14001e014  mov     [rdi+r12*8+60C0h], rax
0x14001e01c  lea     rax, [rcx+1]
0x14001e020  cmp     rax, 1
0x14001e024  jbe     short loc_14001E02C
0x14001e026  call    cs:__imp_CloseHandle
0x14001e02c  mov     rax, [rdi+r12*8+60C0h]
0x14001e034  mov     r12d, 1
0x14001e03a  add     rax, r12
0x14001e03d  cmp     rax, r12
0x14001e040  jbe     short loc_14001E047
0x14001e042  add     r13d, r12d
0x14001e045  jmp     short loc_14001E084
0x14001e047  mov     rax, cs:WPP_GLOBAL_Control
0x14001e04e  cmp     rax, rsi
0x14001e051  jz      short loc_14001E084
0x14001e053  test    byte ptr [rax+1Ch], 2
0x14001e057  jz      short loc_14001E084
0x14001e059  call    cs:__imp_GetLastError
0x14001e05f  test    eax, eax
0x14001e061  jle     short loc_14001E069
0x14001e063  movzx   eax, ax
0x14001e066  or      eax, r15d
0x14001e069  mov     edx, 31h ; '1'
0x14001e06e  mov     r9d, eax
0x14001e071  mov     r8, r14
0x14001e074  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e07b  mov     rcx, [rcx+10h]
0x14001e07f  call    WPP_SF_d
0x14001e084  add     ebx, r12d
0x14001e087  cmp     ebx, 0Fh
0x14001e08a  jb      loc_14001DFE1
0x14001e090  xor     r9d, r9d; lpName
0x14001e093  xor     r8d, r8d; bInitialState
0x14001e096  xor     edx, edx; bManualReset
0x14001e098  xor     ecx, ecx; lpEventAttributes
0x14001e09a  call    cs:__imp_CreateEventW
0x14001e0a0  mov     rcx, [rdi+6088h]; hObject
0x14001e0a7  mov     [rdi+6088h], rax
0x14001e0ae  lea     rax, [rcx+1]
0x14001e0b2  cmp     rax, r12
0x14001e0b5  jbe     short loc_14001E0BD
0x14001e0b7  call    cs:__imp_CloseHandle
0x14001e0bd  mov     rax, [rdi+6088h]
0x14001e0c4  add     rax, r12
0x14001e0c7  cmp     rax, r12
0x14001e0ca  jbe     loc_14001E8E5
0x14001e0d0  xor     r8d, r8d; pcbe
0x14001e0d3  mov     rdx, rdi; pv
0x14001e0d6  lea     rbx, ?StaticCancelCallback@CHangReport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; CHangReport::StaticCancelCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x14001e0dd  mov     rcx, rbx; pfnwa
0x14001e0e0  call    cs:__imp_CreateThreadpoolWait
0x14001e0e6  mov     rcx, [rdi+60B0h]; pwa
0x14001e0ed  mov     [rdi+60B0h], rax
0x14001e0f4  xor     r13d, r13d
0x14001e0f7  test    rcx, rcx
0x14001e0fa  jz      short loc_14001E102
0x14001e0fc  call    cs:__imp_CloseThreadpoolWait
0x14001e102  mov     rcx, [rdi+60B0h]; pwa
0x14001e109  test    rcx, rcx
0x14001e10c  jz      loc_14001E8AF
0x14001e112  mov     rdx, [rdi+5F70h]
0x14001e119  xor     r8d, r8d; pftTimeout
0x14001e11c  mov     rdx, [rdx+6C8h]; h
0x14001e123  call    cs:__imp_SetThreadpoolWait
0x14001e129  xor     r8d, r8d; pcbe
0x14001e12c  mov     rdx, rdi; pv
0x14001e12f  mov     rcx, rbx; pfnwa
0x14001e132  call    cs:__imp_CreateThreadpoolWait
0x14001e138  mov     rcx, [rdi+60A8h]; pwa
0x14001e13f  mov     [rdi+60A8h], rax
0x14001e146  test    rcx, rcx
0x14001e149  jz      short loc_14001E151
0x14001e14b  call    cs:__imp_CloseThreadpoolWait
0x14001e151  mov     rcx, [rdi+60A8h]; pwa
0x14001e158  test    rcx, rcx
0x14001e15b  jz      loc_14001E879
0x14001e161  xor     r8d, r8d; pftTimeout
0x14001e164  mov     rdx, [rdi+6088h]; h
0x14001e16b  call    cs:__imp_SetThreadpoolWait
0x14001e171  xor     r8d, r8d; pcbe
0x14001e174  mov     rdx, rdi; pv
0x14001e177  mov     rcx, rbx; pfnwa
0x14001e17a  call    cs:__imp_CreateThreadpoolWait
0x14001e180  mov     rcx, [rdi+60A0h]; pwa
0x14001e187  mov     [rdi+60A0h], rax
0x14001e18e  test    rcx, rcx
0x14001e191  jz      short loc_14001E199
0x14001e193  call    cs:__imp_CloseThreadpoolWait
0x14001e199  cmp     [rdi+60A0h], r13
0x14001e1a0  jz      loc_14001E843
0x14001e1a6  mov     rax, [rdi+5F70h]
0x14001e1ad  test    dword ptr [rax+5A0h], 10000h
0x14001e1b7  jz      short loc_14001E1C1
0x14001e1b9  mov     rcx, rdi; this
0x14001e1bc  call    ?_RegisterLpeNotification@CHangReport@@AEAAJXZ; CHangReport::_RegisterLpeNotification(void)
0x14001e1c1  mov     rax, [rdi]
0x14001e1c4  mov     rcx, rdi
0x14001e1c7  mov     rax, [rax+10h]
0x14001e1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e1d0  mov     ebx, eax
0x14001e1d2  test    eax, eax
0x14001e1d4  jns     short loc_14001E200
0x14001e1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1dd  cmp     rcx, rsi
0x14001e1e0  jz      loc_14001E95D
0x14001e1e6  test    [rcx+1Ch], r12b
0x14001e1ea  jz      loc_14001E95D
0x14001e1f0  mov     edx, 36h ; '6'
0x14001e1f5  mov     r9d, eax
0x14001e1f8  mov     r8, r14
0x14001e1fb  jmp     loc_14001E953
0x14001e200  mov     [rbp+0AC0h+pReportInformation.dwSize], 9C8h
0x14001e20a  mov     rax, [rdi+5F70h]
0x14001e211  test    dword ptr [rax+5A0h], 1C0h
0x14001e21b  jz      short loc_14001E255
0x14001e21d  cmp     [rax+598h], r13
0x14001e224  jnz     short loc_14001E255
0x14001e226  mov     r12, [rsp+0BC0h+var_B90]
0x14001e22b  cmp     [rdi+6148h], r13d
0x14001e232  jnz     short loc_14001E268
0x14001e234  mov     edx, [r12]; unsigned int
0x14001e238  mov     rcx, rdi; this
0x14001e23b  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x14001e240  mov     [rbp+0AC0h+var_60], rax
0x14001e247  test    rax, rax
0x14001e24a  jz      short loc_14001E25A
0x14001e24c  mov     [rbp+0AC0h+pReportInformation.hProcess], r13
0x14001e253  jmp     short loc_14001E268
0x14001e255  mov     r12, [rsp+0BC0h+var_B90]
0x14001e25a  mov     rax, [rdi+6090h]
0x14001e261  mov     [rbp+0AC0h+pReportInformation.hProcess], rax
0x14001e268  mov     ebx, 80h
0x14001e26d  mov     r8d, ebx; unsigned int
0x14001e270  lea     rdx, [rbp+0AC0h+pReportInformation.wzApplicationName]; wchar_t *
0x14001e277  mov     rcx, [rdi+5D60h]; this
0x14001e27e  call    ?GetApplicationName@CProcessInformation@@QEAAJPEA_WI@Z; CProcessInformation::GetApplicationName(wchar_t *,uint)
0x14001e283  test    eax, eax
0x14001e285  jns     short loc_14001E2AC
0x14001e287  mov     r10, cs:WPP_GLOBAL_Control
0x14001e28e  cmp     r10, rsi
0x14001e291  jz      short loc_14001E2B3
0x14001e293  test    byte ptr [r10+1Ch], 2
0x14001e298  jz      short loc_14001E2B3
0x14001e29a  lea     edx, [rbx-49h]
0x14001e29d  mov     r9d, eax
0x14001e2a0  mov     r8, r14
0x14001e2a3  mov     rcx, [r10+10h]
0x14001e2a7  call    WPP_SF_d
  ... truncated ...
```

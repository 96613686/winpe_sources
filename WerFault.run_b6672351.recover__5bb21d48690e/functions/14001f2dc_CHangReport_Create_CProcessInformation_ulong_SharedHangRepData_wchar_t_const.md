# CHangReport::Create(CProcessInformation *,ulong,SharedHangRepData *,wchar_t const *)

- ea: `0x14001f2dc`
- end: `0x14001ff9c`
- name: `?Create@CHangReport@@QEAAJPEAVCProcessInformation@@KPEAUSharedHangRepData@@PEB_W@Z`
- size: `3264`
- prototype: `__int64 __usercall@<rax>(CHangReport *__hidden this@<rcx>, struct CProcessInformation *@<rdx>, unsigned int@<r8d>, struct SharedHangRepData *@<r9>, const wchar_t *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a274`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000b50c`
- `0x140012994`
- `0x140014ee4`
- `0x140014f14`
- `0x1400166ec`
- `0x14001b1b4`
- `0x14001bc7c`
- `0x14001e46c`
- `0x14001f2dc`
- `0x14001ffa4`
- `0x1400207c4`
- `0x140020bf0`
- `0x1400235a8`
- `0x140049108`
- `0x140049798`
- `0x14004986c`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001f61c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001f61c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001ff63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001ff63`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001fbe7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001fbe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ff0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fe97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ff0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001f66e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001f6d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001f72c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001f66e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001f6d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001f72c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f6bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f717`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f6bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f717`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001f690`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001f6f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001f74b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001f690`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001f6f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001f74b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001f4ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001f4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f59c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f63f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f59c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001f63f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001f4a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001f573`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001f4a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001f573`
- `wer!WerpSetReportIsFatal` at `0x14001fc93`
- `wer!WerpSetReportIsFatal` at `0x14001fc93`
- `wer!WerpSetCallBack` at `0x14001fb3e`
- `wer!WerpSetCallBack` at `0x14001fb3e`
- `wer!WerpGetReportId` at `0x14001fafb`
- `wer!WerpGetReportId` at `0x14001fafb`
- `wer!WerReportCreate` at `0x14001fab2`
- `wer!WerReportCreate` at `0x14001fab2`
- `wer!WerpSetProcessTimelines` at `0x14001fc45`
- `wer!WerpSetProcessTimelines` at `0x14001fc45`
- `wer!WerpSetTelemetryAppParams` at `0x14001fbfe`
- `wer!WerpSetTelemetryAppParams` at `0x14001fbfe`

## string_xrefs

- `0x14001f359`: `CHangReport::Create`

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
  char *v73; // rcx
  HREPORT *v74; // rbx
  const WCHAR *v75; // rax
  WER_REPORT_TYPE v76; // edx
  int ReportId; // eax
  int v78; // eax
  int v79; // eax
  int IsFatal; // eax
  CUserModeHangReport *v81; // rcx
  void **v82; // r15
  __int64 v83; // rax
  int v84; // ebx
  HINSTANCE v85; // r9
  int v86; // eax
  CPluginList *v87; // rcx
  signed int v88; // eax
  signed int v89; // eax
  signed int v90; // eax
  signed int v91; // eax
  signed int LastError; // eax
  bool v94; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-C8h] BYREF
  char v97; // [rsp+40h] [rbp-C0h]
  _QWORD v98[31]; // [rsp+50h] [rbp-B0h] BYREF
  int v99; // [rsp+148h] [rbp+48h]
  int v100; // [rsp+14Ch] [rbp+4Ch]
  WCHAR *wzApplicationPath; // [rsp+150h] [rbp+50h]
  __int64 v102; // [rsp+158h] [rbp+58h]
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+1B0h] [rbp+B0h] BYREF
  char v104; // [rsp+A50h] [rbp+950h] BYREF
  char v105; // [rsp+AD0h] [rbp+9D0h] BYREF
  void *TokenHandle; // [rsp+B68h] [rbp+A68h] BYREF
  int v108; // [rsp+B70h] [rbp+A70h]

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
LABEL_198:
      v41 = v15;
      goto LABEL_199;
    }
    goto LABEL_200;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 2988) + 1800LL) & 0x100) != 0
    || (v19 = UtilRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
                L"DisableSnapshots",
                0,
                0,
                v94) == 0,
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
      goto LABEL_198;
    }
    goto LABEL_200;
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
        WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
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
            WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
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
    v91 = GetLastError();
    v15 = v91;
    if ( v91 > 0 )
      v15 = (unsigned __int16)v91 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 50;
      goto LABEL_198;
    }
    goto LABEL_200;
  }
  ThreadpoolWait = CreateThreadpoolWait(CHangReport::StaticCancelCallback, this, 0);
  v33 = (struct _TP_WAIT *)*((_QWORD *)this + 3094);
  *((_QWORD *)this + 3094) = ThreadpoolWait;
  if ( v33 )
    CloseThreadpoolWait(v33);
  v34 = (struct _TP_WAIT *)*((_QWORD *)this + 3094);
  if ( !v34 )
  {
    v90 = GetLastError();
    v15 = v90;
    if ( v90 > 0 )
      v15 = (unsigned __int16)v90 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 51;
      goto LABEL_198;
    }
    goto LABEL_200;
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
    v89 = GetLastError();
    v15 = v89;
    if ( v89 > 0 )
      v15 = (unsigned __int16)v89 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 52;
      goto LABEL_198;
    }
    goto LABEL_200;
  }
  SetThreadpoolWait(v37, *((HANDLE *)this + 3089), 0);
  v38 = CreateThreadpoolWait(CHangReport::StaticCancelCallback, this, 0);
  v39 = (struct _TP_WAIT *)*((_QWORD *)this + 3092);
  *((_QWORD *)this + 3092) = v38;
  if ( v39 )
    CloseThreadpoolWait(v39);
  if ( !*((_QWORD *)this + 3092) )
  {
    v88 = GetLastError();
    v15 = v88;
    if ( v88 > 0 )
      v15 = (unsigned __int16)v88 | 0x80070000;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 53;
      goto LABEL_198;
    }
    goto LABEL_200;
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
      goto LABEL_200;
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
      WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
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
    WPP_SF_d(*((_QWORD *)v46 + 2), 56, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, v44 == 0 ? 0x8007007A : 0);
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
    WPP_SF_d(*((_QWORD *)v46 + 2), 57, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, v55 == 0 ? 0x8007007A : 0);
  v59 = CProcessInformation::AppFileName(*((CProcessInformation **)this + 2988));
  StringCchCopyW(pReportInformation.wzApplicationPath, 0x104u, v59);
  v60 = 2147483646;
  v61 = L"windows";
  v62 = 64;
  v63 = (wchar_t *)&v104;
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
  v68 = (wchar_t *)&v105;
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
  v108 = 12;
  v71 = *((_QWORD *)this + 3054);
  v72 = (_QWORD *)((char *)this + 24440);
  v73 = (char *)this + 24440;
  if ( *(_DWORD *)(v71 + 1152) == 1 )
  {
    v74 = (HREPORT *)tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long WerReportCloseHandle(void *),0>>(v73);
    v75 = (const WCHAR *)(*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
    v76 = WerReportKernel;
  }
  else if ( (*(_BYTE *)(v71 + 1440) & 1) != 0 )
  {
    v74 = (HREPORT *)tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long WerReportCloseHandle(void *),0>>(v73);
    v75 = (const WCHAR *)(*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
    v76 = WerReportCritical;
  }
  else
  {
    v74 = (HREPORT *)tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long WerReportCloseHandle(void *),0>>(v73);
    v75 = (const WCHAR *)(*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
    v76 = WerReportApplicationHang;
  }
  v15 = WerReportCreate(v75, v76, &pReportInformation, v74);
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
        WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
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
        goto LABEL_200;
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
        goto LABEL_200;
      }
      v18 = 61;
      goto LABEL_69;
    }
    if ( *(_QWORD *)(*((_QWORD *)this + 3054) + 1744LL) )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
      }
      SetEvent(*(HANDLE *)(*((_QWORD *)this + 3054) + 1744LL));
    }
    v78 = WerpSetTelemetryAppParams(*v72, (char *)v43 + 1872);
    if ( v78 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)v78);
    }
    v79 = WerpSetProcessTimelines(*v72, (char *)v43 + 1920, 1);
    if ( v79 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)v79);
    }
    IsFatal = WerpSetReportIsFatal(*v72, (*(_DWORD *)(*((_QWORD *)this + 3054) + 1440LL) & 8) == 0);
    if ( IsFatal < 0 )
    {
      v81 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
      {
LABEL_156:
        v40 = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 24LL))(this);
        v15 = v40;
        if ( v40 >= 0 )
        {
          v82 = (void **)((char *)this + 72);
          v83 = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
          v84 = WerPluginsCreate(v83, (char *)this + 72);
          if ( v84 < 0 )
          {
            if ( *v82 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                69,
                WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
                (unsigned int)v84);
            }
          }
          else
          {
            memset_0(v98, 0, 0x158u);
            v98[0] = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
            v99 = 0;
            v100 = 2;
            v102 = *((_QWORD *)this + 3090);
            wzApplicationPath = pReportInformation.wzApplicationPath;
            v86 = WerPluginsInitialize(*v82, (struct WER_PLUGIN_INIT_IN *)v98, 0, v85);
            v15 = v86;
            if ( v86 >= 0 )
              goto LABEL_200;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                68,
                WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
                (unsigned int)v86);
            }
            v87 = (CPluginList *)*v82;
            *v82 = 0;
            if ( v87 )
              WerPluginsDestroy(v87);
          }
          v15 = 0;
          goto LABEL_200;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_200;
        }
        v18 = 67;
LABEL_69:
        v41 = (unsigned int)v40;
LABEL_199:
        WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, v41);
        goto LABEL_200;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_153:
        if ( v81 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v81 + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)v81 + 2), 66, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
        goto LABEL_156;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
        (unsigned int)IsFatal);
    }
    v81 = WPP_GLOBAL_Control;
    goto LABEL_153;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 58;
    goto LABEL_198;
  }
LABEL_200:
  if ( v97 )
    LeaveCriticalSection(lpCriticalSection);
  return v15;
}

```

## disassembly

```asm
0x14001f2dc  mov     [rsp-8+arg_10], rbx
0x14001f2e1  push    rbp
0x14001f2e2  push    rsi
0x14001f2e3  push    rdi
0x14001f2e4  push    r12
0x14001f2e6  push    r13
0x14001f2e8  push    r14
0x14001f2ea  push    r15
0x14001f2ec  lea     rbp, [rsp-0A90h]
0x14001f2f4  sub     rsp, 0B90h
0x14001f2fb  mov     rax, cs:__security_cookie
0x14001f302  xor     rax, rsp
0x14001f305  mov     [rbp+0AC0h+var_40], rax
0x14001f30c  mov     rsi, r9
0x14001f30f  mov     r14d, r8d
0x14001f312  mov     r15, rdx
0x14001f315  mov     [rsp+0BC0h+var_B90], rdx
0x14001f31a  mov     rdi, rcx
0x14001f31d  xor     edx, edx; Val
0x14001f31f  mov     r8d, 9C8h; Size
0x14001f325  lea     rcx, [rbp+0AC0h+pReportInformation]; void *
0x14001f32c  call    memset_0
0x14001f331  xor     r13d, r13d
0x14001f334  test    r15, r15
0x14001f337  jnz     short loc_14001F33E
0x14001f339  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f33e  test    rsi, rsi
0x14001f341  jnz     short loc_14001F348
0x14001f343  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f348  mov     rbx, [rbp+0AC0h+arg_20]
0x14001f34f  test    rbx, rbx
0x14001f352  jnz     short loc_14001F359
0x14001f354  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f359  lea     r8, aChangreportCre; "CHangReport::Create"
0x14001f360  lea     rdx, [rsp+0BC0h+lpCriticalSection]
0x14001f365  mov     rcx, rdi
0x14001f368  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14001f36d  nop
0x14001f36e  cmp     [rdi+5D60h], r13
0x14001f375  jz      short loc_14001F37C
0x14001f377  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f37c  cmp     [rdi+5F70h], r13
0x14001f383  jz      short loc_14001F38A
0x14001f385  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f38a  cmp     [rdi+5F78h], r13
0x14001f391  jz      short loc_14001F398
0x14001f393  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f398  cmp     [rdi+60B0h], r13
0x14001f39f  jz      short loc_14001F3A6
0x14001f3a1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f3a6  cmp     [rdi+60A8h], r13
0x14001f3ad  jz      short loc_14001F3B4
0x14001f3af  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f3b4  mov     [rdi+5D60h], r15
0x14001f3bb  mov     [rdi+5F70h], rsi
0x14001f3c2  mov     [rdi+40h], r14d
0x14001f3c6  mov     eax, 7FFFFFFEh
0x14001f3cb  mov     edx, 104h
0x14001f3d0  lea     r8, [rdi+5D68h]
0x14001f3d7  mov     r12d, 1
0x14001f3dd  test    rax, rax
0x14001f3e0  jz      short loc_14001F3FE
0x14001f3e2  movzx   ecx, word ptr [rbx]
0x14001f3e5  test    cx, cx
0x14001f3e8  jz      short loc_14001F3FE
0x14001f3ea  add     rbx, 2
0x14001f3ee  mov     [r8], cx
0x14001f3f2  add     r8, 2
0x14001f3f6  sub     rax, r12
0x14001f3f9  sub     rdx, r12
0x14001f3fc  jnz     short loc_14001F3DD
0x14001f3fe  mov     rax, rdx
0x14001f401  neg     rax
0x14001f404  sbb     ebx, ebx
0x14001f406  not     ebx
0x14001f408  and     ebx, 8007007Ah
0x14001f40e  lea     rcx, [r8-2]
0x14001f412  test    rdx, rdx
0x14001f415  cmovnz  rcx, r8
0x14001f419  mov     [rcx], r13w
0x14001f41d  jnz     short loc_14001F44A
0x14001f41f  lea     rsi, WPP_GLOBAL_Control
0x14001f426  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f42d  cmp     rcx, rsi
0x14001f430  jz      loc_14001FF57
0x14001f436  test    [rcx+1Ch], r12b
0x14001f43a  jz      loc_14001FF57
0x14001f440  mov     edx, 2Eh ; '.'
0x14001f445  jmp     loc_14001FF43
0x14001f44a  mov     rax, [rdi+5D60h]
0x14001f451  test    dword ptr [rax+708h], 100h
0x14001f45b  jnz     short loc_14001F486
0x14001f45d  mov     [rsp+0BC0h+var_BA0], r13; bool *
0x14001f462  xor     r9d, r9d; unsigned int
0x14001f465  lea     r8, aDisablesnapsho; "DisableSnapshots"
0x14001f46c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x14001f473  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001f47a  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x14001f47f  test    eax, eax
0x14001f481  mov     eax, r13d
0x14001f484  jz      short loc_14001F489
0x14001f486  mov     eax, r12d
0x14001f489  mov     [rdi+6148h], eax
0x14001f48f  mov     r8, [rdi+5D60h]
0x14001f496  mov     r8d, [r8]; dwProcessId
0x14001f499  xor     edx, edx; bInheritHandle
0x14001f49b  mov     ecx, 100C51h; dwDesiredAccess
0x14001f4a0  call    cs:__imp_OpenProcess
0x14001f4a7  nop     dword ptr [rax+rax+00h]
0x14001f4ac  mov     rcx, [rdi+6090h]; hObject
0x14001f4b3  mov     [rdi+6090h], rax
0x14001f4ba  lea     rax, [rcx+1]
0x14001f4be  cmp     rax, r12
0x14001f4c1  jbe     short loc_14001F4CF
0x14001f4c3  call    cs:__imp_CloseHandle
0x14001f4ca  nop     dword ptr [rax+rax+00h]
0x14001f4cf  mov     rcx, [rdi+6090h]; ProcessHandle
0x14001f4d6  lea     rax, [rcx+1]
0x14001f4da  cmp     rax, r12
0x14001f4dd  jbe     loc_14001FF0A
0x14001f4e3  lea     r8, [rbp+0AC0h+TokenHandle]; TokenHandle
0x14001f4ea  mov     edx, 0Bh; DesiredAccess
0x14001f4ef  call    cs:__imp_OpenProcessToken
0x14001f4f6  nop     dword ptr [rax+rax+00h]
0x14001f4fb  lea     r14, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001f502  lea     rsi, WPP_GLOBAL_Control
0x14001f509  mov     r15d, 80070000h
0x14001f50f  test    eax, eax
0x14001f511  jnz     short loc_14001F54F
0x14001f513  call    cs:__imp_GetLastError
0x14001f51a  nop     dword ptr [rax+rax+00h]
0x14001f51f  test    eax, eax
0x14001f521  jle     short loc_14001F529
0x14001f523  movzx   eax, ax
0x14001f526  or      eax, r15d
0x14001f529  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f530  cmp     rcx, rsi
0x14001f533  jz      short loc_14001F54F
0x14001f535  test    byte ptr [rcx+1Ch], 2
0x14001f539  jz      short loc_14001F54F
0x14001f53b  mov     edx, 30h ; '0'
0x14001f540  mov     r9d, eax
0x14001f543  mov     r8, r14
0x14001f546  mov     rcx, [rcx+10h]
0x14001f54a  call    WPP_SF_d
0x14001f54f  xor     ebx, ebx
0x14001f551  movsxd  rcx, ebx
0x14001f554  mov     rax, [rdi+5F70h]
0x14001f55b  mov     r8d, [rax+rcx*4+48Ch]; dwProcessId
0x14001f563  test    r8d, r8d
0x14001f566  jz      loc_14001F606
0x14001f56c  xor     edx, edx; bInheritHandle
0x14001f56e  mov     ecx, 100C51h; dwDesiredAccess
0x14001f573  call    cs:__imp_OpenProcess
0x14001f57a  nop     dword ptr [rax+rax+00h]
0x14001f57f  movsxd  r12, r13d
0x14001f582  mov     rcx, [rdi+r12*8+60C0h]; hObject
0x14001f58a  mov     [rdi+r12*8+60C0h], rax
0x14001f592  lea     rax, [rcx+1]
0x14001f596  cmp     rax, 1
0x14001f59a  jbe     short loc_14001F5A8
0x14001f59c  call    cs:__imp_CloseHandle
0x14001f5a3  nop     dword ptr [rax+rax+00h]
0x14001f5a8  mov     rax, [rdi+r12*8+60C0h]
0x14001f5b0  mov     r12d, 1
0x14001f5b6  add     rax, r12
0x14001f5b9  cmp     rax, r12
0x14001f5bc  jbe     short loc_14001F5C3
0x14001f5be  add     r13d, r12d
0x14001f5c1  jmp     short loc_14001F606
0x14001f5c3  mov     rax, cs:WPP_GLOBAL_Control
0x14001f5ca  cmp     rax, rsi
0x14001f5cd  jz      short loc_14001F606
0x14001f5cf  test    byte ptr [rax+1Ch], 2
0x14001f5d3  jz      short loc_14001F606
0x14001f5d5  call    cs:__imp_GetLastError
0x14001f5dc  nop     dword ptr [rax+rax+00h]
0x14001f5e1  test    eax, eax
0x14001f5e3  jle     short loc_14001F5EB
0x14001f5e5  movzx   eax, ax
0x14001f5e8  or      eax, r15d
0x14001f5eb  mov     edx, 31h ; '1'
0x14001f5f0  mov     r9d, eax
0x14001f5f3  mov     r8, r14
0x14001f5f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5fd  mov     rcx, [rcx+10h]
0x14001f601  call    WPP_SF_d
0x14001f606  add     ebx, r12d
0x14001f609  cmp     ebx, 0Fh
0x14001f60c  jb      loc_14001F551
0x14001f612  xor     r9d, r9d; lpName
0x14001f615  xor     r8d, r8d; bInitialState
0x14001f618  xor     edx, edx; bManualReset
0x14001f61a  xor     ecx, ecx; lpEventAttributes
0x14001f61c  call    cs:__imp_CreateEventW
0x14001f623  nop     dword ptr [rax+rax+00h]
0x14001f628  mov     rcx, [rdi+6088h]; hObject
0x14001f62f  mov     [rdi+6088h], rax
0x14001f636  lea     rax, [rcx+1]
0x14001f63a  cmp     rax, r12
0x14001f63d  jbe     short loc_14001F64B
0x14001f63f  call    cs:__imp_CloseHandle
0x14001f646  nop     dword ptr [rax+rax+00h]
0x14001f64b  mov     rax, [rdi+6088h]
0x14001f652  add     rax, r12
0x14001f655  cmp     rax, r12
0x14001f658  jbe     loc_14001FED3
0x14001f65e  xor     r8d, r8d; pcbe
0x14001f661  mov     rdx, rdi; pv
0x14001f664  lea     rbx, ?StaticCancelCallback@CHangReport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; CHangReport::StaticCancelCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x14001f66b  mov     rcx, rbx; pfnwa
0x14001f66e  call    cs:__imp_CreateThreadpoolWait
0x14001f675  nop     dword ptr [rax+rax+00h]
0x14001f67a  mov     rcx, [rdi+60B0h]; pwa
0x14001f681  mov     [rdi+60B0h], rax
0x14001f688  xor     r13d, r13d
0x14001f68b  test    rcx, rcx
0x14001f68e  jz      short loc_14001F69C
0x14001f690  call    cs:__imp_CloseThreadpoolWait
0x14001f697  nop     dword ptr [rax+rax+00h]
0x14001f69c  mov     rcx, [rdi+60B0h]; pwa
0x14001f6a3  test    rcx, rcx
0x14001f6a6  jz      loc_14001FE97
0x14001f6ac  mov     rdx, [rdi+5F70h]
0x14001f6b3  xor     r8d, r8d; pftTimeout
0x14001f6b6  mov     rdx, [rdx+6C8h]; h
0x14001f6bd  call    cs:__imp_SetThreadpoolWait
0x14001f6c4  nop     dword ptr [rax+rax+00h]
0x14001f6c9  xor     r8d, r8d; pcbe
0x14001f6cc  mov     rdx, rdi; pv
0x14001f6cf  mov     rcx, rbx; pfnwa
0x14001f6d2  call    cs:__imp_CreateThreadpoolWait
0x14001f6d9  nop     dword ptr [rax+rax+00h]
0x14001f6de  mov     rcx, [rdi+60A8h]; pwa
0x14001f6e5  mov     [rdi+60A8h], rax
0x14001f6ec  test    rcx, rcx
0x14001f6ef  jz      short loc_14001F6FD
0x14001f6f1  call    cs:__imp_CloseThreadpoolWait
0x14001f6f8  nop     dword ptr [rax+rax+00h]
0x14001f6fd  mov     rcx, [rdi+60A8h]; pwa
0x14001f704  test    rcx, rcx
0x14001f707  jz      loc_14001FE5B
0x14001f70d  xor     r8d, r8d; pftTimeout
0x14001f710  mov     rdx, [rdi+6088h]; h
0x14001f717  call    cs:__imp_SetThreadpoolWait
0x14001f71e  nop     dword ptr [rax+rax+00h]
0x14001f723  xor     r8d, r8d; pcbe
0x14001f726  mov     rdx, rdi; pv
0x14001f729  mov     rcx, rbx; pfnwa
0x14001f72c  call    cs:__imp_CreateThreadpoolWait
0x14001f733  nop     dword ptr [rax+rax+00h]
0x14001f738  mov     rcx, [rdi+60A0h]; pwa
0x14001f73f  mov     [rdi+60A0h], rax
0x14001f746  test    rcx, rcx
0x14001f749  jz      short loc_14001F757
0x14001f74b  call    cs:__imp_CloseThreadpoolWait
0x14001f752  nop     dword ptr [rax+rax+00h]
0x14001f757  cmp     [rdi+60A0h], r13
0x14001f75e  jz      loc_14001FE1F
0x14001f764  mov     rax, [rdi+5F70h]
0x14001f76b  test    dword ptr [rax+5A0h], 10000h
0x14001f775  jz      short loc_14001F77F
0x14001f777  mov     rcx, rdi; this
0x14001f77a  call    ?_RegisterLpeNotification@CHangReport@@AEAAJXZ; CHangReport::_RegisterLpeNotification(void)
0x14001f77f  mov     rax, [rdi]
0x14001f782  mov     rcx, rdi
0x14001f785  mov     rax, [rax+10h]
0x14001f789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f78e  mov     ebx, eax
0x14001f790  test    eax, eax
0x14001f792  jns     short loc_14001F7BE
0x14001f794  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f79b  cmp     rcx, rsi
0x14001f79e  jz      loc_14001FF57
0x14001f7a4  test    [rcx+1Ch], r12b
0x14001f7a8  jz      loc_14001FF57
0x14001f7ae  mov     edx, 36h ; '6'
0x14001f7b3  mov     r9d, eax
0x14001f7b6  mov     r8, r14
0x14001f7b9  jmp     loc_14001FF4D
0x14001f7be  mov     [rbp+0AC0h+pReportInformation.dwSize], 9C8h
0x14001f7c8  mov     rax, [rdi+5F70h]
0x14001f7cf  test    dword ptr [rax+5A0h], 1C0h
0x14001f7d9  jz      short loc_14001F813
0x14001f7db  cmp     [rax+598h], r13
0x14001f7e2  jnz     short loc_14001F813
0x14001f7e4  mov     r12, [rsp+0BC0h+var_B90]
0x14001f7e9  cmp     [rdi+6148h], r13d
0x14001f7f0  jnz     short loc_14001F826
0x14001f7f2  mov     edx, [r12]; unsigned int
0x14001f7f6  mov     rcx, rdi; this
0x14001f7f9  call    ?FindSnapshotForProcess@CHangReport@@IEAAPEAUHPSS__@@K@Z; CHangReport::FindSnapshotForProcess(ulong)
0x14001f7fe  mov     [rbp+0AC0h+var_60], rax
0x14001f805  test    rax, rax
0x14001f808  jz      short loc_14001F818
0x14001f80a  mov     [rbp+0AC0h+pReportInformation.hProcess], r13
0x14001f811  jmp     short loc_14001F826
0x14001f813  mov     r12, [rsp+0BC0h+var_B90]
0x14001f818  mov     rax, [rdi+6090h]
0x14001f81f  mov     [rbp+0AC0h+pReportInformation.hProcess], rax
  ... truncated ...
```

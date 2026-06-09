# CProcessInformation::Init(ulong,ulong,HWND__ *)

- ea: `0x14001cf1c`
- end: `0x14001d9e6`
- name: `?Init@CProcessInformation@@QEAAJKKPEAUHWND__@@@Z`
- size: `2762`
- prototype: `__int64 __fastcall(CProcessInformation *__hidden this, unsigned int, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a274`

## callees

- `0x140002490`
- `0x140002748`
- `0x14000353c`
- `0x140003bb8`
- `0x140014ee4`
- `0x140014f14`
- `0x140014f58`
- `0x140016618`
- `0x1400166ec`
- `0x14001bac4`
- `0x14001cf1c`
- `0x14001de2c`
- `0x14001e428`
- `0x140031f74`
- `0x1400328c0`
- `0x140032b40`
- `0x140032ec4`
- `0x140034024`
- `0x140034968`
- `0x140034da8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d8d9`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001d935`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001d969`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001d935`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001d969`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001d499`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001d499`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d2b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d2f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d2b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d2f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d982`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14001d342`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14001d342`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001d160`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001d160`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x14001d191`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x14001d191`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001d2d3`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001d2d3`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001d247`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001d247`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001d20e`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001d20e`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001d59b`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001d59b`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x14001d7c4`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x14001d7c4`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14001d0b6`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14001d0b6`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14001d027`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14001d027`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x14001d04e`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x14001d04e`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x14001d09c`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x14001d09c`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001d86d`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001d86d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CProcessInformation::Init(CProcessInformation *this, __int64 a2, __int64 a3, HWND a4)
{
  int v5; // esi
  DWORD v6; // r9d
  WCHAR *v8; // r12
  HANDLE v9; // r15
  DWORD WindowThreadProcessId; // eax
  DWORD v11; // r14d
  __int64 v12; // rdx
  HWND Window; // rax
  CUserModeHangReport *v14; // rcx
  unsigned int v15; // ebx
  _DWORD *v16; // rbx
  HRESULT Flags; // eax
  CUserModeHangReport *v18; // rcx
  HANDLE Toolhelp32Snapshot; // r14
  signed int v20; // eax
  signed int v21; // eax
  CUserModeHangReport *v22; // rcx
  __int64 v23; // rdx
  int IsHostedApp; // eax
  CUserModeHangReport **v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  int Rundll32HostedAppName; // eax
  unsigned int v29; // ebx
  HANDLE v30; // rbx
  DWORD v31; // r8d
  void *v32; // r14
  int SvchostInformation; // eax
  DWORD v34; // eax
  __int64 v35; // rcx
  LONG PackageFullName; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  int ProcessAppSessionGuid; // eax
  int ProcessTelemetryTargetAppParams; // eax
  int ProcessTimelines; // eax
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int16 *v46; // rdx
  __int64 v47; // r8
  _WORD *v48; // rax
  __int16 v49; // r9
  _WORD *v50; // rdx
  __int16 *v51; // rcx
  __int64 v52; // rdx
  _WORD *v53; // rax
  __int16 v54; // r8
  _WORD *v55; // rcx
  int v56; // eax
  _DWORD *v57; // rbx
  CUserModeHangReport *v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // r9
  int PackageIdentity; // eax
  __int64 v62; // r9
  signed int LastError; // eax
  DWORD EnvironmentVariableW; // eax
  bool v65; // cf
  int v66; // eax
  DWORD dwProcessId; // [rsp+30h] [rbp-99h] BYREF
  UINT32 packageFullNameLength; // [rsp+38h] [rbp-91h] BYREF
  DWORD dwSize; // [rsp+3Ch] [rbp-8Dh] BYREF
  HANDLE v71; // [rsp+40h] [rbp-89h]
  void *v72; // [rsp+48h] [rbp-81h]
  _WORD *v73; // [rsp+50h] [rbp-79h]
  _WORD v74[8]; // [rsp+58h] [rbp-71h] BYREF
  void *v75[2]; // [rsp+68h] [rbp-61h] BYREF
  _WORD v76[8]; // [rsp+78h] [rbp-51h] BYREF
  HANDLE v77; // [rsp+88h] [rbp-41h]
  _OWORD v78[2]; // [rsp+90h] [rbp-39h] BYREF
  THREADENTRY32 te; // [rsp+B0h] [rbp-19h] BYREF

  v5 = a3;
  v6 = a2;
  dwProcessId = a2;
  v8 = (WCHAR *)((char *)this + 8);
  if ( *((_WORD *)this + 4) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, (unsigned int)a2);
    v6 = dwProcessId;
  }
  dwSize = 260;
  packageFullNameLength = 0;
  v72 = v74;
  v73 = v74;
  v74[0] = 0;
  v75[0] = v76;
  v75[1] = v76;
  v76[0] = 0;
  v9 = 0;
  v77 = 0;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
    v6 = dwProcessId;
  }
  *(_DWORD *)this = v6;
  *((_DWORD *)this + 1) = v5;
  if ( a4 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, a4);
    }
    dwProcessId = 0;
    WindowThreadProcessId = GetWindowThreadProcessId(a4, &dwProcessId);
    v11 = WindowThreadProcessId;
    v12 = dwProcessId;
    if ( dwProcessId != *(_DWORD *)this || WindowThreadProcessId != *((_DWORD *)this + 1) )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
        v12 = dwProcessId;
      }
      MicrosoftTelemetryAssertTriggeredArgs(v14, v12, v11);
      v15 = -2147024809;
      goto LABEL_161;
    }
    if ( !IsHungAppWindow(a4) )
    {
      *((_DWORD *)this + 451) |= 0x1000u;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, a4);
      }
      if ( !IsWindowEnabled(a4) )
      {
        Window = GetWindow(a4, 6u);
        if ( Window )
        {
          if ( Window != a4 )
          {
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, Window);
            }
            *((_DWORD *)this + 451) |= 0x400u;
          }
        }
      }
    }
  }
  v9 = OpenProcess(0x100450u, 0, *(_DWORD *)this);
  v77 = v9;
  if ( (unsigned __int64)v9 + 1 <= 1 )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 71;
      goto LABEL_159;
    }
    goto LABEL_161;
  }
  v16 = (_DWORD *)((char *)this + 1800);
  Flags = WerGetFlags(v9, (PDWORD)this + 450);
  if ( Flags < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
        (unsigned int)Flags);
    }
    *v16 = 0;
    goto LABEL_36;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
      (unsigned int)*v16);
LABEL_36:
    v18 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 1) )
  {
    Toolhelp32Snapshot = CreateToolhelp32Snapshot(4u, 0);
    v71 = Toolhelp32Snapshot;
    memset(v78, 0, 28);
    *(_OWORD *)&te.dwSize = v78[0];
    *(_OWORD *)&te.th32OwnerProcessID = 0;
    te.dwSize = 28;
    if ( !Thread32First(Toolhelp32Snapshot, &te) )
    {
      v20 = GetLastError();
      v15 = v20;
      if ( v20 > 0 )
        v15 = (unsigned __int16)v20 | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v15);
      }
      if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 )
        CloseHandle(Toolhelp32Snapshot);
      goto LABEL_161;
    }
    while ( te.th32OwnerProcessID != *(_DWORD *)this )
    {
      if ( !Thread32Next(Toolhelp32Snapshot, &te) )
        goto LABEL_50;
    }
    *((_DWORD *)this + 1) = te.th32ThreadID;
LABEL_50:
    if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 )
      CloseHandle(Toolhelp32Snapshot);
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)v18 + 2), 75, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, *((unsigned int *)this + 1));
  if ( !QueryFullProcessImageNameW(v9, 0, v8, &dwSize) )
  {
    v21 = GetLastError();
    v15 = v21;
    if ( v21 > 0 )
      v15 = (unsigned __int16)v21 | 0x80070000;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 76;
LABEL_159:
      v62 = v15;
      goto LABEL_160;
    }
    goto LABEL_161;
  }
  IsHostedApp = UtilIsHostedApp(v8, (int *)this + 453, (CProcessInformation *)((char *)this + 1816));
  if ( IsHostedApp >= 0 )
  {
    if ( !*((_DWORD *)this + 453) )
      goto LABEL_90;
    v25 = (CUserModeHangReport **)*((unsigned int *)this + 454);
    if ( (_DWORD)v25 )
    {
      if ( (_DWORD)v25 == 1 )
      {
        Rundll32HostedAppName = UtilGetRundll32HostedAppName(v9, (__int64)this + 1824);
        v29 = Rundll32HostedAppName;
        if ( Rundll32HostedAppName < 0 )
        {
          v25 = (CUserModeHangReport **)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                91,
                WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
                (unsigned int)Rundll32HostedAppName);
              v25 = (CUserModeHangReport **)WPP_GLOBAL_Control;
            }
            if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 2) != 0 )
            {
              v26 = 78;
              v27 = v29;
              goto LABEL_76;
            }
          }
        }
      }
    }
    else
    {
      v30 = 0;
      v71 = 0;
      v31 = *((_DWORD *)this + 1);
      v32 = 0;
      if ( v31 )
      {
        v30 = OpenThread(0x58u, 0, v31);
        v71 = v30;
        if ( (unsigned __int64)v30 + 1 <= 1 )
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v34 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v34);
          }
          v32 = v30;
        }
        else
        {
          v32 = v30;
        }
      }
      SvchostInformation = CProcessInformation::ExtractSvchostInformation(this, v9, v30);
      if ( SvchostInformation < 0 )
      {
        v25 = (CUserModeHangReport **)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            80,
            WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
            (unsigned int)SvchostInformation);
        }
      }
      if ( (unsigned __int64)v32 + 1 > 1 )
        CloseHandle(v32);
    }
  }
  else
  {
    v25 = (CUserModeHangReport **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v26 = 77;
      v27 = (unsigned int)IsHostedApp;
LABEL_76:
      WPP_SF_d(v25[2], v26, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v27);
    }
  }
LABEL_90:
  packageFullNameLength = 128;
  *((_WORD *)this + 524) = 0;
  *((_DWORD *)this + 452) = 0;
  if ( !(unsigned __int8)IsGetPackageFullNamePresent(v25) )
  {
    if ( (unsigned __int8)IsXerGetPackageIdentityPresent(v35) )
    {
      PackageIdentity = XerGetPackageIdentity(v9, &packageFullNameLength, (char *)this + 1048, 0, 0);
      v15 = PackageIdentity;
      if ( PackageIdentity < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_161;
        }
        v23 = 82;
        v62 = (unsigned int)PackageIdentity;
LABEL_160:
        WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v62);
        goto LABEL_161;
      }
      goto LABEL_145;
    }
LABEL_96:
    ProcessAppSessionGuid = TelGetProcessAppSessionGuid(v9, (struct _GUID *)this + 118, (unsigned __int64 *)this + 235);
    if ( ProcessAppSessionGuid < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
        (unsigned int)ProcessAppSessionGuid);
    }
    ProcessTelemetryTargetAppParams = UtilGetProcessTelemetryTargetAppParams(v9);
    if ( ProcessTelemetryTargetAppParams < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
        (unsigned int)ProcessTelemetryTargetAppParams);
    }
    *((_QWORD *)this + 238) = *((_QWORD *)this + 217);
    *((_QWORD *)this + 239) = *((_QWORD *)this + 221);
    ProcessTimelines = UtilGetProcessTimelines(v9, (CProcessInformation *)((char *)this + 1920));
    if ( ProcessTimelines < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
        (unsigned int)ProcessTimelines);
    }
    if ( *((_DWORD *)this + 452) && (int)PackageUtility::GetProcessApplicationId(v9) >= 0 )
    {
      v44 = 2147483646;
      v45 = 2147483646;
      v46 = (__int16 *)v72;
      v47 = 131;
      v48 = (_WORD *)((char *)this + 1436);
      do
      {
        if ( !v45 )
          break;
        v49 = *v46;
        if ( !*v46 )
          break;
        ++v46;
        *v48++ = v49;
        --v45;
        --v47;
      }
      while ( v47 );
      v50 = v48 - 1;
      if ( v47 )
        v50 = v48;
      *v50 = 0;
      if ( !v47 )
        *((_WORD *)this + 718) = 0;
      if ( (int)PackageUtility::ParseApplicationId(v72, v50, v75) >= 0 )
      {
        v51 = (__int16 *)v75[0];
        v52 = 66;
        v53 = (_WORD *)((char *)this + 1304);
        do
        {
          if ( !v44 )
            break;
          v54 = *v51;
          if ( !*v51 )
            break;
          ++v51;
          *v53++ = v54;
          --v44;
          --v52;
        }
        while ( v52 );
        v55 = v53 - 1;
        if ( v52 )
          v55 = v53;
        *v55 = 0;
        if ( !v52 )
          *((_WORD *)this + 652) = 0;
      }
    }
    v56 = CProcessInformation::LookupMinClrVersion(this);
    if ( v56 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
        (unsigned int)v56);
    }
    v57 = (_DWORD *)((char *)this + 1864);
    if ( (unsigned int)GetProcessUIContextInformation(v9, (char *)this + 1864) )
    {
      v58 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_153;
      }
      v59 = 88;
      v60 = (unsigned int)*v57;
    }
    else
    {
      *v57 = 0;
      *((_DWORD *)this + 467) = 0;
      v58 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_153;
      }
      v59 = 87;
      v60 = 0;
    }
    WPP_SF_d(*((_QWORD *)v58 + 2), v59, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v60);
LABEL_153:
    v15 = 0;
    goto LABEL_161;
  }
  PackageFullName = GetPackageFullName(v9, &packageFullNameLength, (PWSTR)this + 524);
  v15 = PackageFullName;
  switch ( PackageFullName )
  {
    case 0:
      if ( !*((_WORD *)this + 524) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v38, v37, v39, v40);
LABEL_145:
      *((_DWORD *)this + 452) = 1;
      goto LABEL_96;
    case 122:
      MicrosoftTelemetryAssertTriggeredNoArgs(v38, v37, v39, v40);
      goto LABEL_96;
    case 15700:
      goto LABEL_96;
  }
  if ( PackageFullName > 0 )
    v15 = (unsigned __int16)PackageFullName | 0x80070000;
  if ( (v15 & 0x80000000) == 0 )
    v15 = -2147467259;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v23 = 81;
    goto LABEL_159;
  }
LABEL_161:
  EnvironmentVariableW = GetEnvironmentVariableW(L"_HANGREP_PKGFULLNAME", (LPWSTR)this + 524, 0x80u);
  if ( !EnvironmentVariableW || (v65 = EnvironmentVariableW < 0x80, v66 = 1, !v65) )
    v66 = 0;
  *((_DWORD *)this + 452) |= v66;
  GetEnvironmentVariableW(L"_HANGREP_PKGRELAPPID", (LPWSTR)this + 652, 0x42u);
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  if ( v75[0] != v76 )
    operator delete(v75[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v72 != v74 )
    operator delete(v72, (const struct std::nothrow_t *)&std::nothrow);
  return v15;
}

```

## disassembly

```asm
0x14001cf1c  push    rbp
0x14001cf1e  push    rbx
0x14001cf1f  push    rsi
0x14001cf20  push    rdi
0x14001cf21  push    r12
0x14001cf23  push    r13
0x14001cf25  push    r14
0x14001cf27  push    r15
0x14001cf29  lea     rbp, [rsp-1Fh]
0x14001cf2e  sub     rsp, 0E8h
0x14001cf35  mov     rax, cs:__security_cookie
0x14001cf3c  xor     rax, rsp
0x14001cf3f  mov     [rbp+57h+var_50], rax
0x14001cf43  mov     rbx, r9
0x14001cf46  mov     esi, r8d
0x14001cf49  mov     r9d, edx
0x14001cf4c  mov     rdi, rcx
0x14001cf4f  mov     [rsp+120h+dwProcessId], edx
0x14001cf53  lea     r12, [rcx+8]
0x14001cf57  xor     r13d, r13d
0x14001cf5a  cmp     [r12], r13w
0x14001cf5f  jz      short loc_14001CF6B
0x14001cf61  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001cf66  mov     r9d, [rsp+120h+dwProcessId]
0x14001cf6b  mov     [rsp+120h+dwSize], 104h
0x14001cf73  mov     [rsp+120h+packageFullNameLength], r13d
0x14001cf78  lea     rax, [rbp+57h+var_C8]
0x14001cf7c  mov     [rsp+120h+var_D8], rax
0x14001cf81  lea     rax, [rbp+57h+var_C8]
0x14001cf85  mov     [rbp+57h+var_D0], rax
0x14001cf89  mov     [rbp+57h+var_C8], r13w
0x14001cf8e  lea     rax, [rbp+57h+var_A8]
0x14001cf92  mov     [rbp+57h+var_B8], rax
0x14001cf96  lea     rax, [rbp+57h+var_A8]
0x14001cf9a  mov     [rbp+57h+var_B0], rax
0x14001cf9e  mov     [rbp+57h+var_A8], r13w
0x14001cfa3  mov     r15, r13
0x14001cfa6  mov     [rbp+57h+var_98], r13
0x14001cfaa  lea     r14, WPP_GLOBAL_Control
0x14001cfb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cfb8  cmp     rcx, r14
0x14001cfbb  jz      short loc_14001CFE1
0x14001cfbd  test    byte ptr [rcx+1Ch], 4
0x14001cfc1  jz      short loc_14001CFE1
0x14001cfc3  mov     edx, 42h ; 'B'
0x14001cfc8  mov     dword ptr [rsp+120h+var_100], esi
0x14001cfcc  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001cfd3  mov     rcx, [rcx+10h]
0x14001cfd7  call    WPP_SF_Dd
0x14001cfdc  mov     r9d, [rsp+120h+dwProcessId]
0x14001cfe1  mov     [rdi], r9d
0x14001cfe4  mov     [rdi+4], esi
0x14001cfe7  test    rbx, rbx
0x14001cfea  jz      loc_14001D156
0x14001cff0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cff7  cmp     rcx, r14
0x14001cffa  jz      short loc_14001D01A
0x14001cffc  test    byte ptr [rcx+1Ch], 4
0x14001d000  jz      short loc_14001D01A
0x14001d002  mov     edx, 43h ; 'C'
0x14001d007  mov     r9, rbx
0x14001d00a  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d011  mov     rcx, [rcx+10h]
0x14001d015  call    WPP_SF_q
0x14001d01a  mov     [rsp+120h+dwProcessId], r13d
0x14001d01f  lea     rdx, [rsp+120h+dwProcessId]; lpdwProcessId
0x14001d024  mov     rcx, rbx; hWnd
0x14001d027  call    cs:__imp_GetWindowThreadProcessId
0x14001d02e  nop     dword ptr [rax+rax+00h]
0x14001d033  mov     r14d, eax
0x14001d036  mov     edx, [rsp+120h+dwProcessId]
0x14001d03a  cmp     edx, [rdi]
0x14001d03c  jnz     loc_14001D108
0x14001d042  cmp     eax, [rdi+4]
0x14001d045  jnz     loc_14001D108
0x14001d04b  mov     rcx, rbx; hwnd
0x14001d04e  call    cs:__imp_IsHungAppWindow
0x14001d055  nop     dword ptr [rax+rax+00h]
0x14001d05a  test    eax, eax
0x14001d05c  jnz     loc_14001D14F
0x14001d062  bts     dword ptr [rdi+70Ch], 0Ch
0x14001d06a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d071  lea     r14, WPP_GLOBAL_Control
0x14001d078  cmp     rcx, r14
0x14001d07b  jz      short loc_14001D099
0x14001d07d  test    byte ptr [rcx+1Ch], 4
0x14001d081  jz      short loc_14001D099
0x14001d083  lea     edx, [rax+45h]
0x14001d086  mov     r9, rbx
0x14001d089  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d090  mov     rcx, [rcx+10h]
0x14001d094  call    WPP_SF_q
0x14001d099  mov     rcx, rbx; hWnd
0x14001d09c  call    cs:__imp_IsWindowEnabled
0x14001d0a3  nop     dword ptr [rax+rax+00h]
0x14001d0a8  test    eax, eax
0x14001d0aa  jnz     loc_14001D156
0x14001d0b0  lea     edx, [rax+6]; uCmd
0x14001d0b3  mov     rcx, rbx; hWnd
0x14001d0b6  call    cs:__imp_GetWindow
0x14001d0bd  nop     dword ptr [rax+rax+00h]
0x14001d0c2  test    rax, rax
0x14001d0c5  jz      loc_14001D156
0x14001d0cb  cmp     rax, rbx
0x14001d0ce  jz      loc_14001D156
0x14001d0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0db  cmp     rcx, r14
0x14001d0de  jz      short loc_14001D0FE
0x14001d0e0  test    byte ptr [rcx+1Ch], 4
0x14001d0e4  jz      short loc_14001D0FE
0x14001d0e6  mov     edx, 46h ; 'F'
0x14001d0eb  mov     r9, rax
0x14001d0ee  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d0f5  mov     rcx, [rcx+10h]
0x14001d0f9  call    WPP_SF_q
0x14001d0fe  bts     dword ptr [rdi+70Ch], 0Ah
0x14001d106  jmp     short loc_14001D156
0x14001d108  mov     esi, 1
0x14001d10d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d114  lea     rax, WPP_GLOBAL_Control
0x14001d11b  cmp     rcx, rax
0x14001d11e  jz      short loc_14001D13D
0x14001d120  test    [rcx+1Ch], sil
0x14001d124  jz      short loc_14001D13D
0x14001d126  lea     edx, [rsi+43h]
0x14001d129  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d130  mov     rcx, [rcx+10h]
0x14001d134  call    WPP_SF_
0x14001d139  mov     edx, [rsp+120h+dwProcessId]
0x14001d13d  mov     r8d, r14d
0x14001d140  call    MicrosoftTelemetryAssertTriggeredArgs
0x14001d145  mov     ebx, 80070057h
0x14001d14a  jmp     loc_14001D91E
0x14001d14f  lea     r14, WPP_GLOBAL_Control
0x14001d156  mov     r8d, [rdi]; dwProcessId
0x14001d159  xor     edx, edx; bInheritHandle
0x14001d15b  mov     ecx, 100450h; dwDesiredAccess
0x14001d160  call    cs:__imp_OpenProcess
0x14001d167  nop     dword ptr [rax+rax+00h]
0x14001d16c  mov     r15, rax
0x14001d16f  mov     [rbp+57h+var_98], rax
0x14001d173  inc     rax
0x14001d176  mov     esi, 1
0x14001d17b  cmp     rax, rsi
0x14001d17e  jbe     loc_14001D8D9
0x14001d184  lea     rbx, [rdi+708h]
0x14001d18b  mov     rdx, rbx; pdwFlags
0x14001d18e  mov     rcx, r15; hProcess
0x14001d191  call    cs:__imp_WerGetFlags
0x14001d198  nop     dword ptr [rax+rax+00h]
0x14001d19d  test    eax, eax
0x14001d19f  js      short loc_14001D1CB
0x14001d1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1a8  cmp     rcx, r14
0x14001d1ab  jz      short loc_14001D1FF
0x14001d1ad  test    byte ptr [rcx+1Ch], 8
0x14001d1b1  jz      short loc_14001D1FF
0x14001d1b3  lea     edx, [rsi+47h]
0x14001d1b6  mov     r9d, [rbx]
0x14001d1b9  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d1c0  mov     rcx, [rcx+10h]
0x14001d1c4  call    WPP_SF_d
0x14001d1c9  jmp     short loc_14001D1F8
0x14001d1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1d2  cmp     rcx, r14
0x14001d1d5  jz      short loc_14001D1F5
0x14001d1d7  test    byte ptr [rcx+1Ch], 2
0x14001d1db  jz      short loc_14001D1F5
0x14001d1dd  mov     edx, 49h ; 'I'
0x14001d1e2  mov     r9d, eax
0x14001d1e5  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d1ec  mov     rcx, [rcx+10h]
0x14001d1f0  call    WPP_SF_d
0x14001d1f5  mov     [rbx], r13d
0x14001d1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1ff  cmp     [rdi+4], r13d
0x14001d203  jnz     loc_14001D311
0x14001d209  xor     edx, edx; th32ProcessID
0x14001d20b  lea     ecx, [rdx+4]; dwFlags
0x14001d20e  call    cs:__imp_CreateToolhelp32Snapshot
0x14001d215  nop     dword ptr [rax+rax+00h]
0x14001d21a  mov     r14, rax
0x14001d21d  mov     [rsp+120h+var_E0], rax
0x14001d222  xorps   xmm1, xmm1
0x14001d225  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x14001d229  movups  xmmword ptr [rbp+57h+var_90+0Ch], xmm1
0x14001d22d  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x14001d231  movups  xmmword ptr [rbp+57h+te.dwSize], xmm0
0x14001d235  movups  xmmword ptr [rbp+57h+te.th32OwnerProcessID], xmm1
0x14001d239  mov     [rbp+57h+te.dwSize], 1Ch
0x14001d240  lea     rdx, [rbp+57h+te]; lpte
0x14001d244  mov     rcx, rax; hSnapshot
0x14001d247  call    cs:__imp_Thread32First
0x14001d24e  nop     dword ptr [rax+rax+00h]
0x14001d253  test    eax, eax
0x14001d255  jnz     short loc_14001D2C5
0x14001d257  call    cs:__imp_GetLastError
0x14001d25e  nop     dword ptr [rax+rax+00h]
0x14001d263  mov     ebx, eax
0x14001d265  test    eax, eax
0x14001d267  jle     short loc_14001D272
0x14001d269  movzx   ebx, ax
0x14001d26c  or      ebx, 80070000h
0x14001d272  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d279  lea     rax, WPP_GLOBAL_Control
0x14001d280  cmp     rcx, rax
0x14001d283  jz      short loc_14001D2A4
0x14001d285  test    [rcx+1Ch], sil
0x14001d289  jz      short loc_14001D2A4
0x14001d28b  mov     edx, 4Ah ; 'J'
0x14001d290  mov     r9d, ebx
0x14001d293  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d29a  mov     rcx, [rcx+10h]
0x14001d29e  call    WPP_SF_d
0x14001d2a3  nop
0x14001d2a4  lea     rax, [r14+1]
0x14001d2a8  cmp     rax, rsi
0x14001d2ab  jbe     loc_14001D91E
0x14001d2b1  mov     rcx, r14; hObject
0x14001d2b4  call    cs:__imp_CloseHandle
0x14001d2bb  nop     dword ptr [rax+rax+00h]
0x14001d2c0  jmp     loc_14001D91E
0x14001d2c5  mov     eax, [rdi]
0x14001d2c7  cmp     [rbp+57h+te.th32OwnerProcessID], eax
0x14001d2ca  jz      short loc_14001D2E5
0x14001d2cc  lea     rdx, [rbp+57h+te]; lpte
0x14001d2d0  mov     rcx, r14; hSnapshot
0x14001d2d3  call    cs:__imp_Thread32Next
0x14001d2da  nop     dword ptr [rax+rax+00h]
0x14001d2df  test    eax, eax
0x14001d2e1  jnz     short loc_14001D2C5
0x14001d2e3  jmp     short loc_14001D2EB
0x14001d2e5  mov     eax, [rbp+57h+te.th32ThreadID]
0x14001d2e8  mov     [rdi+4], eax
0x14001d2eb  lea     rax, [r14+1]
0x14001d2ef  cmp     rax, rsi
0x14001d2f2  jbe     short loc_14001D303
0x14001d2f4  mov     rcx, r14; hObject
0x14001d2f7  call    cs:__imp_CloseHandle
0x14001d2fe  nop     dword ptr [rax+rax+00h]
0x14001d303  lea     r14, WPP_GLOBAL_Control
0x14001d30a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d311  cmp     rcx, r14
0x14001d314  jz      short loc_14001D335
0x14001d316  test    byte ptr [rcx+1Ch], 4
0x14001d31a  jz      short loc_14001D335
0x14001d31c  mov     edx, 4Bh ; 'K'
0x14001d321  mov     r9d, [rdi+4]
0x14001d325  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001d32c  mov     rcx, [rcx+10h]
0x14001d330  call    WPP_SF_d
0x14001d335  lea     r9, [rsp+120h+dwSize]; lpdwSize
0x14001d33a  mov     r8, r12; lpExeName
0x14001d33d  xor     edx, edx; dwFlags
0x14001d33f  mov     rcx, r15; hProcess
0x14001d342  call    cs:__imp_QueryFullProcessImageNameW
0x14001d349  nop     dword ptr [rax+rax+00h]
0x14001d34e  test    eax, eax
0x14001d350  jnz     short loc_14001D391
0x14001d352  call    cs:__imp_GetLastError
0x14001d359  nop     dword ptr [rax+rax+00h]
0x14001d35e  mov     ebx, eax
0x14001d360  test    eax, eax
0x14001d362  jle     short loc_14001D36D
0x14001d364  movzx   ebx, ax
0x14001d367  or      ebx, 80070000h
0x14001d36d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d374  cmp     rcx, r14
0x14001d377  jz      loc_14001D91E
0x14001d37d  test    [rcx+1Ch], sil
0x14001d381  jz      loc_14001D91E
0x14001d387  mov     edx, 4Ch ; 'L'
0x14001d38c  jmp     loc_14001D90B
0x14001d391  lea     rbx, [rdi+718h]
0x14001d398  lea     r14, [rdi+714h]
0x14001d39f  mov     r8, rbx; enum _HOSTED_PROCESS_TYPE *
0x14001d3a2  mov     rdx, r14; int *
0x14001d3a5  mov     rcx, r12; wchar_t *
0x14001d3a8  call    ?UtilIsHostedApp@@YAJPEB_WPEAHPEAW4_HOSTED_PROCESS_TYPE@@@Z; UtilIsHostedApp(wchar_t const *,int *,_HOSTED_PROCESS_TYPE *)
0x14001d3ad  test    eax, eax
0x14001d3af  jns     short loc_14001D3DF
0x14001d3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d3b8  lea     r12, WPP_GLOBAL_Control
0x14001d3bf  cmp     rcx, r12
0x14001d3c2  jz      loc_14001D569
0x14001d3c8  test    byte ptr [rcx+1Ch], 2
0x14001d3cc  jz      loc_14001D569
0x14001d3d2  mov     edx, 4Dh ; 'M'
0x14001d3d7  mov     r9d, eax
0x14001d3da  jmp     loc_14001D46B
0x14001d3df  cmp     [r14], r13d
0x14001d3e2  jz      loc_14001D562
0x14001d3e8  mov     ecx, [rbx]
0x14001d3ea  test    ecx, ecx
0x14001d3ec  jz      loc_14001D480
0x14001d3f2  cmp     ecx, 1
0x14001d3f5  jnz     loc_14001D562
0x14001d3fb  lea     rdx, [rdi+720h]
0x14001d402  mov     rcx, r15; hProcess
0x14001d405  call    ?UtilGetRundll32HostedAppName@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetRundll32HostedAppName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
  ... truncated ...
```

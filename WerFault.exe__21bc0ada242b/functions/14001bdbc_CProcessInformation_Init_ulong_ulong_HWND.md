# CProcessInformation::Init(ulong,ulong,HWND__ *)

- ea: `0x14001bdbc`
- end: `0x14001c7f1`
- name: `?Init@CProcessInformation@@QEAAJKKPEAUHWND__@@@Z`
- size: `2613`
- prototype: `__int64 __fastcall(CProcessInformation *this, DWORD, int, HWND)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019374`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400034ec`
- `0x140003b68`
- `0x14001444c`
- `0x140014474`
- `0x1400144b4`
- `0x140015a78`
- `0x140015b40`
- `0x14001aa8c`
- `0x14001bdbc`
- `0x14001cc04`
- `0x14001d1b8`
- `0x14002fe0c`
- `0x1400306f4`
- `0x140030968`
- `0x140030cd8`
- `0x140031e20`
- `0x140032628`
- `0x140032a48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c1a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c36f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c1a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c36f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c6fd`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001c753`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001c781`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001c753`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14001c781`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001c2e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14001c2e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c11e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c34e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c794`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c11e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c34e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c794`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14001c19a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x14001c19a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001bfe8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001bfe8`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x14001c013`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x14001c013`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001c137`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14001c137`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001c0bd`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14001c0bd`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001c08a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14001c08a`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001c3d5`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14001c3d5`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x14001c5f8`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x14001c5f8`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14001bf44`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14001bf44`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14001bec7`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14001bec7`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x14001bee8`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x14001bee8`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x14001bf30`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x14001bf30`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001c69b`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x14001c69b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProcessInformation::Init(CProcessInformation *this, DWORD a2, int a3, HWND a4)
{
  __int64 v6; // r9
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
  _DWORD *v24; // rbx
  int IsHostedApp; // eax
  CUserModeHangReport *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  int Rundll32HostedAppName; // eax
  unsigned int v30; // ebx
  HANDLE v31; // rbx
  DWORD v32; // r8d
  void *v33; // r14
  int SvchostInformation; // eax
  DWORD v35; // eax
  LONG PackageFullName; // eax
  __int64 v37; // rcx
  int ProcessAppSessionGuid; // eax
  int ProcessTelemetryTargetAppParams; // eax
  int ProcessTimelines; // eax
  __int64 v41; // rbx
  __int64 v42; // rcx
  __int16 *v43; // rdx
  __int64 v44; // r8
  _WORD *v45; // rax
  __int16 v46; // r9
  _WORD *v47; // rdx
  __int16 *v48; // rcx
  __int64 v49; // rdx
  _WORD *v50; // rax
  __int16 v51; // r8
  _WORD *v52; // rcx
  int v53; // eax
  _DWORD *v54; // rbx
  CUserModeHangReport *v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // r9
  int PackageIdentity; // eax
  __int64 v59; // r9
  signed int LastError; // eax
  DWORD EnvironmentVariableW; // eax
  bool v62; // cf
  int v63; // eax
  DWORD dwProcessId; // [rsp+30h] [rbp-99h] BYREF
  UINT32 packageFullNameLength; // [rsp+38h] [rbp-91h] BYREF
  DWORD dwSize; // [rsp+3Ch] [rbp-8Dh] BYREF
  HANDLE v68; // [rsp+40h] [rbp-89h]
  void *v69; // [rsp+48h] [rbp-81h]
  _WORD *v70; // [rsp+50h] [rbp-79h]
  _WORD v71[8]; // [rsp+58h] [rbp-71h] BYREF
  void *v72[2]; // [rsp+68h] [rbp-61h] BYREF
  _WORD v73[8]; // [rsp+78h] [rbp-51h] BYREF
  HANDLE v74; // [rsp+88h] [rbp-41h]
  _OWORD v75[2]; // [rsp+90h] [rbp-39h] BYREF
  THREADENTRY32 te; // [rsp+B0h] [rbp-19h] BYREF

  v6 = a2;
  dwProcessId = a2;
  v8 = (WCHAR *)((char *)this + 8);
  if ( *((_WORD *)this + 4) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
    v6 = dwProcessId;
  }
  dwSize = 260;
  packageFullNameLength = 0;
  v69 = v71;
  v70 = v71;
  v71[0] = 0;
  v72[0] = v73;
  v72[1] = v73;
  v73[0] = 0;
  v9 = 0;
  v74 = 0;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v6, a3);
    LODWORD(v6) = dwProcessId;
  }
  *(_DWORD *)this = v6;
  *((_DWORD *)this + 1) = a3;
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
  v74 = v9;
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
    v68 = Toolhelp32Snapshot;
    memset(v75, 0, 28);
    *(_OWORD *)&te.dwSize = v75[0];
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
      v59 = v15;
      goto LABEL_160;
    }
    goto LABEL_161;
  }
  v24 = (_DWORD *)((char *)this + 1816);
  IsHostedApp = UtilIsHostedApp(v8, (int *)this + 453, (CProcessInformation *)((char *)this + 1816));
  if ( IsHostedApp >= 0 )
  {
    if ( !*((_DWORD *)this + 453) )
      goto LABEL_90;
    if ( *v24 )
    {
      if ( *v24 == 1 )
      {
        Rundll32HostedAppName = UtilGetRundll32HostedAppName(v9);
        v30 = Rundll32HostedAppName;
        if ( Rundll32HostedAppName < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                91,
                WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
                (unsigned int)Rundll32HostedAppName);
              v26 = WPP_GLOBAL_Control;
            }
            if ( v26 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 2) != 0 )
            {
              v27 = 78;
              v28 = v30;
              goto LABEL_76;
            }
          }
        }
      }
    }
    else
    {
      v31 = 0;
      v68 = 0;
      v32 = *((_DWORD *)this + 1);
      v33 = 0;
      if ( v32 )
      {
        v31 = OpenThread(0x58u, 0, v32);
        v68 = v31;
        if ( (unsigned __int64)v31 + 1 <= 1 )
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v35 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v35);
          }
          v33 = v31;
        }
        else
        {
          v33 = v31;
        }
      }
      SvchostInformation = CProcessInformation::ExtractSvchostInformation(this, v9, v31);
      if ( SvchostInformation < 0
        && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
          (unsigned int)SvchostInformation);
      }
      if ( (unsigned __int64)v33 + 1 > 1 )
        CloseHandle(v33);
    }
  }
  else
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v27 = 77;
      v28 = (unsigned int)IsHostedApp;
LABEL_76:
      WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v28);
    }
  }
LABEL_90:
  packageFullNameLength = 128;
  *((_WORD *)this + 524) = 0;
  *((_DWORD *)this + 452) = 0;
  if ( !(unsigned __int8)IsGetPackageFullNamePresent() )
  {
    if ( (unsigned __int8)IsXerGetPackageIdentityPresent() )
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
        v59 = (unsigned int)PackageIdentity;
LABEL_160:
        WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v59);
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
      v41 = 2147483646;
      v42 = 2147483646;
      v43 = (__int16 *)v69;
      v44 = 131;
      v45 = (_WORD *)((char *)this + 1436);
      do
      {
        if ( !v42 )
          break;
        v46 = *v43;
        if ( !*v43 )
          break;
        ++v43;
        *v45++ = v46;
        --v42;
        --v44;
      }
      while ( v44 );
      v47 = v45 - 1;
      if ( v44 )
        v47 = v45;
      *v47 = 0;
      if ( !v44 )
        *((_WORD *)this + 718) = 0;
      if ( (int)PackageUtility::ParseApplicationId(v69, v47, v72) >= 0 )
      {
        v48 = (__int16 *)v72[0];
        v49 = 66;
        v50 = (_WORD *)((char *)this + 1304);
        do
        {
          if ( !v41 )
            break;
          v51 = *v48;
          if ( !*v48 )
            break;
          ++v48;
          *v50++ = v51;
          --v41;
          --v49;
        }
        while ( v49 );
        v52 = v50 - 1;
        if ( v49 )
          v52 = v50;
        *v52 = 0;
        if ( !v49 )
          *((_WORD *)this + 652) = 0;
      }
    }
    v53 = CProcessInformation::LookupMinClrVersion(this);
    if ( v53 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
        (unsigned int)v53);
    }
    v54 = (_DWORD *)((char *)this + 1864);
    if ( (unsigned int)GetProcessUIContextInformation(v9, (char *)this + 1864) )
    {
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_153;
      }
      v56 = 88;
      v57 = (unsigned int)*v54;
    }
    else
    {
      *v54 = 0;
      *((_DWORD *)this + 467) = 0;
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_153;
      }
      v56 = 87;
      v57 = 0;
    }
    WPP_SF_d(*((_QWORD *)v55 + 2), v56, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v57);
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
        MicrosoftTelemetryAssertTriggeredNoArgs(v37);
LABEL_145:
      *((_DWORD *)this + 452) = 1;
      goto LABEL_96;
    case 122:
      MicrosoftTelemetryAssertTriggeredNoArgs(v37);
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
  if ( !EnvironmentVariableW || (v62 = EnvironmentVariableW < 0x80, v63 = 1, !v62) )
    v63 = 0;
  *((_DWORD *)this + 452) |= v63;
  GetEnvironmentVariableW(L"_HANGREP_PKGRELAPPID", (LPWSTR)this + 652, 0x42u);
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  if ( v72[0] != v73 )
    operator delete(v72[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v69 != v71 )
    operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
  return v15;
}

```

## disassembly

```asm
0x14001bdbc  push    rbp
0x14001bdbe  push    rbx
0x14001bdbf  push    rsi
0x14001bdc0  push    rdi
0x14001bdc1  push    r12
0x14001bdc3  push    r13
0x14001bdc5  push    r14
0x14001bdc7  push    r15
0x14001bdc9  lea     rbp, [rsp-1Fh]
0x14001bdce  sub     rsp, 0E8h
0x14001bdd5  mov     rax, cs:__security_cookie
0x14001bddc  xor     rax, rsp
0x14001bddf  mov     [rbp+57h+var_50], rax
0x14001bde3  mov     rbx, r9
0x14001bde6  mov     esi, r8d
0x14001bde9  mov     r9d, edx
0x14001bdec  mov     rdi, rcx
0x14001bdef  mov     [rsp+120h+dwProcessId], edx
0x14001bdf3  lea     r12, [rcx+8]
0x14001bdf7  xor     r13d, r13d
0x14001bdfa  cmp     [r12], r13w
0x14001bdff  jz      short loc_14001BE0B
0x14001be01  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001be06  mov     r9d, [rsp+120h+dwProcessId]
0x14001be0b  mov     [rsp+120h+dwSize], 104h
0x14001be13  mov     [rsp+120h+packageFullNameLength], r13d
0x14001be18  lea     rax, [rbp+57h+var_C8]
0x14001be1c  mov     [rsp+120h+var_D8], rax
0x14001be21  lea     rax, [rbp+57h+var_C8]
0x14001be25  mov     [rbp+57h+var_D0], rax
0x14001be29  mov     [rbp+57h+var_C8], r13w
0x14001be2e  lea     rax, [rbp+57h+var_A8]
0x14001be32  mov     [rbp+57h+var_B8], rax
0x14001be36  lea     rax, [rbp+57h+var_A8]
0x14001be3a  mov     [rbp+57h+var_B0], rax
0x14001be3e  mov     [rbp+57h+var_A8], r13w
0x14001be43  mov     r15, r13
0x14001be46  mov     [rbp+57h+var_98], r13
0x14001be4a  lea     r14, WPP_GLOBAL_Control
0x14001be51  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be58  cmp     rcx, r14
0x14001be5b  jz      short loc_14001BE81
0x14001be5d  test    byte ptr [rcx+1Ch], 4
0x14001be61  jz      short loc_14001BE81
0x14001be63  mov     edx, 42h ; 'B'
0x14001be68  mov     dword ptr [rsp+120h+var_100], esi
0x14001be6c  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001be73  mov     rcx, [rcx+10h]
0x14001be77  call    WPP_SF_Dd
0x14001be7c  mov     r9d, [rsp+120h+dwProcessId]
0x14001be81  mov     [rdi], r9d
0x14001be84  mov     [rdi+4], esi
0x14001be87  test    rbx, rbx
0x14001be8a  jz      loc_14001BFDE
0x14001be90  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be97  cmp     rcx, r14
0x14001be9a  jz      short loc_14001BEBA
0x14001be9c  test    byte ptr [rcx+1Ch], 4
0x14001bea0  jz      short loc_14001BEBA
0x14001bea2  mov     edx, 43h ; 'C'
0x14001bea7  mov     r9, rbx
0x14001beaa  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001beb1  mov     rcx, [rcx+10h]
0x14001beb5  call    WPP_SF_q
0x14001beba  mov     [rsp+120h+dwProcessId], r13d
0x14001bebf  lea     rdx, [rsp+120h+dwProcessId]; lpdwProcessId
0x14001bec4  mov     rcx, rbx; hWnd
0x14001bec7  call    cs:__imp_GetWindowThreadProcessId
0x14001becd  mov     r14d, eax
0x14001bed0  mov     edx, [rsp+120h+dwProcessId]
0x14001bed4  cmp     edx, [rdi]
0x14001bed6  jnz     loc_14001BF90
0x14001bedc  cmp     eax, [rdi+4]
0x14001bedf  jnz     loc_14001BF90
0x14001bee5  mov     rcx, rbx; hwnd
0x14001bee8  call    cs:__imp_IsHungAppWindow
0x14001beee  test    eax, eax
0x14001bef0  jnz     loc_14001BFD7
0x14001bef6  bts     dword ptr [rdi+70Ch], 0Ch
0x14001befe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf05  lea     r14, WPP_GLOBAL_Control
0x14001bf0c  cmp     rcx, r14
0x14001bf0f  jz      short loc_14001BF2D
0x14001bf11  test    byte ptr [rcx+1Ch], 4
0x14001bf15  jz      short loc_14001BF2D
0x14001bf17  lea     edx, [rax+45h]
0x14001bf1a  mov     r9, rbx
0x14001bf1d  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001bf24  mov     rcx, [rcx+10h]
0x14001bf28  call    WPP_SF_q
0x14001bf2d  mov     rcx, rbx; hWnd
0x14001bf30  call    cs:__imp_IsWindowEnabled
0x14001bf36  test    eax, eax
0x14001bf38  jnz     loc_14001BFDE
0x14001bf3e  lea     edx, [rax+6]; uCmd
0x14001bf41  mov     rcx, rbx; hWnd
0x14001bf44  call    cs:__imp_GetWindow
0x14001bf4a  test    rax, rax
0x14001bf4d  jz      loc_14001BFDE
0x14001bf53  cmp     rax, rbx
0x14001bf56  jz      loc_14001BFDE
0x14001bf5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf63  cmp     rcx, r14
0x14001bf66  jz      short loc_14001BF86
0x14001bf68  test    byte ptr [rcx+1Ch], 4
0x14001bf6c  jz      short loc_14001BF86
0x14001bf6e  mov     edx, 46h ; 'F'
0x14001bf73  mov     r9, rax
0x14001bf76  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001bf7d  mov     rcx, [rcx+10h]
0x14001bf81  call    WPP_SF_q
0x14001bf86  bts     dword ptr [rdi+70Ch], 0Ah
0x14001bf8e  jmp     short loc_14001BFDE
0x14001bf90  mov     esi, 1
0x14001bf95  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf9c  lea     rax, WPP_GLOBAL_Control
0x14001bfa3  cmp     rcx, rax
0x14001bfa6  jz      short loc_14001BFC5
0x14001bfa8  test    [rcx+1Ch], sil
0x14001bfac  jz      short loc_14001BFC5
0x14001bfae  lea     edx, [rsi+43h]
0x14001bfb1  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001bfb8  mov     rcx, [rcx+10h]
0x14001bfbc  call    WPP_SF_
0x14001bfc1  mov     edx, [rsp+120h+dwProcessId]
0x14001bfc5  mov     r8d, r14d
0x14001bfc8  call    MicrosoftTelemetryAssertTriggeredArgs
0x14001bfcd  mov     ebx, 80070057h
0x14001bfd2  jmp     loc_14001C73C
0x14001bfd7  lea     r14, WPP_GLOBAL_Control
0x14001bfde  mov     r8d, [rdi]; dwProcessId
0x14001bfe1  xor     edx, edx; bInheritHandle
0x14001bfe3  mov     ecx, 100450h; dwDesiredAccess
0x14001bfe8  call    cs:__imp_OpenProcess
0x14001bfee  mov     r15, rax
0x14001bff1  mov     [rbp+57h+var_98], rax
0x14001bff5  inc     rax
0x14001bff8  mov     esi, 1
0x14001bffd  cmp     rax, rsi
0x14001c000  jbe     loc_14001C6FD
0x14001c006  lea     rbx, [rdi+708h]
0x14001c00d  mov     rdx, rbx; pdwFlags
0x14001c010  mov     rcx, r15; hProcess
0x14001c013  call    cs:__imp_WerGetFlags
0x14001c019  test    eax, eax
0x14001c01b  js      short loc_14001C047
0x14001c01d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c024  cmp     rcx, r14
0x14001c027  jz      short loc_14001C07B
0x14001c029  test    byte ptr [rcx+1Ch], 8
0x14001c02d  jz      short loc_14001C07B
0x14001c02f  lea     edx, [rsi+47h]
0x14001c032  mov     r9d, [rbx]
0x14001c035  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c03c  mov     rcx, [rcx+10h]
0x14001c040  call    WPP_SF_d
0x14001c045  jmp     short loc_14001C074
0x14001c047  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c04e  cmp     rcx, r14
0x14001c051  jz      short loc_14001C071
0x14001c053  test    byte ptr [rcx+1Ch], 2
0x14001c057  jz      short loc_14001C071
0x14001c059  mov     edx, 49h ; 'I'
0x14001c05e  mov     r9d, eax
0x14001c061  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c068  mov     rcx, [rcx+10h]
0x14001c06c  call    WPP_SF_d
0x14001c071  mov     [rbx], r13d
0x14001c074  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c07b  cmp     [rdi+4], r13d
0x14001c07f  jnz     loc_14001C169
0x14001c085  xor     edx, edx; th32ProcessID
0x14001c087  lea     ecx, [rdx+4]; dwFlags
0x14001c08a  call    cs:__imp_CreateToolhelp32Snapshot
0x14001c090  mov     r14, rax
0x14001c093  mov     [rsp+120h+var_E0], rax
0x14001c098  xorps   xmm1, xmm1
0x14001c09b  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x14001c09f  movups  xmmword ptr [rbp+57h+var_90+0Ch], xmm1
0x14001c0a3  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x14001c0a7  movups  xmmword ptr [rbp+57h+te.dwSize], xmm0
0x14001c0ab  movups  xmmword ptr [rbp+57h+te.th32OwnerProcessID], xmm1
0x14001c0af  mov     [rbp+57h+te.dwSize], 1Ch
0x14001c0b6  lea     rdx, [rbp+57h+te]; lpte
0x14001c0ba  mov     rcx, rax; hSnapshot
0x14001c0bd  call    cs:__imp_Thread32First
0x14001c0c3  test    eax, eax
0x14001c0c5  jnz     short loc_14001C129
0x14001c0c7  call    cs:__imp_GetLastError
0x14001c0cd  mov     ebx, eax
0x14001c0cf  test    eax, eax
0x14001c0d1  jle     short loc_14001C0DC
0x14001c0d3  movzx   ebx, ax
0x14001c0d6  or      ebx, 80070000h
0x14001c0dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c0e3  lea     rax, WPP_GLOBAL_Control
0x14001c0ea  cmp     rcx, rax
0x14001c0ed  jz      short loc_14001C10E
0x14001c0ef  test    [rcx+1Ch], sil
0x14001c0f3  jz      short loc_14001C10E
0x14001c0f5  mov     edx, 4Ah ; 'J'
0x14001c0fa  mov     r9d, ebx
0x14001c0fd  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c104  mov     rcx, [rcx+10h]
0x14001c108  call    WPP_SF_d
0x14001c10d  nop
0x14001c10e  lea     rax, [r14+1]
0x14001c112  cmp     rax, rsi
0x14001c115  jbe     loc_14001C73C
0x14001c11b  mov     rcx, r14; hObject
0x14001c11e  call    cs:__imp_CloseHandle
0x14001c124  jmp     loc_14001C73C
0x14001c129  mov     eax, [rdi]
0x14001c12b  cmp     [rbp+57h+te.th32OwnerProcessID], eax
0x14001c12e  jz      short loc_14001C143
0x14001c130  lea     rdx, [rbp+57h+te]; lpte
0x14001c134  mov     rcx, r14; hSnapshot
0x14001c137  call    cs:__imp_Thread32Next
0x14001c13d  test    eax, eax
0x14001c13f  jnz     short loc_14001C129
0x14001c141  jmp     short loc_14001C149
0x14001c143  mov     eax, [rbp+57h+te.th32ThreadID]
0x14001c146  mov     [rdi+4], eax
0x14001c149  lea     rax, [r14+1]
0x14001c14d  cmp     rax, rsi
0x14001c150  jbe     short loc_14001C15B
0x14001c152  mov     rcx, r14; hObject
0x14001c155  call    cs:__imp_CloseHandle
0x14001c15b  lea     r14, WPP_GLOBAL_Control
0x14001c162  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c169  cmp     rcx, r14
0x14001c16c  jz      short loc_14001C18D
0x14001c16e  test    byte ptr [rcx+1Ch], 4
0x14001c172  jz      short loc_14001C18D
0x14001c174  mov     edx, 4Bh ; 'K'
0x14001c179  mov     r9d, [rdi+4]
0x14001c17d  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c184  mov     rcx, [rcx+10h]
0x14001c188  call    WPP_SF_d
0x14001c18d  lea     r9, [rsp+120h+dwSize]; lpdwSize
0x14001c192  mov     r8, r12; lpExeName
0x14001c195  xor     edx, edx; dwFlags
0x14001c197  mov     rcx, r15; hProcess
0x14001c19a  call    cs:__imp_QueryFullProcessImageNameW
0x14001c1a0  test    eax, eax
0x14001c1a2  jnz     short loc_14001C1DD
0x14001c1a4  call    cs:__imp_GetLastError
0x14001c1aa  mov     ebx, eax
0x14001c1ac  test    eax, eax
0x14001c1ae  jle     short loc_14001C1B9
0x14001c1b0  movzx   ebx, ax
0x14001c1b3  or      ebx, 80070000h
0x14001c1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c1c0  cmp     rcx, r14
0x14001c1c3  jz      loc_14001C73C
0x14001c1c9  test    [rcx+1Ch], sil
0x14001c1cd  jz      loc_14001C73C
0x14001c1d3  mov     edx, 4Ch ; 'L'
0x14001c1d8  jmp     loc_14001C729
0x14001c1dd  lea     rbx, [rdi+718h]
0x14001c1e4  lea     r14, [rdi+714h]
0x14001c1eb  mov     r8, rbx; enum _HOSTED_PROCESS_TYPE *
0x14001c1ee  mov     rdx, r14; int *
0x14001c1f1  mov     rcx, r12; wchar_t *
0x14001c1f4  call    ?UtilIsHostedApp@@YAJPEB_WPEAHPEAW4_HOSTED_PROCESS_TYPE@@@Z; UtilIsHostedApp(wchar_t const *,int *,_HOSTED_PROCESS_TYPE *)
0x14001c1f9  test    eax, eax
0x14001c1fb  jns     short loc_14001C22B
0x14001c1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c204  lea     r12, WPP_GLOBAL_Control
0x14001c20b  cmp     rcx, r12
0x14001c20e  jz      loc_14001C3A3
0x14001c214  test    byte ptr [rcx+1Ch], 2
0x14001c218  jz      loc_14001C3A3
0x14001c21e  mov     edx, 4Dh ; 'M'
0x14001c223  mov     r9d, eax
0x14001c226  jmp     loc_14001C2B7
0x14001c22b  cmp     [r14], r13d
0x14001c22e  jz      loc_14001C39C
0x14001c234  mov     ecx, [rbx]
0x14001c236  test    ecx, ecx
0x14001c238  jz      loc_14001C2CC
0x14001c23e  cmp     ecx, 1
0x14001c241  jnz     loc_14001C39C
0x14001c247  lea     rdx, [rdi+720h]
0x14001c24e  mov     rcx, r15; hProcess
0x14001c251  call    ?UtilGetRundll32HostedAppName@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetRundll32HostedAppName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001c256  mov     ebx, eax
0x14001c258  test    eax, eax
0x14001c25a  jns     loc_14001C39C
0x14001c260  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c267  lea     r12, WPP_GLOBAL_Control
0x14001c26e  cmp     rcx, r12
0x14001c271  jz      loc_14001C3A3
0x14001c277  test    [rcx+1Ch], sil
0x14001c27b  jz      short loc_14001C29C
0x14001c27d  mov     edx, 5Bh ; '['
0x14001c282  mov     r9d, eax
0x14001c285  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c28c  mov     rcx, [rcx+10h]
0x14001c290  call    WPP_SF_d
  ... truncated ...
```

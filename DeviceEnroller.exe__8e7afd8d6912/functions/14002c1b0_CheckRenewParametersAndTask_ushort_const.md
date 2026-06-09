# CheckRenewParametersAndTask(ushort const *)

- ea: `0x14002c1b0`
- end: `0x14002c84e`
- name: `?CheckRenewParametersAndTask@@YAJPEBG@Z`
- size: `1694`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x14000a0fc`
- `0x14001d7ec`
- `0x14001d938`
- `0x14002b3a0`
- `0x14002c1b0`
- `0x140030410`
- `0x1400310c4`
- `0x1400347e8`
- `0x140034f24`
- `0x1400516ec`
- `0x140051a48`
- `0x140051b48`
- `0x140051d84`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14002c28f`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14002c28f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002c22e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002c22e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c3cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c261`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002c261`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c2e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c7d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c824`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c2e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c7d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002c824`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14002c3af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14002c3af`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002c3c1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14002c3c1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002c525`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002c542`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002c525`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002c542`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002c558`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002c6a5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002c558`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14002c6a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CheckRenewParametersAndTask(unsigned __int16 *a1)
{
  signed int DeviceCertExpiryTime; // ebx
  char IsStateSeparationEnabled; // al
  LSTATUS v5; // eax
  bool v6; // sf
  __int64 v7; // rcx
  const wchar_t *v8; // r8
  HKEY v9; // rcx
  int v10; // eax
  signed int LastError; // eax
  struct _FILETIME v12; // rbx
  DWORD dwHighDateTime; // r9d
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned int v16; // esi
  __int64 v17; // rax
  FILETIME v18; // rdx
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v20; // rdx
  LONG v21; // eax
  int v22; // esi
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int16 *v25; // r9
  unsigned __int16 *v26; // r8
  HKEY v27; // rcx
  int v28; // edi
  int v29; // eax
  __int64 v30; // rcx
  unsigned __int16 *v31; // r9
  unsigned __int16 *v32; // r8
  CEnrollmentLogger *v33; // rax
  HKEY v34; // rcx
  HKEY v35; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  __int64 v40; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+28h] [rbp-D8h]
  __int64 v42; // [rsp+28h] [rbp-D8h]
  __int64 v43; // [rsp+30h] [rbp-D0h]
  __int64 v44; // [rsp+30h] [rbp-D0h]
  __int64 v45; // [rsp+38h] [rbp-C8h]
  __int64 v46; // [rsp+38h] [rbp-C8h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+40h] [rbp-C0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v50; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME v51; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v52; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v53; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v54; // [rsp+70h] [rbp-90h] BYREF
  int v55; // [rsp+74h] [rbp-8Ch] BYREF
  int v56; // [rsp+78h] [rbp-88h] BYREF
  FILETIME v57; // [rsp+80h] [rbp-80h]
  FILETIME FileTime2; // [rsp+88h] [rbp-78h] BYREF
  FILETIME v59; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME FileTime; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-58h] BYREF
  struct _SYSTEMTIME v62; // [rsp+B8h] [rbp-48h] BYREF
  struct _SYSTEMTIME v63; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v64[264]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v65[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+448h]

  if ( !a1 )
  {
    DeviceCertExpiryTime = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return (unsigned int)DeviceCertExpiryTime;
  }
  v51 = 0;
  v52 = 0;
  v50 = 0;
  v54 = 0;
  v56 = 0;
  v53 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_14005EF50 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v6 = v5 < 0;
  if ( v5 > 0 )
    v6 = 1;
  if ( v6 || (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewNow", &v53) < 0 || !v53 )
  {
    DeviceCertExpiryTime = GetDeviceCertExpiryTime(a1, &v51);
    if ( DeviceCertExpiryTime < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
        goto LABEL_13;
      v8 = L"ClientCertExpirationDate";
      goto LABEL_12;
    }
    DeviceCertExpiryTime = GetRenewPeriodInSeconds(a1, &v52);
    if ( DeviceCertExpiryTime < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v8 = L"RenewPeriod";
LABEL_12:
        McTemplateU0zd_EventWriteTransfer(v7, EnterpriseDiagnosticsEnrollRenewFailedToReadRegKey, v8);
        goto LABEL_13;
      }
      goto LABEL_13;
    }
    DeviceCertExpiryTime = GetRenewRetryIntervalInSeconds(a1, 1, &v50);
    if ( DeviceCertExpiryTime < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v8 = L"RenewRetryInterval";
        goto LABEL_12;
      }
LABEL_13:
      v9 = hKey;
      hKey = 0;
      if ( v9 )
        RegCloseKey(v9);
      return (unsigned int)DeviceCertExpiryTime;
    }
    DeviceCertExpiryTime = GetRenewRetryIntervalInSeconds(a1, 0, &v54);
    if ( DeviceCertExpiryTime < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v8 = L"RenewRetryAfterExpiryInterval";
        goto LABEL_12;
      }
      goto LABEL_13;
    }
    v10 = IsROBOMode(a1, &v56);
    DeviceCertExpiryTime = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x132E,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v10,
        (int)phkResulta);
      goto LABEL_13;
    }
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    FileTime = 0;
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
LABEL_27:
      LastError = GetLastError();
      DeviceCertExpiryTime = LastError;
      if ( LastError > 0 )
        DeviceCertExpiryTime = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_13;
    }
    v12 = v51;
    dwHighDateTime = v51.dwHighDateTime;
    v57 = v51;
    v51 = 0;
    if ( !is_mul_ok(v52, 0x989680u) )
    {
      v14 = 4931;
      goto LABEL_74;
    }
    if ( *(_QWORD *)&v57 < 10000000 * (unsigned __int64)v52 )
    {
      v14 = 4935;
LABEL_74:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)0x80070216LL,
        (int)phkResulta);
      v35 = hKey;
      hKey = 0;
      if ( v35 )
        RegCloseKey(v35);
      return 2147942934LL;
    }
    v51 = 0;
    if ( !is_mul_ok(0xA8C0u, 0x989680u) )
    {
      v14 = 4943;
      goto LABEL_74;
    }
    v15 = *(_QWORD *)&v57 - 10000000LL * v52;
    if ( v15 < 0x649534E000LL )
    {
      v14 = 4946;
      goto LABEL_74;
    }
    v16 = v54;
    v57 = (FILETIME)(v15 - 432000000000LL);
    v17 = 10000000LL * v54;
    v51.dwHighDateTime = dwHighDateTime;
    v51.dwLowDateTime = v12.dwLowDateTime;
    if ( !is_mul_ok(v54, 0x989680u) )
    {
      v14 = 4957;
      goto LABEL_74;
    }
    v18 = (FILETIME)(v17 + *(_QWORD *)&v51);
    if ( v17 + *(_QWORD *)&v51 < *(unsigned __int64 *)&v51 )
    {
      v14 = 4961;
      goto LABEL_74;
    }
    FileTime2 = v57;
    *(_QWORD *)&v51 += v17;
    v59 = v18;
    v55 = 0;
    if ( (int)CheckAndFixRenewSchedule(a1, v57, v18, &v55) >= 0 && v55 )
      ScheduleRenewalSession(a1, v12, v52, v50, v16, v56);
    v50 = 0;
    if ( (int)IsLastRenewRecent(a1, (int *)&v50) >= 0 && v50 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      v20 = L"Last renew was within 12 hours";
LABEL_53:
      CEnrollmentLogger::LogRenewNotAllowed(Logger, v20, -2145910762);
      v27 = hKey;
      hKey = 0;
      if ( v27 )
        RegCloseKey(v27);
      return 2149056534LL;
    }
    v62 = 0;
    if ( !FileTimeToSystemTime(&FileTime2, &v62) )
      goto LABEL_27;
    v63 = 0;
    if ( !FileTimeToSystemTime(&v59, &v63) )
      goto LABEL_27;
    v21 = CompareFileTime(&FileTime, &FileTime2);
    if ( v21 < 0 )
    {
      memset_0(v65, 0, 0x208u);
      memset_0(v64, 0, 0x208u);
      LODWORD(v40) = SystemTime.wDay;
      LODWORD(phkResulta) = SystemTime.wMonth;
      v22 = StringCchPrintfW(
              v65,
              0x104u,
              L"%4d-%02d-%02dT%2d:%02d:%02d",
              SystemTime.wYear,
              phkResulta,
              v40,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond);
      LODWORD(v47) = v62.wSecond;
      LODWORD(v45) = v62.wMinute;
      LODWORD(v43) = v62.wHour;
      LODWORD(v41) = v62.wDay;
      LODWORD(phkResultb) = v62.wMonth;
      v23 = StringCchPrintfW(v64, 0x104u, L"%4d-%02d-%02dT%2d:%02d:%02d", v62.wYear, phkResultb, v41, v43, v45, v47);
      if ( v22 < 0 || v23 < 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          v25 = (unsigned __int16 *)&SubKey;
          v26 = (unsigned __int16 *)&SubKey;
          goto LABEL_51;
        }
      }
      else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v25 = v64;
        v26 = v65;
LABEL_51:
        McTemplateU0zz_EventWriteTransfer(v24, EnterpriseDiagnosticsEnrollRenewBeforeAllowedDate, v26, v25);
      }
      Logger = CEnrollmentLogger::GetLogger();
      v20 = L"Current time is at least 12 hours sooner than the earliest allowed renew window";
      goto LABEL_53;
    }
    if ( v21 > 0 && CompareFileTime(&FileTime, &v59) > 0 )
    {
      memset_0(v64, 0, 0x208u);
      memset_0(v65, 0, 0x208u);
      LODWORD(v40) = SystemTime.wDay;
      LODWORD(phkResulta) = SystemTime.wMonth;
      v28 = StringCchPrintfW(
              v64,
              0x104u,
              L"%4d-%02d-%02d %2d:%02d:%02d",
              SystemTime.wYear,
              phkResulta,
              v40,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond);
      LODWORD(v48) = v63.wSecond;
      LODWORD(v46) = v63.wMinute;
      LODWORD(v44) = v63.wHour;
      LODWORD(v42) = v63.wDay;
      LODWORD(phkResultc) = v63.wMonth;
      v29 = StringCchPrintfW(v65, 0x104u, L"%4d-%02d-%02d %2d:%02d:%02d", v63.wYear, phkResultc, v42, v44, v46, v48);
      if ( v28 < 0 || v29 < 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          v31 = (unsigned __int16 *)&SubKey;
          v32 = (unsigned __int16 *)&SubKey;
          goto LABEL_64;
        }
      }
      else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v31 = v65;
        v32 = v64;
LABEL_64:
        McTemplateU0zz_EventWriteTransfer(v30, EnterpriseDiagnosticsEnrollRenewPostExpirationDate, v32, v31);
      }
      v33 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogRenewNotAllowed(
        v33,
        L"Current time is later than the expected renew end time, but still allows renew",
        0);
    }
  }
  v34 = hKey;
  hKey = 0;
  if ( v34 )
    RegCloseKey(v34);
  return 0;
}

```

## disassembly

```asm
0x14002c1b0  push    rbp
0x14002c1b2  push    rbx
0x14002c1b3  push    rsi
0x14002c1b4  push    rdi
0x14002c1b5  push    r14
0x14002c1b7  push    r15
0x14002c1b9  lea     rbp, [rsp-418h]
0x14002c1c1  sub     rsp, 518h
0x14002c1c8  mov     rax, cs:__security_cookie
0x14002c1cf  xor     rax, rsp
0x14002c1d2  mov     [rbp+440h+var_40], rax
0x14002c1d9  xor     r15d, r15d
0x14002c1dc  mov     rdi, rcx
0x14002c1df  test    rcx, rcx
0x14002c1e2  jnz     short loc_14002C20B
0x14002c1e4  mov     rcx, [rbp+448h]; this
0x14002c1eb  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002c1f2  mov     ebx, 80070057h
0x14002c1f7  mov     edx, 12F0h; void *
0x14002c1fc  mov     r9d, ebx; char *
0x14002c1ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c204  mov     eax, ebx
0x14002c206  jmp     loc_14002C82F
0x14002c20b  mov     qword ptr [rsp+540h+var_4E0.dwLowDateTime], r15
0x14002c210  mov     [rsp+540h+var_4D8], r15d
0x14002c215  mov     [rsp+540h+var_4E8], r15d
0x14002c21a  mov     [rsp+540h+var_4D0], r15d
0x14002c21f  mov     [rsp+540h+var_4C8], r15d
0x14002c224  mov     [rsp+540h+var_4D4], r15d
0x14002c229  mov     [rsp+540h+hKey], r15
0x14002c22e  call    cs:__imp_RtlIsStateSeparationEnabled
0x14002c234  lea     rcx, off_14005EF50; "Software\\Microsoft\\Enrollments"
0x14002c23b  mov     r9d, 20019h; samDesired
0x14002c241  neg     al
0x14002c243  lea     rax, [rsp+540h+hKey]
0x14002c248  sbb     rdx, rdx
0x14002c24b  mov     [rsp+540h+phkResult], rax; int
0x14002c250  and     edx, 8
0x14002c253  xor     r8d, r8d; ulOptions
0x14002c256  mov     rdx, [rdx+rcx]; lpSubKey
0x14002c25a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002c261  call    cs:__imp_RegOpenKeyExW
0x14002c267  mov     r14d, 80070000h
0x14002c26d  test    eax, eax
0x14002c26f  jle     short loc_14002C279
0x14002c271  movzx   eax, ax
0x14002c274  or      eax, r14d
0x14002c277  test    eax, eax
0x14002c279  js      short loc_14002C2A4
0x14002c27b  mov     rcx, [rsp+540h+hKey]
0x14002c280  lea     r9, [rsp+540h+var_4D4]
0x14002c285  lea     r8, aRenewnow; "RenewNow"
0x14002c28c  mov     rdx, rdi
0x14002c28f  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14002c295  test    eax, eax
0x14002c297  js      short loc_14002C2A4
0x14002c299  cmp     [rsp+540h+var_4D4], r15d
0x14002c29e  jnz     loc_14002C7C2
0x14002c2a4  lea     rdx, [rsp+540h+var_4E0]; struct _FILETIME *
0x14002c2a9  mov     rcx, rdi; unsigned __int16 *
0x14002c2ac  call    ?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z; GetDeviceCertExpiryTime(ushort const *,_FILETIME *)
0x14002c2b1  mov     ebx, eax
0x14002c2b3  test    eax, eax
0x14002c2b5  jns     short loc_14002C2F4
0x14002c2b7  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x14002c2be  jz      short loc_14002C2D6
0x14002c2c0  lea     r8, aClientcertexpi; "ClientCertExpirationDate"
0x14002c2c7  mov     r9d, ebx
0x14002c2ca  lea     rdx, EnterpriseDiagnosticsEnrollRenewFailedToReadRegKey
0x14002c2d1  call    McTemplateU0zd_EventWriteTransfer
0x14002c2d6  mov     rcx, [rsp+540h+hKey]; hKey
0x14002c2db  mov     [rsp+540h+hKey], r15
0x14002c2e0  test    rcx, rcx
0x14002c2e3  jz      loc_14002C204
0x14002c2e9  call    cs:__imp_RegCloseKey
0x14002c2ef  jmp     loc_14002C204
0x14002c2f4  lea     rdx, [rsp+540h+var_4D8]; unsigned int *
0x14002c2f9  mov     rcx, rdi; unsigned __int16 *
0x14002c2fc  call    ?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z; GetRenewPeriodInSeconds(ushort const *,ulong *)
0x14002c301  mov     ebx, eax
0x14002c303  test    eax, eax
0x14002c305  jns     short loc_14002C319
0x14002c307  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x14002c30e  jz      short loc_14002C2D6
0x14002c310  lea     r8, aRenewperiod; "RenewPeriod"
0x14002c317  jmp     short loc_14002C2C7
0x14002c319  lea     r8, [rsp+540h+var_4E8]; unsigned int *
0x14002c31e  mov     edx, 1; int
0x14002c323  mov     rcx, rdi; unsigned __int16 *
0x14002c326  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x14002c32b  mov     ebx, eax
0x14002c32d  test    eax, eax
0x14002c32f  jns     short loc_14002C343
0x14002c331  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x14002c338  jz      short loc_14002C2D6
0x14002c33a  lea     r8, aRenewretryinte; "RenewRetryInterval"
0x14002c341  jmp     short loc_14002C2C7
0x14002c343  lea     r8, [rsp+540h+var_4D0]; unsigned int *
0x14002c348  xor     edx, edx; int
0x14002c34a  mov     rcx, rdi; unsigned __int16 *
0x14002c34d  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x14002c352  mov     ebx, eax
0x14002c354  test    eax, eax
0x14002c356  jns     short loc_14002C371
0x14002c358  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x14002c35f  jz      loc_14002C2D6
0x14002c365  lea     r8, aRenewretryafte; "RenewRetryAfterExpiryInterval"
0x14002c36c  jmp     loc_14002C2C7
0x14002c371  lea     rdx, [rsp+540h+var_4C8]; int *
0x14002c376  mov     rcx, rdi; unsigned __int16 *
0x14002c379  call    ?IsROBOMode@@YAJPEBGPEAH@Z; IsROBOMode(ushort const *,int *)
0x14002c37e  mov     ebx, eax
0x14002c380  test    eax, eax
0x14002c382  jns     short loc_14002C3A4
0x14002c384  mov     rcx, [rbp+448h]; this
0x14002c38b  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002c392  mov     r9d, eax; char *
0x14002c395  mov     edx, 132Eh; void *
0x14002c39a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c39f  jmp     loc_14002C2D6
0x14002c3a4  xorps   xmm0, xmm0
0x14002c3a7  lea     rcx, [rbp+440h+SystemTime]; lpSystemTime
0x14002c3ab  movups  xmmword ptr [rbp+440h+SystemTime.wYear], xmm0
0x14002c3af  call    cs:__imp_GetSystemTime
0x14002c3b5  lea     rdx, [rbp+440h+FileTime]; lpFileTime
0x14002c3b9  mov     qword ptr [rbp+440h+FileTime.dwLowDateTime], r15
0x14002c3bd  lea     rcx, [rbp+440h+SystemTime]; lpSystemTime
0x14002c3c1  call    cs:__imp_SystemTimeToFileTime
0x14002c3c7  test    eax, eax
0x14002c3c9  jnz     short loc_14002C3E6
0x14002c3cb  call    cs:__imp_GetLastError
0x14002c3d1  mov     ebx, eax
0x14002c3d3  test    eax, eax
0x14002c3d5  jle     loc_14002C2D6
0x14002c3db  movzx   ebx, ax
0x14002c3de  or      ebx, r14d
0x14002c3e1  jmp     loc_14002C2D6
0x14002c3e6  mov     rbx, qword ptr [rsp+540h+var_4E0.dwLowDateTime]
0x14002c3eb  mov     r10d, 989680h
0x14002c3f1  mov     r9d, [rsp+540h+var_4E0.dwHighDateTime]
0x14002c3f6  mov     eax, r10d
0x14002c3f9  mov     ecx, [rsp+540h+var_4D8]
0x14002c3fd  mul     rcx
0x14002c400  mov     dword ptr [rbp+440h+var_4C0+4], r9d
0x14002c404  mov     dword ptr [rbp+440h+var_4C0], ebx
0x14002c407  mov     r8, rax
0x14002c40a  mov     qword ptr [rsp+540h+var_4E0.dwLowDateTime], r15
0x14002c40f  test    rdx, rdx
0x14002c412  jnz     loc_14002C7F7
0x14002c418  mov     rcx, [rbp+440h+var_4C0]
0x14002c41c  cmp     rcx, rax
0x14002c41f  jnb     short loc_14002C42B
0x14002c421  mov     edx, 1347h
0x14002c426  jmp     loc_14002C7FC
0x14002c42b  mov     edx, 0A8C0h
0x14002c430  mov     qword ptr [rsp+540h+var_4E0.dwLowDateTime], r15
0x14002c435  mov     rax, r10
0x14002c438  mul     rdx
0x14002c43b  test    rdx, rdx
0x14002c43e  jnz     loc_14002C7F0
0x14002c444  sub     rcx, r8
0x14002c447  cmp     rcx, rax
0x14002c44a  jb      loc_14002C7E9
0x14002c450  mov     esi, [rsp+540h+var_4D0]
0x14002c454  sub     rcx, rax
0x14002c457  mov     rax, r10
0x14002c45a  mov     [rbp+440h+var_4C0], rcx
0x14002c45e  mul     rsi
0x14002c461  mov     [rsp+540h+var_4E0.dwHighDateTime], r9d
0x14002c466  mov     [rsp+540h+var_4E0.dwLowDateTime], ebx
0x14002c46a  test    rdx, rdx
0x14002c46d  jnz     loc_14002C7E2
0x14002c473  mov     rcx, qword ptr [rsp+540h+var_4E0.dwLowDateTime]
0x14002c478  lea     rdx, [rax+rcx]
0x14002c47c  cmp     rdx, rcx
0x14002c47f  jb      loc_14002C7DB
0x14002c485  mov     eax, dword ptr [rbp+440h+var_4C0+4]
0x14002c488  lea     r9, [rsp+540h+var_4CC]; int *
0x14002c48d  mov     [rbp+440h+FileTime2.dwHighDateTime], eax
0x14002c490  mov     rcx, rdi; unsigned __int16 *
0x14002c493  mov     eax, dword ptr [rbp+440h+var_4C0]
0x14002c496  mov     [rbp+440h+FileTime2.dwLowDateTime], eax
0x14002c499  mov     qword ptr [rsp+540h+var_4E0.dwLowDateTime], rdx
0x14002c49e  mov     eax, [rsp+540h+var_4E0.dwHighDateTime]
0x14002c4a2  mov     [rbp+440h+var_4B0.dwHighDateTime], eax
0x14002c4a5  mov     eax, edx
0x14002c4a7  mov     [rbp+440h+var_4B0.dwLowDateTime], edx
0x14002c4aa  mov     rdx, qword ptr [rbp+440h+FileTime2.dwLowDateTime]; struct _FILETIME
0x14002c4ae  mov     r8, qword ptr [rbp+440h+var_4B0.dwLowDateTime]; struct _FILETIME
0x14002c4b2  mov     [rsp+540h+var_4CC], r15d
0x14002c4b7  call    ?CheckAndFixRenewSchedule@@YAJPEBGU_FILETIME@@1PEAH@Z; CheckAndFixRenewSchedule(ushort const *,_FILETIME,_FILETIME,int *)
0x14002c4bc  test    eax, eax
0x14002c4be  js      short loc_14002C4E8
0x14002c4c0  cmp     [rsp+540h+var_4CC], r15d
0x14002c4c5  jz      short loc_14002C4E8
0x14002c4c7  mov     eax, [rsp+540h+var_4C8]
0x14002c4cb  mov     rdx, rbx; struct _FILETIME
0x14002c4ce  mov     r9d, [rsp+540h+var_4E8]; unsigned int
0x14002c4d3  mov     rcx, rdi; unsigned __int16 *
0x14002c4d6  mov     r8d, [rsp+540h+var_4D8]; unsigned int
0x14002c4db  mov     dword ptr [rsp+540h+var_518], eax; int
0x14002c4df  mov     dword ptr [rsp+540h+phkResult], esi; unsigned int
0x14002c4e3  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x14002c4e8  lea     rdx, [rsp+540h+var_4E8]; int *
0x14002c4ed  mov     [rsp+540h+var_4E8], r15d
0x14002c4f2  mov     rcx, rdi; unsigned __int16 *
0x14002c4f5  call    ?IsLastRenewRecent@@YAJPEBGPEAH@Z; IsLastRenewRecent(ushort const *,int *)
0x14002c4fa  test    eax, eax
0x14002c4fc  js      short loc_14002C516
0x14002c4fe  cmp     [rsp+540h+var_4E8], r15d
0x14002c503  jz      short loc_14002C516
0x14002c505  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14002c50a  lea     rdx, aLastRenewWasWi; "Last renew was within 12 hours"
0x14002c511  jmp     loc_14002C66A
0x14002c516  xorps   xmm0, xmm0
0x14002c519  lea     rdx, [rbp+440h+var_488]; lpSystemTime
0x14002c51d  lea     rcx, [rbp+440h+FileTime2]; lpFileTime
0x14002c521  movups  xmmword ptr [rbp+440h+var_488.wYear], xmm0
0x14002c525  call    cs:__imp_FileTimeToSystemTime
0x14002c52b  test    eax, eax
0x14002c52d  jz      loc_14002C3CB
0x14002c533  xorps   xmm0, xmm0
0x14002c536  lea     rdx, [rbp+440h+var_478]; lpSystemTime
0x14002c53a  lea     rcx, [rbp+440h+var_4B0]; lpFileTime
0x14002c53e  movups  xmmword ptr [rbp+440h+var_478.wYear], xmm0
0x14002c542  call    cs:__imp_FileTimeToSystemTime
0x14002c548  test    eax, eax
0x14002c54a  jz      loc_14002C3CB
0x14002c550  lea     rdx, [rbp+440h+FileTime2]; lpFileTime2
0x14002c554  lea     rcx, [rbp+440h+FileTime]; lpFileTime1
0x14002c558  call    cs:__imp_CompareFileTime
0x14002c55e  test    eax, eax
0x14002c560  jns     loc_14002C697
0x14002c566  mov     ebx, 208h
0x14002c56b  lea     rcx, [rbp+440h+var_250]; void *
0x14002c572  mov     r8d, ebx; Size
0x14002c575  xor     edx, edx; Val
0x14002c577  call    memset_0
0x14002c57c  mov     r8d, ebx; Size
0x14002c57f  lea     rcx, [rbp+440h+var_460]; void *
0x14002c583  xor     edx, edx; Val
0x14002c585  call    memset_0
0x14002c58a  movzx   ecx, [rbp+440h+SystemTime.wMinute]
0x14002c58e  mov     r14d, 104h
0x14002c594  movzx   edx, [rbp+440h+SystemTime.wHour]
0x14002c598  movzx   r8d, [rbp+440h+SystemTime.wDay]
0x14002c59d  movzx   eax, [rbp+440h+SystemTime.wSecond]
0x14002c5a1  movzx   r10d, [rbp+440h+SystemTime.wMonth]
0x14002c5a6  movzx   r9d, [rbp+440h+SystemTime.wYear]
0x14002c5ab  mov     [rsp+540h+var_500], eax
0x14002c5af  mov     dword ptr [rsp+540h+var_508], ecx
0x14002c5b3  lea     rcx, [rbp+440h+var_250]; unsigned __int16 *
0x14002c5ba  mov     dword ptr [rsp+540h+var_510], edx
0x14002c5be  mov     edx, r14d; unsigned __int64
0x14002c5c1  mov     dword ptr [rsp+540h+var_518], r8d
0x14002c5c6  lea     r8, a4d02d02dt2d02d; "%4d-%02d-%02dT%2d:%02d:%02d"
0x14002c5cd  mov     dword ptr [rsp+540h+phkResult], r10d
0x14002c5d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002c5d7  movzx   ecx, [rbp+440h+var_488.wSecond]
0x14002c5db  lea     r8, a4d02d02dt2d02d; "%4d-%02d-%02dT%2d:%02d:%02d"
0x14002c5e2  movzx   r10d, [rbp+440h+var_488.wMinute]
0x14002c5e7  mov     edx, r14d; unsigned __int64
0x14002c5ea  movzx   r11d, [rbp+440h+var_488.wHour]
0x14002c5ef  mov     esi, eax
0x14002c5f1  movzx   ebx, [rbp+440h+var_488.wDay]
0x14002c5f5  movzx   edi, [rbp+440h+var_488.wMonth]
0x14002c5f9  movzx   r9d, [rbp+440h+var_488.wYear]
0x14002c5fe  mov     [rsp+540h+var_500], ecx
0x14002c602  lea     rcx, [rbp+440h+var_460]; unsigned __int16 *
0x14002c606  mov     dword ptr [rsp+540h+var_508], r10d
0x14002c60b  mov     dword ptr [rsp+540h+var_510], r11d
0x14002c610  mov     dword ptr [rsp+540h+var_518], ebx
0x14002c614  mov     dword ptr [rsp+540h+phkResult], edi
0x14002c618  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002c61d  test    esi, esi
0x14002c61f  js      short loc_14002C63B
0x14002c621  test    eax, eax
0x14002c623  js      short loc_14002C63B
0x14002c625  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x14002c62c  jz      short loc_14002C65E
0x14002c62e  lea     r9, [rbp+440h+var_460]
0x14002c632  lea     r8, [rbp+440h+var_250]
0x14002c639  jmp     short loc_14002C652
0x14002c63b  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x14002c642  jz      short loc_14002C65E
0x14002c644  lea     r9, SubKey
0x14002c64b  lea     r8, SubKey
0x14002c652  lea     rdx, EnterpriseDiagnosticsEnrollRenewBeforeAllowedDate
0x14002c659  call    McTemplateU0zz_EventWriteTransfer
0x14002c65e  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14002c663  lea     rdx, aCurrentTimeIsA; "Current time is at least 12 hours soone"...
0x14002c66a  mov     r8d, 80180016h; int
0x14002c670  mov     rcx, rax; this
0x14002c673  call    ?LogRenewNotAllowed@CEnrollmentLogger@@QEAAXPEBGJ@Z; CEnrollmentLogger::LogRenewNotAllowed(ushort const *,long)
0x14002c678  mov     rcx, [rsp+540h+hKey]; hKey
0x14002c67d  mov     [rsp+540h+hKey], r15
0x14002c682  test    rcx, rcx
0x14002c685  jz      short loc_14002C68D
0x14002c687  call    cs:__imp_RegCloseKey
0x14002c68d  mov     eax, 80180016h
  ... truncated ...
```

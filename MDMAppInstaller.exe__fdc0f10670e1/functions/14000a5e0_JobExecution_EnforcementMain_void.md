# JobExecution::EnforcementMain(void *)

- ea: `0x14000a5e0`
- end: `0x14000b296`
- name: `?EnforcementMain@JobExecution@@CAKPEAX@Z`
- size: `3254`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140003674`
- `0x1400036ac`
- `0x140003d00`
- `0x140006480`
- `0x1400068c8`
- `0x14000740c`
- `0x1400074d4`
- `0x14000775c`
- `0x140007f14`
- `0x140008600`
- `0x140008e80`
- `0x140009598`
- `0x1400095f8`
- `0x14000a5e0`
- `0x140011c90`
- `0x140011d58`
- `0x140012878`
- `0x140012fe0`
- `0x14001309c`
- `0x140013170`
- `0x14001326c`
- `0x14001668c`
- `0x140016ecc`
- `0x140017610`
- `0x140018258`
- `0x14001a8aa`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x14000ac6b`
- `ADVAPI32!RevertToSelf` at `0x14000b128`
- `ADVAPI32!RevertToSelf` at `0x14000ac6b`
- `ADVAPI32!RevertToSelf` at `0x14000b128`
- `ADVAPI32!CreateProcessAsUserW` at `0x14000ad71`
- `ADVAPI32!CreateProcessAsUserW` at `0x14000ad71`
- `KERNEL32!GetExitCodeProcess` at `0x14000aeaa`
- `KERNEL32!GetExitCodeProcess` at `0x14000aeaa`
- `KERNEL32!CreateProcessW` at `0x14000adfc`
- `KERNEL32!CreateProcessW` at `0x14000adfc`
- `KERNEL32!GetTempFileNameW` at `0x14000ab88`
- `KERNEL32!GetTempFileNameW` at `0x14000ab88`
- `KERNEL32!GetSystemDirectoryW` at `0x14000a73a`
- `KERNEL32!GetSystemDirectoryW` at `0x14000a73a`
- `KERNEL32!LeaveCriticalSection` at `0x14000b1c7`
- `KERNEL32!LeaveCriticalSection` at `0x14000b1c7`
- `KERNEL32!EnterCriticalSection` at `0x14000b19b`
- `KERNEL32!EnterCriticalSection` at `0x14000b19b`
- `KERNEL32!DeleteFileW` at `0x14000b04f`
- `KERNEL32!DeleteFileW` at `0x14000b13a`
- `KERNEL32!DeleteFileW` at `0x14000b04f`
- `KERNEL32!DeleteFileW` at `0x14000b13a`
- `KERNEL32!WaitForSingleObject` at `0x14000ae93`
- `KERNEL32!WaitForSingleObject` at `0x14000ae93`
- `KERNEL32!CloseHandle` at `0x14000b1dd`
- `KERNEL32!CloseHandle` at `0x14000b1ec`
- `KERNEL32!CloseHandle` at `0x14000b1fa`
- `KERNEL32!CloseHandle` at `0x14000b1dd`
- `KERNEL32!CloseHandle` at `0x14000b1ec`
- `KERNEL32!CloseHandle` at `0x14000b1fa`
- `KERNEL32!GetLastError` at `0x14000ab92`
- `KERNEL32!GetLastError` at `0x14000ad06`
- `KERNEL32!GetLastError` at `0x14000ad7f`
- `KERNEL32!GetLastError` at `0x14000ae06`
- `KERNEL32!GetLastError` at `0x14000aeb4`
- `KERNEL32!GetLastError` at `0x14000b05d`
- `KERNEL32!GetLastError` at `0x14000b103`
- `KERNEL32!GetLastError` at `0x14000b144`
- `KERNEL32!GetLastError` at `0x14000ab92`
- `KERNEL32!GetLastError` at `0x14000ad06`
- `KERNEL32!GetLastError` at `0x14000ad7f`
- `KERNEL32!GetLastError` at `0x14000ae06`
- `KERNEL32!GetLastError` at `0x14000aeb4`
- `KERNEL32!GetLastError` at `0x14000b05d`
- `KERNEL32!GetLastError` at `0x14000b103`
- `KERNEL32!GetLastError` at `0x14000b144`
- `msvcrt!wcscat_s` at `0x14000a889`
- `msvcrt!wcscat_s` at `0x14000a889`
- `USERENV!CreateEnvironmentBlock` at `0x14000acfc`
- `USERENV!CreateEnvironmentBlock` at `0x14000acfc`
- `USERENV!DestroyEnvironmentBlock` at `0x14000b169`
- `USERENV!DestroyEnvironmentBlock` at `0x14000b169`
- `msi!__imp_MsiAdvertiseProductW` at `0x14000abd5`
- `msi!__imp_MsiAdvertiseProductW` at `0x14000abd5`
- `msi!__imp_MsiAdvertiseScriptW` at `0x14000ac49`
- `msi!__imp_MsiAdvertiseScriptW` at `0x14000ac49`

## string_xrefs

- `0x14000a6f4`: `+ Entering enforcement thread for job %1.`
- `0x14000a81d`: `Failed to get MDM temp folder. Error 0x%1!x!`
- `0x14000ab50`: `Failed to get MDM temp folder. Error 0x%1!x!`
- `0x14000a876`: `\msiexec.exe`
- `0x14000a9b1`: `REINSTALL`
- `0x14000a9c0`: `REINSTALL`
- `0x14000aa6c`: `REINSTALL`
- `0x14000aa7b`: `REINSTALL`
- `0x14000a9e6`: ` REINSTALL=ALL `
- `0x14000aa15`: `REINSTALLMODE`
- `0x14000aa46`: ` REINSTALLMODE=vomus `
- `0x14000aab7`: `Job %1 may be trying to install a minor upgrade, but the MinorUpgradeAllowed node is not set to true.`
- `0x14000ab09`: `Run command "%1"`
- `0x14000aba9`: `Failed to get temp file name. Error 0x%1!x!`
- `0x14000ac26`: `Failed to impersonate before advertise MSI script. Error 0x%1!x!`
- `0x14000ac93`: `Unexpected empty user SID for user assignment job %1`
- `0x14000acd7`: `Failed to get user token before perform enforcement. Error 0x%1!x!`
- `0x14000adad`: `Failed to create process as user %1. Error 0x%2!x!`
- `0x14000ae1d`: `Failed to create process. Error 0x%1!x!`
- `0x14000b02d`: `Enforcement command succeeded. (Win32 return=%1!d!. HR=0x%2!x!)`
- `0x14000b073`: `Failed to delete file %1 hr=0x%2!x!`
- `0x14000afb1`: `Enforcement command failed! (Win32 return=%1!d!. HR=0x%2!x!.)`
- `0x14000b0f7`: `"%1" didn't complete in %2!d! minutes.`
- `0x14000b154`: `Failed to delete advertisement script file %1 hr=0x%2!x!`
- `0x14000b216`: `+ Exiting enforcement thread for job %1.`

## pseudocode

```c
__int64 __fastcall JobExecution::EnforcementMain(PVOID Parameter)
{
  HANDLE v2; // r14
  unsigned int v3; // ebx
  _QWORD *v4; // rdx
  char v5; // r15
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rbx
  bool v11; // si
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rdx
  LPCWSTR *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // rbx
  __int64 v35; // rdx
  _QWORD *v36; // rdx
  LPWSTR *v37; // rdx
  int MdmTempFolder; // eax
  const WCHAR *v39; // rcx
  signed int v40; // eax
  const WCHAR *v41; // rcx
  signed int v42; // eax
  wchar_t *v43; // rax
  int v44; // eax
  signed int v45; // eax
  _QWORD *v46; // rdx
  wchar_t *v47; // rcx
  int UserTokenFromSid; // eax
  signed int v49; // eax
  WCHAR *v50; // r8
  __int64 v51; // rcx
  signed int v52; // eax
  wchar_t **v53; // rdx
  WCHAR *v54; // rdx
  signed int LastError; // eax
  __int64 *v56; // rdx
  wchar_t **v57; // r9
  _QWORD *v58; // r8
  DWORD v59; // eax
  int v60; // ecx
  int v61; // ecx
  signed int v62; // eax
  __int64 v63; // rdx
  __int64 *v64; // rdx
  wchar_t **v65; // rcx
  _QWORD *v66; // rax
  LPWSTR *v67; // r9
  LPCWSTR *v68; // r8
  __int64 *v69; // rdx
  wchar_t **v70; // r9
  _QWORD *v71; // r8
  const WCHAR *v72; // rcx
  DWORD v73; // eax
  LPCWSTR *v74; // rdx
  wchar_t **v75; // rax
  _QWORD *v76; // r9
  LPWSTR *v77; // r8
  LPWSTR *v78; // rdx
  signed int v79; // eax
  DWORD v80; // eax
  __int64 v81; // rcx
  __int64 v82; // rax
  int v83; // ecx
  int v84; // r8d
  _QWORD *v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rdx
  char lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  char dwCreationFlags; // [rsp+30h] [rbp-D0h]
  DWORD ExitCode; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  char v95; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  LPVOID Environment; // [rsp+98h] [rbp-68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR lpCommandLine[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v100; // [rsp+128h] [rbp+28h]
  LPCWSTR lpFileName[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v102; // [rsp+148h] [rbp+48h]
  _BYTE v103[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v104[32]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v105[3]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v106; // [rsp+1A8h] [rbp+A8h]
  wchar_t *String2[3]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int64 v108; // [rsp+1C8h] [rbp+C8h]
  ULONG SessionId; // [rsp+1D0h] [rbp+D0h]
  char v110[72]; // [rsp+1D8h] [rbp+D8h] BYREF
  int v111; // [rsp+220h] [rbp+120h]
  unsigned int v112; // [rsp+230h] [rbp+130h]
  LPCWSTR szPackagePath[16]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v114[16]; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v115; // [rsp+2E8h] [rbp+1E8h]
  int v116; // [rsp+2F8h] [rbp+1F8h]
  unsigned int v117; // [rsp+304h] [rbp+204h]
  char v118; // [rsp+314h] [rbp+214h]
  _WORD v119[8]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v120; // [rsp+370h] [rbp+270h]
  __int64 v121; // [rsp+378h] [rbp+278h]
  unsigned int v122; // [rsp+380h] [rbp+280h]
  LPCWSTR lpPathName[5]; // [rsp+388h] [rbp+288h] BYREF
  WCHAR TempFileName[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  WCHAR Buffer[264]; // [rsp+5C0h] [rbp+4C0h] BYREF

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  std::wstring::wstring(lpCommandLine, &word_14001E5B4);
  v102 = 7;
  lpFileName[2] = 0;
  LOWORD(lpFileName[0]) = 0;
  ExitCode = 0;
  _Job::_Job((_Job *)v105);
  v121 = 7;
  v120 = 0;
  v119[0] = 0;
  v122 = 0;
  v2 = 0;
  hToken = 0;
  std::wstring::wstring(lpPathName, &word_14001E5B4);
  memset_0(TempFileName, 0, 0x208u);
  Environment = 0;
  if ( !Parameter )
  {
    v3 = -2147024809;
    goto LABEL_161;
  }
  _Job::operator=(v105, Parameter);
  v4 = v105;
  if ( v106 >= 8 )
    v4 = (_QWORD *)v105[0];
  LogInfo(L"+ Entering enforcement thread for job %1.", v4);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 1;
  StartupInfo.wShowWindow = 0;
  StartupInfo.lpDesktop = (LPWSTR)&word_14001E5B4;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_6;
  if ( v111 == 1 && !szPackagePath[2] )
  {
    LogError(L"The value for DownloadLocation is empty.");
LABEL_6:
    v3 = -2147418113;
    goto LABEL_159;
  }
  v5 = 0;
  v6 = std::wstring::wstring(v104, v114);
  ToUpperCase(v103, v6);
  v7 = std::char_traits<unsigned short>::length(L"/L");
  v10 = std::wstring::find(v9, v8, v9, v7);
  v11 = v10 == -1;
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v103, v12, 0);
  if ( v10 == -1 )
  {
    if ( (int)GetMdmTempFolder(String2, SessionId, lpFileName) < 0 )
    {
      LogError(L"Failed to get MDM temp folder. Error 0x%1!x!", 0);
      v11 = 0;
    }
    else
    {
      std::wstring::append(lpFileName, L"\\");
      std::wstring::append(lpFileName, v105, 0, -1);
      std::wstring::append(lpFileName, L".log");
    }
  }
  v13 = std::wstring::wstring(v103, v114);
  ToUpperCase(v104, v13);
  v14 = std::char_traits<unsigned short>::length(L"/QUIET");
  v17 = std::wstring::find(v16, v15, v16, v14);
  LOBYTE(v18) = 1;
  std::wstring::_Tidy(v104, v18, 0);
  wcscat_s(Buffer, 0x104u, L"\\msiexec.exe");
  std::wstring::append(lpCommandLine, L"\"");
  std::wstring::append(lpCommandLine, Buffer);
  std::wstring::append(lpCommandLine, L"\"");
  if ( v17 == -1 )
    std::wstring::append(lpCommandLine, L" /quiet ");
  if ( v11 )
  {
    std::wstring::append(lpCommandLine, L" /l*v \"");
    v19 = lpFileName;
    if ( v102 >= 8 )
      v19 = (LPCWSTR *)lpFileName[0];
    std::wstring::append(lpCommandLine, v19);
    std::wstring::append(lpCommandLine, L"\" ");
  }
  if ( v111 == 1 )
  {
    std::wstring::append(lpCommandLine, L" /qn /i \"");
    std::wstring::append(lpCommandLine, szPackagePath, 0, -1);
    std::wstring::append(lpCommandLine, L"\" ");
  }
  else
  {
    std::wstring::append(lpCommandLine, L" /qn ");
    std::wstring::append(lpCommandLine, L" /x ");
    std::wstring::append(lpCommandLine, v110, 0, -1);
  }
  if ( v118 )
  {
    v20 = std::wstring::wstring(v103, v114);
    ToUpperCase(v104, v20);
    v21 = std::char_traits<unsigned short>::length(L"REINSTALL");
    v23 = std::wstring::find(v22, L"REINSTALL", v22, v21);
    LOBYTE(v24) = 1;
    std::wstring::_Tidy(v104, v24, 0);
    if ( v23 == -1 )
      std::wstring::append(lpCommandLine, L" REINSTALL=ALL ");
    v25 = std::wstring::wstring(v103, v114);
    ToUpperCase(v104, v25);
    v26 = std::char_traits<unsigned short>::length(L"REINSTALLMODE");
    v29 = std::wstring::find(v28, v27, v28, v26);
    LOBYTE(v30) = 1;
    std::wstring::_Tidy(v104, v30, 0);
    if ( v29 == -1 )
      std::wstring::append(lpCommandLine, L" REINSTALLMODE=vomus ");
  }
  else
  {
    v31 = std::wstring::wstring(v103, v114);
    ToUpperCase(v104, v31);
    v32 = std::char_traits<unsigned short>::length(L"REINSTALL");
    v34 = std::wstring::find(v33, L"REINSTALL", v33, v32);
    LOBYTE(v35) = 1;
    std::wstring::_Tidy(v104, v35, 0);
    if ( v34 != -1 )
    {
      v36 = v105;
      if ( v106 >= 8 )
        v36 = (_QWORD *)v105[0];
      LogWarn(
        L"Job %1 may be trying to install a minor upgrade, but the MinorUpgradeAllowed node is not set to true.",
        v36);
    }
  }
  if ( v111 == 1 && v115 )
  {
    std::wstring::append(lpCommandLine, L" ");
    std::wstring::append(lpCommandLine, v114, 0, -1);
  }
  v37 = lpCommandLine;
  if ( v100 >= 8 )
    v37 = (LPWSTR *)lpCommandLine[0];
  LogInfo(L"Run command \"%1\"", v37);
  if ( v116 )
  {
    v3 = 0;
    v54 = (WCHAR *)lpCommandLine;
    if ( v100 >= 8 )
      v54 = lpCommandLine[0];
    if ( !CreateProcessW(0, v54, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      LogError(L"Failed to create process. Error 0x%1!x!", v3);
      goto LABEL_159;
    }
    goto LABEL_86;
  }
  if ( v111 != 1 )
  {
LABEL_60:
    if ( !String2[2] )
    {
      v46 = v105;
      if ( v106 >= 8 )
        v46 = (_QWORD *)v105[0];
      LogError(L"Unexpected empty user SID for user assignment job %1", v46);
      v3 = -2147418113;
      goto LABEL_156;
    }
    v47 = (wchar_t *)String2;
    if ( v108 >= 8 )
      v47 = String2[0];
    UserTokenFromSid = GetUserTokenFromSid(v47, SessionId, &hToken);
    v3 = UserTokenFromSid;
    if ( UserTokenFromSid < 0 )
    {
      LogError(L"Failed to get user token before perform enforcement. Error 0x%1!x!", (unsigned int)UserTokenFromSid);
      v2 = hToken;
      goto LABEL_156;
    }
    v2 = hToken;
    if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
    {
      v49 = GetLastError();
      v3 = v49;
      if ( v49 > 0 )
        v3 = (unsigned __int16)v49 | 0x80070000;
      LogError(L"Failed to get environment block before perform enforcement. Error 0x%1!x!", v3);
      goto LABEL_156;
    }
    v50 = (WCHAR *)lpCommandLine;
    if ( v100 >= 8 )
      v50 = lpCommandLine[0];
    if ( !CreateProcessAsUserW(v2, 0, v50, 0, 0, 0, 0x1000410u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v52 = GetLastError();
      v3 = v52;
      if ( v52 > 0 )
        v3 = (unsigned __int16)v52 | 0x80070000;
      v53 = String2;
      if ( v108 >= 8 )
        v53 = (wchar_t **)String2[0];
      LogError(L"Failed to create process as user %1. Error 0x%2!x!", v53, v3);
      goto LABEL_156;
    }
LABEL_86:
    if ( v111 == 1 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) == 0 )
        goto LABEL_96;
      v56 = AppInstallStarted;
    }
    else
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) == 0 )
        goto LABEL_96;
      v56 = AppUninstallStarted;
    }
    v57 = String2;
    if ( v108 >= 8 )
      v57 = (wchar_t **)String2[0];
    v58 = v105;
    if ( v106 >= 8 )
      v58 = (_QWORD *)v105[0];
    McTemplateU0zz_EventWriteTransfer(v51, v56, v58, v57);
LABEL_96:
    v59 = WaitForSingleObject(ProcessInformation.hProcess, 60000 * v117);
    if ( v59 )
    {
      if ( v59 == 258 )
      {
        if ( (byte_14002B9C1 & 0x40) != 0 )
        {
          v75 = String2;
          if ( v108 >= 8 )
            v75 = (wchar_t **)String2[0];
          v76 = v105;
          if ( v106 >= 8 )
            LODWORD(v76) = v105[0];
          v77 = lpCommandLine;
          if ( v100 >= 8 )
            LODWORD(v77) = lpCommandLine[0];
          McTemplateU0zzz_EventWriteTransfer(
            v60,
            (unsigned int)AppEnforcementTimeout,
            (_DWORD)v77,
            (_DWORD)v76,
            (__int64)v75);
        }
        v3 = -2147417825;
        v78 = lpCommandLine;
        if ( v100 >= 8 )
          v78 = (LPWSTR *)lpCommandLine[0];
        LogWarn(L"\"%1\" didn't complete in %2!d! minutes.", v78, v117);
      }
      else
      {
        v79 = GetLastError();
        if ( v79 > 0 )
          v79 = (unsigned __int16)v79 | 0x80070000;
        LogError(L"Enforcement failed with error. Error 0x%1!x!", (unsigned int)v79);
      }
      goto LABEL_156;
    }
    if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      v62 = GetLastError();
      v3 = v62;
      if ( v62 > 0 )
        v3 = (unsigned __int16)v62 | 0x80070000;
      LogError(L"Failed to get process exit code. Error 0x%1!x!", v3);
      goto LABEL_156;
    }
    v63 = ExitCode;
    if ( (int)ExitCode > 0 )
      v3 = (unsigned __int16)ExitCode | 0x80070000;
    else
      v3 = ExitCode;
    if ( ExitCode != 3010 && ExitCode != 1641 && ExitCode != 1618 && ExitCode != 1707 && ExitCode )
    {
      if ( v111 == 1 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
        {
          dwCreationFlags = ExitCode;
          v64 = AppInstallFailure;
LABEL_114:
          v65 = String2;
          if ( v108 >= 8 )
            v65 = (wchar_t **)String2[0];
          v66 = v105;
          if ( v106 >= 8 )
            v66 = (_QWORD *)v105[0];
          v67 = lpCommandLine;
          if ( v100 >= 8 )
            LODWORD(v67) = lpCommandLine[0];
          v68 = lpFileName;
          if ( v102 >= 8 )
            LODWORD(v68) = lpFileName[0];
          McTemplateU0zzzzd_EventWriteTransfer(
            (_DWORD)v65,
            (_DWORD)v64,
            (_DWORD)v68,
            (_DWORD)v67,
            (__int64)v66,
            (__int64)v65,
            dwCreationFlags);
          v63 = ExitCode;
        }
      }
      else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      {
        dwCreationFlags = ExitCode;
        v64 = AppUninstallFailure;
        goto LABEL_114;
      }
      LogError(L"Enforcement command failed! (Win32 return=%1!d!. HR=0x%2!x!.)", v63, v3);
      goto LABEL_156;
    }
    if ( v111 == 1 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
      {
        lpThreadAttributes = ExitCode;
        v69 = AppInstallSuccess;
LABEL_129:
        v70 = String2;
        if ( v108 >= 8 )
          LODWORD(v70) = String2[0];
        v71 = v105;
        if ( v106 >= 8 )
          LODWORD(v71) = v105[0];
        McTemplateU0zzd_EventWriteTransfer(v61, (_DWORD)v69, (_DWORD)v71, (_DWORD)v70, lpThreadAttributes);
        v63 = ExitCode;
      }
    }
    else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    {
      lpThreadAttributes = ExitCode;
      v69 = AppUninstallSuccess;
      goto LABEL_129;
    }
    LogInfo(L"Enforcement command succeeded. (Win32 return=%1!d!. HR=0x%2!x!)", v63, v3);
    if ( v11 )
    {
      v72 = (const WCHAR *)lpFileName;
      if ( v102 >= 8 )
        v72 = lpFileName[0];
      if ( !DeleteFileW(v72) )
      {
        v73 = GetLastError();
        v74 = lpFileName;
        if ( v102 >= 8 )
          v74 = (LPCWSTR *)lpFileName[0];
        LogWarn(L"Failed to delete file %1 hr=0x%2!x!", v74, v73);
      }
    }
    goto LABEL_156;
  }
  MdmTempFolder = GetMdmTempFolder(String2, SessionId, lpPathName);
  v3 = MdmTempFolder;
  if ( MdmTempFolder >= 0 )
  {
    v39 = (const WCHAR *)lpPathName;
    if ( lpPathName[3] >= (LPCWSTR)8 )
      v39 = lpPathName[0];
    if ( !GetTempFileNameW(v39, L"tmp", 0, TempFileName) )
    {
      v40 = GetLastError();
      v3 = v40;
      if ( v40 > 0 )
        v3 = (unsigned __int16)v40 | 0x80070000;
      LogError(L"Failed to get temp file name. Error 0x%1!x!", v3);
      goto LABEL_159;
    }
    v41 = (const WCHAR *)szPackagePath;
    if ( szPackagePath[3] >= (LPCWSTR)8 )
      v41 = szPackagePath[0];
    v42 = MsiAdvertiseProductW(v41, TempFileName, 0, 0);
    v3 = v42;
    if ( v42 )
    {
      if ( v42 > 0 )
        v3 = (unsigned __int16)v42 | 0x80070000;
      LogError(L"Failed to advertise the product. Error 0x%1!x!", v3);
      goto LABEL_159;
    }
    v5 = 1;
    v43 = (wchar_t *)std::wstring::wstring(v103, String2);
    v44 = ImpersonateUser(v43, SessionId);
    v3 = v44;
    if ( v44 < 0 )
    {
      LogError(L"Failed to impersonate before advertise MSI script. Error 0x%1!x!", (unsigned int)v44);
LABEL_156:
      if ( v5 && !DeleteFileW(TempFileName) )
      {
        v80 = GetLastError();
        LogWarn(L"Failed to delete advertisement script file %1 hr=0x%2!x!", TempFileName, v80);
      }
      goto LABEL_159;
    }
    v45 = MsiAdvertiseScriptW(TempFileName, 0x1A1u, 0, 0);
    v3 = v45;
    if ( v45 )
    {
      if ( v45 > 0 )
        v3 = (unsigned __int16)v45 | 0x80070000;
      LogError(L"Failed to advertise the script. Error 0x%1!x!", v3);
      goto LABEL_156;
    }
    RevertToSelf();
    goto LABEL_60;
  }
  LogError(L"Failed to get MDM temp folder. Error 0x%1!x!", (unsigned int)MdmTempFolder);
LABEL_159:
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
LABEL_161:
  v112 = v3;
  std::wstring::operator=(v119, v105);
  v122 = v112;
  EnterCriticalSection(&JobExecution::m_critSec);
  v82 = std::_Tree_buy<std::pair<std::wstring const,unsigned long>>::_Buynode<std::pair<std::wstring,unsigned long> &>(
          v81,
          v119);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Insert_nohint<std::pair<std::wstring const,unsigned long> &,std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *> *>(
    v83,
    (unsigned int)&v95,
    v84,
    v82 + 32,
    v82);
  LeaveCriticalSection(&JobExecution::m_critSec);
  JobExecution::m_bIsEnforcementThreadRunning = 0;
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( v2 )
    CloseHandle(v2);
  v85 = v105;
  if ( v106 >= 8 )
    v85 = (_QWORD *)v105[0];
  LogInfo(L"+ Exiting enforcement thread for job %1.", v85);
  LOBYTE(v86) = 1;
  std::wstring::_Tidy(lpPathName, v86, 0);
  LOBYTE(v87) = 1;
  std::wstring::_Tidy(v119, v87, 0);
  _Job::~_Job((_Job *)v105);
  LOBYTE(v88) = 1;
  std::wstring::_Tidy(lpFileName, v88, 0);
  LOBYTE(v89) = 1;
  std::wstring::_Tidy(lpCommandLine, v89, 0);
  return v3;
}

```

## disassembly

```asm
0x14000a5e0  push    rbp
0x14000a5e2  push    rbx
0x14000a5e3  push    rsi
0x14000a5e4  push    rdi
0x14000a5e5  push    r12
0x14000a5e7  push    r13
0x14000a5e9  push    r14
0x14000a5eb  push    r15
0x14000a5ed  lea     rbp, [rsp-6E8h]
0x14000a5f5  sub     rsp, 7E8h
0x14000a5fc  mov     rax, cs:__security_cookie
0x14000a603  xor     rax, rsp
0x14000a606  mov     [rbp+720h+var_50], rax
0x14000a60d  mov     rbx, rcx
0x14000a610  xorps   xmm0, xmm0
0x14000a613  xor     eax, eax
0x14000a615  movups  xmmword ptr [rbp+720h+ProcessInformation.hProcess], xmm0
0x14000a619  mov     qword ptr [rbp+720h+ProcessInformation.dwProcessId], rax
0x14000a61d  lea     esi, [rax+68h]
0x14000a620  mov     r8d, esi; Size
0x14000a623  xor     edx, edx; Val
0x14000a625  lea     rcx, [rbp+720h+StartupInfo]; void *
0x14000a629  call    memset_0
0x14000a62e  lea     r15, word_14001E5B4
0x14000a635  mov     rdx, r15
0x14000a638  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a63c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a641  nop
0x14000a642  lea     edi, [rsi-61h]
0x14000a645  mov     [rbp+720h+var_6D8], rdi
0x14000a649  xor     r12d, r12d
0x14000a64c  mov     [rbp+720h+var_6E0], r12
0x14000a650  mov     word ptr [rbp+720h+lpFileName], r12w
0x14000a655  mov     [rsp+820h+ExitCode], r12d
0x14000a65a  lea     rcx, [rbp+720h+var_690]; this
0x14000a661  call    ??0_Job@@QEAA@XZ; _Job::_Job(void)
0x14000a666  nop
0x14000a667  mov     [rbp+720h+var_4A8], rdi
0x14000a66e  mov     [rbp+720h+var_4B0], r12
0x14000a675  mov     [rbp+720h+var_4C0], r12w
0x14000a67d  mov     [rbp+720h+var_4A0], r12d
0x14000a684  mov     r14d, r12d
0x14000a687  mov     [rsp+820h+hToken], r12
0x14000a68c  mov     rdx, r15
0x14000a68f  lea     rcx, [rbp+720h+lpPathName]
0x14000a696  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a69b  nop
0x14000a69c  xor     edx, edx; Val
0x14000a69e  mov     r8d, 208h; Size
0x14000a6a4  lea     rcx, [rbp+720h+TempFileName]; void *
0x14000a6ab  call    memset_0
0x14000a6b0  mov     dil, r12b
0x14000a6b3  mov     [rsp+820h+var_7C0], r12b
0x14000a6b8  mov     [rbp+720h+Environment], r12
0x14000a6bc  lea     r13d, [rsi-60h]
0x14000a6c0  test    rbx, rbx
0x14000a6c3  jnz     short loc_14000A6CF
0x14000a6c5  mov     ebx, 80070057h
0x14000a6ca  jmp     loc_14000B16F
0x14000a6cf  mov     rdx, rbx
0x14000a6d2  lea     rcx, [rbp+720h+var_690]
0x14000a6d9  call    ??4_Job@@QEAAAEAU0@AEBU0@@Z; _Job::operator=(_Job const &)
0x14000a6de  lea     rdx, [rbp+720h+var_690]
0x14000a6e5  cmp     [rbp+720h+var_678], r13
0x14000a6ec  cmovnb  rdx, [rbp+720h+var_690]
0x14000a6f4  lea     rcx, aEnteringEnforc; "+ Entering enforcement thread for job %"...
0x14000a6fb  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000a700  mov     r8, rsi; Size
0x14000a703  xor     edx, edx; Val
0x14000a705  lea     rcx, [rbp+720h+StartupInfo]; void *
0x14000a709  call    memset_0
0x14000a70e  xorps   xmm0, xmm0
0x14000a711  xor     eax, eax
0x14000a713  movups  xmmword ptr [rbp+720h+ProcessInformation.hProcess], xmm0
0x14000a717  mov     qword ptr [rbp+720h+ProcessInformation.dwProcessId], rax
0x14000a71b  mov     [rbp+720h+StartupInfo.cb], esi
0x14000a71e  mov     [rbp+720h+StartupInfo.dwFlags], 1
0x14000a725  mov     [rbp+720h+StartupInfo.wShowWindow], r12w
0x14000a72a  mov     [rbp+720h+StartupInfo.lpDesktop], r15
0x14000a72e  mov     edx, 104h; uSize
0x14000a733  lea     rcx, [rbp+720h+Buffer]; lpBuffer
0x14000a73a  call    cs:__imp_GetSystemDirectoryW
0x14000a740  test    eax, eax
0x14000a742  jnz     short loc_14000A74E
0x14000a744  mov     ebx, 8000FFFFh
0x14000a749  jmp     loc_14000B160
0x14000a74e  cmp     [rbp+720h+var_600], 1
0x14000a755  jnz     short loc_14000A76E
0x14000a757  cmp     [rbp+720h+var_5B8], r12
0x14000a75e  jnz     short loc_14000A76E
0x14000a760  lea     rcx, aTheValueForDow; "The value for DownloadLocation is empty"...
0x14000a767  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000a76c  jmp     short loc_14000A744
0x14000a76e  mov     r15b, r12b
0x14000a771  lea     rdx, [rbp+720h+var_548]
0x14000a778  lea     rcx, [rbp+720h+var_6B0]
0x14000a77c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a781  mov     rdx, rax
0x14000a784  lea     rcx, [rbp+720h+var_6D0]
0x14000a788  call    ?ToUpperCase@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; ToUpperCase(std::wstring)
0x14000a78d  mov     r8, rax
0x14000a790  lea     rcx, asc_140020C34; "/L"
0x14000a797  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000a79c  mov     r9, rax
0x14000a79f  mov     rdx, rcx
0x14000a7a2  mov     rcx, r8
0x14000a7a5  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x14000a7aa  mov     rbx, rax
0x14000a7ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a7b1  setz    sil
0x14000a7b5  xor     r8d, r8d
0x14000a7b8  mov     dl, 1
0x14000a7ba  lea     rcx, [rbp+720h+var_6D0]
0x14000a7be  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a7c3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000a7c7  jnz     short loc_14000A82C
0x14000a7c9  lea     r8, [rbp+720h+lpFileName]
0x14000a7cd  mov     edx, [rbp+720h+SessionId]
0x14000a7d3  lea     rcx, [rbp+720h+String2]
0x14000a7da  call    ?GetMdmTempFolder@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV12@@Z; GetMdmTempFolder(std::wstring const &,ulong,std::wstring &)
0x14000a7df  test    eax, eax
0x14000a7e1  js      short loc_14000A81B
0x14000a7e3  lea     rdx, asc_140020C3C; "\\"
0x14000a7ea  lea     rcx, [rbp+720h+lpFileName]
0x14000a7ee  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a7f3  or      r9, rbx
0x14000a7f6  xor     r8d, r8d
0x14000a7f9  lea     rdx, [rbp+720h+var_690]
0x14000a800  lea     rcx, [rbp+720h+lpFileName]
0x14000a804  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000a809  lea     rdx, aLog; ".log"
0x14000a810  lea     rcx, [rbp+720h+lpFileName]
0x14000a814  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a819  jmp     short loc_14000A82C
0x14000a81b  xor     edx, edx
0x14000a81d  lea     rcx, aFailedToGetMdm; "Failed to get MDM temp folder. Error 0x"...
0x14000a824  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000a829  mov     sil, r12b
0x14000a82c  lea     rdx, [rbp+720h+var_548]
0x14000a833  lea     rcx, [rbp+720h+var_6D0]
0x14000a837  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a83c  mov     rdx, rax
0x14000a83f  lea     rcx, [rbp+720h+var_6B0]
0x14000a843  call    ?ToUpperCase@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; ToUpperCase(std::wstring)
0x14000a848  mov     r8, rax
0x14000a84b  lea     rcx, aQuiet; "/QUIET"
0x14000a852  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000a857  mov     r9, rax
0x14000a85a  mov     rdx, rcx
0x14000a85d  mov     rcx, r8
0x14000a860  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x14000a865  mov     rbx, rax
0x14000a868  xor     r8d, r8d
0x14000a86b  mov     dl, 1
0x14000a86d  lea     rcx, [rbp+720h+var_6B0]
0x14000a871  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a876  lea     r8, aMsiexecExe; "\\msiexec.exe"
0x14000a87d  mov     edx, 104h; SizeInWords
0x14000a882  lea     rcx, [rbp+720h+Buffer]; Destination
0x14000a889  call    cs:__imp_wcscat_s
0x14000a88f  lea     rdx, asc_140020CDC; "\""
0x14000a896  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a89a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a89f  lea     rdx, [rbp+720h+Buffer]
0x14000a8a6  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a8aa  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a8af  lea     rdx, asc_140020CDC; "\""
0x14000a8b6  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a8ba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a8bf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000a8c3  jnz     short loc_14000A8D5
0x14000a8c5  lea     rdx, aQuiet_0; " /quiet "
0x14000a8cc  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a8d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a8d5  test    sil, sil
0x14000a8d8  jz      short loc_14000A910
0x14000a8da  lea     rdx, aLV; " /l*v \""
0x14000a8e1  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a8e5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a8ea  lea     rdx, [rbp+720h+lpFileName]
0x14000a8ee  cmp     [rbp+720h+var_6D8], r13
0x14000a8f2  cmovnb  rdx, [rbp+720h+lpFileName]
0x14000a8f7  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a8fb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a900  lea     rdx, asc_140020D08; "\" "
0x14000a907  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a90b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a910  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a914  cmp     [rbp+720h+var_600], 1
0x14000a91b  jnz     short loc_14000A952
0x14000a91d  lea     rdx, aQnI; " /qn /i \""
0x14000a924  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a929  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000a92d  xor     r8d, r8d
0x14000a930  lea     rdx, [rbp+720h+szPackagePath]
0x14000a937  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a93b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000a940  lea     rdx, asc_140020D08; "\" "
0x14000a947  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a94b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a950  jmp     short loc_14000A985
0x14000a952  lea     rdx, aQn; " /qn "
0x14000a959  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a95e  lea     rdx, asc_140020D38; " /x "
0x14000a965  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a969  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a96e  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000a972  xor     r8d, r8d
0x14000a975  lea     rdx, [rbp+720h+var_648]
0x14000a97c  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a980  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000a985  lea     rdx, [rbp+720h+var_548]
0x14000a98c  lea     rcx, [rbp+720h+var_6D0]
0x14000a990  cmp     [rbp+720h+var_50C], r12b
0x14000a997  jz      loc_14000AA58
0x14000a99d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a9a2  mov     rdx, rax
0x14000a9a5  lea     rcx, [rbp+720h+var_6B0]
0x14000a9a9  call    ?ToUpperCase@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; ToUpperCase(std::wstring)
0x14000a9ae  mov     r8, rax
0x14000a9b1  lea     rcx, aReinstall; "REINSTALL"
0x14000a9b8  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000a9bd  mov     r9, rax
0x14000a9c0  lea     rdx, aReinstall; "REINSTALL"
0x14000a9c7  mov     rcx, r8
0x14000a9ca  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x14000a9cf  mov     rbx, rax
0x14000a9d2  xor     r8d, r8d
0x14000a9d5  mov     dl, 1
0x14000a9d7  lea     rcx, [rbp+720h+var_6B0]
0x14000a9db  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a9e0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000a9e4  jnz     short loc_14000A9F6
0x14000a9e6  lea     rdx, aReinstallAll; " REINSTALL=ALL "
0x14000a9ed  lea     rcx, [rbp+720h+lpCommandLine]
0x14000a9f1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000a9f6  lea     rdx, [rbp+720h+var_548]
0x14000a9fd  lea     rcx, [rbp+720h+var_6D0]
0x14000aa01  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000aa06  mov     rdx, rax
0x14000aa09  lea     rcx, [rbp+720h+var_6B0]
0x14000aa0d  call    ?ToUpperCase@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; ToUpperCase(std::wstring)
0x14000aa12  mov     r8, rax
0x14000aa15  lea     rcx, aReinstallmode; "REINSTALLMODE"
0x14000aa1c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000aa21  mov     r9, rax
0x14000aa24  mov     rdx, rcx
0x14000aa27  mov     rcx, r8
0x14000aa2a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x14000aa2f  mov     rbx, rax
0x14000aa32  xor     r8d, r8d
0x14000aa35  mov     dl, 1
0x14000aa37  lea     rcx, [rbp+720h+var_6B0]
0x14000aa3b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000aa40  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000aa44  jnz     short loc_14000AAC3
0x14000aa46  lea     rdx, aReinstallmodeV; " REINSTALLMODE=vomus "
0x14000aa4d  lea     rcx, [rbp+720h+lpCommandLine]
0x14000aa51  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000aa56  jmp     short loc_14000AAC3
0x14000aa58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000aa5d  mov     rdx, rax
0x14000aa60  lea     rcx, [rbp+720h+var_6B0]
0x14000aa64  call    ?ToUpperCase@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; ToUpperCase(std::wstring)
0x14000aa69  mov     r8, rax
0x14000aa6c  lea     rcx, aReinstall; "REINSTALL"
0x14000aa73  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000aa78  mov     r9, rax
0x14000aa7b  lea     rdx, aReinstall; "REINSTALL"
0x14000aa82  mov     rcx, r8
0x14000aa85  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x14000aa8a  mov     rbx, rax
0x14000aa8d  xor     r8d, r8d
0x14000aa90  mov     dl, 1
0x14000aa92  lea     rcx, [rbp+720h+var_6B0]
0x14000aa96  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000aa9b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000aa9f  jz      short loc_14000AAC3
0x14000aaa1  lea     rdx, [rbp+720h+var_690]
0x14000aaa8  cmp     [rbp+720h+var_678], r13
0x14000aaaf  cmovnb  rdx, [rbp+720h+var_690]
0x14000aab7  lea     rcx, aJob1MayBeTryin; "Job %1 may be trying to install a minor"...
0x14000aabe  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14000aac3  cmp     [rbp+720h+var_600], 1
0x14000aaca  jnz     short loc_14000AAFC
0x14000aacc  cmp     [rbp+720h+var_538], r12
0x14000aad3  jz      short loc_14000AAFC
0x14000aad5  lea     rdx, asc_140020EAC; " "
0x14000aadc  lea     rcx, [rbp+720h+lpCommandLine]
0x14000aae0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000aae5  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000aae9  xor     r8d, r8d
0x14000aaec  lea     rdx, [rbp+720h+var_548]
0x14000aaf3  lea     rcx, [rbp+720h+lpCommandLine]
0x14000aaf7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000aafc  lea     rdx, [rbp+720h+lpCommandLine]
0x14000ab00  cmp     [rbp+720h+var_6F8], r13
0x14000ab04  cmovnb  rdx, [rbp+720h+lpCommandLine]
0x14000ab09  lea     rcx, aRunCommand1; "Run command \"%1\""
0x14000ab10  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
  ... truncated ...
```

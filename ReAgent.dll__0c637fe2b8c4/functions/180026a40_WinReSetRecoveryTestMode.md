# WinReSetRecoveryTestMode

- ea: `0x180026a40`
- end: `0x180026e95`
- name: `WinReSetRecoveryTestMode`
- size: `1109`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000196c`
- `0x180001adc`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000c658`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000ff68`
- `0x180026a40`
- `0x180032728`
- `0x18003e940`
- `0x18004d52c`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026bda`
- `KERNEL32!GetLastError` at `0x180026ca3`
- `KERNEL32!GetLastError` at `0x180026d98`
- `KERNEL32!GetLastError` at `0x180026e0f`
- `KERNEL32!GetLastError` at `0x180026bda`
- `KERNEL32!GetLastError` at `0x180026ca3`
- `KERNEL32!GetLastError` at `0x180026d98`
- `KERNEL32!GetLastError` at `0x180026e0f`
- `KERNEL32!WriteFile` at `0x180026e05`
- `KERNEL32!WriteFile` at `0x180026e05`
- `KERNEL32!SetLastError` at `0x180026e6e`
- `KERNEL32!SetLastError` at `0x180026e6e`
- `KERNEL32!CreateFileW` at `0x180026d89`
- `KERNEL32!CreateFileW` at `0x180026d89`
- `KERNEL32!CloseHandle` at `0x180026e31`
- `KERNEL32!CloseHandle` at `0x180026e31`
- `KERNEL32!DeleteFileW` at `0x180026c99`
- `KERNEL32!DeleteFileW` at `0x180026c99`
- `KERNEL32!GetWindowsDirectoryW` at `0x180026bd0`
- `KERNEL32!GetWindowsDirectoryW` at `0x180026bd0`
- `ADVAPI32!RegSetValueExW` at `0x180026d44`
- `ADVAPI32!RegSetValueExW` at `0x180026d44`
- `ADVAPI32!RegCreateKeyExW` at `0x180026cfd`
- `ADVAPI32!RegCreateKeyExW` at `0x180026cfd`
- `ADVAPI32!RegCloseKey` at `0x180026e41`
- `ADVAPI32!RegCloseKey` at `0x180026e41`

## string_xrefs

- `0x180026dfb`: `[Recovery]\nActive=Yes\nHeadlessMode=No\nAutoRemediation=Yes\nCloudRemediation=Yes\n\n[Failure.Info]\nCrashDump.Code=0x85\nCrashDump.Module=qmrsimulation.sys\nCrashDump.Stack=qmrsimulation.sys;nt.sys\n\n[Simulation.Setup]\n0=Create,File,%windir%\system32\recovery\TestRecovery.txt\n\n[Simulation.Cleanup]\n0=Delete,File,%windir%\system32\recovery\TestRecovery.txt\n\n[Simulation.Success]\n0=Absent,File,%windir%\system32\recovery\TestRecovery.txt\n`
- `0x180026ba3`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180026c30`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180026dbc`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180026b30`: `system32\recovery\RecoverySimulation.ini`
- `0x180026c14`: `system32\recovery\RecoverySimulation.ini`
- `0x180026b9c`: `Failed to append path to test mode simulation file`
- `0x180026c47`: `Failed to append path to test mode simulation file`
- `0x180026be8`: `GetWindowsDirectoryW() failed`
- `0x180026c86`: `Delete existing test mode simulation file`
- `0x180026ca9`: `DeleteFileW() failed. 0x%x`
- `0x180026cbb`: `Set registry key for RelPost.exe`
- `0x180026d09`: `RegCreateKeyEx() failed. 0x%x`
- `0x180026d50`: `RegSetValueEx() failed. 0x%x`
- `0x180026d59`: `Create test mode simulation file`
- `0x180026da0`: `CreateFileW() failed. 0x%x`
- `0x180026dd3`: `Failed to set ACL on test mode simulation file`
- `0x180026e15`: `WriteFile() failed. 0x%x`

## pseudocode

```c
__int64 __fastcall WinReSetRecoveryTestMode(unsigned __int16 *a1)
{
  unsigned int v2; // esi
  __int64 v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  const unsigned __int16 *v6; // r8
  const wchar_t *v7; // r8
  DWORD LastError; // eax
  DWORD v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  HANDLE v12; // rdi
  REGSAM samDesired; // [rsp+28h] [rbp-D8h]
  __int64 samDesireda; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR Buffer; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[606]; // [rsp+72h] [rbp-8Eh] BYREF

  v2 = 0;
  Buffer = 0;
  NumberOfBytesWritten = 0;
  memset_0(v21, 0, 0x25Au);
  hKey = 0;
  *(_DWORD *)Data = 1;
  TraceLoggingRegisterEx_EventRegister_2U();
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetRecoveryTestMode");
  UnattendLogW(0, L"Parameters: winDir: %s", a1);
  if ( a1 )
  {
    v16 = 0;
    LODWORD(v3) = StringCchLengthW(a1, 0x7FFFFFFFu, &v16);
    if ( (int)v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 14;
LABEL_13:
        WPP_SF_d(v4[2], v5, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v3);
        goto LABEL_14;
      }
      goto LABEL_14;
    }
    if ( !v16 || (v6 = L"%s\\%s", a1[v16 - 1] == 92) )
      v6 = L"%s%s";
    LODWORD(v3) = StringCchPrintfW(&Buffer, 0x12Eu, v6, a1, L"system32\\recovery\\RecoverySimulation.ini");
    if ( (int)v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 15;
        goto LABEL_13;
      }
LABEL_14:
      LODWORD(v3) = (unsigned __int16)v3;
      if ( (_WORD)v3 )
      {
        samDesired = 9056;
        v7 = L"Failed to append path to test mode simulation file";
LABEL_16:
        UnattendLogW(
          2,
          L"WinReSetRecoveryTestMode %s (0x%x) in file %S line %d",
          v7,
          (unsigned int)v3,
          "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
          samDesired);
        goto LABEL_39;
      }
    }
  }
  else
  {
    if ( !GetWindowsDirectoryW(&Buffer, 0x12Eu) )
    {
      LastError = GetLastError();
      samDesired = 9060;
      v7 = L"GetWindowsDirectoryW() failed";
      LODWORD(v3) = LastError;
      goto LABEL_16;
    }
    LODWORD(v3) = winreAddTrailingBackslash(&Buffer);
    if ( (_DWORD)v3 )
    {
      samDesired = 9061;
      v7 = L"failed to add trailing back slash";
      goto LABEL_16;
    }
    LODWORD(v3) = StringCchCatW(&Buffer, 0x12Eu, L"system32\\recovery\\RecoverySimulation.ini");
    if ( (int)v3 < 0 )
    {
      UnattendLogW(
        2,
        L"WinReSetRecoveryTestMode %s (0x%x) in file %S line %d",
        L"Failed to append path to test mode simulation file",
        (unsigned int)v3,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        9063);
      LODWORD(v3) = (unsigned __int16)v3;
      goto LABEL_39;
    }
  }
  UnattendLogW(0, L"Test mode simulation file: %s", &Buffer);
  if ( !Utils::DoesPathExist(&Buffer) )
  {
    UnattendLogW(0, L"Delete existing test mode simulation file");
    if ( !DeleteFileW(&Buffer) )
    {
      v9 = GetLastError();
      UnattendLogW(2, L"DeleteFileW() failed. 0x%x", v9);
    }
  }
  UnattendLogW(0, L"Set registry key for RelPost.exe");
  v10 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\Srt",
          0,
          0,
          0,
          0x20006u,
          0,
          &hKey,
          0);
  LODWORD(v3) = v10;
  if ( v10 )
  {
    UnattendLogW(1, L"RegCreateKeyEx() failed. 0x%x", v10);
  }
  else
  {
    v11 = RegSetValueExW(hKey, L"Run", 0, 4u, Data, 4u);
    LODWORD(v3) = v11;
    if ( v11 )
    {
      UnattendLogW(1, L"RegSetValueEx() failed. 0x%x", v11);
    }
    else
    {
      UnattendLogW(0, L"Create test mode simulation file");
      v12 = CreateFileW(&Buffer, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      if ( v12 == (HANDLE)-1LL )
      {
        v3 = GetLastError();
        UnattendLogW(1, L"CreateFileW() failed. 0x%x", v3);
      }
      else
      {
        LODWORD(v3) = winreSetACL(&Buffer);
        if ( (_DWORD)v3 )
        {
          LODWORD(samDesireda) = 9115;
          UnattendLogW(
            2,
            L"WinReSetRecoveryTestMode %s (0x%x) in file %S line %d",
            L"Failed to set ACL on test mode simulation file",
            (unsigned int)v3,
            "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
            samDesireda);
        }
        else if ( WriteFile(
                    v12,
                    "[Recovery]\r\n"
                    "Active=Yes\r\n"
                    "HeadlessMode=No\r\n"
                    "AutoRemediation=Yes\r\n"
                    "CloudRemediation=Yes\r\n"
                    "\r\n"
                    "[Failure.Info]\r\n"
                    "CrashDump.Code=0x85\r\n"
                    "CrashDump.Module=qmrsimulation.sys\r\n"
                    "CrashDump.Stack=qmrsimulation.sys;nt.sys\r\n"
                    "\r\n"
                    "[Simulation.Setup]\r\n"
                    "0=Create,File,%windir%\\system32\\recovery\\TestRecovery.txt\r\n"
                    "\r\n"
                    "[Simulation.Cleanup]\r\n"
                    "0=Delete,File,%windir%\\system32\\recovery\\TestRecovery.txt\r\n"
                    "\r\n"
                    "[Simulation.Success]\r\n"
                    "0=Absent,File,%windir%\\system32\\recovery\\TestRecovery.txt\r\n",
                    0x1C2u,
                    &NumberOfBytesWritten,
                    0) )
        {
          v2 = 1;
        }
        else
        {
          v3 = GetLastError();
          UnattendLogW(1, L"WriteFile() failed. 0x%x", v3);
        }
        CloseHandle(v12);
      }
    }
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  AsmWinRESetRecoveryTestMode(v3);
  UnattendLogW(0, L"Exit WinReSetRecoveryTestMode return value: %d, last error: 0x%x", v2, (unsigned int)v3);
  UnattendFinalizeLog();
  TraceLoggingUnregister_EventUnregister();
  SetLastError(v3);
  return v2;
}

```

## disassembly

```asm
0x180026a40  push    rbp
0x180026a42  push    rbx
0x180026a43  push    rsi
0x180026a44  push    rdi
0x180026a45  push    r12
0x180026a47  push    r15
0x180026a49  lea     rbp, [rsp-1E8h]
0x180026a51  sub     rsp, 2E8h
0x180026a58  mov     rax, cs:__security_cookie
0x180026a5f  xor     rax, rsp
0x180026a62  mov     [rbp+210h+var_40], rax
0x180026a69  mov     rdi, rcx
0x180026a6c  xor     eax, eax
0x180026a6e  xor     esi, esi
0x180026a70  mov     [rsp+310h+Buffer], ax
0x180026a75  lea     rcx, [rsp+310h+var_29E]; void *
0x180026a7a  mov     [rsp+310h+NumberOfBytesWritten], esi
0x180026a7e  xor     edx, edx; Val
0x180026a80  mov     r8d, 25Ah; Size
0x180026a86  call    memset_0
0x180026a8b  lea     r12d, [rsi+1]
0x180026a8f  mov     [rsp+310h+hKey], rsi
0x180026a94  mov     dword ptr [rsp+310h+Data], r12d
0x180026a99  call    TraceLoggingRegisterEx_EventRegister_2U
0x180026a9e  xor     ecx, ecx
0x180026aa0  call    UnattendInitializeLogEx2
0x180026aa5  lea     rdx, aEnterWinresetr_0; "Enter WinReSetRecoveryTestMode"
0x180026aac  xor     ecx, ecx
0x180026aae  call    UnattendLogW
0x180026ab3  mov     r8, rdi
0x180026ab6  lea     rdx, aParametersWind_2; "Parameters: winDir: %s"
0x180026abd  xor     ecx, ecx
0x180026abf  call    UnattendLogW
0x180026ac4  lea     r15d, [rsi+2]
0x180026ac8  test    rdi, rdi
0x180026acb  jz      loc_180026BC6
0x180026ad1  lea     r8, [rsp+310h+var_2C0]; unsigned __int64 *
0x180026ad6  mov     [rsp+310h+var_2C0], rsi
0x180026adb  mov     edx, 7FFFFFFFh; unsigned __int64
0x180026ae0  mov     rcx, rdi; unsigned __int16 *
0x180026ae3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180026ae8  mov     ebx, eax
0x180026aea  test    eax, eax
0x180026aec  jns     short loc_180026B10
0x180026aee  mov     rcx, cs:WPP_GLOBAL_Control
0x180026af5  lea     rax, WPP_GLOBAL_Control
0x180026afc  cmp     rcx, rax
0x180026aff  jz      loc_180026B89
0x180026b05  test    [rcx+1Ch], r15b
0x180026b09  jz      short loc_180026B89
0x180026b0b  lea     edx, [rsi+0Eh]
0x180026b0e  jmp     short loc_180026B76
0x180026b10  mov     rax, [rsp+310h+var_2C0]
0x180026b15  test    rax, rax
0x180026b18  jz      short loc_180026B29
0x180026b1a  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180026b20  lea     r8, aSS_1; "%s\\%s"
0x180026b27  jnz     short loc_180026B30
0x180026b29  lea     r8, aSS_2; "%s%s"
0x180026b30  lea     rax, aSystem32Recove_0; "system32\\recovery\\RecoverySimulation."...
0x180026b37  mov     r9, rdi
0x180026b3a  mov     edx, 12Eh; unsigned __int64
0x180026b3f  mov     qword ptr [rsp+310h+dwOptions], rax
0x180026b44  lea     rcx, [rsp+310h+Buffer]; unsigned __int16 *
0x180026b49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026b4e  mov     ebx, eax
0x180026b50  test    eax, eax
0x180026b52  jns     loc_180026C65
0x180026b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b5f  lea     rax, WPP_GLOBAL_Control
0x180026b66  cmp     rcx, rax
0x180026b69  jz      short loc_180026B89
0x180026b6b  test    [rcx+1Ch], r15b
0x180026b6f  jz      short loc_180026B89
0x180026b71  mov     edx, 0Fh
0x180026b76  mov     rcx, [rcx+10h]
0x180026b7a  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180026b81  mov     r9d, ebx
0x180026b84  call    WPP_SF_d
0x180026b89  movzx   ebx, bx
0x180026b8c  test    ebx, ebx
0x180026b8e  jz      loc_180026C65
0x180026b94  mov     dword ptr [rsp+310h+samDesired], 2360h
0x180026b9c  lea     r8, aFailedToAppend_2; "Failed to append path to test mode simu"...
0x180026ba3  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180026baa  mov     r9d, ebx
0x180026bad  lea     rdx, aWinresetrecove_9; "WinReSetRecoveryTestMode %s (0x%x) in f"...
0x180026bb4  mov     qword ptr [rsp+310h+dwOptions], rax
0x180026bb9  mov     ecx, r15d
0x180026bbc  call    UnattendLogW
0x180026bc1  jmp     loc_180026E37
0x180026bc6  mov     edx, 12Eh; uSize
0x180026bcb  lea     rcx, [rsp+310h+Buffer]; lpBuffer
0x180026bd0  call    cs:__imp_GetWindowsDirectoryW
0x180026bd6  test    eax, eax
0x180026bd8  jnz     short loc_180026BF3
0x180026bda  call    cs:__imp_GetLastError
0x180026be0  mov     dword ptr [rsp+310h+samDesired], 2364h
0x180026be8  lea     r8, aGetwindowsdire; "GetWindowsDirectoryW() failed"
0x180026bef  mov     ebx, eax
0x180026bf1  jmp     short loc_180026BA3
0x180026bf3  lea     rcx, [rsp+310h+Buffer]
0x180026bf8  call    winreAddTrailingBackslash
0x180026bfd  mov     ebx, eax
0x180026bff  test    eax, eax
0x180026c01  jz      short loc_180026C14
0x180026c03  mov     dword ptr [rsp+310h+samDesired], 2365h
0x180026c0b  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180026c12  jmp     short loc_180026BA3
0x180026c14  lea     r8, aSystem32Recove_0; "system32\\recovery\\RecoverySimulation."...
0x180026c1b  mov     edx, 12Eh; unsigned __int64
0x180026c20  lea     rcx, [rsp+310h+Buffer]; unsigned __int16 *
0x180026c25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026c2a  mov     ebx, eax
0x180026c2c  test    eax, eax
0x180026c2e  jns     short loc_180026C65
0x180026c30  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180026c37  mov     dword ptr [rsp+310h+samDesired], 2367h
0x180026c3f  mov     r9d, ebx
0x180026c42  mov     qword ptr [rsp+310h+dwOptions], rax
0x180026c47  lea     r8, aFailedToAppend_2; "Failed to append path to test mode simu"...
0x180026c4e  mov     ecx, r15d
0x180026c51  lea     rdx, aWinresetrecove_9; "WinReSetRecoveryTestMode %s (0x%x) in f"...
0x180026c58  call    UnattendLogW
0x180026c5d  movzx   ebx, bx
0x180026c60  jmp     loc_180026E37
0x180026c65  lea     r8, [rsp+310h+Buffer]
0x180026c6a  xor     ecx, ecx
0x180026c6c  lea     rdx, aTestModeSimula_2; "Test mode simulation file: %s"
0x180026c73  call    UnattendLogW
0x180026c78  lea     rcx, [rsp+310h+Buffer]; unsigned __int16 *
0x180026c7d  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180026c82  test    eax, eax
0x180026c84  jnz     short loc_180026CBB
0x180026c86  lea     rdx, aDeleteExisting; "Delete existing test mode simulation fi"...
0x180026c8d  xor     ecx, ecx
0x180026c8f  call    UnattendLogW
0x180026c94  lea     rcx, [rsp+310h+Buffer]; lpFileName
0x180026c99  call    cs:__imp_DeleteFileW
0x180026c9f  test    eax, eax
0x180026ca1  jnz     short loc_180026CBB
0x180026ca3  call    cs:__imp_GetLastError
0x180026ca9  lea     rdx, aDeletefilewFai; "DeleteFileW() failed. 0x%x"
0x180026cb0  mov     ecx, r15d
0x180026cb3  mov     r8d, eax
0x180026cb6  call    UnattendLogW
0x180026cbb  lea     rdx, aSetRegistryKey; "Set registry key for RelPost.exe"
0x180026cc2  xor     ecx, ecx
0x180026cc4  call    UnattendLogW
0x180026cc9  mov     [rsp+310h+lpdwDisposition], rsi; lpdwDisposition
0x180026cce  lea     rax, [rsp+310h+hKey]
0x180026cd3  mov     [rsp+310h+phkResult], rax; phkResult
0x180026cd8  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026cdf  mov     [rsp+310h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180026ce4  xor     r9d, r9d; lpClass
0x180026ce7  mov     dword ptr [rsp+310h+samDesired], 20006h; samDesired
0x180026cef  xor     r8d, r8d; Reserved
0x180026cf2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026cf9  mov     [rsp+310h+dwOptions], esi; dwOptions
0x180026cfd  call    cs:__imp_RegCreateKeyExW
0x180026d03  mov     ebx, eax
0x180026d05  test    eax, eax
0x180026d07  jz      short loc_180026D20
0x180026d09  lea     rdx, aRegcreatekeyex_0; "RegCreateKeyEx() failed. 0x%x"
0x180026d10  mov     r8d, eax
0x180026d13  mov     ecx, r12d
0x180026d16  call    UnattendLogW
0x180026d1b  jmp     loc_180026E37
0x180026d20  mov     rcx, [rsp+310h+hKey]; hKey
0x180026d25  lea     rax, [rsp+310h+Data]
0x180026d2a  mov     r9d, 4; dwType
0x180026d30  lea     rdx, aRun; "Run"
0x180026d37  mov     dword ptr [rsp+310h+samDesired], r9d; cbData
0x180026d3c  xor     r8d, r8d; Reserved
0x180026d3f  mov     qword ptr [rsp+310h+dwOptions], rax; lpData
0x180026d44  call    cs:__imp_RegSetValueExW
0x180026d4a  mov     ebx, eax
0x180026d4c  test    eax, eax
0x180026d4e  jz      short loc_180026D59
0x180026d50  lea     rdx, aRegsetvalueexF; "RegSetValueEx() failed. 0x%x"
0x180026d57  jmp     short loc_180026D10
0x180026d59  lea     rdx, aCreateTestMode; "Create test mode simulation file"
0x180026d60  xor     ecx, ecx
0x180026d62  call    UnattendLogW
0x180026d67  mov     [rsp+310h+lpSecurityAttributes], rsi; hTemplateFile
0x180026d6c  lea     rcx, [rsp+310h+Buffer]; lpFileName
0x180026d71  mov     dword ptr [rsp+310h+samDesired], 80h; dwFlagsAndAttributes
0x180026d79  xor     r9d, r9d; lpSecurityAttributes
0x180026d7c  xor     r8d, r8d; dwShareMode
0x180026d7f  mov     [rsp+310h+dwOptions], r15d; dwCreationDisposition
0x180026d84  mov     edx, 40000000h; dwDesiredAccess
0x180026d89  call    cs:__imp_CreateFileW
0x180026d8f  mov     rdi, rax
0x180026d92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026d96  jnz     short loc_180026DAC
0x180026d98  call    cs:__imp_GetLastError
0x180026d9e  mov     ebx, eax
0x180026da0  lea     rdx, aCreatefilewFai; "CreateFileW() failed. 0x%x"
0x180026da7  jmp     loc_180026D10
0x180026dac  lea     rcx, [rsp+310h+Buffer]; lpFileName
0x180026db1  call    winreSetACL
0x180026db6  mov     ebx, eax
0x180026db8  test    eax, eax
0x180026dba  jz      short loc_180026DEB
0x180026dbc  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180026dc3  mov     dword ptr [rsp+310h+samDesired], 239Bh
0x180026dcb  mov     r9d, ebx
0x180026dce  mov     qword ptr [rsp+310h+dwOptions], rax
0x180026dd3  lea     r8, aFailedToSetAcl_2; "Failed to set ACL on test mode simulati"...
0x180026dda  mov     ecx, r15d
0x180026ddd  lea     rdx, aWinresetrecove_9; "WinReSetRecoveryTestMode %s (0x%x) in f"...
0x180026de4  call    UnattendLogW
0x180026de9  jmp     short loc_180026E2E
0x180026deb  lea     r9, [rsp+310h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180026df0  mov     qword ptr [rsp+310h+dwOptions], rsi; lpOverlapped
0x180026df5  mov     r8d, 1C2h; nNumberOfBytesToWrite
0x180026dfb  lea     rdx, aRecoveryActive; "[Recovery]\r\nActive=Yes\r\nHeadlessMod"...
0x180026e02  mov     rcx, rdi; hFile
0x180026e05  call    cs:__imp_WriteFile
0x180026e0b  test    eax, eax
0x180026e0d  jnz     short loc_180026E2B
0x180026e0f  call    cs:__imp_GetLastError
0x180026e15  lea     rdx, aWritefileFaile_0; "WriteFile() failed. 0x%x"
0x180026e1c  mov     ecx, r12d
0x180026e1f  mov     r8d, eax
0x180026e22  mov     ebx, eax
0x180026e24  call    UnattendLogW
0x180026e29  jmp     short loc_180026E2E
0x180026e2b  mov     esi, r12d
0x180026e2e  mov     rcx, rdi; hObject
0x180026e31  call    cs:__imp_CloseHandle
0x180026e37  mov     rcx, [rsp+310h+hKey]; hKey
0x180026e3c  test    rcx, rcx
0x180026e3f  jz      short loc_180026E47
0x180026e41  call    cs:__imp_RegCloseKey
0x180026e47  mov     ecx, ebx; unsigned int
0x180026e49  call    ?AsmWinRESetRecoveryTestMode@@YAXK@Z; AsmWinRESetRecoveryTestMode(ulong)
0x180026e4e  mov     r9d, ebx
0x180026e51  lea     rdx, aExitWinresetre; "Exit WinReSetRecoveryTestMode return va"...
0x180026e58  mov     r8d, esi
0x180026e5b  xor     ecx, ecx
0x180026e5d  call    UnattendLogW
0x180026e62  call    UnattendFinalizeLog
0x180026e67  call    TraceLoggingUnregister_EventUnregister
0x180026e6c  mov     ecx, ebx; dwErrCode
0x180026e6e  call    cs:__imp_SetLastError
0x180026e74  mov     eax, esi
0x180026e76  mov     rcx, [rbp+210h+var_40]
0x180026e7d  xor     rcx, rsp; StackCookie
0x180026e80  call    __security_check_cookie
0x180026e85  add     rsp, 2E8h
0x180026e8c  pop     r15
0x180026e8e  pop     r12
0x180026e90  pop     rdi
0x180026e91  pop     rsi
0x180026e92  pop     rbx
0x180026e93  pop     rbp
0x180026e94  retn
```

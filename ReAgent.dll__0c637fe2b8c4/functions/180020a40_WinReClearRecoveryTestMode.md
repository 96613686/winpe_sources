# WinReClearRecoveryTestMode

- ea: `0x180020a40`
- end: `0x180020d12`
- name: `WinReClearRecoveryTestMode`
- size: `722`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task`

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
- `0x180020a40`
- `0x18003e624`
- `0x18004d52c`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020bee`
- `KERNEL32!GetLastError` at `0x180020c23`
- `KERNEL32!GetLastError` at `0x180020bee`
- `KERNEL32!GetLastError` at `0x180020c23`
- `KERNEL32!SetLastError` at `0x180020cef`
- `KERNEL32!SetLastError` at `0x180020cef`
- `KERNEL32!DeleteFileW` at `0x180020be0`
- `KERNEL32!DeleteFileW` at `0x180020be0`
- `KERNEL32!GetWindowsDirectoryW` at `0x180020c19`
- `KERNEL32!GetWindowsDirectoryW` at `0x180020c19`

## string_xrefs

- `0x180020b81`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180020c83`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180020b16`: `system32\recovery\RecoverySimulation.ini`
- `0x180020c63`: `system32\recovery\RecoverySimulation.ini`
- `0x180020b7a`: `Failed to append path to test mode simulation file`
- `0x180020c9a`: `Failed to append path to test mode simulation file`
- `0x180020c31`: `GetWindowsDirectoryW() failed`
- `0x180020bf4`: `DeleteFileW() failed. 0x%x`
- `0x180020bcf`: `Delete test mode simulation file`

## pseudocode

```c
__int64 __fastcall WinReClearRecoveryTestMode(unsigned __int16 *a1)
{
  unsigned int v2; // esi
  __int64 v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  const unsigned __int16 *v6; // r8
  const wchar_t *v7; // r8
  DWORD LastError; // eax
  int v9; // edi
  int v11; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[606]; // [rsp+42h] [rbp-BEh] BYREF

  FileName = 0;
  v2 = 0;
  memset_0(v14, 0, 0x25Au);
  TraceLoggingRegisterEx_EventRegister_2U();
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReClearRecoveryTestMode");
  UnattendLogW(0, L"Parameters: winDir: %s", a1);
  if ( !a1 )
  {
    if ( !GetWindowsDirectoryW(&FileName, 0x12Eu) )
    {
      LastError = GetLastError();
      v11 = 9176;
      v7 = L"GetWindowsDirectoryW() failed";
      LODWORD(v3) = LastError;
      goto LABEL_16;
    }
    LODWORD(v3) = winreAddTrailingBackslash(&FileName);
    if ( (_DWORD)v3 )
    {
      v11 = 9177;
      v7 = L"failed to add trailing back slash";
      goto LABEL_16;
    }
    v9 = StringCchCatW(&FileName, 0x12Eu, L"system32\\recovery\\RecoverySimulation.ini");
    if ( v9 < 0 )
    {
      UnattendLogW(
        2,
        L"WinReClearRecoveryTestMode %s (0x%x) in file %S line %d",
        L"Failed to append path to test mode simulation file",
        (unsigned int)v9,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        9179);
      LODWORD(v3) = (unsigned __int16)v9;
      goto LABEL_29;
    }
LABEL_18:
    UnattendLogW(0, L"Test mode simulation file: %s", &FileName);
    if ( Utils::DoesPathExist(&FileName) )
    {
      UnattendLogW(0, L"Test mode simulation file does not exist");
    }
    else
    {
      UnattendLogW(0, L"Delete test mode simulation file");
      if ( !DeleteFileW(&FileName) )
      {
        v3 = GetLastError();
        UnattendLogW(1, L"DeleteFileW() failed. 0x%x", v3);
        goto LABEL_29;
      }
    }
    v2 = 1;
    goto LABEL_29;
  }
  v12 = 0;
  LODWORD(v3) = StringCchLengthW(a1, 0x7FFFFFFFu, &v12);
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
  if ( !v12 || (v6 = L"%s\\%s", a1[v12 - 1] == 92) )
    v6 = L"%s%s";
  LODWORD(v3) = StringCchPrintfW(&FileName, 0x12Eu, v6, a1, L"system32\\recovery\\RecoverySimulation.ini");
  if ( (int)v3 >= 0 )
  {
    LODWORD(v3) = 0;
    goto LABEL_18;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = 15;
    goto LABEL_13;
  }
LABEL_14:
  LODWORD(v3) = (unsigned __int16)v3;
  if ( !(_WORD)v3 )
    goto LABEL_18;
  v11 = 9172;
  v7 = L"Failed to append path to test mode simulation file";
LABEL_16:
  UnattendLogW(
    2,
    L"WinReClearRecoveryTestMode %s (0x%x) in file %S line %d",
    v7,
    (unsigned int)v3,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    v11);
LABEL_29:
  AsmWinREClearRecoveryTestMode(v3);
  UnattendLogW(0, L"Exit WinReClearRecoveryTestMode return value: %d, last error: 0x%x", v2, (unsigned int)v3);
  UnattendFinalizeLog();
  TraceLoggingUnregister_EventUnregister();
  SetLastError(v3);
  return v2;
}

```

## disassembly

```asm
0x180020a40  push    rbp
0x180020a42  push    rbx
0x180020a43  push    rsi
0x180020a44  push    rdi
0x180020a45  lea     rbp, [rsp-1B8h]
0x180020a4d  sub     rsp, 2B8h
0x180020a54  mov     rax, cs:__security_cookie
0x180020a5b  xor     rax, rsp
0x180020a5e  mov     [rbp+1D0h+var_30], rax
0x180020a65  mov     rdi, rcx
0x180020a68  xor     eax, eax
0x180020a6a  lea     rcx, [rsp+2D0h+var_28E]; void *
0x180020a6f  mov     [rsp+2D0h+FileName], ax
0x180020a74  xor     edx, edx; Val
0x180020a76  mov     r8d, 25Ah; Size
0x180020a7c  xor     esi, esi
0x180020a7e  call    memset_0
0x180020a83  call    TraceLoggingRegisterEx_EventRegister_2U
0x180020a88  xor     ecx, ecx
0x180020a8a  call    UnattendInitializeLogEx2
0x180020a8f  lea     rdx, aEnterWinreclea_1; "Enter WinReClearRecoveryTestMode"
0x180020a96  xor     ecx, ecx
0x180020a98  call    UnattendLogW
0x180020a9d  mov     r8, rdi
0x180020aa0  lea     rdx, aParametersWind_2; "Parameters: winDir: %s"
0x180020aa7  xor     ecx, ecx
0x180020aa9  call    UnattendLogW
0x180020aae  test    rdi, rdi
0x180020ab1  jz      loc_180020C0F
0x180020ab7  lea     r8, [rsp+2D0h+var_2A0]; unsigned __int64 *
0x180020abc  mov     [rsp+2D0h+var_2A0], rsi
0x180020ac1  mov     edx, 7FFFFFFFh; unsigned __int64
0x180020ac6  mov     rcx, rdi; unsigned __int16 *
0x180020ac9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180020ace  mov     ebx, eax
0x180020ad0  test    eax, eax
0x180020ad2  jns     short loc_180020AF6
0x180020ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180020adb  lea     rax, WPP_GLOBAL_Control
0x180020ae2  cmp     rcx, rax
0x180020ae5  jz      loc_180020B6B
0x180020aeb  test    byte ptr [rcx+1Ch], 2
0x180020aef  jz      short loc_180020B6B
0x180020af1  lea     edx, [rsi+0Eh]
0x180020af4  jmp     short loc_180020B58
0x180020af6  mov     rax, [rsp+2D0h+var_2A0]
0x180020afb  test    rax, rax
0x180020afe  jz      short loc_180020B0F
0x180020b00  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180020b06  lea     r8, aSS_1; "%s\\%s"
0x180020b0d  jnz     short loc_180020B16
0x180020b0f  lea     r8, aSS_2; "%s%s"
0x180020b16  lea     rax, aSystem32Recove_0; "system32\\recovery\\RecoverySimulation."...
0x180020b1d  mov     r9, rdi
0x180020b20  mov     edx, 12Eh; unsigned __int64
0x180020b25  mov     [rsp+2D0h+var_2B0], rax
0x180020b2a  lea     rcx, [rsp+2D0h+FileName]; unsigned __int16 *
0x180020b2f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020b34  mov     ebx, eax
0x180020b36  test    eax, eax
0x180020b38  jns     short loc_180020BA6
0x180020b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b41  lea     rax, WPP_GLOBAL_Control
0x180020b48  cmp     rcx, rax
0x180020b4b  jz      short loc_180020B6B
0x180020b4d  test    byte ptr [rcx+1Ch], 2
0x180020b51  jz      short loc_180020B6B
0x180020b53  mov     edx, 0Fh
0x180020b58  mov     rcx, [rcx+10h]
0x180020b5c  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180020b63  mov     r9d, ebx
0x180020b66  call    WPP_SF_d
0x180020b6b  movzx   ebx, bx
0x180020b6e  test    ebx, ebx
0x180020b70  jz      short loc_180020BA8
0x180020b72  mov     [rsp+2D0h+var_2A8], 23D4h
0x180020b7a  lea     r8, aFailedToAppend_2; "Failed to append path to test mode simu"...
0x180020b81  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180020b88  mov     r9d, ebx
0x180020b8b  lea     rdx, aWinreclearreco_0; "WinReClearRecoveryTestMode %s (0x%x) in"...
0x180020b92  mov     [rsp+2D0h+var_2B0], rax
0x180020b97  mov     ecx, 2
0x180020b9c  call    UnattendLogW
0x180020ba1  jmp     loc_180020CC8
0x180020ba6  xor     ebx, ebx
0x180020ba8  lea     r8, [rsp+2D0h+FileName]
0x180020bad  xor     ecx, ecx
0x180020baf  lea     rdx, aTestModeSimula_2; "Test mode simulation file: %s"
0x180020bb6  call    UnattendLogW
0x180020bbb  lea     rcx, [rsp+2D0h+FileName]; unsigned __int16 *
0x180020bc0  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180020bc5  xor     ecx, ecx
0x180020bc7  test    eax, eax
0x180020bc9  jnz     loc_180020CB7
0x180020bcf  lea     rdx, aDeleteTestMode; "Delete test mode simulation file"
0x180020bd6  call    UnattendLogW
0x180020bdb  lea     rcx, [rsp+2D0h+FileName]; lpFileName
0x180020be0  call    cs:__imp_DeleteFileW
0x180020be6  test    eax, eax
0x180020be8  jnz     loc_180020CC3
0x180020bee  call    cs:__imp_GetLastError
0x180020bf4  lea     rdx, aDeletefilewFai; "DeleteFileW() failed. 0x%x"
0x180020bfb  mov     ecx, 1
0x180020c00  mov     r8d, eax
0x180020c03  mov     ebx, eax
0x180020c05  call    UnattendLogW
0x180020c0a  jmp     loc_180020CC8
0x180020c0f  mov     edx, 12Eh; uSize
0x180020c14  lea     rcx, [rsp+2D0h+FileName]; lpBuffer
0x180020c19  call    cs:__imp_GetWindowsDirectoryW
0x180020c1f  test    eax, eax
0x180020c21  jnz     short loc_180020C3F
0x180020c23  call    cs:__imp_GetLastError
0x180020c29  mov     [rsp+2D0h+var_2A8], 23D8h
0x180020c31  lea     r8, aGetwindowsdire; "GetWindowsDirectoryW() failed"
0x180020c38  mov     ebx, eax
0x180020c3a  jmp     loc_180020B81
0x180020c3f  lea     rcx, [rsp+2D0h+FileName]
0x180020c44  call    winreAddTrailingBackslash
0x180020c49  mov     ebx, eax
0x180020c4b  test    eax, eax
0x180020c4d  jz      short loc_180020C63
0x180020c4f  mov     [rsp+2D0h+var_2A8], 23D9h
0x180020c57  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180020c5e  jmp     loc_180020B81
0x180020c63  lea     r8, aSystem32Recove_0; "system32\\recovery\\RecoverySimulation."...
0x180020c6a  mov     edx, 12Eh; unsigned __int64
0x180020c6f  lea     rcx, [rsp+2D0h+FileName]; unsigned __int16 *
0x180020c74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020c79  mov     edi, eax
0x180020c7b  test    eax, eax
0x180020c7d  jns     loc_180020BA8
0x180020c83  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180020c8a  mov     [rsp+2D0h+var_2A8], 23DBh
0x180020c92  mov     r9d, edi
0x180020c95  mov     [rsp+2D0h+var_2B0], rax
0x180020c9a  lea     r8, aFailedToAppend_2; "Failed to append path to test mode simu"...
0x180020ca1  mov     ecx, 2
0x180020ca6  lea     rdx, aWinreclearreco_0; "WinReClearRecoveryTestMode %s (0x%x) in"...
0x180020cad  call    UnattendLogW
0x180020cb2  movzx   ebx, di
0x180020cb5  jmp     short loc_180020CC8
0x180020cb7  lea     rdx, aTestModeSimula; "Test mode simulation file does not exis"...
0x180020cbe  call    UnattendLogW
0x180020cc3  mov     esi, 1
0x180020cc8  mov     ecx, ebx; unsigned int
0x180020cca  call    ?AsmWinREClearRecoveryTestMode@@YAXK@Z; AsmWinREClearRecoveryTestMode(ulong)
0x180020ccf  mov     r9d, ebx
0x180020cd2  lea     rdx, aExitWinreclear_1; "Exit WinReClearRecoveryTestMode return "...
0x180020cd9  mov     r8d, esi
0x180020cdc  xor     ecx, ecx
0x180020cde  call    UnattendLogW
0x180020ce3  call    UnattendFinalizeLog
0x180020ce8  call    TraceLoggingUnregister_EventUnregister
0x180020ced  mov     ecx, ebx; dwErrCode
0x180020cef  call    cs:__imp_SetLastError
0x180020cf5  mov     eax, esi
0x180020cf7  mov     rcx, [rbp+1D0h+var_30]
0x180020cfe  xor     rcx, rsp; StackCookie
0x180020d01  call    __security_check_cookie
0x180020d06  add     rsp, 2B8h
0x180020d0d  pop     rdi
0x180020d0e  pop     rsi
0x180020d0f  pop     rbx
0x180020d10  pop     rbp
0x180020d11  retn
```

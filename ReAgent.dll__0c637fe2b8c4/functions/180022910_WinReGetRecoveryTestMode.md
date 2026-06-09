# WinReGetRecoveryTestMode

- ea: `0x180022910`
- end: `0x1800230a6`
- name: `WinReGetRecoveryTestMode`
- size: `1942`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

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
- `0x180022910`
- `0x18003e624`
- `0x18004d52c`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180022c33`
- `msvcrt!_wcsicmp` at `0x180022dc6`
- `msvcrt!_wcsicmp` at `0x180022fd5`
- `msvcrt!_wcsicmp` at `0x180022c33`
- `msvcrt!_wcsicmp` at `0x180022dc6`
- `msvcrt!_wcsicmp` at `0x180022fd5`
- `msvcrt!swscanf_s` at `0x180022f55`
- `msvcrt!swscanf_s` at `0x180022f55`
- `KERNEL32!GetLastError` at `0x180022b25`
- `KERNEL32!GetLastError` at `0x180022df1`
- `KERNEL32!GetLastError` at `0x180022b25`
- `KERNEL32!GetLastError` at `0x180022df1`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022c1b`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022daa`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022ed4`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022fbd`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022c1b`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022daa`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022ed4`
- `KERNEL32!GetPrivateProfileStringW` at `0x180022fbd`
- `KERNEL32!SetLastError` at `0x180023079`
- `KERNEL32!SetLastError` at `0x180023079`
- `KERNEL32!GetWindowsDirectoryW` at `0x180022b1b`
- `KERNEL32!GetWindowsDirectoryW` at `0x180022de7`
- `KERNEL32!GetWindowsDirectoryW` at `0x180022b1b`
- `KERNEL32!GetWindowsDirectoryW` at `0x180022de7`

## string_xrefs

- `0x180022aed`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180022b7d`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180022e4f`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180022a77`: `system32\recovery\RecoverySimulation.ini`
- `0x180022b61`: `system32\recovery\RecoverySimulation.ini`
- `0x180022ae3`: `Failed to append path to test mode simulation file`
- `0x180022b94`: `Failed to append path to test mode simulation file`
- `0x180022d3a`: `Failed to append path to test mode simulation file`
- `0x180022e66`: `Failed to append path to test mode simulation file`
- `0x180022b33`: `GetWindowsDirectoryW() failed`
- `0x180022dff`: `GetWindowsDirectoryW() failed`
- `0x180022cd5`: `system32\recovery\RecoverySimulationResults.ini`
- `0x180022e31`: `system32\recovery\RecoverySimulationResults.ini`
- `0x180022da0`: `Completed`
- `0x180022e98`: `Test mode was %scompleted`

## pseudocode

```c
__int64 __fastcall WinReGetRecoveryTestMode(unsigned __int16 *a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, __int64 a5)
{
  const unsigned __int16 *v9; // r12
  int v10; // eax
  void *v11; // r11
  signed int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  const unsigned __int16 *v16; // r8
  const wchar_t *v17; // r8
  DWORD LastError; // eax
  const wchar_t *v19; // r15
  const wchar_t *v20; // r8
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  bool v23; // zf
  _DWORD *v24; // rax
  DWORD v25; // eax
  int v26; // edi
  const wchar_t *v27; // r8
  _DWORD *v28; // rax
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h]
  unsigned int v32; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v34; // [rsp+58h] [rbp-A8h] BYREF
  int v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+64h] [rbp-9Ch] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  WCHAR FileName; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[606]; // [rsp+72h] [rbp-8Eh] BYREF
  WCHAR ReturnedString[304]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Buffer; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v42[606]; // [rsp+532h] [rbp+432h] BYREF

  v34 = a3;
  v32 = 0;
  Buffer = 0;
  memset_0(v42, 0, 0x25Au);
  FileName = 0;
  memset_0(v39, 0, 0x25Au);
  memset_0(ReturnedString, 0, 0x25Cu);
  TraceLoggingRegisterEx_EventRegister_2U();
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReGetRecoveryTestMode");
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v12 = 87;
    UnattendLogW(1, L"Invalid parameters. 0x%x", 87);
    goto LABEL_74;
  }
  UnattendLogW(0, L"Parameters: winDir: %s", a1);
  v9 = L"%s\\%s";
  if ( a1 )
  {
    v33 = 0;
    v10 = StringCchLengthW(a1, 0x7FFFFFFFu, &v33);
    LOWORD(v12) = v10;
    if ( v10 >= 0 )
    {
      if ( !v33 || (v16 = L"%s\\%s", a1[v33 - 1] == 92) )
        v16 = L"%s%s";
      v12 = StringCchPrintfW(&Buffer, 0x12Eu, v16, a1, L"system32\\recovery\\RecoverySimulation.ini");
      if ( v12 >= 0 )
        goto LABEL_27;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_18;
      v14 = 15;
      v15 = (unsigned int)v12;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == v11 || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_18:
        v12 = (unsigned __int16)v12;
        if ( (_WORD)v12 )
        {
          LODWORD(lpFileName) = 9253;
          v17 = L"Failed to append path to test mode simulation file";
LABEL_20:
          UnattendLogW(
            2,
            L"WinReGetRecoveryTestMode %s (0x%x) in file %S line %d",
            v17,
            (unsigned int)v12,
            "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
            lpFileName);
          goto LABEL_74;
        }
        goto LABEL_27;
      }
      v14 = 14;
      v15 = (unsigned int)v10;
    }
    WPP_SF_d(v13[2], v14, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, v15);
    goto LABEL_18;
  }
  if ( !GetWindowsDirectoryW(&Buffer, 0x12Eu) )
  {
    LastError = GetLastError();
    LODWORD(lpFileName) = 9257;
    v17 = L"GetWindowsDirectoryW() failed";
    v12 = LastError;
    goto LABEL_20;
  }
  v12 = winreAddTrailingBackslash(&Buffer);
  if ( v12 )
  {
    LODWORD(lpFileName) = 9258;
    v17 = L"failed to add trailing back slash";
    goto LABEL_20;
  }
  v12 = StringCchCatW(&Buffer, 0x12Eu, L"system32\\recovery\\RecoverySimulation.ini");
  if ( v12 < 0 )
  {
    UnattendLogW(
      2,
      L"WinReGetRecoveryTestMode %s (0x%x) in file %S line %d",
      L"Failed to append path to test mode simulation file",
      (unsigned int)v12,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      9260);
    v12 = (unsigned __int16)v12;
    goto LABEL_74;
  }
LABEL_27:
  UnattendLogW(0, L"Test mode simulation file: %s", &Buffer);
  v19 = &cchOriginalDestLength;
  if ( Utils::DoesPathExist(&Buffer) )
  {
    UnattendLogW(0, L"Test mode simulation file does not exist");
    *a2 = 0;
  }
  else
  {
    UnattendLogW(0, L"Test mode simulation file exists");
    if ( GetPrivateProfileStringW(L"Recovery", L"Active", 0, ReturnedString, 0x12Eu, &Buffer) )
      *a2 = _wcsicmp(ReturnedString, L"Yes") == 0;
    v20 = &cchOriginalDestLength;
    if ( !*a2 )
      v20 = L"not ";
    UnattendLogW(0, L"Test mode is %sactive", v20);
  }
  if ( !a1 )
  {
    if ( !GetWindowsDirectoryW(&FileName, 0x12Eu) )
    {
      v25 = GetLastError();
      LODWORD(lpFileName) = 9299;
      v17 = L"GetWindowsDirectoryW() failed";
      v12 = v25;
      goto LABEL_20;
    }
    v12 = winreAddTrailingBackslash(&FileName);
    if ( v12 )
    {
      LODWORD(lpFileName) = 9300;
      v17 = L"failed to add trailing back slash";
      goto LABEL_20;
    }
    v26 = StringCchCatW(&FileName, 0x12Eu, L"system32\\recovery\\RecoverySimulationResults.ini");
    if ( v26 < 0 )
    {
      LODWORD(lpFileName) = 9302;
      UnattendLogW(
        2,
        L"WinReGetRecoveryTestMode %s (0x%x) in file %S line %d",
        L"Failed to append path to test mode simulation file",
        (unsigned int)v26,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        lpFileName);
      v12 = (unsigned __int16)v26;
      goto LABEL_74;
    }
    goto LABEL_50;
  }
  v33 = 0;
  v12 = StringCchLengthW(a1, 0x7FFFFFFFu, &v33);
  if ( v12 >= 0 )
  {
    if ( !v33 || a1[v33 - 1] == 92 )
      v9 = L"%s%s";
    v12 = StringCchPrintfW(&FileName, 0x12Eu, v9, a1, L"system32\\recovery\\RecoverySimulationResults.ini");
    if ( v12 >= 0 )
    {
      v12 = 0;
      goto LABEL_50;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v22 = 15;
    goto LABEL_46;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v22 = 14;
LABEL_46:
    WPP_SF_d(v21[2], v22, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v12);
  }
LABEL_47:
  v12 = (unsigned __int16)v12;
  if ( (_WORD)v12 )
  {
    LODWORD(lpFileName) = 9295;
    v17 = L"Failed to append path to test mode simulation file";
    goto LABEL_20;
  }
LABEL_50:
  UnattendLogW(0, L"Test mode simulation result file: %s", &FileName);
  if ( Utils::DoesPathExist(&FileName) )
  {
    UnattendLogW(0, L"Test mode simulation result file does not exist");
    *v34 = 0;
    *a4 = 0;
    *(_OWORD *)a5 = 0;
  }
  else
  {
    UnattendLogW(0, L"Test mode simulation file exists");
    if ( GetPrivateProfileStringW(L"Results", L"Completed", 0, ReturnedString, 0x12Eu, &FileName) )
    {
      v23 = _wcsicmp(ReturnedString, L"Yes") == 0;
      v24 = v34;
      *v34 = v23;
    }
    else
    {
      v24 = v34;
    }
    v27 = &cchOriginalDestLength;
    if ( !*v24 )
      v27 = L"not ";
    UnattendLogW(0, L"Test mode was %scompleted", v27);
    *(_OWORD *)a5 = 0;
    if ( GetPrivateProfileStringW(L"Results", L"Time", 0, ReturnedString, 0x12Eu, &FileName) )
    {
      UnattendLogW(0, L"Test mode last run time: %s", ReturnedString);
      v35 = 0;
      v36 = 0;
      v37 = 0;
      LODWORD(v33) = 0;
      LODWORD(v34) = 0;
      v32 = 0;
      if ( swscanf_s(ReturnedString, L"%u/%u/%u %u:%u:%u", &v35, &v36, &v37, &v33, &v34, &v32) == 6 )
      {
        *(_WORD *)(a5 + 2) = v35;
        *(_WORD *)(a5 + 6) = v36;
        *(_WORD *)a5 = v37;
        *(_WORD *)(a5 + 8) = v33;
        *(_WORD *)(a5 + 10) = (_WORD)v34;
        *(_WORD *)(a5 + 12) = v32;
      }
    }
    if ( GetPrivateProfileStringW(L"Results", L"Success", 0, ReturnedString, 0x12Eu, &FileName) )
    {
      v23 = _wcsicmp(ReturnedString, L"Yes") == 0;
      v28 = a4;
      *a4 = v23;
    }
    else
    {
      v28 = a4;
    }
    if ( !*v28 )
      v19 = L"not ";
    UnattendLogW(0, L"Test mode was %ssuccessful", v19);
  }
  v32 = 1;
LABEL_74:
  AsmWinREClearRecoveryTestMode(v12);
  UnattendLogW(0, L"Exit WinReGetRecoveryTestMode return value: %d, last error: 0x%x", v32, (unsigned int)v12);
  UnattendFinalizeLog();
  TraceLoggingUnregister_EventUnregister();
  SetLastError(v12);
  return v32;
}

```

## disassembly

```asm
0x180022910  push    rbp
0x180022912  push    rbx
0x180022913  push    rsi
0x180022914  push    rdi
0x180022915  push    r12
0x180022917  push    r13
0x180022919  push    r14
0x18002291b  push    r15
0x18002291d  lea     rbp, [rsp-6A8h]
0x180022925  sub     rsp, 7A8h
0x18002292c  mov     rax, cs:__security_cookie
0x180022933  xor     rax, rsp
0x180022936  mov     [rbp+6E0h+var_50], rax
0x18002293d  mov     r14, [rbp+6E0h+arg_20]
0x180022944  mov     rbx, r9
0x180022947  mov     rsi, r8
0x18002294a  mov     [rsp+7E0h+var_788], r8
0x18002294f  mov     r13, rdx
0x180022952  mov     [rsp+7E0h+var_7A0], rbx
0x180022957  mov     rdi, rcx
0x18002295a  mov     [rsp+7E0h+var_798], 0
0x180022962  xor     eax, eax
0x180022964  lea     rcx, [rbp+6E0h+var_2AE]; void *
0x18002296b  mov     r15d, 25Ah
0x180022971  mov     [rbp+6E0h+Buffer], ax
0x180022978  mov     r8d, r15d; Size
0x18002297b  xor     edx, edx; Val
0x18002297d  call    memset_0
0x180022982  xor     eax, eax
0x180022984  lea     rcx, [rsp+7E0h+var_76E]; void *
0x180022989  mov     r8d, r15d; Size
0x18002298c  mov     [rsp+7E0h+FileName], ax
0x180022991  xor     edx, edx; Val
0x180022993  call    memset_0
0x180022998  xor     edx, edx; Val
0x18002299a  lea     r8d, [r15+2]; Size
0x18002299e  lea     rcx, [rbp+6E0h+ReturnedString]; void *
0x1800229a5  call    memset_0
0x1800229aa  call    TraceLoggingRegisterEx_EventRegister_2U
0x1800229af  xor     ecx, ecx
0x1800229b1  call    UnattendInitializeLogEx2
0x1800229b6  lea     rdx, aEnterWinregetr; "Enter WinReGetRecoveryTestMode"
0x1800229bd  xor     ecx, ecx
0x1800229bf  call    UnattendLogW
0x1800229c4  test    r13, r13
0x1800229c7  jz      loc_180023039
0x1800229cd  test    rsi, rsi
0x1800229d0  jz      loc_180023039
0x1800229d6  test    rbx, rbx
0x1800229d9  jz      loc_180023039
0x1800229df  test    r14, r14
0x1800229e2  jz      loc_180023039
0x1800229e8  mov     r8, rdi
0x1800229eb  lea     rdx, aParametersWind_2; "Parameters: winDir: %s"
0x1800229f2  xor     ecx, ecx
0x1800229f4  call    UnattendLogW
0x1800229f9  lea     r11, WPP_GLOBAL_Control
0x180022a00  mov     r15d, 2
0x180022a06  lea     r12, aSS_1; "%s\\%s"
0x180022a0d  test    rdi, rdi
0x180022a10  jz      loc_180022B0D
0x180022a16  lea     r8, [rsp+7E0h+var_790]; unsigned __int64 *
0x180022a1b  mov     [rsp+7E0h+var_790], 0
0x180022a24  mov     edx, 7FFFFFFFh; unsigned __int64
0x180022a29  mov     rcx, rdi; unsigned __int16 *
0x180022a2c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180022a31  mov     ebx, eax
0x180022a33  mov     esi, 12Eh
0x180022a38  test    eax, eax
0x180022a3a  jns     short loc_180022A5B
0x180022a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a43  cmp     rcx, r11
0x180022a46  jz      loc_180022AD0
0x180022a4c  test    [rcx+1Ch], r15b
0x180022a50  jz      short loc_180022AD0
0x180022a52  lea     edx, [r15+0Ch]
0x180022a56  mov     r9d, eax
0x180022a59  jmp     short loc_180022AC0
0x180022a5b  mov     rax, [rsp+7E0h+var_790]
0x180022a60  test    rax, rax
0x180022a63  jz      short loc_180022A70
0x180022a65  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180022a6b  mov     r8, r12
0x180022a6e  jnz     short loc_180022A77
0x180022a70  lea     r8, aSS_2; "%s%s"
0x180022a77  lea     rax, aSystem32Recove_0; "system32\\recovery\\RecoverySimulation."...
0x180022a7e  mov     r9, rdi
0x180022a81  mov     rdx, rsi; unsigned __int64
0x180022a84  mov     qword ptr [rsp+7E0h+nSize], rax
0x180022a89  lea     rcx, [rbp+6E0h+Buffer]; unsigned __int16 *
0x180022a90  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022a95  mov     ebx, eax
0x180022a97  test    eax, eax
0x180022a99  jns     loc_180022BB2
0x180022a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aa6  lea     rax, WPP_GLOBAL_Control
0x180022aad  cmp     rcx, rax
0x180022ab0  jz      short loc_180022AD0
0x180022ab2  test    [rcx+1Ch], r15b
0x180022ab6  jz      short loc_180022AD0
0x180022ab8  mov     edx, 0Fh
0x180022abd  mov     r9d, ebx
0x180022ac0  mov     rcx, [rcx+10h]
0x180022ac4  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180022acb  call    WPP_SF_d
0x180022ad0  movzx   ebx, bx
0x180022ad3  test    ebx, ebx
0x180022ad5  jz      loc_180022BB2
0x180022adb  mov     dword ptr [rsp+7E0h+lpFileName], 2425h
0x180022ae3  lea     r8, aFailedToAppend_2; "Failed to append path to test mode simu"...
0x180022aea  mov     ecx, r15d
0x180022aed  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180022af4  mov     r9d, ebx
0x180022af7  lea     rdx, aWinregetrecove_0; "WinReGetRecoveryTestMode %s (0x%x) in f"...
0x180022afe  mov     qword ptr [rsp+7E0h+nSize], rax
0x180022b03  call    UnattendLogW
0x180022b08  jmp     loc_180023050
0x180022b0d  mov     esi, 12Eh
0x180022b12  lea     rcx, [rbp+6E0h+Buffer]; lpBuffer
0x180022b19  mov     edx, esi; uSize
0x180022b1b  call    cs:__imp_GetWindowsDirectoryW
0x180022b21  test    eax, eax
0x180022b23  jnz     short loc_180022B3E
0x180022b25  call    cs:__imp_GetLastError
0x180022b2b  mov     dword ptr [rsp+7E0h+lpFileName], 2429h
0x180022b33  lea     r8, aGetwindowsdire; "GetWindowsDirectoryW() failed"
0x180022b3a  mov     ebx, eax
0x180022b3c  jmp     short loc_180022AEA
0x180022b3e  lea     rcx, [rbp+6E0h+Buffer]
0x180022b45  call    winreAddTrailingBackslash
0x180022b4a  mov     ebx, eax
0x180022b4c  test    eax, eax
0x180022b4e  jz      short loc_180022B61
0x180022b50  mov     dword ptr [rsp+7E0h+lpFileName], 242Ah
0x180022b58  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180022b5f  jmp     short loc_180022AEA
0x180022b61  lea     r8, aSystem32Recove_0; "system32\\recovery\\RecoverySimulation."...
0x180022b68  mov     rdx, rsi; unsigned __int64
0x180022b6b  lea     rcx, [rbp+6E0h+Buffer]; unsigned __int16 *
0x180022b72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022b77  mov     ebx, eax
0x180022b79  test    eax, eax
0x180022b7b  jns     short loc_180022BB2
0x180022b7d  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180022b84  mov     dword ptr [rsp+7E0h+lpFileName], 242Ch
0x180022b8c  mov     r9d, ebx
0x180022b8f  mov     qword ptr [rsp+7E0h+nSize], rax
0x180022b94  lea     r8, aFailedToAppend_2; "Failed to append path to test mode simu"...
0x180022b9b  mov     ecx, r15d
0x180022b9e  lea     rdx, aWinregetrecove_0; "WinReGetRecoveryTestMode %s (0x%x) in f"...
0x180022ba5  call    UnattendLogW
0x180022baa  movzx   ebx, bx
0x180022bad  jmp     loc_180023050
0x180022bb2  lea     r8, [rbp+6E0h+Buffer]
0x180022bb9  xor     ecx, ecx
0x180022bbb  lea     rdx, aTestModeSimula_2; "Test mode simulation file: %s"
0x180022bc2  call    UnattendLogW
0x180022bc7  lea     rcx, [rbp+6E0h+Buffer]; unsigned __int16 *
0x180022bce  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180022bd3  xor     ecx, ecx
0x180022bd5  lea     rbx, aNot; "not "
0x180022bdc  lea     r15, cchOriginalDestLength
0x180022be3  test    eax, eax
0x180022be5  jnz     short loc_180022C60
0x180022be7  lea     rdx, aTestModeSimula_0; "Test mode simulation file exists"
0x180022bee  call    UnattendLogW
0x180022bf3  lea     rax, [rbp+6E0h+Buffer]
0x180022bfa  xor     r8d, r8d; lpDefault
0x180022bfd  mov     [rsp+7E0h+lpFileName], rax; lpFileName
0x180022c02  lea     r9, [rbp+6E0h+ReturnedString]; lpReturnedString
0x180022c09  lea     rdx, KeyName; "Active"
0x180022c10  mov     [rsp+7E0h+nSize], esi; nSize
0x180022c14  lea     rcx, AppName; "Recovery"
0x180022c1b  call    cs:__imp_GetPrivateProfileStringW
0x180022c21  test    eax, eax
0x180022c23  jz      short loc_180022C44
0x180022c25  lea     rdx, aYes_0; "Yes"
0x180022c2c  lea     rcx, [rbp+6E0h+ReturnedString]; String1
0x180022c33  call    cs:__imp__wcsicmp
0x180022c39  xor     ecx, ecx
0x180022c3b  test    eax, eax
0x180022c3d  setz    cl
0x180022c40  mov     [r13+0], ecx
0x180022c44  cmp     dword ptr [r13+0], 0
0x180022c49  lea     rdx, aTestModeIsSact; "Test mode is %sactive"
0x180022c50  mov     r8, r15
0x180022c53  cmovz   r8, rbx
0x180022c57  xor     ecx, ecx
0x180022c59  call    UnattendLogW
0x180022c5e  jmp     short loc_180022C74
0x180022c60  lea     rdx, aTestModeSimula; "Test mode simulation file does not exis"...
0x180022c67  call    UnattendLogW
0x180022c6c  mov     dword ptr [r13+0], 0
0x180022c74  xor     r13d, r13d
0x180022c77  test    rdi, rdi
0x180022c7a  jz      loc_180022DE0
0x180022c80  lea     r8, [rsp+7E0h+var_790]; unsigned __int64 *
0x180022c85  mov     [rsp+7E0h+var_790], r13
0x180022c8a  mov     edx, 7FFFFFFFh; unsigned __int64
0x180022c8f  mov     rcx, rdi; unsigned __int16 *
0x180022c92  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180022c97  mov     ebx, eax
0x180022c99  test    eax, eax
0x180022c9b  jns     short loc_180022CBC
0x180022c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ca4  lea     rax, WPP_GLOBAL_Control
0x180022cab  cmp     rcx, rax
0x180022cae  jz      short loc_180022D2B
0x180022cb0  test    byte ptr [rcx+1Ch], 2
0x180022cb4  jz      short loc_180022D2B
0x180022cb6  lea     edx, [r13+0Eh]
0x180022cba  jmp     short loc_180022D18
0x180022cbc  mov     rax, [rsp+7E0h+var_790]
0x180022cc1  test    rax, rax
0x180022cc4  jz      short loc_180022CCE
0x180022cc6  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180022ccc  jnz     short loc_180022CD5
0x180022cce  lea     r12, aSS_2; "%s%s"
0x180022cd5  lea     r8, aSystem32Recove_1; "system32\\recovery\\RecoverySimulationR"...
0x180022cdc  mov     r9, rdi
0x180022cdf  mov     qword ptr [rsp+7E0h+nSize], r8
0x180022ce4  lea     rcx, [rsp+7E0h+FileName]; unsigned __int16 *
0x180022ce9  mov     r8, r12; unsigned __int16 *
0x180022cec  mov     rdx, rsi; unsigned __int64
0x180022cef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022cf4  mov     ebx, eax
0x180022cf6  test    eax, eax
0x180022cf8  jns     short loc_180022D4B
0x180022cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d01  lea     rax, WPP_GLOBAL_Control
0x180022d08  cmp     rcx, rax
0x180022d0b  jz      short loc_180022D2B
0x180022d0d  test    byte ptr [rcx+1Ch], 2
0x180022d11  jz      short loc_180022D2B
0x180022d13  mov     edx, 0Fh
0x180022d18  mov     rcx, [rcx+10h]
0x180022d1c  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180022d23  mov     r9d, ebx
0x180022d26  call    WPP_SF_d
0x180022d2b  movzx   ebx, bx
0x180022d2e  test    ebx, ebx
0x180022d30  jz      short loc_180022D4E
0x180022d32  mov     dword ptr [rsp+7E0h+lpFileName], 244Fh
0x180022d3a  lea     r8, aFailedToAppend_2; "Failed to append path to test mode simu"...
0x180022d41  mov     ecx, 2
0x180022d46  jmp     loc_180022AED
0x180022d4b  mov     ebx, r13d
0x180022d4e  lea     r8, [rsp+7E0h+FileName]
0x180022d53  xor     ecx, ecx
0x180022d55  lea     rdx, aTestModeSimula_3; "Test mode simulation result file: %s"
0x180022d5c  call    UnattendLogW
0x180022d61  lea     rcx, [rsp+7E0h+FileName]; unsigned __int16 *
0x180022d66  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180022d6b  xor     ecx, ecx
0x180022d6d  test    eax, eax
0x180022d6f  jnz     loc_18002300B
0x180022d75  lea     rdx, aTestModeSimula_0; "Test mode simulation file exists"
0x180022d7c  call    UnattendLogW
0x180022d81  lea     rax, [rsp+7E0h+FileName]
0x180022d86  xor     r8d, r8d; lpDefault
0x180022d89  mov     [rsp+7E0h+lpFileName], rax; lpFileName
0x180022d8e  lea     rdi, aResults; "Results"
0x180022d95  lea     r9, [rbp+6E0h+ReturnedString]; lpReturnedString
0x180022d9c  mov     [rsp+7E0h+nSize], esi; nSize
0x180022da0  lea     rdx, aCompleted; "Completed"
0x180022da7  mov     rcx, rdi; lpAppName
0x180022daa  call    cs:__imp_GetPrivateProfileStringW
0x180022db0  test    eax, eax
0x180022db2  jz      loc_180022E86
0x180022db8  lea     rdx, aYes_0; "Yes"
0x180022dbf  lea     rcx, [rbp+6E0h+ReturnedString]; String1
0x180022dc6  call    cs:__imp__wcsicmp
0x180022dcc  test    eax, eax
0x180022dce  mov     ecx, r13d
0x180022dd1  mov     rax, [rsp+7E0h+var_788]
0x180022dd6  setz    cl
0x180022dd9  mov     [rax], ecx
0x180022ddb  jmp     loc_180022E8B
0x180022de0  mov     edx, esi; uSize
0x180022de2  lea     rcx, [rsp+7E0h+FileName]; lpBuffer
0x180022de7  call    cs:__imp_GetWindowsDirectoryW
0x180022ded  test    eax, eax
0x180022def  jnz     short loc_180022E0D
0x180022df1  call    cs:__imp_GetLastError
0x180022df7  mov     dword ptr [rsp+7E0h+lpFileName], 2453h
0x180022dff  lea     r8, aGetwindowsdire; "GetWindowsDirectoryW() failed"
0x180022e06  mov     ebx, eax
0x180022e08  jmp     loc_180022D41
0x180022e0d  lea     rcx, [rsp+7E0h+FileName]
0x180022e12  call    winreAddTrailingBackslash
0x180022e17  mov     ebx, eax
0x180022e19  test    eax, eax
0x180022e1b  jz      short loc_180022E31
0x180022e1d  mov     dword ptr [rsp+7E0h+lpFileName], 2454h
0x180022e25  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x180022e2c  jmp     loc_180022D41
0x180022e31  lea     r8, aSystem32Recove_1; "system32\\recovery\\RecoverySimulationR"...
0x180022e38  mov     rdx, rsi; unsigned __int64
0x180022e3b  lea     rcx, [rsp+7E0h+FileName]; unsigned __int16 *
0x180022e40  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
  ... truncated ...
```

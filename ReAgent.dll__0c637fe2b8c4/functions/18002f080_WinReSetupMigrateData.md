# WinReSetupMigrateData

- ea: `0x18002f080`
- end: `0x18002f4b4`
- name: `WinReSetupMigrateData`
- size: `1076`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000196c`
- `0x180001adc`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000f044`
- `0x18002f080`
- `0x18003e05c`
- `0x18003e0e8`
- `0x180042b6c`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002f1c3`
- `KERNEL32!GetLastError` at `0x18002f43b`
- `KERNEL32!GetLastError` at `0x18002f1c3`
- `KERNEL32!GetLastError` at `0x18002f43b`

## string_xrefs

- `0x18002f3c5`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002f1cc`: `failed to get winre config, assuming WinRE is disabled: 0x%x`
- `0x18002f160`: `WinRELocation: %s, SourceImagePath: %s, DownlevelWinREPath: %s, OldOsWinDir: %s, NewOsWinDir: %s, RemoveSetupFilter: %s`
- `0x18002f2f2`: `WinRE is not installed or staged.  Nothing to do.`
- `0x18002f3cf`: `Failed to construct path to winre.wim`
- `0x18002f454`: `overriding return value to prevent rollback.`

## pseudocode

```c
__int64 __fastcall WinReSetupMigrateData(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        int a7)
{
  const wchar_t *v11; // r10
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rcx
  const unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  const unsigned __int16 *v16; // r8
  __int64 LastError; // rbx
  unsigned __int16 *v18; // r11
  int v19; // eax
  __int64 v20; // r11
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  const unsigned __int16 *v23; // r8
  int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  const unsigned __int16 *v27; // r8
  unsigned __int16 *v29; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+6Ch] [rbp-94h]
  __int16 v34; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 v35; // [rsp+2D8h] [rbp+1D8h] BYREF
  unsigned __int16 v36; // [rsp+F00h] [rbp+E00h] BYREF
  _BYTE v37[606]; // [rsp+F02h] [rbp+E02h] BYREF

  memset_0(&v31, 0, 0xEA0u);
  v36 = 0;
  memset_0(v37, 0, 0x25Au);
  TraceLoggingRegisterEx_EventRegister_2U();
  AsmMigrateDriversStart(a1, a2);
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetupMigrateData");
  v11 = L"Yes";
  v12 = a5;
  if ( !a6 )
    v11 = L"No";
  v13 = a4;
  v14 = a3;
  v15 = a2;
  if ( !a5 )
    v12 = L"NULL";
  v16 = a1;
  if ( !a4 )
    v13 = L"NULL";
  if ( !a3 )
    v14 = L"NULL";
  if ( !a2 )
    v15 = L"NULL";
  if ( !a1 )
    v16 = L"NULL";
  UnattendLogW(
    0,
    L"WinRELocation: %s, SourceImagePath: %s, DownlevelWinREPath: %s, OldOsWinDir: %s, NewOsWinDir: %s, RemoveSetupFilter: %s",
    v16,
    v15,
    v14,
    v13,
    v12,
    v11);
  if ( !a1 )
  {
    UnattendLogW(0, L"Looking for winre.wim");
    v31 = 3744;
    if ( !(unsigned int)WinReGetConfigInternal(0, 0, (__int64)&v31) )
    {
      LastError = GetLastError();
      UnattendLogW(2, L"failed to get winre config, assuming WinRE is disabled: 0x%x", LastError);
LABEL_55:
      UnattendLogW(0, L"overriding return value to prevent rollback.");
      goto LABEL_56;
    }
    if ( v32 && v35 )
    {
      v18 = &v35;
    }
    else
    {
      if ( !v33 || !v34 )
      {
        LODWORD(LastError) = 50;
        UnattendLogW(2, L"WinRE is not installed or staged.  Nothing to do.");
        goto LABEL_55;
      }
      v18 = (unsigned __int16 *)&v34;
    }
    v30[0] = 0;
    v19 = StringCchLengthW(v18, 0x7FFFFFFFu, v30);
    LOWORD(LastError) = v19;
    if ( v19 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v22 = 14;
LABEL_33:
        WPP_SF_d(v21[2], v22, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v19);
        goto LABEL_34;
      }
      goto LABEL_34;
    }
    if ( !v30[0] || (v23 = L"%s\\%s", *(_WORD *)(v20 + 2 * v30[0] - 2) == 92) )
      v23 = L"%s%s";
    v19 = StringCchPrintfW(&v36, 0x12Eu, v23, v20, L"Winre.wim");
    LOWORD(LastError) = v19;
    if ( v19 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v22 = 15;
        goto LABEL_33;
      }
LABEL_34:
      LODWORD(LastError) = (unsigned __int16)LastError;
      if ( (_WORD)LastError )
      {
        LODWORD(v29) = 2087;
LABEL_51:
        UnattendLogW(
          2,
          L"WinReSetupMigrateData %s (0x%x) in file %S line %d",
          L"Failed to construct path to winre.wim",
          (unsigned int)LastError,
          "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
          v29);
        goto LABEL_55;
      }
      goto LABEL_53;
    }
LABEL_52:
    LODWORD(LastError) = 0;
    goto LABEL_53;
  }
  v30[0] = 0;
  v24 = StringCchLengthW(a1, 0x7FFFFFFFu, v30);
  LOWORD(LastError) = v24;
  if ( v24 >= 0 )
  {
    if ( !v30[0] || (v27 = L"%s\\%s", a1[v30[0] - 1] == 92) )
      v27 = L"%s%s";
    v24 = StringCchPrintfW(&v36, 0x12Eu, v27, a1, L"Winre.wim");
    LOWORD(LastError) = v24;
    if ( v24 >= 0 )
      goto LABEL_52;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v26 = 15;
      goto LABEL_48;
    }
  }
  else
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v26 = 14;
LABEL_48:
      WPP_SF_d(v25[2], v26, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v24);
    }
  }
  LODWORD(LastError) = (unsigned __int16)LastError;
  if ( (_WORD)LastError )
  {
    LODWORD(v29) = 2099;
    goto LABEL_51;
  }
LABEL_53:
  UnattendLogW(0, L"Migrating drivers to %s", &v36);
  if ( !MigrateDataWithMount(&v36, 0, a2, a3, a1, a4, a5, a6, a7) )
  {
    LODWORD(LastError) = GetLastError();
    UnattendLogW(2, L"Failed to migrate drivers.");
    goto LABEL_55;
  }
LABEL_56:
  UnattendLogW(0, L"WinReSetupMigrateData returning %s", L"TRUE");
  UnattendFinalizeLog();
  AsmMigrateDriversEnd(1, LastError);
  TraceLoggingUnregister_EventUnregister();
  return 1;
}

```

## disassembly

```asm
0x18002f080  push    rbp
0x18002f082  push    rbx
0x18002f083  push    rsi
0x18002f084  push    rdi
0x18002f085  push    r12
0x18002f087  push    r13
0x18002f089  push    r14
0x18002f08b  push    r15
0x18002f08d  lea     rbp, [rsp-1078h]
0x18002f095  mov     eax, 1178h
0x18002f09a  call    _alloca_probe
0x18002f09f  sub     rsp, rax
0x18002f0a2  mov     rax, cs:__security_cookie
0x18002f0a9  xor     rax, rsp
0x18002f0ac  mov     [rbp+10B0h+var_50], rax
0x18002f0b3  mov     r12, [rbp+10B0h+arg_20]
0x18002f0ba  mov     r14, r8
0x18002f0bd  mov     rsi, rdx
0x18002f0c0  mov     rdi, rcx
0x18002f0c3  xor     edx, edx; Val
0x18002f0c5  lea     rcx, [rsp+11B0h+var_1150]; void *
0x18002f0ca  mov     r8d, 0EA0h; Size
0x18002f0d0  mov     r15, r9
0x18002f0d3  call    memset_0
0x18002f0d8  xor     ebx, ebx
0x18002f0da  lea     rcx, [rbp+10B0h+var_2AE]; void *
0x18002f0e1  xor     edx, edx; Val
0x18002f0e3  mov     [rbp+10B0h+var_2B0], bx
0x18002f0ea  mov     r8d, 25Ah; Size
0x18002f0f0  call    memset_0
0x18002f0f5  call    TraceLoggingRegisterEx_EventRegister_2U
0x18002f0fa  mov     rdx, rsi; unsigned __int16 *
0x18002f0fd  mov     rcx, rdi; unsigned __int16 *
0x18002f100  call    ?AsmMigrateDriversStart@@YAXPEBG0@Z; AsmMigrateDriversStart(ushort const *,ushort const *)
0x18002f105  xor     ecx, ecx
0x18002f107  call    UnattendInitializeLogEx2
0x18002f10c  lea     rdx, aEnterWinresetu_4; "Enter WinReSetupMigrateData"
0x18002f113  xor     ecx, ecx
0x18002f115  call    UnattendLogW
0x18002f11a  mov     r13d, [rbp+10B0h+arg_28]
0x18002f121  lea     r11, aNull_0; "NULL"
0x18002f128  test    r13d, r13d
0x18002f12b  lea     rax, aNo; "No"
0x18002f132  lea     r10, aYes_0; "Yes"
0x18002f139  mov     rdx, r12
0x18002f13c  cmovz   r10, rax
0x18002f140  mov     rcx, r15
0x18002f143  test    r12, r12
0x18002f146  mov     qword ptr [rsp+11B0h+var_1178], r10
0x18002f14b  mov     rax, r14
0x18002f14e  mov     r9, rsi
0x18002f151  cmovz   rdx, r11
0x18002f155  mov     r8, rdi
0x18002f158  test    r15, r15
0x18002f15b  mov     [rsp+11B0h+var_1180], rdx
0x18002f160  lea     rdx, aWinrelocationS; "WinRELocation: %s, SourceImagePath: %s,"...
0x18002f167  cmovz   rcx, r11
0x18002f16b  test    r14, r14
0x18002f16e  mov     [rsp+11B0h+var_1188], rcx
0x18002f173  cmovz   rax, r11
0x18002f177  test    rsi, rsi
0x18002f17a  mov     [rsp+11B0h+var_1190], rax
0x18002f17f  cmovz   r9, r11
0x18002f183  test    rdi, rdi
0x18002f186  cmovz   r8, r11
0x18002f18a  xor     ecx, ecx
0x18002f18c  call    UnattendLogW
0x18002f191  test    rdi, rdi
0x18002f194  jnz     loc_18002F2FE
0x18002f19a  lea     rdx, aLookingForWinr; "Looking for winre.wim"
0x18002f1a1  xor     ecx, ecx
0x18002f1a3  call    UnattendLogW
0x18002f1a8  lea     r8, [rsp+11B0h+var_1150]
0x18002f1ad  mov     [rsp+11B0h+var_1150], 0EA0h
0x18002f1b6  xor     edx, edx
0x18002f1b8  xor     ecx, ecx
0x18002f1ba  call    WinReGetConfigInternal
0x18002f1bf  test    eax, eax
0x18002f1c1  jnz     short loc_18002F1E2
0x18002f1c3  call    cs:__imp_GetLastError
0x18002f1c9  mov     r8d, eax
0x18002f1cc  lea     rdx, aFailedToGetWin_8; "failed to get winre config, assuming Wi"...
0x18002f1d3  lea     ecx, [rdi+2]
0x18002f1d6  mov     ebx, eax
0x18002f1d8  call    UnattendLogW
0x18002f1dd  jmp     loc_18002F454
0x18002f1e2  cmp     [rsp+11B0h+var_1148], ebx
0x18002f1e6  jz      short loc_18002F1FA
0x18002f1e8  cmp     bx, [rbp+10B0h+var_ED8]
0x18002f1ef  jz      short loc_18002F1FA
0x18002f1f1  lea     r11, [rbp+10B0h+var_ED8]
0x18002f1f8  jmp     short loc_18002F214
0x18002f1fa  cmp     [rsp+11B0h+var_1144], ebx
0x18002f1fe  jz      loc_18002F2ED
0x18002f204  cmp     bx, [rsp+11B0h+var_1134]
0x18002f209  jz      loc_18002F2ED
0x18002f20f  lea     r11, [rsp+11B0h+var_1134]
0x18002f214  lea     r8, [rsp+11B0h+var_1160]; unsigned __int64 *
0x18002f219  mov     [rsp+11B0h+var_1160], rbx
0x18002f21e  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002f223  mov     rcx, r11; unsigned __int16 *
0x18002f226  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f22b  mov     ebx, eax
0x18002f22d  test    eax, eax
0x18002f22f  jns     short loc_18002F259
0x18002f231  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f238  lea     rdx, WPP_GLOBAL_Control
0x18002f23f  cmp     rcx, rdx
0x18002f242  jz      loc_18002F2D5
0x18002f248  test    byte ptr [rcx+1Ch], 2
0x18002f24c  jz      loc_18002F2D5
0x18002f252  mov     edx, 0Eh
0x18002f257  jmp     short loc_18002F2C2
0x18002f259  mov     rax, [rsp+11B0h+var_1160]
0x18002f25e  test    rax, rax
0x18002f261  jz      short loc_18002F273
0x18002f263  cmp     word ptr [r11+rax*2-2], 5Ch ; '\'
0x18002f26a  lea     r8, aSS_1; "%s\\%s"
0x18002f271  jnz     short loc_18002F27A
0x18002f273  lea     r8, aSS_2; "%s%s"
0x18002f27a  lea     rax, aWinreWim; "Winre.wim"
0x18002f281  mov     r9, r11
0x18002f284  mov     edx, 12Eh; unsigned __int64
0x18002f289  mov     [rsp+11B0h+var_1190], rax
0x18002f28e  lea     rcx, [rbp+10B0h+var_2B0]; unsigned __int16 *
0x18002f295  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f29a  mov     ebx, eax
0x18002f29c  test    eax, eax
0x18002f29e  jns     loc_18002F3EE
0x18002f2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2ab  lea     rdx, WPP_GLOBAL_Control
0x18002f2b2  cmp     rcx, rdx
0x18002f2b5  jz      short loc_18002F2D5
0x18002f2b7  test    byte ptr [rcx+1Ch], 2
0x18002f2bb  jz      short loc_18002F2D5
0x18002f2bd  mov     edx, 0Fh
0x18002f2c2  mov     rcx, [rcx+10h]
0x18002f2c6  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18002f2cd  mov     r9d, eax
0x18002f2d0  call    WPP_SF_d
0x18002f2d5  movzx   ebx, bx
0x18002f2d8  test    ebx, ebx
0x18002f2da  jz      loc_18002F3F0
0x18002f2e0  mov     dword ptr [rsp+11B0h+var_1188], 827h
0x18002f2e8  jmp     loc_18002F3C5
0x18002f2ed  mov     ebx, 32h ; '2'
0x18002f2f2  lea     rdx, aWinreIsNotInst_0; "WinRE is not installed or staged.  Noth"...
0x18002f2f9  jmp     loc_18002F44A
0x18002f2fe  lea     r8, [rsp+11B0h+var_1160]; unsigned __int64 *
0x18002f303  mov     [rsp+11B0h+var_1160], rbx
0x18002f308  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002f30d  mov     rcx, rdi; unsigned __int16 *
0x18002f310  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f315  mov     ebx, eax
0x18002f317  test    eax, eax
0x18002f319  jns     short loc_18002F33F
0x18002f31b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f322  lea     rdx, WPP_GLOBAL_Control
0x18002f329  cmp     rcx, rdx
0x18002f32c  jz      loc_18002F3B6
0x18002f332  test    byte ptr [rcx+1Ch], 2
0x18002f336  jz      short loc_18002F3B6
0x18002f338  mov     edx, 0Eh
0x18002f33d  jmp     short loc_18002F3A3
0x18002f33f  mov     rax, [rsp+11B0h+var_1160]
0x18002f344  test    rax, rax
0x18002f347  jz      short loc_18002F358
0x18002f349  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18002f34f  lea     r8, aSS_1; "%s\\%s"
0x18002f356  jnz     short loc_18002F35F
0x18002f358  lea     r8, aSS_2; "%s%s"
0x18002f35f  lea     rax, aWinreWim; "Winre.wim"
0x18002f366  mov     r9, rdi
0x18002f369  mov     edx, 12Eh; unsigned __int64
0x18002f36e  mov     [rsp+11B0h+var_1190], rax
0x18002f373  lea     rcx, [rbp+10B0h+var_2B0]; unsigned __int16 *
0x18002f37a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f37f  mov     ebx, eax
0x18002f381  test    eax, eax
0x18002f383  jns     short loc_18002F3EE
0x18002f385  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f38c  lea     rdx, WPP_GLOBAL_Control
0x18002f393  cmp     rcx, rdx
0x18002f396  jz      short loc_18002F3B6
0x18002f398  test    byte ptr [rcx+1Ch], 2
0x18002f39c  jz      short loc_18002F3B6
0x18002f39e  mov     edx, 0Fh
0x18002f3a3  mov     rcx, [rcx+10h]
0x18002f3a7  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18002f3ae  mov     r9d, eax
0x18002f3b1  call    WPP_SF_d
0x18002f3b6  movzx   ebx, bx
0x18002f3b9  test    ebx, ebx
0x18002f3bb  jz      short loc_18002F3F0
0x18002f3bd  mov     dword ptr [rsp+11B0h+var_1188], 833h
0x18002f3c5  lea     rax, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002f3cc  mov     r9d, ebx
0x18002f3cf  lea     r8, aFailedToConstr_1; "Failed to construct path to winre.wim"
0x18002f3d6  mov     [rsp+11B0h+var_1190], rax
0x18002f3db  lea     rdx, aWinresetupmigr_1; "WinReSetupMigrateData %s (0x%x) in file"...
0x18002f3e2  mov     ecx, 2
0x18002f3e7  call    UnattendLogW
0x18002f3ec  jmp     short loc_18002F454
0x18002f3ee  xor     ebx, ebx
0x18002f3f0  lea     r8, [rbp+10B0h+var_2B0]
0x18002f3f7  xor     ecx, ecx
0x18002f3f9  lea     rdx, aMigratingDrive; "Migrating drivers to %s"
0x18002f400  call    UnattendLogW
0x18002f405  mov     eax, [rbp+10B0h+arg_30]
0x18002f40b  lea     rcx, [rbp+10B0h+var_2B0]; unsigned __int16 *
0x18002f412  mov     [rsp+11B0h+var_1170], eax; int
0x18002f416  mov     r9, r14
0x18002f419  mov     [rsp+11B0h+var_1178], r13d; int
0x18002f41e  mov     r8, rsi
0x18002f421  mov     [rsp+11B0h+var_1180], r12; __int64
0x18002f426  xor     edx, edx
0x18002f428  mov     [rsp+11B0h+var_1188], r15; unsigned __int16 *
0x18002f42d  mov     [rsp+11B0h+var_1190], rdi; unsigned __int16 *
0x18002f432  call    MigrateDataWithMount
0x18002f437  test    eax, eax
0x18002f439  jnz     short loc_18002F462
0x18002f43b  call    cs:__imp_GetLastError
0x18002f441  mov     ebx, eax
0x18002f443  lea     rdx, aFailedToMigrat_0; "Failed to migrate drivers."
0x18002f44a  mov     ecx, 2
0x18002f44f  call    UnattendLogW
0x18002f454  lea     rdx, aOverridingRetu; "overriding return value to prevent roll"...
0x18002f45b  xor     ecx, ecx
0x18002f45d  call    UnattendLogW
0x18002f462  lea     r8, aTrue_0; "TRUE"
0x18002f469  xor     ecx, ecx
0x18002f46b  lea     rdx, aWinresetupmigr_8; "WinReSetupMigrateData returning %s"
0x18002f472  call    UnattendLogW
0x18002f477  call    UnattendFinalizeLog
0x18002f47c  mov     edx, ebx; unsigned int
0x18002f47e  mov     ebx, 1
0x18002f483  mov     ecx, ebx; int
0x18002f485  call    ?AsmMigrateDriversEnd@@YAXHK@Z; AsmMigrateDriversEnd(int,ulong)
0x18002f48a  call    TraceLoggingUnregister_EventUnregister
0x18002f48f  mov     eax, ebx
0x18002f491  mov     rcx, [rbp+10B0h+var_50]
0x18002f498  xor     rcx, rsp; StackCookie
0x18002f49b  call    __security_check_cookie
0x18002f4a0  add     rsp, 1178h
0x18002f4a7  pop     r15
0x18002f4a9  pop     r14
0x18002f4ab  pop     r13
0x18002f4ad  pop     r12
0x18002f4af  pop     rdi
0x18002f4b0  pop     rsi
0x18002f4b1  pop     rbx
0x18002f4b2  pop     rbp
0x18002f4b3  retn
```

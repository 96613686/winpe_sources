# MsProviderStart

- ea: `0x18002c3d4`
- end: `0x18002c738`
- name: `MsProviderStart`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c090`

## callees

- `0x18000ad0c`
- `0x18000ecb0`
- `0x18002bf08`
- `0x18002c034`
- `0x18002c3d4`
- `0x18002ca20`
- `0x18002d1b4`
- `0x18002de30`
- `0x18004e798`
- `0x18004e884`
- `0x18004eb84`
- `0x1800631b4`
- `0x180063468`
- `0x180063944`
- `0x18007f790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c620`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c478`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c478`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002c554`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002c554`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c59a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c5fa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c59a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c5fa`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002c49c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002c49c`

## string_xrefs

- `0x18002c471`: `vertdll.dll`
- `0x18002c495`: `iumbase.dll`
- `0x18002c4cb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\dllmainhlpr.c`

## pseudocode

```c
__int64 __fastcall MsProviderStart(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // eax
  char v5; // r14
  __int64 TrustedEnvironment; // rcx
  __int64 v7; // rcx
  HMODULE LibraryW; // rax
  __int64 v9; // r9
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  char v16; // al
  unsigned __int64 v17; // rsi
  __int64 v18; // rbx
  DWORD LastError; // eax
  __int64 v20; // r8
  __int64 v21; // rbx
  DWORD v22; // eax
  __int64 v23; // r8
  unsigned __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  char v28; // al
  __int64 v29; // rbx
  DWORD v30; // eax
  __int64 v31; // r8
  __int64 DriverSelftestCycleCount; // rax
  int v33; // r9d
  int v35; // [rsp+20h] [rbp-79h]
  LARGE_INTEGER Frequency; // [rsp+30h] [rbp-69h] BYREF
  LARGE_INTEGER v37; // [rsp+38h] [rbp-61h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-59h] BYREF
  __int64 v39; // [rsp+48h] [rbp-51h] BYREF
  int v40[2]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v41; // [rsp+58h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+60h] [rbp-39h] BYREF
  __int64 *v43; // [rsp+80h] [rbp-19h]
  __int64 v44; // [rsp+88h] [rbp-11h]
  int *v45; // [rsp+90h] [rbp-9h]
  __int64 v46; // [rsp+98h] [rbp-1h]
  __int64 *v47; // [rsp+A0h] [rbp+7h]
  __int64 v48; // [rsp+A8h] [rbp+Fh]

  v4 = g_TrustedEnvironment;
  v5 = 0;
  PerformanceCount.QuadPart = 0;
  v37.QuadPart = 0;
  Frequency.QuadPart = 1;
  if ( g_TrustedEnvironment )
  {
    TrustedEnvironment = (unsigned int)g_TrustedEnvironment;
  }
  else
  {
    TrustedEnvironment = (unsigned int)GetTrustedEnvironment(a1, a2, a3, a4);
    v4 = g_TrustedEnvironment;
  }
  if ( (TrustedEnvironment & 0x18) == 0 )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    v4 = g_TrustedEnvironment;
  }
  if ( v4 )
  {
    v7 = v4;
  }
  else
  {
    v7 = (unsigned int)GetTrustedEnvironment(TrustedEnvironment, a2, a3, a4);
    v4 = g_TrustedEnvironment;
  }
  if ( (v7 & 0x16) == 0 )
    goto LABEL_22;
  if ( !v4 )
    LOBYTE(v4) = GetTrustedEnvironment(v7, a2, a3, a4);
  if ( (v4 & 0x10) != 0 )
  {
    if ( GetModuleHandleExW(0, L"vertdll.dll", &g_hIumBase) )
    {
      LibraryW = g_hIumBase;
      goto LABEL_18;
    }
    LibraryW = 0;
  }
  else
  {
    LibraryW = LoadLibraryW(L"iumbase.dll");
  }
  g_hIumBase = LibraryW;
LABEL_18:
  if ( !LibraryW )
  {
    v9 = 130;
    goto LABEL_20;
  }
LABEL_22:
  g_fSteEnabled = 1;
  g_fSelftest = 1;
  g_fSelftestsRunning = 1;
  SymCryptRngAesInstantiateSelftest();
  SymCryptRngAesReseedSelftest();
  SymCryptRngAesGenerateSelftest();
  g_fSelftestsRunning = 0;
  if ( (unsigned int)InitUmRootRngState() )
  {
    v5 = 1;
    v10 = 0;
    if ( IsInLSAProcess() )
    {
      v16 = g_TrustedEnvironment;
      v17 = 0;
      if ( !g_TrustedEnvironment )
        v16 = GetTrustedEnvironment(v13, v12, v14, v15);
      if ( (v16 & 0x18) == 0 )
      {
        if ( !QueryPerformanceFrequency(&Frequency)
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          LastError = GetLastError();
          WPP_SF_D(v18, 10, v20, LastError);
        }
        if ( !QueryPerformanceCounter(&PerformanceCount)
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v22 = GetLastError();
          WPP_SF_D(v21, 11, v23, v22);
        }
      }
      v10 = AlgorithmCheck();
      v28 = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
        v28 = GetTrustedEnvironment(v25, v24, v26, v27);
      if ( (v28 & 0x18) == 0 )
      {
        if ( !QueryPerformanceCounter(&v37)
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v29 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v30 = GetLastError();
          WPP_SF_D(v29, 12, v31, v30);
        }
        v24 = (unsigned __int64)(1000000 * (v37.QuadPart - PerformanceCount.QuadPart)) % Frequency.QuadPart;
        v17 = (unsigned __int64)(1000000 * (v37.QuadPart - PerformanceCount.QuadPart)) / Frequency.QuadPart;
      }
      if ( v10 < 0 )
      {
        v9 = 205;
        v11 = (unsigned int)v10;
        goto LABEL_21;
      }
      if ( g_fSteEnabled )
      {
        DriverSelftestCycleCount = GetDriverSelftestCycleCount(v25, v24);
        if ( (unsigned int)dword_1800A4438 > 5
          && (qword_1800A4448 & 0x800000000000LL) != 0
          && (qword_1800A4450 & 0x800000000000LL) == qword_1800A4450 )
        {
          v41 = DriverSelftestCycleCount;
          v43 = &v39;
          v47 = &v41;
          v39 = 50331648;
          v44 = 8;
          *(_QWORD *)v40 = v17;
          v45 = v40;
          v46 = 8;
          v48 = 8;
          tlgWriteTransfer_EventWriteTransfer((int)v40, (int)&byte_18009B8D1, 0, v33, v35, &v42);
        }
      }
    }
    g_fProviderStarted = 1;
    goto LABEL_52;
  }
  v9 = 161;
LABEL_20:
  v10 = -1073741595;
  v11 = 3221225701LL;
LABEL_21:
  DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\dllmainhlpr.c", v9);
LABEL_52:
  if ( !g_fProviderStarted && v5 )
    TearDownRNGStates();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002c3d4  push    rbp
0x18002c3d6  push    rbx
0x18002c3d7  push    rsi
0x18002c3d8  push    rdi
0x18002c3d9  push    r13
0x18002c3db  push    r14
0x18002c3dd  lea     rbp, [rsp-2Fh]
0x18002c3e2  sub     rsp, 0C8h
0x18002c3e9  mov     rax, cs:__security_cookie
0x18002c3f0  xor     rax, rsp
0x18002c3f3  mov     [rbp+57h+var_40], rax
0x18002c3f7  mov     eax, cs:g_TrustedEnvironment
0x18002c3fd  xor     r14b, r14b
0x18002c400  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x18002c408  mov     qword ptr [rbp+57h+var_B8], 0
0x18002c410  mov     qword ptr [rbp+57h+Frequency], 1
0x18002c418  test    eax, eax
0x18002c41a  jnz     short loc_18002C42B
0x18002c41c  call    GetTrustedEnvironment
0x18002c421  mov     ecx, eax
0x18002c423  mov     eax, cs:g_TrustedEnvironment
0x18002c429  jmp     short loc_18002C42D
0x18002c42b  mov     ecx, eax
0x18002c42d  test    cl, 18h
0x18002c430  jnz     short loc_18002C43D
0x18002c432  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002c437  mov     eax, cs:g_TrustedEnvironment
0x18002c43d  test    eax, eax
0x18002c43f  jnz     short loc_18002C450
0x18002c441  call    GetTrustedEnvironment
0x18002c446  mov     ecx, eax
0x18002c448  mov     eax, cs:g_TrustedEnvironment
0x18002c44e  jmp     short loc_18002C452
0x18002c450  mov     ecx, eax
0x18002c452  test    cl, 16h
0x18002c455  jz      loc_18002C4DC
0x18002c45b  test    eax, eax
0x18002c45d  jnz     short loc_18002C464
0x18002c45f  call    GetTrustedEnvironment
0x18002c464  test    al, 10h
0x18002c466  jz      short loc_18002C495
0x18002c468  lea     r8, g_hIumBase; phModule
0x18002c46f  xor     ecx, ecx; dwFlags
0x18002c471  lea     rdx, ModuleName; "vertdll.dll"
0x18002c478  call    cs:__imp_GetModuleHandleExW
0x18002c47f  nop     dword ptr [rax+rax+00h]
0x18002c484  test    eax, eax
0x18002c486  jnz     short loc_18002C48C
0x18002c488  xor     eax, eax
0x18002c48a  jmp     short loc_18002C4A8
0x18002c48c  mov     rax, cs:g_hIumBase
0x18002c493  jmp     short loc_18002C4AF
0x18002c495  lea     rcx, LibFileName; "iumbase.dll"
0x18002c49c  call    cs:__imp_LoadLibraryW
0x18002c4a3  nop     dword ptr [rax+rax+00h]
0x18002c4a8  mov     cs:g_hIumBase, rax
0x18002c4af  test    rax, rax
0x18002c4b2  jnz     short loc_18002C4DC
0x18002c4b4  mov     r9d, 82h
0x18002c4ba  mov     edi, 0C00000E5h
0x18002c4bf  mov     ecx, 0C00000E5h
0x18002c4c4  lea     rdx, aStatus_0; "status"
0x18002c4cb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002c4d2  call    DebugTraceError
0x18002c4d7  jmp     loc_18002C706
0x18002c4dc  mov     cs:g_fSteEnabled, 1
0x18002c4e3  mov     cs:g_fSelftest, 1
0x18002c4ea  mov     cs:g_fSelftestsRunning, 1
0x18002c4f4  call    SymCryptRngAesInstantiateSelftest
0x18002c4f9  call    SymCryptRngAesReseedSelftest
0x18002c4fe  call    SymCryptRngAesGenerateSelftest
0x18002c503  mov     cs:g_fSelftestsRunning, 0
0x18002c50d  call    InitUmRootRngState
0x18002c512  test    eax, eax
0x18002c514  jnz     short loc_18002C51E
0x18002c516  mov     r9d, 0A1h
0x18002c51c  jmp     short loc_18002C4BA
0x18002c51e  mov     r14b, 1
0x18002c521  call    IsInLSAProcess
0x18002c526  xor     edi, edi
0x18002c528  test    eax, eax
0x18002c52a  jz      loc_18002C6FF
0x18002c530  mov     eax, cs:g_TrustedEnvironment
0x18002c536  xor     esi, esi
0x18002c538  test    eax, eax
0x18002c53a  jnz     short loc_18002C541
0x18002c53c  call    GetTrustedEnvironment
0x18002c541  lea     r13, WPP_GLOBAL_Control
0x18002c548  test    al, 18h
0x18002c54a  jnz     loc_18002C5DC
0x18002c550  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x18002c554  call    cs:__imp_QueryPerformanceFrequency
0x18002c55b  nop     dword ptr [rax+rax+00h]
0x18002c560  test    eax, eax
0x18002c562  jnz     short loc_18002C596
0x18002c564  mov     rbx, cs:WPP_GLOBAL_Control
0x18002c56b  cmp     rbx, r13
0x18002c56e  jz      short loc_18002C596
0x18002c570  test    [rbx+1Ch], r14b
0x18002c574  jz      short loc_18002C596
0x18002c576  mov     rbx, [rbx+10h]
0x18002c57a  call    cs:__imp_GetLastError
0x18002c581  nop     dword ptr [rax+rax+00h]
0x18002c586  mov     edx, 0Ah
0x18002c58b  mov     rcx, rbx
0x18002c58e  mov     r9d, eax
0x18002c591  call    WPP_SF_D
0x18002c596  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18002c59a  call    cs:__imp_QueryPerformanceCounter
0x18002c5a1  nop     dword ptr [rax+rax+00h]
0x18002c5a6  test    eax, eax
0x18002c5a8  jnz     short loc_18002C5DC
0x18002c5aa  mov     rbx, cs:WPP_GLOBAL_Control
0x18002c5b1  cmp     rbx, r13
0x18002c5b4  jz      short loc_18002C5DC
0x18002c5b6  test    [rbx+1Ch], r14b
0x18002c5ba  jz      short loc_18002C5DC
0x18002c5bc  mov     rbx, [rbx+10h]
0x18002c5c0  call    cs:__imp_GetLastError
0x18002c5c7  nop     dword ptr [rax+rax+00h]
0x18002c5cc  mov     edx, 0Bh
0x18002c5d1  mov     rcx, rbx
0x18002c5d4  mov     r9d, eax
0x18002c5d7  call    WPP_SF_D
0x18002c5dc  call    AlgorithmCheck
0x18002c5e1  mov     edi, eax
0x18002c5e3  mov     eax, cs:g_TrustedEnvironment
0x18002c5e9  test    eax, eax
0x18002c5eb  jnz     short loc_18002C5F2
0x18002c5ed  call    GetTrustedEnvironment
0x18002c5f2  test    al, 18h
0x18002c5f4  jnz     short loc_18002C654
0x18002c5f6  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x18002c5fa  call    cs:__imp_QueryPerformanceCounter
0x18002c601  nop     dword ptr [rax+rax+00h]
0x18002c606  test    eax, eax
0x18002c608  jnz     short loc_18002C63C
0x18002c60a  mov     rbx, cs:WPP_GLOBAL_Control
0x18002c611  cmp     rbx, r13
0x18002c614  jz      short loc_18002C63C
0x18002c616  test    [rbx+1Ch], r14b
0x18002c61a  jz      short loc_18002C63C
0x18002c61c  mov     rbx, [rbx+10h]
0x18002c620  call    cs:__imp_GetLastError
0x18002c627  nop     dword ptr [rax+rax+00h]
0x18002c62c  mov     edx, 0Ch
0x18002c631  mov     rcx, rbx
0x18002c634  mov     r9d, eax
0x18002c637  call    WPP_SF_D
0x18002c63c  mov     rax, qword ptr [rbp+57h+var_B8]
0x18002c640  xor     edx, edx
0x18002c642  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x18002c646  imul    rax, 0F4240h
0x18002c64d  div     qword ptr [rbp+57h+Frequency]
0x18002c651  mov     rsi, rax
0x18002c654  test    edi, edi
0x18002c656  jns     short loc_18002C665
0x18002c658  mov     r9d, 0CDh
0x18002c65e  mov     ecx, edi
0x18002c660  jmp     loc_18002C4C4
0x18002c665  cmp     cs:g_fSteEnabled, 0
0x18002c66c  jz      loc_18002C6FF
0x18002c672  call    GetDriverSelftestCycleCount
0x18002c677  mov     ecx, cs:dword_1800A4438
0x18002c67d  cmp     ecx, 5
0x18002c680  jbe     short loc_18002C6FF
0x18002c682  mov     rdx, cs:qword_1800A4450
0x18002c689  mov     r8, 800000000000h; int
0x18002c693  mov     rcx, cs:qword_1800A4448
0x18002c69a  test    r8, rcx
0x18002c69d  jz      short loc_18002C6FF
0x18002c69f  mov     rcx, rdx
0x18002c6a2  and     rcx, r8
0x18002c6a5  cmp     rcx, rdx
0x18002c6a8  jnz     short loc_18002C6FF
0x18002c6aa  mov     [rbp+57h+var_98], rax
0x18002c6ae  lea     rcx, [rbp+57h+var_A8]
0x18002c6b2  lea     rax, [rbp+57h+var_98]
0x18002c6b6  mov     [rbp+57h+var_70], rcx
0x18002c6ba  mov     [rbp+57h+var_50], rax
0x18002c6be  lea     rcx, [rbp+57h+var_A0]; int
0x18002c6c2  lea     rax, [rbp+57h+var_90]
0x18002c6c6  mov     [rbp+57h+var_A8], 3000000h
0x18002c6ce  lea     rdx, byte_18009B8D1; int
0x18002c6d5  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x18002c6da  mov     [rbp+57h+var_68], 8
0x18002c6e2  mov     qword ptr [rbp+57h+var_A0], rsi
0x18002c6e6  mov     [rbp+57h+var_60], rcx
0x18002c6ea  mov     [rbp+57h+var_58], 8
0x18002c6f2  mov     [rbp+57h+var_48], 8
0x18002c6fa  call    _tlgWriteTransfer_EventWriteTransfer
0x18002c6ff  mov     cs:g_fProviderStarted, r14b
0x18002c706  cmp     cs:g_fProviderStarted, 0
0x18002c70d  jnz     short loc_18002C719
0x18002c70f  test    r14b, r14b
0x18002c712  jz      short loc_18002C719
0x18002c714  call    TearDownRNGStates
0x18002c719  mov     eax, edi
0x18002c71b  mov     rcx, [rbp+57h+var_40]
0x18002c71f  xor     rcx, rsp; StackCookie
0x18002c722  call    __security_check_cookie
0x18002c727  add     rsp, 0C8h
0x18002c72e  pop     r14
0x18002c730  pop     r13
0x18002c732  pop     rdi
0x18002c733  pop     rsi
0x18002c734  pop     rbx
0x18002c735  pop     rbp
0x18002c736  retn
```

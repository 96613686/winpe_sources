# TelemetryProvider::RunCommand(char const *,void *,void *)

- ea: `0x1800c0418`
- end: `0x1800c0736`
- name: `?RunCommand@TelemetryProvider@@AEAAJPEBDPEAX1@Z`
- size: `798`
- prototype: `__int64 __fastcall(TelemetryProvider *__hidden this, const char *, void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022e5c`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x18000f698`
- `0x18000f7bc`
- `0x1800152d0`
- `0x1800c0418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c04b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c04b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c0545`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c0545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c04df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c06b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c04df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c06b5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800c067b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800c067b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800c0606`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800c0606`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800c06dc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800c06dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800c04d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800c04d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c06f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0704`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c06f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0704`

## string_xrefs

- `0x1800c04e5`: `GetSystemDirectoryW failed [%d]`
- `0x1800c0505`: `\compattelrunner.exe`
- `0x1800c04f2`: `TelemetryProvider::RunCommand`
- `0x1800c052f`: `TelemetryProvider::RunCommand`
- `0x1800c05bc`: `TelemetryProvider::RunCommand`
- `0x1800c0623`: `TelemetryProvider::RunCommand`
- `0x1800c069f`: `TelemetryProvider::RunCommand`
- `0x1800c0616`: `CreateProcessW failed [%d]`

## pseudocode

```c
__int64 __fastcall TelemetryProvider::RunCommand(TelemetryProvider *this, const char *a2, void *a3, void *a4)
{
  signed int v8; // ebx
  unsigned __int64 v9; // rdx
  DWORD LastError; // eax
  int v11; // eax
  const wchar_t *v12; // rcx
  int v13; // eax
  DWORD v14; // eax
  const char *v15; // r9
  __int64 v16; // r8
  signed int v17; // eax
  DWORD v18; // eax
  BOOL ExitCodeProcess; // eax
  BOOL bInheritHandles[2]; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR CommandLine[264]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  ExitCode = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(CommandLine, 0, 0x208u);
  StartupInfo.cb = 104;
  *(_OWORD *)Handles = 0;
  if ( TelemetryProvider::CompattelrunnerPath )
    goto LABEL_8;
  v8 = -2147467259;
  AcquireSRWLockExclusive(&TelemetryProvider::TelemetryProviderLock);
  if ( !TelemetryProvider::CompattelrunnerPath )
  {
    if ( !GetSystemDirectoryW(&TelemetryProvider::CompattelrunnerPath, 0x104u) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "TelemetryProvider::RunCommand", 512, "GetSystemDirectoryW failed [%d]", LastError);
    }
    v11 = StringCchCatW(&TelemetryProvider::CompattelrunnerPath, v9, L"\\compattelrunner.exe");
    v8 = v11;
    if ( v11 < 0 )
      AslLogCallPrintf(1, "TelemetryProvider::RunCommand", 517, "StringCchCatW failed [%#x]", v11);
  }
  ReleaseSRWLockExclusive(&TelemetryProvider::TelemetryProviderLock);
  if ( v8 >= 0 )
  {
LABEL_8:
    v12 = L" -fullsync";
    if ( !*((_BYTE *)this + 49) )
      v12 = (const wchar_t *)&cchOriginalDestLength;
    v13 = StringCchPrintfW(
            CommandLine,
            0x104u,
            L"%ls -cv:%hs -wce:%p %ls -m:%ls -f:%ls ",
            &TelemetryProvider::CompattelrunnerPath,
            a2,
            a4,
            v12,
            *((_QWORD *)this + 1),
            *(_QWORD *)this);
    v8 = v13;
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "TelemetryProvider::RunCommand", 544, "StringCchPrintfW failed [%#x]", v13);
      goto LABEL_23;
    }
    if ( CreateProcessW(0, CommandLine, 0, 0, 1, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      Handles[1] = a3;
      Handles[0] = ProcessInformation.hProcess;
      v18 = WaitForMultipleObjects((a3 != 0) + 1, Handles, 0, 0xFFFFFFFF);
      if ( !v18 )
      {
        ExitCodeProcess = GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
        v8 = ExitCodeProcess ? ExitCode : 0;
        goto LABEL_23;
      }
      if ( v18 == 1 )
      {
        v8 = 0;
        goto LABEL_23;
      }
      if ( v18 != -1 )
      {
        AslLogCallPrintf(1, "TelemetryProvider::RunCommand", 616, "WaitForMultipleObjects failed [%d]", v18);
        v8 = -2147467259;
        goto LABEL_23;
      }
      v14 = GetLastError();
      v15 = "WaitForMultipleObjects failed [%d]";
      v16 = 594;
    }
    else
    {
      v14 = GetLastError();
      v15 = "CreateProcessW failed [%d]";
      v16 = 559;
    }
    bInheritHandles[0] = v14;
    AslLogCallPrintf(1, "TelemetryProvider::RunCommand", v16, v15, *(_QWORD *)bInheritHandles);
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
  }
LABEL_23:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c0418  mov     [rsp-8+arg_10], rbx
0x1800c041d  push    rbp
0x1800c041e  push    rsi
0x1800c041f  push    rdi
0x1800c0420  push    r12
0x1800c0422  push    r13
0x1800c0424  push    r14
0x1800c0426  push    r15
0x1800c0428  lea     rbp, [rsp-210h]
0x1800c0430  sub     rsp, 310h
0x1800c0437  mov     rax, cs:__security_cookie
0x1800c043e  xor     rax, rsp
0x1800c0441  mov     [rbp+240h+var_40], rax
0x1800c0448  mov     r14, rdx
0x1800c044b  mov     rdi, r8
0x1800c044e  xor     edx, edx; Val
0x1800c0450  mov     rsi, rcx
0x1800c0453  lea     rcx, [rbp+240h+StartupInfo+4]; void *
0x1800c0457  mov     r15, r9
0x1800c045a  lea     r8d, [rdx+64h]; Size
0x1800c045e  call    memset_0
0x1800c0463  xorps   xmm0, xmm0
0x1800c0466  lea     rcx, [rbp+240h+CommandLine]; void *
0x1800c046a  xor     eax, eax
0x1800c046c  xor     r12d, r12d
0x1800c046f  xor     edx, edx; Val
0x1800c0471  mov     qword ptr [rsp+340h+ProcessInformation.dwProcessId], rax
0x1800c0476  mov     r8d, 208h; Size
0x1800c047c  mov     [rsp+340h+ExitCode], r12d
0x1800c0481  movups  xmmword ptr [rsp+340h+ProcessInformation.hProcess], xmm0
0x1800c0486  call    memset_0
0x1800c048b  cmp     cs:?CompattelrunnerPath@TelemetryProvider@@0PAGA, r12w; ushort near * TelemetryProvider::CompattelrunnerPath
0x1800c0493  lea     r13d, [r12+1]
0x1800c0498  xorps   xmm0, xmm0
0x1800c049b  mov     [rbp+240h+StartupInfo.cb], 68h ; 'h'
0x1800c04a2  movups  xmmword ptr [rsp+340h+Handles], xmm0
0x1800c04a7  jnz     loc_1800C0553
0x1800c04ad  lea     rcx, ?TelemetryProviderLock@TelemetryProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800c04b4  mov     ebx, 80004005h
0x1800c04b9  call    cs:__imp_AcquireSRWLockExclusive
0x1800c04bf  cmp     cs:?CompattelrunnerPath@TelemetryProvider@@0PAGA, r12w; ushort near * TelemetryProvider::CompattelrunnerPath
0x1800c04c7  jnz     short loc_1800C053E
0x1800c04c9  mov     edx, 104h; uSize
0x1800c04ce  lea     rcx, ?CompattelrunnerPath@TelemetryProvider@@0PAGA; lpBuffer
0x1800c04d5  call    cs:__imp_GetSystemDirectoryW
0x1800c04db  test    eax, eax
0x1800c04dd  jnz     short loc_1800C0505
0x1800c04df  call    cs:__imp_GetLastError
0x1800c04e5  lea     r9, aGetsystemdirec; "GetSystemDirectoryW failed [%d]"
0x1800c04ec  mov     r8d, 200h
0x1800c04f2  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::RunCommand"
0x1800c04f9  mov     [rsp+340h+bInheritHandles], eax
0x1800c04fd  mov     ecx, r13d
0x1800c0500  call    AslLogCallPrintf
0x1800c0505  lea     r8, aCompattelrunne; "\\compattelrunner.exe"
0x1800c050c  lea     rcx, ?CompattelrunnerPath@TelemetryProvider@@0PAGA; unsigned __int16 *
0x1800c0513  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c0518  mov     ebx, eax
0x1800c051a  test    eax, eax
0x1800c051c  jns     short loc_1800C053E
0x1800c051e  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800c0525  mov     [rsp+340h+bInheritHandles], eax
0x1800c0529  mov     r8d, 205h
0x1800c052f  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::RunCommand"
0x1800c0536  mov     ecx, r13d
0x1800c0539  call    AslLogCallPrintf
0x1800c053e  lea     rcx, ?TelemetryProviderLock@TelemetryProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800c0545  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c054b  test    ebx, ebx
0x1800c054d  js      loc_1800C06EA
0x1800c0553  cmp     [rsi+31h], r12b
0x1800c0557  lea     rax, cchOriginalDestLength
0x1800c055e  lea     rcx, aFullsync; " -fullsync"
0x1800c0565  mov     edx, 104h; unsigned __int64
0x1800c056a  cmovz   rcx, rax
0x1800c056e  lea     r9, ?CompattelrunnerPath@TelemetryProvider@@0PAGA; ushort near * TelemetryProvider::CompattelrunnerPath
0x1800c0575  mov     rax, [rsi]
0x1800c0578  lea     r8, aLsCvHsWcePLsML; "%ls -cv:%hs -wce:%p %ls -m:%ls -f:%ls "
0x1800c057f  mov     [rsp+340h+lpStartupInfo], rax
0x1800c0584  mov     rax, [rsi+8]
0x1800c0588  mov     [rsp+340h+lpCurrentDirectory], rax
0x1800c058d  mov     [rsp+340h+lpEnvironment], rcx
0x1800c0592  lea     rcx, [rbp+240h+CommandLine]; unsigned __int16 *
0x1800c0596  mov     qword ptr [rsp+340h+dwCreationFlags], r15
0x1800c059b  mov     qword ptr [rsp+340h+bInheritHandles], r14
0x1800c05a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c05a5  mov     ebx, eax
0x1800c05a7  test    eax, eax
0x1800c05a9  jns     short loc_1800C05D0
0x1800c05ab  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x1800c05b2  mov     [rsp+340h+bInheritHandles], eax
0x1800c05b6  mov     r8d, 220h
0x1800c05bc  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::RunCommand"
0x1800c05c3  mov     ecx, r13d
0x1800c05c6  call    AslLogCallPrintf
0x1800c05cb  jmp     loc_1800C06EA
0x1800c05d0  lea     rax, [rsp+340h+ProcessInformation]
0x1800c05d5  xor     r9d, r9d; lpThreadAttributes
0x1800c05d8  mov     [rsp+340h+lpProcessInformation], rax; lpProcessInformation
0x1800c05dd  lea     rdx, [rbp+240h+CommandLine]; lpCommandLine
0x1800c05e1  lea     rax, [rbp+240h+StartupInfo]
0x1800c05e5  xor     r8d, r8d; lpProcessAttributes
0x1800c05e8  mov     [rsp+340h+lpStartupInfo], rax; lpStartupInfo
0x1800c05ed  xor     ecx, ecx; lpApplicationName
0x1800c05ef  mov     [rsp+340h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800c05f4  mov     [rsp+340h+lpEnvironment], r12; lpEnvironment
0x1800c05f9  mov     [rsp+340h+dwCreationFlags], 8; dwCreationFlags
0x1800c0601  mov     [rsp+340h+bInheritHandles], r13d; bInheritHandles
0x1800c0606  call    cs:__imp_CreateProcessW
0x1800c060c  test    eax, eax
0x1800c060e  jnz     short loc_1800C0654
0x1800c0610  call    cs:__imp_GetLastError
0x1800c0616  lea     r9, aCreateprocessw; "CreateProcessW failed [%d]"
0x1800c061d  mov     r8d, 22Fh
0x1800c0623  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::RunCommand"
0x1800c062a  mov     [rsp+340h+bInheritHandles], eax
0x1800c062e  mov     ecx, r13d
0x1800c0631  call    AslLogCallPrintf
0x1800c0636  call    cs:__imp_GetLastError
0x1800c063c  mov     ebx, eax
0x1800c063e  test    eax, eax
0x1800c0640  jle     loc_1800C06EA
0x1800c0646  movzx   ebx, ax
0x1800c0649  or      ebx, 80070000h
0x1800c064f  jmp     loc_1800C06EA
0x1800c0654  mov     rax, [rsp+340h+ProcessInformation.hProcess]
0x1800c0659  lea     rdx, [rsp+340h+Handles]; lpHandles
0x1800c065e  mov     [rsp+340h+Handles+8], rdi
0x1800c0663  neg     rdi
0x1800c0666  mov     [rsp+340h+Handles], rax
0x1800c066b  sbb     ecx, ecx
0x1800c066d  or      ebx, 0FFFFFFFFh
0x1800c0670  neg     ecx
0x1800c0672  mov     r9d, ebx; dwMilliseconds
0x1800c0675  add     ecx, r13d; nCount
0x1800c0678  xor     r8d, r8d; bWaitAll
0x1800c067b  call    cs:__imp_WaitForMultipleObjects
0x1800c0681  test    eax, eax
0x1800c0683  jz      short loc_1800C06D2
0x1800c0685  cmp     eax, r13d
0x1800c0688  jz      short loc_1800C06CD
0x1800c068a  cmp     eax, ebx
0x1800c068c  jz      short loc_1800C06B5
0x1800c068e  lea     r9, aWaitformultipl_1; "WaitForMultipleObjects failed [%d]"
0x1800c0695  mov     [rsp+340h+bInheritHandles], eax
0x1800c0699  mov     r8d, 268h
0x1800c069f  lea     rdx, aTelemetryprovi_0; "TelemetryProvider::RunCommand"
0x1800c06a6  mov     ecx, r13d
0x1800c06a9  call    AslLogCallPrintf
0x1800c06ae  mov     ebx, 80004005h
0x1800c06b3  jmp     short loc_1800C06EA
0x1800c06b5  call    cs:__imp_GetLastError
0x1800c06bb  lea     r9, aWaitformultipl_1; "WaitForMultipleObjects failed [%d]"
0x1800c06c2  mov     r8d, 252h
0x1800c06c8  jmp     loc_1800C0623
0x1800c06cd  mov     ebx, r12d
0x1800c06d0  jmp     short loc_1800C06EA
0x1800c06d2  mov     rcx, [rsp+340h+ProcessInformation.hProcess]; hProcess
0x1800c06d7  lea     rdx, [rsp+340h+ExitCode]; lpExitCode
0x1800c06dc  call    cs:__imp_GetExitCodeProcess
0x1800c06e2  neg     eax
0x1800c06e4  sbb     ebx, ebx
0x1800c06e6  and     ebx, [rsp+340h+ExitCode]
0x1800c06ea  mov     rcx, [rsp+340h+ProcessInformation.hProcess]; hObject
0x1800c06ef  test    rcx, rcx
0x1800c06f2  jz      short loc_1800C06FA
0x1800c06f4  call    cs:__imp_CloseHandle
0x1800c06fa  mov     rcx, [rsp+340h+ProcessInformation.hThread]; hObject
0x1800c06ff  test    rcx, rcx
0x1800c0702  jz      short loc_1800C070A
0x1800c0704  call    cs:__imp_CloseHandle
0x1800c070a  mov     eax, ebx
0x1800c070c  mov     rcx, [rbp+240h+var_40]
0x1800c0713  xor     rcx, rsp; StackCookie
0x1800c0716  call    __security_check_cookie
0x1800c071b  mov     rbx, [rsp+340h+arg_10]
0x1800c0723  add     rsp, 310h
0x1800c072a  pop     r15
0x1800c072c  pop     r14
0x1800c072e  pop     r13
0x1800c0730  pop     r12
0x1800c0732  pop     rdi
0x1800c0733  pop     rsi
0x1800c0734  pop     rbp
0x1800c0735  retn
```

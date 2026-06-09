# CAxInstaller::WinVerifyFile(ushort const *,ushort const *)

- ea: `0x180006ea0`
- end: `0x1800071dc`
- name: `?WinVerifyFile@CAxInstaller@@QEAAJPEBG0@Z`
- size: `828`
- prototype: `__int64 __fastcall(CAxInstaller *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005ee0`

## callees

- `0x1800021b8`
- `0x180005934`
- `0x180005b78`
- `0x180006ea0`
- `0x18000725c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007102`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007066`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007066`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007166`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014874`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007166`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014874`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006fcc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180006fcc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007139`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800148ca`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000714c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000714c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000712b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000712b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800070f8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800070f8`
- `USERENV!DestroyEnvironmentBlock` at `0x180007184`
- `USERENV!DestroyEnvironmentBlock` at `0x180014897`
- `USERENV!DestroyEnvironmentBlock` at `0x180007184`
- `USERENV!DestroyEnvironmentBlock` at `0x180014897`
- `USERENV!CreateEnvironmentBlock` at `0x180007039`
- `USERENV!CreateEnvironmentBlock` at `0x180007039`

## string_xrefs

- `0x180007085`: `Failed to Impersonate %x`
- `0x180006feb`: `Failed to duplicate Token. Error %x`
- `0x180007023`: `Failed to Set Token Integrity Level. Error %x`
- `0x180007058`: `Failed to Create Environment Block. Error %x`
- `0x180007117`: `Failed to CreateProcess %x`

## pseudocode

```c
__int64 __fastcall CAxInstaller::WinVerifyFile(
        CAxInstaller *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // r12d
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rdi
  signed int v13; // ebx
  unsigned int v14; // edx
  signed int LastError; // eax
  unsigned __int16 *v16; // r9
  int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  TOKEN_TYPE TokenType[2]; // [rsp+20h] [rbp-118h]
  HANDLE hToken; // [rsp+60h] [rbp-D8h] BYREF
  int v24; // [rsp+68h] [rbp-D0h]
  LPVOID Environment; // [rsp+70h] [rbp-C8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-C0h] BYREF
  unsigned __int16 *v27; // [rsp+90h] [rbp-A8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-98h] BYREF
  DWORD ExitCode; // [rsp+158h] [rbp+20h] BYREF

  hToken = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Environment = 0;
  v6 = 0;
  v24 = 0;
  v27 = 0;
  ExitCode = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  do
    ++v7;
  while ( word_180021670[v7] );
  v10 = (unsigned int)(v9 + 24 + v7 + v8);
  v11 = (unsigned int)v10;
  v12 = (unsigned __int16 *)LocalAlloc(0, 2 * v10);
  v27 = v12;
  if ( !v12 )
  {
    v13 = -2147024882;
    goto LABEL_31;
  }
  v13 = StringCchPrintfW(v12, v11, L"\"%s\" %Iu \"%s\" \"%s\"", word_180021670, *((_QWORD *)this + 86), a2, a3);
  if ( v13 >= 0 )
  {
    if ( !DuplicateTokenEx(*((HANDLE *)this + 85), 0, 0, SecurityImpersonation, TokenPrimary, &hToken) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      v16 = L"Failed to duplicate Token. Error %x";
LABEL_13:
      TokenType[0] = v13;
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, v16, *(_QWORD *)TokenType);
      goto LABEL_31;
    }
    v17 = Utils::SetTokenIntegrityLevel(hToken, v14);
    v13 = v17;
    if ( v17 < 0 )
    {
      TokenType[0] = v17;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        8u,
        2u,
        L"Failed to Set Token Integrity Level. Error %x",
        *(_QWORD *)TokenType);
      goto LABEL_31;
    }
    if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
    {
      v18 = GetLastError();
      v13 = v18;
      if ( v18 > 0 )
        v13 = (unsigned __int16)v18 | 0x80070000;
      v16 = L"Failed to Create Environment Block. Error %x";
      goto LABEL_13;
    }
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      v19 = GetLastError();
      v13 = v19;
      if ( v19 > 0 )
        v13 = (unsigned __int16)v19 | 0x80070000;
      v16 = L"Failed to Impersonate %x";
      goto LABEL_13;
    }
    v6 = 1;
    v24 = 1;
    StartupInfo.cb = 104;
    StartupInfo.lpDesktop = (LPWSTR)*((_QWORD *)this + 82);
    if ( !CreateProcessAsUserW(hToken, 0, v12, 0, 0, 0, 0x404u, Environment, 0, &StartupInfo, &ProcessInformation) )
    {
      v20 = GetLastError();
      v13 = v20;
      if ( v20 > 0 )
        v13 = (unsigned __int16)v20 | 0x80070000;
      v16 = L"Failed to CreateProcess %x";
      goto LABEL_13;
    }
    ResumeThread(ProcessInformation.hThread);
    WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    v13 = -2146762748;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      v13 = ExitCode;
  }
LABEL_31:
  if ( v6 )
    RevertToSelf();
  if ( v12 )
    LocalFree(v12);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( hToken )
    CloseHandle(hToken);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180006ea0  mov     [rsp+arg_0], rbx
0x180006ea5  mov     [rsp+arg_8], rsi
0x180006eaa  push    rdi
0x180006eab  push    r12
0x180006ead  push    r13
0x180006eaf  push    r14
0x180006eb1  push    r15
0x180006eb3  sub     rsp, 110h
0x180006eba  mov     rsi, r8
0x180006ebd  mov     r14, rdx
0x180006ec0  mov     r15, rcx
0x180006ec3  xor     r13d, r13d
0x180006ec6  mov     [rsp+138h+hToken], r13
0x180006ecb  xor     edx, edx; Val
0x180006ecd  lea     r8d, [r13+68h]; Size
0x180006ed1  lea     rcx, [rsp+138h+StartupInfo]; void *
0x180006ed9  call    memset_0
0x180006ede  xorps   xmm0, xmm0
0x180006ee1  xor     eax, eax
0x180006ee3  movups  xmmword ptr [rsp+138h+ProcessInformation.hProcess], xmm0
0x180006ee8  mov     qword ptr [rsp+138h+ProcessInformation.dwProcessId], rax
0x180006ef0  mov     [rsp+138h+Environment], r13
0x180006ef5  mov     r12d, r13d
0x180006ef8  mov     [rsp+138h+var_D0], r13d
0x180006efd  mov     [rsp+138h+var_A8], r13
0x180006f05  mov     [rsp+138h+ExitCode], r13d
0x180006f0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006f11  mov     rcx, rax
0x180006f14  inc     rcx
0x180006f17  cmp     [rsi+rcx*2], r13w
0x180006f1c  jnz     short loc_180006F14
0x180006f1e  mov     rdx, rax
0x180006f21  inc     rdx
0x180006f24  cmp     [r14+rdx*2], r13w
0x180006f29  jnz     short loc_180006F21
0x180006f2b  lea     r8, word_180021670
0x180006f32  inc     rax
0x180006f35  cmp     [r8+rax*2], r13w
0x180006f3a  jnz     short loc_180006F32
0x180006f3c  add     edx, 18h
0x180006f3f  add     eax, edx
0x180006f41  add     ecx, eax
0x180006f43  mov     ebx, ecx
0x180006f45  lea     rdx, [rcx+rcx]; uBytes
0x180006f49  xor     ecx, ecx; uFlags
0x180006f4b  call    cs:__imp_LocalAlloc
0x180006f51  mov     rdi, rax
0x180006f54  mov     [rsp+138h+var_A8], rax
0x180006f5c  test    rax, rax
0x180006f5f  jnz     short loc_180006F6B
0x180006f61  mov     ebx, 8007000Eh
0x180006f66  jmp     loc_180007161
0x180006f6b  mov     qword ptr [rsp+138h+dwCreationFlags], rsi
0x180006f70  mov     [rsp+138h+phNewToken], r14
0x180006f75  mov     rax, [r15+2B0h]
0x180006f7c  mov     qword ptr [rsp+138h+TokenType], rax
0x180006f81  lea     r9, word_180021670
0x180006f88  lea     r8, aSIuSS; "\"%s\" %Iu \"%s\" \"%s\""
0x180006f8f  mov     rdx, rbx; unsigned __int64
0x180006f92  mov     rcx, rdi; unsigned __int16 *
0x180006f95  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f9a  mov     ebx, eax
0x180006f9c  test    eax, eax
0x180006f9e  js      loc_180007161
0x180006fa4  lea     rax, [rsp+138h+hToken]
0x180006fa9  mov     [rsp+138h+phNewToken], rax; phNewToken
0x180006fae  mov     r14d, 1
0x180006fb4  mov     [rsp+138h+TokenType], r14d; TokenType
0x180006fb9  lea     esi, [r14+1]
0x180006fbd  mov     r9d, esi; ImpersonationLevel
0x180006fc0  xor     r8d, r8d; lpTokenAttributes
0x180006fc3  xor     edx, edx; dwDesiredAccess
0x180006fc5  mov     rcx, [r15+2A8h]; hExistingToken
0x180006fcc  call    cs:__imp_DuplicateTokenEx
0x180006fd2  test    eax, eax
0x180006fd4  jnz     short loc_18000700F
0x180006fd6  call    cs:__imp_GetLastError
0x180006fdc  mov     ebx, eax
0x180006fde  test    eax, eax
0x180006fe0  jle     short loc_180006FEB
0x180006fe2  movzx   ebx, ax
0x180006fe5  or      ebx, 80070000h
0x180006feb  lea     r9, aFailedToDuplic; "Failed to duplicate Token. Error %x"
0x180006ff2  mov     [rsp+138h+TokenType], ebx
0x180006ff6  mov     r8d, esi; unsigned __int8
0x180006ff9  mov     edx, 8; unsigned int
0x180006ffe  lea     rcx, qword_180021AD8; this
0x180007005  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000700a  jmp     loc_180007161
0x18000700f  mov     rcx, [rsp+138h+hToken]; TokenHandle
0x180007014  call    ?SetTokenIntegrityLevel@Utils@@SAJPEAXK@Z; Utils::SetTokenIntegrityLevel(void *,ulong)
0x180007019  mov     ebx, eax
0x18000701b  test    eax, eax
0x18000701d  jns     short loc_18000702C
0x18000701f  mov     [rsp+138h+TokenType], eax
0x180007023  lea     r9, aFailedToSetTok; "Failed to Set Token Integrity Level. Er"...
0x18000702a  jmp     short loc_180006FF6
0x18000702c  xor     r8d, r8d; bInherit
0x18000702f  mov     rdx, [rsp+138h+hToken]; hToken
0x180007034  lea     rcx, [rsp+138h+Environment]; lpEnvironment
0x180007039  call    cs:__imp_CreateEnvironmentBlock
0x18000703f  test    eax, eax
0x180007041  jnz     short loc_180007061
0x180007043  call    cs:__imp_GetLastError
0x180007049  mov     ebx, eax
0x18000704b  test    eax, eax
0x18000704d  jle     short loc_180007058
0x18000704f  movzx   ebx, ax
0x180007052  or      ebx, 80070000h
0x180007058  lea     r9, aFailedToCreate_2; "Failed to Create Environment Block. Err"...
0x18000705f  jmp     short loc_180006FF2
0x180007061  mov     rcx, [rsp+138h+hToken]; hToken
0x180007066  call    cs:__imp_ImpersonateLoggedOnUser
0x18000706c  test    eax, eax
0x18000706e  jnz     short loc_180007091
0x180007070  call    cs:__imp_GetLastError
0x180007076  mov     ebx, eax
0x180007078  test    eax, eax
0x18000707a  jle     short loc_180007085
0x18000707c  movzx   ebx, ax
0x18000707f  or      ebx, 80070000h
0x180007085  lea     r9, aFailedToImpers; "Failed to Impersonate %x"
0x18000708c  jmp     loc_180006FF2
0x180007091  mov     r12d, r14d
0x180007094  mov     [rsp+138h+var_D0], r14d
0x180007099  mov     [rsp+138h+StartupInfo.cb], 68h ; 'h'
0x1800070a4  mov     rax, [r15+290h]
0x1800070ab  mov     [rsp+138h+StartupInfo.lpDesktop], rax
0x1800070b3  lea     rax, [rsp+138h+ProcessInformation]
0x1800070b8  mov     [rsp+138h+lpProcessInformation], rax; lpProcessInformation
0x1800070bd  lea     rax, [rsp+138h+StartupInfo]
0x1800070c5  mov     [rsp+138h+lpStartupInfo], rax; lpStartupInfo
0x1800070ca  mov     [rsp+138h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1800070cf  mov     rax, [rsp+138h+Environment]
0x1800070d4  mov     [rsp+138h+lpEnvironment], rax; lpEnvironment
0x1800070d9  mov     [rsp+138h+dwCreationFlags], 404h; dwCreationFlags
0x1800070e1  mov     dword ptr [rsp+138h+phNewToken], r13d; bInheritHandles
0x1800070e6  mov     qword ptr [rsp+138h+TokenType], r13; lpThreadAttributes
0x1800070eb  xor     r9d, r9d; lpProcessAttributes
0x1800070ee  mov     r8, rdi; lpCommandLine
0x1800070f1  xor     edx, edx; lpApplicationName
0x1800070f3  mov     rcx, [rsp+138h+hToken]; hToken
0x1800070f8  call    cs:__imp_CreateProcessAsUserW
0x1800070fe  test    eax, eax
0x180007100  jnz     short loc_180007123
0x180007102  call    cs:__imp_GetLastError
0x180007108  mov     ebx, eax
0x18000710a  test    eax, eax
0x18000710c  jle     short loc_180007117
0x18000710e  movzx   ebx, ax
0x180007111  or      ebx, 80070000h
0x180007117  lea     r9, aFailedToCreate_0; "Failed to CreateProcess %x"
0x18000711e  jmp     loc_180006FF2
0x180007123  mov     rcx, [rsp+138h+ProcessInformation.hThread]; hThread
0x18000712b  call    cs:__imp_ResumeThread
0x180007131  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007134  mov     rcx, [rsp+138h+ProcessInformation.hProcess]; hHandle
0x180007139  call    cs:__imp_WaitForSingleObject
0x18000713f  lea     rdx, [rsp+138h+ExitCode]; lpExitCode
0x180007147  mov     rcx, [rsp+138h+ProcessInformation.hProcess]; hProcess
0x18000714c  call    cs:__imp_GetExitCodeProcess
0x180007152  mov     ebx, 800B0004h
0x180007157  test    eax, eax
0x180007159  cmovnz  ebx, [rsp+138h+ExitCode]
0x180007161  test    r12d, r12d
0x180007164  jz      short loc_18000716C
0x180007166  call    cs:__imp_RevertToSelf
0x18000716c  test    rdi, rdi
0x18000716f  jz      short loc_18000717A
0x180007171  mov     rcx, rdi; hMem
0x180007174  call    cs:__imp_LocalFree
0x18000717a  mov     rcx, [rsp+138h+Environment]; lpEnvironment
0x18000717f  test    rcx, rcx
0x180007182  jz      short loc_18000718A
0x180007184  call    cs:__imp_DestroyEnvironmentBlock
0x18000718a  mov     rcx, [rsp+138h+hToken]; hObject
0x18000718f  test    rcx, rcx
0x180007192  jz      short loc_18000719A
0x180007194  call    cs:__imp_CloseHandle
0x18000719a  mov     rcx, [rsp+138h+ProcessInformation.hThread]; hObject
0x1800071a2  test    rcx, rcx
0x1800071a5  jz      short loc_1800071AD
0x1800071a7  call    cs:__imp_CloseHandle
0x1800071ad  mov     rcx, [rsp+138h+ProcessInformation.hProcess]; hObject
0x1800071b2  test    rcx, rcx
0x1800071b5  jz      short loc_1800071BD
0x1800071b7  call    cs:__imp_CloseHandle
0x1800071bd  mov     eax, ebx
0x1800071bf  lea     r11, [rsp+138h+var_28]
0x1800071c7  mov     rbx, [r11+30h]
0x1800071cb  mov     rsi, [r11+38h]
0x1800071cf  mov     rsp, r11
0x1800071d2  pop     r15
0x1800071d4  pop     r14
0x1800071d6  pop     r13
0x1800071d8  pop     r12
0x1800071da  pop     rdi
0x1800071db  retn
0x180014865  push    rbp
0x180014867  sub     rsp, 60h
0x18001486b  mov     rbp, rdx
0x18001486e  cmp     dword ptr [rbp+68h], 0
0x180014872  jz      short loc_18001487B
0x180014874  call    cs:__imp_RevertToSelf
0x18001487a  nop
0x18001487b  mov     rcx, [rbp+90h]; hMem
0x180014882  test    rcx, rcx
0x180014885  jz      short loc_18001488E
0x180014887  call    cs:__imp_LocalFree
0x18001488d  nop
0x18001488e  mov     rcx, [rbp+70h]; lpEnvironment
0x180014892  test    rcx, rcx
0x180014895  jz      short loc_18001489E
0x180014897  call    cs:__imp_DestroyEnvironmentBlock
0x18001489d  nop
0x18001489e  mov     rcx, [rbp+60h]; hObject
0x1800148a2  test    rcx, rcx
0x1800148a5  jz      short loc_1800148AE
0x1800148a7  call    cs:__imp_CloseHandle
0x1800148ad  nop
0x1800148ae  mov     rcx, [rbp+80h]; hObject
0x1800148b5  test    rcx, rcx
0x1800148b8  jz      short loc_1800148C1
0x1800148ba  call    cs:__imp_CloseHandle
0x1800148c0  nop
0x1800148c1  mov     rcx, [rbp+78h]; hObject
0x1800148c5  test    rcx, rcx
0x1800148c8  jz      short loc_1800148D1
0x1800148ca  call    cs:__imp_CloseHandle
0x1800148d0  nop
0x1800148d1  add     rsp, 60h
0x1800148d5  pop     rbp
0x1800148d6  retn
```

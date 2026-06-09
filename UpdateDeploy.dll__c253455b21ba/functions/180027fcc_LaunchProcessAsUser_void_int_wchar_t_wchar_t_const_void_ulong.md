# LaunchProcessAsUser(void *,int,wchar_t *,wchar_t const *,void * *,ulong *)

- ea: `0x180027fcc`
- end: `0x1800282fd`
- name: `?LaunchProcessAsUser@@YAJPEAXHPEA_WPEB_WPEAPEAXPEAK@Z`
- size: `817`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int, wchar_t *, const wchar_t *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016f8c`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b6c`
- `0x1800110fc`
- `0x180027d30`
- `0x180027fcc`
- `0x180061960`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028173`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028173`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028161`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180028215`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180028215`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002815b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800282a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800282cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002815b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800282a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800282cc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180028074`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180028093`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180028074`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180028093`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800281c6`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800281c6`
- `USERENV!DestroyEnvironmentBlock` at `0x1800280e9`
- `USERENV!DestroyEnvironmentBlock` at `0x1800282be`
- `USERENV!DestroyEnvironmentBlock` at `0x1800280e9`
- `USERENV!DestroyEnvironmentBlock` at `0x1800282be`
- `USERENV!CreateEnvironmentBlock` at `0x180028101`
- `USERENV!CreateEnvironmentBlock` at `0x180028101`

## string_xrefs

- `0x1800280c1`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhutil.cpp`
- `0x180028228`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhutil.cpp`
- `0x180028261`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhutil.cpp`
- `0x18002808c`: `SeRemoteShutdownPrivilege`
- `0x18002806d`: `SeShutdownPrivilege`
- `0x180028130`: `Attempting to create remote process with host process token`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall LaunchProcessAsUser(
        HANDLE TokenHandle,
        int a2,
        wchar_t *a3,
        const wchar_t *a4,
        void **a5,
        unsigned int *a6)
{
  WCHAR *v6; // r12
  void *v9; // rbx
  unsigned int LastError; // edi
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  void *v15; // r12
  DWORD v16; // edi
  HANDLE CurrentProcess; // rax
  HANDLE hThread; // rax
  int DeletePrivilegeCount; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hToken; // [rsp+F0h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID lpEnvironment; // [rsp+100h] [rbp+0h] BYREF
  _LUID Luid[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v28; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v6 = a3;
  v9 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  lpEnvironment = 0;
  hObject = 0;
  hToken = 0;
  v28 = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  if ( !a5 )
  {
    LastError = -2147467261;
    v11 = 88;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhutil.cpp",
      (const char *)LastError,
      DeletePrivilegeCount);
    goto LABEL_41;
  }
  if ( a6 )
    *a6 = 0;
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", Luid) )
  {
    v13 = 95;
LABEL_31:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhutil.cpp",
                  v12);
    goto LABEL_41;
  }
  if ( !LookupPrivilegeValueW(0, L"SeRemoteShutdownPrivilege", (PLUID)&Luid[1].HighPart) )
  {
    v13 = 96;
    goto LABEL_31;
  }
  StartupInfo.cb = 104;
  if ( TokenHandle )
  {
    v14 = DumpTokenInfo(TokenHandle);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhutil.cpp",
        (const char *)(unsigned int)v14,
        DeletePrivilegeCount);
    v15 = lpEnvironment;
    if ( lpEnvironment )
    {
      v16 = GetLastError();
      DestroyEnvironmentBlock(v15);
      SetLastError(v16);
    }
    if ( !CreateEnvironmentBlock(&lpEnvironment, TokenHandle, 0) )
    {
      v13 = 107;
      goto LABEL_31;
    }
    v6 = a3;
LABEL_19:
    StartupInfo.lpDesktop = L"winsta0\\default";
    if ( TokenHandle )
      goto LABEL_25;
    goto LABEL_20;
  }
  if ( a2 )
    goto LABEL_19;
LABEL_20:
  WUTrace(0, 0, 0x1000000, 5, 0, L"Attempting to create remote process with host process token");
  if ( hObject )
    CloseHandle(hObject);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xBu, &hObject) )
  {
    v13 = 123;
    goto LABEL_31;
  }
  TokenHandle = hObject;
LABEL_25:
  if ( hToken )
    CloseHandle(hToken);
  if ( !CreateRestrictedToken(TokenHandle, 0, 0, 0, 2u, (PLUID_AND_ATTRIBUTES)Luid, 0, 0, &hToken) )
  {
    v13 = 136;
    goto LABEL_31;
  }
  if ( !CreateProcessAsUserW(hToken, 0, v6, 0, 0, 0, 0x400u, lpEnvironment, 0, &StartupInfo, &ProcessInformation) )
  {
    v13 = 148;
    goto LABEL_31;
  }
  hThread = ProcessInformation.hThread;
  if ( !ProcessInformation.hThread )
  {
    v11 = 150;
LABEL_36:
    LastError = -2145120257;
    goto LABEL_37;
  }
  if ( !ProcessInformation.hProcess )
  {
    v11 = 151;
    goto LABEL_36;
  }
  *a5 = ProcessInformation.hProcess;
  v9 = hThread;
  if ( a6 )
    *a6 = ProcessInformation.dwProcessId;
  LastError = 0;
LABEL_41:
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( lpEnvironment )
    DestroyEnvironmentBlock(lpEnvironment);
  if ( v9 )
    CloseHandle(v9);
  return LastError;
}

```

## disassembly

```asm
0x180027fcc  mov     [rsp-8+arg_8], rbx
0x180027fd1  mov     [rsp-8+arg_18], rdi
0x180027fd6  push    rbp
0x180027fd7  push    r12
0x180027fd9  push    r13
0x180027fdb  push    r14
0x180027fdd  push    r15
0x180027fdf  lea     rbp, [rsp-30h]
0x180027fe4  sub     rsp, 130h
0x180027feb  mov     rax, cs:__security_cookie
0x180027ff2  xor     rax, rsp
0x180027ff5  mov     [rbp+50h+var_30], rax
0x180027ff9  mov     r13, [rbp+50h+arg_20]
0x180028000  mov     r12, r8
0x180028003  mov     r15, [rbp+50h+arg_28]
0x18002800a  mov     edi, edx
0x18002800c  mov     [rsp+150h+var_F0], r8
0x180028011  mov     r14, rcx
0x180028014  xorps   xmm0, xmm0
0x180028017  lea     rcx, [rbp+50h+StartupInfo]; void *
0x18002801b  xor     eax, eax
0x18002801d  xor     ebx, ebx
0x18002801f  xor     edx, edx; Val
0x180028021  mov     qword ptr [rsp+150h+ProcessInformation.dwProcessId], rax
0x180028026  movups  xmmword ptr [rsp+150h+ProcessInformation.hProcess], xmm0
0x18002802b  lea     r8d, [rbx+68h]; Size
0x18002802f  call    memset
0x180028034  xor     eax, eax
0x180028036  mov     [rbp+50h+lpEnvironment], rbx
0x18002803a  mov     [rbp+50h+hObject], rbx
0x18002803e  xorps   xmm0, xmm0
0x180028041  mov     [rbp+50h+hToken], rbx
0x180028045  mov     [rbp+50h+var_38], rax
0x180028049  movups  xmmword ptr [rbp+50h+Luid.LowPart], xmm0
0x18002804d  test    r13, r13
0x180028050  jnz     short loc_18002805F
0x180028052  mov     edi, 80004003h
0x180028057  lea     edx, [rbx+58h]
0x18002805a  jmp     loc_18002825D
0x18002805f  test    r15, r15
0x180028062  jz      short loc_180028067
0x180028064  mov     [r15], eax
0x180028067  lea     r8, [rbp+50h+Luid]; lpLuid
0x18002806b  xor     ecx, ecx; lpSystemName
0x18002806d  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x180028074  call    cs:__imp_LookupPrivilegeValueW
0x18002807a  test    eax, eax
0x18002807c  jnz     short loc_180028086
0x18002807e  lea     edx, [rax+5Fh]
0x180028081  jmp     loc_180028224
0x180028086  lea     r8, [rbp+50h+Luid.HighPart+8]; lpLuid
0x18002808a  xor     ecx, ecx; lpSystemName
0x18002808c  lea     rdx, aSeremoteshutdo; "SeRemoteShutdownPrivilege"
0x180028093  call    cs:__imp_LookupPrivilegeValueW
0x180028099  test    eax, eax
0x18002809b  jnz     short loc_1800280A5
0x18002809d  lea     edx, [rax+60h]
0x1800280a0  jmp     loc_180028224
0x1800280a5  mov     [rbp+50h+StartupInfo.cb], 68h ; 'h'
0x1800280ac  test    r14, r14
0x1800280af  jz      short loc_180028113
0x1800280b1  mov     rcx, r14; TokenHandle
0x1800280b4  call    DumpTokenInfo
0x1800280b9  test    eax, eax
0x1800280bb  jns     short loc_1800280D5
0x1800280bd  mov     rcx, [rbp+58h]; this
0x1800280c1  lea     r8, aCW1SSrcClientU_8; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800280c8  mov     r9d, eax; char *
0x1800280cb  mov     edx, 67h ; 'g'; void *
0x1800280d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800280d5  mov     r12, [rbp+50h+lpEnvironment]
0x1800280d9  test    r12, r12
0x1800280dc  jz      short loc_1800280F7
0x1800280de  call    cs:__imp_GetLastError
0x1800280e4  mov     rcx, r12; lpEnvironment
0x1800280e7  mov     edi, eax
0x1800280e9  call    cs:__imp_DestroyEnvironmentBlock
0x1800280ef  mov     ecx, edi; dwErrCode
0x1800280f1  call    cs:__imp_SetLastError
0x1800280f7  xor     r8d, r8d; bInherit
0x1800280fa  lea     rcx, [rbp+50h+lpEnvironment]; lpEnvironment
0x1800280fe  mov     rdx, r14; hToken
0x180028101  call    cs:__imp_CreateEnvironmentBlock
0x180028107  test    eax, eax
0x180028109  jnz     short loc_180028119
0x18002810b  lea     edx, [rax+6Bh]
0x18002810e  jmp     loc_180028224
0x180028113  test    edi, edi
0x180028115  jz      short loc_18002812E
0x180028117  jmp     short loc_18002811E
0x180028119  mov     r12, [rsp+150h+var_F0]
0x18002811e  lea     rax, aWinsta0Default; "winsta0\\default"
0x180028125  mov     [rbp+50h+StartupInfo.lpDesktop], rax
0x180028129  test    r14, r14
0x18002812c  jnz     short loc_180028189
0x18002812e  xor     edx, edx
0x180028130  lea     rax, aAttemptingToCr_0; "Attempting to create remote process wit"...
0x180028137  mov     [rsp+150h+PrivilegesToDelete], rax
0x18002813c  xor     ecx, ecx
0x18002813e  mov     r8d, 1000000h
0x180028144  mov     qword ptr [rsp+150h+DeletePrivilegeCount], rbx
0x180028149  lea     r9d, [rdx+5]
0x18002814d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028152  mov     rcx, [rbp+50h+hObject]; hObject
0x180028156  test    rcx, rcx
0x180028159  jz      short loc_180028161
0x18002815b  call    cs:__imp_CloseHandle
0x180028161  call    cs:__imp_GetCurrentProcess
0x180028167  lea     r8, [rbp+50h+hObject]; TokenHandle
0x18002816b  mov     edx, 0Bh; DesiredAccess
0x180028170  mov     rcx, rax; ProcessHandle
0x180028173  call    cs:__imp_OpenProcessToken
0x180028179  test    eax, eax
0x18002817b  jnz     short loc_180028185
0x18002817d  lea     edx, [rax+7Bh]
0x180028180  jmp     loc_180028224
0x180028185  mov     r14, [rbp+50h+hObject]
0x180028189  mov     rcx, [rbp+50h+hToken]; hObject
0x18002818d  test    rcx, rcx
0x180028190  jz      short loc_180028198
0x180028192  call    cs:__imp_CloseHandle
0x180028198  lea     rax, [rbp+50h+hToken]
0x18002819c  xor     r9d, r9d; SidsToDisable
0x18002819f  mov     [rsp+150h+NewTokenHandle], rax; NewTokenHandle
0x1800281a4  xor     r8d, r8d; DisableSidCount
0x1800281a7  mov     [rsp+150h+SidsToRestrict], rbx; SidsToRestrict
0x1800281ac  lea     rax, [rbp+50h+Luid]
0x1800281b0  mov     [rsp+150h+RestrictedSidCount], ebx; RestrictedSidCount
0x1800281b4  xor     edx, edx; Flags
0x1800281b6  mov     [rsp+150h+PrivilegesToDelete], rax; PrivilegesToDelete
0x1800281bb  mov     rcx, r14; ExistingTokenHandle
0x1800281be  mov     [rsp+150h+DeletePrivilegeCount], 2; DeletePrivilegeCount
0x1800281c6  call    cs:__imp_CreateRestrictedToken
0x1800281cc  test    eax, eax
0x1800281ce  jnz     short loc_1800281D7
0x1800281d0  mov     edx, 88h
0x1800281d5  jmp     short loc_180028224
0x1800281d7  mov     rax, [rbp+50h+lpEnvironment]
0x1800281db  lea     rcx, [rsp+150h+ProcessInformation]
0x1800281e0  mov     [rsp+150h+lpProcessInformation], rcx; lpProcessInformation
0x1800281e5  xor     r9d, r9d; lpProcessAttributes
0x1800281e8  lea     rcx, [rbp+50h+StartupInfo]
0x1800281ec  mov     r8, r12; lpCommandLine
0x1800281ef  mov     [rsp+150h+lpStartupInfo], rcx; lpStartupInfo
0x1800281f4  xor     edx, edx; lpApplicationName
0x1800281f6  mov     rcx, [rbp+50h+hToken]; hToken
0x1800281fa  mov     [rsp+150h+NewTokenHandle], rbx; lpCurrentDirectory
0x1800281ff  mov     [rsp+150h+SidsToRestrict], rax; lpEnvironment
0x180028204  mov     [rsp+150h+RestrictedSidCount], 400h; dwCreationFlags
0x18002820c  mov     dword ptr [rsp+150h+PrivilegesToDelete], ebx; bInheritHandles
0x180028210  mov     qword ptr [rsp+150h+DeletePrivilegeCount], rbx; int
0x180028215  call    cs:__imp_CreateProcessAsUserW
0x18002821b  test    eax, eax
0x18002821d  jnz     short loc_180028238
0x18002821f  mov     edx, 94h; void *
0x180028224  mov     rcx, [rbp+58h]; this
0x180028228  lea     r8, aCW1SSrcClientU_8; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002822f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028234  mov     edi, eax
0x180028236  jmp     short loc_180028287
0x180028238  mov     rax, [rsp+150h+ProcessInformation.hThread]
0x18002823d  test    rax, rax
0x180028240  jnz     short loc_180028249
0x180028242  mov     edx, 96h
0x180028247  jmp     short loc_180028258
0x180028249  mov     rcx, [rsp+150h+ProcessInformation.hProcess]
0x18002824e  test    rcx, rcx
0x180028251  jnz     short loc_180028272
0x180028253  mov     edx, 97h; void *
0x180028258  mov     edi, 80240FFFh
0x18002825d  mov     rcx, [rbp+58h]; this
0x180028261  lea     r8, aCW1SSrcClientU_8; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180028268  mov     r9d, edi; char *
0x18002826b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028270  jmp     short loc_180028287
0x180028272  mov     [r13+0], rcx
0x180028276  mov     rbx, rax
0x180028279  test    r15, r15
0x18002827c  jz      short loc_180028285
0x18002827e  mov     eax, [rsp+150h+ProcessInformation.dwProcessId]
0x180028282  mov     [r15], eax
0x180028285  xor     edi, edi
0x180028287  mov     rcx, [rbp+50h+hToken]; hObject
0x18002828b  test    rcx, rcx
0x18002828e  jz      short loc_18002829E
0x180028290  call    cs:__imp_CloseHandle
0x180028296  mov     [rbp+50h+hToken], 0
0x18002829e  mov     rcx, [rbp+50h+hObject]; hObject
0x1800282a2  test    rcx, rcx
0x1800282a5  jz      short loc_1800282B5
0x1800282a7  call    cs:__imp_CloseHandle
0x1800282ad  mov     [rbp+50h+hObject], 0
0x1800282b5  mov     rcx, [rbp+50h+lpEnvironment]; lpEnvironment
0x1800282b9  test    rcx, rcx
0x1800282bc  jz      short loc_1800282C4
0x1800282be  call    cs:__imp_DestroyEnvironmentBlock
0x1800282c4  test    rbx, rbx
0x1800282c7  jz      short loc_1800282D2
0x1800282c9  mov     rcx, rbx; hObject
0x1800282cc  call    cs:__imp_CloseHandle
0x1800282d2  mov     eax, edi
0x1800282d4  mov     rcx, [rbp+50h+var_30]
0x1800282d8  xor     rcx, rsp; StackCookie
0x1800282db  call    __security_check_cookie
0x1800282e0  lea     r11, [rsp+150h+var_20]
0x1800282e8  mov     rbx, [r11+38h]
0x1800282ec  mov     rdi, [r11+48h]
0x1800282f0  mov     rsp, r11
0x1800282f3  pop     r15
0x1800282f5  pop     r14
0x1800282f7  pop     r13
0x1800282f9  pop     r12
0x1800282fb  pop     rbp
0x1800282fc  retn
```

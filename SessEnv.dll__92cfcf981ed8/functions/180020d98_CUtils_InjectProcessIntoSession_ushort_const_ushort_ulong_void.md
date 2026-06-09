# CUtils::InjectProcessIntoSession(ushort const *,ushort *,ulong,void * *)

- ea: `0x180020d98`
- end: `0x180020fcd`
- name: `?InjectProcessIntoSession@CUtils@@SAJPEBGPEAGKPEAPEAX@Z`
- size: `565`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine, unsigned int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180037e30`

## callees

- `0x180003f30`
- `0x18001ad5c`
- `0x180020d98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020de3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020df6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020df6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180020f27`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180020f27`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180020e9d`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180020e9d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020e61`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020e61`

## string_xrefs

- `0x180020e1c`: `OpenProcessToken failed: 0x%x in %s`
- `0x180020e81`: `DuplicateTokenEx failed: 0x%x in %s`
- `0x180020ebd`: `SetTokenInformation failed: 0x%x in %s`
- `0x180020f47`: `CreateProcessAsUserW failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::InjectProcessIntoSession(LPCWSTR lpApplicationName, LPWSTR lpCommandLine, int a3, void **a4)
{
  signed int v4; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  int TokenInformation; // [rsp+150h] [rbp+50h] BYREF

  TokenInformation = a3;
  v4 = 0;
  TokenHandle = 0;
  hToken = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
    goto LABEL_10;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_10:
    if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
      goto LABEL_15;
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_15:
      if ( SetTokenInformation(hToken, TokenSessionId, &TokenInformation, 4u) )
        goto LABEL_17;
      v11 = GetLastError();
      v4 = v11;
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_17:
        StartupInfo.lpDesktop = L"Winsta0\\default";
        StartupInfo.cb = 104;
        if ( CreateProcessAsUserW(
               hToken,
               lpApplicationName,
               lpCommandLine,
               0,
               0,
               0,
               0,
               0,
               0,
               &StartupInfo,
               &ProcessInformation) )
        {
          goto LABEL_22;
        }
        v12 = GetLastError();
        v4 = v12;
        if ( v12 > 0 )
          v4 = (unsigned __int16)v12 | 0x80070000;
        if ( v4 >= 0 )
        {
LABEL_22:
          if ( a4 )
          {
            *a4 = ProcessInformation.hProcess;
            ProcessInformation.hProcess = 0;
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "CreateProcessAsUserW failed: 0x%x in %s",
            (unsigned int)v4,
            "CUtils::InjectProcessIntoSession");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "SetTokenInformation failed: 0x%x in %s",
          (unsigned int)v4,
          "CUtils::InjectProcessIntoSession");
      }
    }
    else
    {
      _DbgPrintMessage(8, "DuplicateTokenEx failed: 0x%x in %s", (unsigned int)v4, "CUtils::InjectProcessIntoSession");
    }
  }
  else
  {
    _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x in %s", (unsigned int)v4, "CUtils::InjectProcessIntoSession");
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hToken )
    CloseHandle(hToken);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180020d98  mov     [rsp-8+TokenInformation], r8d
0x180020d9d  push    rbp
0x180020d9e  push    rbx
0x180020d9f  push    rsi
0x180020da0  push    rdi
0x180020da1  push    r12
0x180020da3  push    r14
0x180020da5  lea     rbp, [rsp-8]
0x180020daa  sub     rsp, 108h
0x180020db1  xor     ebx, ebx
0x180020db3  mov     rsi, rdx
0x180020db6  mov     r14, rcx
0x180020db9  mov     [rsp+130h+TokenHandle], rbx
0x180020dbe  xorps   xmm0, xmm0
0x180020dc1  mov     [rsp+130h+hToken], rbx
0x180020dc6  xor     eax, eax
0x180020dc8  lea     rcx, [rbp+30h+StartupInfo]; void *
0x180020dcc  lea     r8d, [rbx+68h]; Size
0x180020dd0  mov     qword ptr [rbp+30h+ProcessInformation.dwProcessId], rax
0x180020dd4  xor     edx, edx; Val
0x180020dd6  mov     rdi, r9
0x180020dd9  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x180020dde  call    memset_0
0x180020de3  call    cs:__imp_GetCurrentProcess
0x180020de9  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x180020dee  mov     edx, 0F01FFh; DesiredAccess
0x180020df3  mov     rcx, rax; ProcessHandle
0x180020df6  call    cs:__imp_OpenProcessToken
0x180020dfc  mov     r12d, 80070000h
0x180020e02  test    eax, eax
0x180020e04  jnz     short loc_180020E3C
0x180020e06  call    cs:__imp_GetLastError
0x180020e0c  mov     ebx, eax
0x180020e0e  test    eax, eax
0x180020e10  jle     short loc_180020E18
0x180020e12  movzx   ebx, ax
0x180020e15  or      ebx, r12d
0x180020e18  test    ebx, ebx
0x180020e1a  jns     short loc_180020E3C
0x180020e1c  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: 0x%x in %s"
0x180020e23  mov     r8d, ebx
0x180020e26  lea     r9, aCutilsInjectpr; "CUtils::InjectProcessIntoSession"
0x180020e2d  mov     ecx, 8; int
0x180020e32  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020e37  jmp     loc_180020F69
0x180020e3c  mov     rcx, [rsp+130h+TokenHandle]; hExistingToken
0x180020e41  lea     rax, [rsp+130h+hToken]
0x180020e46  mov     [rsp+130h+phNewToken], rax; phNewToken
0x180020e4b  mov     r9d, 2; ImpersonationLevel
0x180020e51  xor     r8d, r8d; lpTokenAttributes
0x180020e54  mov     [rsp+130h+TokenType], 1; TokenType
0x180020e5c  mov     edx, 2000000h; dwDesiredAccess
0x180020e61  call    cs:__imp_DuplicateTokenEx
0x180020e67  test    eax, eax
0x180020e69  jnz     short loc_180020E8A
0x180020e6b  call    cs:__imp_GetLastError
0x180020e71  mov     ebx, eax
0x180020e73  test    eax, eax
0x180020e75  jle     short loc_180020E7D
0x180020e77  movzx   ebx, ax
0x180020e7a  or      ebx, r12d
0x180020e7d  test    ebx, ebx
0x180020e7f  jns     short loc_180020E8A
0x180020e81  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed: 0x%x in %s"
0x180020e88  jmp     short loc_180020E23
0x180020e8a  mov     rcx, [rsp+130h+hToken]; TokenHandle
0x180020e8f  lea     r8, [rbp+30h+TokenInformation]; TokenInformation
0x180020e93  mov     r9d, 4; TokenInformationLength
0x180020e99  lea     edx, [r9+8]; TokenInformationClass
0x180020e9d  call    cs:__imp_SetTokenInformation
0x180020ea3  test    eax, eax
0x180020ea5  jnz     short loc_180020EC9
0x180020ea7  call    cs:__imp_GetLastError
0x180020ead  mov     ebx, eax
0x180020eaf  test    eax, eax
0x180020eb1  jle     short loc_180020EB9
0x180020eb3  movzx   ebx, ax
0x180020eb6  or      ebx, r12d
0x180020eb9  test    ebx, ebx
0x180020ebb  jns     short loc_180020EC9
0x180020ebd  lea     rdx, aSettokeninform; "SetTokenInformation failed: 0x%x in %s"
0x180020ec4  jmp     loc_180020E23
0x180020ec9  mov     rcx, [rsp+130h+hToken]; hToken
0x180020ece  lea     rax, aWinsta0Default; "Winsta0\\default"
0x180020ed5  mov     [rbp+30h+StartupInfo.lpDesktop], rax
0x180020ed9  xor     r9d, r9d; lpProcessAttributes
0x180020edc  lea     rax, [rsp+130h+ProcessInformation]
0x180020ee1  mov     [rbp+30h+StartupInfo.cb], 68h ; 'h'
0x180020ee8  mov     [rsp+130h+lpProcessInformation], rax; lpProcessInformation
0x180020eed  mov     r8, rsi; lpCommandLine
0x180020ef0  lea     rax, [rbp+30h+StartupInfo]
0x180020ef4  mov     rdx, r14; lpApplicationName
0x180020ef7  mov     [rsp+130h+lpStartupInfo], rax; lpStartupInfo
0x180020efc  mov     [rsp+130h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180020f05  mov     [rsp+130h+lpEnvironment], 0; lpEnvironment
0x180020f0e  mov     [rsp+130h+dwCreationFlags], 0; dwCreationFlags
0x180020f16  mov     dword ptr [rsp+130h+phNewToken], 0; bInheritHandles
0x180020f1e  mov     qword ptr [rsp+130h+TokenType], 0; lpThreadAttributes
0x180020f27  call    cs:__imp_CreateProcessAsUserW
0x180020f2d  test    eax, eax
0x180020f2f  jnz     short loc_180020F53
0x180020f31  call    cs:__imp_GetLastError
0x180020f37  mov     ebx, eax
0x180020f39  test    eax, eax
0x180020f3b  jle     short loc_180020F43
0x180020f3d  movzx   ebx, ax
0x180020f40  or      ebx, r12d
0x180020f43  test    ebx, ebx
0x180020f45  jns     short loc_180020F53
0x180020f47  lea     rdx, aCreateprocessa; "CreateProcessAsUserW failed: 0x%x in %s"
0x180020f4e  jmp     loc_180020E23
0x180020f53  test    rdi, rdi
0x180020f56  jz      short loc_180020F69
0x180020f58  mov     rax, [rsp+130h+ProcessInformation.hProcess]
0x180020f5d  mov     [rdi], rax
0x180020f60  mov     [rsp+130h+ProcessInformation.hProcess], 0
0x180020f69  mov     rcx, [rsp+130h+ProcessInformation.hThread]; hObject
0x180020f6e  test    rcx, rcx
0x180020f71  jz      short loc_180020F82
0x180020f73  call    cs:__imp_CloseHandle
0x180020f79  mov     [rsp+130h+ProcessInformation.hThread], 0
0x180020f82  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hObject
0x180020f87  test    rcx, rcx
0x180020f8a  jz      short loc_180020F9B
0x180020f8c  call    cs:__imp_CloseHandle
0x180020f92  mov     [rsp+130h+ProcessInformation.hProcess], 0
0x180020f9b  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x180020fa0  test    rcx, rcx
0x180020fa3  jz      short loc_180020FAB
0x180020fa5  call    cs:__imp_CloseHandle
0x180020fab  mov     rcx, [rsp+130h+hToken]; hObject
0x180020fb0  test    rcx, rcx
0x180020fb3  jz      short loc_180020FBB
0x180020fb5  call    cs:__imp_CloseHandle
0x180020fbb  mov     eax, ebx
0x180020fbd  add     rsp, 108h
0x180020fc4  pop     r14
0x180020fc6  pop     r12
0x180020fc8  pop     rdi
0x180020fc9  pop     rsi
0x180020fca  pop     rbx
0x180020fcb  pop     rbp
0x180020fcc  retn
```

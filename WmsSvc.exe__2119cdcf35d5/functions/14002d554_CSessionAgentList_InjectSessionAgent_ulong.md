# CSessionAgentList::InjectSessionAgent(ulong)

- ea: `0x14002d554`
- end: `0x14002d969`
- name: `?InjectSessionAgent@CSessionAgentList@@QEAAJK@Z`
- size: `1045`
- prototype: `__int64 __fastcall(CSessionAgentList *this, DWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140018154`
- `0x140020100`
- `0x1400221e0`
- `0x14002db34`

## callees

- `0x1400282a8`
- `0x14002d554`
- `0x14002e384`
- `0x14002e718`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140066fe8`
- `0x1400733b0`
- `0x140076348`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14002d6ae`
- `ADVAPI32!OpenProcessToken` at `0x14002d6ae`
- `ADVAPI32!DuplicateTokenEx` at `0x14002d795`
- `ADVAPI32!DuplicateTokenEx` at `0x14002d795`
- `ADVAPI32!SetTokenInformation` at `0x14002d803`
- `ADVAPI32!SetTokenInformation` at `0x14002d803`
- `ADVAPI32!CreateProcessAsUserW` at `0x14002d8bf`
- `ADVAPI32!CreateProcessAsUserW` at `0x14002d8bf`
- `KERNEL32!CloseHandle` at `0x14002d8ea`
- `KERNEL32!CloseHandle` at `0x14002d8f4`
- `KERNEL32!CloseHandle` at `0x14002d909`
- `KERNEL32!CloseHandle` at `0x14002d923`
- `KERNEL32!CloseHandle` at `0x14002d8ea`
- `KERNEL32!CloseHandle` at `0x14002d8f4`
- `KERNEL32!CloseHandle` at `0x14002d909`
- `KERNEL32!CloseHandle` at `0x14002d923`
- `KERNEL32!GetLastError` at `0x14002d6bc`
- `KERNEL32!GetLastError` at `0x14002d79f`
- `KERNEL32!GetLastError` at `0x14002d7d2`
- `KERNEL32!GetLastError` at `0x14002d80d`
- `KERNEL32!GetLastError` at `0x14002d8c9`
- `KERNEL32!GetLastError` at `0x14002d6bc`
- `KERNEL32!GetLastError` at `0x14002d79f`
- `KERNEL32!GetLastError` at `0x14002d7d2`
- `KERNEL32!GetLastError` at `0x14002d80d`
- `KERNEL32!GetLastError` at `0x14002d8c9`
- `KERNEL32!IsDebuggerPresent` at `0x14002d716`
- `KERNEL32!IsDebuggerPresent` at `0x14002d716`
- `KERNEL32!GetCurrentProcess` at `0x14002d69b`
- `KERNEL32!GetCurrentProcess` at `0x14002d69b`
- `USERENV!DestroyEnvironmentBlock` at `0x14002d937`
- `USERENV!DestroyEnvironmentBlock` at `0x14002d937`
- `USERENV!CreateEnvironmentBlock` at `0x14002d7c8`
- `USERENV!CreateEnvironmentBlock` at `0x14002d7c8`

## string_xrefs

- `0x14002d863`: `WmsSessionAgent.exe`
- `0x14002d617`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002d6ec`: `termsrv\wms\src\devices\wmssvc\sessionagentlist.cpp`
- `0x14002d5cc`: `CSessionAgentList::InjectSessionAgent - idSession = %lu.\n`
- `0x14002d610`: `CSessionAgentList::InjectSessionAgent`
- `0x14002d6e2`: `CSessionAgentList::InjectSessionAgent`
- `0x14002d5fe`: `Not injecting agent into worker session.`
- `0x14002d67a`: `Not injecting agent into WmsShell session.`

## pseudocode

```c
__int64 __fastcall CSessionAgentList::InjectSessionAgent(CSessionAgentList *this, DWORD a2)
{
  int SessionType; // eax
  int *v5; // rdx
  int IsWmsShellSession; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // r9
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v11; // r13d
  unsigned int v12; // edx
  DWORD dwCreationFlags[2]; // [rsp+30h] [rbp-D0h]
  LPVOID lpEnvironment; // [rsp+38h] [rbp-C8h]
  DWORD TokenInformation; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  int v18; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+74h] [rbp-8Ch] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  LPVOID Environment; // [rsp+80h] [rbp-80h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-78h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ApplicationName[264]; // [rsp+110h] [rbp+10h] BYREF

  TokenInformation = a2;
  hToken = 0;
  TokenHandle = 0;
  Environment = 0;
  memset_0(ApplicationName, 0, 0x208u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v19 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  DEBUGMSG(L"CSessionAgentList::InjectSessionAgent - idSession = %lu.\n", a2);
  SessionType = GetSessionType(TokenInformation);
  switch ( SessionType )
  {
    case 0:
      IsWmsShellSession = -2147467259;
      goto LABEL_40;
    case 6:
      v7 = L"Not injecting agent into worker session.";
      v8 = 916;
LABEL_5:
      IsWmsShellSession = 0;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        v8,
        L"CSessionAgentList::InjectSessionAgent",
        v7);
      goto LABEL_40;
    case 1:
      v18 = 0;
      PlatformSkuUtils::IsRole((PlatformSkuUtils *)&v18, v5);
      if ( v18 )
      {
        IsWmsShellSession = CEventNotificationService::s_IsWmsShellSession(TokenInformation, &v19);
        if ( IsWmsShellSession < 0 )
          goto LABEL_40;
        if ( v19 )
        {
          v7 = L"Not injecting agent into WmsShell session.";
          v8 = 923;
          goto LABEL_5;
        }
      }
      break;
  }
  IsWmsShellSession = CSessionAgentList::StartWebLimitingDriver(this);
  if ( IsWmsShellSession >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xBu, &TokenHandle) )
    {
      if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityIdentification, TokenPrimary, &hToken) )
      {
        if ( CreateEnvironmentBlock(&Environment, hToken, 0) )
        {
          if ( SetTokenInformation(hToken, TokenSessionId, &TokenInformation, 4u) )
          {
            memset_0(&StartupInfo, 0, sizeof(StartupInfo));
            StartupInfo.cb = 104;
            StartupInfo.wShowWindow = 5;
            StartupInfo.lpDesktop = L"Winsta0\\Default";
            IsWmsShellSession = GetModulePath(ApplicationName, v12);
            if ( IsWmsShellSession < 0 )
              goto LABEL_40;
            IsWmsShellSession = StringCchCatW(ApplicationName, 0x104u, L"WmsSessionAgent.exe");
            if ( IsWmsShellSession < 0 )
              goto LABEL_40;
            if ( CreateProcessAsUserW(
                   hToken,
                   ApplicationName,
                   0,
                   0,
                   0,
                   0,
                   0x400u,
                   Environment,
                   0,
                   &StartupInfo,
                   &ProcessInformation) )
            {
              CloseHandle(ProcessInformation.hThread);
              CloseHandle(ProcessInformation.hProcess);
              goto LABEL_40;
            }
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v11 = 974;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v11 = 947;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v11 = 939;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v11 = 935;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = 931;
    }
    if ( LastError >= 0 )
      LastError = -2147467259;
    IsWmsShellSession = LastError;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
      v11,
      L"CSessionAgentList::InjectSessionAgent",
      L"CBRAEx",
      L"fSuccess",
      LastError);
    if ( IsDebuggerPresent() )
    {
      LODWORD(lpEnvironment) = IsWmsShellSession;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        v11,
        L"CSessionAgentList::InjectSessionAgent",
        L"CBRAEx",
        L"fSuccess",
        lpEnvironment);
    }
    else
    {
      dwCreationFlags[0] = IsWmsShellSession;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\sessionagentlist.cpp",
        v11,
        L"CSessionAgentList::InjectSessionAgent",
        L"CBRAEx",
        L"fSuccess",
        *(_QWORD *)dwCreationFlags);
    }
  }
LABEL_40:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  return (unsigned int)IsWmsShellSession;
}

```

## disassembly

```asm
0x14002d554  mov     [rsp-8+arg_10], rbx
0x14002d559  push    rbp
0x14002d55a  push    rsi
0x14002d55b  push    rdi
0x14002d55c  push    r12
0x14002d55e  push    r13
0x14002d560  push    r14
0x14002d562  push    r15
0x14002d564  lea     rbp, [rsp-230h]
0x14002d56c  sub     rsp, 330h
0x14002d573  mov     rax, cs:__security_cookie
0x14002d57a  xor     rax, rsp
0x14002d57d  mov     [rbp+260h+var_40], rax
0x14002d584  xor     r12d, r12d
0x14002d587  mov     [rsp+360h+TokenInformation], edx
0x14002d58b  mov     ebx, edx
0x14002d58d  mov     [rsp+360h+hToken], r12
0x14002d592  mov     rdi, rcx
0x14002d595  mov     [rsp+360h+TokenHandle], r12
0x14002d59a  xor     edx, edx; Val
0x14002d59c  mov     [rbp+260h+Environment], r12
0x14002d5a0  lea     rcx, [rbp+260h+ApplicationName]; void *
0x14002d5a4  mov     r8d, 208h; Size
0x14002d5aa  call    memset_0
0x14002d5af  lea     r14d, [r12+68h]
0x14002d5b4  xor     edx, edx; Val
0x14002d5b6  mov     r8d, r14d; Size
0x14002d5b9  lea     rcx, [rbp+260h+StartupInfo]; void *
0x14002d5bd  call    memset_0
0x14002d5c2  xorps   xmm0, xmm0
0x14002d5c5  mov     [rsp+360h+var_2EC], r12d
0x14002d5ca  xor     eax, eax
0x14002d5cc  lea     rcx, aCsessionagentl_33; "CSessionAgentList::InjectSessionAgent -"...
0x14002d5d3  mov     edx, ebx
0x14002d5d5  mov     qword ptr [rbp+260h+ProcessInformation.dwProcessId], rax
0x14002d5d9  movups  xmmword ptr [rbp+260h+ProcessInformation.hProcess], xmm0
0x14002d5dd  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002d5e2  mov     ecx, [rsp+360h+TokenInformation]
0x14002d5e6  call    ?GetSessionType@@YA?AW4ESessionType@@K@Z; GetSessionType(ulong)
0x14002d5eb  test    eax, eax
0x14002d5ed  jnz     short loc_14002D5F9
0x14002d5ef  mov     ebx, 80004005h
0x14002d5f4  jmp     loc_14002D8FA
0x14002d5f9  cmp     eax, 6
0x14002d5fc  jnz     short loc_14002D63C
0x14002d5fe  lea     rax, aNotInjectingAg_0; "Not injecting agent into worker session"...
0x14002d605  mov     r9d, 394h
0x14002d60b  mov     [rsp+360h+phNewToken], rax
0x14002d610  lea     rsi, aCsessionagentl_0; "CSessionAgentList::InjectSessionAgent"
0x14002d617  lea     r8, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002d61e  mov     qword ptr [rsp+360h+TokenType], rsi
0x14002d623  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14002d62a  mov     ecx, 4; unsigned __int8
0x14002d62f  mov     ebx, r12d
0x14002d632  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002d637  jmp     loc_14002D8FA
0x14002d63c  mov     esi, 1
0x14002d641  cmp     eax, esi
0x14002d643  jnz     short loc_14002D689
0x14002d645  lea     rcx, [rsp+360h+var_2F0]; this
0x14002d64a  mov     [rsp+360h+var_2F0], r12d
0x14002d64f  call    ?IsRole@PlatformSkuUtils@@YAJPEAH@Z; PlatformSkuUtils::IsRole(int *)
0x14002d654  cmp     [rsp+360h+var_2F0], r12d
0x14002d659  jz      short loc_14002D689
0x14002d65b  mov     ecx, [rsp+360h+TokenInformation]; SessionId
0x14002d65f  lea     rdx, [rsp+360h+var_2EC]; int *
0x14002d664  call    ?s_IsWmsShellSession@CEventNotificationService@@SAJKPEAH@Z; CEventNotificationService::s_IsWmsShellSession(ulong,int *)
0x14002d669  mov     ebx, eax
0x14002d66b  test    eax, eax
0x14002d66d  js      loc_14002D8FA
0x14002d673  cmp     [rsp+360h+var_2EC], r12d
0x14002d678  jz      short loc_14002D689
0x14002d67a  lea     rax, aNotInjectingAg; "Not injecting agent into WmsShell sessi"...
0x14002d681  mov     r9d, 39Bh
0x14002d687  jmp     short loc_14002D60B
0x14002d689  mov     rcx, rdi; this
0x14002d68c  call    ?StartWebLimitingDriver@CSessionAgentList@@AEAAJXZ; CSessionAgentList::StartWebLimitingDriver(void)
0x14002d691  mov     ebx, eax
0x14002d693  test    eax, eax
0x14002d695  js      loc_14002D8FA
0x14002d69b  call    cs:__imp_GetCurrentProcess
0x14002d6a1  lea     r8, [rsp+360h+TokenHandle]; TokenHandle
0x14002d6a6  mov     edx, 0Bh; DesiredAccess
0x14002d6ab  mov     rcx, rax; ProcessHandle
0x14002d6ae  call    cs:__imp_OpenProcessToken
0x14002d6b4  test    eax, eax
0x14002d6b6  jnz     loc_14002D777
0x14002d6bc  call    cs:__imp_GetLastError
0x14002d6c2  test    eax, eax
0x14002d6c4  jle     short loc_14002D6CE
0x14002d6c6  movzx   eax, ax
0x14002d6c9  or      eax, 80070000h
0x14002d6ce  mov     r13d, 3A3h
0x14002d6d4  test    eax, eax
0x14002d6d6  lea     r15, aCbraex; "CBRAEx"
0x14002d6dd  mov     ebx, 80004005h
0x14002d6e2  lea     rsi, aCsessionagentl_0; "CSessionAgentList::InjectSessionAgent"
0x14002d6e9  cmovns  eax, ebx
0x14002d6ec  lea     rdi, aTermsrvWmsSrcD_19; "termsrv\\wms\\src\\devices\\wmssvc\\ses"...
0x14002d6f3  mov     dword ptr [rsp+360h+phNewToken], eax; int
0x14002d6f7  lea     r14, aFsuccess; "fSuccess"
0x14002d6fe  mov     r9, r15; unsigned __int16 *
0x14002d701  mov     qword ptr [rsp+360h+TokenType], r14; unsigned __int16 *
0x14002d706  mov     r8, rsi; unsigned __int16 *
0x14002d709  mov     edx, r13d; unsigned int
0x14002d70c  mov     rcx, rdi; unsigned __int16 *
0x14002d70f  mov     ebx, eax
0x14002d711  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002d716  call    cs:__imp_IsDebuggerPresent
0x14002d71c  test    eax, eax
0x14002d71e  jz      short loc_14002D74F
0x14002d720  mov     dword ptr [rsp+360h+lpEnvironment], ebx
0x14002d724  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002d72b  mov     qword ptr [rsp+360h+dwCreationFlags], r14
0x14002d730  mov     r9d, r13d
0x14002d733  mov     [rsp+360h+phNewToken], r15
0x14002d738  mov     r8, rdi
0x14002d73b  mov     ecx, 2; unsigned __int8
0x14002d740  mov     qword ptr [rsp+360h+TokenType], rsi
0x14002d745  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002d74a  jmp     loc_14002D8FA
0x14002d74f  mov     [rsp+360h+dwCreationFlags], ebx
0x14002d753  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002d75a  mov     [rsp+360h+phNewToken], r14
0x14002d75f  mov     r9, rsi
0x14002d762  mov     r8d, r13d
0x14002d765  mov     qword ptr [rsp+360h+TokenType], r15
0x14002d76a  mov     rdx, rdi
0x14002d76d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002d772  jmp     loc_14002D8FA
0x14002d777  mov     rcx, [rsp+360h+TokenHandle]; hExistingToken
0x14002d77c  lea     rax, [rsp+360h+hToken]
0x14002d781  mov     [rsp+360h+phNewToken], rax; phNewToken
0x14002d786  mov     r9d, esi; ImpersonationLevel
0x14002d789  xor     r8d, r8d; lpTokenAttributes
0x14002d78c  mov     [rsp+360h+TokenType], esi; TokenType
0x14002d790  mov     edx, 2000000h; dwDesiredAccess
0x14002d795  call    cs:__imp_DuplicateTokenEx
0x14002d79b  test    eax, eax
0x14002d79d  jnz     short loc_14002D7BC
0x14002d79f  call    cs:__imp_GetLastError
0x14002d7a5  test    eax, eax
0x14002d7a7  jle     short loc_14002D7B1
0x14002d7a9  movzx   eax, ax
0x14002d7ac  or      eax, 80070000h
0x14002d7b1  mov     r13d, 3A7h
0x14002d7b7  jmp     loc_14002D6D4
0x14002d7bc  mov     rdx, [rsp+360h+hToken]; hToken
0x14002d7c1  lea     rcx, [rbp+260h+Environment]; lpEnvironment
0x14002d7c5  xor     r8d, r8d; bInherit
0x14002d7c8  call    cs:__imp_CreateEnvironmentBlock
0x14002d7ce  test    eax, eax
0x14002d7d0  jnz     short loc_14002D7EF
0x14002d7d2  call    cs:__imp_GetLastError
0x14002d7d8  test    eax, eax
0x14002d7da  jle     short loc_14002D7E4
0x14002d7dc  movzx   eax, ax
0x14002d7df  or      eax, 80070000h
0x14002d7e4  mov     r13d, 3ABh
0x14002d7ea  jmp     loc_14002D6D4
0x14002d7ef  mov     rcx, [rsp+360h+hToken]; TokenHandle
0x14002d7f4  lea     r8, [rsp+360h+TokenInformation]; TokenInformation
0x14002d7f9  mov     r9d, 4; TokenInformationLength
0x14002d7ff  lea     edx, [r9+8]; TokenInformationClass
0x14002d803  call    cs:__imp_SetTokenInformation
0x14002d809  test    eax, eax
0x14002d80b  jnz     short loc_14002D82A
0x14002d80d  call    cs:__imp_GetLastError
0x14002d813  test    eax, eax
0x14002d815  jle     short loc_14002D81F
0x14002d817  movzx   eax, ax
0x14002d81a  or      eax, 80070000h
0x14002d81f  mov     r13d, 3B3h
0x14002d825  jmp     loc_14002D6D4
0x14002d82a  mov     r8, r14; Size
0x14002d82d  lea     rcx, [rbp+260h+StartupInfo]; void *
0x14002d831  xor     edx, edx; Val
0x14002d833  call    memset_0
0x14002d838  mov     eax, 5
0x14002d83d  mov     [rbp+260h+StartupInfo.cb], r14d
0x14002d841  mov     [rbp+260h+StartupInfo.wShowWindow], ax
0x14002d845  lea     rcx, [rbp+260h+ApplicationName]; Str
0x14002d849  lea     rax, aWinsta0Default; "Winsta0\\Default"
0x14002d850  mov     [rbp+260h+StartupInfo.lpDesktop], rax
0x14002d854  call    ?GetModulePath@@YAJPEAGK@Z; GetModulePath(ushort *,ulong)
0x14002d859  mov     ebx, eax
0x14002d85b  test    eax, eax
0x14002d85d  js      loc_14002D8FA
0x14002d863  lea     r8, aWmssessionagen; "WmsSessionAgent.exe"
0x14002d86a  mov     edx, 104h; unsigned __int64
0x14002d86f  lea     rcx, [rbp+260h+ApplicationName]; unsigned __int16 *
0x14002d873  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002d878  mov     ebx, eax
0x14002d87a  test    eax, eax
0x14002d87c  js      short loc_14002D8FA
0x14002d87e  mov     rcx, [rsp+360h+hToken]; hToken
0x14002d883  lea     rax, [rbp+260h+ProcessInformation]
0x14002d887  mov     [rsp+360h+lpProcessInformation], rax; lpProcessInformation
0x14002d88c  lea     rdx, [rbp+260h+ApplicationName]; lpApplicationName
0x14002d890  lea     rax, [rbp+260h+StartupInfo]
0x14002d894  xor     r9d, r9d; lpProcessAttributes
0x14002d897  mov     [rsp+360h+lpStartupInfo], rax; lpStartupInfo
0x14002d89c  xor     r8d, r8d; lpCommandLine
0x14002d89f  mov     rax, [rbp+260h+Environment]
0x14002d8a3  mov     [rsp+360h+lpCurrentDirectory], r12; lpCurrentDirectory
0x14002d8a8  mov     [rsp+360h+lpEnvironment], rax; lpEnvironment
0x14002d8ad  mov     [rsp+360h+dwCreationFlags], 400h; dwCreationFlags
0x14002d8b5  mov     dword ptr [rsp+360h+phNewToken], r12d; bInheritHandles
0x14002d8ba  mov     qword ptr [rsp+360h+TokenType], r12; lpThreadAttributes
0x14002d8bf  call    cs:__imp_CreateProcessAsUserW
0x14002d8c5  test    eax, eax
0x14002d8c7  jnz     short loc_14002D8E6
0x14002d8c9  call    cs:__imp_GetLastError
0x14002d8cf  test    eax, eax
0x14002d8d1  jle     short loc_14002D8DB
0x14002d8d3  movzx   eax, ax
0x14002d8d6  or      eax, 80070000h
0x14002d8db  mov     r13d, 3CEh
0x14002d8e1  jmp     loc_14002D6D4
0x14002d8e6  mov     rcx, [rbp+260h+ProcessInformation.hThread]; hObject
0x14002d8ea  call    cs:__imp_CloseHandle
0x14002d8f0  mov     rcx, [rbp+260h+ProcessInformation.hProcess]; hObject
0x14002d8f4  call    cs:__imp_CloseHandle
0x14002d8fa  mov     rcx, [rsp+360h+TokenHandle]; hObject
0x14002d8ff  lea     rax, [rcx-1]
0x14002d903  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002d907  ja      short loc_14002D914
0x14002d909  call    cs:__imp_CloseHandle
0x14002d90f  mov     [rsp+360h+TokenHandle], r12
0x14002d914  mov     rcx, [rsp+360h+hToken]; hObject
0x14002d919  lea     rax, [rcx-1]
0x14002d91d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002d921  ja      short loc_14002D92E
0x14002d923  call    cs:__imp_CloseHandle
0x14002d929  mov     [rsp+360h+hToken], r12
0x14002d92e  mov     rcx, [rbp+260h+Environment]; lpEnvironment
0x14002d932  test    rcx, rcx
0x14002d935  jz      short loc_14002D93D
0x14002d937  call    cs:__imp_DestroyEnvironmentBlock
0x14002d93d  mov     eax, ebx
0x14002d93f  mov     rcx, [rbp+260h+var_40]
0x14002d946  xor     rcx, rsp; StackCookie
0x14002d949  call    __security_check_cookie
0x14002d94e  mov     rbx, [rsp+360h+arg_10]
0x14002d956  add     rsp, 330h
0x14002d95d  pop     r15
0x14002d95f  pop     r14
0x14002d961  pop     r13
0x14002d963  pop     r12
0x14002d965  pop     rdi
0x14002d966  pop     rsi
0x14002d967  pop     rbp
0x14002d968  retn
```

# LaunchDmDesktopUI(ushort *)

- ea: `0x1800074dc`
- end: `0x18000780e`
- name: `?LaunchDmDesktopUI@@YAJPEAG@Z`
- size: `818`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007880`
- `0x180007a40`

## callees

- `0x1800074dc`
- `0x180007b4c`
- `0x180007c8c`
- `0x180009efe`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007626`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007754`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180007744`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180007744`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000772a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000772a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180007681`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180007681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000778f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000778f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077d6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800075d6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800075d6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800076c3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800076c3`
- `USERENV!CreateEnvironmentBlock` at `0x180007608`
- `USERENV!CreateEnvironmentBlock` at `0x180007608`
- `USERENV!DestroyEnvironmentBlock` at `0x180007779`
- `USERENV!DestroyEnvironmentBlock` at `0x180007779`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077e7`
- `DMCmnUtils!DmImpersonate` at `0x1800075a0`
- `DMCmnUtils!DmImpersonate` at `0x1800075a0`
- `DMCmnUtils!DmRevertToSelf` at `0x1800077b5`
- `DMCmnUtils!DmRevertToSelf` at `0x1800077b5`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180007546`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180007546`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180007562`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180007562`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x180007585`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x180007585`

## pseudocode

```c
__int64 __fastcall LaunchDmDesktopUI(LPWSTR lpCommandLine)
{
  signed int IsRunningInSystemContext; // ebx
  BOOL v3; // eax
  DWORD v4; // eax
  signed int LastError; // eax
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID Environment; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hExistingToken; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handles[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  int v13; // [rsp+138h] [rbp+38h] BYREF
  DWORD ExitCode; // [rsp+140h] [rbp+40h] BYREF
  HANDLE hToken; // [rsp+148h] [rbp+48h] BYREF

  hExistingToken = 0;
  hToken = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  hMem = 0;
  Environment = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)Handles = 0;
  ExitCode = 0;
  IsRunningInSystemContext = RegisterDmUiRPCInterface();
  if ( IsRunningInSystemContext < 0 )
    goto LABEL_20;
  v13 = 1;
  IsRunningInSystemContext = DmIsRunningInSystemContext(&v13);
  if ( v13 )
  {
    IsRunningInSystemContext = DmGetActiveUserSid((unsigned __int16 **)&hMem);
    if ( IsRunningInSystemContext < 0 )
      goto LABEL_20;
    IsRunningInSystemContext = DmGetUserTokenFromSid((const unsigned __int16 *)hMem, &hExistingToken, 0);
    if ( IsRunningInSystemContext < 0 )
      goto LABEL_20;
    IsRunningInSystemContext = DmImpersonate((const unsigned __int16 *)hMem);
    if ( IsRunningInSystemContext < 0 )
      goto LABEL_20;
    if ( !DuplicateTokenEx(hExistingToken, 0xBu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
      goto LABEL_18;
    StartupInfo.lpDesktop = L"WinSta0\\Default";
    StartupInfo.cb = 104;
    if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
      goto LABEL_18;
    g_hUserInputReceivedEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_hUserInputReceivedEvent )
      goto LABEL_18;
    v3 = CreateProcessAsUserW(
           hToken,
           0,
           lpCommandLine,
           0,
           0,
           0,
           0x400u,
           Environment,
           0,
           &StartupInfo,
           &ProcessInformation);
  }
  else
  {
    v3 = CreateProcessW(0, lpCommandLine, 0, 0, 0, 0x400u, 0, 0, &StartupInfo, &ProcessInformation);
  }
  if ( v3 )
  {
    Handles[0] = ProcessInformation.hProcess;
    Handles[1] = g_hUserInputReceivedEvent;
    g_ClientProcessID = ProcessInformation.dwProcessId;
    v4 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v4 )
    {
      if ( v4 != 1 && v4 != 258 && v4 != -1 )
        IsRunningInSystemContext = -2147418113;
      goto LABEL_20;
    }
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      goto LABEL_20;
  }
LABEL_18:
  LastError = GetLastError();
  IsRunningInSystemContext = LastError;
  if ( LastError > 0 )
    IsRunningInSystemContext = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  g_ClientProcessID = 0;
  CloseHandle(ProcessInformation.hThread);
  CloseHandle(g_hUserInputReceivedEvent);
  g_hUserInputReceivedEvent = 0;
  DmRevertToSelf();
  CloseHandle(hExistingToken);
  CloseHandle(hToken);
  LocalFree(hMem);
  UnregisterDmUiRPCInterface();
  return (unsigned int)IsRunningInSystemContext;
}

```

## disassembly

```asm
0x1800074dc  mov     [rsp-8+arg_0], rbx
0x1800074e1  push    rbp
0x1800074e2  push    rsi
0x1800074e3  push    rdi
0x1800074e4  lea     rbp, [rsp-10h]
0x1800074e9  sub     rsp, 110h
0x1800074f0  xor     esi, esi
0x1800074f2  mov     rdi, rcx
0x1800074f5  xor     edx, edx; Val
0x1800074f7  mov     [rsp+120h+hExistingToken], rsi
0x1800074fc  lea     rcx, [rbp+20h+StartupInfo]; void *
0x180007500  mov     [rbp+20h+hToken], rsi
0x180007504  lea     r8d, [rsi+68h]; Size
0x180007508  call    memset_0
0x18000750d  xorps   xmm0, xmm0
0x180007510  mov     [rsp+120h+hMem], rsi
0x180007515  xor     eax, eax
0x180007517  mov     [rsp+120h+Environment], rsi
0x18000751c  movups  xmmword ptr [rsp+120h+ProcessInformation.hProcess], xmm0
0x180007521  mov     qword ptr [rbp+20h+ProcessInformation.dwProcessId], rax
0x180007525  movups  xmmword ptr [rbp+20h+Handles], xmm0
0x180007529  mov     [rbp+20h+ExitCode], esi
0x18000752c  call    ?RegisterDmUiRPCInterface@@YAJXZ; RegisterDmUiRPCInterface(void)
0x180007531  mov     ebx, eax
0x180007533  test    eax, eax
0x180007535  js      loc_18000776F
0x18000753b  lea     rcx, [rbp+20h+arg_8]
0x18000753f  mov     [rbp+20h+arg_8], 1
0x180007546  call    cs:__imp_?DmIsRunningInSystemContext@@YAJPEAH@Z; DmIsRunningInSystemContext(int *)
0x18000754d  nop     dword ptr [rax+rax+00h]
0x180007552  mov     ebx, eax
0x180007554  cmp     [rbp+20h+arg_8], esi
0x180007557  jz      loc_1800076F6
0x18000755d  lea     rcx, [rsp+120h+hMem]
0x180007562  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180007569  nop     dword ptr [rax+rax+00h]
0x18000756e  mov     ebx, eax
0x180007570  test    eax, eax
0x180007572  js      loc_18000776F
0x180007578  mov     rcx, [rsp+120h+hMem]
0x18000757d  lea     rdx, [rsp+120h+hExistingToken]
0x180007582  xor     r8d, r8d
0x180007585  call    cs:__imp_?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z; DmGetUserTokenFromSid(ushort const *,void * *,ulong *)
0x18000758c  nop     dword ptr [rax+rax+00h]
0x180007591  mov     ebx, eax
0x180007593  test    eax, eax
0x180007595  js      loc_18000776F
0x18000759b  mov     rcx, [rsp+120h+hMem]
0x1800075a0  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1800075a7  nop     dword ptr [rax+rax+00h]
0x1800075ac  mov     ebx, eax
0x1800075ae  test    eax, eax
0x1800075b0  js      loc_18000776F
0x1800075b6  mov     rcx, [rsp+120h+hExistingToken]; hExistingToken
0x1800075bb  lea     rax, [rbp+20h+hToken]
0x1800075bf  mov     [rsp+120h+phNewToken], rax; phNewToken
0x1800075c4  lea     r9d, [rsi+2]; ImpersonationLevel
0x1800075c8  xor     r8d, r8d; lpTokenAttributes
0x1800075cb  mov     [rsp+120h+TokenType], 1; TokenType
0x1800075d3  lea     edx, [rsi+0Bh]; dwDesiredAccess
0x1800075d6  call    cs:__imp_DuplicateTokenEx
0x1800075dd  nop     dword ptr [rax+rax+00h]
0x1800075e2  test    eax, eax
0x1800075e4  jz      loc_180007754
0x1800075ea  mov     rdx, [rbp+20h+hToken]; hToken
0x1800075ee  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x1800075f5  xor     r8d, r8d; bInherit
0x1800075f8  mov     [rbp+20h+StartupInfo.lpDesktop], rax
0x1800075fc  lea     rcx, [rsp+120h+Environment]; lpEnvironment
0x180007601  mov     [rbp+20h+StartupInfo.cb], 68h ; 'h'
0x180007608  call    cs:__imp_CreateEnvironmentBlock
0x18000760f  nop     dword ptr [rax+rax+00h]
0x180007614  test    eax, eax
0x180007616  jz      loc_180007754
0x18000761c  xor     r9d, r9d; lpName
0x18000761f  xor     r8d, r8d; bInitialState
0x180007622  xor     edx, edx; bManualReset
0x180007624  xor     ecx, ecx; lpEventAttributes
0x180007626  call    cs:__imp_CreateEventW
0x18000762d  nop     dword ptr [rax+rax+00h]
0x180007632  mov     cs:?g_hUserInputReceivedEvent@@3PEAXEA, rax; void * g_hUserInputReceivedEvent
0x180007639  test    rax, rax
0x18000763c  jz      loc_180007754
0x180007642  mov     rcx, [rbp+20h+hToken]; hToken
0x180007646  lea     rax, [rsp+120h+ProcessInformation]
0x18000764b  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x180007650  xor     r9d, r9d; lpProcessAttributes
0x180007653  lea     rax, [rbp+20h+StartupInfo]
0x180007657  mov     r8, rdi; lpCommandLine
0x18000765a  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x18000765f  xor     edx, edx; lpApplicationName
0x180007661  mov     rax, [rsp+120h+Environment]
0x180007666  mov     [rsp+120h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x18000766b  mov     [rsp+120h+lpEnvironment], rax; lpEnvironment
0x180007670  mov     [rsp+120h+dwCreationFlags], 400h; dwCreationFlags
0x180007678  mov     dword ptr [rsp+120h+phNewToken], esi; bInheritHandles
0x18000767c  mov     qword ptr [rsp+120h+TokenType], rsi; lpThreadAttributes
0x180007681  call    cs:__imp_CreateProcessAsUserW
0x180007688  nop     dword ptr [rax+rax+00h]
0x18000768d  test    eax, eax
0x18000768f  jz      loc_180007754
0x180007695  mov     rax, [rsp+120h+ProcessInformation.hProcess]
0x18000769a  lea     rdx, [rbp+20h+Handles]; lpHandles
0x18000769e  mov     [rbp+20h+Handles], rax
0x1800076a2  xor     r8d, r8d; bWaitAll
0x1800076a5  mov     rax, cs:?g_hUserInputReceivedEvent@@3PEAXEA; void * g_hUserInputReceivedEvent
0x1800076ac  or      edi, 0FFFFFFFFh
0x1800076af  mov     [rbp+20h+Handles+8], rax
0x1800076b3  mov     r9d, edi; dwMilliseconds
0x1800076b6  mov     eax, [rbp+20h+ProcessInformation.dwProcessId]
0x1800076b9  lea     ecx, [r8+2]; nCount
0x1800076bd  mov     cs:?g_ClientProcessID@@3KA, eax; ulong g_ClientProcessID
0x1800076c3  call    cs:__imp_WaitForMultipleObjects
0x1800076ca  nop     dword ptr [rax+rax+00h]
0x1800076cf  test    eax, eax
0x1800076d1  jz      short loc_18000773B
0x1800076d3  cmp     eax, 1
0x1800076d6  jz      loc_18000776F
0x1800076dc  cmp     eax, 102h
0x1800076e1  jz      loc_18000776F
0x1800076e7  cmp     eax, edi
0x1800076e9  jz      loc_18000776F
0x1800076ef  mov     ebx, 8000FFFFh
0x1800076f4  jmp     short loc_18000776F
0x1800076f6  lea     rax, [rsp+120h+ProcessInformation]
0x1800076fb  xor     r9d, r9d; lpThreadAttributes
0x1800076fe  mov     [rsp+120h+lpStartupInfo], rax; lpProcessInformation
0x180007703  xor     r8d, r8d; lpProcessAttributes
0x180007706  lea     rax, [rbp+20h+StartupInfo]
0x18000770a  mov     rdx, rdi; lpCommandLine
0x18000770d  mov     [rsp+120h+lpCurrentDirectory], rax; lpStartupInfo
0x180007712  xor     ecx, ecx; lpApplicationName
0x180007714  mov     [rsp+120h+lpEnvironment], rsi; lpCurrentDirectory
0x180007719  mov     qword ptr [rsp+120h+dwCreationFlags], rsi; lpEnvironment
0x18000771e  mov     dword ptr [rsp+120h+phNewToken], 400h; dwCreationFlags
0x180007726  mov     [rsp+120h+TokenType], esi; bInheritHandles
0x18000772a  call    cs:__imp_CreateProcessW
0x180007731  nop     dword ptr [rax+rax+00h]
0x180007736  jmp     loc_18000768D
0x18000773b  mov     rcx, [rsp+120h+ProcessInformation.hProcess]; hProcess
0x180007740  lea     rdx, [rbp+20h+ExitCode]; lpExitCode
0x180007744  call    cs:__imp_GetExitCodeProcess
0x18000774b  nop     dword ptr [rax+rax+00h]
0x180007750  test    eax, eax
0x180007752  jnz     short loc_18000776F
0x180007754  call    cs:__imp_GetLastError
0x18000775b  nop     dword ptr [rax+rax+00h]
0x180007760  mov     ebx, eax
0x180007762  test    eax, eax
0x180007764  jle     short loc_18000776F
0x180007766  movzx   ebx, ax
0x180007769  or      ebx, 80070000h
0x18000776f  mov     rcx, [rsp+120h+Environment]; lpEnvironment
0x180007774  test    rcx, rcx
0x180007777  jz      short loc_180007785
0x180007779  call    cs:__imp_DestroyEnvironmentBlock
0x180007780  nop     dword ptr [rax+rax+00h]
0x180007785  mov     rcx, [rbp+20h+ProcessInformation.hThread]; hObject
0x180007789  mov     cs:?g_ClientProcessID@@3KA, esi; ulong g_ClientProcessID
0x18000778f  call    cs:__imp_CloseHandle
0x180007796  nop     dword ptr [rax+rax+00h]
0x18000779b  mov     rcx, cs:?g_hUserInputReceivedEvent@@3PEAXEA; hObject
0x1800077a2  call    cs:__imp_CloseHandle
0x1800077a9  nop     dword ptr [rax+rax+00h]
0x1800077ae  mov     cs:?g_hUserInputReceivedEvent@@3PEAXEA, rsi; void * g_hUserInputReceivedEvent
0x1800077b5  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1800077bc  nop     dword ptr [rax+rax+00h]
0x1800077c1  mov     rcx, [rsp+120h+hExistingToken]; hObject
0x1800077c6  call    cs:__imp_CloseHandle
0x1800077cd  nop     dword ptr [rax+rax+00h]
0x1800077d2  mov     rcx, [rbp+20h+hToken]; hObject
0x1800077d6  call    cs:__imp_CloseHandle
0x1800077dd  nop     dword ptr [rax+rax+00h]
0x1800077e2  mov     rcx, [rsp+120h+hMem]; hMem
0x1800077e7  call    cs:__imp_LocalFree
0x1800077ee  nop     dword ptr [rax+rax+00h]
0x1800077f3  call    ?UnregisterDmUiRPCInterface@@YAJXZ; UnregisterDmUiRPCInterface(void)
0x1800077f8  mov     eax, ebx
0x1800077fa  mov     rbx, [rsp+120h+arg_0]
0x180007802  add     rsp, 110h
0x180007809  pop     rdi
0x18000780a  pop     rsi
0x18000780b  pop     rbp
0x18000780c  retn
```

# _InitRestrictedProcess(void * *,void * *)

- ea: `0x18003a7b8`
- end: `0x18003a979`
- name: `?_InitRestrictedProcess@@YAJPEAPEAX0@Z`
- size: `449`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ddf0`
- `0x18003a730`

## callees

- `0x18003a7b8`
- `0x18003aa84`
- `0x180050ba0`
- `0x180051524`
- `0x1800d1390`
- `0x1800d14e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a882`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a882`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a81f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a81f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a80c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a80c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003a917`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003a917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a853`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a94a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a853`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a94a`

## pseudocode

```c
__int64 __fastcall _InitRestrictedProcess(void **a1, void **a2)
{
  HANDLE CurrentProcess; // rax
  int Error; // ebx
  const unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  HANDLE EventW; // rdi
  HANDLE hThread; // rcx
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR CommandLine[264]; // [rsp+100h] [rbp+0h] BYREF

  *a1 = 0;
  *a2 = 0;
  hToken = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x8Bu, &TokenHandle) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = _CreateRestrictedTokenFromSpecifiedToken((void *)0x2000, TokenHandle, &hToken);
    CloseHandle(TokenHandle);
    if ( Error >= 0 )
    {
      Error = _GetCommandLine(v6, CommandLine, v7);
      if ( Error >= 0 )
      {
        EventW = CreateEventW(0, 0, 0, L"22d8c27b-47a1-48d1-ad08-7da7abd79617");
        if ( EventW || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          *(_QWORD *)&StartupInfo.cb = 104;
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          memset_0(&StartupInfo.lpReserved, 0, 0x60u);
          StartupInfo.dwFlags = 128;
          if ( CreateProcessAsUserW(hToken, 0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            Error = 0;
LABEL_10:
            hThread = ProcessInformation.hThread;
            *a1 = ProcessInformation.hProcess;
            *a2 = EventW;
LABEL_13:
            CloseHandle(hThread);
            return (unsigned int)Error;
          }
          Error = ResultFromKnownLastError();
          if ( Error >= 0 )
            goto LABEL_10;
          if ( EventW )
          {
            hThread = EventW;
            goto LABEL_13;
          }
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003a7b8  mov     [rsp-8+arg_10], rbx
0x18003a7bd  mov     [rsp-8+arg_18], rsi
0x18003a7c2  push    rbp
0x18003a7c3  push    rdi
0x18003a7c4  push    r14
0x18003a7c6  lea     rbp, [rsp-220h]
0x18003a7ce  sub     rsp, 320h
0x18003a7d5  mov     rax, cs:__security_cookie
0x18003a7dc  xor     rax, rsp
0x18003a7df  mov     [rbp+230h+var_20], rax
0x18003a7e6  mov     qword ptr [rcx], 0
0x18003a7ed  mov     r14, rdx
0x18003a7f0  mov     qword ptr [rdx], 0
0x18003a7f7  mov     rsi, rcx
0x18003a7fa  mov     [rsp+330h+hToken], 0
0x18003a803  mov     [rsp+330h+TokenHandle], 0
0x18003a80c  call    cs:__imp_GetCurrentProcess
0x18003a812  lea     r8, [rsp+330h+TokenHandle]; TokenHandle
0x18003a817  mov     edx, 8Bh; DesiredAccess
0x18003a81c  mov     rcx, rax; ProcessHandle
0x18003a81f  call    cs:__imp_OpenProcessToken
0x18003a825  test    eax, eax
0x18003a827  jnz     short loc_18003A838
0x18003a829  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003a82e  mov     ebx, eax
0x18003a830  test    eax, eax
0x18003a832  js      loc_18003A950
0x18003a838  mov     rdx, [rsp+330h+TokenHandle]; ExistingTokenHandle
0x18003a83d  lea     r8, [rsp+330h+hToken]; void **
0x18003a842  mov     ecx, 2000h; nSubAuthority0
0x18003a847  call    ?_CreateRestrictedTokenFromSpecifiedToken@@YAJKPEAXPEAPEAX@Z; _CreateRestrictedTokenFromSpecifiedToken(ulong,void *,void * *)
0x18003a84c  mov     rcx, [rsp+330h+TokenHandle]; hObject
0x18003a851  mov     ebx, eax
0x18003a853  call    cs:__imp_CloseHandle
0x18003a859  test    ebx, ebx
0x18003a85b  js      loc_18003A950
0x18003a861  lea     rdx, [rbp+230h+CommandLine]; unsigned __int16 *
0x18003a865  call    ?_GetCommandLine@@YAJPEBGPEAGI@Z; _GetCommandLine(ushort const *,ushort *,uint)
0x18003a86a  mov     ebx, eax
0x18003a86c  test    eax, eax
0x18003a86e  js      loc_18003A950
0x18003a874  lea     r9, a22d8c27b47a148; "22d8c27b-47a1-48d1-ad08-7da7abd79617"
0x18003a87b  xor     r8d, r8d; bInitialState
0x18003a87e  xor     edx, edx; bManualReset
0x18003a880  xor     ecx, ecx; lpEventAttributes
0x18003a882  call    cs:__imp_CreateEventW
0x18003a888  mov     rdi, rax
0x18003a88b  test    rax, rax
0x18003a88e  jnz     short loc_18003A89F
0x18003a890  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003a895  mov     ebx, eax
0x18003a897  test    eax, eax
0x18003a899  js      loc_18003A950
0x18003a89f  xor     eax, eax
0x18003a8a1  mov     qword ptr [rbp+230h+StartupInfo.cb], 68h ; 'h'
0x18003a8a9  xorps   xmm0, xmm0
0x18003a8ac  mov     qword ptr [rbp+230h+ProcessInformation.dwProcessId], rax
0x18003a8b0  xor     edx, edx; Val
0x18003a8b2  lea     rcx, [rbp+230h+StartupInfo.lpReserved]; void *
0x18003a8b6  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x18003a8bb  lea     r8d, [rax+60h]; Size
0x18003a8bf  call    memset_0
0x18003a8c4  mov     rcx, [rsp+330h+hToken]; hToken
0x18003a8c9  lea     rax, [rsp+330h+ProcessInformation]
0x18003a8ce  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x18003a8d3  lea     r8, [rbp+230h+CommandLine]; lpCommandLine
0x18003a8d7  lea     rax, [rbp+230h+StartupInfo]
0x18003a8db  mov     [rbp+230h+StartupInfo.dwFlags], 80h
0x18003a8e2  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x18003a8e7  xor     r9d, r9d; lpProcessAttributes
0x18003a8ea  mov     [rsp+330h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18003a8f3  xor     edx, edx; lpApplicationName
0x18003a8f5  mov     [rsp+330h+lpEnvironment], 0; lpEnvironment
0x18003a8fe  mov     [rsp+330h+dwCreationFlags], 0; dwCreationFlags
0x18003a906  mov     [rsp+330h+bInheritHandles], 0; bInheritHandles
0x18003a90e  mov     [rsp+330h+lpThreadAttributes], 0; lpThreadAttributes
0x18003a917  call    cs:__imp_CreateProcessAsUserW
0x18003a91d  test    eax, eax
0x18003a91f  jz      short loc_18003A925
0x18003a921  xor     ebx, ebx
0x18003a923  jmp     short loc_18003A930
0x18003a925  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003a92a  mov     ebx, eax
0x18003a92c  test    eax, eax
0x18003a92e  js      short loc_18003A942
0x18003a930  mov     rax, [rsp+330h+ProcessInformation.hProcess]
0x18003a935  mov     rcx, [rsp+330h+ProcessInformation.hThread]
0x18003a93a  mov     [rsi], rax
0x18003a93d  mov     [r14], rdi
0x18003a940  jmp     short loc_18003A94A
0x18003a942  test    rdi, rdi
0x18003a945  jz      short loc_18003A950
0x18003a947  mov     rcx, rdi; hObject
0x18003a94a  call    cs:__imp_CloseHandle
0x18003a950  mov     eax, ebx
0x18003a952  mov     rcx, [rbp+230h+var_20]
0x18003a959  xor     rcx, rsp; StackCookie
0x18003a95c  call    __security_check_cookie
0x18003a961  lea     r11, [rsp+330h+var_10]
0x18003a969  mov     rbx, [r11+30h]
0x18003a96d  mov     rsi, [r11+38h]
0x18003a971  mov     rsp, r11
0x18003a974  pop     r14
0x18003a976  pop     rdi
0x18003a977  pop     rbp
0x18003a978  retn
```

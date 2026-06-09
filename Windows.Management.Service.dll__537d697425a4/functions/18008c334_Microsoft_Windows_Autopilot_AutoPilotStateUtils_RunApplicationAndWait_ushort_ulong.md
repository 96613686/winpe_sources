# Microsoft::Windows::Autopilot::AutoPilotStateUtils::RunApplicationAndWait(ushort *,ulong)

- ea: `0x18008c334`
- end: `0x18008c677`
- name: `?RunApplicationAndWait@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAGK@Z`
- size: `835`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007ef6c`

## callees

- `0x18000c504`
- `0x180067e34`
- `0x180067e54`
- `0x18008c334`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008c478`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008c478`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18008c3ae`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18008c3ae`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18008c58e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18008c58e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c3e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c45b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c4bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c4d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c51c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c54c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c563`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c5c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c5db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c60a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c621`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c64e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c3e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c45b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c4bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c4d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c51c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c54c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c563`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c5c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c5db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c60a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c621`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c64e`

## string_xrefs

- `0x18008c3c6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008c428`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008c494`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008c5a6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::RunApplicationAndWait(
        LPWSTR lpCommandLine,
        DWORD dwMilliseconds)
{
  const char *v4; // r9
  unsigned int v5; // ebx
  DWORD v7; // eax
  const char *v8; // r9
  unsigned int LastError; // ebx
  const char *v10; // r9
  unsigned int v11; // ebx
  DWORD v12; // ebx
  BOOL bInheritHandles; // [rsp+20h] [rbp-C8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  DWORD ExitCode; // [rsp+100h] [rbp+18h] BYREF

  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(0, lpCommandLine, 0, 0, 1, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    if ( ProcessInformation.hProcess )
    {
      if ( dwMilliseconds )
      {
        v7 = WaitForSingleObject(ProcessInformation.hProcess, dwMilliseconds);
        if ( v7 )
        {
          if ( v7 == 258 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DD,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
              (const char *)0x800705B4LL,
              bInheritHandles);
            if ( ProcessInformation.hProcess != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hProcess);
            if ( ProcessInformation.hThread != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hThread);
            return 2147943860LL;
          }
          else if ( v7 == -1 )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x1DE,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                          v8);
            if ( ProcessInformation.hProcess != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hProcess);
            if ( ProcessInformation.hThread != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hThread);
            return LastError;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DF,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
              (const char *)0x8000FFFFLL,
              bInheritHandles);
            if ( ProcessInformation.hProcess != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hProcess);
            if ( ProcessInformation.hThread != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hThread);
            return 2147549183LL;
          }
        }
        else
        {
          ExitCode = 0;
          if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
          {
            v12 = ExitCode;
            if ( (int)ExitCode > 0 )
              v12 = (unsigned __int16)ExitCode | 0x80070000;
            if ( ProcessInformation.hProcess != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hProcess);
            if ( ProcessInformation.hThread != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hThread);
            return v12;
          }
          else
          {
            v11 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1E3,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                    v10);
            if ( ProcessInformation.hProcess != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hProcess);
            if ( ProcessInformation.hThread != (HANDLE)-1LL )
              CloseHandle(ProcessInformation.hThread);
            return v11;
          }
        }
      }
      else
      {
        if ( ProcessInformation.hProcess != (HANDLE)-1LL )
          CloseHandle(ProcessInformation.hProcess);
        if ( ProcessInformation.hThread != (HANDLE)-1LL )
          CloseHandle(ProcessInformation.hThread);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D6,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
        (const char *)0x8000FFFFLL,
        bInheritHandles);
      if ( ProcessInformation.hProcess != (HANDLE)-1LL )
        CloseHandle(ProcessInformation.hProcess);
      if ( ProcessInformation.hThread != (HANDLE)-1LL )
        CloseHandle(ProcessInformation.hThread);
      return 2147549183LL;
    }
  }
  else
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1D4,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
           v4);
    if ( ProcessInformation.hProcess != (HANDLE)-1LL )
      CloseHandle(ProcessInformation.hProcess);
    if ( ProcessInformation.hThread != (HANDLE)-1LL )
      CloseHandle(ProcessInformation.hThread);
    return v5;
  }
}

```

## disassembly

```asm
0x18008c334  mov     [rsp+arg_0], rbx
0x18008c339  push    rdi
0x18008c33a  sub     rsp, 0E0h
0x18008c341  mov     ebx, edx
0x18008c343  mov     rdi, rcx
0x18008c346  xor     edx, edx; Val
0x18008c348  lea     r8d, [rdx+64h]; Size
0x18008c34c  lea     rcx, [rsp+0E8h+StartupInfo+4]; void *
0x18008c351  call    memset_0
0x18008c356  mov     [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18008c35e  xorps   xmm0, xmm0
0x18008c361  xor     eax, eax
0x18008c363  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x18008c368  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18008c36d  lea     rax, [rsp+0E8h+ProcessInformation]
0x18008c372  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18008c377  lea     rax, [rsp+0E8h+StartupInfo]
0x18008c37c  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x18008c381  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18008c38a  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18008c393  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18008c39b  mov     [rsp+0E8h+bInheritHandles], 1; int
0x18008c3a3  xor     r9d, r9d; lpThreadAttributes
0x18008c3a6  xor     r8d, r8d; lpProcessAttributes
0x18008c3a9  mov     rdx, rdi; lpCommandLine
0x18008c3ac  xor     ecx, ecx; lpApplicationName
0x18008c3ae  call    cs:__imp_CreateProcessW
0x18008c3b5  nop     dword ptr [rax+rax+00h]
0x18008c3ba  test    eax, eax
0x18008c3bc  jnz     short loc_18008C40E
0x18008c3be  mov     rcx, [rsp+0E8h]; this
0x18008c3c6  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008c3cd  mov     edx, 1D4h; void *
0x18008c3d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008c3d7  mov     ebx, eax
0x18008c3d9  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c3de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c3e2  jz      short loc_18008C3F0
0x18008c3e4  call    cs:__imp_CloseHandle
0x18008c3eb  nop     dword ptr [rax+rax+00h]
0x18008c3f0  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c3f5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c3f9  jz      short loc_18008C407
0x18008c3fb  call    cs:__imp_CloseHandle
0x18008c402  nop     dword ptr [rax+rax+00h]
0x18008c407  mov     eax, ebx
0x18008c409  jmp     loc_18008C665
0x18008c40e  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c413  test    rcx, rcx
0x18008c416  jnz     short loc_18008C46E
0x18008c418  mov     rcx, [rsp+0E8h]; this
0x18008c420  mov     ebx, 8000FFFFh
0x18008c425  mov     r9d, ebx; char *
0x18008c428  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008c42f  mov     edx, 1D6h; void *
0x18008c434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c439  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c43e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c442  jz      short loc_18008C450
0x18008c444  call    cs:__imp_CloseHandle
0x18008c44b  nop     dword ptr [rax+rax+00h]
0x18008c450  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c455  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c459  jz      short loc_18008C467
0x18008c45b  call    cs:__imp_CloseHandle
0x18008c462  nop     dword ptr [rax+rax+00h]
0x18008c467  mov     eax, ebx
0x18008c469  jmp     loc_18008C665
0x18008c46e  test    ebx, ebx
0x18008c470  jz      loc_18008C631
0x18008c476  mov     edx, ebx; dwMilliseconds
0x18008c478  call    cs:__imp_WaitForSingleObject
0x18008c47f  nop     dword ptr [rax+rax+00h]
0x18008c484  test    eax, eax
0x18008c486  jz      loc_18008C576
0x18008c48c  mov     rcx, [rsp+0E8h]; this
0x18008c494  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008c49b  cmp     eax, 102h
0x18008c4a0  jnz     short loc_18008C4E9
0x18008c4a2  mov     ebx, 800705B4h
0x18008c4a7  mov     r9d, ebx; char *
0x18008c4aa  mov     edx, 1DDh; void *
0x18008c4af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c4b4  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c4b9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c4bd  jz      short loc_18008C4CB
0x18008c4bf  call    cs:__imp_CloseHandle
0x18008c4c6  nop     dword ptr [rax+rax+00h]
0x18008c4cb  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c4d0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c4d4  jz      short loc_18008C4E2
0x18008c4d6  call    cs:__imp_CloseHandle
0x18008c4dd  nop     dword ptr [rax+rax+00h]
0x18008c4e2  mov     eax, ebx
0x18008c4e4  jmp     loc_18008C665
0x18008c4e9  cmp     eax, 0FFFFFFFFh
0x18008c4ec  jnz     short loc_18008C52F
0x18008c4ee  mov     edx, 1DEh; void *
0x18008c4f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008c4f8  mov     ebx, eax
0x18008c4fa  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c4ff  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c503  jz      short loc_18008C511
0x18008c505  call    cs:__imp_CloseHandle
0x18008c50c  nop     dword ptr [rax+rax+00h]
0x18008c511  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c516  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c51a  jz      short loc_18008C528
0x18008c51c  call    cs:__imp_CloseHandle
0x18008c523  nop     dword ptr [rax+rax+00h]
0x18008c528  mov     eax, ebx
0x18008c52a  jmp     loc_18008C665
0x18008c52f  mov     ebx, 8000FFFFh
0x18008c534  mov     r9d, ebx; char *
0x18008c537  mov     edx, 1DFh; void *
0x18008c53c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c541  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c546  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c54a  jz      short loc_18008C558
0x18008c54c  call    cs:__imp_CloseHandle
0x18008c553  nop     dword ptr [rax+rax+00h]
0x18008c558  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c55d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c561  jz      short loc_18008C56F
0x18008c563  call    cs:__imp_CloseHandle
0x18008c56a  nop     dword ptr [rax+rax+00h]
0x18008c56f  mov     eax, ebx
0x18008c571  jmp     loc_18008C665
0x18008c576  mov     [rsp+0E8h+ExitCode], 0
0x18008c581  lea     rdx, [rsp+0E8h+ExitCode]; lpExitCode
0x18008c589  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x18008c58e  call    cs:__imp_GetExitCodeProcess
0x18008c595  nop     dword ptr [rax+rax+00h]
0x18008c59a  test    eax, eax
0x18008c59c  jnz     short loc_18008C5EB
0x18008c59e  mov     rcx, [rsp+0E8h]; this
0x18008c5a6  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008c5ad  mov     edx, 1E3h; void *
0x18008c5b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008c5b7  mov     ebx, eax
0x18008c5b9  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c5be  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c5c2  jz      short loc_18008C5D0
0x18008c5c4  call    cs:__imp_CloseHandle
0x18008c5cb  nop     dword ptr [rax+rax+00h]
0x18008c5d0  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c5d5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c5d9  jz      short loc_18008C5E7
0x18008c5db  call    cs:__imp_CloseHandle
0x18008c5e2  nop     dword ptr [rax+rax+00h]
0x18008c5e7  mov     eax, ebx
0x18008c5e9  jmp     short loc_18008C665
0x18008c5eb  mov     ebx, [rsp+0E8h+ExitCode]
0x18008c5f2  test    ebx, ebx
0x18008c5f4  jle     short loc_18008C5FF
0x18008c5f6  movzx   ebx, bx
0x18008c5f9  or      ebx, 80070000h
0x18008c5ff  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008c604  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c608  jz      short loc_18008C616
0x18008c60a  call    cs:__imp_CloseHandle
0x18008c611  nop     dword ptr [rax+rax+00h]
0x18008c616  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c61b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c61f  jz      short loc_18008C62D
0x18008c621  call    cs:__imp_CloseHandle
0x18008c628  nop     dword ptr [rax+rax+00h]
0x18008c62d  mov     eax, ebx
0x18008c62f  jmp     short loc_18008C665
0x18008c631  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c635  jz      short loc_18008C643
0x18008c637  call    cs:__imp_CloseHandle
0x18008c63e  nop     dword ptr [rax+rax+00h]
0x18008c643  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008c648  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c64c  jz      short loc_18008C65A
0x18008c64e  call    cs:__imp_CloseHandle
0x18008c655  nop     dword ptr [rax+rax+00h]
0x18008c65a  xor     eax, eax
0x18008c65c  jmp     short loc_18008C665
0x18008c65e  mov     eax, [rsp+0E8h+ExitCode]
0x18008c665  mov     rbx, [rsp+0E8h+arg_0]
0x18008c66d  add     rsp, 0E0h
0x18008c674  pop     rdi
0x18008c675  retn
```

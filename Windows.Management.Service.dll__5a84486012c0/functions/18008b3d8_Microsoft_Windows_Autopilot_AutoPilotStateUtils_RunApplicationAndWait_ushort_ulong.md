# Microsoft::Windows::Autopilot::AutoPilotStateUtils::RunApplicationAndWait(ushort *,ulong)

- ea: `0x18008b3d8`
- end: `0x18008b6a9`
- name: `?RunApplicationAndWait@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAGK@Z`
- size: `721`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007e5cc`

## callees

- `0x18000c414`
- `0x180067a34`
- `0x180067a54`
- `0x18008b3d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008b4fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008b4fe`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18008b452`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18008b452`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18008b5ea`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18008b5ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b58a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b61a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b62b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b654`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b675`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b686`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b4e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b58a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b61a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b62b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b654`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b675`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b686`

## string_xrefs

- `0x18008b464`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b4ba`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b514`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b5fc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
0x18008b3d8  mov     [rsp+arg_0], rbx
0x18008b3dd  push    rdi
0x18008b3de  sub     rsp, 0E0h
0x18008b3e5  mov     ebx, edx
0x18008b3e7  mov     rdi, rcx
0x18008b3ea  xor     edx, edx; Val
0x18008b3ec  lea     r8d, [rdx+64h]; Size
0x18008b3f0  lea     rcx, [rsp+0E8h+StartupInfo+4]; void *
0x18008b3f5  call    memset_0
0x18008b3fa  mov     [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18008b402  xorps   xmm0, xmm0
0x18008b405  xor     eax, eax
0x18008b407  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x18008b40c  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18008b411  lea     rax, [rsp+0E8h+ProcessInformation]
0x18008b416  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18008b41b  lea     rax, [rsp+0E8h+StartupInfo]
0x18008b420  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x18008b425  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18008b42e  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18008b437  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18008b43f  mov     [rsp+0E8h+bInheritHandles], 1; int
0x18008b447  xor     r9d, r9d; lpThreadAttributes
0x18008b44a  xor     r8d, r8d; lpProcessAttributes
0x18008b44d  mov     rdx, rdi; lpCommandLine
0x18008b450  xor     ecx, ecx; lpApplicationName
0x18008b452  call    cs:__imp_CreateProcessW
0x18008b458  test    eax, eax
0x18008b45a  jnz     short loc_18008B4A0
0x18008b45c  mov     rcx, [rsp+0E8h]; this
0x18008b464  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b46b  mov     edx, 1D4h; void *
0x18008b470  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b475  mov     ebx, eax
0x18008b477  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b47c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b480  jz      short loc_18008B488
0x18008b482  call    cs:__imp_CloseHandle
0x18008b488  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b48d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b491  jz      short loc_18008B499
0x18008b493  call    cs:__imp_CloseHandle
0x18008b499  mov     eax, ebx
0x18008b49b  jmp     loc_18008B697
0x18008b4a0  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b4a5  test    rcx, rcx
0x18008b4a8  jnz     short loc_18008B4F4
0x18008b4aa  mov     rcx, [rsp+0E8h]; this
0x18008b4b2  mov     ebx, 8000FFFFh
0x18008b4b7  mov     r9d, ebx; char *
0x18008b4ba  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b4c1  mov     edx, 1D6h; void *
0x18008b4c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b4cb  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b4d0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b4d4  jz      short loc_18008B4DC
0x18008b4d6  call    cs:__imp_CloseHandle
0x18008b4dc  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b4e1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b4e5  jz      short loc_18008B4ED
0x18008b4e7  call    cs:__imp_CloseHandle
0x18008b4ed  mov     eax, ebx
0x18008b4ef  jmp     loc_18008B697
0x18008b4f4  test    ebx, ebx
0x18008b4f6  jz      loc_18008B66F
0x18008b4fc  mov     edx, ebx; dwMilliseconds
0x18008b4fe  call    cs:__imp_WaitForSingleObject
0x18008b504  test    eax, eax
0x18008b506  jz      loc_18008B5D2
0x18008b50c  mov     rcx, [rsp+0E8h]; this
0x18008b514  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b51b  cmp     eax, 102h
0x18008b520  jnz     short loc_18008B55D
0x18008b522  mov     ebx, 800705B4h
0x18008b527  mov     r9d, ebx; char *
0x18008b52a  mov     edx, 1DDh; void *
0x18008b52f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b534  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b539  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b53d  jz      short loc_18008B545
0x18008b53f  call    cs:__imp_CloseHandle
0x18008b545  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b54a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b54e  jz      short loc_18008B556
0x18008b550  call    cs:__imp_CloseHandle
0x18008b556  mov     eax, ebx
0x18008b558  jmp     loc_18008B697
0x18008b55d  cmp     eax, 0FFFFFFFFh
0x18008b560  jnz     short loc_18008B597
0x18008b562  mov     edx, 1DEh; void *
0x18008b567  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b56c  mov     ebx, eax
0x18008b56e  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b573  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b577  jz      short loc_18008B57F
0x18008b579  call    cs:__imp_CloseHandle
0x18008b57f  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b584  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b588  jz      short loc_18008B590
0x18008b58a  call    cs:__imp_CloseHandle
0x18008b590  mov     eax, ebx
0x18008b592  jmp     loc_18008B697
0x18008b597  mov     ebx, 8000FFFFh
0x18008b59c  mov     r9d, ebx; char *
0x18008b59f  mov     edx, 1DFh; void *
0x18008b5a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b5a9  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b5ae  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b5b2  jz      short loc_18008B5BA
0x18008b5b4  call    cs:__imp_CloseHandle
0x18008b5ba  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b5bf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b5c3  jz      short loc_18008B5CB
0x18008b5c5  call    cs:__imp_CloseHandle
0x18008b5cb  mov     eax, ebx
0x18008b5cd  jmp     loc_18008B697
0x18008b5d2  mov     [rsp+0E8h+ExitCode], 0
0x18008b5dd  lea     rdx, [rsp+0E8h+ExitCode]; lpExitCode
0x18008b5e5  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x18008b5ea  call    cs:__imp_GetExitCodeProcess
0x18008b5f0  test    eax, eax
0x18008b5f2  jnz     short loc_18008B635
0x18008b5f4  mov     rcx, [rsp+0E8h]; this
0x18008b5fc  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b603  mov     edx, 1E3h; void *
0x18008b608  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b60d  mov     ebx, eax
0x18008b60f  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b614  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b618  jz      short loc_18008B620
0x18008b61a  call    cs:__imp_CloseHandle
0x18008b620  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b625  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b629  jz      short loc_18008B631
0x18008b62b  call    cs:__imp_CloseHandle
0x18008b631  mov     eax, ebx
0x18008b633  jmp     short loc_18008B697
0x18008b635  mov     ebx, [rsp+0E8h+ExitCode]
0x18008b63c  test    ebx, ebx
0x18008b63e  jle     short loc_18008B649
0x18008b640  movzx   ebx, bx
0x18008b643  or      ebx, 80070000h
0x18008b649  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18008b64e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b652  jz      short loc_18008B65A
0x18008b654  call    cs:__imp_CloseHandle
0x18008b65a  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b65f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b663  jz      short loc_18008B66B
0x18008b665  call    cs:__imp_CloseHandle
0x18008b66b  mov     eax, ebx
0x18008b66d  jmp     short loc_18008B697
0x18008b66f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b673  jz      short loc_18008B67B
0x18008b675  call    cs:__imp_CloseHandle
0x18008b67b  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18008b680  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b684  jz      short loc_18008B68C
0x18008b686  call    cs:__imp_CloseHandle
0x18008b68c  xor     eax, eax
0x18008b68e  jmp     short loc_18008B697
0x18008b690  mov     eax, [rsp+0E8h+ExitCode]
0x18008b697  mov     rbx, [rsp+0E8h+arg_0]
0x18008b69f  add     rsp, 0E0h
0x18008b6a6  pop     rdi
0x18008b6a7  retn
```

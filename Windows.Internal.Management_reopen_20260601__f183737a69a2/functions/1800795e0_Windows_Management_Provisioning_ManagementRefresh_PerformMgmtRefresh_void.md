# Windows::Management::Provisioning::ManagementRefresh::PerformMgmtRefresh(void)

- ea: `0x1800795e0`
- end: `0x180079788`
- name: `?PerformMgmtRefresh@ManagementRefresh@Provisioning@Management@Windows@@AEAAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::ManagementRefresh *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800798f0`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x18000a5a4`
- `0x18000a5c4`
- `0x1800795ac`
- `0x1800795e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800796ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800796ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800796cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800796cf`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180079706`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180079706`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007965e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007965e`

## string_xrefs

- `0x180079635`: `%windir%\System32\ProvTool.exe`

## pseudocode

```c
__int64 __fastcall Windows::Management::Provisioning::ManagementRefresh::PerformMgmtRefresh(
        Windows::Management::Provisioning::ManagementRefresh *this)
{
  const char *v1; // r9
  const char *v3; // r9
  __int64 v4; // rdx
  struct _PROCESS_INFORMATION *v5; // rdx
  DWORD LastError; // ebx
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Dst[264]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.cbReserved2 = 0;
  memset(&StartupInfo.lpReserved, 0, 24);
  StartupInfo.lpReserved2 = 0;
  StartupInfo.dwFlags = 0;
  *(_QWORD *)&ProcessAttributes.bInheritHandle = 0;
  ProcessAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&ProcessAttributes.nLength = 24;
  if ( !ExpandEnvironmentStringsW(L"%windir%\\System32\\ProvTool.exe", Dst, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2A,
             (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\mgmtrefresh.cpp",
             v1);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(
         Dst,
         (LPWSTR)L"Provtool.exe /ManagementRefresh /Timeloop",
         &ProcessAttributes,
         0,
         0,
         0,
         0,
         0,
         &StartupInfo,
         &ProcessInformation) )
  {
    WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    ExitCode = 0;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      LastError = ExitCode;
      if ( (ExitCode & 0x80000000) == 0 )
        LastError = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\mgmtrefresh.cpp",
          (const char *)ExitCode,
          bInheritHandles);
      goto LABEL_11;
    }
    v4 = 62;
  }
  else
  {
    v4 = 58;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v4,
                (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\mgmtrefresh.cpp",
                v3);
LABEL_11:
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v5);
  return LastError;
}

```

## disassembly

```asm
0x1800795e0  mov     [rsp-8+arg_0], rbx
0x1800795e5  mov     [rsp-8+arg_8], rdi
0x1800795ea  push    rbp
0x1800795eb  lea     rbp, [rsp-220h]
0x1800795f3  sub     rsp, 320h
0x1800795fa  mov     rax, cs:__security_cookie
0x180079601  xor     rax, rsp
0x180079604  mov     [rbp+220h+var_10], rax
0x18007960b  mov     ebx, 68h ; 'h'
0x180079610  lea     rcx, [rbp+220h+StartupInfo]; void *
0x180079614  mov     r8d, ebx; Size
0x180079617  xor     edx, edx; Val
0x180079619  call    memset_0
0x18007961e  xor     edi, edi
0x180079620  mov     [rbp+220h+StartupInfo.cb], ebx
0x180079623  mov     r8d, 104h; nSize
0x180079629  mov     [rbp+220h+StartupInfo.cbReserved2], di
0x18007962d  lea     rdx, [rbp+220h+Dst]; lpDst
0x180079631  mov     [rbp+220h+StartupInfo.lpDesktop], rdi
0x180079635  lea     rcx, aWindirSystem32_1; "%windir%\\System32\\ProvTool.exe"
0x18007963c  mov     [rbp+220h+StartupInfo.lpReserved], rdi
0x180079640  mov     [rbp+220h+StartupInfo.lpReserved2], rdi
0x180079644  mov     [rbp+220h+StartupInfo.lpTitle], rdi
0x180079648  mov     [rbp+220h+StartupInfo.dwFlags], edi
0x18007964b  mov     qword ptr [rsp+320h+ProcessAttributes.bInheritHandle], rdi
0x180079650  mov     [rsp+320h+ProcessAttributes.lpSecurityDescriptor], rdi
0x180079655  mov     qword ptr [rsp+320h+ProcessAttributes.nLength], 18h
0x18007965e  call    cs:__imp_ExpandEnvironmentStringsW
0x180079665  nop     dword ptr [rax+rax+00h]
0x18007966a  test    eax, eax
0x18007966c  jnz     short loc_180079689
0x18007966e  mov     rcx, [rbp+228h]; this
0x180079675  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007967c  lea     edx, [rbx-3Eh]; void *
0x18007967f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180079684  jmp     loc_180079763
0x180079689  xor     eax, eax
0x18007968b  lea     r8, [rsp+320h+ProcessAttributes]; lpProcessAttributes
0x180079690  mov     qword ptr [rbp+220h+ProcessInformation.dwProcessId], rax
0x180079694  lea     rdx, CommandLine; "Provtool.exe /ManagementRefresh /Timelo"...
0x18007969b  lea     rax, [rsp+320h+ProcessInformation]
0x1800796a0  xorps   xmm0, xmm0
0x1800796a3  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x1800796a8  lea     rcx, [rbp+220h+Dst]; lpApplicationName
0x1800796ac  lea     rax, [rbp+220h+StartupInfo]
0x1800796b0  xor     r9d, r9d; lpThreadAttributes
0x1800796b3  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x1800796b8  mov     [rsp+320h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x1800796bd  mov     [rsp+320h+lpEnvironment], rdi; lpEnvironment
0x1800796c2  mov     [rsp+320h+dwCreationFlags], edi; dwCreationFlags
0x1800796c6  mov     [rsp+320h+bInheritHandles], edi; int
0x1800796ca  movups  xmmword ptr [rsp+320h+ProcessInformation.hProcess], xmm0
0x1800796cf  call    cs:__imp_CreateProcessW
0x1800796d6  nop     dword ptr [rax+rax+00h]
0x1800796db  test    eax, eax
0x1800796dd  jnz     short loc_1800796E4
0x1800796df  lea     edx, [rax+3Ah]
0x1800796e2  jmp     short loc_180079719
0x1800796e4  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hHandle
0x1800796e9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800796ec  call    cs:__imp_WaitForSingleObject
0x1800796f3  nop     dword ptr [rax+rax+00h]
0x1800796f8  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hProcess
0x1800796fd  lea     rdx, [rsp+320h+ExitCode]; lpExitCode
0x180079702  mov     [rsp+320h+ExitCode], edi
0x180079706  call    cs:__imp_GetExitCodeProcess
0x18007970d  nop     dword ptr [rax+rax+00h]
0x180079712  test    eax, eax
0x180079714  jnz     short loc_180079730
0x180079716  lea     edx, [rax+3Eh]; void *
0x180079719  mov     rcx, [rbp+228h]; this
0x180079720  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079727  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007972c  mov     ebx, eax
0x18007972e  jmp     short loc_180079757
0x180079730  mov     ebx, [rsp+320h+ExitCode]
0x180079734  test    ebx, ebx
0x180079736  jns     short loc_180079755
0x180079738  mov     rcx, [rbp+228h]; this
0x18007973f  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079746  mov     r9d, ebx; char *
0x180079749  mov     edx, 3Fh ; '?'; void *
0x18007974e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079753  jmp     short loc_180079757
0x180079755  mov     ebx, edi
0x180079757  lea     rcx, [rsp+320h+ProcessInformation]; this
0x18007975c  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180079761  mov     eax, ebx
0x180079763  mov     rcx, [rbp+220h+var_10]
0x18007976a  xor     rcx, rsp; StackCookie
0x18007976d  call    __security_check_cookie
0x180079772  lea     r11, [rsp+320h+var_s0]
0x18007977a  mov     rbx, [r11+10h]
0x18007977e  mov     rdi, [r11+18h]
0x180079782  mov     rsp, r11
0x180079785  pop     rbp
0x180079786  retn
```

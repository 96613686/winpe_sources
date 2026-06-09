# Windows::Management::Provisioning::ManagementRefresh::PerformMgmtRefresh(void)

- ea: `0x180077e2c`
- end: `0x180077fbb`
- name: `?PerformMgmtRefresh@ManagementRefresh@Provisioning@Management@Windows@@AEAAJXZ`
- size: `399`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::ManagementRefresh *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180078130`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000a284`
- `0x18000a2a4`
- `0x180077dfc`
- `0x180077e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077f2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180077f40`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180077f40`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180077f15`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180077f15`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180077eaa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180077eaa`

## string_xrefs

- `0x180077e81`: `%windir%\System32\ProvTool.exe`

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
0x180077e2c  mov     [rsp-8+arg_0], rbx
0x180077e31  mov     [rsp-8+arg_8], rdi
0x180077e36  push    rbp
0x180077e37  lea     rbp, [rsp-220h]
0x180077e3f  sub     rsp, 320h
0x180077e46  mov     rax, cs:__security_cookie
0x180077e4d  xor     rax, rsp
0x180077e50  mov     [rbp+220h+var_10], rax
0x180077e57  mov     ebx, 68h ; 'h'
0x180077e5c  lea     rcx, [rbp+220h+StartupInfo]; void *
0x180077e60  mov     r8d, ebx; Size
0x180077e63  xor     edx, edx; Val
0x180077e65  call    memset_0
0x180077e6a  xor     edi, edi
0x180077e6c  mov     [rbp+220h+StartupInfo.cb], ebx
0x180077e6f  mov     r8d, 104h; nSize
0x180077e75  mov     [rbp+220h+StartupInfo.cbReserved2], di
0x180077e79  lea     rdx, [rbp+220h+Dst]; lpDst
0x180077e7d  mov     [rbp+220h+StartupInfo.lpDesktop], rdi
0x180077e81  lea     rcx, aWindirSystem32_1; "%windir%\\System32\\ProvTool.exe"
0x180077e88  mov     [rbp+220h+StartupInfo.lpReserved], rdi
0x180077e8c  mov     [rbp+220h+StartupInfo.lpReserved2], rdi
0x180077e90  mov     [rbp+220h+StartupInfo.lpTitle], rdi
0x180077e94  mov     [rbp+220h+StartupInfo.dwFlags], edi
0x180077e97  mov     qword ptr [rsp+320h+ProcessAttributes.bInheritHandle], rdi
0x180077e9c  mov     [rsp+320h+ProcessAttributes.lpSecurityDescriptor], rdi
0x180077ea1  mov     qword ptr [rsp+320h+ProcessAttributes.nLength], 18h
0x180077eaa  call    cs:__imp_ExpandEnvironmentStringsW
0x180077eb0  test    eax, eax
0x180077eb2  jnz     short loc_180077ECF
0x180077eb4  mov     rcx, [rbp+228h]; this
0x180077ebb  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077ec2  lea     edx, [rbx-3Eh]; void *
0x180077ec5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180077eca  jmp     loc_180077F97
0x180077ecf  xor     eax, eax
0x180077ed1  lea     r8, [rsp+320h+ProcessAttributes]; lpProcessAttributes
0x180077ed6  mov     qword ptr [rbp+220h+ProcessInformation.dwProcessId], rax
0x180077eda  lea     rdx, CommandLine; "Provtool.exe /ManagementRefresh /Timelo"...
0x180077ee1  lea     rax, [rsp+320h+ProcessInformation]
0x180077ee6  xorps   xmm0, xmm0
0x180077ee9  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x180077eee  lea     rcx, [rbp+220h+Dst]; lpApplicationName
0x180077ef2  lea     rax, [rbp+220h+StartupInfo]
0x180077ef6  xor     r9d, r9d; lpThreadAttributes
0x180077ef9  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x180077efe  mov     [rsp+320h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x180077f03  mov     [rsp+320h+lpEnvironment], rdi; lpEnvironment
0x180077f08  mov     [rsp+320h+dwCreationFlags], edi; dwCreationFlags
0x180077f0c  mov     [rsp+320h+bInheritHandles], edi; int
0x180077f10  movups  xmmword ptr [rsp+320h+ProcessInformation.hProcess], xmm0
0x180077f15  call    cs:__imp_CreateProcessW
0x180077f1b  test    eax, eax
0x180077f1d  jnz     short loc_180077F24
0x180077f1f  lea     edx, [rax+3Ah]
0x180077f22  jmp     short loc_180077F4D
0x180077f24  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hHandle
0x180077f29  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180077f2c  call    cs:__imp_WaitForSingleObject
0x180077f32  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hProcess
0x180077f37  lea     rdx, [rsp+320h+ExitCode]; lpExitCode
0x180077f3c  mov     [rsp+320h+ExitCode], edi
0x180077f40  call    cs:__imp_GetExitCodeProcess
0x180077f46  test    eax, eax
0x180077f48  jnz     short loc_180077F64
0x180077f4a  lea     edx, [rax+3Eh]; void *
0x180077f4d  mov     rcx, [rbp+228h]; this
0x180077f54  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077f5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180077f60  mov     ebx, eax
0x180077f62  jmp     short loc_180077F8B
0x180077f64  mov     ebx, [rsp+320h+ExitCode]
0x180077f68  test    ebx, ebx
0x180077f6a  jns     short loc_180077F89
0x180077f6c  mov     rcx, [rbp+228h]; this
0x180077f73  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180077f7a  mov     r9d, ebx; char *
0x180077f7d  mov     edx, 3Fh ; '?'; void *
0x180077f82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077f87  jmp     short loc_180077F8B
0x180077f89  mov     ebx, edi
0x180077f8b  lea     rcx, [rsp+320h+ProcessInformation]; this
0x180077f90  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180077f95  mov     eax, ebx
0x180077f97  mov     rcx, [rbp+220h+var_10]
0x180077f9e  xor     rcx, rsp; StackCookie
0x180077fa1  call    __security_check_cookie
0x180077fa6  lea     r11, [rsp+320h+var_s0]
0x180077fae  mov     rbx, [r11+10h]
0x180077fb2  mov     rdi, [r11+18h]
0x180077fb6  mov     rsp, r11
0x180077fb9  pop     rbp
0x180077fba  retn
```

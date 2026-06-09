# CSogouIMEShim::Install(void)

- ea: `0x180036cd8`
- end: `0x180036ead`
- name: `?Install@CSogouIMEShim@@QEAAKXZ`
- size: `469`
- prototype: `unsigned int __fastcall(CSogouIMEShim *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180036ec0`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180036cd8`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetExitCodeProcess` at `0x180036e27`
- `KERNEL32!GetExitCodeProcess` at `0x180036e27`
- `KERNEL32!CreateProcessW` at `0x180036db5`
- `KERNEL32!CreateProcessW` at `0x180036db5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180036d36`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180036d36`
- `KERNEL32!CloseHandle` at `0x180036e75`
- `KERNEL32!CloseHandle` at `0x180036e85`
- `KERNEL32!CloseHandle` at `0x180036e75`
- `KERNEL32!CloseHandle` at `0x180036e85`
- `KERNEL32!GetLastError` at `0x180036d40`
- `KERNEL32!GetLastError` at `0x180036dbf`
- `KERNEL32!GetLastError` at `0x180036e08`
- `KERNEL32!GetLastError` at `0x180036e38`
- `KERNEL32!GetLastError` at `0x180036d40`
- `KERNEL32!GetLastError` at `0x180036dbf`
- `KERNEL32!GetLastError` at `0x180036e08`
- `KERNEL32!GetLastError` at `0x180036e38`
- `KERNEL32!WaitForSingleObject` at `0x180036dfe`
- `KERNEL32!WaitForSingleObject` at `0x180036dfe`

## string_xrefs

- `0x180036d46`: `Error expanding windows directory. [%d]`
- `0x180036d53`: `CSogouIMEShim::Install`
- `0x180036dd6`: `CSogouIMEShim::Install`
- `0x180036e53`: `CSogouIMEShim::Install`

## pseudocode

```c
__int64 __fastcall CSogouIMEShim::Install(CSogouIMEShim *this)
{
  DWORD LastError; // ebx
  DWORD v2; // eax
  const char *v3; // r9
  __int64 v4; // r8
  __int64 dwCreationFlags; // [rsp+28h] [rbp-D8h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  ExitCode = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !ExpandEnvironmentStringsW(L"%windir%\\syswow64\\ime\\sogoupy\\SogouWin10Setup.exe", Dst, 0x103u) )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "CSogouIMEShim::Install", 161, "Error expanding windows directory. [%d]", LastError);
    goto LABEL_12;
  }
  StartupInfo.cb = 104;
  if ( !CreateProcessW(Dst, 0, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v2 = GetLastError();
    v3 = "sogouIMEShim failed to start process [%ws] [%d]";
    v4 = 179;
LABEL_5:
    LODWORD(dwCreationFlags) = v2;
    LastError = v2;
    AslLogCallPrintf(1, "CSogouIMEShim::Install", v4, v3, Dst, dwCreationFlags);
    goto LABEL_12;
  }
  if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) == -1 )
  {
    v2 = GetLastError();
    v3 = "Wait for sogouIMEShim setup process failed [%ws] [%d]";
    v4 = 186;
    goto LABEL_5;
  }
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) || ExitCode )
  {
    LODWORD(dwCreationFlags) = GetLastError();
    AslLogCallPrintf(
      1,
      "CSogouIMEShim::Install",
      193,
      "Failed to get sogouIMEShim setup exit code [%ws] [%d]",
      Dst,
      dwCreationFlags);
  }
  LastError = 0;
LABEL_12:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return LastError;
}

```

## disassembly

```asm
0x180036cd8  mov     [rsp-8+arg_0], rbx
0x180036cdd  push    rbp
0x180036cde  lea     rbp, [rsp-200h]
0x180036ce6  sub     rsp, 300h
0x180036ced  mov     rax, cs:__security_cookie
0x180036cf4  xor     rax, rsp
0x180036cf7  mov     [rbp+200h+var_10], rax
0x180036cfe  mov     ebx, 68h ; 'h'
0x180036d03  lea     rcx, [rsp+300h+StartupInfo]; void *
0x180036d08  mov     r8d, ebx; Size
0x180036d0b  xor     edx, edx; Val
0x180036d0d  call    memset_0
0x180036d12  xor     eax, eax
0x180036d14  lea     rdx, [rbp+200h+Dst]; lpDst
0x180036d18  xorps   xmm0, xmm0
0x180036d1b  mov     qword ptr [rsp+300h+ProcessInformation.dwProcessId], rax
0x180036d20  mov     r8d, 103h; nSize
0x180036d26  mov     [rsp+300h+ExitCode], eax
0x180036d2a  lea     rcx, aWindirSyswow64; "%windir%\\syswow64\\ime\\sogoupy\\Sogou"...
0x180036d31  movups  xmmword ptr [rsp+300h+ProcessInformation.hProcess], xmm0
0x180036d36  call    cs:__imp_ExpandEnvironmentStringsW
0x180036d3c  test    eax, eax
0x180036d3e  jnz     short loc_180036D6F
0x180036d40  call    cs:__imp_GetLastError
0x180036d46  lea     r9, aErrorExpanding_1; "Error expanding windows directory. [%d]"
0x180036d4d  mov     r8d, 0A1h
0x180036d53  lea     rdx, aCsogouimeshimI_0; "CSogouIMEShim::Install"
0x180036d5a  mov     [rsp+300h+bInheritHandles], eax
0x180036d5e  mov     ecx, 1
0x180036d63  mov     ebx, eax
0x180036d65  call    AslLogCallPrintf
0x180036d6a  jmp     loc_180036E6B
0x180036d6f  lea     rax, [rsp+300h+ProcessInformation]
0x180036d74  mov     [rsp+300h+StartupInfo.cb], ebx
0x180036d78  mov     [rsp+300h+lpProcessInformation], rax; lpProcessInformation
0x180036d7d  lea     rcx, [rbp+200h+Dst]; lpApplicationName
0x180036d81  lea     rax, [rsp+300h+StartupInfo]
0x180036d86  xor     r9d, r9d; lpThreadAttributes
0x180036d89  mov     [rsp+300h+lpStartupInfo], rax; lpStartupInfo
0x180036d8e  xor     r8d, r8d; lpProcessAttributes
0x180036d91  mov     [rsp+300h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180036d9a  xor     edx, edx; lpCommandLine
0x180036d9c  mov     [rsp+300h+lpEnvironment], 0; lpEnvironment
0x180036da5  mov     dword ptr [rsp+300h+dwCreationFlags], 8000000h; dwCreationFlags
0x180036dad  mov     [rsp+300h+bInheritHandles], 0; bInheritHandles
0x180036db5  call    cs:__imp_CreateProcessW
0x180036dbb  test    eax, eax
0x180036dbd  jnz     short loc_180036DF4
0x180036dbf  call    cs:__imp_GetLastError
0x180036dc5  lea     r9, aSogouimeshimFa; "sogouIMEShim failed to start process [%"...
0x180036dcc  mov     r8d, 0B3h
0x180036dd2  mov     dword ptr [rsp+300h+dwCreationFlags], eax
0x180036dd6  lea     rdx, aCsogouimeshimI_0; "CSogouIMEShim::Install"
0x180036ddd  mov     ebx, eax
0x180036ddf  mov     ecx, 1
0x180036de4  lea     rax, [rbp+200h+Dst]
0x180036de8  mov     qword ptr [rsp+300h+bInheritHandles], rax
0x180036ded  call    AslLogCallPrintf
0x180036df2  jmp     short loc_180036E6B
0x180036df4  mov     rcx, [rsp+300h+ProcessInformation.hProcess]; hHandle
0x180036df9  or      ebx, 0FFFFFFFFh
0x180036dfc  mov     edx, ebx; dwMilliseconds
0x180036dfe  call    cs:__imp_WaitForSingleObject
0x180036e04  cmp     eax, ebx
0x180036e06  jnz     short loc_180036E1D
0x180036e08  call    cs:__imp_GetLastError
0x180036e0e  lea     r9, aWaitForSogouim; "Wait for sogouIMEShim setup process fai"...
0x180036e15  mov     r8d, 0BAh
0x180036e1b  jmp     short loc_180036DD2
0x180036e1d  mov     rcx, [rsp+300h+ProcessInformation.hProcess]; hProcess
0x180036e22  lea     rdx, [rsp+300h+ExitCode]; lpExitCode
0x180036e27  call    cs:__imp_GetExitCodeProcess
0x180036e2d  test    eax, eax
0x180036e2f  jz      short loc_180036E38
0x180036e31  cmp     [rsp+300h+ExitCode], 0
0x180036e36  jz      short loc_180036E69
0x180036e38  call    cs:__imp_GetLastError
0x180036e3e  mov     dword ptr [rsp+300h+dwCreationFlags], eax
0x180036e42  lea     r9, aFailedToGetSog; "Failed to get sogouIMEShim setup exit c"...
0x180036e49  lea     rax, [rbp+200h+Dst]
0x180036e4d  mov     r8d, 0C1h
0x180036e53  lea     rdx, aCsogouimeshimI_0; "CSogouIMEShim::Install"
0x180036e5a  mov     qword ptr [rsp+300h+bInheritHandles], rax
0x180036e5f  mov     ecx, 1
0x180036e64  call    AslLogCallPrintf
0x180036e69  xor     ebx, ebx
0x180036e6b  mov     rcx, [rsp+300h+ProcessInformation.hProcess]; hObject
0x180036e70  test    rcx, rcx
0x180036e73  jz      short loc_180036E7B
0x180036e75  call    cs:__imp_CloseHandle
0x180036e7b  mov     rcx, [rsp+300h+ProcessInformation.hThread]; hObject
0x180036e80  test    rcx, rcx
0x180036e83  jz      short loc_180036E8B
0x180036e85  call    cs:__imp_CloseHandle
0x180036e8b  mov     eax, ebx
0x180036e8d  mov     rcx, [rbp+200h+var_10]
0x180036e94  xor     rcx, rsp; StackCookie
0x180036e97  call    __security_check_cookie
0x180036e9c  mov     rbx, [rsp+300h+arg_0]
0x180036ea4  add     rsp, 300h
0x180036eab  pop     rbp
0x180036eac  retn
```

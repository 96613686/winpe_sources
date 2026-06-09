# FF_RunCmd(ushort const *,...)

- ea: `0x18008921c`
- end: `0x180089370`
- name: `?FF_RunCmd@@YAJPEBGZZ`
- size: `340`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180088b84`

## callees

- `0x180085d18`
- `0x18008921c`
- `0x1800b83ee`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800892fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800892fa`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180089324`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180089324`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008930c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008930c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008932f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008933a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008932f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008933a`

## pseudocode

```c
signed int FF_RunCmd(const unsigned __int16 *a1, ...)
{
  signed int result; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v3; // [rsp+70h] [rbp-98h]
  struct _STARTUPINFOW StartupInfo; // [rsp+78h] [rbp-90h] BYREF
  WCHAR CommandLine[520]; // [rsp+E8h] [rbp-20h] BYREF
  va_list va; // [rsp+520h] [rbp+418h] BYREF

  va_start(va, a1);
  CommandLine[0] = 0;
  ProcessInformation.hProcess = 0;
  CommandLine[519] = 0;
  result = StringCchVPrintfW(CommandLine, 0x208u, a1, va);
  if ( result >= 0 )
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.wShowWindow = 6;
    StartupInfo.dwFlags = 129;
    v3 = 0;
    *(_OWORD *)&ProcessInformation.hThread = 0;
    if ( CreateProcessW(
           0,
           CommandLine,
           0,
           0,
           0,
           8u,
           0,
           0,
           &StartupInfo,
           (LPPROCESS_INFORMATION)&ProcessInformation.hThread) )
    {
      WaitForSingleObject(ProcessInformation.hThread, 0xFFFFFFFF);
      LODWORD(ProcessInformation.hProcess) = 0;
      GetExitCodeProcess(ProcessInformation.hThread, (LPDWORD)&ProcessInformation);
      CloseHandle(ProcessInformation.hThread);
      CloseHandle(*(HANDLE *)&ProcessInformation.dwProcessId);
      result = (signed int)ProcessInformation.hProcess;
    }
    else
    {
      result = GetLastError();
    }
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18008921c  mov     rax, rsp
0x18008921f  mov     [rax+8], rcx
0x180089223  mov     [rax+10h], rdx
0x180089227  mov     [rax+18h], r8
0x18008922b  mov     [rax+20h], r9
0x18008922f  push    rbp
0x180089230  lea     rbp, [rax-408h]
0x180089237  sub     rsp, 500h
0x18008923e  mov     rax, cs:__security_cookie
0x180089245  xor     rax, rsp
0x180089248  mov     [rbp+400h+var_10], rax
0x18008924f  xor     eax, eax
0x180089251  lea     r9, [rbp+400h+arg_8]; char *
0x180089258  mov     r8, rcx; unsigned __int16 *
0x18008925b  mov     [rbp+400h+CommandLine], ax
0x18008925f  lea     rcx, [rbp+400h+CommandLine]; unsigned __int16 *
0x180089263  mov     [rsp+500h+ProcessInformation.hProcess], rax
0x180089268  mov     edx, 208h; unsigned __int64
0x18008926d  mov     [rbp+400h+var_12], ax
0x180089274  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180089279  test    eax, eax
0x18008927b  js      loc_180089358
0x180089281  xor     edx, edx; Val
0x180089283  lea     rcx, [rsp+500h+StartupInfo]; void *
0x180089288  lea     r8d, [rdx+68h]; Size
0x18008928c  call    memset_0
0x180089291  mov     eax, 6
0x180089296  mov     [rsp+500h+StartupInfo.cb], 68h ; 'h'
0x18008929e  mov     [rbp+400h+StartupInfo.wShowWindow], ax
0x1800892a2  lea     rdx, [rbp+400h+CommandLine]; lpCommandLine
0x1800892a6  xor     eax, eax
0x1800892a8  mov     [rbp+400h+StartupInfo.dwFlags], 81h
0x1800892af  mov     [rsp+500h+var_498], rax
0x1800892b4  xorps   xmm0, xmm0
0x1800892b7  lea     rax, [rsp+500h+ProcessInformation.hThread]
0x1800892bc  xor     r9d, r9d; lpThreadAttributes
0x1800892bf  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x1800892c4  xor     r8d, r8d; lpProcessAttributes
0x1800892c7  lea     rax, [rsp+500h+StartupInfo]
0x1800892cc  xor     ecx, ecx; lpApplicationName
0x1800892ce  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x1800892d3  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800892dc  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x1800892e5  mov     [rsp+500h+dwCreationFlags], 8; dwCreationFlags
0x1800892ed  mov     [rsp+500h+bInheritHandles], 0; bInheritHandles
0x1800892f5  movups  xmmword ptr [rsp+500h+ProcessInformation.hThread], xmm0
0x1800892fa  call    cs:__imp_CreateProcessW
0x180089300  test    eax, eax
0x180089302  jz      short loc_180089346
0x180089304  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hHandle
0x180089309  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18008930c  call    cs:__imp_WaitForSingleObject
0x180089312  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hProcess
0x180089317  lea     rdx, [rsp+500h+ProcessInformation]; lpExitCode
0x18008931c  mov     dword ptr [rsp+500h+ProcessInformation.hProcess], 0
0x180089324  call    cs:__imp_GetExitCodeProcess
0x18008932a  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x18008932f  call    cs:__imp_CloseHandle
0x180089335  mov     rcx, qword ptr [rsp+500h+ProcessInformation.dwProcessId]; hObject
0x18008933a  call    cs:__imp_CloseHandle
0x180089340  mov     eax, dword ptr [rsp+500h+ProcessInformation.hProcess]
0x180089344  jmp     short loc_18008934C
0x180089346  call    cs:__imp_GetLastError
0x18008934c  test    eax, eax
0x18008934e  jle     short loc_180089358
0x180089350  movzx   eax, ax
0x180089353  or      eax, 80070000h
0x180089358  mov     rcx, [rbp+400h+var_10]
0x18008935f  xor     rcx, rsp; StackCookie
0x180089362  call    __security_check_cookie
0x180089367  add     rsp, 500h
0x18008936e  pop     rbp
0x18008936f  retn
```

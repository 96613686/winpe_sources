# SpoolerUtility::RegisterPrintConfig(ushort)

- ea: `0x180033d00`
- end: `0x180033f03`
- name: `?RegisterPrintConfig@SpoolerUtility@@SAXG@Z`
- size: `515`
- prototype: `void __fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d410`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000f8a8`
- `0x18001cfd4`
- `0x18001d0a0`
- `0x18002b28c`
- `0x1800329ac`
- `0x180032dfc`
- `0x180032ecc`
- `0x180033d00`
- `0x180033f0c`
- `0x1800344f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033e13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033e13`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180033e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180033e4f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180033de1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180033de1`

## string_xrefs

- `0x180033deb`: `CreateProcessAsUser failed!`
- `0x180033dfa`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180033e32`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180033e6e`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180033eac`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180033e9c`: `Process failed to register PrintConfig.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SpoolerUtility::RegisterPrintConfig(unsigned __int16 a1)
{
  __int64 v2; // rax
  WCHAR *v3; // rdx
  const WCHAR *v4; // rcx
  unsigned int v5; // eax
  DWORD v6; // eax
  BOOL ExitCodeProcess; // eax
  const char *v8; // r9
  struct _PROCESS_INFORMATION *v9; // rdx
  const char *dwCreationFlags; // [rsp+28h] [rbp-D8h]
  const char *dwCreationFlagsa; // [rsp+28h] [rbp-D8h]
  const char *dwCreationFlagsb; // [rsp+28h] [rbp-D8h]
  const char *lpEnvironment; // [rsp+30h] [rbp-D0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpApplicationName[4]; // [rsp+E0h] [rbp-20h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR NewFileName[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v20[32]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  SpoolerUtility::_GetPrintConfigLocationForArchitecture(NewFileName);
  SpoolerUtility::_GetRegsvr32PathForArchitecture(lpApplicationName, a1);
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v2 = std::operator+<unsigned short>(v20, lpApplicationName, L" /s ");
  std::operator+<unsigned short>(lpCommandLine, v2, NewFileName);
  std::wstring::_Tidy_deallocate(v20);
  v3 = (WCHAR *)lpCommandLine;
  if ( lpCommandLine[3] > (LPWSTR)7 )
    v3 = lpCommandLine[0];
  v4 = (const WCHAR *)lpApplicationName;
  if ( lpApplicationName[3] > (LPCWSTR)7 )
    v4 = lpApplicationName[0];
  v5 = CreateProcessW(v4, v3, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x45,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)v5,
    (int)"CreateProcessAsUser failed!",
    dwCreationFlags);
  v6 = WaitForSingleObject(ProcessInformation.hProcess, 0x1388u);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x46,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)(v6 != 0),
    (bool)"Error waiting for process exit",
    dwCreationFlagsa);
  ExitCode = 0;
  ExitCodeProcess = GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x48,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)!ExitCodeProcess,
    (bool)"Error retrieving process exit code",
    dwCreationFlagsb);
  v8 = (const char *)ExitCode;
  if ( (int)ExitCode > 0 )
    v8 = (const char *)((unsigned __int16)ExitCode | 0x80070000);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x49,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    v8,
    ExitCode != 0,
    (bool)"Process failed to register PrintConfig.dll",
    lpEnvironment);
  std::wstring::_Tidy_deallocate(lpCommandLine);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v9);
  std::wstring::_Tidy_deallocate(lpApplicationName);
  std::wstring::_Tidy_deallocate(NewFileName);
}

```

## disassembly

```asm
0x180033d00  mov     [rsp-8+arg_0], rbx
0x180033d05  push    rbp
0x180033d06  lea     rbp, [rsp-70h]
0x180033d0b  sub     rsp, 170h
0x180033d12  mov     rax, cs:__security_cookie
0x180033d19  xor     rax, rsp
0x180033d1c  mov     [rbp+70h+var_10], rax
0x180033d20  movzx   ebx, cx
0x180033d23  movzx   edx, cx
0x180033d26  lea     rcx, [rbp+70h+NewFileName]; lpNewFileName
0x180033d2a  call    ?_GetPrintConfigLocationForArchitecture@SpoolerUtility@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z; SpoolerUtility::_GetPrintConfigLocationForArchitecture(ushort)
0x180033d2f  nop
0x180033d30  movzx   edx, bx
0x180033d33  lea     rcx, [rbp+70h+lpApplicationName]
0x180033d37  call    ?_GetRegsvr32PathForArchitecture@SpoolerUtility@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z; SpoolerUtility::_GetRegsvr32PathForArchitecture(ushort)
0x180033d3c  nop
0x180033d3d  xor     edx, edx; Val
0x180033d3f  lea     r8d, [rdx+64h]; Size
0x180033d43  lea     rcx, [rsp+170h+StartupInfo+4]; void *
0x180033d48  call    memset_0
0x180033d4d  mov     [rsp+170h+StartupInfo.cb], 68h ; 'h'
0x180033d55  xorps   xmm0, xmm0
0x180033d58  xor     eax, eax
0x180033d5a  movups  xmmword ptr [rsp+170h+ProcessInformation.hProcess], xmm0
0x180033d5f  mov     qword ptr [rsp+170h+ProcessInformation.dwProcessId], rax
0x180033d64  lea     r8, aS; " /s "
0x180033d6b  lea     rdx, [rbp+70h+lpApplicationName]
0x180033d6f  lea     rcx, [rbp+70h+var_30]
0x180033d73  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180033d78  nop
0x180033d79  lea     r8, [rbp+70h+NewFileName]
0x180033d7d  mov     rdx, rax
0x180033d80  lea     rcx, [rbp+70h+lpCommandLine]
0x180033d84  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180033d89  nop
0x180033d8a  lea     rcx, [rbp+70h+var_30]
0x180033d8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033d93  lea     rdx, [rbp+70h+lpCommandLine]
0x180033d97  cmp     [rbp+70h+var_58], 7
0x180033d9c  cmova   rdx, [rbp+70h+lpCommandLine]; lpCommandLine
0x180033da1  lea     rcx, [rbp+70h+lpApplicationName]
0x180033da5  cmp     [rbp+70h+var_78], 7
0x180033daa  cmova   rcx, [rbp+70h+lpApplicationName]; lpApplicationName
0x180033daf  lea     rax, [rsp+170h+ProcessInformation]
0x180033db4  mov     [rsp+170h+lpProcessInformation], rax; lpProcessInformation
0x180033db9  lea     rax, [rsp+170h+StartupInfo]
0x180033dbe  mov     [rsp+170h+lpStartupInfo], rax; lpStartupInfo
0x180033dc3  xor     ebx, ebx
0x180033dc5  mov     [rsp+170h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x180033dca  mov     [rsp+170h+lpEnvironment], rbx; char *
0x180033dcf  mov     [rsp+170h+dwCreationFlags], 8000000h; char *
0x180033dd7  mov     [rsp+170h+bInheritHandles], ebx; bInheritHandles
0x180033ddb  xor     r9d, r9d; lpThreadAttributes
0x180033dde  xor     r8d, r8d; lpProcessAttributes
0x180033de1  call    cs:__imp_CreateProcessW
0x180033de7  mov     rcx, [rbp+78h]; this
0x180033deb  lea     rdx, aCreateprocessa; "CreateProcessAsUser failed!"
0x180033df2  mov     qword ptr [rsp+170h+bInheritHandles], rdx; int
0x180033df7  mov     r9d, eax; char *
0x180033dfa  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033e01  lea     edx, [rbx+45h]; void *
0x180033e04  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180033e09  mov     edx, 1388h; dwMilliseconds
0x180033e0e  mov     rcx, [rsp+170h+ProcessInformation.hProcess]; hHandle
0x180033e13  call    cs:__imp_WaitForSingleObject
0x180033e19  test    eax, eax
0x180033e1b  setnz   al
0x180033e1e  mov     rcx, [rbp+78h]; this
0x180033e22  lea     rdx, aErrorWaitingFo; "Error waiting for process exit"
0x180033e29  mov     qword ptr [rsp+170h+bInheritHandles], rdx; bool
0x180033e2e  movzx   r9d, al; char *
0x180033e32  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033e39  lea     edx, [rbx+46h]; void *
0x180033e3c  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180033e41  mov     [rsp+170h+ExitCode], ebx
0x180033e45  lea     rdx, [rsp+170h+ExitCode]; lpExitCode
0x180033e4a  mov     rcx, [rsp+170h+ProcessInformation.hProcess]; hProcess
0x180033e4f  call    cs:__imp_GetExitCodeProcess
0x180033e55  test    eax, eax
0x180033e57  setz    al
0x180033e5a  mov     rcx, [rbp+78h]; this
0x180033e5e  lea     rdx, aErrorRetrievin; "Error retrieving process exit code"
0x180033e65  mov     qword ptr [rsp+170h+bInheritHandles], rdx; bool
0x180033e6a  movzx   r9d, al; char *
0x180033e6e  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033e75  lea     edx, [rbx+48h]; void *
0x180033e78  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180033e7d  mov     r9d, [rsp+170h+ExitCode]
0x180033e82  test    r9d, r9d
0x180033e85  setnz   al
0x180033e88  test    r9d, r9d
0x180033e8b  jle     short loc_180033E98
0x180033e8d  movzx   r9d, r9w
0x180033e91  or      r9d, 80070000h; char *
0x180033e98  mov     rcx, [rbp+78h]; this
0x180033e9c  lea     rdx, aProcessFailedT; "Process failed to register PrintConfig."...
0x180033ea3  mov     qword ptr [rsp+170h+dwCreationFlags], rdx; bool
0x180033ea8  mov     byte ptr [rsp+170h+bInheritHandles], al; char
0x180033eac  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033eb3  mov     edx, 49h ; 'I'; void *
0x180033eb8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180033ebd  nop
0x180033ebe  lea     rcx, [rbp+70h+lpCommandLine]
0x180033ec2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033ec7  nop
0x180033ec8  lea     rcx, [rsp+170h+ProcessInformation]; this
0x180033ecd  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180033ed2  nop
0x180033ed3  lea     rcx, [rbp+70h+lpApplicationName]
0x180033ed7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033edc  nop
0x180033edd  lea     rcx, [rbp+70h+NewFileName]
0x180033ee1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033ee6  mov     rcx, [rbp+70h+var_10]
0x180033eea  xor     rcx, rsp; StackCookie
0x180033eed  call    __security_check_cookie
0x180033ef2  mov     rbx, [rsp+170h+arg_0]
0x180033efa  add     rsp, 170h
0x180033f01  pop     rbp
0x180033f02  retn
```

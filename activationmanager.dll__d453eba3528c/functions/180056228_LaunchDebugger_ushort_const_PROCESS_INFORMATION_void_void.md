# LaunchDebugger(ushort const *,_PROCESS_INFORMATION *,void *,void * *)

- ea: `0x180056228`
- end: `0x1800565e7`
- name: `?LaunchDebugger@@YAXPEBGPEAU_PROCESS_INFORMATION@@PEAXPEAPEAX@Z`
- size: `959`
- prototype: `void(const unsigned __int16 *, struct _PROCESS_INFORMATION *, void *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008d9c0`

## callees

- `0x180010514`
- `0x180035ee8`
- `0x18003a02c`
- `0x180056208`
- `0x180056228`
- `0x1800565f0`
- `0x180056620`
- `0x18005ae90`
- `0x18005ba40`
- `0x180067e64`
- `0x18007638c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800563c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056562`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056562`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18005639d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180056505`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18005639d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180056505`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005658d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005658d`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18005642a`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18005642a`
- `ntdll!RtlNtStatusToDosError` at `0x180056432`
- `ntdll!RtlNtStatusToDosError` at `0x180056432`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180056301`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180056301`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800565ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800565ba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800563d3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800563d3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180056493`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180056493`
- `profapi!__imp_CreateEnvBlock` at `0x18005627c`
- `profapi!__imp_CreateEnvBlock` at `0x18005627c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall LaunchDebugger(const unsigned __int16 *a1, struct _PROCESS_INFORMATION *a2, void *a3, void **a4)
{
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  struct _PROCESS_INFORMATION *v10; // rdx
  signed int LastError; // eax
  signed int v12; // ebx
  NTSTATUS v13; // eax
  signed int v14; // eax
  HRESULT v15; // eax
  const char *v16; // r9
  HANDLE CurrentProcess; // rbx
  HANDLE v18; // rax
  const char *v19; // r9
  int lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  int lpThreadAttributesa; // [rsp+20h] [rbp-E0h]
  int lpThreadAttributesb; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPathOut; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpEnvironment; // [rsp+68h] [rbp-98h] BYREF
  char v25; // [rsp+71h] [rbp-8Fh]
  struct _PROCESS_INFORMATION *v26; // [rsp+78h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _PROCESS_INFORMATION **v28; // [rsp+98h] [rbp-68h]
  char v29; // [rsp+A0h] [rbp-60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR CommandLine[296]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR pszPathIn[264]; // [rsp+370h] [rbp+270h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5B8h] [rbp+4B8h]

  v26 = a2;
  v28 = &v26;
  v29 = 1;
  lpEnvironment = 0;
  v7 = CreateEnvBlock(&lpEnvironment, a3, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      (const char *)(unsigned int)v7,
      lpThreadAttributes);
  memset_0(CommandLine, 0, 0x244u);
  lpThreadAttributesa = v26->dwProcessId;
  v8 = StringCchPrintfW(CommandLine, 0x122u, L"%s -p %d -tid %d", a1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      (const char *)(unsigned int)v8,
      lpThreadAttributesa);
  if ( !ImpersonateLoggedOnUser(a3) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      v9);
  v25 = 1;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 128;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessAsUserW(a3, 0, CommandLine, 0, 0, 0, 0x410u, lpEnvironment, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( GetLastError() == 2 && PathIsRelativeW(CommandLine) )
    {
      memset_0(pszPathIn, 0, 0x20Au);
      ppszPathOut = 0;
      v13 = RtlExpandEnvironmentStrings(lpEnvironment, L"%localappdata%\\Microsoft\\WindowsApps", 36, pszPathIn);
      v14 = RtlNtStatusToDosError(v13);
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 >= 0 )
      {
        ppszPathOut = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ppszPathOut,
          0);
        v15 = PathAllocCombine(pszPathIn, CommandLine, 1u, &ppszPathOut);
        if ( v15 >= 0 )
        {
          if ( !CreateProcessAsUserW(
                  a3,
                  0,
                  ppszPathOut,
                  0,
                  0,
                  0,
                  0x410u,
                  lpEnvironment,
                  0,
                  &StartupInfo,
                  &ProcessInformation) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xFF,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
              v16);
          v12 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
            (const char *)(unsigned int)v15,
            261);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
          (const char *)(unsigned int)v14,
          261);
      }
    }
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
        (const char *)(unsigned int)v12,
        lpThreadAttributesb);
  }
  if ( a4 )
  {
    CurrentProcess = GetCurrentProcess();
    v18 = GetCurrentProcess();
    if ( !DuplicateHandle(v18, ProcessInformation.hProcess, CurrentProcess, a4, 0, 0, 2u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x112,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
        v19);
  }
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v10);
  RevertToSelf();
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpEnvironment);
}

```

## disassembly

```asm
0x180056228  push    rbp
0x18005622a  push    rbx
0x18005622b  push    rsi
0x18005622c  push    rdi
0x18005622d  lea     rbp, [rsp-498h]
0x180056235  sub     rsp, 598h
0x18005623c  mov     rax, cs:__security_cookie
0x180056243  xor     rax, rsp
0x180056246  mov     [rbp+4B0h+var_30], rax
0x18005624d  mov     rsi, r9
0x180056250  mov     rdi, r8
0x180056253  mov     rbx, rcx
0x180056256  mov     [rsp+5B0h+var_538], rdx
0x18005625b  lea     rax, [rsp+5B0h+var_538]
0x180056260  mov     [rbp+4B0h+var_518], rax
0x180056264  mov     [rbp+4B0h+var_510], 1
0x180056268  mov     [rsp+5B0h+var_548], 0
0x180056271  xor     r8d, r8d
0x180056274  mov     rdx, rdi
0x180056277  lea     rcx, [rsp+5B0h+var_548]
0x18005627c  call    cs:__imp_CreateEnvBlock
0x180056282  mov     rcx, [rbp+4B8h]; this
0x180056289  test    eax, eax
0x18005628b  jns     short loc_1800562A2
0x18005628d  mov     r9d, eax; char *
0x180056290  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x180056297  mov     edx, 0B8h; void *
0x18005629c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800562a2  xor     edx, edx; Val
0x1800562a4  mov     r8d, 244h; Size
0x1800562aa  lea     rcx, [rbp+4B0h+CommandLine]; void *
0x1800562ae  call    memset_0
0x1800562b3  mov     rcx, [rsp+5B0h+var_538]
0x1800562b8  mov     eax, [rcx+14h]
0x1800562bb  mov     [rsp+5B0h+bInheritHandles], eax
0x1800562bf  mov     eax, [rcx+10h]
0x1800562c2  mov     dword ptr [rsp+5B0h+lpThreadAttributes], eax; int
0x1800562c6  mov     r9, rbx
0x1800562c9  lea     r8, aSPDTidD; "%s -p %d -tid %d"
0x1800562d0  mov     edx, 122h; unsigned __int64
0x1800562d5  lea     rcx, [rbp+4B0h+CommandLine]; unsigned __int16 *
0x1800562d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800562de  mov     rcx, [rbp+4B8h]; this
0x1800562e5  test    eax, eax
0x1800562e7  jns     short loc_1800562FE
0x1800562e9  mov     r9d, eax; char *
0x1800562ec  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800562f3  mov     edx, 0BFh; void *
0x1800562f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800562fe  mov     rcx, rdi; hToken
0x180056301  call    cs:__imp_ImpersonateLoggedOnUser
0x180056307  mov     rcx, [rbp+4B8h]; this
0x18005630e  test    eax, eax
0x180056310  jnz     short loc_180056324
0x180056312  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x180056319  mov     edx, 0C3h; void *
0x18005631e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180056324  mov     [rsp+5B0h+var_53F], 1
0x180056329  mov     ebx, 68h ; 'h'
0x18005632e  mov     r8d, ebx; Size
0x180056331  xor     edx, edx; Val
0x180056333  lea     rcx, [rbp+4B0h+StartupInfo]; void *
0x180056337  call    memset_0
0x18005633c  mov     [rbp+4B0h+StartupInfo.cb], ebx
0x18005633f  mov     [rbp+4B0h+StartupInfo.dwFlags], 80h
0x180056346  xorps   xmm0, xmm0
0x180056349  xor     eax, eax
0x18005634b  movups  xmmword ptr [rbp+4B0h+ProcessInformation.hProcess], xmm0
0x18005634f  mov     qword ptr [rbp+4B0h+ProcessInformation.dwProcessId], rax
0x180056353  lea     rax, [rbp+4B0h+ProcessInformation]
0x180056357  mov     [rsp+5B0h+lpProcessInformation], rax; lpProcessInformation
0x18005635c  lea     rax, [rbp+4B0h+StartupInfo]
0x180056360  mov     [rsp+5B0h+lpStartupInfo], rax; lpStartupInfo
0x180056365  mov     [rsp+5B0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18005636e  mov     rax, [rsp+5B0h+var_548]
0x180056373  mov     [rsp+5B0h+lpEnvironment], rax; lpEnvironment
0x180056378  mov     [rsp+5B0h+dwCreationFlags], 410h; dwCreationFlags
0x180056380  mov     [rsp+5B0h+bInheritHandles], 0; bInheritHandles
0x180056388  mov     [rsp+5B0h+lpThreadAttributes], 0; lpThreadAttributes
0x180056391  xor     r9d, r9d; lpProcessAttributes
0x180056394  lea     r8, [rbp+4B0h+CommandLine]; lpCommandLine
0x180056398  xor     edx, edx; lpApplicationName
0x18005639a  mov     rcx, rdi; hToken
0x18005639d  call    cs:__imp_CreateProcessAsUserW
0x1800563a3  test    eax, eax
0x1800563a5  jnz     loc_180056554
0x1800563ab  call    cs:__imp_GetLastError
0x1800563b1  mov     ebx, eax
0x1800563b3  test    eax, eax
0x1800563b5  jle     short loc_1800563C0
0x1800563b7  movzx   ebx, ax
0x1800563ba  or      ebx, 80070000h
0x1800563c0  call    cs:__imp_GetLastError
0x1800563c6  cmp     eax, 2
0x1800563c9  jnz     loc_180056534
0x1800563cf  lea     rcx, [rbp+4B0h+CommandLine]; pszPath
0x1800563d3  call    cs:__imp_PathIsRelativeW
0x1800563d9  test    eax, eax
0x1800563db  jz      loc_180056534
0x1800563e1  xor     edx, edx; Val
0x1800563e3  mov     r8d, 20Ah; Size
0x1800563e9  lea     rcx, [rbp+4B0h+pszPathIn]; void *
0x1800563f0  call    memset_0
0x1800563f5  mov     [rsp+5B0h+ppszPathOut], 0
0x1800563fe  lea     rax, [rsp+5B0h+ppszPathOut]
0x180056403  mov     qword ptr [rsp+5B0h+bInheritHandles], rax
0x180056408  mov     [rsp+5B0h+lpThreadAttributes], 105h; int
0x180056411  lea     r9, [rbp+4B0h+pszPathIn]
0x180056418  mov     r8d, 24h ; '$'
0x18005641e  lea     rdx, aLocalappdataMi; "%localappdata%\\Microsoft\\WindowsApps"
0x180056425  mov     rcx, [rsp+5B0h+var_548]
0x18005642a  call    cs:__imp_RtlExpandEnvironmentStrings
0x180056430  mov     ecx, eax; Status
0x180056432  call    cs:__imp_RtlNtStatusToDosError
0x180056438  test    eax, eax
0x18005643a  jle     short loc_180056444
0x18005643c  movzx   eax, ax
0x18005643f  or      eax, 80070000h
0x180056444  mov     rcx, [rbp+4B8h]; this
0x18005644b  test    eax, eax
0x18005644d  jns     short loc_180056468
0x18005644f  mov     r9d, eax; char *
0x180056452  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x180056459  mov     edx, 0EBh; void *
0x18005645e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180056463  jmp     loc_180056534
0x180056468  mov     [rsp+5B0h+ppszPathOut], 0
0x180056471  xor     edx, edx
0x180056473  lea     rcx, [rsp+5B0h+ppszPathOut]
0x180056478  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005647d  lea     r9, [rsp+5B0h+ppszPathOut]; ppszPathOut
0x180056482  mov     r8d, 1; dwFlags
0x180056488  lea     rdx, [rbp+4B0h+CommandLine]; pszMore
0x18005648c  lea     rcx, [rbp+4B0h+pszPathIn]; pszPathIn
0x180056493  call    cs:__imp_PathAllocCombine
0x180056499  mov     rcx, [rbp+4B8h]; this
0x1800564a0  test    eax, eax
0x1800564a2  jns     short loc_1800564BA
0x1800564a4  mov     r9d, eax; char *
0x1800564a7  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800564ae  mov     edx, 0F2h; void *
0x1800564b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800564b8  jmp     short loc_18005652A
0x1800564ba  mov     rax, [rsp+5B0h+var_548]
0x1800564bf  lea     rcx, [rbp+4B0h+ProcessInformation]
0x1800564c3  mov     [rsp+5B0h+lpProcessInformation], rcx; lpProcessInformation
0x1800564c8  lea     rcx, [rbp+4B0h+StartupInfo]
0x1800564cc  mov     [rsp+5B0h+lpStartupInfo], rcx; lpStartupInfo
0x1800564d1  mov     [rsp+5B0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800564da  mov     [rsp+5B0h+lpEnvironment], rax; lpEnvironment
0x1800564df  mov     [rsp+5B0h+dwCreationFlags], 410h; dwCreationFlags
0x1800564e7  mov     [rsp+5B0h+bInheritHandles], 0; bInheritHandles
0x1800564ef  mov     [rsp+5B0h+lpThreadAttributes], 0; int
0x1800564f8  xor     r9d, r9d; lpProcessAttributes
0x1800564fb  mov     r8, [rsp+5B0h+ppszPathOut]; lpCommandLine
0x180056500  xor     edx, edx; lpApplicationName
0x180056502  mov     rcx, rdi; hToken
0x180056505  call    cs:__imp_CreateProcessAsUserW
0x18005650b  mov     rcx, [rbp+4B8h]; this
0x180056512  test    eax, eax
0x180056514  jnz     short loc_180056528
0x180056516  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005651d  mov     edx, 0FFh; void *
0x180056522  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180056528  xor     ebx, ebx
0x18005652a  lea     rcx, [rsp+5B0h+ppszPathOut]
0x18005652f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180056534  mov     rcx, [rbp+4B8h]; this
0x18005653b  test    ebx, ebx
0x18005653d  jns     short loc_180056554
0x18005653f  mov     r9d, ebx; char *
0x180056542  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x180056549  mov     edx, 106h; void *
0x18005654e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056554  test    rsi, rsi
0x180056557  jz      short loc_1800565B0
0x180056559  call    cs:__imp_GetCurrentProcess
0x18005655f  mov     rbx, rax
0x180056562  call    cs:__imp_GetCurrentProcess
0x180056568  mov     [rsp+5B0h+dwCreationFlags], 2; dwOptions
0x180056570  mov     [rsp+5B0h+bInheritHandles], 0; bInheritHandle
0x180056578  mov     dword ptr [rsp+5B0h+lpThreadAttributes], 0; dwDesiredAccess
0x180056580  mov     r9, rsi; lpTargetHandle
0x180056583  mov     r8, rbx; hTargetProcessHandle
0x180056586  mov     rdx, [rbp+4B0h+ProcessInformation.hProcess]; hSourceHandle
0x18005658a  mov     rcx, rax; hSourceProcessHandle
0x18005658d  call    cs:__imp_DuplicateHandle
0x180056593  mov     rcx, [rbp+4B8h]; this
0x18005659a  test    eax, eax
0x18005659c  jnz     short loc_1800565B0
0x18005659e  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800565a5  mov     edx, 112h; void *
0x1800565aa  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800565b0  lea     rcx, [rbp+4B0h+ProcessInformation]; this
0x1800565b4  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1800565b9  nop
0x1800565ba  call    cs:__imp_RevertToSelf
0x1800565c0  nop
0x1800565c1  lea     rcx, [rsp+5B0h+var_548]
0x1800565c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?DestroyEnvBlock@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&DestroyEnvBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800565cb  nop
0x1800565cc  mov     rcx, [rbp+4B0h+var_30]
0x1800565d3  xor     rcx, rsp; StackCookie
0x1800565d6  call    __security_check_cookie
0x1800565db  add     rsp, 598h
0x1800565e2  pop     rdi
0x1800565e3  pop     rsi
0x1800565e4  pop     rbx
0x1800565e5  pop     rbp
0x1800565e6  retn
```

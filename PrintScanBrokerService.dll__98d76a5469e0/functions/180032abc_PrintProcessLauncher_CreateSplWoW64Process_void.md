# PrintProcessLauncher::_CreateSplWoW64Process(void)

- ea: `0x180032abc`
- end: `0x180032df4`
- name: `?_CreateSplWoW64Process@PrintProcessLauncher@@AEAAXXZ`
- size: `824`
- prototype: `void __fastcall(PrintProcessLauncher *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800329dc`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x1800082c8`
- `0x18000e5f4`
- `0x18001cfd4`
- `0x18001d058`
- `0x18001d0a0`
- `0x18002b28c`
- `0x18003292c`
- `0x1800329ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180032b56`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180032b56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032b8f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032b8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180032c04`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180032c04`
- `KERNELBASE!CreateProcessAsUserW` at `0x180032d82`
- `KERNELBASE!CreateProcessAsUserW` at `0x180032d82`
- `USERENV!DestroyEnvironmentBlock` at `0x180032dbc`
- `USERENV!DestroyEnvironmentBlock` at `0x180032dbc`
- `USERENV!CreateEnvironmentBlock` at `0x180032cd1`
- `USERENV!CreateEnvironmentBlock` at `0x180032cd1`

## string_xrefs

- `0x180032b3a`: `onecoreuap\printscan\print\printscanbroker\class\printprocesslauncher.cpp`
- `0x180032c16`: `GetSystemWindowsDirectory failed!`
- `0x180032b6b`: `CreateMutex failed!`
- `0x180032ca0`: `StringCchPrintf (command line) failed!`
- `0x180032d8f`: `CreateProcessAsUser failed!`
- `0x180032cde`: `CreateEnvironmentBlock failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrintProcessLauncher::_CreateSplWoW64Process(PrintProcessLauncher *this)
{
  unsigned int v2; // eax
  DWORD v3; // eax
  UINT SystemWindowsDirectoryW; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  struct _PROCESS_INFORMATION *v9; // rdx
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  const char *bInheritHandles; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlesa; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlesb; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlesc; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlesd; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlese; // [rsp+28h] [rbp-D8h]
  const char *dwCreationFlags; // [rsp+30h] [rbp-D0h]
  LPVOID Environment; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE MutexW; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  LPVOID *p_Environment; // [rsp+88h] [rbp-78h]
  char v22; // [rsp+90h] [rbp-70h]
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[64]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Buffer[264]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR ApplicationName[264]; // [rsp+3A0h] [rbp+2A0h] BYREF
  WCHAR CommandLine[520]; // [rsp+5B0h] [rbp+4B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9E8h] [rbp+8E8h]

  memset_0(Name, 0, 0x78u);
  v2 = StringCchPrintfW(
         Name,
         0x3Cu,
         L"Local\\WinSpl64To32Mutex_%x_%x_%x",
         *((unsigned int *)this + 10),
         *((_DWORD *)this + 11),
         0x2000);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1A,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)v2,
    (int)"StringCchPrintf (mutext name) failed!",
    bInheritHandles);
  MutexW = CreateMutexW(0, 0, Name);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    retaddr,
    29,
    "onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    MutexW,
    "CreateMutex failed!");
  v3 = WaitForSingleObject(MutexW, 0x2710u);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x1E,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)0x800705B4LL,
    v3 != 0,
    (bool)"CreateMutex failed!",
    dwCreationFlags);
  memset_0(ApplicationName, 0, 0x20Au);
  memset_0(Buffer, 0, 0x20Au);
  memset_0(CommandLine, 0, sizeof(CommandLine));
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x23,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)(SystemWindowsDirectoryW == 0),
    (bool)"GetSystemWindowsDirectory failed!",
    bInheritHandlesa);
  v5 = StringCchPrintfW(ApplicationName, 0x105u, L"%ws\\splwow64.exe", Buffer);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x24,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)v5,
    (int)"StringCchPrintf (process name) failed!",
    bInheritHandlesb);
  LODWORD(lpThreadAttributes) = *((_DWORD *)this + 12);
  v6 = StringCchPrintfW(CommandLine, 0x208u, L"%ws\\splwow64.exe %d", Buffer, lpThreadAttributes);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x25,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)v6,
    (int)"StringCchPrintf (command line) failed!",
    bInheritHandlesc);
  Environment = 0;
  v7 = CreateEnvironmentBlock(&Environment, *((HANDLE *)this + 7), 0);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x28,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)v7,
    (int)"CreateEnvironmentBlock failed!",
    bInheritHandlesd);
  p_Environment = &Environment;
  v22 = 1;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v8 = CreateProcessAsUserW(
         *((HANDLE *)this + 7),
         ApplicationName,
         CommandLine,
         0,
         0,
         0,
         0xC000408u,
         Environment,
         Buffer,
         &StartupInfo,
         &ProcessInformation);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printprocesslauncher.cpp",
    (const char *)v8,
    (int)"CreateProcessAsUser failed!",
    bInheritHandlese);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v9);
  DestroyEnvironmentBlock(Environment);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&MutexW);
}

```

## disassembly

```asm
0x180032abc  mov     [rsp-8+arg_8], rbx
0x180032ac1  mov     [rsp-8+arg_10], rsi
0x180032ac6  push    rbp
0x180032ac7  push    rdi
0x180032ac8  push    r15
0x180032aca  lea     rbp, [rsp-8D0h]
0x180032ad2  sub     rsp, 9D0h
0x180032ad9  mov     rax, cs:__security_cookie
0x180032ae0  xor     rax, rsp
0x180032ae3  mov     [rbp+8E0h+var_20], rax
0x180032aea  mov     rdi, rcx
0x180032aed  xor     edx, edx; Val
0x180032aef  lea     r8d, [rdx+78h]; Size
0x180032af3  lea     rcx, [rbp+8E0h+Name]; void *
0x180032af7  call    memset_0
0x180032afc  mov     [rsp+9E0h+bInheritHandles], 2000h; char *
0x180032b04  mov     eax, [rdi+2Ch]
0x180032b07  mov     dword ptr [rsp+9E0h+lpThreadAttributes], eax
0x180032b0b  mov     r9d, [rdi+28h]
0x180032b0f  lea     r8, aLocalWinspl64t; "Local\\WinSpl64To32Mutex_%x_%x_%x"
0x180032b16  mov     edx, 3Ch ; '<'; unsigned __int64
0x180032b1b  lea     rcx, [rbp+8E0h+Name]; unsigned __int16 *
0x180032b1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032b24  mov     rcx, [rbp+8E8h]; this
0x180032b2b  lea     rdx, aStringcchprint_3; "StringCchPrintf (mutext name) failed!"
0x180032b32  mov     [rsp+9E0h+lpThreadAttributes], rdx; int
0x180032b37  mov     r9d, eax; char *
0x180032b3a  lea     r15, aOnecoreuapPrin_4; "onecoreuap\\printscan\\print\\printscan"...
0x180032b41  mov     r8, r15; unsigned int
0x180032b44  mov     edx, 1Ah; void *
0x180032b49  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032b4e  lea     r8, [rbp+8E0h+Name]; lpName
0x180032b52  xor     edx, edx; bInitialOwner
0x180032b54  xor     ecx, ecx; lpMutexAttributes
0x180032b56  call    cs:__imp_CreateMutexW
0x180032b5c  mov     rbx, rax
0x180032b5f  mov     [rsp+9E0h+var_978], rax
0x180032b64  mov     rcx, [rbp+8E8h]
0x180032b6b  lea     rsi, aCreatemutexFai; "CreateMutex failed!"
0x180032b72  mov     [rsp+9E0h+lpThreadAttributes], rsi
0x180032b77  mov     r9, rax
0x180032b7a  mov     r8, r15
0x180032b7d  mov     edx, 1Dh
0x180032b82  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x180032b87  mov     edx, 2710h; dwMilliseconds
0x180032b8c  mov     rcx, rbx; hHandle
0x180032b8f  call    cs:__imp_WaitForSingleObject
0x180032b95  test    eax, eax
0x180032b97  setnz   al
0x180032b9a  mov     rcx, [rbp+8E8h]; this
0x180032ba1  mov     qword ptr [rsp+9E0h+bInheritHandles], rsi; char *
0x180032ba6  mov     byte ptr [rsp+9E0h+lpThreadAttributes], al; char
0x180032baa  mov     r9d, 800705B4h; char *
0x180032bb0  mov     r8, r15; unsigned int
0x180032bb3  mov     edx, 1Eh; void *
0x180032bb8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180032bbd  mov     ebx, 20Ah
0x180032bc2  mov     r8d, ebx; Size
0x180032bc5  xor     edx, edx; Val
0x180032bc7  lea     rcx, [rbp+8E0h+ApplicationName]; void *
0x180032bce  call    memset_0
0x180032bd3  mov     r8d, ebx; Size
0x180032bd6  xor     edx, edx; Val
0x180032bd8  lea     rcx, [rbp+8E0h+Buffer]; void *
0x180032bdf  call    memset_0
0x180032be4  xor     edx, edx; Val
0x180032be6  mov     r8d, 410h; Size
0x180032bec  lea     rcx, [rbp+8E0h+CommandLine]; void *
0x180032bf3  call    memset_0
0x180032bf8  mov     edx, 104h; uSize
0x180032bfd  lea     rcx, [rbp+8E0h+Buffer]; lpBuffer
0x180032c04  call    cs:__imp_GetSystemWindowsDirectoryW
0x180032c0a  test    eax, eax
0x180032c0c  setz    al
0x180032c0f  mov     rcx, [rbp+8E8h]; this
0x180032c16  lea     rdx, aGetsystemwindo; "GetSystemWindowsDirectory failed!"
0x180032c1d  mov     [rsp+9E0h+lpThreadAttributes], rdx; bool
0x180032c22  movzx   r9d, al; char *
0x180032c26  mov     r8, r15; unsigned int
0x180032c29  mov     edx, 23h ; '#'; void *
0x180032c2e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180032c33  lea     r9, [rbp+8E0h+Buffer]
0x180032c3a  lea     r8, aWsSplwow64Exe; "%ws\\splwow64.exe"
0x180032c41  mov     edx, 105h; unsigned __int64
0x180032c46  lea     rcx, [rbp+8E0h+ApplicationName]; unsigned __int16 *
0x180032c4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032c52  mov     rcx, [rbp+8E8h]; this
0x180032c59  lea     rdx, aStringcchprint_2; "StringCchPrintf (process name) failed!"
0x180032c60  mov     [rsp+9E0h+lpThreadAttributes], rdx; int
0x180032c65  mov     r9d, eax; char *
0x180032c68  mov     r8, r15; unsigned int
0x180032c6b  mov     edx, 24h ; '$'; void *
0x180032c70  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032c75  mov     eax, [rdi+30h]
0x180032c78  mov     dword ptr [rsp+9E0h+lpThreadAttributes], eax
0x180032c7c  lea     r9, [rbp+8E0h+Buffer]
0x180032c83  lea     r8, aWsSplwow64ExeD; "%ws\\splwow64.exe %d"
0x180032c8a  lea     edx, [rbx-2]; unsigned __int64
0x180032c8d  lea     rcx, [rbp+8E0h+CommandLine]; unsigned __int16 *
0x180032c94  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032c99  mov     rcx, [rbp+8E8h]; this
0x180032ca0  lea     rdx, aStringcchprint_0; "StringCchPrintf (command line) failed!"
0x180032ca7  mov     [rsp+9E0h+lpThreadAttributes], rdx; int
0x180032cac  mov     r9d, eax; char *
0x180032caf  mov     r8, r15; unsigned int
0x180032cb2  mov     edx, 25h ; '%'; void *
0x180032cb7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032cbc  mov     [rsp+9E0h+Environment], 0
0x180032cc5  xor     r8d, r8d; bInherit
0x180032cc8  mov     rdx, [rdi+38h]; hToken
0x180032ccc  lea     rcx, [rsp+9E0h+Environment]; lpEnvironment
0x180032cd1  call    cs:__imp_CreateEnvironmentBlock
0x180032cd7  mov     rcx, [rbp+8E8h]; this
0x180032cde  lea     rdx, aCreateenvironm; "CreateEnvironmentBlock failed!"
0x180032ce5  mov     [rsp+9E0h+lpThreadAttributes], rdx; int
0x180032cea  mov     r9d, eax; char *
0x180032ced  mov     r8, r15; unsigned int
0x180032cf0  mov     edx, 28h ; '('; void *
0x180032cf5  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180032cfa  lea     rax, [rsp+9E0h+Environment]
0x180032cff  mov     [rbp+8E0h+var_958], rax
0x180032d03  mov     [rbp+8E0h+var_950], 1
0x180032d07  xor     edx, edx; Val
0x180032d09  lea     r8d, [rdx+64h]; Size
0x180032d0d  lea     rcx, [rbp+8E0h+StartupInfo+4]; void *
0x180032d11  call    memset_0
0x180032d16  mov     [rbp+8E0h+StartupInfo.cb], 68h ; 'h'
0x180032d1d  xorps   xmm0, xmm0
0x180032d20  xor     eax, eax
0x180032d22  movups  xmmword ptr [rsp+9E0h+ProcessInformation.hProcess], xmm0
0x180032d27  mov     qword ptr [rbp+8E0h+ProcessInformation.dwProcessId], rax
0x180032d2b  mov     rax, [rsp+9E0h+Environment]
0x180032d30  lea     rcx, [rsp+9E0h+ProcessInformation]
0x180032d35  mov     [rsp+9E0h+lpProcessInformation], rcx; lpProcessInformation
0x180032d3a  lea     rcx, [rbp+8E0h+StartupInfo]
0x180032d3e  mov     [rsp+9E0h+lpStartupInfo], rcx; lpStartupInfo
0x180032d43  lea     rcx, [rbp+8E0h+Buffer]
0x180032d4a  mov     [rsp+9E0h+lpCurrentDirectory], rcx; lpCurrentDirectory
0x180032d4f  mov     [rsp+9E0h+lpEnvironment], rax; lpEnvironment
0x180032d54  mov     dword ptr [rsp+9E0h+dwCreationFlags], 0C000408h; dwCreationFlags
0x180032d5c  mov     [rsp+9E0h+bInheritHandles], 0; char *
0x180032d64  mov     [rsp+9E0h+lpThreadAttributes], 0; lpThreadAttributes
0x180032d6d  xor     r9d, r9d; lpProcessAttributes
0x180032d70  lea     r8, [rbp+8E0h+CommandLine]; lpCommandLine
0x180032d77  lea     rdx, [rbp+8E0h+ApplicationName]; lpApplicationName
0x180032d7e  mov     rcx, [rdi+38h]; hToken
0x180032d82  call    cs:__imp_CreateProcessAsUserW
0x180032d88  mov     rcx, [rbp+8E8h]; this
0x180032d8f  lea     rdx, aCreateprocessa; "CreateProcessAsUser failed!"
0x180032d96  mov     [rsp+9E0h+lpThreadAttributes], rdx; int
0x180032d9b  mov     r9d, eax; char *
0x180032d9e  mov     r8, r15; unsigned int
0x180032da1  mov     edx, 3Bh ; ';'; void *
0x180032da6  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180032dab  nop
0x180032dac  lea     rcx, [rsp+9E0h+ProcessInformation]; this
0x180032db1  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180032db6  nop
0x180032db7  mov     rcx, [rsp+9E0h+Environment]; lpEnvironment
0x180032dbc  call    cs:__imp_DestroyEnvironmentBlock
0x180032dc2  nop
0x180032dc3  lea     rcx, [rsp+9E0h+var_978]
0x180032dc8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032dcd  mov     rcx, [rbp+8E0h+var_20]
0x180032dd4  xor     rcx, rsp; StackCookie
0x180032dd7  call    __security_check_cookie
0x180032ddc  lea     r11, [rsp+9E0h+var_10]
0x180032de4  mov     rbx, [r11+28h]
0x180032de8  mov     rsi, [r11+30h]
0x180032dec  mov     rsp, r11
0x180032def  pop     r15
0x180032df1  pop     rdi
0x180032df2  pop     rbp
0x180032df3  retn
```

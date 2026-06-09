# DcaMgr::DeviceCredentialMgr::ExecuteLockWorkStation(void)

- ea: `0x180098448`
- end: `0x1800986d7`
- name: `?ExecuteLockWorkStation@DeviceCredentialMgr@DcaMgr@@CAJXZ`
- size: `655`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180097e08`

## callees

- `0x18000782c`
- `0x180007964`
- `0x180021690`
- `0x180026410`
- `0x1800323d0`
- `0x180048304`
- `0x1800535f4`
- `0x18005cee0`
- `0x18005dd44`
- `0x18005fdf0`
- `0x180098448`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098516`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180098680`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180098680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009869f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009869f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009850c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009850c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800985c2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800985c2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800985fb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800985fb`

## string_xrefs

- `0x1800984b0`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180098542`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009861d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180098563`: `rundll32.exe`
- `0x180098599`: `rundll32.exe user32.dll,LockWorkStation`

## pseudocode

```c
__int64 DcaMgr::DeviceCredentialMgr::ExecuteLockWorkStation(void)
{
  unsigned int LastError; // eax
  UINT SystemDirectoryW; // eax
  signed int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned __int64 v5; // r9
  int v6; // eax
  int v7; // eax
  ULONG active; // eax
  BOOL v9; // ebx
  const char *v10; // r9
  __int64 v11; // rdx
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE *p_hToken; // [rsp+68h] [rbp-98h] BYREF
  void *phToken; // [rsp+70h] [rbp-90h] BYREF
  char v17; // [rsp+78h] [rbp-88h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR CommandLine[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR ApplicationName[264]; // [rsp+530h] [rbp+430h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+758h] [rbp+658h]

  hToken = 0;
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !(unsigned __int8)IsWTSQueryUserTokenPresent() )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x3D8,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                  (const char *)0x32,
                  (unsigned int)lpThreadAttributes);
LABEL_21:
    v3 = LastError;
    goto LABEL_25;
  }
  memset_0(Buffer, 0, 0x208u);
  memset_0(ApplicationName, 0, 0x208u);
  memset_0(CommandLine, 0, 0x208u);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW < 0x104 )
    {
      lpThreadAttributes = (LPSECURITY_ATTRIBUTES)L"rundll32.exe";
      v6 = StringCchPrintfW(ApplicationName, 0x104u, L"%s\\%s", Buffer);
      v3 = v6;
      if ( v6 < 0 )
      {
        v5 = (unsigned int)v6;
        v4 = 1009;
        goto LABEL_9;
      }
      v7 = StringCchCopyW(CommandLine, 0x104u, L"rundll32.exe user32.dll,LockWorkStation");
      v3 = v7;
      if ( v7 < 0 )
      {
        v5 = (unsigned int)v7;
        v4 = 1014;
        goto LABEL_9;
      }
      active = WTSGetActiveConsoleSessionId();
      if ( active != -1 )
      {
        phToken = 0;
        p_hToken = &hToken;
        v17 = 1;
        v9 = WTSQueryUserToken(active, &phToken);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hToken);
        if ( v9 )
        {
          if ( CreateProcessAsUserW(
                 hToken,
                 ApplicationName,
                 CommandLine,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0,
                 &StartupInfo,
                 &ProcessInformation) )
          {
            CloseHandle(ProcessInformation.hThread);
            CloseHandle(ProcessInformation.hProcess);
            v3 = 0;
            goto LABEL_25;
          }
          v11 = 1037;
        }
        else
        {
          v11 = 1023;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v11,
                      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                      v10);
        goto LABEL_21;
      }
      v3 = -2147467259;
      v4 = 1019;
    }
    else
    {
      v3 = -2147024883;
      v4 = 1002;
    }
LABEL_8:
    v5 = v3;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)v5,
      (int)lpThreadAttributes);
    goto LABEL_25;
  }
  v2 = GetLastError();
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( (v3 & 0x80000000) != 0 )
  {
    v4 = 1000;
    goto LABEL_8;
  }
LABEL_25:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  return v3;
}

```

## disassembly

```asm
0x180098448  mov     [rsp-8+arg_0], rbx
0x18009844d  mov     [rsp-8+arg_8], rsi
0x180098452  push    rbp
0x180098453  lea     rbp, [rsp-650h]
0x18009845b  sub     rsp, 750h
0x180098462  mov     rax, cs:__security_cookie
0x180098469  xor     rax, rsp
0x18009846c  mov     [rbp+650h+var_10], rax
0x180098473  xor     edx, edx; Val
0x180098475  mov     [rsp+750h+hToken], 0
0x18009847e  lea     rcx, [rbp+650h+StartupInfo.lpReserved]; void *
0x180098482  mov     qword ptr [rbp+650h+StartupInfo.cb], 68h ; 'h'
0x18009848a  lea     r8d, [rdx+60h]; Size
0x18009848e  call    memset_0
0x180098493  xorps   xmm0, xmm0
0x180098496  xor     eax, eax
0x180098498  movups  xmmword ptr [rbp+650h+ProcessInformation.hProcess], xmm0
0x18009849c  mov     qword ptr [rbp+650h+ProcessInformation.dwProcessId], rax
0x1800984a0  call    IsWTSQueryUserTokenPresent
0x1800984a5  test    al, al
0x1800984a7  jnz     short loc_1800984CC
0x1800984a9  mov     rcx, [rbp+658h]; this
0x1800984b0  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800984b7  mov     r9d, 32h ; '2'; char *
0x1800984bd  mov     edx, 3D8h; void *
0x1800984c2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800984c7  jmp     loc_180098629
0x1800984cc  mov     ebx, 208h
0x1800984d1  lea     rcx, [rbp+650h+Buffer]; void *
0x1800984d5  mov     r8d, ebx; Size
0x1800984d8  xor     edx, edx; Val
0x1800984da  call    memset_0
0x1800984df  mov     r8d, ebx; Size
0x1800984e2  lea     rcx, [rbp+650h+ApplicationName]; void *
0x1800984e9  xor     edx, edx; Val
0x1800984eb  call    memset_0
0x1800984f0  mov     r8d, ebx; Size
0x1800984f3  lea     rcx, [rbp+650h+CommandLine]; void *
0x1800984fa  xor     edx, edx; Val
0x1800984fc  call    memset_0
0x180098501  mov     esi, 104h
0x180098506  lea     rcx, [rbp+650h+Buffer]; lpBuffer
0x18009850a  mov     edx, esi; uSize
0x18009850c  call    cs:__imp_GetSystemDirectoryW
0x180098512  test    eax, eax
0x180098514  jnz     short loc_180098553
0x180098516  call    cs:__imp_GetLastError
0x18009851c  mov     ebx, eax
0x18009851e  test    eax, eax
0x180098520  jle     short loc_18009852B
0x180098522  movzx   ebx, ax
0x180098525  or      ebx, 80070000h
0x18009852b  test    ebx, ebx
0x18009852d  jns     loc_1800986A7
0x180098533  mov     edx, 3E8h; void *
0x180098538  mov     r9d, ebx; char *
0x18009853b  mov     rcx, [rbp+658h]; this
0x180098542  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180098549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009854e  jmp     loc_1800986A7
0x180098553  cmp     eax, esi
0x180098555  jb      short loc_180098563
0x180098557  mov     ebx, 8007000Dh
0x18009855c  mov     edx, 3EAh
0x180098561  jmp     short loc_180098538
0x180098563  lea     rax, aRundll32Exe; "rundll32.exe"
0x18009856a  mov     rdx, rsi; unsigned __int64
0x18009856d  lea     r9, [rbp+650h+Buffer]
0x180098571  mov     [rsp+750h+lpThreadAttributes], rax
0x180098576  lea     r8, aSS_0; "%s\\%s"
0x18009857d  lea     rcx, [rbp+650h+ApplicationName]; unsigned __int16 *
0x180098584  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180098589  mov     ebx, eax
0x18009858b  test    eax, eax
0x18009858d  jns     short loc_180098599
0x18009858f  mov     r9d, eax
0x180098592  mov     edx, 3F1h
0x180098597  jmp     short loc_18009853B
0x180098599  lea     r8, aRundll32ExeUse; "rundll32.exe user32.dll,LockWorkStation"
0x1800985a0  mov     rdx, rsi; unsigned __int64
0x1800985a3  lea     rcx, [rbp+650h+CommandLine]; unsigned __int16 *
0x1800985aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800985af  mov     ebx, eax
0x1800985b1  test    eax, eax
0x1800985b3  jns     short loc_1800985C2
0x1800985b5  mov     r9d, eax
0x1800985b8  mov     edx, 3F6h
0x1800985bd  jmp     loc_18009853B
0x1800985c2  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800985c8  cmp     eax, 0FFFFFFFFh
0x1800985cb  jnz     short loc_1800985DC
0x1800985cd  mov     ebx, 80004005h
0x1800985d2  mov     edx, 3FBh
0x1800985d7  jmp     loc_180098538
0x1800985dc  lea     rcx, [rsp+750h+hToken]
0x1800985e1  mov     [rsp+750h+phToken], 0
0x1800985ea  mov     [rsp+750h+var_6E8], rcx
0x1800985ef  lea     rdx, [rsp+750h+phToken]; phToken
0x1800985f4  mov     ecx, eax; SessionId
0x1800985f6  mov     [rsp+750h+var_6D8], 1
0x1800985fb  call    cs:__imp_WTSQueryUserToken
0x180098601  lea     rcx, [rsp+750h+var_6E8]
0x180098606  mov     ebx, eax
0x180098608  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18009860d  test    ebx, ebx
0x18009860f  jnz     short loc_18009862D
0x180098611  mov     edx, 3FFh; void *
0x180098616  mov     rcx, [rbp+658h]; this
0x18009861d  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180098624  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180098629  mov     ebx, eax
0x18009862b  jmp     short loc_1800986A7
0x18009862d  mov     rcx, [rsp+750h+hToken]; hToken
0x180098632  lea     rax, [rbp+650h+ProcessInformation]
0x180098636  mov     [rsp+750h+lpProcessInformation], rax; lpProcessInformation
0x18009863b  lea     r8, [rbp+650h+CommandLine]; lpCommandLine
0x180098642  lea     rax, [rbp+650h+StartupInfo]
0x180098646  xor     r9d, r9d; lpProcessAttributes
0x180098649  mov     [rsp+750h+lpStartupInfo], rax; lpStartupInfo
0x18009864e  lea     rdx, [rbp+650h+ApplicationName]; lpApplicationName
0x180098655  mov     [rsp+750h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18009865e  mov     [rsp+750h+lpEnvironment], 0; lpEnvironment
0x180098667  mov     [rsp+750h+dwCreationFlags], 0; dwCreationFlags
0x18009866f  mov     [rsp+750h+bInheritHandles], 0; bInheritHandles
0x180098677  mov     [rsp+750h+lpThreadAttributes], 0; lpThreadAttributes
0x180098680  call    cs:__imp_CreateProcessAsUserW
0x180098686  test    eax, eax
0x180098688  jnz     short loc_180098691
0x18009868a  mov     edx, 40Dh
0x18009868f  jmp     short loc_180098616
0x180098691  mov     rcx, [rbp+650h+ProcessInformation.hThread]; hObject
0x180098695  call    cs:__imp_CloseHandle
0x18009869b  mov     rcx, [rbp+650h+ProcessInformation.hProcess]; hObject
0x18009869f  call    cs:__imp_CloseHandle
0x1800986a5  xor     ebx, ebx
0x1800986a7  lea     rcx, [rsp+750h+hToken]
0x1800986ac  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800986b1  mov     eax, ebx
0x1800986b3  mov     rcx, [rbp+650h+var_10]
0x1800986ba  xor     rcx, rsp; StackCookie
0x1800986bd  call    __security_check_cookie
0x1800986c2  lea     r11, [rsp+750h+var_s0]
0x1800986ca  mov     rbx, [r11+10h]
0x1800986ce  mov     rsi, [r11+18h]
0x1800986d2  mov     rsp, r11
0x1800986d5  pop     rbp
0x1800986d6  retn
```

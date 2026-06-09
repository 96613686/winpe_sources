# InternetTime_StartServiceAndRefresh

- ea: `0x140068398`
- end: `0x14006861c`
- name: `InternetTime_StartServiceAndRefresh`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140036b20`

## callees

- `0x140005f30`
- `0x140005f54`
- `0x1400060d0`
- `0x14002996c`
- `0x14003d630`
- `0x140068160`
- `0x140068198`
- `0x140068398`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006841a`
- `KERNEL32!GetLastError` at `0x14006850f`
- `KERNEL32!GetLastError` at `0x14006841a`
- `KERNEL32!GetLastError` at `0x14006850f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400683c3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400683c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400683e5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400683e5`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400684e3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400684e3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400685a3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400685d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400685a3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400685d1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14006855e`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14006855e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1400684a3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1400684a3`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14006840c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140068445`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14006840c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140068445`

## string_xrefs

- `0x1400684ba`: `shell\cpls\utc\inettimecommon.cpp`
- `0x140068534`: `shell\cpls\utc\inettimecommon.cpp`
- `0x140068584`: `shell\cpls\utc\inettimecommon.cpp`
- `0x1400685b8`: `shell\cpls\utc\inettimecommon.cpp`
- `0x1400685e6`: `shell\cpls\utc\inettimecommon.cpp`

## pseudocode

```c
__int64 __fastcall InternetTime_StartServiceAndRefresh(int a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  struct _QUERY_SERVICE_CONFIGW *v6; // rdi
  unsigned int v7; // eax
  const struct std::nothrow_t *v8; // rdx
  int v9; // eax
  unsigned int Error; // ebx
  __int64 v11; // rdx
  signed int LastError; // eax
  int lpBinaryPathName; // [rsp+20h] [rbp-98h]
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp-58h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v2 = OpenSCManagerW(0, 0, 0x15u);
  v3 = v2;
  if ( !v2 )
  {
    Error = ResultFromLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1C8,
      (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
      (const char *)Error,
      lpBinaryPathName);
    return Error;
  }
  v4 = OpenServiceW(v2, L"w32time", 0x53u);
  v5 = v4;
  if ( !v4 )
  {
    Error = ResultFromLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
      (const char *)Error,
      lpBinaryPathName);
    goto LABEL_30;
  }
  pcbBytesNeeded = 0;
  if ( !QueryServiceConfigW(v4, 0, 0, &pcbBytesNeeded) && GetLastError() == 122 )
  {
    v6 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded);
    goto LABEL_6;
  }
  v6 = 0;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  if ( (Error & 0x80000000) == 0 )
  {
LABEL_6:
    if ( QueryServiceConfigW(v5, v6, pcbBytesNeeded, &pcbBytesNeeded)
      && v6->dwStartType == 4
      && !ChangeServiceConfigW(v5, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v7 = ResultFromKnownLastError();
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
        (const char *)v7,
        lpBinaryPathName);
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( StartServiceW(v5, 0, 0) || (v9 = ResultFromLastError(), Error = v9, v9 == -2147023840) || v9 == -2147023835 )
    {
      Error = 0;
    }
    else if ( v9 < 0 )
    {
      v11 = 429;
      goto LABEL_25;
    }
    if ( !a1 )
      goto LABEL_26;
    if ( ControlService(v5, 6u, &ServiceStatus) )
    {
      Error = 0;
      goto LABEL_26;
    }
    v9 = ResultFromLastError();
    Error = v9;
    if ( v9 >= 0 )
    {
LABEL_26:
      if ( v6 )
        operator delete(v6, v8);
      goto LABEL_28;
    }
    v11 = 434;
LABEL_25:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
      (const char *)(unsigned int)v9,
      lpBinaryPathName);
    goto LABEL_26;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x18F,
    (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
    (const char *)Error,
    lpBinaryPathName);
LABEL_28:
  CloseServiceHandle(v5);
LABEL_30:
  CloseServiceHandle(v3);
  return Error;
}

```

## disassembly

```asm
0x140068398  push    rbx
0x14006839a  push    rbp
0x14006839b  push    rsi
0x14006839c  push    rdi
0x14006839d  push    r14
0x14006839f  sub     rsp, 90h
0x1400683a6  mov     rax, cs:__security_cookie
0x1400683ad  xor     rax, rsp
0x1400683b0  mov     [rsp+0B8h+var_30], rax
0x1400683b8  xor     edx, edx; lpDatabaseName
0x1400683ba  mov     r14d, ecx
0x1400683bd  xor     ecx, ecx; lpMachineName
0x1400683bf  lea     r8d, [rdx+15h]; dwDesiredAccess
0x1400683c3  call    cs:__imp_OpenSCManagerW
0x1400683c9  mov     rbp, rax
0x1400683cc  test    rax, rax
0x1400683cf  jz      loc_1400685D9
0x1400683d5  mov     r8d, 53h ; 'S'; dwDesiredAccess
0x1400683db  lea     rdx, aW32time; "w32time"
0x1400683e2  mov     rcx, rax; hSCManager
0x1400683e5  call    cs:__imp_OpenServiceW
0x1400683eb  mov     rsi, rax
0x1400683ee  test    rax, rax
0x1400683f1  jz      loc_1400685AB
0x1400683f7  lea     r9, [rsp+0B8h+pcbBytesNeeded]; pcbBytesNeeded
0x1400683fc  mov     [rsp+0B8h+pcbBytesNeeded], 0
0x140068404  xor     r8d, r8d; cbBufSize
0x140068407  xor     edx, edx; lpServiceConfig
0x140068409  mov     rcx, rax; hService
0x14006840c  call    cs:__imp_QueryServiceConfigW
0x140068412  test    eax, eax
0x140068414  jnz     loc_14006850D
0x14006841a  call    cs:__imp_GetLastError
0x140068420  cmp     eax, 7Ah ; 'z'
0x140068423  jnz     loc_14006850D
0x140068429  mov     ecx, [rsp+0B8h+pcbBytesNeeded]; unsigned __int64
0x14006842d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140068432  mov     rdi, rax
0x140068435  mov     r8d, [rsp+0B8h+pcbBytesNeeded]; cbBufSize
0x14006843a  lea     r9, [rsp+0B8h+pcbBytesNeeded]; pcbBytesNeeded
0x14006843f  mov     rdx, rdi; lpServiceConfig
0x140068442  mov     rcx, rsi; hService
0x140068445  call    cs:__imp_QueryServiceConfigW
0x14006844b  test    eax, eax
0x14006844d  jz      short loc_1400684CE
0x14006844f  cmp     dword ptr [rdi+4], 4
0x140068453  jnz     short loc_1400684CE
0x140068455  mov     [rsp+0B8h+lpDisplayName], 0; lpDisplayName
0x14006845e  or      edx, 0FFFFFFFFh; dwServiceType
0x140068461  mov     [rsp+0B8h+lpPassword], 0; lpPassword
0x14006846a  mov     r9d, edx; dwErrorControl
0x14006846d  mov     [rsp+0B8h+lpServiceStartName], 0; lpServiceStartName
0x140068476  mov     r8d, 3; dwStartType
0x14006847c  mov     [rsp+0B8h+lpDependencies], 0; lpDependencies
0x140068485  mov     rcx, rsi; hService
0x140068488  mov     [rsp+0B8h+lpdwTagId], 0; lpdwTagId
0x140068491  mov     [rsp+0B8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x14006849a  mov     [rsp+0B8h+lpBinaryPathName], 0; int
0x1400684a3  call    cs:__imp_ChangeServiceConfigW
0x1400684a9  test    eax, eax
0x1400684ab  jnz     short loc_1400684CE
0x1400684ad  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400684b2  mov     rcx, [rsp+0B8h]; this
0x1400684ba  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1400684c1  mov     r9d, eax; char *
0x1400684c4  mov     edx, 19Ah; void *
0x1400684c9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400684ce  xorps   xmm0, xmm0
0x1400684d1  xor     r8d, r8d; lpServiceArgVectors
0x1400684d4  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwServiceType], xmm0
0x1400684d9  xor     edx, edx; dwNumServiceArgs
0x1400684db  mov     rcx, rsi; hService
0x1400684de  movups  xmmword ptr [rsp+0B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400684e3  call    cs:__imp_StartServiceW
0x1400684e9  test    eax, eax
0x1400684eb  jnz     short loc_14006854A
0x1400684ed  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400684f2  mov     ebx, eax
0x1400684f4  cmp     eax, 80070420h
0x1400684f9  jz      short loc_14006854A
0x1400684fb  cmp     eax, 80070425h
0x140068500  jz      short loc_14006854A
0x140068502  test    eax, eax
0x140068504  jns     short loc_14006854C
0x140068506  mov     edx, 1ADh
0x14006850b  jmp     short loc_14006857C
0x14006850d  xor     edi, edi
0x14006850f  call    cs:__imp_GetLastError
0x140068515  mov     ebx, eax
0x140068517  test    eax, eax
0x140068519  jle     short loc_140068524
0x14006851b  movzx   ebx, ax
0x14006851e  or      ebx, 80070000h
0x140068524  test    ebx, ebx
0x140068526  jns     loc_140068435
0x14006852c  mov     rcx, [rsp+0B8h]; this
0x140068534  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x14006853b  mov     r9d, ebx; char *
0x14006853e  mov     edx, 18Fh; void *
0x140068543  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140068548  jmp     short loc_1400685A0
0x14006854a  xor     ebx, ebx
0x14006854c  test    r14d, r14d
0x14006854f  jz      short loc_140068593
0x140068551  lea     r8, [rsp+0B8h+ServiceStatus]; lpServiceStatus
0x140068556  mov     edx, 6; dwControl
0x14006855b  mov     rcx, rsi; hService
0x14006855e  call    cs:__imp_ControlService
0x140068564  test    eax, eax
0x140068566  jz      short loc_14006856C
0x140068568  xor     ebx, ebx
0x14006856a  jmp     short loc_140068593
0x14006856c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140068571  mov     ebx, eax
0x140068573  test    eax, eax
0x140068575  jns     short loc_140068593
0x140068577  mov     edx, 1B2h; void *
0x14006857c  mov     rcx, [rsp+0B8h]; this
0x140068584  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x14006858b  mov     r9d, eax; char *
0x14006858e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140068593  test    rdi, rdi
0x140068596  jz      short loc_1400685A0
0x140068598  mov     rcx, rdi; void *
0x14006859b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400685a0  mov     rcx, rsi; hSCObject
0x1400685a3  call    cs:__imp_CloseServiceHandle
0x1400685a9  jmp     short loc_1400685CE
0x1400685ab  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400685b0  mov     rcx, [rsp+0B8h]; this
0x1400685b8  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1400685bf  mov     r9d, eax; char *
0x1400685c2  mov     edx, 1C0h; void *
0x1400685c7  mov     ebx, eax
0x1400685c9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400685ce  mov     rcx, rbp; hSCObject
0x1400685d1  call    cs:__imp_CloseServiceHandle
0x1400685d7  jmp     short loc_1400685FC
0x1400685d9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400685de  mov     rcx, [rsp+0B8h]; this
0x1400685e6  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1400685ed  mov     r9d, eax; char *
0x1400685f0  mov     edx, 1C8h; void *
0x1400685f5  mov     ebx, eax
0x1400685f7  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400685fc  mov     eax, ebx
0x1400685fe  mov     rcx, [rsp+0B8h+var_30]
0x140068606  xor     rcx, rsp; StackCookie
0x140068609  call    __security_check_cookie
0x14006860e  add     rsp, 90h
0x140068615  pop     r14
0x140068617  pop     rdi
0x140068618  pop     rsi
0x140068619  pop     rbp
0x14006861a  pop     rbx
0x14006861b  retn
```

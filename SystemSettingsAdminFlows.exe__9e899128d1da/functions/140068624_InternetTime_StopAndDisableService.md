# InternetTime_StopAndDisableService

- ea: `0x140068624`
- end: `0x140068759`
- name: `InternetTime_StopAndDisableService`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140036b20`

## callees

- `0x140005f30`
- `0x14003d630`
- `0x140068160`
- `0x140068624`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140068650`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140068650`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140068672`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140068672`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400686d9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140068707`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400686d9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140068707`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1400686d0`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1400686d0`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1400686b2`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1400686b2`

## string_xrefs

- `0x1400686ee`: `shell\cpls\utc\inettimecommon.cpp`
- `0x14006871c`: `shell\cpls\utc\inettimecommon.cpp`

## pseudocode

```c
__int64 InternetTime_StopAndDisableService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  unsigned int Error; // ebx
  int lpBinaryPathName; // [rsp+20h] [rbp-78h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v0 = OpenSCManagerW(0, 0, 0x15u);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"w32time", 0x63u);
    v3 = v2;
    if ( v2 )
    {
      Error = 0;
      ChangeServiceConfigW(v2, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      ControlService(v3, 1u, &ServiceStatus);
      CloseServiceHandle(v3);
    }
    else
    {
      Error = ResultFromKnownLastError();
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
        (const char *)Error,
        lpBinaryPathName);
    }
    CloseServiceHandle(v1);
  }
  else
  {
    Error = ResultFromKnownLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
      (const char *)Error,
      lpBinaryPathName);
  }
  return Error;
}

```

## disassembly

```asm
0x140068624  mov     [rsp+arg_0], rbx
0x140068629  mov     [rsp+arg_8], rsi
0x14006862e  push    rdi
0x14006862f  sub     rsp, 90h
0x140068636  mov     rax, cs:__security_cookie
0x14006863d  xor     rax, rsp
0x140068640  mov     [rsp+98h+var_18], rax
0x140068648  xor     edx, edx; lpDatabaseName
0x14006864a  xor     ecx, ecx; lpMachineName
0x14006864c  lea     r8d, [rdx+15h]; dwDesiredAccess
0x140068650  call    cs:__imp_OpenSCManagerW
0x140068656  mov     rdi, rax
0x140068659  test    rax, rax
0x14006865c  jz      loc_14006870F
0x140068662  mov     r8d, 63h ; 'c'; dwDesiredAccess
0x140068668  lea     rdx, aW32time; "w32time"
0x14006866f  mov     rcx, rax; hSCManager
0x140068672  call    cs:__imp_OpenServiceW
0x140068678  mov     rsi, rax
0x14006867b  test    rax, rax
0x14006867e  jz      short loc_1400686E1
0x140068680  xor     ebx, ebx
0x140068682  or      edx, 0FFFFFFFFh; dwServiceType
0x140068685  mov     [rsp+98h+lpDisplayName], rbx; lpDisplayName
0x14006868a  mov     r9d, edx; dwErrorControl
0x14006868d  mov     [rsp+98h+lpPassword], rbx; lpPassword
0x140068692  mov     rcx, rax; hService
0x140068695  mov     [rsp+98h+lpServiceStartName], rbx; lpServiceStartName
0x14006869a  mov     [rsp+98h+lpDependencies], rbx; lpDependencies
0x14006869f  lea     r8d, [rbx+4]; dwStartType
0x1400686a3  mov     [rsp+98h+lpdwTagId], rbx; lpdwTagId
0x1400686a8  mov     [rsp+98h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x1400686ad  mov     [rsp+98h+lpBinaryPathName], rbx; lpBinaryPathName
0x1400686b2  call    cs:__imp_ChangeServiceConfigW
0x1400686b8  xorps   xmm0, xmm0
0x1400686bb  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x1400686c0  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x1400686c5  lea     edx, [rbx+1]; dwControl
0x1400686c8  mov     rcx, rsi; hService
0x1400686cb  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400686d0  call    cs:__imp_ControlService
0x1400686d6  mov     rcx, rsi; hSCObject
0x1400686d9  call    cs:__imp_CloseServiceHandle
0x1400686df  jmp     short loc_140068704
0x1400686e1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400686e6  mov     rcx, [rsp+98h]; this
0x1400686ee  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x1400686f5  mov     r9d, eax; char *
0x1400686f8  mov     edx, 1E8h; void *
0x1400686fd  mov     ebx, eax
0x1400686ff  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140068704  mov     rcx, rdi; hSCObject
0x140068707  call    cs:__imp_CloseServiceHandle
0x14006870d  jmp     short loc_140068732
0x14006870f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140068714  mov     rcx, [rsp+98h]; this
0x14006871c  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x140068723  mov     r9d, eax; char *
0x140068726  mov     edx, 1F0h; void *
0x14006872b  mov     ebx, eax
0x14006872d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140068732  mov     eax, ebx
0x140068734  mov     rcx, [rsp+98h+var_18]
0x14006873c  xor     rcx, rsp; StackCookie
0x14006873f  call    __security_check_cookie
0x140068744  lea     r11, [rsp+98h+var_8]
0x14006874c  mov     rbx, [r11+10h]
0x140068750  mov     rsi, [r11+18h]
0x140068754  mov     rsp, r11
0x140068757  pop     rdi
0x140068758  retn
```

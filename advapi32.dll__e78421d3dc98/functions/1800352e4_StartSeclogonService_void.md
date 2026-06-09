# StartSeclogonService(void)

- ea: `0x1800352e4`
- end: `0x180035409`
- name: `?StartSeclogonService@@YAKXZ`
- size: `293`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180033c30`

## callees

- `0x1800352e4`
- `0x180065090`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180035342`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180035342`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180035393`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180035393`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180035317`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180035317`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800353d6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800353e4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800353d6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800353e4`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180035383`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180035383`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180035360`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180035360`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035350`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800353a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035350`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800353a4`
- `KERNEL32!GetLastError` at `0x180035325`
- `KERNEL32!GetLastError` at `0x1800353cb`
- `KERNEL32!GetLastError` at `0x180035325`
- `KERNEL32!GetLastError` at `0x1800353cb`
- `KERNEL32!SleepEx` at `0x1800353b8`
- `KERNEL32!SleepEx` at `0x1800353b8`

## pseudocode

```c
__int64 StartSeclogonService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v3; // rdi
  DWORD TickCount; // ebx
  BOOL started; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( !v0 )
    return GetLastError();
  v3 = OpenServiceW(v0, L"seclogon", 0x54u);
  if ( v3 )
  {
    TickCount = GetTickCount();
    while ( QueryServiceStatus(v3, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState == 1 )
      {
        started = StartServiceW(v3, 0, 0);
      }
      else
      {
        if ( ServiceStatus.dwCurrentState != 7 )
          goto LABEL_11;
        started = ControlService(v3, 3u, &ServiceStatus);
      }
      if ( !started )
        break;
LABEL_11:
      if ( ServiceStatus.dwCurrentState == 4 )
      {
        LastError = 0;
        goto LABEL_17;
      }
      if ( GetTickCount() - TickCount > 0x4E20 )
      {
        LastError = 1053;
        goto LABEL_17;
      }
      SleepEx(0x64u, 0);
    }
  }
  LastError = GetLastError();
LABEL_17:
  CloseServiceHandle(v1);
  if ( v3 )
    CloseServiceHandle(v3);
  return LastError;
}

```

## disassembly

```asm
0x1800352e4  mov     [rsp+arg_0], rbx
0x1800352e9  mov     [rsp+arg_8], rsi
0x1800352ee  push    rdi
0x1800352ef  sub     rsp, 50h
0x1800352f3  mov     rax, cs:__security_cookie
0x1800352fa  xor     rax, rsp
0x1800352fd  mov     [rsp+58h+var_18], rax
0x180035302  xorps   xmm0, xmm0
0x180035305  xor     edx, edx; lpDatabaseName
0x180035307  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18003530c  xor     ecx, ecx; lpMachineName
0x18003530e  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180035313  lea     r8d, [rdx+1]; dwDesiredAccess
0x180035317  call    cs:__imp_OpenSCManagerW
0x18003531d  mov     rsi, rax
0x180035320  test    rax, rax
0x180035323  jnz     short loc_180035332
0x180035325  call    cs:__imp_GetLastError
0x18003532b  mov     ebx, eax
0x18003532d  jmp     loc_1800353EA
0x180035332  mov     r8d, 54h ; 'T'; dwDesiredAccess
0x180035338  lea     rdx, ServiceName; "seclogon"
0x18003533f  mov     rcx, rsi; hSCManager
0x180035342  call    cs:__imp_OpenServiceW
0x180035348  mov     rdi, rax
0x18003534b  test    rax, rax
0x18003534e  jz      short loc_1800353CB
0x180035350  call    cs:__imp_GetTickCount
0x180035356  mov     ebx, eax
0x180035358  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18003535d  mov     rcx, rdi; hService
0x180035360  call    cs:__imp_QueryServiceStatus
0x180035366  test    eax, eax
0x180035368  jz      short loc_1800353CB
0x18003536a  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x18003536e  sub     ecx, 1
0x180035371  jz      short loc_18003538B
0x180035373  cmp     ecx, 6
0x180035376  jnz     short loc_18003539D
0x180035378  lea     edx, [rcx-3]; dwControl
0x18003537b  mov     rcx, rdi; hService
0x18003537e  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180035383  call    cs:__imp_ControlService
0x180035389  jmp     short loc_180035399
0x18003538b  xor     r8d, r8d; lpServiceArgVectors
0x18003538e  xor     edx, edx; dwNumServiceArgs
0x180035390  mov     rcx, rdi; hService
0x180035393  call    cs:__imp_StartServiceW
0x180035399  test    eax, eax
0x18003539b  jz      short loc_1800353CB
0x18003539d  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x1800353a2  jz      short loc_1800353C7
0x1800353a4  call    cs:__imp_GetTickCount
0x1800353aa  sub     eax, ebx
0x1800353ac  cmp     eax, 4E20h
0x1800353b1  ja      short loc_1800353C0
0x1800353b3  xor     edx, edx; bAlertable
0x1800353b5  lea     ecx, [rdx+64h]; dwMilliseconds
0x1800353b8  call    cs:__imp_SleepEx
0x1800353be  jmp     short loc_180035358
0x1800353c0  mov     ebx, 41Dh
0x1800353c5  jmp     short loc_1800353D3
0x1800353c7  xor     ebx, ebx
0x1800353c9  jmp     short loc_1800353D3
0x1800353cb  call    cs:__imp_GetLastError
0x1800353d1  mov     ebx, eax
0x1800353d3  mov     rcx, rsi; hSCObject
0x1800353d6  call    cs:__imp_CloseServiceHandle
0x1800353dc  test    rdi, rdi
0x1800353df  jz      short loc_1800353EA
0x1800353e1  mov     rcx, rdi; hSCObject
0x1800353e4  call    cs:__imp_CloseServiceHandle
0x1800353ea  mov     eax, ebx
0x1800353ec  mov     rcx, [rsp+58h+var_18]
0x1800353f1  xor     rcx, rsp; StackCookie
0x1800353f4  call    __security_check_cookie
0x1800353f9  mov     rbx, [rsp+58h+arg_0]
0x1800353fe  mov     rsi, [rsp+58h+arg_8]
0x180035403  add     rsp, 50h
0x180035407  pop     rdi
0x180035408  retn
```

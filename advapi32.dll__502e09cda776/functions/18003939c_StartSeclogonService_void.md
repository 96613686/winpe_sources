# StartSeclogonService(void)

- ea: `0x18003939c`
- end: `0x180039511`
- name: `?StartSeclogonService@@YAKXZ`
- size: `373`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800377a4`
- `0x18005be60`
- `0x18005bfa0`

## callees

- `0x18003939c`
- `0x1800720b0`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039406`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039406`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180039473`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180039473`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800393cf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800393cf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800394d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800394e5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800394d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800394e5`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18003945d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18003945d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180039434`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180039434`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003941e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003948a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003941e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003948a`
- `KERNEL32!GetLastError` at `0x1800393e3`
- `KERNEL32!GetLastError` at `0x1800394c0`
- `KERNEL32!GetLastError` at `0x1800393e3`
- `KERNEL32!GetLastError` at `0x1800394c0`
- `KERNEL32!SleepEx` at `0x1800394a4`
- `KERNEL32!SleepEx` at `0x1800394a4`

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
0x18003939c  mov     [rsp+arg_0], rbx
0x1800393a1  mov     [rsp+arg_8], rsi
0x1800393a6  push    rdi
0x1800393a7  sub     rsp, 50h
0x1800393ab  mov     rax, cs:__security_cookie
0x1800393b2  xor     rax, rsp
0x1800393b5  mov     [rsp+58h+var_18], rax
0x1800393ba  xorps   xmm0, xmm0
0x1800393bd  xor     edx, edx; lpDatabaseName
0x1800393bf  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800393c4  xor     ecx, ecx; lpMachineName
0x1800393c6  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800393cb  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800393cf  call    cs:__imp_OpenSCManagerW
0x1800393d6  nop     dword ptr [rax+rax+00h]
0x1800393db  mov     rsi, rax
0x1800393de  test    rax, rax
0x1800393e1  jnz     short loc_1800393F6
0x1800393e3  call    cs:__imp_GetLastError
0x1800393ea  nop     dword ptr [rax+rax+00h]
0x1800393ef  mov     ebx, eax
0x1800393f1  jmp     loc_1800394F1
0x1800393f6  mov     r8d, 54h ; 'T'; dwDesiredAccess
0x1800393fc  lea     rdx, ServiceName; "seclogon"
0x180039403  mov     rcx, rsi; hSCManager
0x180039406  call    cs:__imp_OpenServiceW
0x18003940d  nop     dword ptr [rax+rax+00h]
0x180039412  mov     rdi, rax
0x180039415  test    rax, rax
0x180039418  jz      loc_1800394C0
0x18003941e  call    cs:__imp_GetTickCount
0x180039425  nop     dword ptr [rax+rax+00h]
0x18003942a  mov     ebx, eax
0x18003942c  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180039431  mov     rcx, rdi; hService
0x180039434  call    cs:__imp_QueryServiceStatus
0x18003943b  nop     dword ptr [rax+rax+00h]
0x180039440  test    eax, eax
0x180039442  jz      short loc_1800394C0
0x180039444  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x180039448  sub     ecx, 1
0x18003944b  jz      short loc_18003946B
0x18003944d  cmp     ecx, 6
0x180039450  jnz     short loc_180039483
0x180039452  lea     edx, [rcx-3]; dwControl
0x180039455  mov     rcx, rdi; hService
0x180039458  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18003945d  call    cs:__imp_ControlService
0x180039464  nop     dword ptr [rax+rax+00h]
0x180039469  jmp     short loc_18003947F
0x18003946b  xor     r8d, r8d; lpServiceArgVectors
0x18003946e  xor     edx, edx; dwNumServiceArgs
0x180039470  mov     rcx, rdi; hService
0x180039473  call    cs:__imp_StartServiceW
0x18003947a  nop     dword ptr [rax+rax+00h]
0x18003947f  test    eax, eax
0x180039481  jz      short loc_1800394C0
0x180039483  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x180039488  jz      short loc_1800394BC
0x18003948a  call    cs:__imp_GetTickCount
0x180039491  nop     dword ptr [rax+rax+00h]
0x180039496  sub     eax, ebx
0x180039498  cmp     eax, 4E20h
0x18003949d  ja      short loc_1800394B5
0x18003949f  xor     edx, edx; bAlertable
0x1800394a1  lea     ecx, [rdx+64h]; dwMilliseconds
0x1800394a4  call    cs:__imp_SleepEx
0x1800394ab  nop     dword ptr [rax+rax+00h]
0x1800394b0  jmp     loc_18003942C
0x1800394b5  mov     ebx, 41Dh
0x1800394ba  jmp     short loc_1800394CE
0x1800394bc  xor     ebx, ebx
0x1800394be  jmp     short loc_1800394CE
0x1800394c0  call    cs:__imp_GetLastError
0x1800394c7  nop     dword ptr [rax+rax+00h]
0x1800394cc  mov     ebx, eax
0x1800394ce  mov     rcx, rsi; hSCObject
0x1800394d1  call    cs:__imp_CloseServiceHandle
0x1800394d8  nop     dword ptr [rax+rax+00h]
0x1800394dd  test    rdi, rdi
0x1800394e0  jz      short loc_1800394F1
0x1800394e2  mov     rcx, rdi; hSCObject
0x1800394e5  call    cs:__imp_CloseServiceHandle
0x1800394ec  nop     dword ptr [rax+rax+00h]
0x1800394f1  mov     eax, ebx
0x1800394f3  mov     rcx, [rsp+58h+var_18]
0x1800394f8  xor     rcx, rsp; StackCookie
0x1800394fb  call    __security_check_cookie
0x180039500  mov     rbx, [rsp+58h+arg_0]
0x180039505  mov     rsi, [rsp+58h+arg_8]
0x18003950a  add     rsp, 50h
0x18003950e  pop     rdi
0x18003950f  retn
```

# IsServiceRunning

- ea: `0x18009d5dc`
- end: `0x18009d692`
- name: `IsServiceRunning`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18003c098`
- `0x18009d3f4`

## callees

- `0x18009d5dc`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d61b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d61b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d641`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18009d651`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18009d651`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18009d633`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18009d633`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d666`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d674`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d666`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d674`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d60d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d60d`

## pseudocode

```c
_BOOL8 IsServiceRunning()
{
  BOOL v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v0 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceA(v1, "ikeext", 4u);
    v4 = v3;
    if ( v3 && QueryServiceStatus(v3, &ServiceStatus) )
      v0 = ServiceStatus.dwCurrentState == 4;
    else
      GetLastError();
    CloseServiceHandle(v2);
    if ( v4 )
      CloseServiceHandle(v4);
  }
  else
  {
    GetLastError();
  }
  return v0;
}

```

## disassembly

```asm
0x18009d5dc  push    rbx
0x18009d5de  push    rbp
0x18009d5df  push    rsi
0x18009d5e0  push    rdi
0x18009d5e1  sub     rsp, 58h
0x18009d5e5  mov     rax, cs:__security_cookie
0x18009d5ec  xor     rax, rsp
0x18009d5ef  mov     [rsp+78h+var_38], rax
0x18009d5f4  xorps   xmm0, xmm0
0x18009d5f7  xor     ebx, ebx
0x18009d5f9  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18009d5fe  xor     edx, edx; lpDatabaseName
0x18009d600  xor     ecx, ecx; lpMachineName
0x18009d602  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18009d607  lea     ebp, [rbx+1]
0x18009d60a  mov     r8d, ebp; dwDesiredAccess
0x18009d60d  call    cs:__imp_OpenSCManagerW
0x18009d613  mov     rsi, rax
0x18009d616  test    rax, rax
0x18009d619  jnz     short loc_18009D623
0x18009d61b  call    cs:__imp_GetLastError
0x18009d621  jmp     short loc_18009D67A
0x18009d623  mov     r8d, 4; dwDesiredAccess
0x18009d629  lea     rdx, aIkeext; "ikeext"
0x18009d630  mov     rcx, rsi; hSCManager
0x18009d633  call    cs:__imp_OpenServiceA
0x18009d639  mov     rdi, rax
0x18009d63c  test    rax, rax
0x18009d63f  jnz     short loc_18009D649
0x18009d641  call    cs:__imp_GetLastError
0x18009d647  jmp     short loc_18009D663
0x18009d649  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18009d64e  mov     rcx, rdi; hService
0x18009d651  call    cs:__imp_QueryServiceStatus
0x18009d657  test    eax, eax
0x18009d659  jz      short loc_18009D641
0x18009d65b  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18009d660  cmovz   ebx, ebp
0x18009d663  mov     rcx, rsi; hSCObject
0x18009d666  call    cs:__imp_CloseServiceHandle
0x18009d66c  test    rdi, rdi
0x18009d66f  jz      short loc_18009D67A
0x18009d671  mov     rcx, rdi; hSCObject
0x18009d674  call    cs:__imp_CloseServiceHandle
0x18009d67a  mov     eax, ebx
0x18009d67c  mov     rcx, [rsp+78h+var_38]
0x18009d681  xor     rcx, rsp; StackCookie
0x18009d684  call    __security_check_cookie
0x18009d689  add     rsp, 58h
0x18009d68d  pop     rdi
0x18009d68e  pop     rsi
0x18009d68f  pop     rbp
0x18009d690  pop     rbx
0x18009d691  retn
```

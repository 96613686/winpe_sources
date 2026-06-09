# InternetTime_IsW32TimeServiceRunning

- ea: `0x140068258`
- end: `0x140068302`
- name: `InternetTime_IsW32TimeServiceRunning`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140036b20`

## callees

- `0x140005f30`
- `0x140068258`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140068280`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140068280`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14006829c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14006829c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400682d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400682dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400682d4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400682dd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1400682bf`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1400682bf`

## pseudocode

```c
__int64 InternetTime_IsW32TimeServiceRunning()
{
  unsigned int v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v0 = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"w32time", 4u);
    v4 = v3;
    if ( v3 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v3, &ServiceStatus) )
        LOBYTE(v0) = ServiceStatus.dwCurrentState == 4;
      CloseServiceHandle(v4);
    }
    CloseServiceHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x140068258  mov     [rsp+arg_0], rbx
0x14006825d  mov     [rsp+arg_8], rsi
0x140068262  push    rdi
0x140068263  sub     rsp, 50h
0x140068267  mov     rax, cs:__security_cookie
0x14006826e  xor     rax, rsp
0x140068271  mov     [rsp+58h+var_18], rax
0x140068276  xor     ebx, ebx
0x140068278  xor     edx, edx; lpDatabaseName
0x14006827a  xor     ecx, ecx; lpMachineName
0x14006827c  lea     r8d, [rbx+1]; dwDesiredAccess
0x140068280  call    cs:__imp_OpenSCManagerW
0x140068286  mov     rdi, rax
0x140068289  test    rax, rax
0x14006828c  jz      short loc_1400682E3
0x14006828e  lea     r8d, [rbx+4]; dwDesiredAccess
0x140068292  mov     rcx, rax; hSCManager
0x140068295  lea     rdx, aW32time; "w32time"
0x14006829c  call    cs:__imp_OpenServiceW
0x1400682a2  mov     rsi, rax
0x1400682a5  test    rax, rax
0x1400682a8  jz      short loc_1400682DA
0x1400682aa  xorps   xmm0, xmm0
0x1400682ad  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1400682b2  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1400682b7  mov     rcx, rax; hService
0x1400682ba  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400682bf  call    cs:__imp_QueryServiceStatus
0x1400682c5  test    eax, eax
0x1400682c7  jz      short loc_1400682D1
0x1400682c9  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x1400682ce  setz    bl
0x1400682d1  mov     rcx, rsi; hSCObject
0x1400682d4  call    cs:__imp_CloseServiceHandle
0x1400682da  mov     rcx, rdi; hSCObject
0x1400682dd  call    cs:__imp_CloseServiceHandle
0x1400682e3  mov     eax, ebx
0x1400682e5  mov     rcx, [rsp+58h+var_18]
0x1400682ea  xor     rcx, rsp; StackCookie
0x1400682ed  call    __security_check_cookie
0x1400682f2  mov     rbx, [rsp+58h+arg_0]
0x1400682f7  mov     rsi, [rsp+58h+arg_8]
0x1400682fc  add     rsp, 50h
0x140068300  pop     rdi
0x140068301  retn
```

# StopWSearch

- ea: `0x1800127e0`
- end: `0x1800128f6`
- name: `StopWSearch`
- size: `278`
- prototype: `int()`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800128fc`
- `0x1800149a0`

## callees

- `0x1800026f0`
- `0x180012654`
- `0x1800127e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800128a2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800128a2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001282a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001282a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012808`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012808`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128ca`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128d3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128ca`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128d3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001285c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800128b0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001285c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800128b0`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180012881`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180012881`

## pseudocode

```c
int StopWSearch()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  int v4; // esi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"WSearch", 0xF01FFu);
    v3 = v2;
    if ( v2 )
    {
      StopServiceDependents(v1, v2);
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v3, &ServiceStatus)
        && ServiceStatus.dwCurrentState != 1
        && (ServiceStatus.dwCurrentState == 3 || ControlService(v3, 1u, &ServiceStatus)) )
      {
        v4 = 30;
        do
        {
          memset(&ServiceStatus, 0, sizeof(ServiceStatus));
          Sleep(0x3E8u);
          if ( !QueryServiceStatus(v3, &ServiceStatus) )
            break;
          if ( --v4 <= 0 )
            break;
        }
        while ( ServiceStatus.dwCurrentState == 3 );
      }
      CloseServiceHandle(v3);
    }
    LODWORD(v0) = CloseServiceHandle(v1);
  }
  return (int)v0;
}

```

## disassembly

```asm
0x1800127e0  mov     [rsp+arg_0], rbx
0x1800127e5  mov     [rsp+arg_8], rsi
0x1800127ea  push    rdi
0x1800127eb  sub     rsp, 50h
0x1800127ef  mov     rax, cs:__security_cookie
0x1800127f6  xor     rax, rsp
0x1800127f9  mov     [rsp+58h+var_18], rax
0x1800127fe  xor     edx, edx; lpDatabaseName
0x180012800  xor     ecx, ecx; lpMachineName
0x180012802  mov     r8d, 0F003Fh; dwDesiredAccess
0x180012808  call    cs:__imp_OpenSCManagerW
0x18001280e  mov     rdi, rax
0x180012811  test    rax, rax
0x180012814  jz      loc_1800128D9
0x18001281a  mov     r8d, 0F01FFh; dwDesiredAccess
0x180012820  lea     rdx, ServiceName; "WSearch"
0x180012827  mov     rcx, rax; hSCManager
0x18001282a  call    cs:__imp_OpenServiceW
0x180012830  mov     rbx, rax
0x180012833  test    rax, rax
0x180012836  jz      loc_1800128D0
0x18001283c  mov     rdx, rax; hService
0x18001283f  mov     rcx, rdi; hSCManager
0x180012842  call    StopServiceDependents
0x180012847  xorps   xmm0, xmm0
0x18001284a  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001284f  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180012854  mov     rcx, rbx; hService
0x180012857  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001285c  call    cs:__imp_QueryServiceStatus
0x180012862  test    eax, eax
0x180012864  jz      short loc_1800128C7
0x180012866  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x18001286b  jz      short loc_1800128C7
0x18001286d  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 3
0x180012872  jz      short loc_18001288B
0x180012874  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180012879  mov     edx, 1; dwControl
0x18001287e  mov     rcx, rbx; hService
0x180012881  call    cs:__imp_ControlService
0x180012887  test    eax, eax
0x180012889  jz      short loc_1800128C7
0x18001288b  mov     esi, 1Eh
0x180012890  xorps   xmm0, xmm0
0x180012893  mov     ecx, 3E8h; dwMilliseconds
0x180012898  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001289d  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800128a2  call    cs:__imp_Sleep
0x1800128a8  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800128ad  mov     rcx, rbx; hService
0x1800128b0  call    cs:__imp_QueryServiceStatus
0x1800128b6  test    eax, eax
0x1800128b8  jz      short loc_1800128C7
0x1800128ba  dec     esi
0x1800128bc  test    esi, esi
0x1800128be  jle     short loc_1800128C7
0x1800128c0  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 3
0x1800128c5  jz      short loc_180012890
0x1800128c7  mov     rcx, rbx; hSCObject
0x1800128ca  call    cs:__imp_CloseServiceHandle
0x1800128d0  mov     rcx, rdi; hSCObject
0x1800128d3  call    cs:__imp_CloseServiceHandle
0x1800128d9  mov     rcx, [rsp+58h+var_18]
0x1800128de  xor     rcx, rsp; StackCookie
0x1800128e1  call    __security_check_cookie
0x1800128e6  mov     rbx, [rsp+58h+arg_0]
0x1800128eb  mov     rsi, [rsp+58h+arg_8]
0x1800128f0  add     rsp, 50h
0x1800128f4  pop     rdi
0x1800128f5  retn
```

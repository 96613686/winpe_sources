# TsStopService(ushort const *)

- ea: `0x180002060`
- end: `0x180002122`
- name: `?TsStopService@@YAJPEBG@Z`
- size: `194`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000270c`

## callees

- `0x180001460`
- `0x180002060`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000209f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000209f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800020bd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800020bd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800020f4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800020fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800020f4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800020fd`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800020d8`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800020d8`

## string_xrefs

- `0x180002081`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall TsStopService(const unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = -1073741823;
  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, L"w32time", 0x20u);
    v5 = v4;
    if ( v4 )
    {
      if ( ControlService(v4, 1u, &ServiceStatus) )
        v1 = ((ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) != 0 ? 0xC0000001 : 0;
      CloseServiceHandle(v5);
    }
    CloseServiceHandle(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180002060  mov     [rsp+arg_0], rbx
0x180002065  mov     [rsp+arg_8], rsi
0x18000206a  push    rdi
0x18000206b  sub     rsp, 50h
0x18000206f  mov     rax, cs:__security_cookie
0x180002076  xor     rax, rsp
0x180002079  mov     [rsp+58h+var_18], rax
0x18000207e  xorps   xmm0, xmm0
0x180002081  lea     rdx, DatabaseName; "ServicesActive"
0x180002088  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18000208d  mov     r8d, 1; dwDesiredAccess
0x180002093  xor     ecx, ecx; lpMachineName
0x180002095  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000209a  mov     ebx, 0C0000001h
0x18000209f  call    cs:__imp_OpenSCManagerW
0x1800020a5  mov     rsi, rax
0x1800020a8  test    rax, rax
0x1800020ab  jz      short loc_180002103
0x1800020ad  mov     r8d, 20h ; ' '; dwDesiredAccess
0x1800020b3  lea     rdx, ServiceName; "w32time"
0x1800020ba  mov     rcx, rax; hSCManager
0x1800020bd  call    cs:__imp_OpenServiceW
0x1800020c3  mov     rdi, rax
0x1800020c6  test    rax, rax
0x1800020c9  jz      short loc_1800020FA
0x1800020cb  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800020d0  mov     edx, 1; dwControl
0x1800020d5  mov     rcx, rax; hService
0x1800020d8  call    cs:__imp_ControlService
0x1800020de  test    eax, eax
0x1800020e0  jz      short loc_1800020F1
0x1800020e2  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x1800020e6  dec     eax
0x1800020e8  and     eax, 0FFFFFFFDh
0x1800020eb  neg     eax
0x1800020ed  sbb     eax, eax
0x1800020ef  and     ebx, eax
0x1800020f1  mov     rcx, rdi; hSCObject
0x1800020f4  call    cs:__imp_CloseServiceHandle
0x1800020fa  mov     rcx, rsi; hSCObject
0x1800020fd  call    cs:__imp_CloseServiceHandle
0x180002103  mov     eax, ebx
0x180002105  mov     rcx, [rsp+58h+var_18]
0x18000210a  xor     rcx, rsp; StackCookie
0x18000210d  call    __security_check_cookie
0x180002112  mov     rbx, [rsp+58h+arg_0]
0x180002117  mov     rsi, [rsp+58h+arg_8]
0x18000211c  add     rsp, 50h
0x180002120  pop     rdi
0x180002121  retn
```

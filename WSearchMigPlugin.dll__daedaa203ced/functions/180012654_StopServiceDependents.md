# StopServiceDependents

- ea: `0x180012654`
- end: `0x1800127d9`
- name: `StopServiceDependents`
- size: `389`
- prototype: `void __fastcall(SC_HANDLE hSCManager, SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800127e0`

## callees

- `0x1800026f0`
- `0x180002b9c`
- `0x180002c50`
- `0x180012654`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012797`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012780`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012780`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800126a8`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x180012703`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800126a8`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x180012703`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012730`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012730`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800127a0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800127a0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001278d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001278d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180012755`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180012755`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001275f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012772`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001275f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012772`

## pseudocode

```c
void __fastcall StopServiceDependents(SC_HANDLE hSCManager, SC_HANDLE hService)
{
  struct _ENUM_SERVICE_STATUSW *v4; // rax
  struct _ENUM_SERVICE_STATUSW *v5; // rdi
  __int64 i; // rbx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r14
  ULONGLONG v9; // rsi
  DWORD cbBufSize; // [rsp+30h] [rbp-40h] BYREF
  DWORD ServicesReturned[3]; // [rsp+34h] [rbp-3Ch] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-30h] BYREF

  cbBufSize = 0;
  ServicesReturned[0] = 0;
  if ( !EnumDependentServicesW(hService, 1u, 0, 0, &cbBufSize, ServicesReturned) && GetLastError() == 234 )
  {
    v4 = (struct _ENUM_SERVICE_STATUSW *)operator new[](cbBufSize, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v4;
    if ( v4 )
    {
      if ( EnumDependentServicesW(hService, 1u, v4, cbBufSize, &cbBufSize, ServicesReturned) )
      {
        for ( i = 0; (unsigned int)i < ServicesReturned[0]; i = (unsigned int)(i + 1) )
        {
          v7 = OpenServiceW(hSCManager, v5[i].lpServiceName, 0x24u);
          v8 = v7;
          if ( v7 )
          {
            memset(&ServiceStatus, 0, sizeof(ServiceStatus));
            if ( ControlService(v7, 1u, &ServiceStatus) )
            {
              v9 = GetTickCount64() + 30000;
              while ( ServiceStatus.dwCurrentState != 1 && GetTickCount64() < v9 )
              {
                Sleep(ServiceStatus.dwWaitHint);
                if ( !QueryServiceStatus(v8, &ServiceStatus) )
                {
                  GetLastError();
                  break;
                }
              }
            }
            CloseServiceHandle(v8);
          }
        }
      }
      operator delete(v5);
    }
  }
}

```

## disassembly

```asm
0x180012654  mov     [rsp-28h+arg_10], rbx
0x180012659  push    rbp
0x18001265a  push    rsi
0x18001265b  push    rdi
0x18001265c  push    r14
0x18001265e  push    r15
0x180012660  mov     rbp, rsp
0x180012663  sub     rsp, 70h
0x180012667  mov     rax, cs:__security_cookie
0x18001266e  xor     rax, rsp
0x180012671  mov     [rbp+var_10], rax
0x180012675  mov     rbx, rdx
0x180012678  mov     [rbp+cbBufSize], 0
0x18001267f  xor     r9d, r9d; cbBufSize
0x180012682  mov     [rbp+ServicesReturned], 0
0x180012689  lea     rax, [rbp+ServicesReturned]
0x18001268d  mov     r15, rcx
0x180012690  mov     [rsp+70h+lpServicesReturned], rax; lpServicesReturned
0x180012695  xor     r8d, r8d; lpServices
0x180012698  lea     rax, [rbp+cbBufSize]
0x18001269c  mov     rcx, rbx; hService
0x18001269f  lea     edx, [r9+1]; dwServiceState
0x1800126a3  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800126a8  call    cs:__imp_EnumDependentServicesW
0x1800126ae  test    eax, eax
0x1800126b0  jnz     loc_1800127B9
0x1800126b6  call    cs:__imp_GetLastError
0x1800126bc  cmp     eax, 0EAh
0x1800126c1  jnz     loc_1800127B9
0x1800126c7  mov     ecx, [rbp+cbBufSize]; unsigned __int64
0x1800126ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800126d1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800126d6  mov     rdi, rax
0x1800126d9  test    rax, rax
0x1800126dc  jz      loc_1800127B9
0x1800126e2  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x1800126e6  lea     rax, [rbp+ServicesReturned]
0x1800126ea  mov     [rsp+70h+lpServicesReturned], rax; lpServicesReturned
0x1800126ef  mov     r8, rdi; lpServices
0x1800126f2  lea     rax, [rbp+cbBufSize]
0x1800126f6  mov     edx, 1; dwServiceState
0x1800126fb  mov     rcx, rbx; hService
0x1800126fe  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180012703  call    cs:__imp_EnumDependentServicesW
0x180012709  test    eax, eax
0x18001270b  jz      loc_1800127B1
0x180012711  xor     ebx, ebx
0x180012713  cmp     [rbp+ServicesReturned], ebx
0x180012716  jbe     loc_1800127B1
0x18001271c  lea     rdx, [rbx+rbx*2]
0x180012720  mov     r8d, 24h ; '$'; dwDesiredAccess
0x180012726  add     rdx, rdx
0x180012729  mov     rcx, r15; hSCManager
0x18001272c  mov     rdx, [rdi+rdx*8]; lpServiceName
0x180012730  call    cs:__imp_OpenServiceW
0x180012736  mov     r14, rax
0x180012739  test    rax, rax
0x18001273c  jz      short loc_1800127A6
0x18001273e  xorps   xmm0, xmm0
0x180012741  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x180012745  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180012749  mov     edx, 1; dwControl
0x18001274e  mov     rcx, rax; hService
0x180012751  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180012755  call    cs:__imp_ControlService
0x18001275b  test    eax, eax
0x18001275d  jz      short loc_18001279D
0x18001275f  call    cs:__imp_GetTickCount64
0x180012765  lea     rsi, [rax+7530h]
0x18001276c  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x180012770  jz      short loc_18001279D
0x180012772  call    cs:__imp_GetTickCount64
0x180012778  cmp     rax, rsi
0x18001277b  jnb     short loc_18001279D
0x18001277d  mov     ecx, [rbp+ServiceStatus.dwWaitHint]; dwMilliseconds
0x180012780  call    cs:__imp_Sleep
0x180012786  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18001278a  mov     rcx, r14; hService
0x18001278d  call    cs:__imp_QueryServiceStatus
0x180012793  test    eax, eax
0x180012795  jnz     short loc_18001276C
0x180012797  call    cs:__imp_GetLastError
0x18001279d  mov     rcx, r14; hSCObject
0x1800127a0  call    cs:__imp_CloseServiceHandle
0x1800127a6  inc     ebx
0x1800127a8  cmp     ebx, [rbp+ServicesReturned]
0x1800127ab  jb      loc_18001271C
0x1800127b1  mov     rcx, rdi; Block
0x1800127b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800127b9  mov     rcx, [rbp+var_10]
0x1800127bd  xor     rcx, rsp; StackCookie
0x1800127c0  call    __security_check_cookie
0x1800127c5  mov     rbx, [rsp+70h+arg_10]
0x1800127cd  add     rsp, 70h
0x1800127d1  pop     r15
0x1800127d3  pop     r14
0x1800127d5  pop     rdi
0x1800127d6  pop     rsi
0x1800127d7  pop     rbp
0x1800127d8  retn
```

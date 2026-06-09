# TraceServiceStatus(void)

- ea: `0x180006304`
- end: `0x180006459`
- name: `?TraceServiceStatus@@YAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800066d4`
- `0x180006a78`

## callees

- `0x180001cb0`
- `0x180003990`
- `0x180003b84`
- `0x180006304`
- `0x18000789c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000639d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000639d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180006357`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180006357`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006416`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006424`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006416`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180006424`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000638f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000638f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800063bb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800063bb`

## string_xrefs

- `0x18000634e`: `ServicesActive`
- `0x1800063c8`: `Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x, dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.`

## pseudocode

```c
__int64 __fastcall TraceServiceStatus(__int64 a1, __int64 a2, __int64 a3)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  signed int v5; // eax
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbx
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v11; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v12[4]; // [rsp+68h] [rbp+Fh] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+88h] [rbp+2Fh] BYREF

  v11 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  CTraceFuncW<long>::CTraceFuncW<long>(v12, a2, a3, (__int64)&v11);
  v3 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v4 = v3;
  if ( v3 )
  {
    v6 = OpenServiceW(v3, L"WlidSvc", 4u);
    v7 = v6;
    if ( v6 && QueryServiceStatus(v6, &ServiceStatus) )
    {
      TracePrintW(
        (PPTraceStatus *)5,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
        0x3Cu,
        L"Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x,"
         " dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.",
        ServiceStatus.dwCheckPoint,
        ServiceStatus.dwControlsAccepted,
        ServiceStatus.dwCurrentState,
        ServiceStatus.dwServiceSpecificExitCode,
        ServiceStatus.dwServiceType,
        ServiceStatus.dwWaitHint,
        ServiceStatus.dwWin32ExitCode);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = LastError;
    }
    CloseServiceHandle(v4);
    if ( v7 )
      CloseServiceHandle(v7);
  }
  else
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v11 = v5;
  }
  v9 = v11;
  CTraceFuncW<long>::~CTraceFuncW<long>(v12);
  return v9;
}

```

## disassembly

```asm
0x180006304  mov     [rsp-8+arg_0], rbx
0x180006309  mov     [rsp-8+arg_8], rdi
0x18000630e  push    rbp
0x18000630f  lea     rbp, [rsp-57h]
0x180006314  sub     rsp, 0B0h
0x18000631b  mov     rax, cs:__security_cookie
0x180006322  xor     rax, rsp
0x180006325  mov     [rbp+57h+var_8], rax
0x180006329  xorps   xmm0, xmm0
0x18000632c  mov     [rbp+57h+var_50], 0
0x180006333  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180006337  lea     r9, [rbp+57h+var_50]
0x18000633b  lea     rcx, [rbp+57h+var_48]
0x18000633f  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180006343  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0@Z; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *)
0x180006348  mov     r8d, 80000000h; dwDesiredAccess
0x18000634e  lea     rdx, DatabaseName; "ServicesActive"
0x180006355  xor     ecx, ecx; lpMachineName
0x180006357  call    cs:__imp_OpenSCManagerW
0x18000635d  mov     rdi, rax
0x180006360  test    rax, rax
0x180006363  jnz     short loc_18000637F
0x180006365  call    cs:__imp_GetLastError
0x18000636b  test    eax, eax
0x18000636d  jle     short loc_180006377
0x18000636f  movzx   eax, ax
0x180006372  or      eax, 80070000h
0x180006377  mov     [rbp+57h+var_50], eax
0x18000637a  jmp     loc_18000642A
0x18000637f  mov     r8d, 4; dwDesiredAccess
0x180006385  lea     rdx, ServiceName; "WlidSvc"
0x18000638c  mov     rcx, rdi; hSCManager
0x18000638f  call    cs:__imp_OpenServiceW
0x180006395  mov     rbx, rax
0x180006398  test    rax, rax
0x18000639b  jnz     short loc_1800063B4
0x18000639d  call    cs:__imp_GetLastError
0x1800063a3  test    eax, eax
0x1800063a5  jle     short loc_1800063AF
0x1800063a7  movzx   eax, ax
0x1800063aa  or      eax, 80070000h
0x1800063af  mov     [rbp+57h+var_50], eax
0x1800063b2  jmp     short loc_180006413
0x1800063b4  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1800063b8  mov     rcx, rbx; hService
0x1800063bb  call    cs:__imp_QueryServiceStatus
0x1800063c1  test    eax, eax
0x1800063c3  jz      short loc_18000639D
0x1800063c5  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x1800063c8  lea     r9, aServiceStatusD; "Service status: dwCheckPoint=0x%x, dwCo"...
0x1800063cf  mov     [rsp+0B0h+var_60], eax
0x1800063d3  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800063da  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x1800063dd  mov     r8d, 3Ch ; '<'; unsigned int
0x1800063e3  mov     [rsp+0B0h+var_68], eax
0x1800063e7  mov     eax, [rbp+57h+ServiceStatus.dwServiceType]
0x1800063ea  mov     [rsp+0B0h+var_70], eax
0x1800063ee  mov     eax, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x1800063f1  lea     ecx, [r8-37h]; unsigned __int8
0x1800063f5  mov     [rsp+0B0h+var_78], eax
0x1800063f9  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x1800063fc  mov     [rsp+0B0h+var_80], eax
0x180006400  mov     eax, [rbp+57h+ServiceStatus.dwControlsAccepted]
0x180006403  mov     [rsp+0B0h+var_88], eax
0x180006407  mov     eax, [rbp+57h+ServiceStatus.dwCheckPoint]
0x18000640a  mov     [rsp+0B0h+var_90], eax
0x18000640e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006413  mov     rcx, rdi; hSCObject
0x180006416  call    cs:__imp_CloseServiceHandle
0x18000641c  test    rbx, rbx
0x18000641f  jz      short loc_18000642A
0x180006421  mov     rcx, rbx; hSCObject
0x180006424  call    cs:__imp_CloseServiceHandle
0x18000642a  mov     ebx, [rbp+57h+var_50]
0x18000642d  lea     rcx, [rbp+57h+var_48]
0x180006431  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180006436  mov     eax, ebx
0x180006438  mov     rcx, [rbp+57h+var_8]
0x18000643c  xor     rcx, rsp; StackCookie
0x18000643f  call    __security_check_cookie
0x180006444  lea     r11, [rsp+0B0h+var_s0]
0x18000644c  mov     rbx, [r11+10h]
0x180006450  mov     rdi, [r11+18h]
0x180006454  mov     rsp, r11
0x180006457  pop     rbp
0x180006458  retn
```

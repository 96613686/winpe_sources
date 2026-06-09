# TraceServiceStatus(void)

- ea: `0x18001ba00`
- end: `0x18001bb7e`
- name: `?TraceServiceStatus@@YAJXZ`
- size: `382`
- prototype: `__int64(void)`
- caller_count: `33`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001bc2c`
- `0x18001c0f8`
- `0x18001c530`
- `0x18001c9ac`
- `0x18001ccf8`
- `0x18001d028`
- `0x18001d3bc`
- `0x18001d770`
- `0x18001dab0`
- `0x18001ddc0`
- `0x18001e164`
- `0x18001e4cc`
- `0x18001e838`
- `0x18001eba4`
- `0x18001eef0`
- `0x18001f228`
- `0x18001f5e0`
- `0x18001f990`
- `0x18001fd34`
- `0x180020098`
- `0x180020404`
- `0x1800207ac`
- `0x180020b18`
- `0x180020e7c`
- `0x1800211ac`
- `0x180021514`
- `0x1800218a8`
- `0x180021bd8`
- `0x180021f18`
- `0x18002225c`
- `0x18002258c`
- `0x1800228bc`
- `0x180022c40`

## callees

- `0x180003160`
- `0x180008440`
- `0x18000baac`
- `0x18001ba00`
- `0x1800267c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bac2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ba7c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ba7c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001bab4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001bab4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bb3b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bb49`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bb3b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bb49`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001bae0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001bae0`

## string_xrefs

- `0x18001ba3a`: `TraceServiceStatus`
- `0x18001ba73`: `ServicesActive`
- `0x18001baed`: `Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x, dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.`

## pseudocode

```c
__int64 TraceServiceStatus(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  signed int v2; // eax
  __int64 v3; // rdx
  int v4; // r8d
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbx
  signed int LastError; // eax
  unsigned int v8; // ebx
  const unsigned __int16 *v10; // [rsp+20h] [rbp-39h]
  __int64 v11; // [rsp+20h] [rbp-39h]
  signed int v12; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v13[4]; // [rsp+68h] [rbp+Fh] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+88h] [rbp+2Fh] BYREF

  v12 = 0;
  v13[2] = 0;
  v13[3] = 0;
  v13[0] = "TraceServiceStatus";
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v13[1] = &v12;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    "TraceServiceStatus",
    (const char *)0x23,
    0,
    v10);
  v0 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v1 = v0;
  if ( v0 )
  {
    v5 = OpenServiceW(v0, L"WlidSvc", 4u);
    v6 = v5;
    if ( v5 && QueryServiceStatus(v5, &ServiceStatus) )
    {
      LODWORD(v11) = ServiceStatus.dwCheckPoint;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
        0x3Cu,
        L"Service status: dwCheckPoint=0x%x, dwControlsAccepted=0x%x, dwCurrentState=0x%x, dwServiceSpecificExitCode=0x%x,"
         " dwServiceType=0x%x, dwWaitHint=0x%x, dwWin32ExitCode=0x%x.",
        v11,
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
      v12 = LastError;
    }
    CloseServiceHandle(v1);
    if ( v6 )
      CloseServiceHandle(v6);
  }
  else
  {
    v2 = GetLastError();
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    v12 = v2;
  }
  v8 = v12;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v13, v3, v4);
  return v8;
}

```

## disassembly

```asm
0x18001ba00  mov     [rsp-8+arg_0], rbx
0x18001ba05  mov     [rsp-8+arg_8], rdi
0x18001ba0a  push    rbp
0x18001ba0b  lea     rbp, [rsp-57h]
0x18001ba10  sub     rsp, 0B0h
0x18001ba17  mov     rax, cs:__security_cookie
0x18001ba1e  xor     rax, rsp
0x18001ba21  mov     [rbp+57h+var_8], rax
0x18001ba25  xorps   xmm0, xmm0
0x18001ba28  mov     [rbp+57h+var_50], 0
0x18001ba2f  xor     r9d, r9d; unsigned int
0x18001ba32  mov     [rbp+57h+var_38], 0
0x18001ba3a  lea     rdx, aTraceservicest; "TraceServiceStatus"
0x18001ba41  mov     [rbp+57h+var_30], 0
0x18001ba49  lea     rax, [rbp+57h+var_50]
0x18001ba4d  mov     [rbp+57h+var_48], rdx
0x18001ba51  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18001ba55  lea     r8d, [r9+23h]; char *
0x18001ba59  mov     [rbp+57h+var_40], rax
0x18001ba5d  lea     rcx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ba64  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001ba68  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001ba6d  mov     r8d, 80000000h; dwDesiredAccess
0x18001ba73  lea     rdx, DatabaseName; "ServicesActive"
0x18001ba7a  xor     ecx, ecx; lpMachineName
0x18001ba7c  call    cs:__imp_OpenSCManagerW
0x18001ba82  mov     rdi, rax
0x18001ba85  test    rax, rax
0x18001ba88  jnz     short loc_18001BAA4
0x18001ba8a  call    cs:__imp_GetLastError
0x18001ba90  test    eax, eax
0x18001ba92  jle     short loc_18001BA9C
0x18001ba94  movzx   eax, ax
0x18001ba97  or      eax, 80070000h
0x18001ba9c  mov     [rbp+57h+var_50], eax
0x18001ba9f  jmp     loc_18001BB4F
0x18001baa4  mov     r8d, 4; dwDesiredAccess
0x18001baaa  lea     rdx, aWlidsvc_0; "WlidSvc"
0x18001bab1  mov     rcx, rdi; hSCManager
0x18001bab4  call    cs:__imp_OpenServiceW
0x18001baba  mov     rbx, rax
0x18001babd  test    rax, rax
0x18001bac0  jnz     short loc_18001BAD9
0x18001bac2  call    cs:__imp_GetLastError
0x18001bac8  test    eax, eax
0x18001baca  jle     short loc_18001BAD4
0x18001bacc  movzx   eax, ax
0x18001bacf  or      eax, 80070000h
0x18001bad4  mov     [rbp+57h+var_50], eax
0x18001bad7  jmp     short loc_18001BB38
0x18001bad9  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18001badd  mov     rcx, rbx; hService
0x18001bae0  call    cs:__imp_QueryServiceStatus
0x18001bae6  test    eax, eax
0x18001bae8  jz      short loc_18001BAC2
0x18001baea  mov     eax, [rbp+57h+ServiceStatus.dwWin32ExitCode]
0x18001baed  lea     r9, aServiceStatusD; "Service status: dwCheckPoint=0x%x, dwCo"...
0x18001baf4  mov     [rsp+0B0h+var_60], eax
0x18001baf8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001baff  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x18001bb02  mov     r8d, 3Ch ; '<'; unsigned int
0x18001bb08  mov     [rsp+0B0h+var_68], eax
0x18001bb0c  mov     eax, [rbp+57h+ServiceStatus.dwServiceType]
0x18001bb0f  mov     [rsp+0B0h+var_70], eax
0x18001bb13  mov     eax, [rbp+57h+ServiceStatus.dwServiceSpecificExitCode]
0x18001bb16  lea     ecx, [r8-37h]; unsigned __int8
0x18001bb1a  mov     [rsp+0B0h+var_78], eax
0x18001bb1e  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x18001bb21  mov     [rsp+0B0h+var_80], eax
0x18001bb25  mov     eax, [rbp+57h+ServiceStatus.dwControlsAccepted]
0x18001bb28  mov     [rsp+0B0h+var_88], eax
0x18001bb2c  mov     eax, [rbp+57h+ServiceStatus.dwCheckPoint]
0x18001bb2f  mov     dword ptr [rsp+0B0h+var_90], eax
0x18001bb33  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001bb38  mov     rcx, rdi; hSCObject
0x18001bb3b  call    cs:__imp_CloseServiceHandle
0x18001bb41  test    rbx, rbx
0x18001bb44  jz      short loc_18001BB4F
0x18001bb46  mov     rcx, rbx; hSCObject
0x18001bb49  call    cs:__imp_CloseServiceHandle
0x18001bb4f  mov     ebx, [rbp+57h+var_50]
0x18001bb52  lea     rcx, [rbp+57h+var_48]
0x18001bb56  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001bb5b  mov     eax, ebx
0x18001bb5d  mov     rcx, [rbp+57h+var_8]
0x18001bb61  xor     rcx, rsp; StackCookie
0x18001bb64  call    __security_check_cookie
0x18001bb69  lea     r11, [rsp+0B0h+var_s0]
0x18001bb71  mov     rbx, [r11+10h]
0x18001bb75  mov     rdi, [r11+18h]
0x18001bb79  mov     rsp, r11
0x18001bb7c  pop     rbp
0x18001bb7d  retn
```

# BfeFwTriggerInit

- ea: `0x180042eec`
- end: `0x180043161`
- name: `BfeFwTriggerInit`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18003f3e0`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x180042eec`
- `0x180043168`
- `0x18005aa60`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18004314f`
- `ntdll!EtwEventUnregister` at `0x18004314f`
- `ntdll!EtwEventRegister` at `0x180042f31`
- `ntdll!EtwEventRegister` at `0x180042f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004306b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004307a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004306b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004307a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042f4d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042f4d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800430f8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800430f8`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180042ffd`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18004305b`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180042ffd`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18004305b`

## string_xrefs

- `0x180042f6d`: `OpenSCManagerW`
- `0x18004311d`: `EnumServicesStatusExW`

## pseudocode

```c
__int64 BfeFwTriggerInit()
{
  LPBYTE v0; // rdi
  DWORD LastError; // eax
  __int64 v2; // rcx
  SC_HANDLE v3; // r14
  const char *v4; // rdx
  __int64 v5; // rbx
  unsigned int i; // esi
  DWORD v8; // edi
  DWORD v9; // r15d
  __int64 v10; // rcx
  DWORD v11; // esi
  DWORD cbBufSize; // [rsp+28h] [rbp-50h]
  LPBYTE lpServices; // [rsp+50h] [rbp-28h] BYREF
  DWORD pcbBytesNeeded; // [rsp+58h] [rbp-20h] BYREF
  DWORD ServicesReturned; // [rsp+5Ch] [rbp-1Ch] BYREF

  v0 = 0;
  pcbBytesNeeded = 0;
  lpServices = 0;
  ServicesReturned = 0;
  LastError = EtwEventRegister(Symbol_BfeTriggerProvider, 0, 0, &gBfeFwPortEvent);
  if ( LastError )
  {
    v4 = "EtwEventRegister";
    goto LABEL_4;
  }
  v3 = OpenSCManagerW(0, 0, 5u);
  if ( !v3 )
  {
    LastError = GetLastError();
    v4 = "OpenSCManagerW";
LABEL_4:
    v5 = WfpReportSysErrorAsWinError(v2, v4, LastError);
    goto LABEL_5;
  }
  v5 = 0;
  for ( i = 0; i < 4; ++i )
  {
    if ( i >= 3 )
    {
      v8 = 0x40000;
      pcbBytesNeeded = 0x40000;
    }
    else
    {
      EnumServicesStatusExW(v3, SC_ENUM_PROCESS_INFO, 0x30u, 3u, 0, 0, &pcbBytesNeeded, &ServicesReturned, 0, 0);
      v8 = pcbBytesNeeded;
    }
    v5 = WfpMemAlloc(v8, 0);
    if ( v5 )
    {
      v0 = lpServices;
      goto LABEL_20;
    }
    cbBufSize = v8;
    v0 = lpServices;
    if ( EnumServicesStatusExW(
           v3,
           SC_ENUM_PROCESS_INFO,
           0x30u,
           3u,
           lpServices,
           cbBufSize,
           &pcbBytesNeeded,
           &ServicesReturned,
           0,
           0) )
    {
      break;
    }
    v9 = GetLastError();
    if ( GetLastError() == 234 )
    {
      WfpMemFree(&lpServices);
      v0 = 0;
      lpServices = 0;
    }
    else if ( v9 )
    {
      v5 = WfpReportSysErrorAsWinError(v10, "EnumServicesStatusExW", v9);
      goto LABEL_20;
    }
  }
  v11 = 0;
  qword_1800F60C8 = (__int64)&gBfeFwTriggers;
  for ( gBfeFwTriggers = (__int64)&gBfeFwTriggers; v11 < ServicesReturned; ++v11 )
  {
    v5 = BfeFwTriggerBuildDb(v3, (const WCHAR **)&v0[56 * v11]);
    if ( v5 )
      break;
  }
LABEL_20:
  if ( v0 )
    WfpMemFree(&lpServices);
  CloseServiceHandle(v3);
LABEL_5:
  if ( v5 )
  {
    if ( gBfeFwPortEvent )
      EtwEventUnregister();
    WfpReportError(v5, "BfeFwTriggerInit");
  }
  return v5;
}

```

## disassembly

```asm
0x180042eec  push    rbp
0x180042eee  push    rbx
0x180042eef  push    rsi
0x180042ef0  push    rdi
0x180042ef1  push    r14
0x180042ef3  push    r15
0x180042ef5  mov     rbp, rsp
0x180042ef8  sub     rsp, 78h
0x180042efc  mov     rax, cs:__security_cookie
0x180042f03  xor     rax, rsp
0x180042f06  mov     [rbp+var_18], rax
0x180042f0a  xor     edi, edi
0x180042f0c  mov     [rbp+var_20], 0
0x180042f13  lea     r9, gBfeFwPortEvent
0x180042f1a  mov     [rbp+var_28], rdi
0x180042f1e  xor     r8d, r8d
0x180042f21  mov     [rbp+ServicesReturned], 0
0x180042f28  xor     edx, edx
0x180042f2a  lea     rcx, Symbol_BfeTriggerProvider
0x180042f31  call    cs:__imp_EtwEventRegister
0x180042f38  nop     dword ptr [rax+rax+00h]
0x180042f3d  test    eax, eax
0x180042f3f  jnz     loc_180043109
0x180042f45  xor     edx, edx; lpDatabaseName
0x180042f47  lea     r8d, [rdi+5]; dwDesiredAccess
0x180042f4b  xor     ecx, ecx; lpMachineName
0x180042f4d  call    cs:__imp_OpenSCManagerW
0x180042f54  nop     dword ptr [rax+rax+00h]
0x180042f59  mov     r14, rax
0x180042f5c  test    rax, rax
0x180042f5f  jnz     short loc_180042FA5
0x180042f61  call    cs:__imp_GetLastError
0x180042f68  nop     dword ptr [rax+rax+00h]
0x180042f6d  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW"
0x180042f74  mov     r8d, eax
0x180042f77  call    WfpReportSysErrorAsWinError
0x180042f7c  mov     rbx, rax
0x180042f7f  test    rbx, rbx
0x180042f82  jnz     loc_18004313F
0x180042f88  mov     rax, rbx
0x180042f8b  mov     rcx, [rbp+var_18]
0x180042f8f  xor     rcx, rsp; StackCookie
0x180042f92  call    __security_check_cookie
0x180042f97  add     rsp, 78h
0x180042f9b  pop     r15
0x180042f9d  pop     r14
0x180042f9f  pop     rdi
0x180042fa0  pop     rsi
0x180042fa1  pop     rbx
0x180042fa2  pop     rbp
0x180042fa3  retn
0x180042fa5  xor     ebx, ebx
0x180042fa7  xor     esi, esi
0x180042fa9  cmp     esi, 4
0x180042fac  jnb     loc_1800430B4
0x180042fb2  cmp     esi, 3
0x180042fb5  jnb     loc_1800430A7
0x180042fbb  mov     [rsp+78h+pszGroupName], 0; pszGroupName
0x180042fc4  lea     rax, [rbp+ServicesReturned]
0x180042fc8  mov     [rsp+78h+lpResumeHandle], 0; lpResumeHandle
0x180042fd1  xor     edx, edx; InfoLevel
0x180042fd3  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x180042fd8  mov     rcx, r14; hSCManager
0x180042fdb  lea     rax, [rbp+var_20]
0x180042fdf  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180042fe4  mov     [rsp+78h+cbBufSize], 0; cbBufSize
0x180042fec  lea     r9d, [rdx+3]; dwServiceState
0x180042ff0  lea     r8d, [rdx+30h]; dwServiceType
0x180042ff4  mov     [rsp+78h+lpServices], 0; lpServices
0x180042ffd  call    cs:__imp_EnumServicesStatusExW
0x180043004  nop     dword ptr [rax+rax+00h]
0x180043009  mov     edi, [rbp+var_20]
0x18004300c  mov     ecx, edi; dwBytes
0x18004300e  lea     r8, [rbp+var_28]
0x180043012  xor     edx, edx; dwFlags
0x180043014  call    WfpMemAlloc
0x180043019  mov     rbx, rax
0x18004301c  test    rax, rax
0x18004301f  jnz     loc_18004312E
0x180043025  mov     [rsp+78h+pszGroupName], rax; pszGroupName
0x18004302a  lea     r9d, [rbx+3]; dwServiceState
0x18004302e  mov     [rsp+78h+lpResumeHandle], rax; lpResumeHandle
0x180043033  lea     r8d, [rbx+30h]; dwServiceType
0x180043037  lea     rax, [rbp+ServicesReturned]
0x18004303b  xor     edx, edx; InfoLevel
0x18004303d  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x180043042  mov     rcx, r14; hSCManager
0x180043045  lea     rax, [rbp+var_20]
0x180043049  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18004304e  mov     [rsp+78h+cbBufSize], edi; cbBufSize
0x180043052  mov     rdi, [rbp+var_28]
0x180043056  mov     [rsp+78h+lpServices], rdi; lpServices
0x18004305b  call    cs:__imp_EnumServicesStatusExW
0x180043062  nop     dword ptr [rax+rax+00h]
0x180043067  test    eax, eax
0x180043069  jnz     short loc_1800430B4
0x18004306b  call    cs:__imp_GetLastError
0x180043072  nop     dword ptr [rax+rax+00h]
0x180043077  mov     r15d, eax
0x18004307a  call    cs:__imp_GetLastError
0x180043081  nop     dword ptr [rax+rax+00h]
0x180043086  cmp     eax, 0EAh
0x18004308b  jnz     loc_180043115
0x180043091  lea     rcx, [rbp+var_28]
0x180043095  call    WfpMemFree
0x18004309a  xor     edi, edi
0x18004309c  mov     [rbp+var_28], rdi
0x1800430a0  inc     esi
0x1800430a2  jmp     loc_180042FA9
0x1800430a7  mov     edi, 40000h
0x1800430ac  mov     [rbp+var_20], edi
0x1800430af  jmp     loc_18004300C
0x1800430b4  lea     rax, gBfeFwTriggers
0x1800430bb  xor     esi, esi
0x1800430bd  mov     cs:qword_1800F60C8, rax
0x1800430c4  mov     cs:gBfeFwTriggers, rax
0x1800430cb  cmp     [rbp+ServicesReturned], esi
0x1800430ce  jbe     short loc_1800430F0
0x1800430d0  mov     eax, esi
0x1800430d2  mov     rcx, r14
0x1800430d5  imul    rdx, rax, 38h ; '8'
0x1800430d9  add     rdx, rdi
0x1800430dc  call    BfeFwTriggerBuildDb
0x1800430e1  mov     rbx, rax
0x1800430e4  test    rax, rax
0x1800430e7  jnz     short loc_1800430F0
0x1800430e9  inc     esi
0x1800430eb  cmp     esi, [rbp+ServicesReturned]
0x1800430ee  jb      short loc_1800430D0
0x1800430f0  test    rdi, rdi
0x1800430f3  jnz     short loc_180043134
0x1800430f5  mov     rcx, r14; hSCObject
0x1800430f8  call    cs:__imp_CloseServiceHandle
0x1800430ff  nop     dword ptr [rax+rax+00h]
0x180043104  jmp     loc_180042F7F
0x180043109  lea     rdx, aEtweventregist; "EtwEventRegister"
0x180043110  jmp     loc_180042F74
0x180043115  test    r15d, r15d
0x180043118  jz      short loc_1800430A0
0x18004311a  mov     r8d, r15d
0x18004311d  lea     rdx, aEnumservicesst_0; "EnumServicesStatusExW"
0x180043124  call    WfpReportSysErrorAsWinError
0x180043129  mov     rbx, rax
0x18004312c  jmp     short loc_1800430F0
0x18004312e  mov     rdi, [rbp+var_28]
0x180043132  jmp     short loc_1800430F0
0x180043134  lea     rcx, [rbp+var_28]
0x180043138  call    WfpMemFree
0x18004313d  jmp     short loc_1800430F5
0x18004313f  mov     rcx, cs:gBfeFwPortEvent
0x180043146  test    rcx, rcx
0x180043149  jz      loc_18008D7D2
0x18004314f  call    cs:__imp_EtwEventUnregister
0x180043156  nop     dword ptr [rax+rax+00h]
0x18004315b  nop
0x18004315c  jmp     loc_18008D7D2
0x18008d7d2  lea     rdx, aBfefwtriggerin; "BfeFwTriggerInit"
0x18008d7d9  mov     rcx, rbx
0x18008d7dc  call    WfpReportError
0x18008d7e1  nop
0x18008d7e2  jmp     loc_180042F88
```

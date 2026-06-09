# BfeQueryServiceStartType

- ea: `0x1800372b8`
- end: `0x18003744b`
- name: `BfeQueryServiceStartType`
- size: `403`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180037200`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x1800372b8`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003741a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003741a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800372f3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800372f3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180037310`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180037310`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037363`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003736c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037363`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003736c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003732f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800373cc`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003732f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800373cc`

## string_xrefs

- `0x18008a0b7`: `OpenSCManagerW`
- `0x180037423`: `QueryServiceConfigW`
- `0x180037437`: `BfeQueryServiceStartType`

## pseudocode

```c
__int64 __fastcall BfeQueryServiceStartType(LPCWSTR lpServiceName, DWORD *a2)
{
  LPQUERY_SERVICE_CONFIGW v2; // rbp
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r15
  __int64 v7; // rbx
  SC_HANDLE v8; // rdi
  BOOL v9; // r14d
  DWORD LastError; // eax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+20h] [rbp-48h] BYREF
  DWORD pcbBytesNeeded; // [rsp+28h] [rbp-40h] BYREF

  v2 = 0;
  lpServiceConfig = 0;
  pcbBytesNeeded = 0;
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v7 = 0;
    v8 = OpenServiceW(v5, lpServiceName, 1u);
    if ( !v8 )
    {
      LastError = GetLastError();
      switch ( LastError )
      {
        case 0x7Bu:
          goto LABEL_14;
        case 5u:
          *a2 = 2;
          return v7;
        case 0x424u:
LABEL_14:
          *a2 = 4;
          return v7;
      }
      if ( LastError )
        goto LABEL_22;
    }
    v9 = QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded);
    if ( GetLastError() == 122 )
    {
      v7 = WfpMemAlloc(pcbBytesNeeded, 0);
      if ( v7 )
        goto LABEL_6;
      v2 = lpServiceConfig;
      v9 = QueryServiceConfigW(v8, lpServiceConfig, pcbBytesNeeded, &pcbBytesNeeded);
    }
    if ( v9 )
    {
      *a2 = v2->dwStartType;
    }
    else
    {
      v13 = GetLastError();
      v7 = WfpReportSysErrorAsWinError(v14, "QueryServiceConfigW", v13);
    }
LABEL_6:
    if ( v8 )
    {
      WfpMemFree(&lpServiceConfig);
      CloseServiceHandle(v8);
      CloseServiceHandle(v6);
    }
    goto LABEL_8;
  }
  LastError = GetLastError();
LABEL_22:
  v7 = WfpReportSysErrorAsWinError(v12, "OpenSCManagerW", LastError);
LABEL_8:
  if ( v7 )
    WfpReportError(v7, "BfeQueryServiceStartType");
  return v7;
}

```

## disassembly

```asm
0x1800372b8  mov     [rsp+arg_10], rbx
0x1800372bd  push    rbp
0x1800372be  push    rsi
0x1800372bf  push    rdi
0x1800372c0  push    r14
0x1800372c2  push    r15
0x1800372c4  sub     rsp, 40h
0x1800372c8  mov     rax, cs:__security_cookie
0x1800372cf  xor     rax, rsp
0x1800372d2  mov     [rsp+68h+var_38], rax
0x1800372d7  xor     ebp, ebp
0x1800372d9  mov     rsi, rdx
0x1800372dc  mov     rdi, rcx
0x1800372df  mov     [rsp+68h+lpServiceConfig], rbp
0x1800372e4  xor     edx, edx; lpDatabaseName
0x1800372e6  mov     [rsp+68h+pcbBytesNeeded], ebp
0x1800372ea  xor     ecx, ecx; lpMachineName
0x1800372ec  lea     r14d, [rbp+1]
0x1800372f0  mov     r8d, r14d; dwDesiredAccess
0x1800372f3  call    cs:__imp_OpenSCManagerW
0x1800372f9  mov     r15, rax
0x1800372fc  test    rax, rax
0x1800372ff  jz      loc_1800373FA
0x180037305  mov     r8d, r14d; dwDesiredAccess
0x180037308  mov     rdx, rdi; lpServiceName
0x18003730b  mov     rcx, rax; hSCManager
0x18003730e  xor     ebx, ebx
0x180037310  call    cs:__imp_OpenServiceW
0x180037316  mov     rdi, rax
0x180037319  test    rax, rax
0x18003731c  jz      loc_1800373DA
0x180037322  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x180037327  xor     r8d, r8d; cbBufSize
0x18003732a  xor     edx, edx; lpServiceConfig
0x18003732c  mov     rcx, rdi; hService
0x18003732f  call    cs:__imp_QueryServiceConfigW
0x180037335  mov     r14d, eax
0x180037338  call    cs:__imp_GetLastError
0x18003733e  cmp     eax, 7Ah ; 'z'
0x180037341  jz      short loc_18003739F
0x180037343  test    r14d, r14d
0x180037346  jz      loc_18003741A
0x18003734c  mov     eax, [rbp+4]
0x18003734f  mov     [rsi], eax
0x180037351  test    rdi, rdi
0x180037354  jz      short loc_180037372
0x180037356  lea     rcx, [rsp+68h+lpServiceConfig]
0x18003735b  call    WfpMemFree
0x180037360  mov     rcx, rdi; hSCObject
0x180037363  call    cs:__imp_CloseServiceHandle
0x180037369  mov     rcx, r15; hSCObject
0x18003736c  call    cs:__imp_CloseServiceHandle
0x180037372  test    rbx, rbx
0x180037375  jnz     loc_180037437
0x18003737b  mov     rax, rbx
0x18003737e  mov     rcx, [rsp+68h+var_38]
0x180037383  xor     rcx, rsp; StackCookie
0x180037386  call    __security_check_cookie
0x18003738b  mov     rbx, [rsp+68h+arg_10]
0x180037393  add     rsp, 40h
0x180037397  pop     r15
0x180037399  pop     r14
0x18003739b  pop     rdi
0x18003739c  pop     rsi
0x18003739d  pop     rbp
0x18003739e  retn
0x18003739f  mov     ecx, [rsp+68h+pcbBytesNeeded]; dwBytes
0x1800373a3  lea     r8, [rsp+68h+lpServiceConfig]
0x1800373a8  xor     edx, edx; dwFlags
0x1800373aa  call    WfpMemAlloc
0x1800373af  mov     rbx, rax
0x1800373b2  test    rax, rax
0x1800373b5  jnz     short loc_180037351
0x1800373b7  mov     rbp, [rsp+68h+lpServiceConfig]
0x1800373bc  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1800373c1  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x1800373c6  mov     rdx, rbp; lpServiceConfig
0x1800373c9  mov     rcx, rdi; hService
0x1800373cc  call    cs:__imp_QueryServiceConfigW
0x1800373d2  mov     r14d, eax
0x1800373d5  jmp     loc_180037343
0x1800373da  call    cs:__imp_GetLastError
0x1800373e0  cmp     eax, 7Bh ; '{'
0x1800373e3  jnz     short loc_1800373ED
0x1800373e5  mov     dword ptr [rsi], 4
0x1800373eb  jmp     short loc_18003737B
0x1800373ed  cmp     eax, 5
0x1800373f0  jnz     short loc_180037406
0x1800373f2  mov     dword ptr [rsi], 2
0x1800373f8  jmp     short loc_18003737B
0x1800373fa  call    cs:__imp_GetLastError
0x180037400  nop
0x180037401  jmp     loc_18008A0B4
0x180037406  cmp     eax, 424h
0x18003740b  jz      short loc_1800373E5
0x18003740d  test    eax, eax
0x18003740f  jz      loc_180037322
0x180037415  jmp     loc_18008A0B4
0x18003741a  call    cs:__imp_GetLastError
0x180037420  mov     r8d, eax
0x180037423  lea     rdx, aQueryserviceco_2; "QueryServiceConfigW"
0x18003742a  call    WfpReportSysErrorAsWinError
0x18003742f  mov     rbx, rax
0x180037432  jmp     loc_180037351
0x180037437  lea     rdx, aBfequeryservic; "BfeQueryServiceStartType"
0x18003743e  mov     rcx, rbx
0x180037441  call    WfpReportError
0x180037446  jmp     loc_18003737B
0x18008a0b4  mov     r8d, eax
0x18008a0b7  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW"
0x18008a0be  call    WfpReportSysErrorAsWinError
0x18008a0c3  mov     rbx, rax
0x18008a0c6  jmp     loc_180037372
```

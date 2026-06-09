# BfeQueryServiceStartType

- ea: `0x18001d6d8`
- end: `0x18001d8ab`
- name: `BfeQueryServiceStartType`
- size: `467`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001d620`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x18001d6d8`
- `0x180024e40`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d84e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d84e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d874`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d713`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d713`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d736`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d736`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d79b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d7aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d79b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d7aa`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001d75b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001d811`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001d75b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001d811`

## string_xrefs

- `0x18008bb8f`: `OpenSCManagerW`
- `0x18001d883`: `QueryServiceConfigW`
- `0x18001d897`: `BfeQueryServiceStartType`

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
0x18001d6d8  mov     [rsp+arg_10], rbx
0x18001d6dd  push    rbp
0x18001d6de  push    rsi
0x18001d6df  push    rdi
0x18001d6e0  push    r14
0x18001d6e2  push    r15
0x18001d6e4  sub     rsp, 40h
0x18001d6e8  mov     rax, cs:__security_cookie
0x18001d6ef  xor     rax, rsp
0x18001d6f2  mov     [rsp+68h+var_38], rax
0x18001d6f7  xor     ebp, ebp
0x18001d6f9  mov     rsi, rdx
0x18001d6fc  mov     rdi, rcx
0x18001d6ff  mov     [rsp+68h+lpServiceConfig], rbp
0x18001d704  xor     edx, edx; lpDatabaseName
0x18001d706  mov     [rsp+68h+pcbBytesNeeded], ebp
0x18001d70a  xor     ecx, ecx; lpMachineName
0x18001d70c  lea     r14d, [rbp+1]
0x18001d710  mov     r8d, r14d; dwDesiredAccess
0x18001d713  call    cs:__imp_OpenSCManagerW
0x18001d71a  nop     dword ptr [rax+rax+00h]
0x18001d71f  mov     r15, rax
0x18001d722  test    rax, rax
0x18001d725  jz      loc_18001D84E
0x18001d72b  mov     r8d, r14d; dwDesiredAccess
0x18001d72e  mov     rdx, rdi; lpServiceName
0x18001d731  mov     rcx, rax; hSCManager
0x18001d734  xor     ebx, ebx
0x18001d736  call    cs:__imp_OpenServiceW
0x18001d73d  nop     dword ptr [rax+rax+00h]
0x18001d742  mov     rdi, rax
0x18001d745  test    rax, rax
0x18001d748  jz      loc_18001D825
0x18001d74e  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x18001d753  xor     r8d, r8d; cbBufSize
0x18001d756  xor     edx, edx; lpServiceConfig
0x18001d758  mov     rcx, rdi; hService
0x18001d75b  call    cs:__imp_QueryServiceConfigW
0x18001d762  nop     dword ptr [rax+rax+00h]
0x18001d767  mov     r14d, eax
0x18001d76a  call    cs:__imp_GetLastError
0x18001d771  nop     dword ptr [rax+rax+00h]
0x18001d776  cmp     eax, 7Ah ; 'z'
0x18001d779  jz      short loc_18001D7E4
0x18001d77b  test    r14d, r14d
0x18001d77e  jz      loc_18001D874
0x18001d784  mov     eax, [rbp+4]
0x18001d787  mov     [rsi], eax
0x18001d789  test    rdi, rdi
0x18001d78c  jz      short loc_18001D7B6
0x18001d78e  lea     rcx, [rsp+68h+lpServiceConfig]
0x18001d793  call    WfpMemFree
0x18001d798  mov     rcx, rdi; hSCObject
0x18001d79b  call    cs:__imp_CloseServiceHandle
0x18001d7a2  nop     dword ptr [rax+rax+00h]
0x18001d7a7  mov     rcx, r15; hSCObject
0x18001d7aa  call    cs:__imp_CloseServiceHandle
0x18001d7b1  nop     dword ptr [rax+rax+00h]
0x18001d7b6  test    rbx, rbx
0x18001d7b9  jnz     loc_18001D897
0x18001d7bf  mov     rax, rbx
0x18001d7c2  mov     rcx, [rsp+68h+var_38]
0x18001d7c7  xor     rcx, rsp; StackCookie
0x18001d7ca  call    __security_check_cookie
0x18001d7cf  mov     rbx, [rsp+68h+arg_10]
0x18001d7d7  add     rsp, 40h
0x18001d7db  pop     r15
0x18001d7dd  pop     r14
0x18001d7df  pop     rdi
0x18001d7e0  pop     rsi
0x18001d7e1  pop     rbp
0x18001d7e2  retn
0x18001d7e4  mov     ecx, [rsp+68h+pcbBytesNeeded]; dwBytes
0x18001d7e8  lea     r8, [rsp+68h+lpServiceConfig]
0x18001d7ed  xor     edx, edx; dwFlags
0x18001d7ef  call    WfpMemAlloc
0x18001d7f4  mov     rbx, rax
0x18001d7f7  test    rax, rax
0x18001d7fa  jnz     short loc_18001D789
0x18001d7fc  mov     rbp, [rsp+68h+lpServiceConfig]
0x18001d801  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x18001d806  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x18001d80b  mov     rdx, rbp; lpServiceConfig
0x18001d80e  mov     rcx, rdi; hService
0x18001d811  call    cs:__imp_QueryServiceConfigW
0x18001d818  nop     dword ptr [rax+rax+00h]
0x18001d81d  mov     r14d, eax
0x18001d820  jmp     loc_18001D77B
0x18001d825  call    cs:__imp_GetLastError
0x18001d82c  nop     dword ptr [rax+rax+00h]
0x18001d831  cmp     eax, 7Bh ; '{'
0x18001d834  jnz     short loc_18001D83E
0x18001d836  mov     dword ptr [rsi], 4
0x18001d83c  jmp     short loc_18001D7BF
0x18001d83e  cmp     eax, 5
0x18001d841  jnz     short loc_18001D860
0x18001d843  mov     dword ptr [rsi], 2
0x18001d849  jmp     loc_18001D7BF
0x18001d84e  call    cs:__imp_GetLastError
0x18001d855  nop     dword ptr [rax+rax+00h]
0x18001d85a  nop
0x18001d85b  jmp     loc_18008BB8C
0x18001d860  cmp     eax, 424h
0x18001d865  jz      short loc_18001D836
0x18001d867  test    eax, eax
0x18001d869  jz      loc_18001D74E
0x18001d86f  jmp     loc_18008BB8C
0x18001d874  call    cs:__imp_GetLastError
0x18001d87b  nop     dword ptr [rax+rax+00h]
0x18001d880  mov     r8d, eax
0x18001d883  lea     rdx, aQueryserviceco_2; "QueryServiceConfigW"
0x18001d88a  call    WfpReportSysErrorAsWinError
0x18001d88f  mov     rbx, rax
0x18001d892  jmp     loc_18001D789
0x18001d897  lea     rdx, aBfequeryservic; "BfeQueryServiceStartType"
0x18001d89e  mov     rcx, rbx
0x18001d8a1  call    WfpReportError
0x18001d8a6  jmp     loc_18001D7BF
0x18008bb8c  mov     r8d, eax
0x18008bb8f  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW"
0x18008bb96  call    WfpReportSysErrorAsWinError
0x18008bb9b  mov     rbx, rax
0x18008bb9e  jmp     loc_18001D7B6
```

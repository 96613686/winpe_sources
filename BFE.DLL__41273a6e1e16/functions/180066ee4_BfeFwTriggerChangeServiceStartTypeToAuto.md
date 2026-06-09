# BfeFwTriggerChangeServiceStartTypeToAuto

- ea: `0x180066ee4`
- end: `0x18006708a`
- name: `BfeFwTriggerChangeServiceStartTypeToAuto`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180067090`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x180024e40`
- `0x18005aa60`
- `0x180066ee4`
- `0x1800672c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067032`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180066f14`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180066f14`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180067050`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180067050`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180066f5e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180066fa6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180066f5e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180066fa6`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180067022`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180067022`

## string_xrefs

- `0x180066f37`: `OpenServiceW`
- `0x180067041`: `QueryServiceConfig2W`

## pseudocode

```c
int __fastcall BfeFwTriggerChangeServiceStartTypeToAuto(SC_HANDLE a1, const WCHAR **a2)
{
  const WCHAR *v2; // rdx
  SC_HANDLE v3; // rdi
  DWORD v4; // eax
  __int64 v5; // rcx
  DWORD v7; // esi
  unsigned int i; // edx
  DWORD LastError; // eax
  __int64 v10; // rcx
  LPBYTE lpBuffer; // [rsp+68h] [rbp-18h]
  DWORD cbBufSize; // [rsp+70h] [rbp-10h] BYREF

  v2 = *a2;
  lpBuffer = 0;
  cbBufSize = 0;
  v3 = OpenServiceW(a1, v2, 3u);
  if ( v3 )
  {
    QueryServiceConfig2W(v3, 8u, 0, 0, &cbBufSize);
    v7 = cbBufSize;
    if ( cbBufSize && !WfpMemAlloc(cbBufSize, 0) )
    {
      if ( QueryServiceConfig2W(v3, 8u, lpBuffer, v7, &cbBufSize) )
      {
        for ( i = 0; i < *(_DWORD *)lpBuffer; ++i )
        {
          if ( *(_DWORD *)(32LL * i + *((_QWORD *)lpBuffer + 1)) == 4 )
          {
            BfeFwTriggerGetServiceStartType(v3);
            return CloseServiceHandle(v3);
          }
        }
      }
      else
      {
        LastError = GetLastError();
        WfpReportSysErrorAsWinError(v10, "QueryServiceConfig2W", LastError);
      }
    }
    return CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    return WfpReportSysErrorAsWinError(v5, "OpenServiceW", v4);
  }
}

```

## disassembly

```asm
0x180066ee4  mov     [rsp-18h+arg_10], rbx
0x180066ee9  push    rbp
0x180066eea  push    rsi
0x180066eeb  push    rdi
0x180066eec  mov     rbp, rsp
0x180066eef  sub     rsp, 80h
0x180066ef6  mov     rax, cs:__security_cookie
0x180066efd  xor     rax, rsp
0x180066f00  mov     [rbp+var_8], rax
0x180066f04  mov     rdx, [rdx]; lpServiceName
0x180066f07  xor     ebx, ebx
0x180066f09  mov     [rbp+lpBuffer], rbx
0x180066f0d  mov     [rbp+cbBufSize], ebx
0x180066f10  lea     r8d, [rbx+3]; dwDesiredAccess
0x180066f14  call    cs:__imp_OpenServiceW
0x180066f1b  nop     dword ptr [rax+rax+00h]
0x180066f20  mov     rdi, rax
0x180066f23  test    rax, rax
0x180066f26  jnz     short loc_180066F48
0x180066f28  call    cs:__imp_GetLastError
0x180066f2f  nop     dword ptr [rax+rax+00h]
0x180066f34  mov     r8d, eax
0x180066f37  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x180066f3e  call    WfpReportSysErrorAsWinError
0x180066f43  jmp     loc_18006706A
0x180066f48  xor     r9d, r9d; cbBufSize
0x180066f4b  lea     rax, [rbp+cbBufSize]
0x180066f4f  xor     r8d, r8d; lpBuffer
0x180066f52  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180066f57  mov     rcx, rdi; hService
0x180066f5a  lea     edx, [r9+8]; dwInfoLevel
0x180066f5e  call    cs:__imp_QueryServiceConfig2W
0x180066f65  nop     dword ptr [rax+rax+00h]
0x180066f6a  mov     esi, [rbp+cbBufSize]
0x180066f6d  test    esi, esi
0x180066f6f  jz      loc_18006704D
0x180066f75  mov     ecx, esi; dwBytes
0x180066f77  lea     r8, [rbp+lpBuffer]
0x180066f7b  xor     edx, edx; dwFlags
0x180066f7d  call    WfpMemAlloc
0x180066f82  mov     rbx, [rbp+lpBuffer]
0x180066f86  test    rax, rax
0x180066f89  jnz     loc_18006704D
0x180066f8f  lea     rax, [rbp+cbBufSize]
0x180066f93  mov     r9d, esi; cbBufSize
0x180066f96  mov     r8, rbx; lpBuffer
0x180066f99  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180066f9e  mov     edx, 8; dwInfoLevel
0x180066fa3  mov     rcx, rdi; hService
0x180066fa6  call    cs:__imp_QueryServiceConfig2W
0x180066fad  nop     dword ptr [rax+rax+00h]
0x180066fb2  test    eax, eax
0x180066fb4  jz      short loc_180067032
0x180066fb6  xor     edx, edx
0x180066fb8  cmp     edx, [rbx]
0x180066fba  jnb     loc_18006704D
0x180066fc0  mov     rax, [rbx+8]
0x180066fc4  mov     ecx, edx
0x180066fc6  shl     rcx, 5
0x180066fca  cmp     dword ptr [rcx+rax], 4
0x180066fce  jz      short loc_180066FD4
0x180066fd0  inc     edx
0x180066fd2  jmp     short loc_180066FB8
0x180066fd4  lea     rdx, [rbp+var_20]
0x180066fd8  mov     [rbp+var_20], 0
0x180066fdf  mov     rcx, rdi; hService
0x180066fe2  call    BfeFwTriggerGetServiceStartType
0x180066fe7  test    rax, rax
0x180066fea  jnz     short loc_18006704D
0x180066fec  cmp     [rbp+var_20], 3
0x180066ff0  jnz     short loc_18006704D
0x180066ff2  mov     [rsp+80h+lpDisplayName], rax; lpDisplayName
0x180066ff7  lea     r8d, [rax+2]; dwStartType
0x180066ffb  mov     [rsp+80h+lpPassword], rax; lpPassword
0x180067000  or      edx, 0FFFFFFFFh; dwServiceType
0x180067003  mov     [rsp+80h+lpServiceStartName], rax; lpServiceStartName
0x180067008  mov     r9d, edx; dwErrorControl
0x18006700b  mov     [rsp+80h+lpDependencies], rax; lpDependencies
0x180067010  mov     rcx, rdi; hService
0x180067013  mov     [rsp+80h+lpdwTagId], rax; lpdwTagId
0x180067018  mov     [rsp+80h+lpLoadOrderGroup], rax; lpLoadOrderGroup
0x18006701d  mov     [rsp+80h+pcbBytesNeeded], rax; lpBinaryPathName
0x180067022  call    cs:__imp_ChangeServiceConfigW
0x180067029  nop     dword ptr [rax+rax+00h]
0x18006702e  test    eax, eax
0x180067030  jnz     short loc_18006704D
0x180067032  call    cs:__imp_GetLastError
0x180067039  nop     dword ptr [rax+rax+00h]
0x18006703e  mov     r8d, eax
0x180067041  lea     rdx, aQueryserviceco_1; "QueryServiceConfig2W"
0x180067048  call    WfpReportSysErrorAsWinError
0x18006704d  mov     rcx, rdi; hSCObject
0x180067050  call    cs:__imp_CloseServiceHandle
0x180067057  nop     dword ptr [rax+rax+00h]
0x18006705c  test    rbx, rbx
0x18006705f  jz      short loc_18006706A
0x180067061  lea     rcx, [rbp+lpBuffer]
0x180067065  call    WfpMemFree
0x18006706a  mov     rcx, [rbp+var_8]
0x18006706e  xor     rcx, rsp; StackCookie
0x180067071  call    __security_check_cookie
0x180067076  mov     rbx, [rsp+80h+arg_10]
0x18006707e  add     rsp, 80h
0x180067085  pop     rdi
0x180067086  pop     rsi
0x180067087  pop     rbp
0x180067088  retn
```

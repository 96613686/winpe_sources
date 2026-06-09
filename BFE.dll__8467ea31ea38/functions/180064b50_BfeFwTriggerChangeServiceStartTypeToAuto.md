# BfeFwTriggerChangeServiceStartTypeToAuto

- ea: `0x180064b50`
- end: `0x180064ccb`
- name: `BfeFwTriggerChangeServiceStartTypeToAuto`
- size: `379`
- prototype: `int __fastcall(SC_HANDLE, const WCHAR **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180064cd4`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180022730`
- `0x180058b30`
- `0x180064b50`
- `0x180064edc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c80`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180064b80`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180064b80`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180064c98`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180064c98`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180064bbe`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180064c00`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180064bbe`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180064c00`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180064c76`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180064c76`

## string_xrefs

- `0x180064b97`: `OpenServiceW`
- `0x180064c89`: `QueryServiceConfig2W`

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
0x180064b50  mov     [rsp-18h+arg_10], rbx
0x180064b55  push    rbp
0x180064b56  push    rsi
0x180064b57  push    rdi
0x180064b58  mov     rbp, rsp
0x180064b5b  sub     rsp, 80h
0x180064b62  mov     rax, cs:__security_cookie
0x180064b69  xor     rax, rsp
0x180064b6c  mov     [rbp+var_8], rax
0x180064b70  mov     rdx, [rdx]; lpServiceName
0x180064b73  xor     ebx, ebx
0x180064b75  mov     [rbp+lpBuffer], rbx
0x180064b79  mov     [rbp+cbBufSize], ebx
0x180064b7c  lea     r8d, [rbx+3]; dwDesiredAccess
0x180064b80  call    cs:__imp_OpenServiceW
0x180064b86  mov     rdi, rax
0x180064b89  test    rax, rax
0x180064b8c  jnz     short loc_180064BA8
0x180064b8e  call    cs:__imp_GetLastError
0x180064b94  mov     r8d, eax
0x180064b97  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x180064b9e  call    WfpReportSysErrorAsWinError
0x180064ba3  jmp     loc_180064CAC
0x180064ba8  xor     r9d, r9d; cbBufSize
0x180064bab  lea     rax, [rbp+cbBufSize]
0x180064baf  xor     r8d, r8d; lpBuffer
0x180064bb2  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180064bb7  mov     rcx, rdi; hService
0x180064bba  lea     edx, [r9+8]; dwInfoLevel
0x180064bbe  call    cs:__imp_QueryServiceConfig2W
0x180064bc4  mov     esi, [rbp+cbBufSize]
0x180064bc7  test    esi, esi
0x180064bc9  jz      loc_180064C95
0x180064bcf  mov     ecx, esi; dwBytes
0x180064bd1  lea     r8, [rbp+lpBuffer]
0x180064bd5  xor     edx, edx; dwFlags
0x180064bd7  call    WfpMemAlloc
0x180064bdc  mov     rbx, [rbp+lpBuffer]
0x180064be0  test    rax, rax
0x180064be3  jnz     loc_180064C95
0x180064be9  lea     rax, [rbp+cbBufSize]
0x180064bed  mov     r9d, esi; cbBufSize
0x180064bf0  mov     r8, rbx; lpBuffer
0x180064bf3  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180064bf8  mov     edx, 8; dwInfoLevel
0x180064bfd  mov     rcx, rdi; hService
0x180064c00  call    cs:__imp_QueryServiceConfig2W
0x180064c06  test    eax, eax
0x180064c08  jz      short loc_180064C80
0x180064c0a  xor     edx, edx
0x180064c0c  cmp     edx, [rbx]
0x180064c0e  jnb     loc_180064C95
0x180064c14  mov     rax, [rbx+8]
0x180064c18  mov     ecx, edx
0x180064c1a  shl     rcx, 5
0x180064c1e  cmp     dword ptr [rcx+rax], 4
0x180064c22  jz      short loc_180064C28
0x180064c24  inc     edx
0x180064c26  jmp     short loc_180064C0C
0x180064c28  lea     rdx, [rbp+var_20]
0x180064c2c  mov     [rbp+var_20], 0
0x180064c33  mov     rcx, rdi; hService
0x180064c36  call    BfeFwTriggerGetServiceStartType
0x180064c3b  test    rax, rax
0x180064c3e  jnz     short loc_180064C95
0x180064c40  cmp     [rbp+var_20], 3
0x180064c44  jnz     short loc_180064C95
0x180064c46  mov     [rsp+80h+lpDisplayName], rax; lpDisplayName
0x180064c4b  lea     r8d, [rax+2]; dwStartType
0x180064c4f  mov     [rsp+80h+lpPassword], rax; lpPassword
0x180064c54  or      edx, 0FFFFFFFFh; dwServiceType
0x180064c57  mov     [rsp+80h+lpServiceStartName], rax; lpServiceStartName
0x180064c5c  mov     r9d, edx; dwErrorControl
0x180064c5f  mov     [rsp+80h+lpDependencies], rax; lpDependencies
0x180064c64  mov     rcx, rdi; hService
0x180064c67  mov     [rsp+80h+lpdwTagId], rax; lpdwTagId
0x180064c6c  mov     [rsp+80h+lpLoadOrderGroup], rax; lpLoadOrderGroup
0x180064c71  mov     [rsp+80h+pcbBytesNeeded], rax; lpBinaryPathName
0x180064c76  call    cs:__imp_ChangeServiceConfigW
0x180064c7c  test    eax, eax
0x180064c7e  jnz     short loc_180064C95
0x180064c80  call    cs:__imp_GetLastError
0x180064c86  mov     r8d, eax
0x180064c89  lea     rdx, aQueryserviceco_1; "QueryServiceConfig2W"
0x180064c90  call    WfpReportSysErrorAsWinError
0x180064c95  mov     rcx, rdi; hSCObject
0x180064c98  call    cs:__imp_CloseServiceHandle
0x180064c9e  test    rbx, rbx
0x180064ca1  jz      short loc_180064CAC
0x180064ca3  lea     rcx, [rbp+lpBuffer]
0x180064ca7  call    WfpMemFree
0x180064cac  mov     rcx, [rbp+var_8]
0x180064cb0  xor     rcx, rsp; StackCookie
0x180064cb3  call    __security_check_cookie
0x180064cb8  mov     rbx, [rsp+80h+arg_10]
0x180064cc0  add     rsp, 80h
0x180064cc7  pop     rdi
0x180064cc8  pop     rsi
0x180064cc9  pop     rbp
0x180064cca  retn
```

# BfeFwTriggerIsServiceDependOnBfe

- ea: `0x180048448`
- end: `0x1800485b5`
- name: `BfeFwTriggerIsServiceDependOnBfe`
- size: `365`
- prototype: `_BOOL8 __fastcall(SC_HANDLE, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180041ee0`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180022730`
- `0x180048448`
- `0x180058b30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048569`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800484fa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004848b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004848b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004857f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004857f`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800484da`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004854a`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1800484da`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004854a`

## string_xrefs

- `0x1800484aa`: `OpenServiceW`
- `0x180048503`: `EnumDependentServicesW`

## pseudocode

```c
_BOOL8 __fastcall BfeFwTriggerIsServiceDependOnBfe(SC_HANDLE a1, __int64 a2)
{
  SC_HANDLE v3; // r14
  BOOL v4; // ebx
  DWORD v5; // eax
  __int64 v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rcx
  DWORD v9; // edi
  __int64 i; // rdi
  LPENUM_SERVICE_STATUSW lpServices; // [rsp+30h] [rbp-20h]
  DWORD cbBufSize; // [rsp+38h] [rbp-18h] BYREF
  DWORD ServicesReturned; // [rsp+3Ch] [rbp-14h] BYREF

  cbBufSize = 0;
  ServicesReturned = 0;
  lpServices = 0;
  v3 = OpenServiceW(a1, L"BFE", 8u);
  v4 = v3 == 0;
  if ( v3 )
  {
    if ( !EnumDependentServicesW(v3, 3u, 0, 0, &cbBufSize, &ServicesReturned) )
    {
      if ( GetLastError() == 234 )
      {
        v9 = cbBufSize;
        if ( WfpMemAlloc(cbBufSize, 0) )
        {
LABEL_12:
          v4 = 1;
          goto LABEL_13;
        }
        if ( EnumDependentServicesW(v3, 3u, lpServices, v9, &cbBufSize, &ServicesReturned) )
        {
          for ( i = 0; (unsigned int)i < ServicesReturned; i = (unsigned int)(i + 1) )
          {
            if ( !(unsigned int)_o__wcsicmp(lpServices[i].lpServiceName, a2) )
              goto LABEL_12;
          }
          goto LABEL_13;
        }
      }
      v4 = 1;
      LastError = GetLastError();
      WfpReportSysErrorAsWinError(v8, "EnumDependentServicesW", LastError);
    }
LABEL_13:
    CloseServiceHandle(v3);
    return v4;
  }
  v5 = GetLastError();
  WfpReportSysErrorAsWinError(v6, "OpenServiceW", v5);
  return v4;
}

```

## disassembly

```asm
0x180048448  mov     [rsp-28h+arg_10], rbx
0x18004844d  push    rbp
0x18004844e  push    rsi
0x18004844f  push    rdi
0x180048450  push    r14
0x180048452  push    r15
0x180048454  mov     rbp, rsp
0x180048457  sub     rsp, 50h
0x18004845b  mov     rax, cs:__security_cookie
0x180048462  xor     rax, rsp
0x180048465  mov     [rbp+var_10], rax
0x180048469  xor     esi, esi
0x18004846b  mov     [rbp+cbBufSize], 0
0x180048472  mov     r15, rdx
0x180048475  mov     [rbp+ServicesReturned], 0
0x18004847c  lea     rdx, ServiceName; "BFE"
0x180048483  mov     [rbp+lpServices], rsi
0x180048487  lea     r8d, [rsi+8]; dwDesiredAccess
0x18004848b  call    cs:__imp_OpenServiceW
0x180048491  xor     ebx, ebx
0x180048493  mov     r14, rax
0x180048496  test    rax, rax
0x180048499  setz    bl
0x18004849c  test    rax, rax
0x18004849f  jnz     short loc_1800484BB
0x1800484a1  call    cs:__imp_GetLastError
0x1800484a7  mov     r8d, eax
0x1800484aa  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x1800484b1  call    WfpReportSysErrorAsWinError
0x1800484b6  jmp     loc_180048593
0x1800484bb  xor     r9d, r9d; cbBufSize
0x1800484be  lea     rax, [rbp+ServicesReturned]
0x1800484c2  mov     [rsp+50h+lpServicesReturned], rax; lpServicesReturned
0x1800484c7  xor     r8d, r8d; lpServices
0x1800484ca  lea     rax, [rbp+cbBufSize]
0x1800484ce  mov     rcx, r14; hService
0x1800484d1  mov     [rsp+50h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800484d6  lea     edx, [r9+3]; dwServiceState
0x1800484da  call    cs:__imp_EnumDependentServicesW
0x1800484e0  test    eax, eax
0x1800484e2  jnz     loc_18004857C
0x1800484e8  call    cs:__imp_GetLastError
0x1800484ee  cmp     eax, 0EAh
0x1800484f3  jz      short loc_180048511
0x1800484f5  mov     ebx, 1
0x1800484fa  call    cs:__imp_GetLastError
0x180048500  mov     r8d, eax
0x180048503  lea     rdx, aEnumdependents_0; "EnumDependentServicesW"
0x18004850a  call    WfpReportSysErrorAsWinError
0x18004850f  jmp     short loc_18004857C
0x180048511  mov     edi, [rbp+cbBufSize]
0x180048514  lea     r8, [rbp+lpServices]
0x180048518  mov     ecx, edi; dwBytes
0x18004851a  xor     edx, edx; dwFlags
0x18004851c  call    WfpMemAlloc
0x180048521  mov     rsi, [rbp+lpServices]
0x180048525  test    rax, rax
0x180048528  jnz     short loc_180048577
0x18004852a  lea     rax, [rbp+ServicesReturned]
0x18004852e  mov     r9d, edi; cbBufSize
0x180048531  mov     [rsp+50h+lpServicesReturned], rax; lpServicesReturned
0x180048536  mov     r8, rsi; lpServices
0x180048539  lea     rax, [rbp+cbBufSize]
0x18004853d  mov     edx, 3; dwServiceState
0x180048542  mov     rcx, r14; hService
0x180048545  mov     [rsp+50h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18004854a  call    cs:__imp_EnumDependentServicesW
0x180048550  test    eax, eax
0x180048552  jz      short loc_1800484F5
0x180048554  xor     edi, edi
0x180048556  cmp     edi, [rbp+ServicesReturned]
0x180048559  jnb     short loc_18004857C
0x18004855b  lea     rcx, [rdi+rdi*2]
0x18004855f  mov     rdx, r15
0x180048562  add     rcx, rcx
0x180048565  mov     rcx, [rsi+rcx*8]
0x180048569  call    cs:__imp__o__wcsicmp
0x18004856f  test    eax, eax
0x180048571  jz      short loc_180048577
0x180048573  inc     edi
0x180048575  jmp     short loc_180048556
0x180048577  mov     ebx, 1
0x18004857c  mov     rcx, r14; hSCObject
0x18004857f  call    cs:__imp_CloseServiceHandle
0x180048585  test    rsi, rsi
0x180048588  jz      short loc_180048593
0x18004858a  lea     rcx, [rbp+lpServices]
0x18004858e  call    WfpMemFree
0x180048593  mov     eax, ebx
0x180048595  mov     rcx, [rbp+var_10]
0x180048599  xor     rcx, rsp; StackCookie
0x18004859c  call    __security_check_cookie
0x1800485a1  mov     rbx, [rsp+50h+arg_10]
0x1800485a9  add     rsp, 50h
0x1800485ad  pop     r15
0x1800485af  pop     r14
0x1800485b1  pop     rdi
0x1800485b2  pop     rsi
0x1800485b3  pop     rbp
0x1800485b4  retn
```

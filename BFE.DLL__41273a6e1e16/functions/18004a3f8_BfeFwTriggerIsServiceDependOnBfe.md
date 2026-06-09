# BfeFwTriggerIsServiceDependOnBfe

- ea: `0x18004a3f8`
- end: `0x18004a596`
- name: `BfeFwTriggerIsServiceDependOnBfe`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180043168`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x180024e40`
- `0x18004a3f8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a53d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a53d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4c2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004a43b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004a43b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004a559`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004a559`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004a496`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004a518`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004a496`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18004a518`

## string_xrefs

- `0x18004a466`: `OpenServiceW`
- `0x18004a4d1`: `EnumDependentServicesW`

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
0x18004a3f8  mov     [rsp-28h+arg_10], rbx
0x18004a3fd  push    rbp
0x18004a3fe  push    rsi
0x18004a3ff  push    rdi
0x18004a400  push    r14
0x18004a402  push    r15
0x18004a404  mov     rbp, rsp
0x18004a407  sub     rsp, 50h
0x18004a40b  mov     rax, cs:__security_cookie
0x18004a412  xor     rax, rsp
0x18004a415  mov     [rbp+var_10], rax
0x18004a419  xor     esi, esi
0x18004a41b  mov     [rbp+cbBufSize], 0
0x18004a422  mov     r15, rdx
0x18004a425  mov     [rbp+ServicesReturned], 0
0x18004a42c  lea     rdx, ServiceName; "BFE"
0x18004a433  mov     [rbp+lpServices], rsi
0x18004a437  lea     r8d, [rsi+8]; dwDesiredAccess
0x18004a43b  call    cs:__imp_OpenServiceW
0x18004a442  nop     dword ptr [rax+rax+00h]
0x18004a447  xor     ebx, ebx
0x18004a449  mov     r14, rax
0x18004a44c  test    rax, rax
0x18004a44f  setz    bl
0x18004a452  test    rax, rax
0x18004a455  jnz     short loc_18004A477
0x18004a457  call    cs:__imp_GetLastError
0x18004a45e  nop     dword ptr [rax+rax+00h]
0x18004a463  mov     r8d, eax
0x18004a466  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x18004a46d  call    WfpReportSysErrorAsWinError
0x18004a472  jmp     loc_18004A573
0x18004a477  xor     r9d, r9d; cbBufSize
0x18004a47a  lea     rax, [rbp+ServicesReturned]
0x18004a47e  mov     [rsp+50h+lpServicesReturned], rax; lpServicesReturned
0x18004a483  xor     r8d, r8d; lpServices
0x18004a486  lea     rax, [rbp+cbBufSize]
0x18004a48a  mov     rcx, r14; hService
0x18004a48d  mov     [rsp+50h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18004a492  lea     edx, [r9+3]; dwServiceState
0x18004a496  call    cs:__imp_EnumDependentServicesW
0x18004a49d  nop     dword ptr [rax+rax+00h]
0x18004a4a2  test    eax, eax
0x18004a4a4  jnz     loc_18004A556
0x18004a4aa  call    cs:__imp_GetLastError
0x18004a4b1  nop     dword ptr [rax+rax+00h]
0x18004a4b6  cmp     eax, 0EAh
0x18004a4bb  jz      short loc_18004A4DF
0x18004a4bd  mov     ebx, 1
0x18004a4c2  call    cs:__imp_GetLastError
0x18004a4c9  nop     dword ptr [rax+rax+00h]
0x18004a4ce  mov     r8d, eax
0x18004a4d1  lea     rdx, aEnumdependents_0; "EnumDependentServicesW"
0x18004a4d8  call    WfpReportSysErrorAsWinError
0x18004a4dd  jmp     short loc_18004A556
0x18004a4df  mov     edi, [rbp+cbBufSize]
0x18004a4e2  lea     r8, [rbp+lpServices]
0x18004a4e6  mov     ecx, edi; dwBytes
0x18004a4e8  xor     edx, edx; dwFlags
0x18004a4ea  call    WfpMemAlloc
0x18004a4ef  mov     rsi, [rbp+lpServices]
0x18004a4f3  test    rax, rax
0x18004a4f6  jnz     short loc_18004A551
0x18004a4f8  lea     rax, [rbp+ServicesReturned]
0x18004a4fc  mov     r9d, edi; cbBufSize
0x18004a4ff  mov     [rsp+50h+lpServicesReturned], rax; lpServicesReturned
0x18004a504  mov     r8, rsi; lpServices
0x18004a507  lea     rax, [rbp+cbBufSize]
0x18004a50b  mov     edx, 3; dwServiceState
0x18004a510  mov     rcx, r14; hService
0x18004a513  mov     [rsp+50h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18004a518  call    cs:__imp_EnumDependentServicesW
0x18004a51f  nop     dword ptr [rax+rax+00h]
0x18004a524  test    eax, eax
0x18004a526  jz      short loc_18004A4BD
0x18004a528  xor     edi, edi
0x18004a52a  cmp     edi, [rbp+ServicesReturned]
0x18004a52d  jnb     short loc_18004A556
0x18004a52f  lea     rcx, [rdi+rdi*2]
0x18004a533  mov     rdx, r15
0x18004a536  add     rcx, rcx
0x18004a539  mov     rcx, [rsi+rcx*8]
0x18004a53d  call    cs:__imp__o__wcsicmp
0x18004a544  nop     dword ptr [rax+rax+00h]
0x18004a549  test    eax, eax
0x18004a54b  jz      short loc_18004A551
0x18004a54d  inc     edi
0x18004a54f  jmp     short loc_18004A52A
0x18004a551  mov     ebx, 1
0x18004a556  mov     rcx, r14; hSCObject
0x18004a559  call    cs:__imp_CloseServiceHandle
0x18004a560  nop     dword ptr [rax+rax+00h]
0x18004a565  test    rsi, rsi
0x18004a568  jz      short loc_18004A573
0x18004a56a  lea     rcx, [rbp+lpServices]
0x18004a56e  call    WfpMemFree
0x18004a573  mov     eax, ebx
0x18004a575  mov     rcx, [rbp+var_10]
0x18004a579  xor     rcx, rsp; StackCookie
0x18004a57c  call    __security_check_cookie
0x18004a581  mov     rbx, [rsp+50h+arg_10]
0x18004a589  add     rsp, 50h
0x18004a58d  pop     r15
0x18004a58f  pop     r14
0x18004a591  pop     rdi
0x18004a592  pop     rsi
0x18004a593  pop     rbp
0x18004a594  retn
```

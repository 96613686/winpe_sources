# BfeFwTriggerGetServiceStartType

- ea: `0x1800672c8`
- end: `0x1800673c0`
- name: `BfeFwTriggerGetServiceStartType`
- size: `248`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180066ee4`
- `0x1800673d0`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x18005aa60`
- `0x1800672c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067354`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180067309`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180067344`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180067309`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180067344`

## string_xrefs

- `0x180067363`: `QueryServiceConfig2W`
- `0x18006738d`: `BfeFwTriggerGetServiceStartType`

## pseudocode

```c
__int64 __fastcall BfeFwTriggerGetServiceStartType(SC_HANDLE hService, _DWORD *a2)
{
  DWORD v4; // r14d
  __int64 v5; // rbx
  DWORD LastError; // eax
  __int64 v7; // rcx
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+20h] [rbp-38h]
  DWORD cbBufSize; // [rsp+28h] [rbp-30h] BYREF

  cbBufSize = 0;
  lpServiceConfig = 0;
  QueryServiceConfigW(hService, 0, 0, &cbBufSize);
  v4 = cbBufSize;
  v5 = WfpMemAlloc(cbBufSize, 0);
  if ( !v5 )
  {
    if ( QueryServiceConfigW(hService, lpServiceConfig, v4, &cbBufSize) )
    {
      *a2 = MEMORY[4];
    }
    else
    {
      LastError = GetLastError();
      v5 = WfpReportSysErrorAsWinError(v7, "QueryServiceConfig2W", LastError);
    }
  }
  if ( v5 )
    WfpReportError(v5, "BfeFwTriggerGetServiceStartType");
  return v5;
}

```

## disassembly

```asm
0x1800672c8  mov     r11, rsp
0x1800672cb  mov     [r11+18h], rbx
0x1800672cf  mov     [r11+20h], rbp
0x1800672d3  push    rsi
0x1800672d4  push    rdi
0x1800672d5  push    r14
0x1800672d7  sub     rsp, 40h
0x1800672db  mov     rax, cs:__security_cookie
0x1800672e2  xor     rax, rsp
0x1800672e5  mov     [rsp+58h+var_28], rax
0x1800672ea  mov     rsi, rdx
0x1800672ed  mov     [rsp+58h+cbBufSize], 0
0x1800672f5  xor     edx, edx; lpServiceConfig
0x1800672f7  mov     qword ptr [r11-38h], 0
0x1800672ff  lea     r9, [r11-30h]; pcbBytesNeeded
0x180067303  xor     r8d, r8d; cbBufSize
0x180067306  mov     rbp, rcx
0x180067309  call    cs:__imp_QueryServiceConfigW
0x180067310  nop     dword ptr [rax+rax+00h]
0x180067315  mov     r14d, [rsp+58h+cbBufSize]
0x18006731a  lea     r8, [rsp+58h+lpServiceConfig]
0x18006731f  mov     ecx, r14d; dwBytes
0x180067322  xor     edx, edx; dwFlags
0x180067324  call    WfpMemAlloc
0x180067329  mov     rdi, [rsp+58h+lpServiceConfig]
0x18006732e  mov     rbx, rax
0x180067331  test    rax, rax
0x180067334  jnz     short loc_180067379
0x180067336  lea     r9, [rsp+58h+cbBufSize]; pcbBytesNeeded
0x18006733b  mov     r8d, r14d; cbBufSize
0x18006733e  mov     rdx, rdi; lpServiceConfig
0x180067341  mov     rcx, rbp; hService
0x180067344  call    cs:__imp_QueryServiceConfigW
0x18006734b  nop     dword ptr [rax+rax+00h]
0x180067350  test    eax, eax
0x180067352  jnz     short loc_180067374
0x180067354  call    cs:__imp_GetLastError
0x18006735b  nop     dword ptr [rax+rax+00h]
0x180067360  mov     r8d, eax
0x180067363  lea     rdx, aQueryserviceco_1; "QueryServiceConfig2W"
0x18006736a  call    WfpReportSysErrorAsWinError
0x18006736f  mov     rbx, rax
0x180067372  jmp     short loc_180067379
0x180067374  mov     eax, [rdi+4]
0x180067377  mov     [rsi], eax
0x180067379  test    rdi, rdi
0x18006737c  jz      short loc_180067388
0x18006737e  lea     rcx, [rsp+58h+lpServiceConfig]
0x180067383  call    WfpMemFree
0x180067388  test    rbx, rbx
0x18006738b  jz      short loc_18006739C
0x18006738d  lea     rdx, aBfefwtriggerge; "BfeFwTriggerGetServiceStartType"
0x180067394  mov     rcx, rbx
0x180067397  call    WfpReportError
0x18006739c  mov     rax, rbx
0x18006739f  mov     rcx, [rsp+58h+var_28]
0x1800673a4  xor     rcx, rsp; StackCookie
0x1800673a7  call    __security_check_cookie
0x1800673ac  mov     rbx, [rsp+58h+arg_10]
0x1800673b1  mov     rbp, [rsp+58h+arg_18]
0x1800673b6  add     rsp, 40h
0x1800673ba  pop     r14
0x1800673bc  pop     rdi
0x1800673bd  pop     rsi
0x1800673be  retn
```

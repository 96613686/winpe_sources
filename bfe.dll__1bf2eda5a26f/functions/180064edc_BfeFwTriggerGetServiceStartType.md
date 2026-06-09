# BfeFwTriggerGetServiceStartType

- ea: `0x180064edc`
- end: `0x180064fc1`
- name: `BfeFwTriggerGetServiceStartType`
- size: `229`
- prototype: `__int64 __fastcall(SC_HANDLE hService, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180064b50`
- `0x180064fd0`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x180058b30`
- `0x180064edc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f5c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180064f1d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180064f52`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180064f1d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180064f52`

## string_xrefs

- `0x180064f65`: `QueryServiceConfig2W`
- `0x180064f8f`: `BfeFwTriggerGetServiceStartType`

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
0x180064edc  mov     r11, rsp
0x180064edf  mov     [r11+18h], rbx
0x180064ee3  mov     [r11+20h], rbp
0x180064ee7  push    rsi
0x180064ee8  push    rdi
0x180064ee9  push    r14
0x180064eeb  sub     rsp, 40h
0x180064eef  mov     rax, cs:__security_cookie
0x180064ef6  xor     rax, rsp
0x180064ef9  mov     [rsp+58h+var_28], rax
0x180064efe  mov     rsi, rdx
0x180064f01  mov     [rsp+58h+cbBufSize], 0
0x180064f09  xor     edx, edx; lpServiceConfig
0x180064f0b  mov     qword ptr [r11-38h], 0
0x180064f13  lea     r9, [r11-30h]; pcbBytesNeeded
0x180064f17  xor     r8d, r8d; cbBufSize
0x180064f1a  mov     rbp, rcx
0x180064f1d  call    cs:__imp_QueryServiceConfigW
0x180064f23  mov     r14d, [rsp+58h+cbBufSize]
0x180064f28  lea     r8, [rsp+58h+lpServiceConfig]
0x180064f2d  mov     ecx, r14d; dwBytes
0x180064f30  xor     edx, edx; dwFlags
0x180064f32  call    WfpMemAlloc
0x180064f37  mov     rdi, [rsp+58h+lpServiceConfig]
0x180064f3c  mov     rbx, rax
0x180064f3f  test    rax, rax
0x180064f42  jnz     short loc_180064F7B
0x180064f44  lea     r9, [rsp+58h+cbBufSize]; pcbBytesNeeded
0x180064f49  mov     r8d, r14d; cbBufSize
0x180064f4c  mov     rdx, rdi; lpServiceConfig
0x180064f4f  mov     rcx, rbp; hService
0x180064f52  call    cs:__imp_QueryServiceConfigW
0x180064f58  test    eax, eax
0x180064f5a  jnz     short loc_180064F76
0x180064f5c  call    cs:__imp_GetLastError
0x180064f62  mov     r8d, eax
0x180064f65  lea     rdx, aQueryserviceco_1; "QueryServiceConfig2W"
0x180064f6c  call    WfpReportSysErrorAsWinError
0x180064f71  mov     rbx, rax
0x180064f74  jmp     short loc_180064F7B
0x180064f76  mov     eax, [rdi+4]
0x180064f79  mov     [rsi], eax
0x180064f7b  test    rdi, rdi
0x180064f7e  jz      short loc_180064F8A
0x180064f80  lea     rcx, [rsp+58h+lpServiceConfig]
0x180064f85  call    WfpMemFree
0x180064f8a  test    rbx, rbx
0x180064f8d  jz      short loc_180064F9E
0x180064f8f  lea     rdx, aBfefwtriggerge; "BfeFwTriggerGetServiceStartType"
0x180064f96  mov     rcx, rbx
0x180064f99  call    WfpReportError
0x180064f9e  mov     rax, rbx
0x180064fa1  mov     rcx, [rsp+58h+var_28]
0x180064fa6  xor     rcx, rsp; StackCookie
0x180064fa9  call    __security_check_cookie
0x180064fae  mov     rbx, [rsp+58h+arg_10]
0x180064fb3  mov     rbp, [rsp+58h+arg_18]
0x180064fb8  add     rsp, 40h
0x180064fbc  pop     r14
0x180064fbe  pop     rdi
0x180064fbf  pop     rsi
0x180064fc0  retn
```

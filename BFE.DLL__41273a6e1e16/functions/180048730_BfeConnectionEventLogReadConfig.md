# BfeConnectionEventLogReadConfig

- ea: `0x180048730`
- end: `0x18004884d`
- name: `BfeConnectionEventLogReadConfig`
- size: `285`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800486c8`
- `0x1800699e8`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180048730`
- `0x1800592f4`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800487d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800487d5`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x1800487c5`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x1800487c5`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18004876f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18004876f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18004880c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18004880c`

## string_xrefs

- `0x180048792`: `EvtOpenChannelConfig`
- `0x1800487e4`: `EvtGetChannelConfigProperty`
- `0x18004881d`: `BfeConnectionEventLogReadConfig`

## pseudocode

```c
__int64 __fastcall BfeConnectionEventLogReadConfig(LPCWSTR ChannelPath, BOOL *a2)
{
  EVT_HANDLE v3; // rdi
  DWORD v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rbx
  DWORD LastError; // eax
  __int64 v8; // rcx
  DWORD PropertyValueBufferUsed; // [rsp+30h] [rbp-28h] BYREF
  struct _EVT_VARIANT PropertyValueBuffer; // [rsp+38h] [rbp-20h] BYREF

  *a2 = 0;
  PropertyValueBufferUsed = 0;
  PropertyValueBuffer = 0;
  v3 = EvtOpenChannelConfig(0, ChannelPath, 0);
  if ( v3 )
  {
    if ( EvtGetChannelConfigProperty(
           v3,
           EvtChannelConfigEnabled,
           0,
           0x10u,
           &PropertyValueBuffer,
           &PropertyValueBufferUsed) )
    {
      v6 = 0;
      if ( PropertyValueBuffer.Type != 13 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      *a2 = PropertyValueBuffer.BooleanVal;
    }
    else
    {
      LastError = GetLastError();
      v6 = WfpReportSysErrorAsWinError(v8, "EvtGetChannelConfigProperty", LastError);
    }
    EvtClose(v3);
  }
  else
  {
    v4 = GetLastError();
    v6 = WfpReportSysErrorAsWinError(v5, "EvtOpenChannelConfig", v4);
  }
  if ( v6 )
    WfpReportError(v6, "BfeConnectionEventLogReadConfig");
  return v6;
}

```

## disassembly

```asm
0x180048730  mov     [rsp+arg_10], rbx
0x180048735  mov     [rsp+arg_18], rsi
0x18004873a  push    rdi
0x18004873b  sub     rsp, 50h
0x18004873f  mov     rax, cs:__security_cookie
0x180048746  xor     rax, rsp
0x180048749  mov     [rsp+58h+var_10], rax
0x18004874e  mov     rsi, rdx
0x180048751  mov     dword ptr [rdx], 0
0x180048757  mov     rdx, rcx; ChannelPath
0x18004875a  mov     [rsp+58h+var_28], 0
0x180048762  xorps   xmm0, xmm0
0x180048765  xor     ecx, ecx; Session
0x180048767  xor     r8d, r8d; Flags
0x18004876a  movups  xmmword ptr [rsp+58h+var_20], xmm0
0x18004876f  call    cs:__imp_EvtOpenChannelConfig
0x180048776  nop     dword ptr [rax+rax+00h]
0x18004877b  mov     rdi, rax
0x18004877e  test    rax, rax
0x180048781  jnz     short loc_1800487A3
0x180048783  call    cs:__imp_GetLastError
0x18004878a  nop     dword ptr [rax+rax+00h]
0x18004878f  mov     r8d, eax
0x180048792  lea     rdx, aEvtopenchannel_0; "EvtOpenChannelConfig"
0x180048799  call    WfpReportSysErrorAsWinError
0x18004879e  mov     rbx, rax
0x1800487a1  jmp     short loc_180048818
0x1800487a3  lea     rax, [rsp+58h+var_28]
0x1800487a8  mov     r9d, 10h; PropertyValueBufferSize
0x1800487ae  mov     [rsp+58h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x1800487b3  xor     r8d, r8d; Flags
0x1800487b6  lea     rax, [rsp+58h+var_20]
0x1800487bb  xor     edx, edx; PropertyId
0x1800487bd  mov     rcx, rdi; ChannelConfig
0x1800487c0  mov     [rsp+58h+PropertyValueBuffer], rax; PropertyValueBuffer
0x1800487c5  call    cs:__imp_EvtGetChannelConfigProperty
0x1800487cc  nop     dword ptr [rax+rax+00h]
0x1800487d1  test    eax, eax
0x1800487d3  jnz     short loc_1800487F5
0x1800487d5  call    cs:__imp_GetLastError
0x1800487dc  nop     dword ptr [rax+rax+00h]
0x1800487e1  mov     r8d, eax
0x1800487e4  lea     rdx, aEvtgetchannelc_0; "EvtGetChannelConfigProperty"
0x1800487eb  call    WfpReportSysErrorAsWinError
0x1800487f0  mov     rbx, rax
0x1800487f3  jmp     short loc_180048809
0x1800487f5  xor     ebx, ebx
0x1800487f7  cmp     [rsp+58h+var_20.Type], 0Dh
0x1800487fc  jz      short loc_180048803
0x1800487fe  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "evtValue.Type == EvtVarTypeBoolean")
0x180048803  mov     eax, dword ptr [rsp+58h+var_20]
0x180048807  mov     [rsi], eax
0x180048809  mov     rcx, rdi; Object
0x18004880c  call    cs:__imp_EvtClose
0x180048813  nop     dword ptr [rax+rax+00h]
0x180048818  test    rbx, rbx
0x18004881b  jz      short loc_18004882C
0x18004881d  lea     rdx, aBfeconnectione; "BfeConnectionEventLogReadConfig"
0x180048824  mov     rcx, rbx
0x180048827  call    WfpReportError
0x18004882c  mov     rax, rbx
0x18004882f  mov     rcx, [rsp+58h+var_10]
0x180048834  xor     rcx, rsp; StackCookie
0x180048837  call    __security_check_cookie
0x18004883c  mov     rbx, [rsp+58h+arg_10]
0x180048841  mov     rsi, [rsp+58h+arg_18]
0x180048846  add     rsp, 50h
0x18004884a  pop     rdi
0x18004884b  retn
```

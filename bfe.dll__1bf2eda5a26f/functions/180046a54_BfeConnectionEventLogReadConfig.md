# BfeConnectionEventLogReadConfig

- ea: `0x180046a54`
- end: `0x180046b52`
- name: `BfeConnectionEventLogReadConfig`
- size: `254`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800469ec`
- `0x1800674b0`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180046a54`
- `0x1800575c4`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ae7`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x180046add`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x180046add`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x180046a93`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x180046a93`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180046b18`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180046b18`

## string_xrefs

- `0x180046aaa`: `EvtOpenChannelConfig`
- `0x180046af0`: `EvtGetChannelConfigProperty`
- `0x180046b23`: `BfeConnectionEventLogReadConfig`

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
0x180046a54  mov     [rsp+arg_10], rbx
0x180046a59  mov     [rsp+arg_18], rsi
0x180046a5e  push    rdi
0x180046a5f  sub     rsp, 50h
0x180046a63  mov     rax, cs:__security_cookie
0x180046a6a  xor     rax, rsp
0x180046a6d  mov     [rsp+58h+var_10], rax
0x180046a72  mov     rsi, rdx
0x180046a75  mov     dword ptr [rdx], 0
0x180046a7b  mov     rdx, rcx; ChannelPath
0x180046a7e  mov     [rsp+58h+var_28], 0
0x180046a86  xorps   xmm0, xmm0
0x180046a89  xor     ecx, ecx; Session
0x180046a8b  xor     r8d, r8d; Flags
0x180046a8e  movups  xmmword ptr [rsp+58h+var_20], xmm0
0x180046a93  call    cs:__imp_EvtOpenChannelConfig
0x180046a99  mov     rdi, rax
0x180046a9c  test    rax, rax
0x180046a9f  jnz     short loc_180046ABB
0x180046aa1  call    cs:__imp_GetLastError
0x180046aa7  mov     r8d, eax
0x180046aaa  lea     rdx, aEvtopenchannel_0; "EvtOpenChannelConfig"
0x180046ab1  call    WfpReportSysErrorAsWinError
0x180046ab6  mov     rbx, rax
0x180046ab9  jmp     short loc_180046B1E
0x180046abb  lea     rax, [rsp+58h+var_28]
0x180046ac0  mov     r9d, 10h; PropertyValueBufferSize
0x180046ac6  mov     [rsp+58h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x180046acb  xor     r8d, r8d; Flags
0x180046ace  lea     rax, [rsp+58h+var_20]
0x180046ad3  xor     edx, edx; PropertyId
0x180046ad5  mov     rcx, rdi; ChannelConfig
0x180046ad8  mov     [rsp+58h+PropertyValueBuffer], rax; PropertyValueBuffer
0x180046add  call    cs:__imp_EvtGetChannelConfigProperty
0x180046ae3  test    eax, eax
0x180046ae5  jnz     short loc_180046B01
0x180046ae7  call    cs:__imp_GetLastError
0x180046aed  mov     r8d, eax
0x180046af0  lea     rdx, aEvtgetchannelc_0; "EvtGetChannelConfigProperty"
0x180046af7  call    WfpReportSysErrorAsWinError
0x180046afc  mov     rbx, rax
0x180046aff  jmp     short loc_180046B15
0x180046b01  xor     ebx, ebx
0x180046b03  cmp     [rsp+58h+var_20.Type], 0Dh
0x180046b08  jz      short loc_180046B0F
0x180046b0a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046b0f  mov     eax, dword ptr [rsp+58h+var_20]
0x180046b13  mov     [rsi], eax
0x180046b15  mov     rcx, rdi; Object
0x180046b18  call    cs:__imp_EvtClose
0x180046b1e  test    rbx, rbx
0x180046b21  jz      short loc_180046B32
0x180046b23  lea     rdx, aBfeconnectione; "BfeConnectionEventLogReadConfig"
0x180046b2a  mov     rcx, rbx
0x180046b2d  call    WfpReportError
0x180046b32  mov     rax, rbx
0x180046b35  mov     rcx, [rsp+58h+var_10]
0x180046b3a  xor     rcx, rsp; StackCookie
0x180046b3d  call    __security_check_cookie
0x180046b42  mov     rbx, [rsp+58h+arg_10]
0x180046b47  mov     rsi, [rsp+58h+arg_18]
0x180046b4c  add     rsp, 50h
0x180046b50  pop     rdi
0x180046b51  retn
```

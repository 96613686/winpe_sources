# wil::details::lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___::_lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___

- ea: `0x180014da4`
- end: `0x180014e1c`
- name: `wil::details::lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___::_lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800151cc`
- `0x18002874d`

## callees

- `0x1800132d8`
- `0x180013370`
- `0x180014da4`
- `0x180015de0`

## string_xrefs

- `0x180014e09`: `EnableSpecificTask`

## pseudocode

```c
void __fastcall wil::details::lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___::_lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___(
        unsigned int **a1)
{
  __int64 v2; // r8

  if ( *((_BYTE *)a1 + 16) )
  {
    *((_BYTE *)a1 + 16) = 0;
    v2 = **a1;
    if ( (int)v2 >= 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(a1, AutopilotDetectHardwareChangeTaskEnableSucceeded, *(_QWORD *)a1[1]);
    }
    else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      McTemplateU0dz_EventWriteTransfer(a1, AutopilotDetectHardwareChangeTaskEnableFailed, v2, *(_QWORD *)a1[1]);
    }
    Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(
      L"EnableSpecificTask",
      *(const unsigned __int16 **)a1[1],
      **a1);
  }
}

```

## disassembly

```asm
0x180014da4  push    rbx
0x180014da6  sub     rsp, 20h
0x180014daa  mov     rbx, rcx
0x180014dad  cmp     byte ptr [rcx+10h], 0
0x180014db1  jz      short loc_180014E16
0x180014db3  mov     byte ptr [rcx+10h], 0
0x180014db7  mov     rax, [rcx]
0x180014dba  mov     r8d, [rax]
0x180014dbd  test    r8d, r8d
0x180014dc0  jns     short loc_180014DE0
0x180014dc2  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180014dc9  jz      short loc_180014DFC
0x180014dcb  mov     r9, [rcx+8]
0x180014dcf  mov     r9, [r9]
0x180014dd2  lea     rdx, AutopilotDetectHardwareChangeTaskEnableFailed
0x180014dd9  call    McTemplateU0dz_EventWriteTransfer
0x180014dde  jmp     short loc_180014DFC
0x180014de0  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180014de7  jz      short loc_180014DFC
0x180014de9  mov     r8, [rcx+8]
0x180014ded  mov     r8, [r8]
0x180014df0  lea     rdx, AutopilotDetectHardwareChangeTaskEnableSucceeded
0x180014df7  call    McTemplateU0z_EventWriteTransfer
0x180014dfc  mov     r8, [rbx]
0x180014dff  mov     rdx, [rbx+8]
0x180014e03  mov     r8d, [r8]; int
0x180014e06  mov     rdx, [rdx]; unsigned __int16 *
0x180014e09  lea     rcx, aEnablespecific; "EnableSpecificTask"
0x180014e10  call    ?LogAutopilotTaskTelemetryEvent@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(ushort const *,ushort const *,long)
0x180014e15  nop
0x180014e16  add     rsp, 20h
0x180014e1a  pop     rbx
0x180014e1b  retn
```

# wil::details::lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___::_lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___

- ea: `0x18001511c`
- end: `0x180015195`
- name: `wil::details::lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___::_lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800168c0`
- `0x180029a8a`

## callees

- `0x180013580`
- `0x180013618`
- `0x18001511c`
- `0x18001625c`

## string_xrefs

- `0x180015181`: `DisableSpecifiedTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___::_lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___(
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
        McTemplateU0z_EventWriteTransfer(a1, AutopilotDetectHardwareChangeTaskDisableSucceeded, *(_QWORD *)a1[1]);
    }
    else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      McTemplateU0dz_EventWriteTransfer(a1, AutopilotDetectHardwareChangeTaskDisableFailed, v2, *(_QWORD *)a1[1]);
    }
    Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(
      L"DisableSpecifiedTask",
      *(const unsigned __int16 **)a1[1],
      **a1);
  }
}

```

## disassembly

```asm
0x18001511c  push    rbx
0x18001511e  sub     rsp, 20h
0x180015122  mov     rbx, rcx
0x180015125  cmp     byte ptr [rcx+10h], 0
0x180015129  jz      short loc_18001518E
0x18001512b  mov     byte ptr [rcx+10h], 0
0x18001512f  mov     rax, [rcx]
0x180015132  mov     r8d, [rax]
0x180015135  test    r8d, r8d
0x180015138  jns     short loc_180015158
0x18001513a  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180015141  jz      short loc_180015174
0x180015143  mov     r9, [rcx+8]
0x180015147  mov     r9, [r9]
0x18001514a  lea     rdx, AutopilotDetectHardwareChangeTaskDisableFailed
0x180015151  call    McTemplateU0dz_EventWriteTransfer
0x180015156  jmp     short loc_180015174
0x180015158  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18001515f  jz      short loc_180015174
0x180015161  mov     r8, [rcx+8]
0x180015165  mov     r8, [r8]
0x180015168  lea     rdx, AutopilotDetectHardwareChangeTaskDisableSucceeded
0x18001516f  call    McTemplateU0z_EventWriteTransfer
0x180015174  mov     r8, [rbx]
0x180015177  mov     rdx, [rbx+8]
0x18001517b  mov     r8d, [r8]; int
0x18001517e  mov     rdx, [rdx]; unsigned __int16 *
0x180015181  lea     rcx, aDisablespecifi; "DisableSpecifiedTask"
0x180015188  call    ?LogAutopilotTaskTelemetryEvent@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(ushort const *,ushort const *,long)
0x18001518d  nop
0x18001518e  add     rsp, 20h
0x180015192  pop     rbx
0x180015193  retn
```

# wil::details::lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___::_lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___

- ea: `0x180014d24`
- end: `0x180014d9c`
- name: `wil::details::lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___::_lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180016420`
- `0x1800287b9`

## callees

- `0x1800132d8`
- `0x180013370`
- `0x180014d24`
- `0x180015de0`

## string_xrefs

- `0x180014d89`: `DisableSpecifiedTask`

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
0x180014d24  push    rbx
0x180014d26  sub     rsp, 20h
0x180014d2a  mov     rbx, rcx
0x180014d2d  cmp     byte ptr [rcx+10h], 0
0x180014d31  jz      short loc_180014D96
0x180014d33  mov     byte ptr [rcx+10h], 0
0x180014d37  mov     rax, [rcx]
0x180014d3a  mov     r8d, [rax]
0x180014d3d  test    r8d, r8d
0x180014d40  jns     short loc_180014D60
0x180014d42  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180014d49  jz      short loc_180014D7C
0x180014d4b  mov     r9, [rcx+8]
0x180014d4f  mov     r9, [r9]
0x180014d52  lea     rdx, AutopilotDetectHardwareChangeTaskDisableFailed
0x180014d59  call    McTemplateU0dz_EventWriteTransfer
0x180014d5e  jmp     short loc_180014D7C
0x180014d60  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180014d67  jz      short loc_180014D7C
0x180014d69  mov     r8, [rcx+8]
0x180014d6d  mov     r8, [r8]
0x180014d70  lea     rdx, AutopilotDetectHardwareChangeTaskDisableSucceeded
0x180014d77  call    McTemplateU0z_EventWriteTransfer
0x180014d7c  mov     r8, [rbx]
0x180014d7f  mov     rdx, [rbx+8]
0x180014d83  mov     r8d, [r8]; int
0x180014d86  mov     rdx, [rdx]; unsigned __int16 *
0x180014d89  lea     rcx, aDisablespecifi; "DisableSpecifiedTask"
0x180014d90  call    ?LogAutopilotTaskTelemetryEvent@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(ushort const *,ushort const *,long)
0x180014d95  nop
0x180014d96  add     rsp, 20h
0x180014d9a  pop     rbx
0x180014d9b  retn
```

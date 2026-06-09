# wil::details::lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___::_lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___

- ea: `0x18001519c`
- end: `0x180015215`
- name: `wil::details::lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___::_lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800155d4`
- `0x180029a1e`

## callees

- `0x180013580`
- `0x180013618`
- `0x18001519c`
- `0x18001625c`

## string_xrefs

- `0x180015201`: `EnableSpecificTask`

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
0x18001519c  push    rbx
0x18001519e  sub     rsp, 20h
0x1800151a2  mov     rbx, rcx
0x1800151a5  cmp     byte ptr [rcx+10h], 0
0x1800151a9  jz      short loc_18001520E
0x1800151ab  mov     byte ptr [rcx+10h], 0
0x1800151af  mov     rax, [rcx]
0x1800151b2  mov     r8d, [rax]
0x1800151b5  test    r8d, r8d
0x1800151b8  jns     short loc_1800151D8
0x1800151ba  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1800151c1  jz      short loc_1800151F4
0x1800151c3  mov     r9, [rcx+8]
0x1800151c7  mov     r9, [r9]
0x1800151ca  lea     rdx, AutopilotDetectHardwareChangeTaskEnableFailed
0x1800151d1  call    McTemplateU0dz_EventWriteTransfer
0x1800151d6  jmp     short loc_1800151F4
0x1800151d8  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800151df  jz      short loc_1800151F4
0x1800151e1  mov     r8, [rcx+8]
0x1800151e5  mov     r8, [r8]
0x1800151e8  lea     rdx, AutopilotDetectHardwareChangeTaskEnableSucceeded
0x1800151ef  call    McTemplateU0z_EventWriteTransfer
0x1800151f4  mov     r8, [rbx]
0x1800151f7  mov     rdx, [rbx+8]
0x1800151fb  mov     r8d, [r8]; int
0x1800151fe  mov     rdx, [rdx]; unsigned __int16 *
0x180015201  lea     rcx, aEnablespecific; "EnableSpecificTask"
0x180015208  call    ?LogAutopilotTaskTelemetryEvent@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(ushort const *,ushort const *,long)
0x18001520d  nop
0x18001520e  add     rsp, 20h
0x180015212  pop     rbx
0x180015213  retn
```

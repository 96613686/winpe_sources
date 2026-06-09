# EvtDriverUnload

- ea: `0x140024f00`
- end: `0x140025027`
- name: `EvtDriverUnload`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x140006aa4`
- `0x140024f00`
- `0x140047e90`
- `0x140065008`
- `0x140066384`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140024fff`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140024fff`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140024fdc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140024fdc`
- `ntoskrnl!EtwUnregister` at `0x140024f71`
- `ntoskrnl!EtwUnregister` at `0x140024f94`
- `ntoskrnl!EtwUnregister` at `0x140024f71`
- `ntoskrnl!EtwUnregister` at `0x140024f94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f1c`

## pseudocode

```c
__int64 __fastcall EvtDriverUnload(__int64 a1)
{
  __int64 v2; // rax
  __int64 result; // rax

  TlgUnregisterAggregateProvider();
  if ( WPP_MAIN_CB.Dpc.DpcData )
    ExFreePoolWithTag(WPP_MAIN_CB.Dpc.DpcData, 0);
  MbbIpCleanup((struct _MINIPORT_DRIVER_CONTEXT *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext);
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceRoutine )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1664))(WdfDriverGlobals);
    WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = 0;
  }
  if ( WPP_MAIN_CB.DeviceQueue.1 )
  {
    EtwUnregister(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32);
    WPP_MAIN_CB.DeviceQueue.1 = 0;
  }
  if ( WPP_MAIN_CB.Dpc.DpcListEntry.Next )
  {
    EtwUnregister((REGHANDLE)WPP_MAIN_CB.Dpc.DpcListEntry.Next);
    WPP_MAIN_CB.Dpc.DpcListEntry.Next = 0;
  }
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 944))(WdfDriverGlobals, a1);
  result = WppCleanupKm(v2);
  if ( g_wil_details_featureChangeNotification )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return result;
}

```

## disassembly

```asm
0x140024f00  push    rbx
0x140024f02  sub     rsp, 20h
0x140024f06  mov     rbx, rcx
0x140024f09  call    TlgUnregisterAggregateProvider
0x140024f0e  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcData; P
0x140024f15  test    rcx, rcx
0x140024f18  jz      short loc_140024F28
0x140024f1a  xor     edx, edx; Tag
0x140024f1c  call    cs:__imp_ExFreePoolWithTag
0x140024f23  nop     dword ptr [rax+rax+00h]
0x140024f28  lea     rcx, WPP_MAIN_CB.Queue+20h; struct _MINIPORT_DRIVER_CONTEXT *
0x140024f2f  call    ?MbbIpCleanup@@YAXPEAU_MINIPORT_DRIVER_CONTEXT@@@Z; MbbIpCleanup(_MINIPORT_DRIVER_CONTEXT *)
0x140024f34  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x140024f3b  test    rdx, rdx
0x140024f3e  jz      short loc_140024F65
0x140024f40  mov     rax, cs:WdfFunctions_01031
0x140024f47  mov     rcx, cs:WdfDriverGlobals
0x140024f4e  mov     rax, [rax+680h]
0x140024f55  call    _guard_dispatch_icall
0x140024f5a  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, 0
0x140024f65  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h; RegHandle
0x140024f6c  test    rcx, rcx
0x140024f6f  jz      short loc_140024F88
0x140024f71  call    cs:__imp_EtwUnregister
0x140024f78  nop     dword ptr [rax+rax+00h]
0x140024f7d  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 0
0x140024f88  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next; RegHandle
0x140024f8f  test    rcx, rcx
0x140024f92  jz      short loc_140024FAB
0x140024f94  call    cs:__imp_EtwUnregister
0x140024f9b  nop     dword ptr [rax+rax+00h]
0x140024fa0  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, 0
0x140024fab  mov     rax, cs:WdfFunctions_01031
0x140024fb2  mov     rdx, rbx
0x140024fb5  mov     rcx, cs:WdfDriverGlobals
0x140024fbc  mov     rax, [rax+3B0h]
0x140024fc3  call    _guard_dispatch_icall
0x140024fc8  mov     rcx, rax
0x140024fcb  call    WppCleanupKm
0x140024fd0  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140024fd7  test    rcx, rcx
0x140024fda  jz      short loc_140024FF3
0x140024fdc  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140024fe3  nop     dword ptr [rax+rax+00h]
0x140024fe8  mov     cs:g_wil_details_featureChangeNotification, 0
0x140024ff3  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140024ffa  test    rcx, rcx
0x140024ffd  jz      short loc_140025016
0x140024fff  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140025006  nop     dword ptr [rax+rax+00h]
0x14002500b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140025016  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140025020  add     rsp, 20h
0x140025024  pop     rbx
0x140025025  retn
```

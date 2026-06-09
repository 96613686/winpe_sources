# DllUnload

- ea: `0x18000cd20`
- end: `0x18000cd8c`
- name: `DllUnload`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000cd20`
- `0x18001f4e4`
- `0x1800525e4`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x18000cd3b`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x18000cd3b`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x18000cd5e`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x18000cd5e`

## pseudocode

```c
__int64 __fastcall DllUnload(__int64 a1, __int64 a2, __int64 a3)
{
  WfpComponentsDispatchReverse(a1, a2, a3, 8);
  if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.SecurityDescriptor) = 0;
  WppCleanupKm();
  return 0;
}

```

## disassembly

```asm
0x18000cd20  sub     rsp, 28h
0x18000cd24  mov     r9d, 8
0x18000cd2a  call    WfpComponentsDispatchReverse
0x18000cd2f  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x18000cd36  test    rcx, rcx
0x18000cd39  jz      short loc_18000CD52
0x18000cd3b  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x18000cd42  nop     dword ptr [rax+rax+00h]
0x18000cd47  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x18000cd52  mov     rcx, cs:g_wil_details_featureUsageProvider
0x18000cd59  test    rcx, rcx
0x18000cd5c  jz      short loc_18000CD75
0x18000cd5e  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x18000cd65  nop     dword ptr [rax+rax+00h]
0x18000cd6a  mov     cs:g_wil_details_featureUsageProvider, 0
0x18000cd75  mov     dword ptr cs:WPP_MAIN_CB.SecurityDescriptor, 0
0x18000cd7f  call    WppCleanupKm
0x18000cd84  xor     eax, eax
0x18000cd86  add     rsp, 28h
0x18000cd8a  retn
```

# DumpUninitialize

- ea: `0x140003190`
- end: `0x1400031ea`
- name: `DumpUninitialize`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003190`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400031c3`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400031c3`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400031a0`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400031a0`

## pseudocode

```c
__int64 DumpUninitialize()
{
  __int64 result; // rax

  if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 0;
  return result;
}

```

## disassembly

```asm
0x140003190  sub     rsp, 28h
0x140003194  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14000319b  test    rcx, rcx
0x14000319e  jz      short loc_1400031B7
0x1400031a0  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400031a7  nop     dword ptr [rax+rax+00h]
0x1400031ac  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x1400031b7  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400031be  test    rcx, rcx
0x1400031c1  jz      short loc_1400031DA
0x1400031c3  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400031ca  nop     dword ptr [rax+rax+00h]
0x1400031cf  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400031da  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x1400031e4  add     rsp, 28h
0x1400031e8  retn
```

# wil_UninitializeFeatureStaging

- ea: `0x14002132c`
- end: `0x140021386`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140010770`

## callees

- `0x14002132c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002135f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002135f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002133c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002133c`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
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
0x14002132c  sub     rsp, 28h
0x140021330  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140021337  test    rcx, rcx
0x14002133a  jz      short loc_140021353
0x14002133c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140021343  nop     dword ptr [rax+rax+00h]
0x140021348  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x140021353  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14002135a  test    rcx, rcx
0x14002135d  jz      short loc_140021376
0x14002135f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140021366  nop     dword ptr [rax+rax+00h]
0x14002136b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140021376  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x140021380  add     rsp, 28h
0x140021384  retn
```

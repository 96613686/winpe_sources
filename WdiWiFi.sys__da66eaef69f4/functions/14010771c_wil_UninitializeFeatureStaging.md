# wil_UninitializeFeatureStaging

- ea: `0x14010771c`
- end: `0x140107776`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400c5dbc`
- `0x1400c6000`

## callees

- `0x14010771c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14010772c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14010772c`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14010774f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14010774f`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

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
0x14010771c  sub     rsp, 28h
0x140107720  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140107727  test    rcx, rcx
0x14010772a  jz      short loc_140107743
0x14010772c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140107733  nop     dword ptr [rax+rax+00h]
0x140107738  mov     cs:g_wil_details_featureChangeNotification, 0
0x140107743  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14010774a  test    rcx, rcx
0x14010774d  jz      short loc_140107766
0x14010774f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140107756  nop     dword ptr [rax+rax+00h]
0x14010775b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140107766  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140107770  add     rsp, 28h
0x140107774  retn
```

# wil_UninitializeFeatureStaging

- ea: `0x1400846cc`
- end: `0x140084726`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14003baa0`
- `0x14003c5e0`

## callees

- `0x1400846cc`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400846ff`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400846ff`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400846dc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400846dc`

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
0x1400846cc  sub     rsp, 28h
0x1400846d0  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400846d7  test    rcx, rcx
0x1400846da  jz      short loc_1400846F3
0x1400846dc  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400846e3  nop     dword ptr [rax+rax+00h]
0x1400846e8  mov     cs:g_wil_details_featureChangeNotification, 0
0x1400846f3  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400846fa  test    rcx, rcx
0x1400846fd  jz      short loc_140084716
0x1400846ff  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140084706  nop     dword ptr [rax+rax+00h]
0x14008470b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140084716  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140084720  add     rsp, 28h
0x140084724  retn
```

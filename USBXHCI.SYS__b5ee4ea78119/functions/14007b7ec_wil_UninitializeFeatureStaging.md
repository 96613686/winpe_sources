# wil_UninitializeFeatureStaging

- ea: `0x14007b7ec`
- end: `0x14007b846`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14007553c`
- `0x14007b2f0`

## callees

- `0x14007b7ec`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14007b81f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14007b81f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14007b7fc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14007b7fc`

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
0x14007b7ec  sub     rsp, 28h
0x14007b7f0  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14007b7f7  test    rcx, rcx
0x14007b7fa  jz      short loc_14007B813
0x14007b7fc  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14007b803  nop     dword ptr [rax+rax+00h]
0x14007b808  mov     cs:g_wil_details_featureChangeNotification, 0
0x14007b813  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14007b81a  test    rcx, rcx
0x14007b81d  jz      short loc_14007B836
0x14007b81f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14007b826  nop     dword ptr [rax+rax+00h]
0x14007b82b  mov     cs:g_wil_details_featureUsageProvider, 0
0x14007b836  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14007b840  add     rsp, 28h
0x14007b844  retn
```

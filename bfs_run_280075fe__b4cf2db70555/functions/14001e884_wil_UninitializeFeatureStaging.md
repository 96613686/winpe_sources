# wil_UninitializeFeatureStaging

- ea: `0x14001e884`
- end: `0x14001e8de`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001e020`
- `0x14001f078`

## callees

- `0x14001e884`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001e894`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001e894`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001e8b7`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001e8b7`

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
0x14001e884  sub     rsp, 28h
0x14001e888  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14001e88f  test    rcx, rcx
0x14001e892  jz      short loc_14001E8AB
0x14001e894  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14001e89b  nop     dword ptr [rax+rax+00h]
0x14001e8a0  mov     cs:g_wil_details_featureChangeNotification, 0
0x14001e8ab  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14001e8b2  test    rcx, rcx
0x14001e8b5  jz      short loc_14001E8CE
0x14001e8b7  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14001e8be  nop     dword ptr [rax+rax+00h]
0x14001e8c3  mov     cs:g_wil_details_featureUsageProvider, 0
0x14001e8ce  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14001e8d8  add     rsp, 28h
0x14001e8dc  retn
```

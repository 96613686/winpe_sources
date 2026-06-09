# wil_UninitializeFeatureStaging

- ea: `0x14000b4d4`
- end: `0x14000b52e`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000b260`
- `0x140016078`

## callees

- `0x14000b4d4`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000b4e4`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000b4e4`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000b507`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000b507`

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
0x14000b4d4  sub     rsp, 28h
0x14000b4d8  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000b4df  test    rcx, rcx
0x14000b4e2  jz      short loc_14000B4FB
0x14000b4e4  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000b4eb  nop     dword ptr [rax+rax+00h]
0x14000b4f0  mov     cs:g_wil_details_featureChangeNotification, 0
0x14000b4fb  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000b502  test    rcx, rcx
0x14000b505  jz      short loc_14000B51E
0x14000b507  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000b50e  nop     dword ptr [rax+rax+00h]
0x14000b513  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000b51e  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000b528  add     rsp, 28h
0x14000b52c  retn
```

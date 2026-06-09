# wil_UninitializeFeatureStaging

- ea: `0x14011fd30`
- end: `0x14011fd8a`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140035740`
- `0x14012103c`

## callees

- `0x14011fd30`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14011fd40`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14011fd40`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14011fd63`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14011fd63`

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
0x14011fd30  sub     rsp, 28h
0x14011fd34  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14011fd3b  test    rcx, rcx
0x14011fd3e  jz      short loc_14011FD57
0x14011fd40  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14011fd47  nop     dword ptr [rax+rax+00h]
0x14011fd4c  mov     cs:g_wil_details_featureChangeNotification, 0
0x14011fd57  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14011fd5e  test    rcx, rcx
0x14011fd61  jz      short loc_14011FD7A
0x14011fd63  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14011fd6a  nop     dword ptr [rax+rax+00h]
0x14011fd6f  mov     cs:g_wil_details_featureUsageProvider, 0
0x14011fd7a  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14011fd84  add     rsp, 28h
0x14011fd88  retn
```

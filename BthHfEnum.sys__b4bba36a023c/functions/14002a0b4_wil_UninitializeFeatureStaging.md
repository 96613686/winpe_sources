# wil_UninitializeFeatureStaging

- ea: `0x14002a0b4`
- end: `0x14002a10e`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140028f40`
- `0x14003003c`

## callees

- `0x14002a0b4`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002a0e7`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002a0e7`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002a0c4`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002a0c4`

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
  if ( *((_QWORD *)&WPP_MAIN_CB.Reserved + 1) )
  {
    result = RtlUnregisterFeatureUsageProvider();
    *((_QWORD *)&WPP_MAIN_CB.Reserved + 1) = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return result;
}

```

## disassembly

```asm
0x14002a0b4  sub     rsp, 28h
0x14002a0b8  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14002a0bf  test    rcx, rcx
0x14002a0c2  jz      short loc_14002A0DB
0x14002a0c4  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14002a0cb  nop     dword ptr [rax+rax+00h]
0x14002a0d0  mov     cs:g_wil_details_featureChangeNotification, 0
0x14002a0db  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x14002a0e2  test    rcx, rcx
0x14002a0e5  jz      short loc_14002A0FE
0x14002a0e7  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14002a0ee  nop     dword ptr [rax+rax+00h]
0x14002a0f3  mov     qword ptr cs:WPP_MAIN_CB+148h, 0
0x14002a0fe  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002a108  add     rsp, 28h
0x14002a10c  retn
```

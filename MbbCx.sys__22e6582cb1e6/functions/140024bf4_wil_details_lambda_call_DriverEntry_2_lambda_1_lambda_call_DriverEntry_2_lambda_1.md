# wil::details::lambda_call__DriverEntry_::_2_::_lambda_1___::_lambda_call__DriverEntry_::_2_::_lambda_1___

- ea: `0x140024bf4`
- end: `0x140024c58`
- name: `wil::details::lambda_call__DriverEntry_::_2_::_lambda_1___::_lambda_call__DriverEntry_::_2_::_lambda_1___`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14006703c`

## callees

- `0x140024bf4`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140024c31`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140024c31`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140024c0e`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140024c0e`

## pseudocode

```c
__int64 __fastcall wil::details::lambda_call__DriverEntry_::_2_::_lambda_1___::_lambda_call__DriverEntry_::_2_::_lambda_1___(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
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
  }
  return result;
}

```

## disassembly

```asm
0x140024bf4  sub     rsp, 28h
0x140024bf8  cmp     byte ptr [rcx+1], 0
0x140024bfc  jz      short loc_140024C52
0x140024bfe  mov     byte ptr [rcx+1], 0
0x140024c02  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140024c09  test    rcx, rcx
0x140024c0c  jz      short loc_140024C25
0x140024c0e  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140024c15  nop     dword ptr [rax+rax+00h]
0x140024c1a  mov     cs:g_wil_details_featureChangeNotification, 0
0x140024c25  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140024c2c  test    rcx, rcx
0x140024c2f  jz      short loc_140024C48
0x140024c31  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140024c38  nop     dword ptr [rax+rax+00h]
0x140024c3d  mov     cs:g_wil_details_featureUsageProvider, 0
0x140024c48  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140024c52  add     rsp, 28h
0x140024c56  retn
```

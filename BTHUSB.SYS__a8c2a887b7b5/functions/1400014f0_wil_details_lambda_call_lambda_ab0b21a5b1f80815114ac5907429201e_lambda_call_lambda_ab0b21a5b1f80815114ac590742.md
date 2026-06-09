# wil::details::lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___::_lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___

- ea: `0x1400014f0`
- end: `0x14000155c`
- name: `wil::details::lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___::_lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001d03c`

## callees

- `0x1400014f0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140001535`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140001535`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140001512`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140001512`

## pseudocode

```c
int *__fastcall wil::details::lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___::_lambda_call__lambda_ab0b21a5b1f80815114ac5907429201e___(
        __int64 a1)
{
  int *result; // rax

  if ( *(_BYTE *)(a1 + 8) )
  {
    result = *(int **)a1;
    *(_BYTE *)(a1 + 8) = 0;
    if ( *result < 0 )
    {
      if ( g_wil_details_featureChangeNotification )
      {
        result = (int *)RtlUnregisterFeatureConfigurationChangeNotification();
        g_wil_details_featureChangeNotification = 0;
      }
      if ( *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type )
      {
        result = (int *)RtlUnregisterFeatureUsageProvider();
        *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 0;
      }
      g_wil_details_isFeatureStagingInitialized = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400014f0  sub     rsp, 28h
0x1400014f4  cmp     byte ptr [rcx+8], 0
0x1400014f8  jz      short loc_140001556
0x1400014fa  mov     rax, [rcx]
0x1400014fd  mov     byte ptr [rcx+8], 0
0x140001501  cmp     dword ptr [rax], 0
0x140001504  jge     short loc_140001556
0x140001506  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000150d  test    rcx, rcx
0x140001510  jz      short loc_140001529
0x140001512  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140001519  nop     dword ptr [rax+rax+00h]
0x14000151e  mov     cs:g_wil_details_featureChangeNotification, 0
0x140001529  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x140001530  test    rcx, rcx
0x140001533  jz      short loc_14000154C
0x140001535  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000153c  nop     dword ptr [rax+rax+00h]
0x140001541  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, 0
0x14000154c  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140001556  add     rsp, 28h
0x14000155a  retn
```

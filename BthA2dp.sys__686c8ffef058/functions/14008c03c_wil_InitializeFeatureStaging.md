# wil_InitializeFeatureStaging

- ea: `0x14008c03c`
- end: `0x14008c0f5`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003c5e0`

## callees

- `0x14003cdc8`
- `0x14008478c`
- `0x140084a2c`
- `0x14008c03c`
- `0x14008c0fc`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14008c0bc`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14008c0bc`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14008c064`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14008c064`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  __int64 **i; // rcx
  _BYTE *v2; // rax
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  v0 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 **)(v2 + 56) )
  {
    v2 = (_BYTE *)wil_details_FeatureDescriptors_SkipPadding(i);
    if ( !v2 )
      break;
    if ( !v2[29] && !v2[30] && !v2[28] )
    {
      if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                           wil_details_ReevaluateOnFeatureConfigurationChange,
                           0,
                           &v4,
                           &g_wil_details_featureChangeNotification) )
        g_wil_details_featureChangeNotification = 0;
      else
        v0 = 1;
      break;
    }
  }
  result = wil_details_RegisterFeatureUsageProvider();
  if ( !(_DWORD)result )
    return 0;
  if ( v0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14008c03c  push    rbx
0x14008c03e  sub     rsp, 20h
0x14008c042  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14008c049  mov     [rsp+28h+arg_0], 0
0x14008c052  jnz     loc_14008C0EC
0x14008c058  xor     ebx, ebx
0x14008c05a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14008c064  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14008c06b  nop     dword ptr [rax+rax+00h]
0x14008c070  mov     [rsp+28h+arg_0], rax
0x14008c075  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14008c07a  call    wil_details_EvaluateFeatureDependencies
0x14008c07f  lea     rcx, wil_details_featureDescriptors_a
0x14008c086  jmp     short loc_14008C09B
0x14008c088  cmp     [rax+1Dh], bl
0x14008c08b  jnz     short loc_14008C097
0x14008c08d  cmp     [rax+1Eh], bl
0x14008c090  jnz     short loc_14008C097
0x14008c092  cmp     [rax+1Ch], bl
0x14008c095  jz      short loc_14008C0A7
0x14008c097  lea     rcx, [rax+38h]
0x14008c09b  call    wil_details_FeatureDescriptors_SkipPadding
0x14008c0a0  test    rax, rax
0x14008c0a3  jnz     short loc_14008C088
0x14008c0a5  jmp     short loc_14008C0DA
0x14008c0a7  lea     r9, g_wil_details_featureChangeNotification
0x14008c0ae  xor     edx, edx
0x14008c0b0  lea     r8, [rsp+28h+arg_0]
0x14008c0b5  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14008c0bc  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14008c0c3  nop     dword ptr [rax+rax+00h]
0x14008c0c8  test    eax, eax
0x14008c0ca  jz      short loc_14008C0D5
0x14008c0cc  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14008c0d3  jmp     short loc_14008C0DA
0x14008c0d5  mov     ebx, 1
0x14008c0da  call    wil_details_RegisterFeatureUsageProvider
0x14008c0df  test    eax, eax
0x14008c0e1  jz      short loc_14008C0EC
0x14008c0e3  xor     ecx, ecx
0x14008c0e5  test    ebx, ebx
0x14008c0e7  cmovnz  eax, ecx
0x14008c0ea  jmp     short loc_14008C0EE
0x14008c0ec  xor     eax, eax
0x14008c0ee  add     rsp, 20h
0x14008c0f2  pop     rbx
0x14008c0f3  retn
```

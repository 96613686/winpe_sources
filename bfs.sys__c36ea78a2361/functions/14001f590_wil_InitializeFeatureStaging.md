# wil_InitializeFeatureStaging

- ea: `0x14001f590`
- end: `0x14001f647`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001f078`

## callees

- `0x140004784`
- `0x14001e944`
- `0x14001ebec`
- `0x14001f590`
- `0x14001f650`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001f60e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001f60e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14001f5b8`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14001f5b8`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  __int64 *i; // rcx
  __int64 *v2; // rax
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
  for ( i = (__int64 *)wil_details_featureDescriptors_a; ; i = v2 + 7 )
  {
    v2 = wil_details_FeatureDescriptors_SkipPadding(i);
    if ( !v2 )
      break;
    if ( !*((_BYTE *)v2 + 29) && !*((_BYTE *)v2 + 30) && !*((_BYTE *)v2 + 28) )
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
0x14001f590  push    rbx
0x14001f592  sub     rsp, 20h
0x14001f596  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14001f59d  mov     [rsp+28h+arg_0], 0
0x14001f5a6  jnz     loc_14001F63E
0x14001f5ac  xor     ebx, ebx
0x14001f5ae  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14001f5b8  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14001f5bf  nop     dword ptr [rax+rax+00h]
0x14001f5c4  mov     [rsp+28h+arg_0], rax
0x14001f5c9  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14001f5ce  call    wil_details_EvaluateFeatureDependencies
0x14001f5d3  lea     rcx, wil_details_featureDescriptors_a
0x14001f5da  call    wil_details_FeatureDescriptors_SkipPadding
0x14001f5df  test    rax, rax
0x14001f5e2  jz      short loc_14001F62C
0x14001f5e4  cmp     [rax+1Dh], bl
0x14001f5e7  jnz     short loc_14001F5F3
0x14001f5e9  cmp     [rax+1Eh], bl
0x14001f5ec  jnz     short loc_14001F5F3
0x14001f5ee  cmp     [rax+1Ch], bl
0x14001f5f1  jz      short loc_14001F5F9
0x14001f5f3  lea     rcx, [rax+38h]
0x14001f5f7  jmp     short loc_14001F5DA
0x14001f5f9  lea     r9, g_wil_details_featureChangeNotification
0x14001f600  xor     edx, edx
0x14001f602  lea     r8, [rsp+28h+arg_0]
0x14001f607  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14001f60e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14001f615  nop     dword ptr [rax+rax+00h]
0x14001f61a  test    eax, eax
0x14001f61c  jz      short loc_14001F627
0x14001f61e  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14001f625  jmp     short loc_14001F62C
0x14001f627  mov     ebx, 1
0x14001f62c  call    wil_details_RegisterFeatureUsageProvider
0x14001f631  test    eax, eax
0x14001f633  jz      short loc_14001F63E
0x14001f635  xor     ecx, ecx
0x14001f637  test    ebx, ebx
0x14001f639  cmovnz  eax, ecx
0x14001f63c  jmp     short loc_14001F640
0x14001f63e  xor     eax, eax
0x14001f640  add     rsp, 20h
0x14001f644  pop     rbx
0x14001f645  retn
```

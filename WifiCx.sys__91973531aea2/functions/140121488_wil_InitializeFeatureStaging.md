# wil_InitializeFeatureStaging

- ea: `0x140121488`
- end: `0x14012153f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14012103c`

## callees

- `0x1400d94bc`
- `0x14011fdf0`
- `0x14012008c`
- `0x140121488`
- `0x140121548`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1401214b0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1401214b0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140121506`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140121506`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  int **i; // rcx
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
  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v2 + 56) )
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
0x140121488  push    rbx
0x14012148a  sub     rsp, 20h
0x14012148e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140121495  mov     [rsp+28h+arg_0], 0
0x14012149e  jnz     loc_140121536
0x1401214a4  xor     ebx, ebx
0x1401214a6  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1401214b0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1401214b7  nop     dword ptr [rax+rax+00h]
0x1401214bc  mov     [rsp+28h+arg_0], rax
0x1401214c1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1401214c6  call    wil_details_EvaluateFeatureDependencies
0x1401214cb  lea     rcx, wil_details_featureDescriptors_a
0x1401214d2  call    wil_details_FeatureDescriptors_SkipPadding
0x1401214d7  test    rax, rax
0x1401214da  jz      short loc_140121524
0x1401214dc  cmp     [rax+1Dh], bl
0x1401214df  jnz     short loc_1401214EB
0x1401214e1  cmp     [rax+1Eh], bl
0x1401214e4  jnz     short loc_1401214EB
0x1401214e6  cmp     [rax+1Ch], bl
0x1401214e9  jz      short loc_1401214F1
0x1401214eb  lea     rcx, [rax+38h]
0x1401214ef  jmp     short loc_1401214D2
0x1401214f1  lea     r9, g_wil_details_featureChangeNotification
0x1401214f8  xor     edx, edx
0x1401214fa  lea     r8, [rsp+28h+arg_0]
0x1401214ff  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140121506  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14012150d  nop     dword ptr [rax+rax+00h]
0x140121512  test    eax, eax
0x140121514  jz      short loc_14012151F
0x140121516  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14012151d  jmp     short loc_140121524
0x14012151f  mov     ebx, 1
0x140121524  call    wil_details_RegisterFeatureUsageProvider
0x140121529  test    eax, eax
0x14012152b  jz      short loc_140121536
0x14012152d  xor     ecx, ecx
0x14012152f  test    ebx, ebx
0x140121531  cmovnz  eax, ecx
0x140121534  jmp     short loc_140121538
0x140121536  xor     eax, eax
0x140121538  add     rsp, 20h
0x14012153c  pop     rbx
0x14012153d  retn
```

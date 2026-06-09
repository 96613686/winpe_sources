# wil_InitializeFeatureStaging

- ea: `0x14008503c`
- end: `0x1400850f3`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14007553c`

## callees

- `0x140046e28`
- `0x14007b8ac`
- `0x14007bafc`
- `0x14008503c`
- `0x1400850fc`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400850ba`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400850ba`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140085064`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140085064`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  _UNKNOWN **i; // rcx
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
  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 56) )
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
0x14008503c  push    rbx
0x14008503e  sub     rsp, 20h
0x140085042  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140085049  mov     [rsp+28h+arg_0], 0
0x140085052  jnz     loc_1400850EA
0x140085058  xor     ebx, ebx
0x14008505a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140085064  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14008506b  nop     dword ptr [rax+rax+00h]
0x140085070  mov     [rsp+28h+arg_0], rax
0x140085075  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14008507a  call    wil_details_EvaluateFeatureDependencies
0x14008507f  lea     rcx, wil_details_featureDescriptors_a
0x140085086  call    wil_details_FeatureDescriptors_SkipPadding
0x14008508b  test    rax, rax
0x14008508e  jz      short loc_1400850D8
0x140085090  cmp     [rax+1Dh], bl
0x140085093  jnz     short loc_14008509F
0x140085095  cmp     [rax+1Eh], bl
0x140085098  jnz     short loc_14008509F
0x14008509a  cmp     [rax+1Ch], bl
0x14008509d  jz      short loc_1400850A5
0x14008509f  lea     rcx, [rax+38h]
0x1400850a3  jmp     short loc_140085086
0x1400850a5  lea     r9, g_wil_details_featureChangeNotification
0x1400850ac  xor     edx, edx
0x1400850ae  lea     r8, [rsp+28h+arg_0]
0x1400850b3  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400850ba  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400850c1  nop     dword ptr [rax+rax+00h]
0x1400850c6  test    eax, eax
0x1400850c8  jz      short loc_1400850D3
0x1400850ca  mov     cs:g_wil_details_featureChangeNotification, rbx
0x1400850d1  jmp     short loc_1400850D8
0x1400850d3  mov     ebx, 1
0x1400850d8  call    wil_details_RegisterFeatureUsageProvider
0x1400850dd  test    eax, eax
0x1400850df  jz      short loc_1400850EA
0x1400850e1  xor     ecx, ecx
0x1400850e3  test    ebx, ebx
0x1400850e5  cmovnz  eax, ecx
0x1400850e8  jmp     short loc_1400850EC
0x1400850ea  xor     eax, eax
0x1400850ec  add     rsp, 20h
0x1400850f0  pop     rbx
0x1400850f1  retn
```

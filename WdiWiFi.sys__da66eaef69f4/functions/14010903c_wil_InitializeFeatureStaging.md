# wil_InitializeFeatureStaging

- ea: `0x14010903c`
- end: `0x1401090f3`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400c5dbc`

## callees

- `0x1400c6138`
- `0x1401077dc`
- `0x140107a7c`
- `0x14010903c`
- `0x1401090fc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140109064`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140109064`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1401090ba`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1401090ba`

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
0x14010903c  push    rbx
0x14010903e  sub     rsp, 20h
0x140109042  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140109049  mov     [rsp+28h+arg_0], 0
0x140109052  jnz     loc_1401090EA
0x140109058  xor     ebx, ebx
0x14010905a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140109064  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14010906b  nop     dword ptr [rax+rax+00h]
0x140109070  mov     [rsp+28h+arg_0], rax
0x140109075  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14010907a  call    wil_details_EvaluateFeatureDependencies
0x14010907f  lea     rcx, wil_details_featureDescriptors_a
0x140109086  call    wil_details_FeatureDescriptors_SkipPadding
0x14010908b  test    rax, rax
0x14010908e  jz      short loc_1401090D8
0x140109090  cmp     [rax+1Dh], bl
0x140109093  jnz     short loc_14010909F
0x140109095  cmp     [rax+1Eh], bl
0x140109098  jnz     short loc_14010909F
0x14010909a  cmp     [rax+1Ch], bl
0x14010909d  jz      short loc_1401090A5
0x14010909f  lea     rcx, [rax+38h]
0x1401090a3  jmp     short loc_140109086
0x1401090a5  lea     r9, g_wil_details_featureChangeNotification
0x1401090ac  xor     edx, edx
0x1401090ae  lea     r8, [rsp+28h+arg_0]
0x1401090b3  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1401090ba  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1401090c1  nop     dword ptr [rax+rax+00h]
0x1401090c6  test    eax, eax
0x1401090c8  jz      short loc_1401090D3
0x1401090ca  mov     cs:g_wil_details_featureChangeNotification, rbx
0x1401090d1  jmp     short loc_1401090D8
0x1401090d3  mov     ebx, 1
0x1401090d8  call    wil_details_RegisterFeatureUsageProvider
0x1401090dd  test    eax, eax
0x1401090df  jz      short loc_1401090EA
0x1401090e1  xor     ecx, ecx
0x1401090e3  test    ebx, ebx
0x1401090e5  cmovnz  eax, ecx
0x1401090e8  jmp     short loc_1401090EC
0x1401090ea  xor     eax, eax
0x1401090ec  add     rsp, 20h
0x1401090f0  pop     rbx
0x1401090f1  retn
```

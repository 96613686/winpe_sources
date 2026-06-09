# wil_InitializeFeatureStaging

- ea: `0x1400385fc`
- end: `0x1400386b3`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003825c`

## callees

- `0x140001760`
- `0x1400226e0`
- `0x14002298c`
- `0x1400385fc`
- `0x1400386bc`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003867a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003867a`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140038624`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140038624`

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
0x1400385fc  push    rbx
0x1400385fe  sub     rsp, 20h
0x140038602  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140038609  mov     [rsp+28h+arg_0], 0
0x140038612  jnz     loc_1400386AA
0x140038618  xor     ebx, ebx
0x14003861a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140038624  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14003862b  nop     dword ptr [rax+rax+00h]
0x140038630  mov     [rsp+28h+arg_0], rax
0x140038635  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14003863a  call    wil_details_EvaluateFeatureDependencies
0x14003863f  lea     rcx, wil_details_featureDescriptors_a
0x140038646  call    wil_details_FeatureDescriptors_SkipPadding
0x14003864b  test    rax, rax
0x14003864e  jz      short loc_140038698
0x140038650  cmp     [rax+1Dh], bl
0x140038653  jnz     short loc_14003865F
0x140038655  cmp     [rax+1Eh], bl
0x140038658  jnz     short loc_14003865F
0x14003865a  cmp     [rax+1Ch], bl
0x14003865d  jz      short loc_140038665
0x14003865f  lea     rcx, [rax+38h]
0x140038663  jmp     short loc_140038646
0x140038665  lea     r9, g_wil_details_featureChangeNotification
0x14003866c  xor     edx, edx
0x14003866e  lea     r8, [rsp+28h+arg_0]
0x140038673  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14003867a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140038681  nop     dword ptr [rax+rax+00h]
0x140038686  test    eax, eax
0x140038688  jz      short loc_140038693
0x14003868a  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140038691  jmp     short loc_140038698
0x140038693  mov     ebx, 1
0x140038698  call    wil_details_RegisterFeatureUsageProvider
0x14003869d  test    eax, eax
0x14003869f  jz      short loc_1400386AA
0x1400386a1  xor     ecx, ecx
0x1400386a3  test    ebx, ebx
0x1400386a5  cmovnz  eax, ecx
0x1400386a8  jmp     short loc_1400386AC
0x1400386aa  xor     eax, eax
0x1400386ac  add     rsp, 20h
0x1400386b0  pop     rbx
0x1400386b1  retn
```

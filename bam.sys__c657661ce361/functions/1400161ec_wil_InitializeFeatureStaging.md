# wil_InitializeFeatureStaging

- ea: `0x1400161ec`
- end: `0x1400162a3`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140016078`

## callees

- `0x1400018fc`
- `0x14000b594`
- `0x14000b83c`
- `0x1400161ec`
- `0x1400162ac`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140016214`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140016214`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001626a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001626a`

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
0x1400161ec  push    rbx
0x1400161ee  sub     rsp, 20h
0x1400161f2  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400161f9  mov     [rsp+28h+arg_0], 0
0x140016202  jnz     loc_14001629A
0x140016208  xor     ebx, ebx
0x14001620a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140016214  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14001621b  nop     dword ptr [rax+rax+00h]
0x140016220  mov     [rsp+28h+arg_0], rax
0x140016225  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14001622a  call    wil_details_EvaluateFeatureDependencies
0x14001622f  lea     rcx, wil_details_featureDescriptors_a
0x140016236  call    wil_details_FeatureDescriptors_SkipPadding
0x14001623b  test    rax, rax
0x14001623e  jz      short loc_140016288
0x140016240  cmp     [rax+1Dh], bl
0x140016243  jnz     short loc_14001624F
0x140016245  cmp     [rax+1Eh], bl
0x140016248  jnz     short loc_14001624F
0x14001624a  cmp     [rax+1Ch], bl
0x14001624d  jz      short loc_140016255
0x14001624f  lea     rcx, [rax+38h]
0x140016253  jmp     short loc_140016236
0x140016255  lea     r9, g_wil_details_featureChangeNotification
0x14001625c  xor     edx, edx
0x14001625e  lea     r8, [rsp+28h+arg_0]
0x140016263  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14001626a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140016271  nop     dword ptr [rax+rax+00h]
0x140016276  test    eax, eax
0x140016278  jz      short loc_140016283
0x14001627a  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140016281  jmp     short loc_140016288
0x140016283  mov     ebx, 1
0x140016288  call    wil_details_RegisterFeatureUsageProvider
0x14001628d  test    eax, eax
0x14001628f  jz      short loc_14001629A
0x140016291  xor     ecx, ecx
0x140016293  test    ebx, ebx
0x140016295  cmovnz  eax, ecx
0x140016298  jmp     short loc_14001629C
0x14001629a  xor     eax, eax
0x14001629c  add     rsp, 20h
0x1400162a0  pop     rbx
0x1400162a1  retn
```

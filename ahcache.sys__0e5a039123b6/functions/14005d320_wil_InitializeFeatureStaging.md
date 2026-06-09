# wil_InitializeFeatureStaging

- ea: `0x14005d320`
- end: `0x14005d3d7`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005d078`

## callees

- `0x1400050d8`
- `0x14002cb94`
- `0x14002ce2c`
- `0x14005d320`
- `0x14005d3e0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005d348`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14005d348`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005d39e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14005d39e`

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
0x14005d320  push    rbx
0x14005d322  sub     rsp, 20h
0x14005d326  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14005d32d  mov     [rsp+28h+arg_0], 0
0x14005d336  jnz     loc_14005D3CE
0x14005d33c  xor     ebx, ebx
0x14005d33e  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14005d348  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14005d34f  nop     dword ptr [rax+rax+00h]
0x14005d354  mov     [rsp+28h+arg_0], rax
0x14005d359  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14005d35e  call    wil_details_EvaluateFeatureDependencies
0x14005d363  lea     rcx, wil_details_featureDescriptors_a
0x14005d36a  call    wil_details_FeatureDescriptors_SkipPadding
0x14005d36f  test    rax, rax
0x14005d372  jz      short loc_14005D3BC
0x14005d374  cmp     [rax+1Dh], bl
0x14005d377  jnz     short loc_14005D383
0x14005d379  cmp     [rax+1Eh], bl
0x14005d37c  jnz     short loc_14005D383
0x14005d37e  cmp     [rax+1Ch], bl
0x14005d381  jz      short loc_14005D389
0x14005d383  lea     rcx, [rax+38h]
0x14005d387  jmp     short loc_14005D36A
0x14005d389  lea     r9, g_wil_details_featureChangeNotification
0x14005d390  xor     edx, edx
0x14005d392  lea     r8, [rsp+28h+arg_0]
0x14005d397  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14005d39e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14005d3a5  nop     dword ptr [rax+rax+00h]
0x14005d3aa  test    eax, eax
0x14005d3ac  jz      short loc_14005D3B7
0x14005d3ae  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14005d3b5  jmp     short loc_14005D3BC
0x14005d3b7  mov     ebx, 1
0x14005d3bc  call    wil_details_RegisterFeatureUsageProvider
0x14005d3c1  test    eax, eax
0x14005d3c3  jz      short loc_14005D3CE
0x14005d3c5  xor     ecx, ecx
0x14005d3c7  test    ebx, ebx
0x14005d3c9  cmovnz  eax, ecx
0x14005d3cc  jmp     short loc_14005D3D0
0x14005d3ce  xor     eax, eax
0x14005d3d0  add     rsp, 20h
0x14005d3d4  pop     rbx
0x14005d3d5  retn
```

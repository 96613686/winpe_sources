# wil_InitializeFeatureStaging

- ea: `0x1400302ac`
- end: `0x140030365`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003003c`

## callees

- `0x140004dd8`
- `0x14002a174`
- `0x14002a40c`
- `0x1400302ac`
- `0x14003036c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400302d4`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400302d4`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003032c`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003032c`

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
  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v2 + 56) )
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
0x1400302ac  push    rbx
0x1400302ae  sub     rsp, 20h
0x1400302b2  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400302b9  mov     [rsp+28h+arg_0], 0
0x1400302c2  jnz     loc_14003035C
0x1400302c8  xor     ebx, ebx
0x1400302ca  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400302d4  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400302db  nop     dword ptr [rax+rax+00h]
0x1400302e0  mov     [rsp+28h+arg_0], rax
0x1400302e5  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400302ea  call    wil_details_EvaluateFeatureDependencies
0x1400302ef  lea     rcx, wil_details_featureDescriptors_a
0x1400302f6  jmp     short loc_14003030B
0x1400302f8  cmp     [rax+1Dh], bl
0x1400302fb  jnz     short loc_140030307
0x1400302fd  cmp     [rax+1Eh], bl
0x140030300  jnz     short loc_140030307
0x140030302  cmp     [rax+1Ch], bl
0x140030305  jz      short loc_140030317
0x140030307  lea     rcx, [rax+38h]
0x14003030b  call    wil_details_FeatureDescriptors_SkipPadding
0x140030310  test    rax, rax
0x140030313  jnz     short loc_1400302F8
0x140030315  jmp     short loc_14003034A
0x140030317  lea     r9, g_wil_details_featureChangeNotification
0x14003031e  xor     edx, edx
0x140030320  lea     r8, [rsp+28h+arg_0]
0x140030325  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14003032c  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140030333  nop     dword ptr [rax+rax+00h]
0x140030338  test    eax, eax
0x14003033a  jz      short loc_140030345
0x14003033c  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140030343  jmp     short loc_14003034A
0x140030345  mov     ebx, 1
0x14003034a  call    wil_details_RegisterFeatureUsageProvider
0x14003034f  test    eax, eax
0x140030351  jz      short loc_14003035C
0x140030353  xor     ecx, ecx
0x140030355  test    ebx, ebx
0x140030357  cmovnz  eax, ecx
0x14003035a  jmp     short loc_14003035E
0x14003035c  xor     eax, eax
0x14003035e  add     rsp, 20h
0x140030362  pop     rbx
0x140030363  retn
```

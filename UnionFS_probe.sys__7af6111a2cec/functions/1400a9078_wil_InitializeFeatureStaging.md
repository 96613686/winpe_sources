# wil_InitializeFeatureStaging

- ea: `0x1400a9078`
- end: `0x1400a91d9`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140079f58`

## callees

- `0x1400a71dc`
- `0x1400a9078`
- `0x1400a91e0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400a91a2`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400a91a2`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400a912e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400a912e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400a90a9`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400a90a9`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // edi
  int **v1; // rbx
  int **v2; // rax
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = 0;
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  v0 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  v6 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v1 = wil_details_featureDescriptors_a;
  v2 = wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (int **)wil_details_featureDescriptors_z )
  {
    while ( !*v2 )
    {
      if ( ++v2 >= (int **)wil_details_featureDescriptors_z )
        goto LABEL_19;
    }
LABEL_14:
    if ( v2 )
    {
      if ( *((_BYTE *)v2 + 29) || *((_BYTE *)v2 + 30) || *((_BYTE *)v2 + 28) )
      {
        for ( v2 += 7; v2 < (int **)wil_details_featureDescriptors_z; ++v2 )
        {
          if ( *v2 )
            goto LABEL_14;
        }
      }
      else if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                                wil_details_ReevaluateOnFeatureConfigurationChange,
                                0,
                                &v6,
                                &g_wil_details_featureChangeNotification) )
      {
        g_wil_details_featureChangeNotification = 0;
      }
      else
      {
        v0 = 1;
      }
    }
  }
LABEL_19:
  v5 = 0;
  v4 = 0;
  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  while ( v1 < (int **)wil_details_featureDescriptors_z )
  {
    if ( *v1 )
      goto LABEL_24;
    ++v1;
  }
  v1 = 0;
LABEL_24:
  *(_QWORD *)&v4 = v1;
  *((_QWORD *)&v4 + 1) = wil_details_featureDescriptors_z;
  v5 = 0;
  result = RtlRegisterFeatureUsageProvider(
             wil_details_OnFeatureUsageProviderFlushNotification,
             &v4,
             &g_wil_details_featureUsageProvider);
  if ( !(_DWORD)result )
    return 0;
  g_wil_details_featureUsageProvider = 0;
  if ( v0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1400a9078  mov     [rsp+arg_8], rbx
0x1400a907d  mov     [rsp+arg_10], rbp
0x1400a9082  push    rdi
0x1400a9083  sub     rsp, 40h
0x1400a9087  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400a908e  mov     [rsp+48h+arg_0], 0
0x1400a9097  jnz     loc_1400A91C6
0x1400a909d  xor     edi, edi
0x1400a909f  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400a90a9  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400a90b0  nop     dword ptr [rax+rax+00h]
0x1400a90b5  mov     [rsp+48h+arg_0], rax
0x1400a90ba  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400a90bf  call    wil_details_EvaluateFeatureDependencies
0x1400a90c4  lea     rbx, wil_details_featureDescriptors_a
0x1400a90cb  lea     rbp, wil_details_featureDescriptors_z
0x1400a90d2  mov     rax, rbx
0x1400a90d5  cmp     rbx, rbp
0x1400a90d8  jnb     short loc_1400A914C
0x1400a90da  cmp     [rax], rdi
0x1400a90dd  jnz     short loc_1400A9112
0x1400a90df  add     rax, 8
0x1400a90e3  cmp     rax, rbp
0x1400a90e6  jb      short loc_1400A90DA
0x1400a90e8  jmp     short loc_1400A914C
0x1400a90ea  cmp     [rax+1Dh], dil
0x1400a90ee  jnz     short loc_1400A90FC
0x1400a90f0  cmp     [rax+1Eh], dil
0x1400a90f4  jnz     short loc_1400A90FC
0x1400a90f6  cmp     [rax+1Ch], dil
0x1400a90fa  jz      short loc_1400A9119
0x1400a90fc  add     rax, 38h ; '8'
0x1400a9100  jmp     short loc_1400A910B
0x1400a9102  cmp     [rax], rdi
0x1400a9105  jnz     short loc_1400A9112
0x1400a9107  add     rax, 8
0x1400a910b  cmp     rax, rbp
0x1400a910e  jb      short loc_1400A9102
0x1400a9110  jmp     short loc_1400A914C
0x1400a9112  test    rax, rax
0x1400a9115  jnz     short loc_1400A90EA
0x1400a9117  jmp     short loc_1400A914C
0x1400a9119  lea     r9, g_wil_details_featureChangeNotification
0x1400a9120  xor     edx, edx
0x1400a9122  lea     r8, [rsp+48h+arg_0]
0x1400a9127  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400a912e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400a9135  nop     dword ptr [rax+rax+00h]
0x1400a913a  test    eax, eax
0x1400a913c  jz      short loc_1400A9147
0x1400a913e  mov     cs:g_wil_details_featureChangeNotification, rdi
0x1400a9145  jmp     short loc_1400A914C
0x1400a9147  mov     edi, 1
0x1400a914c  xor     eax, eax
0x1400a914e  xorps   xmm0, xmm0
0x1400a9151  mov     [rsp+48h+var_18], rax
0x1400a9156  lea     rax, wil_details_RecordFeatureUsageReporting
0x1400a915d  movups  [rsp+48h+var_28], xmm0
0x1400a9162  mov     cs:g_wil_details_recordFeatureUsage, rax
0x1400a9169  jmp     short loc_1400A9175
0x1400a916b  cmp     qword ptr [rbx], 0
0x1400a916f  jnz     short loc_1400A917C
0x1400a9171  add     rbx, 8
0x1400a9175  cmp     rbx, rbp
0x1400a9178  jb      short loc_1400A916B
0x1400a917a  xor     ebx, ebx
0x1400a917c  lea     r8, g_wil_details_featureUsageProvider
0x1400a9183  mov     qword ptr [rsp+48h+var_28], rbx
0x1400a9188  lea     rdx, [rsp+48h+var_28]
0x1400a918d  mov     qword ptr [rsp+48h+var_28+8], rbp
0x1400a9192  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x1400a9199  mov     [rsp+48h+var_18], 0
0x1400a91a2  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x1400a91a9  nop     dword ptr [rax+rax+00h]
0x1400a91ae  test    eax, eax
0x1400a91b0  jz      short loc_1400A91C6
0x1400a91b2  xor     ecx, ecx
0x1400a91b4  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400a91bf  test    edi, edi
0x1400a91c1  cmovnz  eax, ecx
0x1400a91c4  jmp     short loc_1400A91C8
0x1400a91c6  xor     eax, eax
0x1400a91c8  mov     rbx, [rsp+48h+arg_8]
0x1400a91cd  mov     rbp, [rsp+48h+arg_10]
0x1400a91d2  add     rsp, 40h
0x1400a91d6  pop     rdi
0x1400a91d7  retn
```

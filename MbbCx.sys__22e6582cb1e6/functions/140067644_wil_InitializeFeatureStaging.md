# wil_InitializeFeatureStaging

- ea: `0x140067644`
- end: `0x1400677a5`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14006703c`

## callees

- `0x140065564`
- `0x140067644`
- `0x1400677ac`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14006776e`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14006776e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400676fa`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400676fa`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140067675`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140067675`

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
0x140067644  mov     [rsp+arg_8], rbx
0x140067649  mov     [rsp+arg_10], rbp
0x14006764e  push    rdi
0x14006764f  sub     rsp, 40h
0x140067653  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14006765a  mov     [rsp+48h+arg_0], 0
0x140067663  jnz     loc_140067792
0x140067669  xor     edi, edi
0x14006766b  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140067675  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14006767c  nop     dword ptr [rax+rax+00h]
0x140067681  mov     [rsp+48h+arg_0], rax
0x140067686  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14006768b  call    wil_details_EvaluateFeatureDependencies
0x140067690  lea     rbx, wil_details_featureDescriptors_a
0x140067697  lea     rbp, wil_details_featureDescriptors_z
0x14006769e  mov     rax, rbx
0x1400676a1  cmp     rbx, rbp
0x1400676a4  jnb     short loc_140067718
0x1400676a6  cmp     [rax], rdi
0x1400676a9  jnz     short loc_1400676DE
0x1400676ab  add     rax, 8
0x1400676af  cmp     rax, rbp
0x1400676b2  jb      short loc_1400676A6
0x1400676b4  jmp     short loc_140067718
0x1400676b6  cmp     [rax+1Dh], dil
0x1400676ba  jnz     short loc_1400676C8
0x1400676bc  cmp     [rax+1Eh], dil
0x1400676c0  jnz     short loc_1400676C8
0x1400676c2  cmp     [rax+1Ch], dil
0x1400676c6  jz      short loc_1400676E5
0x1400676c8  add     rax, 38h ; '8'
0x1400676cc  jmp     short loc_1400676D7
0x1400676ce  cmp     [rax], rdi
0x1400676d1  jnz     short loc_1400676DE
0x1400676d3  add     rax, 8
0x1400676d7  cmp     rax, rbp
0x1400676da  jb      short loc_1400676CE
0x1400676dc  jmp     short loc_140067718
0x1400676de  test    rax, rax
0x1400676e1  jnz     short loc_1400676B6
0x1400676e3  jmp     short loc_140067718
0x1400676e5  lea     r9, g_wil_details_featureChangeNotification
0x1400676ec  xor     edx, edx
0x1400676ee  lea     r8, [rsp+48h+arg_0]
0x1400676f3  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400676fa  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140067701  nop     dword ptr [rax+rax+00h]
0x140067706  test    eax, eax
0x140067708  jz      short loc_140067713
0x14006770a  mov     cs:g_wil_details_featureChangeNotification, rdi
0x140067711  jmp     short loc_140067718
0x140067713  mov     edi, 1
0x140067718  xor     eax, eax
0x14006771a  xorps   xmm0, xmm0
0x14006771d  mov     [rsp+48h+var_18], rax
0x140067722  lea     rax, wil_details_RecordFeatureUsageReporting
0x140067729  movups  [rsp+48h+var_28], xmm0
0x14006772e  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140067735  jmp     short loc_140067741
0x140067737  cmp     qword ptr [rbx], 0
0x14006773b  jnz     short loc_140067748
0x14006773d  add     rbx, 8
0x140067741  cmp     rbx, rbp
0x140067744  jb      short loc_140067737
0x140067746  xor     ebx, ebx
0x140067748  lea     r8, g_wil_details_featureUsageProvider
0x14006774f  mov     qword ptr [rsp+48h+var_28], rbx
0x140067754  lea     rdx, [rsp+48h+var_28]
0x140067759  mov     qword ptr [rsp+48h+var_28+8], rbp
0x14006775e  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140067765  mov     [rsp+48h+var_18], 0
0x14006776e  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140067775  nop     dword ptr [rax+rax+00h]
0x14006777a  test    eax, eax
0x14006777c  jz      short loc_140067792
0x14006777e  xor     ecx, ecx
0x140067780  mov     cs:g_wil_details_featureUsageProvider, 0
0x14006778b  test    edi, edi
0x14006778d  cmovnz  eax, ecx
0x140067790  jmp     short loc_140067794
0x140067792  xor     eax, eax
0x140067794  mov     rbx, [rsp+48h+arg_8]
0x140067799  mov     rbp, [rsp+48h+arg_10]
0x14006779e  add     rsp, 40h
0x1400677a2  pop     rdi
0x1400677a3  retn
```

# wil_InitializeFeatureStaging

- ea: `0x140017078`
- end: `0x1400171d9`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003170`

## callees

- `0x140015564`
- `0x140017078`
- `0x1400171e0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400171a2`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400171a2`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001712e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001712e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400170a9`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400170a9`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  __int64 *v0; // rbx
  __int64 result; // rax
  __int128 v2; // [rsp+20h] [rbp-28h] BYREF
  __int64 v3; // [rsp+30h] [rbp-18h]

  if ( LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) )
    return 0;
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 1;
  RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v0 = wil_details_featureDescriptors_a;
  v3 = 0;
  v2 = 0;
  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  while ( v0 < wil_details_featureDescriptors_a )
  {
    if ( *v0 )
      goto LABEL_7;
    ++v0;
  }
  v0 = 0;
LABEL_7:
  *(_QWORD *)&v2 = v0;
  *((_QWORD *)&v2 + 1) = wil_details_featureDescriptors_a;
  v3 = 0;
  result = RtlRegisterFeatureUsageProvider(
             wil_details_OnFeatureUsageProviderFlushNotification,
             &v2,
             &g_wil_details_featureUsageProvider);
  if ( !(_DWORD)result )
    return 0;
  g_wil_details_featureUsageProvider = 0;
  return result;
}

```

## disassembly

```asm
0x140017078  mov     [rsp+arg_8], rbx
0x14001707d  mov     [rsp+arg_10], rbp
0x140017082  push    rdi
0x140017083  sub     rsp, 40h
0x140017087  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14001708e  mov     [rsp+48h+arg_0], 0
0x140017097  jnz     loc_1400171C6
0x14001709d  xor     edi, edi
0x14001709f  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x1400170a9  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400170b0  nop     dword ptr [rax+rax+00h]
0x1400170b5  mov     [rsp+48h+arg_0], rax
0x1400170ba  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400170bf  call    wil_details_EvaluateFeatureDependencies
0x1400170c4  lea     rbx, wil_details_featureDescriptors_a
0x1400170cb  lea     rbp, wil_details_featureDescriptors_a
0x1400170d2  mov     rax, rbx
0x1400170d5  cmp     rbx, rbp
0x1400170d8  jnb     short loc_14001714C
0x1400170da  cmp     [rax], rdi
0x1400170dd  jnz     short loc_140017112
0x1400170df  add     rax, 8
0x1400170e3  cmp     rax, rbp
0x1400170e6  jb      short loc_1400170DA
0x1400170e8  jmp     short loc_14001714C
0x1400170ea  cmp     [rax+1Dh], dil
0x1400170ee  jnz     short loc_1400170FC
0x1400170f0  cmp     [rax+1Eh], dil
0x1400170f4  jnz     short loc_1400170FC
0x1400170f6  cmp     [rax+1Ch], dil
0x1400170fa  jz      short loc_140017119
0x1400170fc  add     rax, 38h ; '8'
0x140017100  jmp     short loc_14001710B
0x140017102  cmp     [rax], rdi
0x140017105  jnz     short loc_140017112
0x140017107  add     rax, 8
0x14001710b  cmp     rax, rbp
0x14001710e  jb      short loc_140017102
0x140017110  jmp     short loc_14001714C
0x140017112  test    rax, rax
0x140017115  jnz     short loc_1400170EA
0x140017117  jmp     short loc_14001714C
0x140017119  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140017120  xor     edx, edx
0x140017122  lea     r8, [rsp+48h+arg_0]
0x140017127  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14001712e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140017135  nop     dword ptr [rax+rax+00h]
0x14001713a  test    eax, eax
0x14001713c  jz      short loc_140017147
0x14001713e  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rdi
0x140017145  jmp     short loc_14001714C
0x140017147  mov     edi, 1
0x14001714c  xor     eax, eax
0x14001714e  xorps   xmm0, xmm0
0x140017151  mov     [rsp+48h+var_18], rax
0x140017156  lea     rax, wil_details_RecordFeatureUsageReporting
0x14001715d  movups  [rsp+48h+var_28], xmm0
0x140017162  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140017169  jmp     short loc_140017175
0x14001716b  cmp     qword ptr [rbx], 0
0x14001716f  jnz     short loc_14001717C
0x140017171  add     rbx, 8
0x140017175  cmp     rbx, rbp
0x140017178  jb      short loc_14001716B
0x14001717a  xor     ebx, ebx
0x14001717c  lea     r8, g_wil_details_featureUsageProvider
0x140017183  mov     qword ptr [rsp+48h+var_28], rbx
0x140017188  lea     rdx, [rsp+48h+var_28]
0x14001718d  mov     qword ptr [rsp+48h+var_28+8], rbp
0x140017192  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140017199  mov     [rsp+48h+var_18], 0
0x1400171a2  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x1400171a9  nop     dword ptr [rax+rax+00h]
0x1400171ae  test    eax, eax
0x1400171b0  jz      short loc_1400171C6
0x1400171b2  xor     ecx, ecx
0x1400171b4  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400171bf  test    edi, edi
0x1400171c1  cmovnz  eax, ecx
0x1400171c4  jmp     short loc_1400171C8
0x1400171c6  xor     eax, eax
0x1400171c8  mov     rbx, [rsp+48h+arg_8]
0x1400171cd  mov     rbp, [rsp+48h+arg_10]
0x1400171d2  add     rsp, 40h
0x1400171d6  pop     rdi
0x1400171d7  retn
```

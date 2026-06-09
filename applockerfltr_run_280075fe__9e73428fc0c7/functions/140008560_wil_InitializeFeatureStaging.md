# wil_InitializeFeatureStaging

- ea: `0x140008560`
- end: `0x1400086c1`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008078`

## callees

- `0x140007970`
- `0x140008560`
- `0x1400086c8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140008591`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140008591`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140008616`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140008616`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000868a`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000868a`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  __int64 *v0; // rbx
  __int64 result; // rax
  __int128 v2; // [rsp+20h] [rbp-28h] BYREF
  __int64 v3; // [rsp+30h] [rbp-18h]

  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  g_wil_details_isFeatureStagingInitialized = 1;
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
0x140008560  mov     [rsp+arg_8], rbx
0x140008565  mov     [rsp+arg_10], rbp
0x14000856a  push    rdi
0x14000856b  sub     rsp, 40h
0x14000856f  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140008576  mov     [rsp+48h+arg_0], 0
0x14000857f  jnz     loc_1400086AE
0x140008585  xor     edi, edi
0x140008587  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140008591  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140008598  nop     dword ptr [rax+rax+00h]
0x14000859d  mov     [rsp+48h+arg_0], rax
0x1400085a2  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400085a7  call    wil_details_EvaluateFeatureDependencies
0x1400085ac  lea     rbx, wil_details_featureDescriptors_a
0x1400085b3  lea     rbp, wil_details_featureDescriptors_a
0x1400085ba  mov     rax, rbx
0x1400085bd  cmp     rbx, rbp
0x1400085c0  jnb     short loc_140008634
0x1400085c2  cmp     [rax], rdi
0x1400085c5  jnz     short loc_1400085FA
0x1400085c7  add     rax, 8
0x1400085cb  cmp     rax, rbp
0x1400085ce  jb      short loc_1400085C2
0x1400085d0  jmp     short loc_140008634
0x1400085d2  cmp     [rax+1Dh], dil
0x1400085d6  jnz     short loc_1400085E4
0x1400085d8  cmp     [rax+1Eh], dil
0x1400085dc  jnz     short loc_1400085E4
0x1400085de  cmp     [rax+1Ch], dil
0x1400085e2  jz      short loc_140008601
0x1400085e4  add     rax, 38h ; '8'
0x1400085e8  jmp     short loc_1400085F3
0x1400085ea  cmp     [rax], rdi
0x1400085ed  jnz     short loc_1400085FA
0x1400085ef  add     rax, 8
0x1400085f3  cmp     rax, rbp
0x1400085f6  jb      short loc_1400085EA
0x1400085f8  jmp     short loc_140008634
0x1400085fa  test    rax, rax
0x1400085fd  jnz     short loc_1400085D2
0x1400085ff  jmp     short loc_140008634
0x140008601  lea     r9, g_wil_details_featureChangeNotification
0x140008608  xor     edx, edx
0x14000860a  lea     r8, [rsp+48h+arg_0]
0x14000860f  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140008616  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14000861d  nop     dword ptr [rax+rax+00h]
0x140008622  test    eax, eax
0x140008624  jz      short loc_14000862F
0x140008626  mov     cs:g_wil_details_featureChangeNotification, rdi
0x14000862d  jmp     short loc_140008634
0x14000862f  mov     edi, 1
0x140008634  xor     eax, eax
0x140008636  xorps   xmm0, xmm0
0x140008639  mov     [rsp+48h+var_18], rax
0x14000863e  lea     rax, wil_details_RecordFeatureUsageReporting
0x140008645  movups  [rsp+48h+var_28], xmm0
0x14000864a  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140008651  jmp     short loc_14000865D
0x140008653  cmp     qword ptr [rbx], 0
0x140008657  jnz     short loc_140008664
0x140008659  add     rbx, 8
0x14000865d  cmp     rbx, rbp
0x140008660  jb      short loc_140008653
0x140008662  xor     ebx, ebx
0x140008664  lea     r8, g_wil_details_featureUsageProvider
0x14000866b  mov     qword ptr [rsp+48h+var_28], rbx
0x140008670  lea     rdx, [rsp+48h+var_28]
0x140008675  mov     qword ptr [rsp+48h+var_28+8], rbp
0x14000867a  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140008681  mov     [rsp+48h+var_18], 0
0x14000868a  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140008691  nop     dword ptr [rax+rax+00h]
0x140008696  test    eax, eax
0x140008698  jz      short loc_1400086AE
0x14000869a  xor     ecx, ecx
0x14000869c  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400086a7  test    edi, edi
0x1400086a9  cmovnz  eax, ecx
0x1400086ac  jmp     short loc_1400086B0
0x1400086ae  xor     eax, eax
0x1400086b0  mov     rbx, [rsp+48h+arg_8]
0x1400086b5  mov     rbp, [rsp+48h+arg_10]
0x1400086ba  add     rsp, 40h
0x1400086be  pop     rdi
0x1400086bf  retn
```

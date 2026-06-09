# wil_InitializeFeatureStaging

- ea: `0x18001f078`
- end: `0x18001f1d9`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011b90`

## callees

- `0x18001d090`
- `0x18001f078`
- `0x18001f1e0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18001f12e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18001f12e`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x18001f1a2`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x18001f1a2`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18001f0a9`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18001f0a9`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  _QWORD *v0; // rbx
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
0x18001f078  mov     [rsp+arg_8], rbx
0x18001f07d  mov     [rsp+arg_10], rbp
0x18001f082  push    rdi
0x18001f083  sub     rsp, 40h
0x18001f087  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x18001f08e  mov     [rsp+48h+arg_0], 0
0x18001f097  jnz     loc_18001F1C6
0x18001f09d  xor     edi, edi
0x18001f09f  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x18001f0a9  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x18001f0b0  nop     dword ptr [rax+rax+00h]
0x18001f0b5  mov     [rsp+48h+arg_0], rax
0x18001f0ba  call    wil_details_PopulateInitialConfiguredFeatureStates
0x18001f0bf  call    wil_details_EvaluateFeatureDependencies
0x18001f0c4  lea     rbx, wil_details_featureDescriptors_a
0x18001f0cb  lea     rbp, wil_details_featureDescriptors_a
0x18001f0d2  mov     rax, rbx
0x18001f0d5  cmp     rbx, rbp
0x18001f0d8  jnb     short loc_18001F14C
0x18001f0da  cmp     [rax], rdi
0x18001f0dd  jnz     short loc_18001F112
0x18001f0df  add     rax, 8
0x18001f0e3  cmp     rax, rbp
0x18001f0e6  jb      short loc_18001F0DA
0x18001f0e8  jmp     short loc_18001F14C
0x18001f0ea  cmp     [rax+1Dh], dil
0x18001f0ee  jnz     short loc_18001F0FC
0x18001f0f0  cmp     [rax+1Eh], dil
0x18001f0f4  jnz     short loc_18001F0FC
0x18001f0f6  cmp     [rax+1Ch], dil
0x18001f0fa  jz      short loc_18001F119
0x18001f0fc  add     rax, 38h ; '8'
0x18001f100  jmp     short loc_18001F10B
0x18001f102  cmp     [rax], rdi
0x18001f105  jnz     short loc_18001F112
0x18001f107  add     rax, 8
0x18001f10b  cmp     rax, rbp
0x18001f10e  jb      short loc_18001F102
0x18001f110  jmp     short loc_18001F14C
0x18001f112  test    rax, rax
0x18001f115  jnz     short loc_18001F0EA
0x18001f117  jmp     short loc_18001F14C
0x18001f119  lea     r9, g_wil_details_featureChangeNotification
0x18001f120  xor     edx, edx
0x18001f122  lea     r8, [rsp+48h+arg_0]
0x18001f127  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x18001f12e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x18001f135  nop     dword ptr [rax+rax+00h]
0x18001f13a  test    eax, eax
0x18001f13c  jz      short loc_18001F147
0x18001f13e  mov     cs:g_wil_details_featureChangeNotification, rdi
0x18001f145  jmp     short loc_18001F14C
0x18001f147  mov     edi, 1
0x18001f14c  xor     eax, eax
0x18001f14e  xorps   xmm0, xmm0
0x18001f151  mov     [rsp+48h+var_18], rax
0x18001f156  lea     rax, wil_details_RecordFeatureUsageReporting
0x18001f15d  movups  [rsp+48h+var_28], xmm0
0x18001f162  mov     cs:g_wil_details_recordFeatureUsage, rax
0x18001f169  jmp     short loc_18001F175
0x18001f16b  cmp     qword ptr [rbx], 0
0x18001f16f  jnz     short loc_18001F17C
0x18001f171  add     rbx, 8
0x18001f175  cmp     rbx, rbp
0x18001f178  jb      short loc_18001F16B
0x18001f17a  xor     ebx, ebx
0x18001f17c  lea     r8, g_wil_details_featureUsageProvider
0x18001f183  mov     qword ptr [rsp+48h+var_28], rbx
0x18001f188  lea     rdx, [rsp+48h+var_28]
0x18001f18d  mov     qword ptr [rsp+48h+var_28+8], rbp
0x18001f192  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x18001f199  mov     [rsp+48h+var_18], 0
0x18001f1a2  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x18001f1a9  nop     dword ptr [rax+rax+00h]
0x18001f1ae  test    eax, eax
0x18001f1b0  jz      short loc_18001F1C6
0x18001f1b2  xor     ecx, ecx
0x18001f1b4  mov     cs:g_wil_details_featureUsageProvider, 0
0x18001f1bf  test    edi, edi
0x18001f1c1  cmovnz  eax, ecx
0x18001f1c4  jmp     short loc_18001F1C8
0x18001f1c6  xor     eax, eax
0x18001f1c8  mov     rbx, [rsp+48h+arg_8]
0x18001f1cd  mov     rbp, [rsp+48h+arg_10]
0x18001f1d2  add     rsp, 40h
0x18001f1d6  pop     rdi
0x18001f1d7  retn
```

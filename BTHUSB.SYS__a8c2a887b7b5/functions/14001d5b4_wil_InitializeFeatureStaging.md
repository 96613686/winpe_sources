# wil_InitializeFeatureStaging

- ea: `0x14001d5b4`
- end: `0x14001d715`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001d03c`

## callees

- `0x140018250`
- `0x14001d5b4`
- `0x14001d71c`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14001d6de`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14001d6de`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001d66a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001d66a`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14001d5e5`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14001d5e5`

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
  *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = wil_details_RecordFeatureUsageReporting;
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
             &WPP_MAIN_CB.DeviceQueue);
  if ( !(_DWORD)result )
    return 0;
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 0;
  return result;
}

```

## disassembly

```asm
0x14001d5b4  mov     [rsp+arg_8], rbx
0x14001d5b9  mov     [rsp+arg_10], rbp
0x14001d5be  push    rdi
0x14001d5bf  sub     rsp, 40h
0x14001d5c3  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14001d5ca  mov     [rsp+48h+arg_0], 0
0x14001d5d3  jnz     loc_14001D702
0x14001d5d9  xor     edi, edi
0x14001d5db  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14001d5e5  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14001d5ec  nop     dword ptr [rax+rax+00h]
0x14001d5f1  mov     [rsp+48h+arg_0], rax
0x14001d5f6  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14001d5fb  call    wil_details_EvaluateFeatureDependencies
0x14001d600  lea     rbx, wil_details_featureDescriptors_a
0x14001d607  lea     rbp, wil_details_featureDescriptors_a
0x14001d60e  mov     rax, rbx
0x14001d611  cmp     rbx, rbp
0x14001d614  jnb     short loc_14001D688
0x14001d616  cmp     [rax], rdi
0x14001d619  jnz     short loc_14001D64E
0x14001d61b  add     rax, 8
0x14001d61f  cmp     rax, rbp
0x14001d622  jb      short loc_14001D616
0x14001d624  jmp     short loc_14001D688
0x14001d626  cmp     [rax+1Dh], dil
0x14001d62a  jnz     short loc_14001D638
0x14001d62c  cmp     [rax+1Eh], dil
0x14001d630  jnz     short loc_14001D638
0x14001d632  cmp     [rax+1Ch], dil
0x14001d636  jz      short loc_14001D655
0x14001d638  add     rax, 38h ; '8'
0x14001d63c  jmp     short loc_14001D647
0x14001d63e  cmp     [rax], rdi
0x14001d641  jnz     short loc_14001D64E
0x14001d643  add     rax, 8
0x14001d647  cmp     rax, rbp
0x14001d64a  jb      short loc_14001D63E
0x14001d64c  jmp     short loc_14001D688
0x14001d64e  test    rax, rax
0x14001d651  jnz     short loc_14001D626
0x14001d653  jmp     short loc_14001D688
0x14001d655  lea     r9, g_wil_details_featureChangeNotification
0x14001d65c  xor     edx, edx
0x14001d65e  lea     r8, [rsp+48h+arg_0]
0x14001d663  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14001d66a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14001d671  nop     dword ptr [rax+rax+00h]
0x14001d676  test    eax, eax
0x14001d678  jz      short loc_14001D683
0x14001d67a  mov     cs:g_wil_details_featureChangeNotification, rdi
0x14001d681  jmp     short loc_14001D688
0x14001d683  mov     edi, 1
0x14001d688  xor     eax, eax
0x14001d68a  xorps   xmm0, xmm0
0x14001d68d  mov     [rsp+48h+var_18], rax
0x14001d692  lea     rax, wil_details_RecordFeatureUsageReporting
0x14001d699  movups  [rsp+48h+var_28], xmm0
0x14001d69e  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rax
0x14001d6a5  jmp     short loc_14001D6B1
0x14001d6a7  cmp     qword ptr [rbx], 0
0x14001d6ab  jnz     short loc_14001D6B8
0x14001d6ad  add     rbx, 8
0x14001d6b1  cmp     rbx, rbp
0x14001d6b4  jb      short loc_14001D6A7
0x14001d6b6  xor     ebx, ebx
0x14001d6b8  lea     r8, WPP_MAIN_CB.DeviceQueue
0x14001d6bf  mov     qword ptr [rsp+48h+var_28], rbx
0x14001d6c4  lea     rdx, [rsp+48h+var_28]
0x14001d6c9  mov     qword ptr [rsp+48h+var_28+8], rbp
0x14001d6ce  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x14001d6d5  mov     [rsp+48h+var_18], 0
0x14001d6de  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x14001d6e5  nop     dword ptr [rax+rax+00h]
0x14001d6ea  test    eax, eax
0x14001d6ec  jz      short loc_14001D702
0x14001d6ee  xor     ecx, ecx
0x14001d6f0  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, 0
0x14001d6fb  test    edi, edi
0x14001d6fd  cmovnz  eax, ecx
0x14001d700  jmp     short loc_14001D704
0x14001d702  xor     eax, eax
0x14001d704  mov     rbx, [rsp+48h+arg_8]
0x14001d709  mov     rbp, [rsp+48h+arg_10]
0x14001d70e  add     rsp, 40h
0x14001d712  pop     rdi
0x14001d713  retn
```

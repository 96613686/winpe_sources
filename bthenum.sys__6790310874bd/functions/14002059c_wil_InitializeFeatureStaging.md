# wil_InitializeFeatureStaging

- ea: `0x14002059c`
- end: `0x1400206fd`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140020078`

## callees

- `0x14001c5e0`
- `0x14002059c`
- `0x140020704`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400206c6`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400206c6`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400205cd`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400205cd`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140020652`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140020652`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // edi
  __int64 **v1; // rbx
  __int64 **v2; // rax
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
  if ( wil_details_featureDescriptors_a < (__int64 **)wil_details_featureDescriptors_z )
  {
    while ( !*v2 )
    {
      if ( ++v2 >= (__int64 **)wil_details_featureDescriptors_z )
        goto LABEL_19;
    }
LABEL_14:
    if ( v2 )
    {
      if ( *((_BYTE *)v2 + 29) || *((_BYTE *)v2 + 30) || *((_BYTE *)v2 + 28) )
      {
        for ( v2 += 7; v2 < (__int64 **)wil_details_featureDescriptors_z; ++v2 )
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
  while ( v1 < (__int64 **)wil_details_featureDescriptors_z )
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
0x14002059c  mov     [rsp+arg_8], rbx
0x1400205a1  mov     [rsp+arg_10], rbp
0x1400205a6  push    rdi
0x1400205a7  sub     rsp, 40h
0x1400205ab  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400205b2  mov     [rsp+48h+arg_0], 0
0x1400205bb  jnz     loc_1400206EA
0x1400205c1  xor     edi, edi
0x1400205c3  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400205cd  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400205d4  nop     dword ptr [rax+rax+00h]
0x1400205d9  mov     [rsp+48h+arg_0], rax
0x1400205de  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400205e3  call    wil_details_EvaluateFeatureDependencies
0x1400205e8  lea     rbx, wil_details_featureDescriptors_a
0x1400205ef  lea     rbp, wil_details_featureDescriptors_z
0x1400205f6  mov     rax, rbx
0x1400205f9  cmp     rbx, rbp
0x1400205fc  jnb     short loc_140020670
0x1400205fe  cmp     [rax], rdi
0x140020601  jnz     short loc_140020636
0x140020603  add     rax, 8
0x140020607  cmp     rax, rbp
0x14002060a  jb      short loc_1400205FE
0x14002060c  jmp     short loc_140020670
0x14002060e  cmp     [rax+1Dh], dil
0x140020612  jnz     short loc_140020620
0x140020614  cmp     [rax+1Eh], dil
0x140020618  jnz     short loc_140020620
0x14002061a  cmp     [rax+1Ch], dil
0x14002061e  jz      short loc_14002063D
0x140020620  add     rax, 38h ; '8'
0x140020624  jmp     short loc_14002062F
0x140020626  cmp     [rax], rdi
0x140020629  jnz     short loc_140020636
0x14002062b  add     rax, 8
0x14002062f  cmp     rax, rbp
0x140020632  jb      short loc_140020626
0x140020634  jmp     short loc_140020670
0x140020636  test    rax, rax
0x140020639  jnz     short loc_14002060E
0x14002063b  jmp     short loc_140020670
0x14002063d  lea     r9, g_wil_details_featureChangeNotification
0x140020644  xor     edx, edx
0x140020646  lea     r8, [rsp+48h+arg_0]
0x14002064b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140020652  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140020659  nop     dword ptr [rax+rax+00h]
0x14002065e  test    eax, eax
0x140020660  jz      short loc_14002066B
0x140020662  mov     cs:g_wil_details_featureChangeNotification, rdi
0x140020669  jmp     short loc_140020670
0x14002066b  mov     edi, 1
0x140020670  xor     eax, eax
0x140020672  xorps   xmm0, xmm0
0x140020675  mov     [rsp+48h+var_18], rax
0x14002067a  lea     rax, wil_details_RecordFeatureUsageReporting
0x140020681  movups  [rsp+48h+var_28], xmm0
0x140020686  mov     cs:g_wil_details_recordFeatureUsage, rax
0x14002068d  jmp     short loc_140020699
0x14002068f  cmp     qword ptr [rbx], 0
0x140020693  jnz     short loc_1400206A0
0x140020695  add     rbx, 8
0x140020699  cmp     rbx, rbp
0x14002069c  jb      short loc_14002068F
0x14002069e  xor     ebx, ebx
0x1400206a0  lea     r8, g_wil_details_featureUsageProvider
0x1400206a7  mov     qword ptr [rsp+48h+var_28], rbx
0x1400206ac  lea     rdx, [rsp+48h+var_28]
0x1400206b1  mov     qword ptr [rsp+48h+var_28+8], rbp
0x1400206b6  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x1400206bd  mov     [rsp+48h+var_18], 0
0x1400206c6  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x1400206cd  nop     dword ptr [rax+rax+00h]
0x1400206d2  test    eax, eax
0x1400206d4  jz      short loc_1400206EA
0x1400206d6  xor     ecx, ecx
0x1400206d8  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400206e3  test    edi, edi
0x1400206e5  cmovnz  eax, ecx
0x1400206e8  jmp     short loc_1400206EC
0x1400206ea  xor     eax, eax
0x1400206ec  mov     rbx, [rsp+48h+arg_8]
0x1400206f1  mov     rbp, [rsp+48h+arg_10]
0x1400206f6  add     rsp, 40h
0x1400206fa  pop     rdi
0x1400206fb  retn
```

# wil_InitializeFeatureStaging

- ea: `0x1400b6160`
- end: `0x1400b6217`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400b6080`

## callees

- `0x1400442dc`
- `0x1400a97ac`
- `0x1400a99ec`
- `0x1400b6160`
- `0x1400b6220`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400b6188`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400b6188`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400b61de`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400b61de`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  _UNKNOWN **i; // rcx
  _BYTE *v2; // rax
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( *((_DWORD *)&WPP_MAIN_CB.Reserved + 2) )
    return 0;
  v0 = 0;
  *((_DWORD *)&WPP_MAIN_CB.Reserved + 2) = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 56) )
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
                           &WPP_MAIN_CB.Dpc.DpcData) )
        WPP_MAIN_CB.Dpc.DpcData = 0;
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
0x1400b6160  push    rbx
0x1400b6162  sub     rsp, 20h
0x1400b6166  cmp     dword ptr cs:WPP_MAIN_CB+148h, 0
0x1400b616d  mov     [rsp+28h+arg_0], 0
0x1400b6176  jnz     loc_1400B620E
0x1400b617c  xor     ebx, ebx
0x1400b617e  mov     dword ptr cs:WPP_MAIN_CB+148h, 1
0x1400b6188  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400b618f  nop     dword ptr [rax+rax+00h]
0x1400b6194  mov     [rsp+28h+arg_0], rax
0x1400b6199  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400b619e  call    wil_details_EvaluateFeatureDependencies
0x1400b61a3  lea     rcx, wil_details_featureDescriptors_a
0x1400b61aa  call    wil_details_FeatureDescriptors_SkipPadding
0x1400b61af  test    rax, rax
0x1400b61b2  jz      short loc_1400B61FC
0x1400b61b4  cmp     [rax+1Dh], bl
0x1400b61b7  jnz     short loc_1400B61C3
0x1400b61b9  cmp     [rax+1Eh], bl
0x1400b61bc  jnz     short loc_1400B61C3
0x1400b61be  cmp     [rax+1Ch], bl
0x1400b61c1  jz      short loc_1400B61C9
0x1400b61c3  lea     rcx, [rax+38h]
0x1400b61c7  jmp     short loc_1400B61AA
0x1400b61c9  lea     r9, WPP_MAIN_CB.Dpc.DpcData
0x1400b61d0  xor     edx, edx
0x1400b61d2  lea     r8, [rsp+28h+arg_0]
0x1400b61d7  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400b61de  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400b61e5  nop     dword ptr [rax+rax+00h]
0x1400b61ea  test    eax, eax
0x1400b61ec  jz      short loc_1400B61F7
0x1400b61ee  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rbx
0x1400b61f5  jmp     short loc_1400B61FC
0x1400b61f7  mov     ebx, 1
0x1400b61fc  call    wil_details_RegisterFeatureUsageProvider
0x1400b6201  test    eax, eax
0x1400b6203  jz      short loc_1400B620E
0x1400b6205  xor     ecx, ecx
0x1400b6207  test    ebx, ebx
0x1400b6209  cmovnz  eax, ecx
0x1400b620c  jmp     short loc_1400B6210
0x1400b620e  xor     eax, eax
0x1400b6210  add     rsp, 20h
0x1400b6214  pop     rbx
0x1400b6215  retn
```

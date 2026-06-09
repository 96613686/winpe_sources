# wil_InitializeFeatureStaging

- ea: `0x14002b078`
- end: `0x14002b131`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140010750`

## callees

- `0x140011224`
- `0x1400213ec`
- `0x14002168c`
- `0x14002b078`
- `0x14002b138`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002b0f8`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002b0f8`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002b0a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002b0a0`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  __int64 *i; // rcx
  _BYTE *v2; // rax
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) )
    return 0;
  v0 = 0;
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v2 + 56) )
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
                           &WPP_MAIN_CB.Dpc.DeferredRoutine) )
        WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
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
0x14002b078  push    rbx
0x14002b07a  sub     rsp, 20h
0x14002b07e  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14002b085  mov     [rsp+28h+arg_0], 0
0x14002b08e  jnz     loc_14002B128
0x14002b094  xor     ebx, ebx
0x14002b096  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x14002b0a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14002b0a7  nop     dword ptr [rax+rax+00h]
0x14002b0ac  mov     [rsp+28h+arg_0], rax
0x14002b0b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14002b0b6  call    wil_details_EvaluateFeatureDependencies
0x14002b0bb  lea     rcx, wil_details_featureDescriptors_a
0x14002b0c2  jmp     short loc_14002B0D7
0x14002b0c4  cmp     [rax+1Dh], bl
0x14002b0c7  jnz     short loc_14002B0D3
0x14002b0c9  cmp     [rax+1Eh], bl
0x14002b0cc  jnz     short loc_14002B0D3
0x14002b0ce  cmp     [rax+1Ch], bl
0x14002b0d1  jz      short loc_14002B0E3
0x14002b0d3  lea     rcx, [rax+38h]
0x14002b0d7  call    wil_details_FeatureDescriptors_SkipPadding
0x14002b0dc  test    rax, rax
0x14002b0df  jnz     short loc_14002B0C4
0x14002b0e1  jmp     short loc_14002B116
0x14002b0e3  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x14002b0ea  xor     edx, edx
0x14002b0ec  lea     r8, [rsp+28h+arg_0]
0x14002b0f1  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14002b0f8  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14002b0ff  nop     dword ptr [rax+rax+00h]
0x14002b104  test    eax, eax
0x14002b106  jz      short loc_14002B111
0x14002b108  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x14002b10f  jmp     short loc_14002B116
0x14002b111  mov     ebx, 1
0x14002b116  call    wil_details_RegisterFeatureUsageProvider
0x14002b11b  test    eax, eax
0x14002b11d  jz      short loc_14002B128
0x14002b11f  xor     ecx, ecx
0x14002b121  test    ebx, ebx
0x14002b123  cmovnz  eax, ecx
0x14002b126  jmp     short loc_14002B12A
0x14002b128  xor     eax, eax
0x14002b12a  add     rsp, 20h
0x14002b12e  pop     rbx
0x14002b12f  retn
```

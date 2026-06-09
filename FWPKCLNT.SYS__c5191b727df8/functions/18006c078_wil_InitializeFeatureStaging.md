# wil_InitializeFeatureStaging

- ea: `0x18006c078`
- end: `0x18006c14d`
- name: `wil_InitializeFeatureStaging`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cbb0`

## callees

- `0x18000cec4`
- `0x1800203c0`
- `0x180052c2c`
- `0x180052e7c`
- `0x18006c078`
- `0x18006c154`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18006c0af`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18006c0af`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18006c107`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18006c107`

## pseudocode

```c
__int64 __fastcall wil_InitializeFeatureStaging(__int64 a1)
{
  int v1; // ebx
  __int64 v2; // rcx
  _UNKNOWN **i; // rcx
  _BYTE *v4; // rax
  __int64 result; // rax
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF

  v6 = 0;
  if ( LODWORD(WPP_MAIN_CB.SecurityDescriptor) )
    return 0;
  v1 = 0;
  LODWORD(WPP_MAIN_CB.SecurityDescriptor) = 1;
  v6 = RtlQueryFeatureConfigurationChangeStamp(a1);
  wil_details_PopulateInitialConfiguredFeatureStates(v2);
  wil_details_EvaluateFeatureDependencies();
  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v4 + 56) )
  {
    v4 = (_BYTE *)wil_details_FeatureDescriptors_SkipPadding(i);
    if ( !v4 )
      break;
    if ( !v4[29] && !v4[30] && !v4[28] )
    {
      if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                           wil_details_ReevaluateOnFeatureConfigurationChange,
                           0,
                           &v6,
                           &WPP_MAIN_CB.Dpc.DeferredRoutine) )
        WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
      else
        v1 = 1;
      break;
    }
  }
  result = wil_details_RegisterFeatureUsageProvider();
  if ( !(_DWORD)result )
    return 0;
  if ( v1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18006c078  push    rbx
0x18006c07a  sub     rsp, 30h
0x18006c07e  mov     rax, cs:__security_cookie
0x18006c085  xor     rax, rsp
0x18006c088  mov     [rsp+38h+var_10], rax
0x18006c08d  cmp     dword ptr cs:WPP_MAIN_CB.SecurityDescriptor, 0
0x18006c094  mov     [rsp+38h+var_18], 0
0x18006c09d  jnz     loc_18006C137
0x18006c0a3  xor     ebx, ebx
0x18006c0a5  mov     dword ptr cs:WPP_MAIN_CB.SecurityDescriptor, 1
0x18006c0af  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x18006c0b6  nop     dword ptr [rax+rax+00h]
0x18006c0bb  mov     [rsp+38h+var_18], rax
0x18006c0c0  call    wil_details_PopulateInitialConfiguredFeatureStates
0x18006c0c5  call    wil_details_EvaluateFeatureDependencies
0x18006c0ca  lea     rcx, wil_details_featureDescriptors_a
0x18006c0d1  jmp     short loc_18006C0E6
0x18006c0d3  cmp     [rax+1Dh], bl
0x18006c0d6  jnz     short loc_18006C0E2
0x18006c0d8  cmp     [rax+1Eh], bl
0x18006c0db  jnz     short loc_18006C0E2
0x18006c0dd  cmp     [rax+1Ch], bl
0x18006c0e0  jz      short loc_18006C0F2
0x18006c0e2  lea     rcx, [rax+38h]
0x18006c0e6  call    wil_details_FeatureDescriptors_SkipPadding
0x18006c0eb  test    rax, rax
0x18006c0ee  jnz     short loc_18006C0D3
0x18006c0f0  jmp     short loc_18006C125
0x18006c0f2  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x18006c0f9  xor     edx, edx
0x18006c0fb  lea     r8, [rsp+38h+var_18]
0x18006c100  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x18006c107  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x18006c10e  nop     dword ptr [rax+rax+00h]
0x18006c113  test    eax, eax
0x18006c115  jz      short loc_18006C120
0x18006c117  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x18006c11e  jmp     short loc_18006C125
0x18006c120  mov     ebx, 1
0x18006c125  call    wil_details_RegisterFeatureUsageProvider
0x18006c12a  test    eax, eax
0x18006c12c  jz      short loc_18006C137
0x18006c12e  xor     ecx, ecx
0x18006c130  test    ebx, ebx
0x18006c132  cmovnz  eax, ecx
0x18006c135  jmp     short loc_18006C139
0x18006c137  xor     eax, eax
0x18006c139  mov     rcx, [rsp+38h+var_10]
0x18006c13e  xor     rcx, rsp; StackCookie
0x18006c141  call    __security_check_cookie
0x18006c146  add     rsp, 30h
0x18006c14a  pop     rbx
0x18006c14b  retn
```

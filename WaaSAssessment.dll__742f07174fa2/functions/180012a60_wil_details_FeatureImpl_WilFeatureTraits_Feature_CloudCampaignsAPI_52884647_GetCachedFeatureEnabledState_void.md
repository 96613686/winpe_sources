# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647>::GetCachedFeatureEnabledState(void)

- ea: `0x180012a60`
- end: `0x180012b39`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016224`

## callees

- `0x1800119a8`
- `0x180012a60`
- `0x180012cc0`
- `0x1800159a4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_CloudCampaignsAPI_52884647__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CloudCampaignsAPI_52884647__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647>::GetCurrentFeatureEnabledState(
      v5,
      &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_CloudCampaignsAPI_52884647__descriptor,
             v9,
             v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_CloudCampaignsAPI_52884647__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180012a60  mov     [rsp+arg_10], rbx
0x180012a65  mov     [rsp+arg_0], rcx
0x180012a6a  push    rbp
0x180012a6b  push    rsi
0x180012a6c  push    rdi
0x180012a6d  sub     rsp, 20h
0x180012a71  mov     rsi, cs:Feature_CloudCampaignsAPI_52884647__descriptor
0x180012a78  mov     rdi, rdx
0x180012a7b  mov     qword ptr [rdx], 0
0x180012a82  mov     eax, [rsi]
0x180012a84  mov     [rdx], eax
0x180012a86  and     eax, 6
0x180012a89  cmp     al, 6
0x180012a8b  jz      loc_180012B29
0x180012a91  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012a96  lea     r8, [rsp+38h+arg_0]
0x180012a9b  mov     dword ptr [rsp+38h+arg_0], 0
0x180012aa3  lea     rdx, [rsp+38h+arg_8]
0x180012aa8  mov     ebp, eax
0x180012aaa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647>::GetCurrentFeatureEnabledState(int *)
0x180012aaf  mov     eax, [rdi]
0x180012ab1  mov     rbx, [rsp+38h+arg_8]
0x180012ab6  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012abb  mov     edx, eax
0x180012abd  mov     [rdi], eax
0x180012abf  mov     ecx, eax
0x180012ac1  jz      short loc_180012ADC
0x180012ac3  test    dl, 2
0x180012ac6  jnz     short loc_180012ADC
0x180012ac8  and     ecx, 0FFFFF63Eh
0x180012ace  mov     eax, ebx
0x180012ad0  and     eax, 9C1h
0x180012ad5  or      ecx, eax
0x180012ad7  or      ecx, 2
0x180012ada  mov     [rdi], ecx
0x180012adc  mov     r8d, edx
0x180012adf  and     r8d, 4
0x180012ae3  jnz     short loc_180012AF7
0x180012ae5  btr     ecx, 0Ah
0x180012ae9  mov     eax, ebx
0x180012aeb  and     eax, 400h
0x180012af0  or      ecx, eax
0x180012af2  or      ecx, 4
0x180012af5  mov     [rdi], ecx
0x180012af7  mov     eax, edx
0x180012af9  lock cmpxchg [rsi], ecx
0x180012afd  jnz     short loc_180012AB6
0x180012aff  test    r8d, r8d
0x180012b02  jnz     short loc_180012B14
0x180012b04  mov     r8d, ebp
0x180012b07  mov     edx, 3
0x180012b0c  mov     rcx, rsi
0x180012b0f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012b14  mov     eax, [rdi]
0x180012b16  test    al, 2
0x180012b18  jnz     short loc_180012B29
0x180012b1a  and     eax, 0FFFFF63Eh
0x180012b1f  and     ebx, 9C1h
0x180012b25  or      eax, ebx
0x180012b27  mov     [rdi], eax
0x180012b29  mov     rbx, [rsp+38h+arg_10]
0x180012b2e  mov     rax, rdi
0x180012b31  add     rsp, 20h
0x180012b35  pop     rdi
0x180012b36  pop     rsi
0x180012b37  pop     rbp
0x180012b38  retn
```

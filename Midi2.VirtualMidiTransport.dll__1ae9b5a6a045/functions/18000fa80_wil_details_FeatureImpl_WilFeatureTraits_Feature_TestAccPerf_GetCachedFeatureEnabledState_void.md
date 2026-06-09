# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000fa80`
- end: `0x18000fb59`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011bb8`

## callees

- `0x18000ee50`
- `0x18000fa80`
- `0x1800101d0`
- `0x180011648`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18000fa80  mov     [rsp+arg_10], rbx
0x18000fa85  mov     [rsp+arg_0], rcx
0x18000fa8a  push    rbp
0x18000fa8b  push    rsi
0x18000fa8c  push    rdi
0x18000fa8d  sub     rsp, 20h
0x18000fa91  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000fa98  mov     rdi, rdx
0x18000fa9b  mov     qword ptr [rdx], 0
0x18000faa2  mov     eax, [rsi]
0x18000faa4  mov     [rdx], eax
0x18000faa6  and     eax, 6
0x18000faa9  cmp     al, 6
0x18000faab  jz      loc_18000FB49
0x18000fab1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fab6  lea     r8, [rsp+38h+arg_0]
0x18000fabb  mov     dword ptr [rsp+38h+arg_0], 0
0x18000fac3  lea     rdx, [rsp+38h+arg_8]
0x18000fac8  mov     ebp, eax
0x18000faca  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000facf  mov     eax, [rdi]
0x18000fad1  mov     rbx, [rsp+38h+arg_8]
0x18000fad6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000fadb  mov     edx, eax
0x18000fadd  mov     [rdi], eax
0x18000fadf  mov     ecx, eax
0x18000fae1  jz      short loc_18000FAFC
0x18000fae3  test    dl, 2
0x18000fae6  jnz     short loc_18000FAFC
0x18000fae8  and     ecx, 0FFFFF63Eh
0x18000faee  mov     eax, ebx
0x18000faf0  and     eax, 9C1h
0x18000faf5  or      ecx, eax
0x18000faf7  or      ecx, 2
0x18000fafa  mov     [rdi], ecx
0x18000fafc  mov     r8d, edx
0x18000faff  and     r8d, 4
0x18000fb03  jnz     short loc_18000FB17
0x18000fb05  btr     ecx, 0Ah
0x18000fb09  mov     eax, ebx
0x18000fb0b  and     eax, 400h
0x18000fb10  or      ecx, eax
0x18000fb12  or      ecx, 4
0x18000fb15  mov     [rdi], ecx
0x18000fb17  mov     eax, edx
0x18000fb19  lock cmpxchg [rsi], ecx
0x18000fb1d  jnz     short loc_18000FAD6
0x18000fb1f  test    r8d, r8d
0x18000fb22  jnz     short loc_18000FB34
0x18000fb24  mov     r8d, ebp
0x18000fb27  mov     edx, 3
0x18000fb2c  mov     rcx, rsi
0x18000fb2f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000fb34  mov     eax, [rdi]
0x18000fb36  test    al, 2
0x18000fb38  jnz     short loc_18000FB49
0x18000fb3a  and     eax, 0FFFFF63Eh
0x18000fb3f  and     ebx, 9C1h
0x18000fb45  or      eax, ebx
0x18000fb47  mov     [rdi], eax
0x18000fb49  mov     rbx, [rsp+38h+arg_10]
0x18000fb4e  mov     rax, rdi
0x18000fb51  add     rsp, 20h
0x18000fb55  pop     rdi
0x18000fb56  pop     rsi
0x18000fb57  pop     rbp
0x18000fb58  retn
```

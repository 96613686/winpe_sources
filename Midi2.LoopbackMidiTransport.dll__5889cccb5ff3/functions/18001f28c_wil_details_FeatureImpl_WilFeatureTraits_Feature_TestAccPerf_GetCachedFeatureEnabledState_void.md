# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f28c`
- end: `0x18001f365`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021464`

## callees

- `0x18001e65c`
- `0x18001f28c`
- `0x18001f9dc`
- `0x180020fe4`

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
0x18001f28c  mov     [rsp+arg_10], rbx
0x18001f291  mov     [rsp+arg_0], rcx
0x18001f296  push    rbp
0x18001f297  push    rsi
0x18001f298  push    rdi
0x18001f299  sub     rsp, 20h
0x18001f29d  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18001f2a4  mov     rdi, rdx
0x18001f2a7  mov     qword ptr [rdx], 0
0x18001f2ae  mov     eax, [rsi]
0x18001f2b0  mov     [rdx], eax
0x18001f2b2  and     eax, 6
0x18001f2b5  cmp     al, 6
0x18001f2b7  jz      loc_18001F355
0x18001f2bd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f2c2  lea     r8, [rsp+38h+arg_0]
0x18001f2c7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f2cf  lea     rdx, [rsp+38h+arg_8]
0x18001f2d4  mov     ebp, eax
0x18001f2d6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18001f2db  mov     eax, [rdi]
0x18001f2dd  mov     rbx, [rsp+38h+arg_8]
0x18001f2e2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f2e7  mov     edx, eax
0x18001f2e9  mov     [rdi], eax
0x18001f2eb  mov     ecx, eax
0x18001f2ed  jz      short loc_18001F308
0x18001f2ef  test    dl, 2
0x18001f2f2  jnz     short loc_18001F308
0x18001f2f4  and     ecx, 0FFFFF63Eh
0x18001f2fa  mov     eax, ebx
0x18001f2fc  and     eax, 9C1h
0x18001f301  or      ecx, eax
0x18001f303  or      ecx, 2
0x18001f306  mov     [rdi], ecx
0x18001f308  mov     r8d, edx
0x18001f30b  and     r8d, 4
0x18001f30f  jnz     short loc_18001F323
0x18001f311  btr     ecx, 0Ah
0x18001f315  mov     eax, ebx
0x18001f317  and     eax, 400h
0x18001f31c  or      ecx, eax
0x18001f31e  or      ecx, 4
0x18001f321  mov     [rdi], ecx
0x18001f323  mov     eax, edx
0x18001f325  lock cmpxchg [rsi], ecx
0x18001f329  jnz     short loc_18001F2E2
0x18001f32b  test    r8d, r8d
0x18001f32e  jnz     short loc_18001F340
0x18001f330  mov     r8d, ebp
0x18001f333  mov     edx, 3
0x18001f338  mov     rcx, rsi
0x18001f33b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f340  mov     eax, [rdi]
0x18001f342  test    al, 2
0x18001f344  jnz     short loc_18001F355
0x18001f346  and     eax, 0FFFFF63Eh
0x18001f34b  and     ebx, 9C1h
0x18001f351  or      eax, ebx
0x18001f353  mov     [rdi], eax
0x18001f355  mov     rbx, [rsp+38h+arg_10]
0x18001f35a  mov     rax, rdi
0x18001f35d  add     rsp, 20h
0x18001f361  pop     rdi
0x18001f362  pop     rsi
0x18001f363  pop     rbp
0x18001f364  retn
```

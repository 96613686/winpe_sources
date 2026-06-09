# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b714`
- end: `0x18000b7ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000df50`

## callees

- `0x18000ab78`
- `0x18000b714`
- `0x18000be14`
- `0x18000d258`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
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
0x18000b714  mov     [rsp+arg_10], rbx
0x18000b719  mov     [rsp+arg_0], rcx
0x18000b71e  push    rbp
0x18000b71f  push    rsi
0x18000b720  push    rdi
0x18000b721  sub     rsp, 20h
0x18000b725  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18000b72c  mov     rdi, rdx
0x18000b72f  mov     qword ptr [rdx], 0
0x18000b736  mov     eax, [rsi]
0x18000b738  mov     [rdx], eax
0x18000b73a  and     eax, 6
0x18000b73d  cmp     al, 6
0x18000b73f  jz      loc_18000B7DD
0x18000b745  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b74a  lea     r8, [rsp+38h+arg_0]
0x18000b74f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b757  lea     rdx, [rsp+38h+arg_8]
0x18000b75c  mov     ebp, eax
0x18000b75e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000b763  mov     eax, [rdi]
0x18000b765  mov     rbx, [rsp+38h+arg_8]
0x18000b76a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b76f  mov     edx, eax
0x18000b771  mov     [rdi], eax
0x18000b773  mov     ecx, eax
0x18000b775  jz      short loc_18000B790
0x18000b777  test    dl, 2
0x18000b77a  jnz     short loc_18000B790
0x18000b77c  and     ecx, 0FFFFF63Eh
0x18000b782  mov     eax, ebx
0x18000b784  and     eax, 9C1h
0x18000b789  or      ecx, eax
0x18000b78b  or      ecx, 2
0x18000b78e  mov     [rdi], ecx
0x18000b790  mov     r8d, edx
0x18000b793  and     r8d, 4
0x18000b797  jnz     short loc_18000B7AB
0x18000b799  btr     ecx, 0Ah
0x18000b79d  mov     eax, ebx
0x18000b79f  and     eax, 400h
0x18000b7a4  or      ecx, eax
0x18000b7a6  or      ecx, 4
0x18000b7a9  mov     [rdi], ecx
0x18000b7ab  mov     eax, edx
0x18000b7ad  lock cmpxchg [rsi], ecx
0x18000b7b1  jnz     short loc_18000B76A
0x18000b7b3  test    r8d, r8d
0x18000b7b6  jnz     short loc_18000B7C8
0x18000b7b8  mov     r8d, ebp
0x18000b7bb  mov     edx, 3
0x18000b7c0  mov     rcx, rsi
0x18000b7c3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b7c8  mov     eax, [rdi]
0x18000b7ca  test    al, 2
0x18000b7cc  jnz     short loc_18000B7DD
0x18000b7ce  and     eax, 0FFFFF63Eh
0x18000b7d3  and     ebx, 9C1h
0x18000b7d9  or      eax, ebx
0x18000b7db  mov     [rdi], eax
0x18000b7dd  mov     rbx, [rsp+38h+arg_10]
0x18000b7e2  mov     rax, rdi
0x18000b7e5  add     rsp, 20h
0x18000b7e9  pop     rdi
0x18000b7ea  pop     rsi
0x18000b7eb  pop     rbp
0x18000b7ec  retn
```

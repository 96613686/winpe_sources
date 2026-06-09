# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e740`
- end: `0x18000e819`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001608c`
- `0x180018720`

## callees

- `0x18000d7e0`
- `0x18000e740`
- `0x18000f30c`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000e740  mov     [rsp+arg_10], rbx
0x18000e745  mov     [rsp+arg_0], rcx
0x18000e74a  push    rbp
0x18000e74b  push    rsi
0x18000e74c  push    rdi
0x18000e74d  sub     rsp, 20h
0x18000e751  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18000e758  mov     rdi, rdx
0x18000e75b  mov     qword ptr [rdx], 0
0x18000e762  mov     eax, [rsi]
0x18000e764  mov     [rdx], eax
0x18000e766  and     eax, 6
0x18000e769  cmp     al, 6
0x18000e76b  jz      loc_18000E809
0x18000e771  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e776  lea     r8, [rsp+38h+arg_0]
0x18000e77b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e783  lea     rdx, [rsp+38h+arg_8]
0x18000e788  mov     ebp, eax
0x18000e78a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000e78f  mov     eax, [rdi]
0x18000e791  mov     rbx, [rsp+38h+arg_8]
0x18000e796  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e79b  mov     edx, eax
0x18000e79d  mov     [rdi], eax
0x18000e79f  mov     ecx, eax
0x18000e7a1  jz      short loc_18000E7BC
0x18000e7a3  test    dl, 2
0x18000e7a6  jnz     short loc_18000E7BC
0x18000e7a8  and     ecx, 0FFFFF63Eh
0x18000e7ae  mov     eax, ebx
0x18000e7b0  and     eax, 9C1h
0x18000e7b5  or      ecx, eax
0x18000e7b7  or      ecx, 2
0x18000e7ba  mov     [rdi], ecx
0x18000e7bc  mov     r8d, edx
0x18000e7bf  and     r8d, 4
0x18000e7c3  jnz     short loc_18000E7D7
0x18000e7c5  btr     ecx, 0Ah
0x18000e7c9  mov     eax, ebx
0x18000e7cb  and     eax, 400h
0x18000e7d0  or      ecx, eax
0x18000e7d2  or      ecx, 4
0x18000e7d5  mov     [rdi], ecx
0x18000e7d7  mov     eax, edx
0x18000e7d9  lock cmpxchg [rsi], ecx
0x18000e7dd  jnz     short loc_18000E796
0x18000e7df  test    r8d, r8d
0x18000e7e2  jnz     short loc_18000E7F4
0x18000e7e4  mov     r8d, ebp
0x18000e7e7  mov     edx, 3
0x18000e7ec  mov     rcx, rsi
0x18000e7ef  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e7f4  mov     eax, [rdi]
0x18000e7f6  test    al, 2
0x18000e7f8  jnz     short loc_18000E809
0x18000e7fa  and     eax, 0FFFFF63Eh
0x18000e7ff  and     ebx, 9C1h
0x18000e805  or      eax, ebx
0x18000e807  mov     [rdi], eax
0x18000e809  mov     rbx, [rsp+38h+arg_10]
0x18000e80e  mov     rax, rdi
0x18000e811  add     rsp, 20h
0x18000e815  pop     rdi
0x18000e816  pop     rsi
0x18000e817  pop     rbp
0x18000e818  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800214b0`
- end: `0x180021589`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800255fc`
- `0x180028b14`

## callees

- `0x180019930`
- `0x18001a080`
- `0x1800214b0`
- `0x180022048`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestLoc1Perf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800214b0  mov     [rsp+arg_10], rbx
0x1800214b5  mov     [rsp+arg_0], rcx
0x1800214ba  push    rbp
0x1800214bb  push    rsi
0x1800214bc  push    rdi
0x1800214bd  sub     rsp, 20h
0x1800214c1  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x1800214c8  mov     rdi, rdx
0x1800214cb  mov     qword ptr [rdx], 0
0x1800214d2  mov     eax, [rsi]
0x1800214d4  mov     [rdx], eax
0x1800214d6  and     eax, 6
0x1800214d9  cmp     al, 6
0x1800214db  jz      loc_180021579
0x1800214e1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800214e6  lea     r8, [rsp+38h+arg_0]
0x1800214eb  mov     dword ptr [rsp+38h+arg_0], 0
0x1800214f3  lea     rdx, [rsp+38h+arg_8]
0x1800214f8  mov     ebp, eax
0x1800214fa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x1800214ff  mov     eax, [rdi]
0x180021501  mov     rbx, [rsp+38h+arg_8]
0x180021506  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002150b  mov     edx, eax
0x18002150d  mov     [rdi], eax
0x18002150f  mov     ecx, eax
0x180021511  jz      short loc_18002152C
0x180021513  test    dl, 2
0x180021516  jnz     short loc_18002152C
0x180021518  and     ecx, 0FFFFF63Eh
0x18002151e  mov     eax, ebx
0x180021520  and     eax, 9C1h
0x180021525  or      ecx, eax
0x180021527  or      ecx, 2
0x18002152a  mov     [rdi], ecx
0x18002152c  mov     r8d, edx
0x18002152f  and     r8d, 4
0x180021533  jnz     short loc_180021547
0x180021535  btr     ecx, 0Ah
0x180021539  mov     eax, ebx
0x18002153b  and     eax, 400h
0x180021540  or      ecx, eax
0x180021542  or      ecx, 4
0x180021545  mov     [rdi], ecx
0x180021547  mov     eax, edx
0x180021549  lock cmpxchg [rsi], ecx
0x18002154d  jnz     short loc_180021506
0x18002154f  test    r8d, r8d
0x180021552  jnz     short loc_180021564
0x180021554  mov     r8d, ebp
0x180021557  mov     edx, 3
0x18002155c  mov     rcx, rsi
0x18002155f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180021564  mov     eax, [rdi]
0x180021566  test    al, 2
0x180021568  jnz     short loc_180021579
0x18002156a  and     eax, 0FFFFF63Eh
0x18002156f  and     ebx, 9C1h
0x180021575  or      eax, ebx
0x180021577  mov     [rdi], eax
0x180021579  mov     rbx, [rsp+38h+arg_10]
0x18002157e  mov     rax, rdi
0x180021581  add     rsp, 20h
0x180021585  pop     rdi
0x180021586  pop     rsi
0x180021587  pop     rbp
0x180021588  retn
```

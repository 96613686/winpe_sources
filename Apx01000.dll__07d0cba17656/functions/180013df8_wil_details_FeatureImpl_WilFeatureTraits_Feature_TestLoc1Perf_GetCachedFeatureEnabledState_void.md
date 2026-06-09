# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180013df8`
- end: `0x180013ed1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015610`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013df8`
- `0x180014c2c`

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
0x180013df8  mov     [rsp+arg_10], rbx
0x180013dfd  mov     [rsp+arg_0], rcx
0x180013e02  push    rbp
0x180013e03  push    rsi
0x180013e04  push    rdi
0x180013e05  sub     rsp, 20h
0x180013e09  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180013e10  mov     rdi, rdx
0x180013e13  mov     qword ptr [rdx], 0
0x180013e1a  mov     eax, [rsi]
0x180013e1c  mov     [rdx], eax
0x180013e1e  and     eax, 6
0x180013e21  cmp     al, 6
0x180013e23  jz      loc_180013EC1
0x180013e29  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013e2e  lea     r8, [rsp+38h+arg_0]
0x180013e33  mov     dword ptr [rsp+38h+arg_0], 0
0x180013e3b  lea     rdx, [rsp+38h+arg_8]
0x180013e40  mov     ebp, eax
0x180013e42  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180013e47  mov     eax, [rdi]
0x180013e49  mov     rbx, [rsp+38h+arg_8]
0x180013e4e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013e53  mov     edx, eax
0x180013e55  mov     [rdi], eax
0x180013e57  mov     ecx, eax
0x180013e59  jz      short loc_180013E74
0x180013e5b  test    dl, 2
0x180013e5e  jnz     short loc_180013E74
0x180013e60  and     ecx, 0FFFFF63Eh
0x180013e66  mov     eax, ebx
0x180013e68  and     eax, 9C1h
0x180013e6d  or      ecx, eax
0x180013e6f  or      ecx, 2
0x180013e72  mov     [rdi], ecx
0x180013e74  mov     r8d, edx
0x180013e77  and     r8d, 4
0x180013e7b  jnz     short loc_180013E8F
0x180013e7d  btr     ecx, 0Ah
0x180013e81  mov     eax, ebx
0x180013e83  and     eax, 400h
0x180013e88  or      ecx, eax
0x180013e8a  or      ecx, 4
0x180013e8d  mov     [rdi], ecx
0x180013e8f  mov     eax, edx
0x180013e91  lock cmpxchg [rsi], ecx
0x180013e95  jnz     short loc_180013E4E
0x180013e97  test    r8d, r8d
0x180013e9a  jnz     short loc_180013EAC
0x180013e9c  mov     r8d, ebp
0x180013e9f  mov     edx, 3
0x180013ea4  mov     rcx, rsi
0x180013ea7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013eac  mov     eax, [rdi]
0x180013eae  test    al, 2
0x180013eb0  jnz     short loc_180013EC1
0x180013eb2  and     eax, 0FFFFF63Eh
0x180013eb7  and     ebx, 9C1h
0x180013ebd  or      eax, ebx
0x180013ebf  mov     [rdi], eax
0x180013ec1  mov     rbx, [rsp+38h+arg_10]
0x180013ec6  mov     rax, rdi
0x180013ec9  add     rsp, 20h
0x180013ecd  pop     rdi
0x180013ece  pop     rsi
0x180013ecf  pop     rbp
0x180013ed0  retn
```

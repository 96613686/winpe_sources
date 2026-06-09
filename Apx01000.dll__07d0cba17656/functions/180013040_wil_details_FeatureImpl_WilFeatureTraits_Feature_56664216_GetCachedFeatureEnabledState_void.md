# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::GetCachedFeatureEnabledState(void)

- ea: `0x180013040`
- end: `0x180013119`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015228`
- `0x1800153f8`
- `0x18001909c`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013040`
- `0x18001472c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_56664216__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56664216__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56664216__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_56664216__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180013040  mov     [rsp+arg_10], rbx
0x180013045  mov     [rsp+arg_0], rcx
0x18001304a  push    rbp
0x18001304b  push    rsi
0x18001304c  push    rdi
0x18001304d  sub     rsp, 20h
0x180013051  mov     rsi, cs:Feature_56664216__descriptor
0x180013058  mov     rdi, rdx
0x18001305b  mov     qword ptr [rdx], 0
0x180013062  mov     eax, [rsi]
0x180013064  mov     [rdx], eax
0x180013066  and     eax, 6
0x180013069  cmp     al, 6
0x18001306b  jz      loc_180013109
0x180013071  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013076  lea     r8, [rsp+38h+arg_0]
0x18001307b  mov     dword ptr [rsp+38h+arg_0], 0
0x180013083  lea     rdx, [rsp+38h+arg_8]
0x180013088  mov     ebp, eax
0x18001308a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::GetCurrentFeatureEnabledState(int *)
0x18001308f  mov     eax, [rdi]
0x180013091  mov     rbx, [rsp+38h+arg_8]
0x180013096  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001309b  mov     edx, eax
0x18001309d  mov     [rdi], eax
0x18001309f  mov     ecx, eax
0x1800130a1  jz      short loc_1800130BC
0x1800130a3  test    dl, 2
0x1800130a6  jnz     short loc_1800130BC
0x1800130a8  and     ecx, 0FFFFF63Eh
0x1800130ae  mov     eax, ebx
0x1800130b0  and     eax, 9C1h
0x1800130b5  or      ecx, eax
0x1800130b7  or      ecx, 2
0x1800130ba  mov     [rdi], ecx
0x1800130bc  mov     r8d, edx
0x1800130bf  and     r8d, 4
0x1800130c3  jnz     short loc_1800130D7
0x1800130c5  btr     ecx, 0Ah
0x1800130c9  mov     eax, ebx
0x1800130cb  and     eax, 400h
0x1800130d0  or      ecx, eax
0x1800130d2  or      ecx, 4
0x1800130d5  mov     [rdi], ecx
0x1800130d7  mov     eax, edx
0x1800130d9  lock cmpxchg [rsi], ecx
0x1800130dd  jnz     short loc_180013096
0x1800130df  test    r8d, r8d
0x1800130e2  jnz     short loc_1800130F4
0x1800130e4  mov     r8d, ebp
0x1800130e7  mov     edx, 3
0x1800130ec  mov     rcx, rsi
0x1800130ef  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800130f4  mov     eax, [rdi]
0x1800130f6  test    al, 2
0x1800130f8  jnz     short loc_180013109
0x1800130fa  and     eax, 0FFFFF63Eh
0x1800130ff  and     ebx, 9C1h
0x180013105  or      eax, ebx
0x180013107  mov     [rdi], eax
0x180013109  mov     rbx, [rsp+38h+arg_10]
0x18001310e  mov     rax, rdi
0x180013111  add     rsp, 20h
0x180013115  pop     rdi
0x180013116  pop     rsi
0x180013117  pop     rbp
0x180013118  retn
```

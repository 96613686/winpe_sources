# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x140005634`
- end: `0x14000570d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b710`

## callees

- `0x1400049e0`
- `0x140005634`
- `0x140005d00`
- `0x14000a88c`

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
0x140005634  mov     [rsp+arg_10], rbx
0x140005639  mov     [rsp+arg_0], rcx
0x14000563e  push    rbp
0x14000563f  push    rsi
0x140005640  push    rdi
0x140005641  sub     rsp, 20h
0x140005645  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x14000564c  mov     rdi, rdx
0x14000564f  mov     qword ptr [rdx], 0
0x140005656  mov     eax, [rsi]
0x140005658  mov     [rdx], eax
0x14000565a  and     eax, 6
0x14000565d  cmp     al, 6
0x14000565f  jz      loc_1400056FD
0x140005665  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000566a  lea     r8, [rsp+38h+arg_0]
0x14000566f  mov     dword ptr [rsp+38h+arg_0], 0
0x140005677  lea     rdx, [rsp+38h+arg_8]
0x14000567c  mov     ebp, eax
0x14000567e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x140005683  mov     eax, [rdi]
0x140005685  mov     rbx, [rsp+38h+arg_8]
0x14000568a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000568f  mov     edx, eax
0x140005691  mov     [rdi], eax
0x140005693  mov     ecx, eax
0x140005695  jz      short loc_1400056B0
0x140005697  test    dl, 2
0x14000569a  jnz     short loc_1400056B0
0x14000569c  and     ecx, 0FFFFF63Eh
0x1400056a2  mov     eax, ebx
0x1400056a4  and     eax, 9C1h
0x1400056a9  or      ecx, eax
0x1400056ab  or      ecx, 2
0x1400056ae  mov     [rdi], ecx
0x1400056b0  mov     r8d, edx
0x1400056b3  and     r8d, 4
0x1400056b7  jnz     short loc_1400056CB
0x1400056b9  btr     ecx, 0Ah
0x1400056bd  mov     eax, ebx
0x1400056bf  and     eax, 400h
0x1400056c4  or      ecx, eax
0x1400056c6  or      ecx, 4
0x1400056c9  mov     [rdi], ecx
0x1400056cb  mov     eax, edx
0x1400056cd  lock cmpxchg [rsi], ecx
0x1400056d1  jnz     short loc_14000568A
0x1400056d3  test    r8d, r8d
0x1400056d6  jnz     short loc_1400056E8
0x1400056d8  mov     r8d, ebp
0x1400056db  mov     edx, 3
0x1400056e0  mov     rcx, rsi
0x1400056e3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400056e8  mov     eax, [rdi]
0x1400056ea  test    al, 2
0x1400056ec  jnz     short loc_1400056FD
0x1400056ee  and     eax, 0FFFFF63Eh
0x1400056f3  and     ebx, 9C1h
0x1400056f9  or      eax, ebx
0x1400056fb  mov     [rdi], eax
0x1400056fd  mov     rbx, [rsp+38h+arg_10]
0x140005702  mov     rax, rdi
0x140005705  add     rsp, 20h
0x140005709  pop     rdi
0x14000570a  pop     rsi
0x14000570b  pop     rbp
0x14000570c  retn
```

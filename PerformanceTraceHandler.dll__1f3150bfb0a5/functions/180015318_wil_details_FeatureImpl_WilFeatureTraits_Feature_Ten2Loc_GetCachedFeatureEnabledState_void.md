# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180015318`
- end: `0x1800153f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800173c8`
- `0x180017d20`

## callees

- `0x18000543c`
- `0x180008794`
- `0x180015318`
- `0x180015b2c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Ten2Loc__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180015318  mov     [rsp+arg_10], rbx
0x18001531d  mov     [rsp+arg_0], rcx
0x180015322  push    rbp
0x180015323  push    rsi
0x180015324  push    rdi
0x180015325  sub     rsp, 20h
0x180015329  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180015330  mov     rdi, rdx
0x180015333  mov     qword ptr [rdx], 0
0x18001533a  mov     eax, [rsi]
0x18001533c  mov     [rdx], eax
0x18001533e  and     eax, 6
0x180015341  cmp     al, 6
0x180015343  jz      loc_1800153E1
0x180015349  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001534e  lea     r8, [rsp+38h+arg_0]
0x180015353  mov     dword ptr [rsp+38h+arg_0], 0
0x18001535b  lea     rdx, [rsp+38h+arg_8]
0x180015360  mov     ebp, eax
0x180015362  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180015367  mov     eax, [rdi]
0x180015369  mov     rbx, [rsp+38h+arg_8]
0x18001536e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180015373  mov     edx, eax
0x180015375  mov     [rdi], eax
0x180015377  mov     ecx, eax
0x180015379  jz      short loc_180015394
0x18001537b  test    dl, 2
0x18001537e  jnz     short loc_180015394
0x180015380  and     ecx, 0FFFFF63Eh
0x180015386  mov     eax, ebx
0x180015388  and     eax, 9C1h
0x18001538d  or      ecx, eax
0x18001538f  or      ecx, 2
0x180015392  mov     [rdi], ecx
0x180015394  mov     r8d, edx
0x180015397  and     r8d, 4
0x18001539b  jnz     short loc_1800153AF
0x18001539d  btr     ecx, 0Ah
0x1800153a1  mov     eax, ebx
0x1800153a3  and     eax, 400h
0x1800153a8  or      ecx, eax
0x1800153aa  or      ecx, 4
0x1800153ad  mov     [rdi], ecx
0x1800153af  mov     eax, edx
0x1800153b1  lock cmpxchg [rsi], ecx
0x1800153b5  jnz     short loc_18001536E
0x1800153b7  test    r8d, r8d
0x1800153ba  jnz     short loc_1800153CC
0x1800153bc  mov     r8d, ebp
0x1800153bf  mov     edx, 3
0x1800153c4  mov     rcx, rsi
0x1800153c7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800153cc  mov     eax, [rdi]
0x1800153ce  test    al, 2
0x1800153d0  jnz     short loc_1800153E1
0x1800153d2  and     eax, 0FFFFF63Eh
0x1800153d7  and     ebx, 9C1h
0x1800153dd  or      eax, ebx
0x1800153df  mov     [rdi], eax
0x1800153e1  mov     rbx, [rsp+38h+arg_10]
0x1800153e6  mov     rax, rdi
0x1800153e9  add     rsp, 20h
0x1800153ed  pop     rdi
0x1800153ee  pop     rsi
0x1800153ef  pop     rbp
0x1800153f0  retn
```

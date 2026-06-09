# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180014218`
- end: `0x1800142f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800157e4`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180014218`
- `0x18001507c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180014218  mov     [rsp+arg_10], rbx
0x18001421d  mov     [rsp+arg_0], rcx
0x180014222  push    rbp
0x180014223  push    rsi
0x180014224  push    rdi
0x180014225  sub     rsp, 20h
0x180014229  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180014230  mov     rdi, rdx
0x180014233  mov     qword ptr [rdx], 0
0x18001423a  mov     eax, [rsi]
0x18001423c  mov     [rdx], eax
0x18001423e  and     eax, 6
0x180014241  cmp     al, 6
0x180014243  jz      loc_1800142E1
0x180014249  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001424e  lea     r8, [rsp+38h+arg_0]
0x180014253  mov     dword ptr [rsp+38h+arg_0], 0
0x18001425b  lea     rdx, [rsp+38h+arg_8]
0x180014260  mov     ebp, eax
0x180014262  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180014267  mov     eax, [rdi]
0x180014269  mov     rbx, [rsp+38h+arg_8]
0x18001426e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014273  mov     edx, eax
0x180014275  mov     [rdi], eax
0x180014277  mov     ecx, eax
0x180014279  jz      short loc_180014294
0x18001427b  test    dl, 2
0x18001427e  jnz     short loc_180014294
0x180014280  and     ecx, 0FFFFF63Eh
0x180014286  mov     eax, ebx
0x180014288  and     eax, 9C1h
0x18001428d  or      ecx, eax
0x18001428f  or      ecx, 2
0x180014292  mov     [rdi], ecx
0x180014294  mov     r8d, edx
0x180014297  and     r8d, 4
0x18001429b  jnz     short loc_1800142AF
0x18001429d  btr     ecx, 0Ah
0x1800142a1  mov     eax, ebx
0x1800142a3  and     eax, 400h
0x1800142a8  or      ecx, eax
0x1800142aa  or      ecx, 4
0x1800142ad  mov     [rdi], ecx
0x1800142af  mov     eax, edx
0x1800142b1  lock cmpxchg [rsi], ecx
0x1800142b5  jnz     short loc_18001426E
0x1800142b7  test    r8d, r8d
0x1800142ba  jnz     short loc_1800142CC
0x1800142bc  mov     r8d, ebp
0x1800142bf  mov     edx, 3
0x1800142c4  mov     rcx, rsi
0x1800142c7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800142cc  mov     eax, [rdi]
0x1800142ce  test    al, 2
0x1800142d0  jnz     short loc_1800142E1
0x1800142d2  and     eax, 0FFFFF63Eh
0x1800142d7  and     ebx, 9C1h
0x1800142dd  or      eax, ebx
0x1800142df  mov     [rdi], eax
0x1800142e1  mov     rbx, [rsp+38h+arg_10]
0x1800142e6  mov     rax, rdi
0x1800142e9  add     rsp, 20h
0x1800142ed  pop     rdi
0x1800142ee  pop     rsi
0x1800142ef  pop     rbp
0x1800142f0  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180015698`
- end: `0x180015771`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800175e8`
- `0x180017e10`

## callees

- `0x18000543c`
- `0x180008794`
- `0x180015698`
- `0x18001606c`

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
0x180015698  mov     [rsp+arg_10], rbx
0x18001569d  mov     [rsp+arg_0], rcx
0x1800156a2  push    rbp
0x1800156a3  push    rsi
0x1800156a4  push    rdi
0x1800156a5  sub     rsp, 20h
0x1800156a9  mov     rsi, cs:Feature_ValAccTest__descriptor
0x1800156b0  mov     rdi, rdx
0x1800156b3  mov     qword ptr [rdx], 0
0x1800156ba  mov     eax, [rsi]
0x1800156bc  mov     [rdx], eax
0x1800156be  and     eax, 6
0x1800156c1  cmp     al, 6
0x1800156c3  jz      loc_180015761
0x1800156c9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800156ce  lea     r8, [rsp+38h+arg_0]
0x1800156d3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800156db  lea     rdx, [rsp+38h+arg_8]
0x1800156e0  mov     ebp, eax
0x1800156e2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x1800156e7  mov     eax, [rdi]
0x1800156e9  mov     rbx, [rsp+38h+arg_8]
0x1800156ee  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800156f3  mov     edx, eax
0x1800156f5  mov     [rdi], eax
0x1800156f7  mov     ecx, eax
0x1800156f9  jz      short loc_180015714
0x1800156fb  test    dl, 2
0x1800156fe  jnz     short loc_180015714
0x180015700  and     ecx, 0FFFFF63Eh
0x180015706  mov     eax, ebx
0x180015708  and     eax, 9C1h
0x18001570d  or      ecx, eax
0x18001570f  or      ecx, 2
0x180015712  mov     [rdi], ecx
0x180015714  mov     r8d, edx
0x180015717  and     r8d, 4
0x18001571b  jnz     short loc_18001572F
0x18001571d  btr     ecx, 0Ah
0x180015721  mov     eax, ebx
0x180015723  and     eax, 400h
0x180015728  or      ecx, eax
0x18001572a  or      ecx, 4
0x18001572d  mov     [rdi], ecx
0x18001572f  mov     eax, edx
0x180015731  lock cmpxchg [rsi], ecx
0x180015735  jnz     short loc_1800156EE
0x180015737  test    r8d, r8d
0x18001573a  jnz     short loc_18001574C
0x18001573c  mov     r8d, ebp
0x18001573f  mov     edx, 3
0x180015744  mov     rcx, rsi
0x180015747  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001574c  mov     eax, [rdi]
0x18001574e  test    al, 2
0x180015750  jnz     short loc_180015761
0x180015752  and     eax, 0FFFFF63Eh
0x180015757  and     ebx, 9C1h
0x18001575d  or      eax, ebx
0x18001575f  mov     [rdi], eax
0x180015761  mov     rbx, [rsp+38h+arg_10]
0x180015766  mov     rax, rdi
0x180015769  add     rsp, 20h
0x18001576d  pop     rdi
0x18001576e  pop     rsi
0x18001576f  pop     rbp
0x180015770  retn
```

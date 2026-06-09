# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f60c`
- end: `0x18001f6e5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800216d4`

## callees

- `0x18001e65c`
- `0x18001f60c`
- `0x18001ff9c`
- `0x180020fe4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x18001f60c  mov     [rsp+arg_10], rbx
0x18001f611  mov     [rsp+arg_0], rcx
0x18001f616  push    rbp
0x18001f617  push    rsi
0x18001f618  push    rdi
0x18001f619  sub     rsp, 20h
0x18001f61d  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18001f624  mov     rdi, rdx
0x18001f627  mov     qword ptr [rdx], 0
0x18001f62e  mov     eax, [rsi]
0x18001f630  mov     [rdx], eax
0x18001f632  and     eax, 6
0x18001f635  cmp     al, 6
0x18001f637  jz      loc_18001F6D5
0x18001f63d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f642  lea     r8, [rsp+38h+arg_0]
0x18001f647  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f64f  lea     rdx, [rsp+38h+arg_8]
0x18001f654  mov     ebp, eax
0x18001f656  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18001f65b  mov     eax, [rdi]
0x18001f65d  mov     rbx, [rsp+38h+arg_8]
0x18001f662  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f667  mov     edx, eax
0x18001f669  mov     [rdi], eax
0x18001f66b  mov     ecx, eax
0x18001f66d  jz      short loc_18001F688
0x18001f66f  test    dl, 2
0x18001f672  jnz     short loc_18001F688
0x18001f674  and     ecx, 0FFFFF63Eh
0x18001f67a  mov     eax, ebx
0x18001f67c  and     eax, 9C1h
0x18001f681  or      ecx, eax
0x18001f683  or      ecx, 2
0x18001f686  mov     [rdi], ecx
0x18001f688  mov     r8d, edx
0x18001f68b  and     r8d, 4
0x18001f68f  jnz     short loc_18001F6A3
0x18001f691  btr     ecx, 0Ah
0x18001f695  mov     eax, ebx
0x18001f697  and     eax, 400h
0x18001f69c  or      ecx, eax
0x18001f69e  or      ecx, 4
0x18001f6a1  mov     [rdi], ecx
0x18001f6a3  mov     eax, edx
0x18001f6a5  lock cmpxchg [rsi], ecx
0x18001f6a9  jnz     short loc_18001F662
0x18001f6ab  test    r8d, r8d
0x18001f6ae  jnz     short loc_18001F6C0
0x18001f6b0  mov     r8d, ebp
0x18001f6b3  mov     edx, 3
0x18001f6b8  mov     rcx, rsi
0x18001f6bb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f6c0  mov     eax, [rdi]
0x18001f6c2  test    al, 2
0x18001f6c4  jnz     short loc_18001F6D5
0x18001f6c6  and     eax, 0FFFFF63Eh
0x18001f6cb  and     ebx, 9C1h
0x18001f6d1  or      eax, ebx
0x18001f6d3  mov     [rdi], eax
0x18001f6d5  mov     rbx, [rsp+38h+arg_10]
0x18001f6da  mov     rax, rdi
0x18001f6dd  add     rsp, 20h
0x18001f6e1  pop     rdi
0x18001f6e2  pop     rsi
0x18001f6e3  pop     rbp
0x18001f6e4  retn
```

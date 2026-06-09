# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f52c`
- end: `0x18001f605`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021638`

## callees

- `0x18001e65c`
- `0x18001f52c`
- `0x18001fe2c`
- `0x180020fe4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UexTest7__descriptor,
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
0x18001f52c  mov     [rsp+arg_10], rbx
0x18001f531  mov     [rsp+arg_0], rcx
0x18001f536  push    rbp
0x18001f537  push    rsi
0x18001f538  push    rdi
0x18001f539  sub     rsp, 20h
0x18001f53d  mov     rsi, cs:Feature_UexTest7__descriptor
0x18001f544  mov     rdi, rdx
0x18001f547  mov     qword ptr [rdx], 0
0x18001f54e  mov     eax, [rsi]
0x18001f550  mov     [rdx], eax
0x18001f552  and     eax, 6
0x18001f555  cmp     al, 6
0x18001f557  jz      loc_18001F5F5
0x18001f55d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f562  lea     r8, [rsp+38h+arg_0]
0x18001f567  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f56f  lea     rdx, [rsp+38h+arg_8]
0x18001f574  mov     ebp, eax
0x18001f576  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18001f57b  mov     eax, [rdi]
0x18001f57d  mov     rbx, [rsp+38h+arg_8]
0x18001f582  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f587  mov     edx, eax
0x18001f589  mov     [rdi], eax
0x18001f58b  mov     ecx, eax
0x18001f58d  jz      short loc_18001F5A8
0x18001f58f  test    dl, 2
0x18001f592  jnz     short loc_18001F5A8
0x18001f594  and     ecx, 0FFFFF63Eh
0x18001f59a  mov     eax, ebx
0x18001f59c  and     eax, 9C1h
0x18001f5a1  or      ecx, eax
0x18001f5a3  or      ecx, 2
0x18001f5a6  mov     [rdi], ecx
0x18001f5a8  mov     r8d, edx
0x18001f5ab  and     r8d, 4
0x18001f5af  jnz     short loc_18001F5C3
0x18001f5b1  btr     ecx, 0Ah
0x18001f5b5  mov     eax, ebx
0x18001f5b7  and     eax, 400h
0x18001f5bc  or      ecx, eax
0x18001f5be  or      ecx, 4
0x18001f5c1  mov     [rdi], ecx
0x18001f5c3  mov     eax, edx
0x18001f5c5  lock cmpxchg [rsi], ecx
0x18001f5c9  jnz     short loc_18001F582
0x18001f5cb  test    r8d, r8d
0x18001f5ce  jnz     short loc_18001F5E0
0x18001f5d0  mov     r8d, ebp
0x18001f5d3  mov     edx, 3
0x18001f5d8  mov     rcx, rsi
0x18001f5db  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f5e0  mov     eax, [rdi]
0x18001f5e2  test    al, 2
0x18001f5e4  jnz     short loc_18001F5F5
0x18001f5e6  and     eax, 0FFFFF63Eh
0x18001f5eb  and     ebx, 9C1h
0x18001f5f1  or      eax, ebx
0x18001f5f3  mov     [rdi], eax
0x18001f5f5  mov     rbx, [rsp+38h+arg_10]
0x18001f5fa  mov     rax, rdi
0x18001f5fd  add     rsp, 20h
0x18001f601  pop     rdi
0x18001f602  pop     rsi
0x18001f603  pop     rbp
0x18001f604  retn
```

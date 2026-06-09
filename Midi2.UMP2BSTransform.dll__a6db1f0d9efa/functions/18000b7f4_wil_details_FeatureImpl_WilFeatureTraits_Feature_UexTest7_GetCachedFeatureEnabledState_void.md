# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b7f4`
- end: `0x18000b8cd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dfec`

## callees

- `0x18000ab78`
- `0x18000b7f4`
- `0x18000bf84`
- `0x18000d258`

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
0x18000b7f4  mov     [rsp+arg_10], rbx
0x18000b7f9  mov     [rsp+arg_0], rcx
0x18000b7fe  push    rbp
0x18000b7ff  push    rsi
0x18000b800  push    rdi
0x18000b801  sub     rsp, 20h
0x18000b805  mov     rsi, cs:Feature_UexTest7__descriptor
0x18000b80c  mov     rdi, rdx
0x18000b80f  mov     qword ptr [rdx], 0
0x18000b816  mov     eax, [rsi]
0x18000b818  mov     [rdx], eax
0x18000b81a  and     eax, 6
0x18000b81d  cmp     al, 6
0x18000b81f  jz      loc_18000B8BD
0x18000b825  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b82a  lea     r8, [rsp+38h+arg_0]
0x18000b82f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b837  lea     rdx, [rsp+38h+arg_8]
0x18000b83c  mov     ebp, eax
0x18000b83e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18000b843  mov     eax, [rdi]
0x18000b845  mov     rbx, [rsp+38h+arg_8]
0x18000b84a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b84f  mov     edx, eax
0x18000b851  mov     [rdi], eax
0x18000b853  mov     ecx, eax
0x18000b855  jz      short loc_18000B870
0x18000b857  test    dl, 2
0x18000b85a  jnz     short loc_18000B870
0x18000b85c  and     ecx, 0FFFFF63Eh
0x18000b862  mov     eax, ebx
0x18000b864  and     eax, 9C1h
0x18000b869  or      ecx, eax
0x18000b86b  or      ecx, 2
0x18000b86e  mov     [rdi], ecx
0x18000b870  mov     r8d, edx
0x18000b873  and     r8d, 4
0x18000b877  jnz     short loc_18000B88B
0x18000b879  btr     ecx, 0Ah
0x18000b87d  mov     eax, ebx
0x18000b87f  and     eax, 400h
0x18000b884  or      ecx, eax
0x18000b886  or      ecx, 4
0x18000b889  mov     [rdi], ecx
0x18000b88b  mov     eax, edx
0x18000b88d  lock cmpxchg [rsi], ecx
0x18000b891  jnz     short loc_18000B84A
0x18000b893  test    r8d, r8d
0x18000b896  jnz     short loc_18000B8A8
0x18000b898  mov     r8d, ebp
0x18000b89b  mov     edx, 3
0x18000b8a0  mov     rcx, rsi
0x18000b8a3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b8a8  mov     eax, [rdi]
0x18000b8aa  test    al, 2
0x18000b8ac  jnz     short loc_18000B8BD
0x18000b8ae  and     eax, 0FFFFF63Eh
0x18000b8b3  and     ebx, 9C1h
0x18000b8b9  or      eax, ebx
0x18000b8bb  mov     [rdi], eax
0x18000b8bd  mov     rbx, [rsp+38h+arg_10]
0x18000b8c2  mov     rax, rdi
0x18000b8c5  add     rsp, 20h
0x18000b8c9  pop     rdi
0x18000b8ca  pop     rsi
0x18000b8cb  pop     rbp
0x18000b8cc  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b634`
- end: `0x18000b70d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000deb4`

## callees

- `0x18000ab78`
- `0x18000b634`
- `0x18000bca4`
- `0x18000d258`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18000b634  mov     [rsp+arg_10], rbx
0x18000b639  mov     [rsp+arg_0], rcx
0x18000b63e  push    rbp
0x18000b63f  push    rsi
0x18000b640  push    rdi
0x18000b641  sub     rsp, 20h
0x18000b645  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000b64c  mov     rdi, rdx
0x18000b64f  mov     qword ptr [rdx], 0
0x18000b656  mov     eax, [rsi]
0x18000b658  mov     [rdx], eax
0x18000b65a  and     eax, 6
0x18000b65d  cmp     al, 6
0x18000b65f  jz      loc_18000B6FD
0x18000b665  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b66a  lea     r8, [rsp+38h+arg_0]
0x18000b66f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b677  lea     rdx, [rsp+38h+arg_8]
0x18000b67c  mov     ebp, eax
0x18000b67e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000b683  mov     eax, [rdi]
0x18000b685  mov     rbx, [rsp+38h+arg_8]
0x18000b68a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b68f  mov     edx, eax
0x18000b691  mov     [rdi], eax
0x18000b693  mov     ecx, eax
0x18000b695  jz      short loc_18000B6B0
0x18000b697  test    dl, 2
0x18000b69a  jnz     short loc_18000B6B0
0x18000b69c  and     ecx, 0FFFFF63Eh
0x18000b6a2  mov     eax, ebx
0x18000b6a4  and     eax, 9C1h
0x18000b6a9  or      ecx, eax
0x18000b6ab  or      ecx, 2
0x18000b6ae  mov     [rdi], ecx
0x18000b6b0  mov     r8d, edx
0x18000b6b3  and     r8d, 4
0x18000b6b7  jnz     short loc_18000B6CB
0x18000b6b9  btr     ecx, 0Ah
0x18000b6bd  mov     eax, ebx
0x18000b6bf  and     eax, 400h
0x18000b6c4  or      ecx, eax
0x18000b6c6  or      ecx, 4
0x18000b6c9  mov     [rdi], ecx
0x18000b6cb  mov     eax, edx
0x18000b6cd  lock cmpxchg [rsi], ecx
0x18000b6d1  jnz     short loc_18000B68A
0x18000b6d3  test    r8d, r8d
0x18000b6d6  jnz     short loc_18000B6E8
0x18000b6d8  mov     r8d, ebp
0x18000b6db  mov     edx, 3
0x18000b6e0  mov     rcx, rsi
0x18000b6e3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b6e8  mov     eax, [rdi]
0x18000b6ea  test    al, 2
0x18000b6ec  jnz     short loc_18000B6FD
0x18000b6ee  and     eax, 0FFFFF63Eh
0x18000b6f3  and     ebx, 9C1h
0x18000b6f9  or      eax, ebx
0x18000b6fb  mov     [rdi], eax
0x18000b6fd  mov     rbx, [rsp+38h+arg_10]
0x18000b702  mov     rax, rdi
0x18000b705  add     rsp, 20h
0x18000b709  pop     rdi
0x18000b70a  pop     rsi
0x18000b70b  pop     rbp
0x18000b70c  retn
```

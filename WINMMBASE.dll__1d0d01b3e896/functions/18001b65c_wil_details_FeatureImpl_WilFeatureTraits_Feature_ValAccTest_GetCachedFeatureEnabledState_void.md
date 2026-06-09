# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b65c`
- end: `0x18001b735`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c6c0`
- `0x18001c960`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001b65c`
- `0x18001bf10`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001b65c  mov     [rsp+arg_10], rbx
0x18001b661  mov     [rsp+arg_0], rcx
0x18001b666  push    rbp
0x18001b667  push    rsi
0x18001b668  push    rdi
0x18001b669  sub     rsp, 20h
0x18001b66d  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18001b674  mov     rdi, rdx
0x18001b677  mov     qword ptr [rdx], 0
0x18001b67e  mov     eax, [rsi]
0x18001b680  mov     [rdx], eax
0x18001b682  and     eax, 6
0x18001b685  cmp     al, 6
0x18001b687  jz      loc_18001B725
0x18001b68d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b692  lea     r8, [rsp+38h+arg_0]
0x18001b697  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b69f  lea     rdx, [rsp+38h+arg_8]
0x18001b6a4  mov     ebp, eax
0x18001b6a6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18001b6ab  mov     eax, [rdi]
0x18001b6ad  mov     rbx, [rsp+38h+arg_8]
0x18001b6b2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b6b7  mov     edx, eax
0x18001b6b9  mov     [rdi], eax
0x18001b6bb  mov     ecx, eax
0x18001b6bd  jz      short loc_18001B6D8
0x18001b6bf  test    dl, 2
0x18001b6c2  jnz     short loc_18001B6D8
0x18001b6c4  and     ecx, 0FFFFF63Eh
0x18001b6ca  mov     eax, ebx
0x18001b6cc  and     eax, 9C1h
0x18001b6d1  or      ecx, eax
0x18001b6d3  or      ecx, 2
0x18001b6d6  mov     [rdi], ecx
0x18001b6d8  mov     r8d, edx
0x18001b6db  and     r8d, 4
0x18001b6df  jnz     short loc_18001B6F3
0x18001b6e1  btr     ecx, 0Ah
0x18001b6e5  mov     eax, ebx
0x18001b6e7  and     eax, 400h
0x18001b6ec  or      ecx, eax
0x18001b6ee  or      ecx, 4
0x18001b6f1  mov     [rdi], ecx
0x18001b6f3  mov     eax, edx
0x18001b6f5  lock cmpxchg [rsi], ecx
0x18001b6f9  jnz     short loc_18001B6B2
0x18001b6fb  test    r8d, r8d
0x18001b6fe  jnz     short loc_18001B710
0x18001b700  mov     r8d, ebp
0x18001b703  mov     edx, 3
0x18001b708  mov     rcx, rsi
0x18001b70b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b710  mov     eax, [rdi]
0x18001b712  test    al, 2
0x18001b714  jnz     short loc_18001B725
0x18001b716  and     eax, 0FFFFF63Eh
0x18001b71b  and     ebx, 9C1h
0x18001b721  or      eax, ebx
0x18001b723  mov     [rdi], eax
0x18001b725  mov     rbx, [rsp+38h+arg_10]
0x18001b72a  mov     rax, rdi
0x18001b72d  add     rsp, 20h
0x18001b731  pop     rdi
0x18001b732  pop     rsi
0x18001b733  pop     rbp
0x18001b734  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x1800155b8`
- end: `0x180015691`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017560`
- `0x180017dd4`

## callees

- `0x18000543c`
- `0x180008794`
- `0x1800155b8`
- `0x180015f1c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UexTest7__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800155b8  mov     [rsp+arg_10], rbx
0x1800155bd  mov     [rsp+arg_0], rcx
0x1800155c2  push    rbp
0x1800155c3  push    rsi
0x1800155c4  push    rdi
0x1800155c5  sub     rsp, 20h
0x1800155c9  mov     rsi, cs:Feature_UexTest7__descriptor
0x1800155d0  mov     rdi, rdx
0x1800155d3  mov     qword ptr [rdx], 0
0x1800155da  mov     eax, [rsi]
0x1800155dc  mov     [rdx], eax
0x1800155de  and     eax, 6
0x1800155e1  cmp     al, 6
0x1800155e3  jz      loc_180015681
0x1800155e9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800155ee  lea     r8, [rsp+38h+arg_0]
0x1800155f3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800155fb  lea     rdx, [rsp+38h+arg_8]
0x180015600  mov     ebp, eax
0x180015602  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x180015607  mov     eax, [rdi]
0x180015609  mov     rbx, [rsp+38h+arg_8]
0x18001560e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180015613  mov     edx, eax
0x180015615  mov     [rdi], eax
0x180015617  mov     ecx, eax
0x180015619  jz      short loc_180015634
0x18001561b  test    dl, 2
0x18001561e  jnz     short loc_180015634
0x180015620  and     ecx, 0FFFFF63Eh
0x180015626  mov     eax, ebx
0x180015628  and     eax, 9C1h
0x18001562d  or      ecx, eax
0x18001562f  or      ecx, 2
0x180015632  mov     [rdi], ecx
0x180015634  mov     r8d, edx
0x180015637  and     r8d, 4
0x18001563b  jnz     short loc_18001564F
0x18001563d  btr     ecx, 0Ah
0x180015641  mov     eax, ebx
0x180015643  and     eax, 400h
0x180015648  or      ecx, eax
0x18001564a  or      ecx, 4
0x18001564d  mov     [rdi], ecx
0x18001564f  mov     eax, edx
0x180015651  lock cmpxchg [rsi], ecx
0x180015655  jnz     short loc_18001560E
0x180015657  test    r8d, r8d
0x18001565a  jnz     short loc_18001566C
0x18001565c  mov     r8d, ebp
0x18001565f  mov     edx, 3
0x180015664  mov     rcx, rsi
0x180015667  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001566c  mov     eax, [rdi]
0x18001566e  test    al, 2
0x180015670  jnz     short loc_180015681
0x180015672  and     eax, 0FFFFF63Eh
0x180015677  and     ebx, 9C1h
0x18001567d  or      eax, ebx
0x18001567f  mov     [rdi], eax
0x180015681  mov     rbx, [rsp+38h+arg_10]
0x180015686  mov     rax, rdi
0x180015689  add     rsp, 20h
0x18001568d  pop     rdi
0x18001568e  pop     rsi
0x18001568f  pop     rbp
0x180015690  retn
```

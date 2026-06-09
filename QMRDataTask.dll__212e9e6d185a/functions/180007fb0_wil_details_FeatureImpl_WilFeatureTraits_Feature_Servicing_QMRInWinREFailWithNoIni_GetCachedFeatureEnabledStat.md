# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetCachedFeatureEnabledState(void)

- ea: `0x180007fb0`
- end: `0x180008089`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011840`

## callees

- `0x18000787c`
- `0x180007fb0`
- `0x180008dd0`
- `0x180010684`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_QMRInWinREFailWithNoIni__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_QMRInWinREFailWithNoIni__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetCurrentFeatureEnabledState(
      v5,
      &v11);
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
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_QMRInWinREFailWithNoIni__descriptor,
             v9,
             v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_QMRInWinREFailWithNoIni__descriptor,
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
0x180007fb0  mov     [rsp+arg_10], rbx
0x180007fb5  mov     [rsp+arg_0], rcx
0x180007fba  push    rbp
0x180007fbb  push    rsi
0x180007fbc  push    rdi
0x180007fbd  sub     rsp, 20h
0x180007fc1  mov     rsi, cs:Feature_Servicing_QMRInWinREFailWithNoIni__descriptor
0x180007fc8  mov     rdi, rdx
0x180007fcb  mov     qword ptr [rdx], 0
0x180007fd2  mov     eax, [rsi]
0x180007fd4  mov     [rdx], eax
0x180007fd6  and     eax, 6
0x180007fd9  cmp     al, 6
0x180007fdb  jz      loc_180008079
0x180007fe1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007fe6  lea     r8, [rsp+38h+arg_0]
0x180007feb  mov     dword ptr [rsp+38h+arg_0], 0
0x180007ff3  lea     rdx, [rsp+38h+arg_8]
0x180007ff8  mov     ebp, eax
0x180007ffa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetCurrentFeatureEnabledState(int *)
0x180007fff  mov     eax, [rdi]
0x180008001  mov     rbx, [rsp+38h+arg_8]
0x180008006  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000800b  mov     edx, eax
0x18000800d  mov     [rdi], eax
0x18000800f  mov     ecx, eax
0x180008011  jz      short loc_18000802C
0x180008013  test    dl, 2
0x180008016  jnz     short loc_18000802C
0x180008018  and     ecx, 0FFFFF63Eh
0x18000801e  mov     eax, ebx
0x180008020  and     eax, 9C1h
0x180008025  or      ecx, eax
0x180008027  or      ecx, 2
0x18000802a  mov     [rdi], ecx
0x18000802c  mov     r8d, edx
0x18000802f  and     r8d, 4
0x180008033  jnz     short loc_180008047
0x180008035  btr     ecx, 0Ah
0x180008039  mov     eax, ebx
0x18000803b  and     eax, 400h
0x180008040  or      ecx, eax
0x180008042  or      ecx, 4
0x180008045  mov     [rdi], ecx
0x180008047  mov     eax, edx
0x180008049  lock cmpxchg [rsi], ecx
0x18000804d  jnz     short loc_180008006
0x18000804f  test    r8d, r8d
0x180008052  jnz     short loc_180008064
0x180008054  mov     r8d, ebp
0x180008057  mov     edx, 3
0x18000805c  mov     rcx, rsi
0x18000805f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008064  mov     eax, [rdi]
0x180008066  test    al, 2
0x180008068  jnz     short loc_180008079
0x18000806a  and     eax, 0FFFFF63Eh
0x18000806f  and     ebx, 9C1h
0x180008075  or      eax, ebx
0x180008077  mov     [rdi], eax
0x180008079  mov     rbx, [rsp+38h+arg_10]
0x18000807e  mov     rax, rdi
0x180008081  add     rsp, 20h
0x180008085  pop     rdi
0x180008086  pop     rsi
0x180008087  pop     rbp
0x180008088  retn
```

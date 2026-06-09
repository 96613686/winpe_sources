# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetCachedFeatureEnabledState(void)

- ea: `0x180008918`
- end: `0x1800089f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a424`
- `0x18000b2d4`

## callees

- `0x1800085b4`
- `0x180008918`
- `0x180008d78`
- `0x18000ab04`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_SCCRedirectionTrustPolicy__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SCCRedirectionTrustPolicy__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_SCCRedirectionTrustPolicy__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_SCCRedirectionTrustPolicy__descriptor,
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
0x180008918  mov     [rsp+arg_10], rbx
0x18000891d  mov     [rsp+arg_0], rcx
0x180008922  push    rbp
0x180008923  push    rsi
0x180008924  push    rdi
0x180008925  sub     rsp, 20h
0x180008929  mov     rsi, cs:Feature_SCCRedirectionTrustPolicy__descriptor
0x180008930  mov     rdi, rdx
0x180008933  mov     qword ptr [rdx], 0
0x18000893a  mov     eax, [rsi]
0x18000893c  mov     [rdx], eax
0x18000893e  and     eax, 6
0x180008941  cmp     al, 6
0x180008943  jz      loc_1800089E1
0x180008949  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000894e  lea     r8, [rsp+38h+arg_0]
0x180008953  mov     dword ptr [rsp+38h+arg_0], 0
0x18000895b  lea     rdx, [rsp+38h+arg_8]
0x180008960  mov     ebp, eax
0x180008962  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetCurrentFeatureEnabledState(int *)
0x180008967  mov     eax, [rdi]
0x180008969  mov     rbx, [rsp+38h+arg_8]
0x18000896e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008973  mov     edx, eax
0x180008975  mov     [rdi], eax
0x180008977  mov     ecx, eax
0x180008979  jz      short loc_180008994
0x18000897b  test    dl, 2
0x18000897e  jnz     short loc_180008994
0x180008980  and     ecx, 0FFFFF63Eh
0x180008986  mov     eax, ebx
0x180008988  and     eax, 9C1h
0x18000898d  or      ecx, eax
0x18000898f  or      ecx, 2
0x180008992  mov     [rdi], ecx
0x180008994  mov     r8d, edx
0x180008997  and     r8d, 4
0x18000899b  jnz     short loc_1800089AF
0x18000899d  btr     ecx, 0Ah
0x1800089a1  mov     eax, ebx
0x1800089a3  and     eax, 400h
0x1800089a8  or      ecx, eax
0x1800089aa  or      ecx, 4
0x1800089ad  mov     [rdi], ecx
0x1800089af  mov     eax, edx
0x1800089b1  lock cmpxchg [rsi], ecx
0x1800089b5  jnz     short loc_18000896E
0x1800089b7  test    r8d, r8d
0x1800089ba  jnz     short loc_1800089CC
0x1800089bc  mov     r8d, ebp
0x1800089bf  mov     edx, 3
0x1800089c4  mov     rcx, rsi
0x1800089c7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800089cc  mov     eax, [rdi]
0x1800089ce  test    al, 2
0x1800089d0  jnz     short loc_1800089E1
0x1800089d2  and     eax, 0FFFFF63Eh
0x1800089d7  and     ebx, 9C1h
0x1800089dd  or      eax, ebx
0x1800089df  mov     [rdi], eax
0x1800089e1  mov     rbx, [rsp+38h+arg_10]
0x1800089e6  mov     rax, rdi
0x1800089e9  add     rsp, 20h
0x1800089ed  pop     rdi
0x1800089ee  pop     rsi
0x1800089ef  pop     rbp
0x1800089f0  retn
```

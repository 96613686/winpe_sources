# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x180017234`
- end: `0x18001731f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b04c`
- `0x180021b30`

## callees

- `0x180003520`
- `0x180016060`
- `0x180017234`
- `0x18001777c`
- `0x18001c760`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v5,
      &v12,
      &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxAccOptimization__descriptor, 3, v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180017234  push    rbx
0x180017236  push    rbp
0x180017237  push    rsi
0x180017238  push    rdi
0x180017239  sub     rsp, 48h
0x18001723d  mov     rax, cs:__security_cookie
0x180017244  xor     rax, rsp
0x180017247  mov     [rsp+68h+var_38], rax
0x18001724c  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x180017253  mov     rdi, rdx
0x180017256  mov     qword ptr [rdx], 0
0x18001725d  mov     eax, [rsi]
0x18001725f  mov     [rdx], eax
0x180017261  and     eax, 6
0x180017264  cmp     al, 6
0x180017266  jz      loc_180017306
0x18001726c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180017271  lea     r8, [rsp+68h+var_40]
0x180017276  mov     [rsp+68h+var_40], 0
0x18001727e  lea     rdx, [rsp+68h+var_48]
0x180017283  mov     ebp, eax
0x180017285  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18001728a  mov     eax, [rdi]
0x18001728c  mov     rbx, [rsp+68h+var_48]
0x180017291  cmp     [rsp+68h+var_40], 0
0x180017296  mov     edx, eax
0x180017298  mov     [rdi], eax
0x18001729a  mov     ecx, eax
0x18001729c  jz      short loc_1800172B7
0x18001729e  test    dl, 2
0x1800172a1  jnz     short loc_1800172B7
0x1800172a3  and     ecx, 0FFFFF63Eh
0x1800172a9  mov     eax, ebx
0x1800172ab  and     eax, 9C1h
0x1800172b0  or      ecx, eax
0x1800172b2  or      ecx, 2
0x1800172b5  mov     [rdi], ecx
0x1800172b7  mov     r8d, edx
0x1800172ba  and     r8d, 4
0x1800172be  jnz     short loc_1800172D2
0x1800172c0  btr     ecx, 0Ah
0x1800172c4  mov     eax, ebx
0x1800172c6  and     eax, 400h
0x1800172cb  or      ecx, eax
0x1800172cd  or      ecx, 4
0x1800172d0  mov     [rdi], ecx
0x1800172d2  mov     eax, edx
0x1800172d4  lock cmpxchg [rsi], ecx
0x1800172d8  jnz     short loc_180017291
0x1800172da  test    r8d, r8d
0x1800172dd  jnz     short loc_1800172EF
0x1800172df  mov     r8d, ebp
0x1800172e2  mov     edx, 3
0x1800172e7  mov     rcx, rsi
0x1800172ea  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800172ef  mov     ecx, [rdi]
0x1800172f1  test    cl, 2
0x1800172f4  jnz     short loc_180017306
0x1800172f6  and     ecx, 0FFFFF63Eh
0x1800172fc  and     ebx, 9C1h
0x180017302  or      ecx, ebx
0x180017304  mov     [rdi], ecx
0x180017306  mov     rax, rdi
0x180017309  mov     rcx, [rsp+68h+var_38]
0x18001730e  xor     rcx, rsp; StackCookie
0x180017311  call    __security_check_cookie
0x180017316  add     rsp, 48h
0x18001731a  pop     rdi
0x18001731b  pop     rsi
0x18001731c  pop     rbp
0x18001731d  pop     rbx
0x18001731e  retn
```

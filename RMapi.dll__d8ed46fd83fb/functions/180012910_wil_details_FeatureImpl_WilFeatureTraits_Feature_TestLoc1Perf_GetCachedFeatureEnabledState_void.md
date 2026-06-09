# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180012910`
- end: `0x1800129fb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015290`
- `0x180016abc`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180012910`
- `0x180012f18`
- `0x180016180`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
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
0x180012910  push    rbx
0x180012912  push    rbp
0x180012913  push    rsi
0x180012914  push    rdi
0x180012915  sub     rsp, 48h
0x180012919  mov     rax, cs:__security_cookie
0x180012920  xor     rax, rsp
0x180012923  mov     [rsp+68h+var_38], rax
0x180012928  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18001292f  mov     rdi, rdx
0x180012932  mov     qword ptr [rdx], 0
0x180012939  mov     eax, [rsi]
0x18001293b  mov     [rdx], eax
0x18001293d  and     eax, 6
0x180012940  cmp     al, 6
0x180012942  jz      loc_1800129E2
0x180012948  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001294d  lea     r8, [rsp+68h+var_40]
0x180012952  mov     [rsp+68h+var_40], 0
0x18001295a  lea     rdx, [rsp+68h+var_48]
0x18001295f  mov     ebp, eax
0x180012961  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180012966  mov     eax, [rdi]
0x180012968  mov     rbx, [rsp+68h+var_48]
0x18001296d  cmp     [rsp+68h+var_40], 0
0x180012972  mov     edx, eax
0x180012974  mov     [rdi], eax
0x180012976  mov     ecx, eax
0x180012978  jz      short loc_180012993
0x18001297a  test    dl, 2
0x18001297d  jnz     short loc_180012993
0x18001297f  and     ecx, 0FFFFF63Eh
0x180012985  mov     eax, ebx
0x180012987  and     eax, 9C1h
0x18001298c  or      ecx, eax
0x18001298e  or      ecx, 2
0x180012991  mov     [rdi], ecx
0x180012993  mov     r8d, edx
0x180012996  and     r8d, 4
0x18001299a  jnz     short loc_1800129AE
0x18001299c  btr     ecx, 0Ah
0x1800129a0  mov     eax, ebx
0x1800129a2  and     eax, 400h
0x1800129a7  or      ecx, eax
0x1800129a9  or      ecx, 4
0x1800129ac  mov     [rdi], ecx
0x1800129ae  mov     eax, edx
0x1800129b0  lock cmpxchg [rsi], ecx
0x1800129b4  jnz     short loc_18001296D
0x1800129b6  test    r8d, r8d
0x1800129b9  jnz     short loc_1800129CB
0x1800129bb  mov     r8d, ebp
0x1800129be  mov     edx, 3
0x1800129c3  mov     rcx, rsi
0x1800129c6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800129cb  mov     ecx, [rdi]
0x1800129cd  test    cl, 2
0x1800129d0  jnz     short loc_1800129E2
0x1800129d2  and     ecx, 0FFFFF63Eh
0x1800129d8  and     ebx, 9C1h
0x1800129de  or      ecx, ebx
0x1800129e0  mov     [rdi], ecx
0x1800129e2  mov     rax, rdi
0x1800129e5  mov     rcx, [rsp+68h+var_38]
0x1800129ea  xor     rcx, rsp; StackCookie
0x1800129ed  call    __security_check_cookie
0x1800129f2  add     rsp, 48h
0x1800129f6  pop     rdi
0x1800129f7  pop     rsi
0x1800129f8  pop     rbp
0x1800129f9  pop     rbx
0x1800129fa  retn
```

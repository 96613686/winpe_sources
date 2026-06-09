# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606323>::GetCachedFeatureEnabledState(void)

- ea: `0x1800148f4`
- end: `0x1800149d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57606323@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001adc8`
- `0x18001ce08`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x1800148f4`
- `0x180016ba8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606323>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_57606323__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57606323__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606323>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57606323__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_57606323__descriptor,
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
0x1800148f4  mov     [rsp+arg_10], rbx
0x1800148f9  mov     [rsp+arg_0], rcx
0x1800148fe  push    rbp
0x1800148ff  push    rsi
0x180014900  push    rdi
0x180014901  sub     rsp, 20h
0x180014905  mov     rsi, cs:Feature_57606323__descriptor
0x18001490c  mov     rdi, rdx
0x18001490f  mov     qword ptr [rdx], 0
0x180014916  mov     eax, [rsi]
0x180014918  mov     [rdx], eax
0x18001491a  and     eax, 6
0x18001491d  cmp     al, 6
0x18001491f  jz      loc_1800149C5
0x180014925  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001492a  lea     r8, [rsp+38h+arg_0]
0x18001492f  mov     dword ptr [rsp+38h+arg_0], 0
0x180014937  lea     rdx, [rsp+38h+arg_8]
0x18001493c  mov     ebp, eax
0x18001493e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57606323@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606323>::GetCurrentFeatureEnabledState(int *)
0x180014943  mov     eax, [rdi]
0x180014945  mov     rbx, [rsp+38h+arg_8]
0x18001494a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001494f  mov     edx, eax
0x180014951  mov     [rdi], eax
0x180014953  mov     ecx, eax
0x180014955  jz      short loc_180014970
0x180014957  test    dl, 2
0x18001495a  jnz     short loc_180014970
0x18001495c  and     ecx, 0FFFFF63Eh
0x180014962  mov     eax, ebx
0x180014964  and     eax, 9C1h
0x180014969  or      ecx, eax
0x18001496b  or      ecx, 2
0x18001496e  mov     [rdi], ecx
0x180014970  mov     r8d, edx
0x180014973  and     r8d, 4
0x180014977  jnz     short loc_18001498B
0x180014979  btr     ecx, 0Ah
0x18001497d  mov     eax, ebx
0x18001497f  and     eax, 400h
0x180014984  or      ecx, eax
0x180014986  or      ecx, 4
0x180014989  mov     [rdi], ecx
0x18001498b  mov     eax, edx
0x18001498d  lock cmpxchg [rsi], ecx
0x180014991  jnz     short loc_18001494A
0x180014993  test    r8d, r8d
0x180014996  jnz     short loc_1800149B0
0x180014998  mov     r9d, ebp
0x18001499b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800149a2  mov     r8d, 3
0x1800149a8  mov     rdx, rsi
0x1800149ab  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800149b0  mov     eax, [rdi]
0x1800149b2  test    al, 2
0x1800149b4  jnz     short loc_1800149C5
0x1800149b6  and     eax, 0FFFFF63Eh
0x1800149bb  and     ebx, 9C1h
0x1800149c1  or      eax, ebx
0x1800149c3  mov     [rdi], eax
0x1800149c5  mov     rbx, [rsp+38h+arg_10]
0x1800149ca  mov     rax, rdi
0x1800149cd  add     rsp, 20h
0x1800149d1  pop     rdi
0x1800149d2  pop     rsi
0x1800149d3  pop     rbp
0x1800149d4  retn
```

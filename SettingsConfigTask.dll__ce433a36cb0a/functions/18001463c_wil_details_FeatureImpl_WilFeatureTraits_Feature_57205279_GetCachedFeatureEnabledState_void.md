# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57205279>::GetCachedFeatureEnabledState(void)

- ea: `0x18001463c`
- end: `0x18001471d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57205279@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ac18`
- `0x18001cd10`
- `0x18001cd50`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x18001463c`
- `0x180016944`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57205279>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_57205279__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57205279__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57205279>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57205279__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_57205279__descriptor,
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
0x18001463c  mov     [rsp+arg_10], rbx
0x180014641  mov     [rsp+arg_0], rcx
0x180014646  push    rbp
0x180014647  push    rsi
0x180014648  push    rdi
0x180014649  sub     rsp, 20h
0x18001464d  mov     rsi, cs:Feature_57205279__descriptor
0x180014654  mov     rdi, rdx
0x180014657  mov     qword ptr [rdx], 0
0x18001465e  mov     eax, [rsi]
0x180014660  mov     [rdx], eax
0x180014662  and     eax, 6
0x180014665  cmp     al, 6
0x180014667  jz      loc_18001470D
0x18001466d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014672  lea     r8, [rsp+38h+arg_0]
0x180014677  mov     dword ptr [rsp+38h+arg_0], 0
0x18001467f  lea     rdx, [rsp+38h+arg_8]
0x180014684  mov     ebp, eax
0x180014686  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57205279@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57205279>::GetCurrentFeatureEnabledState(int *)
0x18001468b  mov     eax, [rdi]
0x18001468d  mov     rbx, [rsp+38h+arg_8]
0x180014692  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014697  mov     edx, eax
0x180014699  mov     [rdi], eax
0x18001469b  mov     ecx, eax
0x18001469d  jz      short loc_1800146B8
0x18001469f  test    dl, 2
0x1800146a2  jnz     short loc_1800146B8
0x1800146a4  and     ecx, 0FFFFF63Eh
0x1800146aa  mov     eax, ebx
0x1800146ac  and     eax, 9C1h
0x1800146b1  or      ecx, eax
0x1800146b3  or      ecx, 2
0x1800146b6  mov     [rdi], ecx
0x1800146b8  mov     r8d, edx
0x1800146bb  and     r8d, 4
0x1800146bf  jnz     short loc_1800146D3
0x1800146c1  btr     ecx, 0Ah
0x1800146c5  mov     eax, ebx
0x1800146c7  and     eax, 400h
0x1800146cc  or      ecx, eax
0x1800146ce  or      ecx, 4
0x1800146d1  mov     [rdi], ecx
0x1800146d3  mov     eax, edx
0x1800146d5  lock cmpxchg [rsi], ecx
0x1800146d9  jnz     short loc_180014692
0x1800146db  test    r8d, r8d
0x1800146de  jnz     short loc_1800146F8
0x1800146e0  mov     r9d, ebp
0x1800146e3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800146ea  mov     r8d, 3
0x1800146f0  mov     rdx, rsi
0x1800146f3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800146f8  mov     eax, [rdi]
0x1800146fa  test    al, 2
0x1800146fc  jnz     short loc_18001470D
0x1800146fe  and     eax, 0FFFFF63Eh
0x180014703  and     ebx, 9C1h
0x180014709  or      eax, ebx
0x18001470b  mov     [rdi], eax
0x18001470d  mov     rbx, [rsp+38h+arg_10]
0x180014712  mov     rax, rdi
0x180014715  add     rsp, 20h
0x180014719  pop     rdi
0x18001471a  pop     rsi
0x18001471b  pop     rbp
0x18001471c  retn
```

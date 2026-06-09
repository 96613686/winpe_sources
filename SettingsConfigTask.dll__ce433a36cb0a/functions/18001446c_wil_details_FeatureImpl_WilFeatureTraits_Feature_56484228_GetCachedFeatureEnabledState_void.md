# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56484228>::GetCachedFeatureEnabledState(void)

- ea: `0x18001446c`
- end: `0x18001454d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56484228@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ab00`
- `0x18001cc98`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x18001446c`
- `0x1800167b0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56484228>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_56484228__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56484228__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56484228>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56484228__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_56484228__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001446c  mov     [rsp+arg_10], rbx
0x180014471  mov     [rsp+arg_0], rcx
0x180014476  push    rbp
0x180014477  push    rsi
0x180014478  push    rdi
0x180014479  sub     rsp, 20h
0x18001447d  mov     rsi, cs:Feature_56484228__descriptor
0x180014484  mov     rdi, rdx
0x180014487  mov     qword ptr [rdx], 0
0x18001448e  mov     eax, [rsi]
0x180014490  mov     [rdx], eax
0x180014492  and     eax, 6
0x180014495  cmp     al, 6
0x180014497  jz      loc_18001453D
0x18001449d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800144a2  lea     r8, [rsp+38h+arg_0]
0x1800144a7  mov     dword ptr [rsp+38h+arg_0], 0
0x1800144af  lea     rdx, [rsp+38h+arg_8]
0x1800144b4  mov     ebp, eax
0x1800144b6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56484228@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56484228>::GetCurrentFeatureEnabledState(int *)
0x1800144bb  mov     eax, [rdi]
0x1800144bd  mov     rbx, [rsp+38h+arg_8]
0x1800144c2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800144c7  mov     edx, eax
0x1800144c9  mov     [rdi], eax
0x1800144cb  mov     ecx, eax
0x1800144cd  jz      short loc_1800144E8
0x1800144cf  test    dl, 2
0x1800144d2  jnz     short loc_1800144E8
0x1800144d4  and     ecx, 0FFFFF63Eh
0x1800144da  mov     eax, ebx
0x1800144dc  and     eax, 9C1h
0x1800144e1  or      ecx, eax
0x1800144e3  or      ecx, 2
0x1800144e6  mov     [rdi], ecx
0x1800144e8  mov     r8d, edx
0x1800144eb  and     r8d, 4
0x1800144ef  jnz     short loc_180014503
0x1800144f1  btr     ecx, 0Ah
0x1800144f5  mov     eax, ebx
0x1800144f7  and     eax, 400h
0x1800144fc  or      ecx, eax
0x1800144fe  or      ecx, 4
0x180014501  mov     [rdi], ecx
0x180014503  mov     eax, edx
0x180014505  lock cmpxchg [rsi], ecx
0x180014509  jnz     short loc_1800144C2
0x18001450b  test    r8d, r8d
0x18001450e  jnz     short loc_180014528
0x180014510  mov     r9d, ebp
0x180014513  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001451a  mov     r8d, 1
0x180014520  mov     rdx, rsi
0x180014523  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014528  mov     eax, [rdi]
0x18001452a  test    al, 2
0x18001452c  jnz     short loc_18001453D
0x18001452e  and     eax, 0FFFFF63Eh
0x180014533  and     ebx, 9C1h
0x180014539  or      eax, ebx
0x18001453b  mov     [rdi], eax
0x18001453d  mov     rbx, [rsp+38h+arg_10]
0x180014542  mov     rax, rdi
0x180014545  add     rsp, 20h
0x180014549  pop     rdi
0x18001454a  pop     rsi
0x18001454b  pop     rbp
0x18001454c  retn
```

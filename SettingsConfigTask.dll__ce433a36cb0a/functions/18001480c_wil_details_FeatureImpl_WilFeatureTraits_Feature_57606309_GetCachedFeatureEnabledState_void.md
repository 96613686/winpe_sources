# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606309>::GetCachedFeatureEnabledState(void)

- ea: `0x18001480c`
- end: `0x1800148ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57606309@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ad3c`
- `0x18001cdcc`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x18001480c`
- `0x180016adc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606309>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_57606309__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57606309__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606309>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57606309__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_57606309__descriptor,
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
0x18001480c  mov     [rsp+arg_10], rbx
0x180014811  mov     [rsp+arg_0], rcx
0x180014816  push    rbp
0x180014817  push    rsi
0x180014818  push    rdi
0x180014819  sub     rsp, 20h
0x18001481d  mov     rsi, cs:Feature_57606309__descriptor
0x180014824  mov     rdi, rdx
0x180014827  mov     qword ptr [rdx], 0
0x18001482e  mov     eax, [rsi]
0x180014830  mov     [rdx], eax
0x180014832  and     eax, 6
0x180014835  cmp     al, 6
0x180014837  jz      loc_1800148DD
0x18001483d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014842  lea     r8, [rsp+38h+arg_0]
0x180014847  mov     dword ptr [rsp+38h+arg_0], 0
0x18001484f  lea     rdx, [rsp+38h+arg_8]
0x180014854  mov     ebp, eax
0x180014856  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57606309@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606309>::GetCurrentFeatureEnabledState(int *)
0x18001485b  mov     eax, [rdi]
0x18001485d  mov     rbx, [rsp+38h+arg_8]
0x180014862  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014867  mov     edx, eax
0x180014869  mov     [rdi], eax
0x18001486b  mov     ecx, eax
0x18001486d  jz      short loc_180014888
0x18001486f  test    dl, 2
0x180014872  jnz     short loc_180014888
0x180014874  and     ecx, 0FFFFF63Eh
0x18001487a  mov     eax, ebx
0x18001487c  and     eax, 9C1h
0x180014881  or      ecx, eax
0x180014883  or      ecx, 2
0x180014886  mov     [rdi], ecx
0x180014888  mov     r8d, edx
0x18001488b  and     r8d, 4
0x18001488f  jnz     short loc_1800148A3
0x180014891  btr     ecx, 0Ah
0x180014895  mov     eax, ebx
0x180014897  and     eax, 400h
0x18001489c  or      ecx, eax
0x18001489e  or      ecx, 4
0x1800148a1  mov     [rdi], ecx
0x1800148a3  mov     eax, edx
0x1800148a5  lock cmpxchg [rsi], ecx
0x1800148a9  jnz     short loc_180014862
0x1800148ab  test    r8d, r8d
0x1800148ae  jnz     short loc_1800148C8
0x1800148b0  mov     r9d, ebp
0x1800148b3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800148ba  mov     r8d, 3
0x1800148c0  mov     rdx, rsi
0x1800148c3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800148c8  mov     eax, [rdi]
0x1800148ca  test    al, 2
0x1800148cc  jnz     short loc_1800148DD
0x1800148ce  and     eax, 0FFFFF63Eh
0x1800148d3  and     ebx, 9C1h
0x1800148d9  or      eax, ebx
0x1800148db  mov     [rdi], eax
0x1800148dd  mov     rbx, [rsp+38h+arg_10]
0x1800148e2  mov     rax, rdi
0x1800148e5  add     rsp, 20h
0x1800148e9  pop     rdi
0x1800148ea  pop     rsi
0x1800148eb  pop     rbp
0x1800148ec  retn
```

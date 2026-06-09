# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::GetCachedFeatureEnabledState(void)

- ea: `0x180014a00`
- end: `0x180014ae1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018764`

## callees

- `0x1800144a4`
- `0x180014a00`
- `0x180014dcc`
- `0x18001b084`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CloudStore__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CloudStore__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CloudStore__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_CloudStore__descriptor,
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
0x180014a00  mov     [rsp+arg_10], rbx
0x180014a05  mov     [rsp+arg_0], rcx
0x180014a0a  push    rbp
0x180014a0b  push    rsi
0x180014a0c  push    rdi
0x180014a0d  sub     rsp, 20h
0x180014a11  mov     rsi, cs:Feature_CloudStore__descriptor
0x180014a18  mov     rdi, rdx
0x180014a1b  mov     qword ptr [rdx], 0
0x180014a22  mov     eax, [rsi]
0x180014a24  mov     [rdx], eax
0x180014a26  and     eax, 6
0x180014a29  cmp     al, 6
0x180014a2b  jz      loc_180014AD1
0x180014a31  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014a36  lea     r8, [rsp+38h+arg_0]
0x180014a3b  mov     dword ptr [rsp+38h+arg_0], 0
0x180014a43  lea     rdx, [rsp+38h+arg_8]
0x180014a48  mov     ebp, eax
0x180014a4a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::GetCurrentFeatureEnabledState(int *)
0x180014a4f  mov     eax, [rdi]
0x180014a51  mov     rbx, [rsp+38h+arg_8]
0x180014a56  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014a5b  mov     edx, eax
0x180014a5d  mov     [rdi], eax
0x180014a5f  mov     ecx, eax
0x180014a61  jz      short loc_180014A7C
0x180014a63  test    dl, 2
0x180014a66  jnz     short loc_180014A7C
0x180014a68  and     ecx, 0FFFFF63Eh
0x180014a6e  mov     eax, ebx
0x180014a70  and     eax, 9C1h
0x180014a75  or      ecx, eax
0x180014a77  or      ecx, 2
0x180014a7a  mov     [rdi], ecx
0x180014a7c  mov     r8d, edx
0x180014a7f  and     r8d, 4
0x180014a83  jnz     short loc_180014A97
0x180014a85  btr     ecx, 0Ah
0x180014a89  mov     eax, ebx
0x180014a8b  and     eax, 400h
0x180014a90  or      ecx, eax
0x180014a92  or      ecx, 4
0x180014a95  mov     [rdi], ecx
0x180014a97  mov     eax, edx
0x180014a99  lock cmpxchg [rsi], ecx
0x180014a9d  jnz     short loc_180014A56
0x180014a9f  test    r8d, r8d
0x180014aa2  jnz     short loc_180014ABC
0x180014aa4  mov     r9d, ebp
0x180014aa7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014aae  mov     r8d, 3
0x180014ab4  mov     rdx, rsi
0x180014ab7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014abc  mov     eax, [rdi]
0x180014abe  test    al, 2
0x180014ac0  jnz     short loc_180014AD1
0x180014ac2  and     eax, 0FFFFF63Eh
0x180014ac7  and     ebx, 9C1h
0x180014acd  or      eax, ebx
0x180014acf  mov     [rdi], eax
0x180014ad1  mov     rbx, [rsp+38h+arg_10]
0x180014ad6  mov     rax, rdi
0x180014ad9  add     rsp, 20h
0x180014add  pop     rdi
0x180014ade  pop     rsi
0x180014adf  pop     rbp
0x180014ae0  retn
```

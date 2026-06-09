# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCachedFeatureEnabledState(void)

- ea: `0x1800594fc`
- end: `0x1800595de`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c128`
- `0x18005cb44`

## callees

- `0x180048c10`
- `0x1800594fc`
- `0x18005aca4`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MediaQI2511__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MediaQI2511__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MediaQI2511__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_MediaQI2511__descriptor,
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
0x1800594fc  mov     [rsp+arg_10], rbx
0x180059501  mov     [rsp+arg_0], rcx
0x180059506  push    rbp
0x180059507  push    rsi
0x180059508  push    rdi
0x180059509  sub     rsp, 20h
0x18005950d  mov     rsi, cs:Feature_MediaQI2511__descriptor
0x180059514  mov     rdi, rdx
0x180059517  mov     qword ptr [rdx], 0
0x18005951e  mov     eax, [rsi]
0x180059520  mov     [rdx], eax
0x180059522  and     eax, 6
0x180059525  cmp     al, 6
0x180059527  jz      loc_1800595CD
0x18005952d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180059532  lea     r8, [rsp+38h+arg_0]
0x180059537  mov     dword ptr [rsp+38h+arg_0], 0
0x18005953f  lea     rdx, [rsp+38h+arg_8]
0x180059544  mov     ebp, eax
0x180059546  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCurrentFeatureEnabledState(int *)
0x18005954b  mov     eax, [rdi]
0x18005954d  mov     rbx, [rsp+38h+arg_8]
0x180059552  cmp     dword ptr [rsp+38h+arg_0], 0
0x180059557  mov     edx, eax
0x180059559  mov     [rdi], eax
0x18005955b  mov     ecx, eax
0x18005955d  jz      short loc_180059578
0x18005955f  test    dl, 2
0x180059562  jnz     short loc_180059578
0x180059564  and     ecx, 0FFFFF63Eh
0x18005956a  mov     eax, ebx
0x18005956c  and     eax, 9C1h
0x180059571  or      ecx, eax
0x180059573  or      ecx, 2
0x180059576  mov     [rdi], ecx
0x180059578  mov     r8d, edx
0x18005957b  and     r8d, 4
0x18005957f  jnz     short loc_180059593
0x180059581  btr     ecx, 0Ah
0x180059585  mov     eax, ebx
0x180059587  and     eax, 400h
0x18005958c  or      ecx, eax
0x18005958e  or      ecx, 4
0x180059591  mov     [rdi], ecx
0x180059593  mov     eax, edx
0x180059595  lock cmpxchg [rsi], ecx
0x180059599  jnz     short loc_180059552
0x18005959b  test    r8d, r8d
0x18005959e  jnz     short loc_1800595B8
0x1800595a0  mov     r9d, ebp
0x1800595a3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800595aa  mov     r8d, 3
0x1800595b0  mov     rdx, rsi
0x1800595b3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800595b8  mov     eax, [rdi]
0x1800595ba  test    al, 2
0x1800595bc  jnz     short loc_1800595CD
0x1800595be  and     eax, 0FFFFF63Eh
0x1800595c3  and     ebx, 9C1h
0x1800595c9  or      eax, ebx
0x1800595cb  mov     [rdi], eax
0x1800595cd  mov     rbx, [rsp+38h+arg_10]
0x1800595d2  mov     rax, rdi
0x1800595d5  add     rsp, 20h
0x1800595d9  pop     rdi
0x1800595da  pop     rsi
0x1800595db  pop     rbp
0x1800595dc  retn
```

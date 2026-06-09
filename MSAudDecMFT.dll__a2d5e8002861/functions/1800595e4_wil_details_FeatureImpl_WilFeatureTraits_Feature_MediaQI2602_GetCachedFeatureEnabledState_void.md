# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCachedFeatureEnabledState(void)

- ea: `0x1800595e4`
- end: `0x1800596c6`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c1b4`
- `0x18005cb80`

## callees

- `0x180048c10`
- `0x180049178`
- `0x1800595e4`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MediaQI2602__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MediaQI2602__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MediaQI2602__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_MediaQI2602__descriptor,
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
0x1800595e4  mov     [rsp+arg_10], rbx
0x1800595e9  mov     [rsp+arg_0], rcx
0x1800595ee  push    rbp
0x1800595ef  push    rsi
0x1800595f0  push    rdi
0x1800595f1  sub     rsp, 20h
0x1800595f5  mov     rsi, cs:Feature_MediaQI2602__descriptor
0x1800595fc  mov     rdi, rdx
0x1800595ff  mov     qword ptr [rdx], 0
0x180059606  mov     eax, [rsi]
0x180059608  mov     [rdx], eax
0x18005960a  and     eax, 6
0x18005960d  cmp     al, 6
0x18005960f  jz      loc_1800596B5
0x180059615  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18005961a  lea     r8, [rsp+38h+arg_0]
0x18005961f  mov     dword ptr [rsp+38h+arg_0], 0
0x180059627  lea     rdx, [rsp+38h+arg_8]
0x18005962c  mov     ebp, eax
0x18005962e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(int *)
0x180059633  mov     eax, [rdi]
0x180059635  mov     rbx, [rsp+38h+arg_8]
0x18005963a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18005963f  mov     edx, eax
0x180059641  mov     [rdi], eax
0x180059643  mov     ecx, eax
0x180059645  jz      short loc_180059660
0x180059647  test    dl, 2
0x18005964a  jnz     short loc_180059660
0x18005964c  and     ecx, 0FFFFF63Eh
0x180059652  mov     eax, ebx
0x180059654  and     eax, 9C1h
0x180059659  or      ecx, eax
0x18005965b  or      ecx, 2
0x18005965e  mov     [rdi], ecx
0x180059660  mov     r8d, edx
0x180059663  and     r8d, 4
0x180059667  jnz     short loc_18005967B
0x180059669  btr     ecx, 0Ah
0x18005966d  mov     eax, ebx
0x18005966f  and     eax, 400h
0x180059674  or      ecx, eax
0x180059676  or      ecx, 4
0x180059679  mov     [rdi], ecx
0x18005967b  mov     eax, edx
0x18005967d  lock cmpxchg [rsi], ecx
0x180059681  jnz     short loc_18005963A
0x180059683  test    r8d, r8d
0x180059686  jnz     short loc_1800596A0
0x180059688  mov     r9d, ebp
0x18005968b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059692  mov     r8d, 3
0x180059698  mov     rdx, rsi
0x18005969b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800596a0  mov     eax, [rdi]
0x1800596a2  test    al, 2
0x1800596a4  jnz     short loc_1800596B5
0x1800596a6  and     eax, 0FFFFF63Eh
0x1800596ab  and     ebx, 9C1h
0x1800596b1  or      eax, ebx
0x1800596b3  mov     [rdi], eax
0x1800596b5  mov     rbx, [rsp+38h+arg_10]
0x1800596ba  mov     rax, rdi
0x1800596bd  add     rsp, 20h
0x1800596c1  pop     rdi
0x1800596c2  pop     rsi
0x1800596c3  pop     rbp
0x1800596c4  retn
```

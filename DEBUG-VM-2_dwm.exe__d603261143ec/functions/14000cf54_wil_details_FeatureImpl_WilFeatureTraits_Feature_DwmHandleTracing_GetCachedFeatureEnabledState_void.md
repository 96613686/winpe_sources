# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cf54`
- end: `0x14000d037`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DwmHandleTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004254`

## callees

- `0x140008084`
- `0x14000aeac`
- `0x14000cf54`
- `0x14000d040`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::GetCachedFeatureEnabledState(
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
  __int64 v12; // r8
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_DwmHandleTracing__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DwmHandleTracing__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      &v14);
    if ( !v5 )
      LODWORD(v14) = 0;
    v7 = *(_DWORD *)a2;
    v8 = v15;
    do
    {
      v9 = (_DWORD)v14 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_DwmHandleTracing__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !(_DWORD)v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_DwmHandleTracing__descriptor,
        v12,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000cf54  mov     [rsp+arg_10], rbx
0x14000cf59  mov     [rsp+arg_0], rcx
0x14000cf5e  push    rbp
0x14000cf5f  push    rsi
0x14000cf60  push    rdi
0x14000cf61  sub     rsp, 20h
0x14000cf65  mov     rsi, cs:Feature_DwmHandleTracing__descriptor
0x14000cf6c  mov     rdi, rdx
0x14000cf6f  mov     qword ptr [rdx], 0
0x14000cf76  mov     eax, [rsi]
0x14000cf78  mov     [rdx], eax
0x14000cf7a  and     eax, 6
0x14000cf7d  cmp     al, 6
0x14000cf7f  jz      loc_14000D027
0x14000cf85  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cf8a  lea     r8, [rsp+38h+arg_0]
0x14000cf8f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000cf97  lea     rdx, [rsp+38h+arg_8]
0x14000cf9c  mov     ebp, eax
0x14000cf9e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DwmHandleTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DwmHandleTracing>::GetCurrentFeatureEnabledState(int *)
0x14000cfa3  test    ebp, ebp
0x14000cfa5  jnz     short loc_14000CFAB
0x14000cfa7  mov     dword ptr [rsp+38h+arg_0], ebp
0x14000cfab  mov     eax, [rdi]
0x14000cfad  mov     rbx, [rsp+38h+arg_8]
0x14000cfb2  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000cfb7  mov     edx, eax
0x14000cfb9  mov     [rdi], eax
0x14000cfbb  mov     ecx, eax
0x14000cfbd  jz      short loc_14000CFD8
0x14000cfbf  test    dl, 2
0x14000cfc2  jnz     short loc_14000CFD8
0x14000cfc4  and     ecx, 0FFFFF63Eh
0x14000cfca  mov     eax, ebx
0x14000cfcc  and     eax, 9C1h
0x14000cfd1  or      ecx, eax
0x14000cfd3  or      ecx, 2
0x14000cfd6  mov     [rdi], ecx
0x14000cfd8  mov     r8d, edx
0x14000cfdb  and     r8d, 4
0x14000cfdf  jnz     short loc_14000CFF3
0x14000cfe1  btr     ecx, 0Ah
0x14000cfe5  mov     eax, ebx
0x14000cfe7  and     eax, 400h
0x14000cfec  or      ecx, eax
0x14000cfee  or      ecx, 4
0x14000cff1  mov     [rdi], ecx
0x14000cff3  mov     eax, edx
0x14000cff5  lock cmpxchg [rsi], ecx
0x14000cff9  jnz     short loc_14000CFB2
0x14000cffb  test    r8d, r8d
0x14000cffe  jnz     short loc_14000D012
0x14000d000  mov     r9d, ebp
0x14000d003  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000d00a  mov     rdx, rsi
0x14000d00d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d012  mov     eax, [rdi]
0x14000d014  test    al, 2
0x14000d016  jnz     short loc_14000D027
0x14000d018  and     eax, 0FFFFF63Eh
0x14000d01d  and     ebx, 9C1h
0x14000d023  or      eax, ebx
0x14000d025  mov     [rdi], eax
0x14000d027  mov     rbx, [rsp+38h+arg_10]
0x14000d02c  mov     rax, rdi
0x14000d02f  add     rsp, 20h
0x14000d033  pop     rdi
0x14000d034  pop     rsi
0x14000d035  pop     rbp
0x14000d036  retn
```

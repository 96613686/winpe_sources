# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::GetCachedFeatureEnabledState(void)

- ea: `0x1800596cc`
- end: `0x1800597ae`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005c240`
- `0x18005cbbc`

## callees

- `0x180048c10`
- `0x1800596cc`
- `0x18005ad6c`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_XHEAACSbrDelay__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_XHEAACSbrDelay__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Servicing_XHEAACSbrDelay__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Servicing_XHEAACSbrDelay__descriptor,
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
0x1800596cc  mov     [rsp+arg_10], rbx
0x1800596d1  mov     [rsp+arg_0], rcx
0x1800596d6  push    rbp
0x1800596d7  push    rsi
0x1800596d8  push    rdi
0x1800596d9  sub     rsp, 20h
0x1800596dd  mov     rsi, cs:Feature_Servicing_XHEAACSbrDelay__descriptor
0x1800596e4  mov     rdi, rdx
0x1800596e7  mov     qword ptr [rdx], 0
0x1800596ee  mov     eax, [rsi]
0x1800596f0  mov     [rdx], eax
0x1800596f2  and     eax, 6
0x1800596f5  cmp     al, 6
0x1800596f7  jz      loc_18005979D
0x1800596fd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180059702  lea     r8, [rsp+38h+arg_0]
0x180059707  mov     dword ptr [rsp+38h+arg_0], 0
0x18005970f  lea     rdx, [rsp+38h+arg_8]
0x180059714  mov     ebp, eax
0x180059716  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::GetCurrentFeatureEnabledState(int *)
0x18005971b  mov     eax, [rdi]
0x18005971d  mov     rbx, [rsp+38h+arg_8]
0x180059722  cmp     dword ptr [rsp+38h+arg_0], 0
0x180059727  mov     edx, eax
0x180059729  mov     [rdi], eax
0x18005972b  mov     ecx, eax
0x18005972d  jz      short loc_180059748
0x18005972f  test    dl, 2
0x180059732  jnz     short loc_180059748
0x180059734  and     ecx, 0FFFFF63Eh
0x18005973a  mov     eax, ebx
0x18005973c  and     eax, 9C1h
0x180059741  or      ecx, eax
0x180059743  or      ecx, 2
0x180059746  mov     [rdi], ecx
0x180059748  mov     r8d, edx
0x18005974b  and     r8d, 4
0x18005974f  jnz     short loc_180059763
0x180059751  btr     ecx, 0Ah
0x180059755  mov     eax, ebx
0x180059757  and     eax, 400h
0x18005975c  or      ecx, eax
0x18005975e  or      ecx, 4
0x180059761  mov     [rdi], ecx
0x180059763  mov     eax, edx
0x180059765  lock cmpxchg [rsi], ecx
0x180059769  jnz     short loc_180059722
0x18005976b  test    r8d, r8d
0x18005976e  jnz     short loc_180059788
0x180059770  mov     r9d, ebp
0x180059773  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005977a  mov     r8d, 3
0x180059780  mov     rdx, rsi
0x180059783  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180059788  mov     eax, [rdi]
0x18005978a  test    al, 2
0x18005978c  jnz     short loc_18005979D
0x18005978e  and     eax, 0FFFFF63Eh
0x180059793  and     ebx, 9C1h
0x180059799  or      eax, ebx
0x18005979b  mov     [rdi], eax
0x18005979d  mov     rbx, [rsp+38h+arg_10]
0x1800597a2  mov     rax, rdi
0x1800597a5  add     rsp, 20h
0x1800597a9  pop     rdi
0x1800597aa  pop     rsi
0x1800597ab  pop     rbp
0x1800597ac  retn
```

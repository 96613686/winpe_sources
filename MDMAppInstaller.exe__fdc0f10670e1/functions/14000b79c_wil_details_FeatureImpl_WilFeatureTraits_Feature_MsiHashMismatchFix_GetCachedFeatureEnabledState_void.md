# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCachedFeatureEnabledState(void)

- ea: `0x14000b79c`
- end: `0x14000b87f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000fc7c`

## callees

- `0x14000b36c`
- `0x14000b79c`
- `0x14000c490`
- `0x140010e28`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MsiHashMismatchFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MsiHashMismatchFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MsiHashMismatchFix__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !(_DWORD)v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_MsiHashMismatchFix__descriptor,
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
0x14000b79c  mov     [rsp+arg_10], rbx
0x14000b7a1  mov     [rsp+arg_0], rcx
0x14000b7a6  push    rbp
0x14000b7a7  push    rsi
0x14000b7a8  push    rdi
0x14000b7a9  sub     rsp, 20h
0x14000b7ad  mov     rsi, cs:Feature_MsiHashMismatchFix__descriptor
0x14000b7b4  mov     rdi, rdx
0x14000b7b7  mov     qword ptr [rdx], 0
0x14000b7be  mov     eax, [rsi]
0x14000b7c0  mov     [rdx], eax
0x14000b7c2  and     eax, 6
0x14000b7c5  cmp     al, 6
0x14000b7c7  jz      loc_14000B86F
0x14000b7cd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000b7d2  lea     r8, [rsp+38h+arg_0]
0x14000b7d7  mov     dword ptr [rsp+38h+arg_0], 0
0x14000b7df  lea     rdx, [rsp+38h+arg_8]
0x14000b7e4  mov     ebp, eax
0x14000b7e6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCurrentFeatureEnabledState(int *)
0x14000b7eb  test    ebp, ebp
0x14000b7ed  jnz     short loc_14000B7F3
0x14000b7ef  mov     dword ptr [rsp+38h+arg_0], ebp
0x14000b7f3  mov     eax, [rdi]
0x14000b7f5  mov     rbx, [rsp+38h+arg_8]
0x14000b7fa  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000b7ff  mov     edx, eax
0x14000b801  mov     [rdi], eax
0x14000b803  mov     ecx, eax
0x14000b805  jz      short loc_14000B820
0x14000b807  test    dl, 2
0x14000b80a  jnz     short loc_14000B820
0x14000b80c  and     ecx, 0FFFFF63Eh
0x14000b812  mov     eax, ebx
0x14000b814  and     eax, 9C1h
0x14000b819  or      ecx, eax
0x14000b81b  or      ecx, 2
0x14000b81e  mov     [rdi], ecx
0x14000b820  mov     r8d, edx
0x14000b823  and     r8d, 4
0x14000b827  jnz     short loc_14000B83B
0x14000b829  btr     ecx, 0Ah
0x14000b82d  mov     eax, ebx
0x14000b82f  and     eax, 400h
0x14000b834  or      ecx, eax
0x14000b836  or      ecx, 4
0x14000b839  mov     [rdi], ecx
0x14000b83b  mov     eax, edx
0x14000b83d  lock cmpxchg [rsi], ecx
0x14000b841  jnz     short loc_14000B7FA
0x14000b843  test    r8d, r8d
0x14000b846  jnz     short loc_14000B85A
0x14000b848  mov     r9d, ebp
0x14000b84b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000b852  mov     rdx, rsi
0x14000b855  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000b85a  mov     eax, [rdi]
0x14000b85c  test    al, 2
0x14000b85e  jnz     short loc_14000B86F
0x14000b860  and     eax, 0FFFFF63Eh
0x14000b865  and     ebx, 9C1h
0x14000b86b  or      eax, ebx
0x14000b86d  mov     [rdi], eax
0x14000b86f  mov     rbx, [rsp+38h+arg_10]
0x14000b874  mov     rax, rdi
0x14000b877  add     rsp, 20h
0x14000b87b  pop     rdi
0x14000b87c  pop     rsi
0x14000b87d  pop     rbp
0x14000b87e  retn
```

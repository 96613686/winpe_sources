# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCachedFeatureEnabledState(void)

- ea: `0x180016f24`
- end: `0x180017008`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001745c`

## callees

- `0x180009fc0`
- `0x180010064`
- `0x180016f24`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WVD_MultiSession_User_Configuration__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WVD_MultiSession_User_Configuration__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_WVD_MultiSession_User_Configuration__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !(_DWORD)v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_WVD_MultiSession_User_Configuration__descriptor,
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
0x180016f24  mov     [rsp+arg_10], rbx
0x180016f29  mov     [rsp+arg_0], rcx
0x180016f2e  push    rbp
0x180016f2f  push    rsi
0x180016f30  push    rdi
0x180016f31  sub     rsp, 20h
0x180016f35  mov     rsi, cs:Feature_WVD_MultiSession_User_Configuration__descriptor
0x180016f3c  mov     rdi, rdx
0x180016f3f  mov     qword ptr [rdx], 0
0x180016f46  mov     eax, [rsi]
0x180016f48  mov     [rdx], eax
0x180016f4a  and     eax, 6
0x180016f4d  cmp     al, 6
0x180016f4f  jz      loc_180016FF7
0x180016f55  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016f5a  lea     r8, [rsp+38h+arg_0]
0x180016f5f  mov     dword ptr [rsp+38h+arg_0], 0
0x180016f67  lea     rdx, [rsp+38h+arg_8]
0x180016f6c  mov     ebp, eax
0x180016f6e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCurrentFeatureEnabledState(int *)
0x180016f73  test    ebp, ebp
0x180016f75  jnz     short loc_180016F7B
0x180016f77  mov     dword ptr [rsp+38h+arg_0], ebp
0x180016f7b  mov     eax, [rdi]
0x180016f7d  mov     rbx, [rsp+38h+arg_8]
0x180016f82  cmp     dword ptr [rsp+38h+arg_0], 0
0x180016f87  mov     edx, eax
0x180016f89  mov     [rdi], eax
0x180016f8b  mov     ecx, eax
0x180016f8d  jz      short loc_180016FA8
0x180016f8f  test    dl, 2
0x180016f92  jnz     short loc_180016FA8
0x180016f94  and     ecx, 0FFFFF63Eh
0x180016f9a  mov     eax, ebx
0x180016f9c  and     eax, 9C1h
0x180016fa1  or      ecx, eax
0x180016fa3  or      ecx, 2
0x180016fa6  mov     [rdi], ecx
0x180016fa8  mov     r8d, edx
0x180016fab  and     r8d, 4
0x180016faf  jnz     short loc_180016FC3
0x180016fb1  btr     ecx, 0Ah
0x180016fb5  mov     eax, ebx
0x180016fb7  and     eax, 400h
0x180016fbc  or      ecx, eax
0x180016fbe  or      ecx, 4
0x180016fc1  mov     [rdi], ecx
0x180016fc3  mov     eax, edx
0x180016fc5  lock cmpxchg [rsi], ecx
0x180016fc9  jnz     short loc_180016F82
0x180016fcb  test    r8d, r8d
0x180016fce  jnz     short loc_180016FE2
0x180016fd0  mov     r9d, ebp
0x180016fd3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016fda  mov     rdx, rsi
0x180016fdd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180016fe2  mov     eax, [rdi]
0x180016fe4  test    al, 2
0x180016fe6  jnz     short loc_180016FF7
0x180016fe8  and     eax, 0FFFFF63Eh
0x180016fed  and     ebx, 9C1h
0x180016ff3  or      eax, ebx
0x180016ff5  mov     [rdi], eax
0x180016ff7  mov     rbx, [rsp+38h+arg_10]
0x180016ffc  mov     rax, rdi
0x180016fff  add     rsp, 20h
0x180017003  pop     rdi
0x180017004  pop     rsi
0x180017005  pop     rbp
0x180017006  retn
```

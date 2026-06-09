# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetCachedFeatureEnabledState(void)

- ea: `0x180048b28`
- end: `0x180048c0a`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180048aec`
- `0x180048d00`

## callees

- `0x180048b28`
- `0x180048c10`
- `0x180048c38`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_XHEAACPeakLimiter__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_XHEAACPeakLimiter__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_XHEAACPeakLimiter__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Servicing_XHEAACPeakLimiter__descriptor,
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
0x180048b28  mov     [rsp+arg_10], rbx
0x180048b2d  mov     [rsp+arg_0], rcx
0x180048b32  push    rbp
0x180048b33  push    rsi
0x180048b34  push    rdi
0x180048b35  sub     rsp, 20h
0x180048b39  mov     rsi, cs:Feature_Servicing_XHEAACPeakLimiter__descriptor
0x180048b40  mov     rdi, rdx
0x180048b43  mov     qword ptr [rdx], 0
0x180048b4a  mov     eax, [rsi]
0x180048b4c  mov     [rdx], eax
0x180048b4e  and     eax, 6
0x180048b51  cmp     al, 6
0x180048b53  jz      loc_180048BF9
0x180048b59  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180048b5e  lea     r8, [rsp+38h+arg_0]
0x180048b63  mov     dword ptr [rsp+38h+arg_0], 0
0x180048b6b  lea     rdx, [rsp+38h+arg_8]
0x180048b70  mov     ebp, eax
0x180048b72  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetCurrentFeatureEnabledState(int *)
0x180048b77  mov     eax, [rdi]
0x180048b79  mov     rbx, [rsp+38h+arg_8]
0x180048b7e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180048b83  mov     edx, eax
0x180048b85  mov     [rdi], eax
0x180048b87  mov     ecx, eax
0x180048b89  jz      short loc_180048BA4
0x180048b8b  test    dl, 2
0x180048b8e  jnz     short loc_180048BA4
0x180048b90  and     ecx, 0FFFFF63Eh
0x180048b96  mov     eax, ebx
0x180048b98  and     eax, 9C1h
0x180048b9d  or      ecx, eax
0x180048b9f  or      ecx, 2
0x180048ba2  mov     [rdi], ecx
0x180048ba4  mov     r8d, edx
0x180048ba7  and     r8d, 4
0x180048bab  jnz     short loc_180048BBF
0x180048bad  btr     ecx, 0Ah
0x180048bb1  mov     eax, ebx
0x180048bb3  and     eax, 400h
0x180048bb8  or      ecx, eax
0x180048bba  or      ecx, 4
0x180048bbd  mov     [rdi], ecx
0x180048bbf  mov     eax, edx
0x180048bc1  lock cmpxchg [rsi], ecx
0x180048bc5  jnz     short loc_180048B7E
0x180048bc7  test    r8d, r8d
0x180048bca  jnz     short loc_180048BE4
0x180048bcc  mov     r9d, ebp
0x180048bcf  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180048bd6  mov     r8d, 3
0x180048bdc  mov     rdx, rsi
0x180048bdf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180048be4  mov     eax, [rdi]
0x180048be6  test    al, 2
0x180048be8  jnz     short loc_180048BF9
0x180048bea  and     eax, 0FFFFF63Eh
0x180048bef  and     ebx, 9C1h
0x180048bf5  or      eax, ebx
0x180048bf7  mov     [rdi], eax
0x180048bf9  mov     rbx, [rsp+38h+arg_10]
0x180048bfe  mov     rax, rdi
0x180048c01  add     rsp, 20h
0x180048c05  pop     rdi
0x180048c06  pop     rsi
0x180048c07  pop     rbp
0x180048c08  retn
```

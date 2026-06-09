# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetCachedFeatureEnabledState(void)

- ea: `0x180008330`
- end: `0x180008409`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011ac0`

## callees

- `0x18000787c`
- `0x180008330`
- `0x1800092f0`
- `0x180010684`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_RemoteManagement__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_RemoteManagement__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_RecoveryRobustness_RemoteManagement__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_RecoveryRobustness_RemoteManagement__descriptor,
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
0x180008330  mov     [rsp+arg_10], rbx
0x180008335  mov     [rsp+arg_0], rcx
0x18000833a  push    rbp
0x18000833b  push    rsi
0x18000833c  push    rdi
0x18000833d  sub     rsp, 20h
0x180008341  mov     rsi, cs:Feature_Servicing_RecoveryRobustness_RemoteManagement__descriptor
0x180008348  mov     rdi, rdx
0x18000834b  mov     qword ptr [rdx], 0
0x180008352  mov     eax, [rsi]
0x180008354  mov     [rdx], eax
0x180008356  and     eax, 6
0x180008359  cmp     al, 6
0x18000835b  jz      loc_1800083F9
0x180008361  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008366  lea     r8, [rsp+38h+arg_0]
0x18000836b  mov     dword ptr [rsp+38h+arg_0], 0
0x180008373  lea     rdx, [rsp+38h+arg_8]
0x180008378  mov     ebp, eax
0x18000837a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetCurrentFeatureEnabledState(int *)
0x18000837f  mov     eax, [rdi]
0x180008381  mov     rbx, [rsp+38h+arg_8]
0x180008386  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000838b  mov     edx, eax
0x18000838d  mov     [rdi], eax
0x18000838f  mov     ecx, eax
0x180008391  jz      short loc_1800083AC
0x180008393  test    dl, 2
0x180008396  jnz     short loc_1800083AC
0x180008398  and     ecx, 0FFFFF63Eh
0x18000839e  mov     eax, ebx
0x1800083a0  and     eax, 9C1h
0x1800083a5  or      ecx, eax
0x1800083a7  or      ecx, 2
0x1800083aa  mov     [rdi], ecx
0x1800083ac  mov     r8d, edx
0x1800083af  and     r8d, 4
0x1800083b3  jnz     short loc_1800083C7
0x1800083b5  btr     ecx, 0Ah
0x1800083b9  mov     eax, ebx
0x1800083bb  and     eax, 400h
0x1800083c0  or      ecx, eax
0x1800083c2  or      ecx, 4
0x1800083c5  mov     [rdi], ecx
0x1800083c7  mov     eax, edx
0x1800083c9  lock cmpxchg [rsi], ecx
0x1800083cd  jnz     short loc_180008386
0x1800083cf  test    r8d, r8d
0x1800083d2  jnz     short loc_1800083E4
0x1800083d4  mov     r8d, ebp
0x1800083d7  mov     edx, 3
0x1800083dc  mov     rcx, rsi
0x1800083df  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800083e4  mov     eax, [rdi]
0x1800083e6  test    al, 2
0x1800083e8  jnz     short loc_1800083F9
0x1800083ea  and     eax, 0FFFFF63Eh
0x1800083ef  and     ebx, 9C1h
0x1800083f5  or      eax, ebx
0x1800083f7  mov     [rdi], eax
0x1800083f9  mov     rbx, [rsp+38h+arg_10]
0x1800083fe  mov     rax, rdi
0x180008401  add     rsp, 20h
0x180008405  pop     rdi
0x180008406  pop     rsi
0x180008407  pop     rbp
0x180008408  retn
```

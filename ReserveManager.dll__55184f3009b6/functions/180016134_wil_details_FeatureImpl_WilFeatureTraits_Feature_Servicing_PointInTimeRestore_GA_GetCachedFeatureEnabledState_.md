# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(void)

- ea: `0x180016134`
- end: `0x18001621f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ea30`
- `0x180021e80`

## callees

- `0x180003870`
- `0x180006e18`
- `0x18000acc8`
- `0x180016134`
- `0x180016524`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_GA__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_GA__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(
      v5,
      &v12,
      &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore_GA__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_PointInTimeRestore_GA__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180016134  push    rbx
0x180016136  push    rbp
0x180016137  push    rsi
0x180016138  push    rdi
0x180016139  sub     rsp, 48h
0x18001613d  mov     rax, cs:__security_cookie
0x180016144  xor     rax, rsp
0x180016147  mov     [rsp+68h+var_38], rax
0x18001614c  mov     rsi, cs:Feature_Servicing_PointInTimeRestore_GA__descriptor
0x180016153  mov     rdi, rdx
0x180016156  mov     qword ptr [rdx], 0
0x18001615d  mov     eax, [rsi]
0x18001615f  mov     [rdx], eax
0x180016161  and     eax, 6
0x180016164  cmp     al, 6
0x180016166  jz      loc_180016206
0x18001616c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016171  lea     r8, [rsp+68h+var_40]
0x180016176  mov     [rsp+68h+var_40], 0
0x18001617e  lea     rdx, [rsp+68h+var_48]
0x180016183  mov     ebp, eax
0x180016185  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(int *)
0x18001618a  mov     eax, [rdi]
0x18001618c  mov     rbx, [rsp+68h+var_48]
0x180016191  cmp     [rsp+68h+var_40], 0
0x180016196  mov     edx, eax
0x180016198  mov     [rdi], eax
0x18001619a  mov     ecx, eax
0x18001619c  jz      short loc_1800161B7
0x18001619e  test    dl, 2
0x1800161a1  jnz     short loc_1800161B7
0x1800161a3  and     ecx, 0FFFFF63Eh
0x1800161a9  mov     eax, ebx
0x1800161ab  and     eax, 9C1h
0x1800161b0  or      ecx, eax
0x1800161b2  or      ecx, 2
0x1800161b5  mov     [rdi], ecx
0x1800161b7  mov     r8d, edx
0x1800161ba  and     r8d, 4
0x1800161be  jnz     short loc_1800161D2
0x1800161c0  btr     ecx, 0Ah
0x1800161c4  mov     eax, ebx
0x1800161c6  and     eax, 400h
0x1800161cb  or      ecx, eax
0x1800161cd  or      ecx, 4
0x1800161d0  mov     [rdi], ecx
0x1800161d2  mov     eax, edx
0x1800161d4  lock cmpxchg [rsi], ecx
0x1800161d8  jnz     short loc_180016191
0x1800161da  test    r8d, r8d
0x1800161dd  jnz     short loc_1800161EF
0x1800161df  mov     r8d, ebp
0x1800161e2  mov     edx, 3
0x1800161e7  mov     rcx, rsi
0x1800161ea  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800161ef  mov     ecx, [rdi]
0x1800161f1  test    cl, 2
0x1800161f4  jnz     short loc_180016206
0x1800161f6  and     ecx, 0FFFFF63Eh
0x1800161fc  and     ebx, 9C1h
0x180016202  or      ecx, ebx
0x180016204  mov     [rdi], ecx
0x180016206  mov     rax, rdi
0x180016209  mov     rcx, [rsp+68h+var_38]
0x18001620e  xor     rcx, rsp; StackCookie
0x180016211  call    __security_check_cookie
0x180016216  add     rsp, 48h
0x18001621a  pop     rdi
0x18001621b  pop     rsi
0x18001621c  pop     rbp
0x18001621d  pop     rbx
0x18001621e  retn
```

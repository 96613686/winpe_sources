# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCachedFeatureEnabledState(void)

- ea: `0x180008250`
- end: `0x180008329`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011a20`

## callees

- `0x18000787c`
- `0x180008250`
- `0x1800091a8`
- `0x180010684`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor,
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
0x180008250  mov     [rsp+arg_10], rbx
0x180008255  mov     [rsp+arg_0], rcx
0x18000825a  push    rbp
0x18000825b  push    rsi
0x18000825c  push    rdi
0x18000825d  sub     rsp, 20h
0x180008261  mov     rsi, cs:Feature_Servicing_RecoveryRobustness_EnableSrtOnServer__descriptor
0x180008268  mov     rdi, rdx
0x18000826b  mov     qword ptr [rdx], 0
0x180008272  mov     eax, [rsi]
0x180008274  mov     [rdx], eax
0x180008276  and     eax, 6
0x180008279  cmp     al, 6
0x18000827b  jz      loc_180008319
0x180008281  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008286  lea     r8, [rsp+38h+arg_0]
0x18000828b  mov     dword ptr [rsp+38h+arg_0], 0
0x180008293  lea     rdx, [rsp+38h+arg_8]
0x180008298  mov     ebp, eax
0x18000829a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCurrentFeatureEnabledState(int *)
0x18000829f  mov     eax, [rdi]
0x1800082a1  mov     rbx, [rsp+38h+arg_8]
0x1800082a6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800082ab  mov     edx, eax
0x1800082ad  mov     [rdi], eax
0x1800082af  mov     ecx, eax
0x1800082b1  jz      short loc_1800082CC
0x1800082b3  test    dl, 2
0x1800082b6  jnz     short loc_1800082CC
0x1800082b8  and     ecx, 0FFFFF63Eh
0x1800082be  mov     eax, ebx
0x1800082c0  and     eax, 9C1h
0x1800082c5  or      ecx, eax
0x1800082c7  or      ecx, 2
0x1800082ca  mov     [rdi], ecx
0x1800082cc  mov     r8d, edx
0x1800082cf  and     r8d, 4
0x1800082d3  jnz     short loc_1800082E7
0x1800082d5  btr     ecx, 0Ah
0x1800082d9  mov     eax, ebx
0x1800082db  and     eax, 400h
0x1800082e0  or      ecx, eax
0x1800082e2  or      ecx, 4
0x1800082e5  mov     [rdi], ecx
0x1800082e7  mov     eax, edx
0x1800082e9  lock cmpxchg [rsi], ecx
0x1800082ed  jnz     short loc_1800082A6
0x1800082ef  test    r8d, r8d
0x1800082f2  jnz     short loc_180008304
0x1800082f4  mov     r8d, ebp
0x1800082f7  mov     edx, 3
0x1800082fc  mov     rcx, rsi
0x1800082ff  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008304  mov     eax, [rdi]
0x180008306  test    al, 2
0x180008308  jnz     short loc_180008319
0x18000830a  and     eax, 0FFFFF63Eh
0x18000830f  and     ebx, 9C1h
0x180008315  or      eax, ebx
0x180008317  mov     [rdi], eax
0x180008319  mov     rbx, [rsp+38h+arg_10]
0x18000831e  mov     rax, rdi
0x180008321  add     rsp, 20h
0x180008325  pop     rdi
0x180008326  pop     rsi
0x180008327  pop     rbp
0x180008328  retn
```

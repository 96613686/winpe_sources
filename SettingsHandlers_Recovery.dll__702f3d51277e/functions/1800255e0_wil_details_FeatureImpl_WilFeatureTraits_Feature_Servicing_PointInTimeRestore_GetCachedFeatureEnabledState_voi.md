# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCachedFeatureEnabledState(void)

- ea: `0x1800255e0`
- end: `0x1800256b9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180026338`

## callees

- `0x180005b50`
- `0x1800097b0`
- `0x1800255e0`
- `0x180025990`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_PointInTimeRestore__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_PointInTimeRestore__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(
      v5,
      &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore__descriptor,
             v9,
             v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore__descriptor,
        3u,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800255e0  mov     [rsp+arg_10], rbx
0x1800255e5  mov     [rsp+arg_0], rcx
0x1800255ea  push    rbp
0x1800255eb  push    rsi
0x1800255ec  push    rdi
0x1800255ed  sub     rsp, 20h
0x1800255f1  mov     rsi, cs:Feature_Servicing_PointInTimeRestore__descriptor
0x1800255f8  mov     rdi, rdx
0x1800255fb  mov     qword ptr [rdx], 0
0x180025602  mov     eax, [rsi]
0x180025604  mov     [rdx], eax
0x180025606  and     eax, 6
0x180025609  cmp     al, 6
0x18002560b  jz      loc_1800256A9
0x180025611  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025616  lea     r8, [rsp+38h+arg_0]
0x18002561b  mov     dword ptr [rsp+38h+arg_0], 0
0x180025623  lea     rdx, [rsp+38h+arg_8]
0x180025628  mov     ebp, eax
0x18002562a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(int *)
0x18002562f  mov     eax, [rdi]
0x180025631  mov     rbx, [rsp+38h+arg_8]
0x180025636  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002563b  mov     edx, eax
0x18002563d  mov     [rdi], eax
0x18002563f  mov     ecx, eax
0x180025641  jz      short loc_18002565C
0x180025643  test    dl, 2
0x180025646  jnz     short loc_18002565C
0x180025648  and     ecx, 0FFFFF63Eh
0x18002564e  mov     eax, ebx
0x180025650  and     eax, 9C1h
0x180025655  or      ecx, eax
0x180025657  or      ecx, 2
0x18002565a  mov     [rdi], ecx
0x18002565c  mov     r8d, edx
0x18002565f  and     r8d, 4
0x180025663  jnz     short loc_180025677
0x180025665  btr     ecx, 0Ah
0x180025669  mov     eax, ebx
0x18002566b  and     eax, 400h
0x180025670  or      ecx, eax
0x180025672  or      ecx, 4
0x180025675  mov     [rdi], ecx
0x180025677  mov     eax, edx
0x180025679  lock cmpxchg [rsi], ecx
0x18002567d  jnz     short loc_180025636
0x18002567f  test    r8d, r8d
0x180025682  jnz     short loc_180025694
0x180025684  mov     r8d, ebp
0x180025687  mov     edx, 3
0x18002568c  mov     rcx, rsi
0x18002568f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180025694  mov     eax, [rdi]
0x180025696  test    al, 2
0x180025698  jnz     short loc_1800256A9
0x18002569a  and     eax, 0FFFFF63Eh
0x18002569f  and     ebx, 9C1h
0x1800256a5  or      eax, ebx
0x1800256a7  mov     [rdi], eax
0x1800256a9  mov     rbx, [rsp+38h+arg_10]
0x1800256ae  mov     rax, rdi
0x1800256b1  add     rsp, 20h
0x1800256b5  pop     rdi
0x1800256b6  pop     rsi
0x1800256b7  pop     rbp
0x1800256b8  retn
```

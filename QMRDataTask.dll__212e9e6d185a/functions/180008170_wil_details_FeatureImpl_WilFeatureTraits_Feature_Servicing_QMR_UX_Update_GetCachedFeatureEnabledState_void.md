# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCachedFeatureEnabledState(void)

- ea: `0x180008170`
- end: `0x180008249`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011980`

## callees

- `0x18000787c`
- `0x180008170`
- `0x180009060`
- `0x180010684`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_QMR_UX_Update__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_QMR_UX_Update__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Servicing_QMR_UX_Update__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_QMR_UX_Update__descriptor,
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
0x180008170  mov     [rsp+arg_10], rbx
0x180008175  mov     [rsp+arg_0], rcx
0x18000817a  push    rbp
0x18000817b  push    rsi
0x18000817c  push    rdi
0x18000817d  sub     rsp, 20h
0x180008181  mov     rsi, cs:Feature_Servicing_QMR_UX_Update__descriptor
0x180008188  mov     rdi, rdx
0x18000818b  mov     qword ptr [rdx], 0
0x180008192  mov     eax, [rsi]
0x180008194  mov     [rdx], eax
0x180008196  and     eax, 6
0x180008199  cmp     al, 6
0x18000819b  jz      loc_180008239
0x1800081a1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800081a6  lea     r8, [rsp+38h+arg_0]
0x1800081ab  mov     dword ptr [rsp+38h+arg_0], 0
0x1800081b3  lea     rdx, [rsp+38h+arg_8]
0x1800081b8  mov     ebp, eax
0x1800081ba  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCurrentFeatureEnabledState(int *)
0x1800081bf  mov     eax, [rdi]
0x1800081c1  mov     rbx, [rsp+38h+arg_8]
0x1800081c6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800081cb  mov     edx, eax
0x1800081cd  mov     [rdi], eax
0x1800081cf  mov     ecx, eax
0x1800081d1  jz      short loc_1800081EC
0x1800081d3  test    dl, 2
0x1800081d6  jnz     short loc_1800081EC
0x1800081d8  and     ecx, 0FFFFF63Eh
0x1800081de  mov     eax, ebx
0x1800081e0  and     eax, 9C1h
0x1800081e5  or      ecx, eax
0x1800081e7  or      ecx, 2
0x1800081ea  mov     [rdi], ecx
0x1800081ec  mov     r8d, edx
0x1800081ef  and     r8d, 4
0x1800081f3  jnz     short loc_180008207
0x1800081f5  btr     ecx, 0Ah
0x1800081f9  mov     eax, ebx
0x1800081fb  and     eax, 400h
0x180008200  or      ecx, eax
0x180008202  or      ecx, 4
0x180008205  mov     [rdi], ecx
0x180008207  mov     eax, edx
0x180008209  lock cmpxchg [rsi], ecx
0x18000820d  jnz     short loc_1800081C6
0x18000820f  test    r8d, r8d
0x180008212  jnz     short loc_180008224
0x180008214  mov     r8d, ebp
0x180008217  mov     edx, 3
0x18000821c  mov     rcx, rsi
0x18000821f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008224  mov     eax, [rdi]
0x180008226  test    al, 2
0x180008228  jnz     short loc_180008239
0x18000822a  and     eax, 0FFFFF63Eh
0x18000822f  and     ebx, 9C1h
0x180008235  or      eax, ebx
0x180008237  mov     [rdi], eax
0x180008239  mov     rbx, [rsp+38h+arg_10]
0x18000823e  mov     rax, rdi
0x180008241  add     rsp, 20h
0x180008245  pop     rdi
0x180008246  pop     rsi
0x180008247  pop     rbp
0x180008248  retn
```

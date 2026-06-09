# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCachedFeatureEnabledState(void)

- ea: `0x180016040`
- end: `0x18001612b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e98c`
- `0x180021e44`

## callees

- `0x180003870`
- `0x180006e18`
- `0x18000acc8`
- `0x180016040`
- `0x1800163c0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_PointInTimeRestore__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_PointInTimeRestore__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_PointInTimeRestore__descriptor,
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
0x180016040  push    rbx
0x180016042  push    rbp
0x180016043  push    rsi
0x180016044  push    rdi
0x180016045  sub     rsp, 48h
0x180016049  mov     rax, cs:__security_cookie
0x180016050  xor     rax, rsp
0x180016053  mov     [rsp+68h+var_38], rax
0x180016058  mov     rsi, cs:Feature_Servicing_PointInTimeRestore__descriptor
0x18001605f  mov     rdi, rdx
0x180016062  mov     qword ptr [rdx], 0
0x180016069  mov     eax, [rsi]
0x18001606b  mov     [rdx], eax
0x18001606d  and     eax, 6
0x180016070  cmp     al, 6
0x180016072  jz      loc_180016112
0x180016078  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001607d  lea     r8, [rsp+68h+var_40]
0x180016082  mov     [rsp+68h+var_40], 0
0x18001608a  lea     rdx, [rsp+68h+var_48]
0x18001608f  mov     ebp, eax
0x180016091  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(int *)
0x180016096  mov     eax, [rdi]
0x180016098  mov     rbx, [rsp+68h+var_48]
0x18001609d  cmp     [rsp+68h+var_40], 0
0x1800160a2  mov     edx, eax
0x1800160a4  mov     [rdi], eax
0x1800160a6  mov     ecx, eax
0x1800160a8  jz      short loc_1800160C3
0x1800160aa  test    dl, 2
0x1800160ad  jnz     short loc_1800160C3
0x1800160af  and     ecx, 0FFFFF63Eh
0x1800160b5  mov     eax, ebx
0x1800160b7  and     eax, 9C1h
0x1800160bc  or      ecx, eax
0x1800160be  or      ecx, 2
0x1800160c1  mov     [rdi], ecx
0x1800160c3  mov     r8d, edx
0x1800160c6  and     r8d, 4
0x1800160ca  jnz     short loc_1800160DE
0x1800160cc  btr     ecx, 0Ah
0x1800160d0  mov     eax, ebx
0x1800160d2  and     eax, 400h
0x1800160d7  or      ecx, eax
0x1800160d9  or      ecx, 4
0x1800160dc  mov     [rdi], ecx
0x1800160de  mov     eax, edx
0x1800160e0  lock cmpxchg [rsi], ecx
0x1800160e4  jnz     short loc_18001609D
0x1800160e6  test    r8d, r8d
0x1800160e9  jnz     short loc_1800160FB
0x1800160eb  mov     r8d, ebp
0x1800160ee  mov     edx, 3
0x1800160f3  mov     rcx, rsi
0x1800160f6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800160fb  mov     ecx, [rdi]
0x1800160fd  test    cl, 2
0x180016100  jnz     short loc_180016112
0x180016102  and     ecx, 0FFFFF63Eh
0x180016108  and     ebx, 9C1h
0x18001610e  or      ecx, ebx
0x180016110  mov     [rdi], ecx
0x180016112  mov     rax, rdi
0x180016115  mov     rcx, [rsp+68h+var_38]
0x18001611a  xor     rcx, rsp; StackCookie
0x18001611d  call    __security_check_cookie
0x180016122  add     rsp, 48h
0x180016126  pop     rdi
0x180016127  pop     rsi
0x180016128  pop     rbp
0x180016129  pop     rbx
0x18001612a  retn
```

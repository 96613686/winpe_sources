# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCachedFeatureEnabledState(void)

- ea: `0x1800055d4`
- end: `0x1800056bf`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008698`
- `0x18000bad4`
- `0x18000bb14`

## callees

- `0x180004f64`
- `0x1800055d4`
- `0x180005ba0`
- `0x180009800`
- `0x1800107c0`

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
0x1800055d4  push    rbx
0x1800055d6  push    rbp
0x1800055d7  push    rsi
0x1800055d8  push    rdi
0x1800055d9  sub     rsp, 48h
0x1800055dd  mov     rax, cs:__security_cookie
0x1800055e4  xor     rax, rsp
0x1800055e7  mov     [rsp+68h+var_38], rax
0x1800055ec  mov     rsi, cs:Feature_Servicing_PointInTimeRestore__descriptor
0x1800055f3  mov     rdi, rdx
0x1800055f6  mov     qword ptr [rdx], 0
0x1800055fd  mov     eax, [rsi]
0x1800055ff  mov     [rdx], eax
0x180005601  and     eax, 6
0x180005604  cmp     al, 6
0x180005606  jz      loc_1800056A6
0x18000560c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005611  lea     r8, [rsp+68h+var_40]
0x180005616  mov     [rsp+68h+var_40], 0
0x18000561e  lea     rdx, [rsp+68h+var_48]
0x180005623  mov     ebp, eax
0x180005625  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(int *)
0x18000562a  mov     eax, [rdi]
0x18000562c  mov     rbx, [rsp+68h+var_48]
0x180005631  cmp     [rsp+68h+var_40], 0
0x180005636  mov     edx, eax
0x180005638  mov     [rdi], eax
0x18000563a  mov     ecx, eax
0x18000563c  jz      short loc_180005657
0x18000563e  test    dl, 2
0x180005641  jnz     short loc_180005657
0x180005643  and     ecx, 0FFFFF63Eh
0x180005649  mov     eax, ebx
0x18000564b  and     eax, 9C1h
0x180005650  or      ecx, eax
0x180005652  or      ecx, 2
0x180005655  mov     [rdi], ecx
0x180005657  mov     r8d, edx
0x18000565a  and     r8d, 4
0x18000565e  jnz     short loc_180005672
0x180005660  btr     ecx, 0Ah
0x180005664  mov     eax, ebx
0x180005666  and     eax, 400h
0x18000566b  or      ecx, eax
0x18000566d  or      ecx, 4
0x180005670  mov     [rdi], ecx
0x180005672  mov     eax, edx
0x180005674  lock cmpxchg [rsi], ecx
0x180005678  jnz     short loc_180005631
0x18000567a  test    r8d, r8d
0x18000567d  jnz     short loc_18000568F
0x18000567f  mov     r8d, ebp
0x180005682  mov     edx, 3
0x180005687  mov     rcx, rsi
0x18000568a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000568f  mov     ecx, [rdi]
0x180005691  test    cl, 2
0x180005694  jnz     short loc_1800056A6
0x180005696  and     ecx, 0FFFFF63Eh
0x18000569c  and     ebx, 9C1h
0x1800056a2  or      ecx, ebx
0x1800056a4  mov     [rdi], ecx
0x1800056a6  mov     rax, rdi
0x1800056a9  mov     rcx, [rsp+68h+var_38]
0x1800056ae  xor     rcx, rsp; StackCookie
0x1800056b1  call    __security_check_cookie
0x1800056b6  add     rsp, 48h
0x1800056ba  pop     rdi
0x1800056bb  pop     rsi
0x1800056bc  pop     rbp
0x1800056bd  pop     rbx
0x1800056be  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR>::GetCachedFeatureEnabledState(void)

- ea: `0x1800056c8`
- end: `0x1800057b3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000874c`
- `0x18000bb54`

## callees

- `0x180004f64`
- `0x1800056c8`
- `0x180005d04`
- `0x180009800`
- `0x1800107c0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_CFR__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_CFR__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore_CFR__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_PointInTimeRestore_CFR__descriptor,
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
0x1800056c8  push    rbx
0x1800056ca  push    rbp
0x1800056cb  push    rsi
0x1800056cc  push    rdi
0x1800056cd  sub     rsp, 48h
0x1800056d1  mov     rax, cs:__security_cookie
0x1800056d8  xor     rax, rsp
0x1800056db  mov     [rsp+68h+var_38], rax
0x1800056e0  mov     rsi, cs:Feature_Servicing_PointInTimeRestore_CFR__descriptor
0x1800056e7  mov     rdi, rdx
0x1800056ea  mov     qword ptr [rdx], 0
0x1800056f1  mov     eax, [rsi]
0x1800056f3  mov     [rdx], eax
0x1800056f5  and     eax, 6
0x1800056f8  cmp     al, 6
0x1800056fa  jz      loc_18000579A
0x180005700  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005705  lea     r8, [rsp+68h+var_40]
0x18000570a  mov     [rsp+68h+var_40], 0
0x180005712  lea     rdx, [rsp+68h+var_48]
0x180005717  mov     ebp, eax
0x180005719  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR>::GetCurrentFeatureEnabledState(int *)
0x18000571e  mov     eax, [rdi]
0x180005720  mov     rbx, [rsp+68h+var_48]
0x180005725  cmp     [rsp+68h+var_40], 0
0x18000572a  mov     edx, eax
0x18000572c  mov     [rdi], eax
0x18000572e  mov     ecx, eax
0x180005730  jz      short loc_18000574B
0x180005732  test    dl, 2
0x180005735  jnz     short loc_18000574B
0x180005737  and     ecx, 0FFFFF63Eh
0x18000573d  mov     eax, ebx
0x18000573f  and     eax, 9C1h
0x180005744  or      ecx, eax
0x180005746  or      ecx, 2
0x180005749  mov     [rdi], ecx
0x18000574b  mov     r8d, edx
0x18000574e  and     r8d, 4
0x180005752  jnz     short loc_180005766
0x180005754  btr     ecx, 0Ah
0x180005758  mov     eax, ebx
0x18000575a  and     eax, 400h
0x18000575f  or      ecx, eax
0x180005761  or      ecx, 4
0x180005764  mov     [rdi], ecx
0x180005766  mov     eax, edx
0x180005768  lock cmpxchg [rsi], ecx
0x18000576c  jnz     short loc_180005725
0x18000576e  test    r8d, r8d
0x180005771  jnz     short loc_180005783
0x180005773  mov     r8d, ebp
0x180005776  mov     edx, 3
0x18000577b  mov     rcx, rsi
0x18000577e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005783  mov     ecx, [rdi]
0x180005785  test    cl, 2
0x180005788  jnz     short loc_18000579A
0x18000578a  and     ecx, 0FFFFF63Eh
0x180005790  and     ebx, 9C1h
0x180005796  or      ecx, ebx
0x180005798  mov     [rdi], ecx
0x18000579a  mov     rax, rdi
0x18000579d  mov     rcx, [rsp+68h+var_38]
0x1800057a2  xor     rcx, rsp; StackCookie
0x1800057a5  call    __security_check_cookie
0x1800057aa  add     rsp, 48h
0x1800057ae  pop     rdi
0x1800057af  pop     rsi
0x1800057b0  pop     rbp
0x1800057b1  pop     rbx
0x1800057b2  retn
```

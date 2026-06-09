# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCachedFeatureEnabledState(void)

- ea: `0x180007df0`
- end: `0x180007ec9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011704`

## callees

- `0x18000787c`
- `0x180007df0`
- `0x180008b40`
- `0x180010684`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_PointInTimeRestore__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_PointInTimeRestore__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_PointInTimeRestore__descriptor,
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
0x180007df0  mov     [rsp+arg_10], rbx
0x180007df5  mov     [rsp+arg_0], rcx
0x180007dfa  push    rbp
0x180007dfb  push    rsi
0x180007dfc  push    rdi
0x180007dfd  sub     rsp, 20h
0x180007e01  mov     rsi, cs:Feature_Servicing_PointInTimeRestore__descriptor
0x180007e08  mov     rdi, rdx
0x180007e0b  mov     qword ptr [rdx], 0
0x180007e12  mov     eax, [rsi]
0x180007e14  mov     [rdx], eax
0x180007e16  and     eax, 6
0x180007e19  cmp     al, 6
0x180007e1b  jz      loc_180007EB9
0x180007e21  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007e26  lea     r8, [rsp+38h+arg_0]
0x180007e2b  mov     dword ptr [rsp+38h+arg_0], 0
0x180007e33  lea     rdx, [rsp+38h+arg_8]
0x180007e38  mov     ebp, eax
0x180007e3a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(int *)
0x180007e3f  mov     eax, [rdi]
0x180007e41  mov     rbx, [rsp+38h+arg_8]
0x180007e46  cmp     dword ptr [rsp+38h+arg_0], 0
0x180007e4b  mov     edx, eax
0x180007e4d  mov     [rdi], eax
0x180007e4f  mov     ecx, eax
0x180007e51  jz      short loc_180007E6C
0x180007e53  test    dl, 2
0x180007e56  jnz     short loc_180007E6C
0x180007e58  and     ecx, 0FFFFF63Eh
0x180007e5e  mov     eax, ebx
0x180007e60  and     eax, 9C1h
0x180007e65  or      ecx, eax
0x180007e67  or      ecx, 2
0x180007e6a  mov     [rdi], ecx
0x180007e6c  mov     r8d, edx
0x180007e6f  and     r8d, 4
0x180007e73  jnz     short loc_180007E87
0x180007e75  btr     ecx, 0Ah
0x180007e79  mov     eax, ebx
0x180007e7b  and     eax, 400h
0x180007e80  or      ecx, eax
0x180007e82  or      ecx, 4
0x180007e85  mov     [rdi], ecx
0x180007e87  mov     eax, edx
0x180007e89  lock cmpxchg [rsi], ecx
0x180007e8d  jnz     short loc_180007E46
0x180007e8f  test    r8d, r8d
0x180007e92  jnz     short loc_180007EA4
0x180007e94  mov     r8d, ebp
0x180007e97  mov     edx, 3
0x180007e9c  mov     rcx, rsi
0x180007e9f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007ea4  mov     eax, [rdi]
0x180007ea6  test    al, 2
0x180007ea8  jnz     short loc_180007EB9
0x180007eaa  and     eax, 0FFFFF63Eh
0x180007eaf  and     ebx, 9C1h
0x180007eb5  or      eax, ebx
0x180007eb7  mov     [rdi], eax
0x180007eb9  mov     rbx, [rsp+38h+arg_10]
0x180007ebe  mov     rax, rdi
0x180007ec1  add     rsp, 20h
0x180007ec5  pop     rdi
0x180007ec6  pop     rsi
0x180007ec7  pop     rbp
0x180007ec8  retn
```

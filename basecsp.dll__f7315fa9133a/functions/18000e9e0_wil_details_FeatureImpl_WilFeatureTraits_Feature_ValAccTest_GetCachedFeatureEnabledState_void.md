# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e9e0`
- end: `0x18000eab9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016224`
- `0x1800187d4`

## callees

- `0x18000d7e0`
- `0x18000e9e0`
- `0x18000f5d0`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x18000e9e0  mov     [rsp+arg_10], rbx
0x18000e9e5  mov     [rsp+arg_0], rcx
0x18000e9ea  push    rbp
0x18000e9eb  push    rsi
0x18000e9ec  push    rdi
0x18000e9ed  sub     rsp, 20h
0x18000e9f1  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000e9f8  mov     rdi, rdx
0x18000e9fb  mov     qword ptr [rdx], 0
0x18000ea02  mov     eax, [rsi]
0x18000ea04  mov     [rdx], eax
0x18000ea06  and     eax, 6
0x18000ea09  cmp     al, 6
0x18000ea0b  jz      loc_18000EAA9
0x18000ea11  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ea16  lea     r8, [rsp+38h+arg_0]
0x18000ea1b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ea23  lea     rdx, [rsp+38h+arg_8]
0x18000ea28  mov     ebp, eax
0x18000ea2a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000ea2f  mov     eax, [rdi]
0x18000ea31  mov     rbx, [rsp+38h+arg_8]
0x18000ea36  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ea3b  mov     edx, eax
0x18000ea3d  mov     [rdi], eax
0x18000ea3f  mov     ecx, eax
0x18000ea41  jz      short loc_18000EA5C
0x18000ea43  test    dl, 2
0x18000ea46  jnz     short loc_18000EA5C
0x18000ea48  and     ecx, 0FFFFF63Eh
0x18000ea4e  mov     eax, ebx
0x18000ea50  and     eax, 9C1h
0x18000ea55  or      ecx, eax
0x18000ea57  or      ecx, 2
0x18000ea5a  mov     [rdi], ecx
0x18000ea5c  mov     r8d, edx
0x18000ea5f  and     r8d, 4
0x18000ea63  jnz     short loc_18000EA77
0x18000ea65  btr     ecx, 0Ah
0x18000ea69  mov     eax, ebx
0x18000ea6b  and     eax, 400h
0x18000ea70  or      ecx, eax
0x18000ea72  or      ecx, 4
0x18000ea75  mov     [rdi], ecx
0x18000ea77  mov     eax, edx
0x18000ea79  lock cmpxchg [rsi], ecx
0x18000ea7d  jnz     short loc_18000EA36
0x18000ea7f  test    r8d, r8d
0x18000ea82  jnz     short loc_18000EA94
0x18000ea84  mov     r8d, ebp
0x18000ea87  mov     edx, 3
0x18000ea8c  mov     rcx, rsi
0x18000ea8f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ea94  mov     eax, [rdi]
0x18000ea96  test    al, 2
0x18000ea98  jnz     short loc_18000EAA9
0x18000ea9a  and     eax, 0FFFFF63Eh
0x18000ea9f  and     ebx, 9C1h
0x18000eaa5  or      eax, ebx
0x18000eaa7  mov     [rdi], eax
0x18000eaa9  mov     rbx, [rsp+38h+arg_10]
0x18000eaae  mov     rax, rdi
0x18000eab1  add     rsp, 20h
0x18000eab5  pop     rdi
0x18000eab6  pop     rsi
0x18000eab7  pop     rbp
0x18000eab8  retn
```

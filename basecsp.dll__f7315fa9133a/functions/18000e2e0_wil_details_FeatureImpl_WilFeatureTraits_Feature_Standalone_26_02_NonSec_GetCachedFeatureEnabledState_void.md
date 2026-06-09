# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e2e0`
- end: `0x18000e3b9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015df0`

## callees

- `0x18000d7e0`
- `0x18000e2e0`
- `0x18000efc0`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
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
0x18000e2e0  mov     [rsp+arg_10], rbx
0x18000e2e5  mov     [rsp+arg_0], rcx
0x18000e2ea  push    rbp
0x18000e2eb  push    rsi
0x18000e2ec  push    rdi
0x18000e2ed  sub     rsp, 20h
0x18000e2f1  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000e2f8  mov     rdi, rdx
0x18000e2fb  mov     qword ptr [rdx], 0
0x18000e302  mov     eax, [rsi]
0x18000e304  mov     [rdx], eax
0x18000e306  and     eax, 6
0x18000e309  cmp     al, 6
0x18000e30b  jz      loc_18000E3A9
0x18000e311  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e316  lea     r8, [rsp+38h+arg_0]
0x18000e31b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e323  lea     rdx, [rsp+38h+arg_8]
0x18000e328  mov     ebp, eax
0x18000e32a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000e32f  mov     eax, [rdi]
0x18000e331  mov     rbx, [rsp+38h+arg_8]
0x18000e336  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e33b  mov     edx, eax
0x18000e33d  mov     [rdi], eax
0x18000e33f  mov     ecx, eax
0x18000e341  jz      short loc_18000E35C
0x18000e343  test    dl, 2
0x18000e346  jnz     short loc_18000E35C
0x18000e348  and     ecx, 0FFFFF63Eh
0x18000e34e  mov     eax, ebx
0x18000e350  and     eax, 9C1h
0x18000e355  or      ecx, eax
0x18000e357  or      ecx, 2
0x18000e35a  mov     [rdi], ecx
0x18000e35c  mov     r8d, edx
0x18000e35f  and     r8d, 4
0x18000e363  jnz     short loc_18000E377
0x18000e365  btr     ecx, 0Ah
0x18000e369  mov     eax, ebx
0x18000e36b  and     eax, 400h
0x18000e370  or      ecx, eax
0x18000e372  or      ecx, 4
0x18000e375  mov     [rdi], ecx
0x18000e377  mov     eax, edx
0x18000e379  lock cmpxchg [rsi], ecx
0x18000e37d  jnz     short loc_18000E336
0x18000e37f  test    r8d, r8d
0x18000e382  jnz     short loc_18000E394
0x18000e384  mov     r8d, ebp
0x18000e387  mov     edx, 3
0x18000e38c  mov     rcx, rsi
0x18000e38f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e394  mov     eax, [rdi]
0x18000e396  test    al, 2
0x18000e398  jnz     short loc_18000E3A9
0x18000e39a  and     eax, 0FFFFF63Eh
0x18000e39f  and     ebx, 9C1h
0x18000e3a5  or      eax, ebx
0x18000e3a7  mov     [rdi], eax
0x18000e3a9  mov     rbx, [rsp+38h+arg_10]
0x18000e3ae  mov     rax, rdi
0x18000e3b1  add     rsp, 20h
0x18000e3b5  pop     rdi
0x18000e3b6  pop     rsi
0x18000e3b7  pop     rbp
0x18000e3b8  retn
```

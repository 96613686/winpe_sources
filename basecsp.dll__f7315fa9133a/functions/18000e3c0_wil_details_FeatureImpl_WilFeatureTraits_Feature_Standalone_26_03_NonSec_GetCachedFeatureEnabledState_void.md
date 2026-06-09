# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e3c0`
- end: `0x18000e499`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015e74`

## callees

- `0x18000d7e0`
- `0x18000e3c0`
- `0x18000f03c`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor,
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
0x18000e3c0  mov     [rsp+arg_10], rbx
0x18000e3c5  mov     [rsp+arg_0], rcx
0x18000e3ca  push    rbp
0x18000e3cb  push    rsi
0x18000e3cc  push    rdi
0x18000e3cd  sub     rsp, 20h
0x18000e3d1  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000e3d8  mov     rdi, rdx
0x18000e3db  mov     qword ptr [rdx], 0
0x18000e3e2  mov     eax, [rsi]
0x18000e3e4  mov     [rdx], eax
0x18000e3e6  and     eax, 6
0x18000e3e9  cmp     al, 6
0x18000e3eb  jz      loc_18000E489
0x18000e3f1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e3f6  lea     r8, [rsp+38h+arg_0]
0x18000e3fb  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e403  lea     rdx, [rsp+38h+arg_8]
0x18000e408  mov     ebp, eax
0x18000e40a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000e40f  mov     eax, [rdi]
0x18000e411  mov     rbx, [rsp+38h+arg_8]
0x18000e416  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e41b  mov     edx, eax
0x18000e41d  mov     [rdi], eax
0x18000e41f  mov     ecx, eax
0x18000e421  jz      short loc_18000E43C
0x18000e423  test    dl, 2
0x18000e426  jnz     short loc_18000E43C
0x18000e428  and     ecx, 0FFFFF63Eh
0x18000e42e  mov     eax, ebx
0x18000e430  and     eax, 9C1h
0x18000e435  or      ecx, eax
0x18000e437  or      ecx, 2
0x18000e43a  mov     [rdi], ecx
0x18000e43c  mov     r8d, edx
0x18000e43f  and     r8d, 4
0x18000e443  jnz     short loc_18000E457
0x18000e445  btr     ecx, 0Ah
0x18000e449  mov     eax, ebx
0x18000e44b  and     eax, 400h
0x18000e450  or      ecx, eax
0x18000e452  or      ecx, 4
0x18000e455  mov     [rdi], ecx
0x18000e457  mov     eax, edx
0x18000e459  lock cmpxchg [rsi], ecx
0x18000e45d  jnz     short loc_18000E416
0x18000e45f  test    r8d, r8d
0x18000e462  jnz     short loc_18000E474
0x18000e464  mov     r8d, ebp
0x18000e467  mov     edx, 3
0x18000e46c  mov     rcx, rsi
0x18000e46f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e474  mov     eax, [rdi]
0x18000e476  test    al, 2
0x18000e478  jnz     short loc_18000E489
0x18000e47a  and     eax, 0FFFFF63Eh
0x18000e47f  and     ebx, 9C1h
0x18000e485  or      eax, ebx
0x18000e487  mov     [rdi], eax
0x18000e489  mov     rbx, [rsp+38h+arg_10]
0x18000e48e  mov     rax, rdi
0x18000e491  add     rsp, 20h
0x18000e495  pop     rdi
0x18000e496  pop     rsi
0x18000e497  pop     rbp
0x18000e498  retn
```

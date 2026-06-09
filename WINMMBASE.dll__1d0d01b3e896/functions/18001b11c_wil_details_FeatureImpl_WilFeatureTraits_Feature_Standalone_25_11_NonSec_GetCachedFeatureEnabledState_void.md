# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b11c`
- end: `0x18001b1f5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c39c`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001b11c`
- `0x18001bb08`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x18001b11c  mov     [rsp+arg_10], rbx
0x18001b121  mov     [rsp+arg_0], rcx
0x18001b126  push    rbp
0x18001b127  push    rsi
0x18001b128  push    rdi
0x18001b129  sub     rsp, 20h
0x18001b12d  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001b134  mov     rdi, rdx
0x18001b137  mov     qword ptr [rdx], 0
0x18001b13e  mov     eax, [rsi]
0x18001b140  mov     [rdx], eax
0x18001b142  and     eax, 6
0x18001b145  cmp     al, 6
0x18001b147  jz      loc_18001B1E5
0x18001b14d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b152  lea     r8, [rsp+38h+arg_0]
0x18001b157  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b15f  lea     rdx, [rsp+38h+arg_8]
0x18001b164  mov     ebp, eax
0x18001b166  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001b16b  mov     eax, [rdi]
0x18001b16d  mov     rbx, [rsp+38h+arg_8]
0x18001b172  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b177  mov     edx, eax
0x18001b179  mov     [rdi], eax
0x18001b17b  mov     ecx, eax
0x18001b17d  jz      short loc_18001B198
0x18001b17f  test    dl, 2
0x18001b182  jnz     short loc_18001B198
0x18001b184  and     ecx, 0FFFFF63Eh
0x18001b18a  mov     eax, ebx
0x18001b18c  and     eax, 9C1h
0x18001b191  or      ecx, eax
0x18001b193  or      ecx, 2
0x18001b196  mov     [rdi], ecx
0x18001b198  mov     r8d, edx
0x18001b19b  and     r8d, 4
0x18001b19f  jnz     short loc_18001B1B3
0x18001b1a1  btr     ecx, 0Ah
0x18001b1a5  mov     eax, ebx
0x18001b1a7  and     eax, 400h
0x18001b1ac  or      ecx, eax
0x18001b1ae  or      ecx, 4
0x18001b1b1  mov     [rdi], ecx
0x18001b1b3  mov     eax, edx
0x18001b1b5  lock cmpxchg [rsi], ecx
0x18001b1b9  jnz     short loc_18001B172
0x18001b1bb  test    r8d, r8d
0x18001b1be  jnz     short loc_18001B1D0
0x18001b1c0  mov     r8d, ebp
0x18001b1c3  mov     edx, 3
0x18001b1c8  mov     rcx, rsi
0x18001b1cb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b1d0  mov     eax, [rdi]
0x18001b1d2  test    al, 2
0x18001b1d4  jnz     short loc_18001B1E5
0x18001b1d6  and     eax, 0FFFFF63Eh
0x18001b1db  and     ebx, 9C1h
0x18001b1e1  or      eax, ebx
0x18001b1e3  mov     [rdi], eax
0x18001b1e5  mov     rbx, [rsp+38h+arg_10]
0x18001b1ea  mov     rax, rdi
0x18001b1ed  add     rsp, 20h
0x18001b1f1  pop     rdi
0x18001b1f2  pop     rsi
0x18001b1f3  pop     rbp
0x18001b1f4  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e040`
- end: `0x18000e119`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015c64`

## callees

- `0x18000d7e0`
- `0x18000e040`
- `0x18000ee4c`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x18000e040  mov     [rsp+arg_10], rbx
0x18000e045  mov     [rsp+arg_0], rcx
0x18000e04a  push    rbp
0x18000e04b  push    rsi
0x18000e04c  push    rdi
0x18000e04d  sub     rsp, 20h
0x18000e051  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000e058  mov     rdi, rdx
0x18000e05b  mov     qword ptr [rdx], 0
0x18000e062  mov     eax, [rsi]
0x18000e064  mov     [rdx], eax
0x18000e066  and     eax, 6
0x18000e069  cmp     al, 6
0x18000e06b  jz      loc_18000E109
0x18000e071  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e076  lea     r8, [rsp+38h+arg_0]
0x18000e07b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e083  lea     rdx, [rsp+38h+arg_8]
0x18000e088  mov     ebp, eax
0x18000e08a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000e08f  mov     eax, [rdi]
0x18000e091  mov     rbx, [rsp+38h+arg_8]
0x18000e096  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e09b  mov     edx, eax
0x18000e09d  mov     [rdi], eax
0x18000e09f  mov     ecx, eax
0x18000e0a1  jz      short loc_18000E0BC
0x18000e0a3  test    dl, 2
0x18000e0a6  jnz     short loc_18000E0BC
0x18000e0a8  and     ecx, 0FFFFF63Eh
0x18000e0ae  mov     eax, ebx
0x18000e0b0  and     eax, 9C1h
0x18000e0b5  or      ecx, eax
0x18000e0b7  or      ecx, 2
0x18000e0ba  mov     [rdi], ecx
0x18000e0bc  mov     r8d, edx
0x18000e0bf  and     r8d, 4
0x18000e0c3  jnz     short loc_18000E0D7
0x18000e0c5  btr     ecx, 0Ah
0x18000e0c9  mov     eax, ebx
0x18000e0cb  and     eax, 400h
0x18000e0d0  or      ecx, eax
0x18000e0d2  or      ecx, 4
0x18000e0d5  mov     [rdi], ecx
0x18000e0d7  mov     eax, edx
0x18000e0d9  lock cmpxchg [rsi], ecx
0x18000e0dd  jnz     short loc_18000E096
0x18000e0df  test    r8d, r8d
0x18000e0e2  jnz     short loc_18000E0F4
0x18000e0e4  mov     r8d, ebp
0x18000e0e7  mov     edx, 3
0x18000e0ec  mov     rcx, rsi
0x18000e0ef  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e0f4  mov     eax, [rdi]
0x18000e0f6  test    al, 2
0x18000e0f8  jnz     short loc_18000E109
0x18000e0fa  and     eax, 0FFFFF63Eh
0x18000e0ff  and     ebx, 9C1h
0x18000e105  or      eax, ebx
0x18000e107  mov     [rdi], eax
0x18000e109  mov     rbx, [rsp+38h+arg_10]
0x18000e10e  mov     rax, rdi
0x18000e111  add     rsp, 20h
0x18000e115  pop     rdi
0x18000e116  pop     rsi
0x18000e117  pop     rbp
0x18000e118  retn
```

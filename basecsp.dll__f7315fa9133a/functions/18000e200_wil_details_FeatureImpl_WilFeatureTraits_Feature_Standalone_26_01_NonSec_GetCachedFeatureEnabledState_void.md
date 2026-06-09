# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e200`
- end: `0x18000e2d9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015d6c`

## callees

- `0x18000d7e0`
- `0x18000e200`
- `0x18000ef44`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18000e200  mov     [rsp+arg_10], rbx
0x18000e205  mov     [rsp+arg_0], rcx
0x18000e20a  push    rbp
0x18000e20b  push    rsi
0x18000e20c  push    rdi
0x18000e20d  sub     rsp, 20h
0x18000e211  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000e218  mov     rdi, rdx
0x18000e21b  mov     qword ptr [rdx], 0
0x18000e222  mov     eax, [rsi]
0x18000e224  mov     [rdx], eax
0x18000e226  and     eax, 6
0x18000e229  cmp     al, 6
0x18000e22b  jz      loc_18000E2C9
0x18000e231  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e236  lea     r8, [rsp+38h+arg_0]
0x18000e23b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e243  lea     rdx, [rsp+38h+arg_8]
0x18000e248  mov     ebp, eax
0x18000e24a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000e24f  mov     eax, [rdi]
0x18000e251  mov     rbx, [rsp+38h+arg_8]
0x18000e256  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e25b  mov     edx, eax
0x18000e25d  mov     [rdi], eax
0x18000e25f  mov     ecx, eax
0x18000e261  jz      short loc_18000E27C
0x18000e263  test    dl, 2
0x18000e266  jnz     short loc_18000E27C
0x18000e268  and     ecx, 0FFFFF63Eh
0x18000e26e  mov     eax, ebx
0x18000e270  and     eax, 9C1h
0x18000e275  or      ecx, eax
0x18000e277  or      ecx, 2
0x18000e27a  mov     [rdi], ecx
0x18000e27c  mov     r8d, edx
0x18000e27f  and     r8d, 4
0x18000e283  jnz     short loc_18000E297
0x18000e285  btr     ecx, 0Ah
0x18000e289  mov     eax, ebx
0x18000e28b  and     eax, 400h
0x18000e290  or      ecx, eax
0x18000e292  or      ecx, 4
0x18000e295  mov     [rdi], ecx
0x18000e297  mov     eax, edx
0x18000e299  lock cmpxchg [rsi], ecx
0x18000e29d  jnz     short loc_18000E256
0x18000e29f  test    r8d, r8d
0x18000e2a2  jnz     short loc_18000E2B4
0x18000e2a4  mov     r8d, ebp
0x18000e2a7  mov     edx, 3
0x18000e2ac  mov     rcx, rsi
0x18000e2af  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e2b4  mov     eax, [rdi]
0x18000e2b6  test    al, 2
0x18000e2b8  jnz     short loc_18000E2C9
0x18000e2ba  and     eax, 0FFFFF63Eh
0x18000e2bf  and     ebx, 9C1h
0x18000e2c5  or      eax, ebx
0x18000e2c7  mov     [rdi], eax
0x18000e2c9  mov     rbx, [rsp+38h+arg_10]
0x18000e2ce  mov     rax, rdi
0x18000e2d1  add     rsp, 20h
0x18000e2d5  pop     rdi
0x18000e2d6  pop     rsi
0x18000e2d7  pop     rbp
0x18000e2d8  retn
```

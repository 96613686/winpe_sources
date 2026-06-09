# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e4a0`
- end: `0x18000e579`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015ef8`

## callees

- `0x18000d7e0`
- `0x18000e4a0`
- `0x18000f0b8`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor,
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
0x18000e4a0  mov     [rsp+arg_10], rbx
0x18000e4a5  mov     [rsp+arg_0], rcx
0x18000e4aa  push    rbp
0x18000e4ab  push    rsi
0x18000e4ac  push    rdi
0x18000e4ad  sub     rsp, 20h
0x18000e4b1  mov     rsi, cs:Feature_Standalone_26_04_NonSec__descriptor
0x18000e4b8  mov     rdi, rdx
0x18000e4bb  mov     qword ptr [rdx], 0
0x18000e4c2  mov     eax, [rsi]
0x18000e4c4  mov     [rdx], eax
0x18000e4c6  and     eax, 6
0x18000e4c9  cmp     al, 6
0x18000e4cb  jz      loc_18000E569
0x18000e4d1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e4d6  lea     r8, [rsp+38h+arg_0]
0x18000e4db  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e4e3  lea     rdx, [rsp+38h+arg_8]
0x18000e4e8  mov     ebp, eax
0x18000e4ea  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000e4ef  mov     eax, [rdi]
0x18000e4f1  mov     rbx, [rsp+38h+arg_8]
0x18000e4f6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e4fb  mov     edx, eax
0x18000e4fd  mov     [rdi], eax
0x18000e4ff  mov     ecx, eax
0x18000e501  jz      short loc_18000E51C
0x18000e503  test    dl, 2
0x18000e506  jnz     short loc_18000E51C
0x18000e508  and     ecx, 0FFFFF63Eh
0x18000e50e  mov     eax, ebx
0x18000e510  and     eax, 9C1h
0x18000e515  or      ecx, eax
0x18000e517  or      ecx, 2
0x18000e51a  mov     [rdi], ecx
0x18000e51c  mov     r8d, edx
0x18000e51f  and     r8d, 4
0x18000e523  jnz     short loc_18000E537
0x18000e525  btr     ecx, 0Ah
0x18000e529  mov     eax, ebx
0x18000e52b  and     eax, 400h
0x18000e530  or      ecx, eax
0x18000e532  or      ecx, 4
0x18000e535  mov     [rdi], ecx
0x18000e537  mov     eax, edx
0x18000e539  lock cmpxchg [rsi], ecx
0x18000e53d  jnz     short loc_18000E4F6
0x18000e53f  test    r8d, r8d
0x18000e542  jnz     short loc_18000E554
0x18000e544  mov     r8d, ebp
0x18000e547  mov     edx, 3
0x18000e54c  mov     rcx, rsi
0x18000e54f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e554  mov     eax, [rdi]
0x18000e556  test    al, 2
0x18000e558  jnz     short loc_18000E569
0x18000e55a  and     eax, 0FFFFF63Eh
0x18000e55f  and     ebx, 9C1h
0x18000e565  or      eax, ebx
0x18000e567  mov     [rdi], eax
0x18000e569  mov     rbx, [rsp+38h+arg_10]
0x18000e56e  mov     rax, rdi
0x18000e571  add     rsp, 20h
0x18000e575  pop     rdi
0x18000e576  pop     rsi
0x18000e577  pop     rbp
0x18000e578  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e120`
- end: `0x18000e1f9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015ce8`

## callees

- `0x18000d7e0`
- `0x18000e120`
- `0x18000eec8`
- `0x1800170d0`

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
0x18000e120  mov     [rsp+arg_10], rbx
0x18000e125  mov     [rsp+arg_0], rcx
0x18000e12a  push    rbp
0x18000e12b  push    rsi
0x18000e12c  push    rdi
0x18000e12d  sub     rsp, 20h
0x18000e131  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000e138  mov     rdi, rdx
0x18000e13b  mov     qword ptr [rdx], 0
0x18000e142  mov     eax, [rsi]
0x18000e144  mov     [rdx], eax
0x18000e146  and     eax, 6
0x18000e149  cmp     al, 6
0x18000e14b  jz      loc_18000E1E9
0x18000e151  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e156  lea     r8, [rsp+38h+arg_0]
0x18000e15b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e163  lea     rdx, [rsp+38h+arg_8]
0x18000e168  mov     ebp, eax
0x18000e16a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000e16f  mov     eax, [rdi]
0x18000e171  mov     rbx, [rsp+38h+arg_8]
0x18000e176  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e17b  mov     edx, eax
0x18000e17d  mov     [rdi], eax
0x18000e17f  mov     ecx, eax
0x18000e181  jz      short loc_18000E19C
0x18000e183  test    dl, 2
0x18000e186  jnz     short loc_18000E19C
0x18000e188  and     ecx, 0FFFFF63Eh
0x18000e18e  mov     eax, ebx
0x18000e190  and     eax, 9C1h
0x18000e195  or      ecx, eax
0x18000e197  or      ecx, 2
0x18000e19a  mov     [rdi], ecx
0x18000e19c  mov     r8d, edx
0x18000e19f  and     r8d, 4
0x18000e1a3  jnz     short loc_18000E1B7
0x18000e1a5  btr     ecx, 0Ah
0x18000e1a9  mov     eax, ebx
0x18000e1ab  and     eax, 400h
0x18000e1b0  or      ecx, eax
0x18000e1b2  or      ecx, 4
0x18000e1b5  mov     [rdi], ecx
0x18000e1b7  mov     eax, edx
0x18000e1b9  lock cmpxchg [rsi], ecx
0x18000e1bd  jnz     short loc_18000E176
0x18000e1bf  test    r8d, r8d
0x18000e1c2  jnz     short loc_18000E1D4
0x18000e1c4  mov     r8d, ebp
0x18000e1c7  mov     edx, 3
0x18000e1cc  mov     rcx, rsi
0x18000e1cf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e1d4  mov     eax, [rdi]
0x18000e1d6  test    al, 2
0x18000e1d8  jnz     short loc_18000E1E9
0x18000e1da  and     eax, 0FFFFF63Eh
0x18000e1df  and     ebx, 9C1h
0x18000e1e5  or      eax, ebx
0x18000e1e7  mov     [rdi], eax
0x18000e1e9  mov     rbx, [rsp+38h+arg_10]
0x18000e1ee  mov     rax, rdi
0x18000e1f1  add     rsp, 20h
0x18000e1f5  pop     rdi
0x18000e1f6  pop     rsi
0x18000e1f7  pop     rbp
0x18000e1f8  retn
```

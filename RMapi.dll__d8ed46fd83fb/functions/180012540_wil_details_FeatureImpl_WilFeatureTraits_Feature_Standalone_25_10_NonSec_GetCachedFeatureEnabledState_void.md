# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012540`
- end: `0x18001262b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015018`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180012540`
- `0x180012cb8`
- `0x180016180`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x180012540  push    rbx
0x180012542  push    rbp
0x180012543  push    rsi
0x180012544  push    rdi
0x180012545  sub     rsp, 48h
0x180012549  mov     rax, cs:__security_cookie
0x180012550  xor     rax, rsp
0x180012553  mov     [rsp+68h+var_38], rax
0x180012558  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001255f  mov     rdi, rdx
0x180012562  mov     qword ptr [rdx], 0
0x180012569  mov     eax, [rsi]
0x18001256b  mov     [rdx], eax
0x18001256d  and     eax, 6
0x180012570  cmp     al, 6
0x180012572  jz      loc_180012612
0x180012578  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001257d  lea     r8, [rsp+68h+var_40]
0x180012582  mov     [rsp+68h+var_40], 0
0x18001258a  lea     rdx, [rsp+68h+var_48]
0x18001258f  mov     ebp, eax
0x180012591  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180012596  mov     eax, [rdi]
0x180012598  mov     rbx, [rsp+68h+var_48]
0x18001259d  cmp     [rsp+68h+var_40], 0
0x1800125a2  mov     edx, eax
0x1800125a4  mov     [rdi], eax
0x1800125a6  mov     ecx, eax
0x1800125a8  jz      short loc_1800125C3
0x1800125aa  test    dl, 2
0x1800125ad  jnz     short loc_1800125C3
0x1800125af  and     ecx, 0FFFFF63Eh
0x1800125b5  mov     eax, ebx
0x1800125b7  and     eax, 9C1h
0x1800125bc  or      ecx, eax
0x1800125be  or      ecx, 2
0x1800125c1  mov     [rdi], ecx
0x1800125c3  mov     r8d, edx
0x1800125c6  and     r8d, 4
0x1800125ca  jnz     short loc_1800125DE
0x1800125cc  btr     ecx, 0Ah
0x1800125d0  mov     eax, ebx
0x1800125d2  and     eax, 400h
0x1800125d7  or      ecx, eax
0x1800125d9  or      ecx, 4
0x1800125dc  mov     [rdi], ecx
0x1800125de  mov     eax, edx
0x1800125e0  lock cmpxchg [rsi], ecx
0x1800125e4  jnz     short loc_18001259D
0x1800125e6  test    r8d, r8d
0x1800125e9  jnz     short loc_1800125FB
0x1800125eb  mov     r8d, ebp
0x1800125ee  mov     edx, 3
0x1800125f3  mov     rcx, rsi
0x1800125f6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800125fb  mov     ecx, [rdi]
0x1800125fd  test    cl, 2
0x180012600  jnz     short loc_180012612
0x180012602  and     ecx, 0FFFFF63Eh
0x180012608  and     ebx, 9C1h
0x18001260e  or      ecx, ebx
0x180012610  mov     [rdi], ecx
0x180012612  mov     rax, rdi
0x180012615  mov     rcx, [rsp+68h+var_38]
0x18001261a  xor     rcx, rsp; StackCookie
0x18001261d  call    __security_check_cookie
0x180012622  add     rsp, 48h
0x180012626  pop     rdi
0x180012627  pop     rsi
0x180012628  pop     rbp
0x180012629  pop     rbx
0x18001262a  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012634`
- end: `0x18001271f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150b4`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180012634`
- `0x180012d34`
- `0x180016180`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x180012634  push    rbx
0x180012636  push    rbp
0x180012637  push    rsi
0x180012638  push    rdi
0x180012639  sub     rsp, 48h
0x18001263d  mov     rax, cs:__security_cookie
0x180012644  xor     rax, rsp
0x180012647  mov     [rsp+68h+var_38], rax
0x18001264c  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180012653  mov     rdi, rdx
0x180012656  mov     qword ptr [rdx], 0
0x18001265d  mov     eax, [rsi]
0x18001265f  mov     [rdx], eax
0x180012661  and     eax, 6
0x180012664  cmp     al, 6
0x180012666  jz      loc_180012706
0x18001266c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012671  lea     r8, [rsp+68h+var_40]
0x180012676  mov     [rsp+68h+var_40], 0
0x18001267e  lea     rdx, [rsp+68h+var_48]
0x180012683  mov     ebp, eax
0x180012685  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001268a  mov     eax, [rdi]
0x18001268c  mov     rbx, [rsp+68h+var_48]
0x180012691  cmp     [rsp+68h+var_40], 0
0x180012696  mov     edx, eax
0x180012698  mov     [rdi], eax
0x18001269a  mov     ecx, eax
0x18001269c  jz      short loc_1800126B7
0x18001269e  test    dl, 2
0x1800126a1  jnz     short loc_1800126B7
0x1800126a3  and     ecx, 0FFFFF63Eh
0x1800126a9  mov     eax, ebx
0x1800126ab  and     eax, 9C1h
0x1800126b0  or      ecx, eax
0x1800126b2  or      ecx, 2
0x1800126b5  mov     [rdi], ecx
0x1800126b7  mov     r8d, edx
0x1800126ba  and     r8d, 4
0x1800126be  jnz     short loc_1800126D2
0x1800126c0  btr     ecx, 0Ah
0x1800126c4  mov     eax, ebx
0x1800126c6  and     eax, 400h
0x1800126cb  or      ecx, eax
0x1800126cd  or      ecx, 4
0x1800126d0  mov     [rdi], ecx
0x1800126d2  mov     eax, edx
0x1800126d4  lock cmpxchg [rsi], ecx
0x1800126d8  jnz     short loc_180012691
0x1800126da  test    r8d, r8d
0x1800126dd  jnz     short loc_1800126EF
0x1800126df  mov     r8d, ebp
0x1800126e2  mov     edx, 3
0x1800126e7  mov     rcx, rsi
0x1800126ea  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800126ef  mov     ecx, [rdi]
0x1800126f1  test    cl, 2
0x1800126f4  jnz     short loc_180012706
0x1800126f6  and     ecx, 0FFFFF63Eh
0x1800126fc  and     ebx, 9C1h
0x180012702  or      ecx, ebx
0x180012704  mov     [rdi], ecx
0x180012706  mov     rax, rdi
0x180012709  mov     rcx, [rsp+68h+var_38]
0x18001270e  xor     rcx, rsp; StackCookie
0x180012711  call    __security_check_cookie
0x180012716  add     rsp, 48h
0x18001271a  pop     rdi
0x18001271b  pop     rsi
0x18001271c  pop     rbp
0x18001271d  pop     rbx
0x18001271e  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012728`
- end: `0x180012813`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015150`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180012728`
- `0x180012db0`
- `0x180016180`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x180012728  push    rbx
0x18001272a  push    rbp
0x18001272b  push    rsi
0x18001272c  push    rdi
0x18001272d  sub     rsp, 48h
0x180012731  mov     rax, cs:__security_cookie
0x180012738  xor     rax, rsp
0x18001273b  mov     [rsp+68h+var_38], rax
0x180012740  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180012747  mov     rdi, rdx
0x18001274a  mov     qword ptr [rdx], 0
0x180012751  mov     eax, [rsi]
0x180012753  mov     [rdx], eax
0x180012755  and     eax, 6
0x180012758  cmp     al, 6
0x18001275a  jz      loc_1800127FA
0x180012760  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012765  lea     r8, [rsp+68h+var_40]
0x18001276a  mov     [rsp+68h+var_40], 0
0x180012772  lea     rdx, [rsp+68h+var_48]
0x180012777  mov     ebp, eax
0x180012779  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18001277e  mov     eax, [rdi]
0x180012780  mov     rbx, [rsp+68h+var_48]
0x180012785  cmp     [rsp+68h+var_40], 0
0x18001278a  mov     edx, eax
0x18001278c  mov     [rdi], eax
0x18001278e  mov     ecx, eax
0x180012790  jz      short loc_1800127AB
0x180012792  test    dl, 2
0x180012795  jnz     short loc_1800127AB
0x180012797  and     ecx, 0FFFFF63Eh
0x18001279d  mov     eax, ebx
0x18001279f  and     eax, 9C1h
0x1800127a4  or      ecx, eax
0x1800127a6  or      ecx, 2
0x1800127a9  mov     [rdi], ecx
0x1800127ab  mov     r8d, edx
0x1800127ae  and     r8d, 4
0x1800127b2  jnz     short loc_1800127C6
0x1800127b4  btr     ecx, 0Ah
0x1800127b8  mov     eax, ebx
0x1800127ba  and     eax, 400h
0x1800127bf  or      ecx, eax
0x1800127c1  or      ecx, 4
0x1800127c4  mov     [rdi], ecx
0x1800127c6  mov     eax, edx
0x1800127c8  lock cmpxchg [rsi], ecx
0x1800127cc  jnz     short loc_180012785
0x1800127ce  test    r8d, r8d
0x1800127d1  jnz     short loc_1800127E3
0x1800127d3  mov     r8d, ebp
0x1800127d6  mov     edx, 3
0x1800127db  mov     rcx, rsi
0x1800127de  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800127e3  mov     ecx, [rdi]
0x1800127e5  test    cl, 2
0x1800127e8  jnz     short loc_1800127FA
0x1800127ea  and     ecx, 0FFFFF63Eh
0x1800127f0  and     ebx, 9C1h
0x1800127f6  or      ecx, ebx
0x1800127f8  mov     [rdi], ecx
0x1800127fa  mov     rax, rdi
0x1800127fd  mov     rcx, [rsp+68h+var_38]
0x180012802  xor     rcx, rsp; StackCookie
0x180012805  call    __security_check_cookie
0x18001280a  add     rsp, 48h
0x18001280e  pop     rdi
0x18001280f  pop     rsi
0x180012810  pop     rbp
0x180012811  pop     rbx
0x180012812  retn
```

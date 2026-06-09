# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000a2a0`
- end: `0x18000a38b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cb18`

## callees

- `0x1800027c0`
- `0x1800099bc`
- `0x18000a2a0`
- `0x18000a45c`
- `0x18000d0e4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000a2a0  push    rbx
0x18000a2a2  push    rbp
0x18000a2a3  push    rsi
0x18000a2a4  push    rdi
0x18000a2a5  sub     rsp, 48h
0x18000a2a9  mov     rax, cs:__security_cookie
0x18000a2b0  xor     rax, rsp
0x18000a2b3  mov     [rsp+68h+var_38], rax
0x18000a2b8  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000a2bf  mov     rdi, rdx
0x18000a2c2  mov     qword ptr [rdx], 0
0x18000a2c9  mov     eax, [rsi]
0x18000a2cb  mov     [rdx], eax
0x18000a2cd  and     eax, 6
0x18000a2d0  cmp     al, 6
0x18000a2d2  jz      loc_18000A372
0x18000a2d8  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a2dd  lea     r8, [rsp+68h+var_40]
0x18000a2e2  mov     [rsp+68h+var_40], 0
0x18000a2ea  lea     rdx, [rsp+68h+var_48]
0x18000a2ef  mov     ebp, eax
0x18000a2f1  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000a2f6  mov     eax, [rdi]
0x18000a2f8  mov     rbx, [rsp+68h+var_48]
0x18000a2fd  cmp     [rsp+68h+var_40], 0
0x18000a302  mov     edx, eax
0x18000a304  mov     [rdi], eax
0x18000a306  mov     ecx, eax
0x18000a308  jz      short loc_18000A323
0x18000a30a  test    dl, 2
0x18000a30d  jnz     short loc_18000A323
0x18000a30f  and     ecx, 0FFFFF63Eh
0x18000a315  mov     eax, ebx
0x18000a317  and     eax, 9C1h
0x18000a31c  or      ecx, eax
0x18000a31e  or      ecx, 2
0x18000a321  mov     [rdi], ecx
0x18000a323  mov     r8d, edx
0x18000a326  and     r8d, 4
0x18000a32a  jnz     short loc_18000A33E
0x18000a32c  btr     ecx, 0Ah
0x18000a330  mov     eax, ebx
0x18000a332  and     eax, 400h
0x18000a337  or      ecx, eax
0x18000a339  or      ecx, 4
0x18000a33c  mov     [rdi], ecx
0x18000a33e  mov     eax, edx
0x18000a340  lock cmpxchg [rsi], ecx
0x18000a344  jnz     short loc_18000A2FD
0x18000a346  test    r8d, r8d
0x18000a349  jnz     short loc_18000A35B
0x18000a34b  mov     r8d, ebp
0x18000a34e  mov     edx, 3
0x18000a353  mov     rcx, rsi
0x18000a356  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a35b  mov     ecx, [rdi]
0x18000a35d  test    cl, 2
0x18000a360  jnz     short loc_18000A372
0x18000a362  and     ecx, 0FFFFF63Eh
0x18000a368  and     ebx, 9C1h
0x18000a36e  or      ecx, ebx
0x18000a370  mov     [rdi], ecx
0x18000a372  mov     rax, rdi
0x18000a375  mov     rcx, [rsp+68h+var_38]
0x18000a37a  xor     rcx, rsp; StackCookie
0x18000a37d  call    __security_check_cookie
0x18000a382  add     rsp, 48h
0x18000a386  pop     rdi
0x18000a387  pop     rsi
0x18000a388  pop     rbp
0x18000a389  pop     rbx
0x18000a38a  retn
```

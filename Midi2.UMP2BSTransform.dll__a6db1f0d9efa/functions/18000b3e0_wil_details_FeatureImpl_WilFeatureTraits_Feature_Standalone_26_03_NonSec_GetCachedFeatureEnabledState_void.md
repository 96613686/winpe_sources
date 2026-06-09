# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b3e0`
- end: `0x18000b54d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bf84`

## callees

- `0x18000ab78`
- `0x18000b3e0`
- `0x18000d258`
- `0x18000f010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599553, 3, &v14);
    }
    else
    {
      v6 = 0;
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor,
        3,
        v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b3e0  mov     [rsp+arg_8], rbx
0x18000b3e5  mov     [rsp+arg_10], rbp
0x18000b3ea  mov     [rsp+arg_0], rcx
0x18000b3ef  push    rsi
0x18000b3f0  push    rdi
0x18000b3f1  push    r15
0x18000b3f3  sub     rsp, 20h
0x18000b3f7  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000b3fe  mov     rbx, rdx
0x18000b401  mov     qword ptr [rdx], 0
0x18000b408  mov     eax, [rsi]
0x18000b40a  mov     [rdx], eax
0x18000b40c  and     eax, 6
0x18000b40f  cmp     al, 6
0x18000b411  jz      loc_18000B537
0x18000b417  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b41c  mov     ebp, eax
0x18000b41e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b426  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b42d  test    rax, rax
0x18000b430  jz      short loc_18000B44A
0x18000b432  lea     r8, [rsp+38h+arg_0]
0x18000b437  mov     edx, 3
0x18000b43c  mov     ecx, 37E2881h
0x18000b441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b446  mov     edx, eax
0x18000b448  jmp     short loc_18000B458
0x18000b44a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b451  test    rax, rax
0x18000b454  jnz     short loc_18000B432
0x18000b456  xor     edx, edx
0x18000b458  mov     r8d, edx
0x18000b45b  mov     eax, edx
0x18000b45d  and     r8d, 0FFFFFF3Fh
0x18000b464  and     edx, 80h
0x18000b46a  mov     ecx, r8d
0x18000b46d  mov     r15d, 40h ; '@'
0x18000b473  and     ecx, 3
0x18000b476  and     eax, r15d
0x18000b479  shl     ecx, 2
0x18000b47c  or      ecx, eax
0x18000b47e  shl     ecx, 2
0x18000b481  or      ecx, edx
0x18000b483  lea     edi, ds:0[rcx*8]
0x18000b48a  test    r8d, r8d
0x18000b48d  jnz     short loc_18000B494
0x18000b48f  mov     eax, r15d
0x18000b492  jmp     short loc_18000B49E
0x18000b494  xor     eax, eax
0x18000b496  cmp     r8d, 2
0x18000b49a  cmovz   eax, r15d
0x18000b49e  or      edi, eax
0x18000b4a0  mov     eax, [rbx]
0x18000b4a2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b4a7  mov     edx, eax
0x18000b4a9  mov     [rbx], eax
0x18000b4ab  jz      short loc_18000B4D7
0x18000b4ad  test    dl, 2
0x18000b4b0  jnz     short loc_18000B4D7
0x18000b4b2  xor     eax, edi
0x18000b4b4  and     eax, 180h
0x18000b4b9  xor     eax, edx
0x18000b4bb  mov     ecx, eax
0x18000b4bd  xor     ecx, edi
0x18000b4bf  and     ecx, r15d
0x18000b4c2  xor     ecx, eax
0x18000b4c4  or      ecx, 1
0x18000b4c7  mov     eax, ecx
0x18000b4c9  xor     eax, edi
0x18000b4cb  and     eax, 800h
0x18000b4d0  xor     eax, ecx
0x18000b4d2  or      eax, 2
0x18000b4d5  mov     [rbx], eax
0x18000b4d7  mov     r8d, edx
0x18000b4da  mov     ecx, eax
0x18000b4dc  and     r8d, 4
0x18000b4e0  jnz     short loc_18000B4F1
0x18000b4e2  xor     ecx, edi
0x18000b4e4  and     ecx, 400h
0x18000b4ea  xor     ecx, eax
0x18000b4ec  or      ecx, 4
0x18000b4ef  mov     [rbx], ecx
0x18000b4f1  mov     eax, edx
0x18000b4f3  lock cmpxchg [rsi], ecx
0x18000b4f7  jnz     short loc_18000B4A2
0x18000b4f9  test    r8d, r8d
0x18000b4fc  jnz     short loc_18000B50E
0x18000b4fe  mov     r8d, ebp
0x18000b501  mov     edx, 3
0x18000b506  mov     rcx, rsi
0x18000b509  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b50e  test    byte ptr [rbx], 2
0x18000b511  jnz     short loc_18000B537
0x18000b513  mov     eax, [rbx]
0x18000b515  xor     eax, edi
0x18000b517  and     eax, 180h
0x18000b51c  xor     eax, [rbx]
0x18000b51e  mov     ecx, eax
0x18000b520  xor     ecx, edi
0x18000b522  and     ecx, r15d
0x18000b525  xor     ecx, eax
0x18000b527  or      ecx, 1
0x18000b52a  mov     eax, ecx
0x18000b52c  xor     eax, edi
0x18000b52e  and     eax, 800h
0x18000b533  xor     eax, ecx
0x18000b535  mov     [rbx], eax
0x18000b537  mov     rbp, [rsp+38h+arg_10]
0x18000b53c  mov     rax, rbx
0x18000b53f  mov     rbx, [rsp+38h+arg_8]
0x18000b544  add     rsp, 20h
0x18000b548  pop     r15
0x18000b54a  pop     rdi
0x18000b54b  pop     rsi
0x18000b54c  retn
```

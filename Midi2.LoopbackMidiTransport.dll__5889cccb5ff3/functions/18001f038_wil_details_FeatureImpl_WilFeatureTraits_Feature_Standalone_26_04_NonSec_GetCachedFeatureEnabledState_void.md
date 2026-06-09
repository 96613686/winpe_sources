# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f038`
- end: `0x18001f1a5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fcbc`

## callees

- `0x18001e65c`
- `0x18001f038`
- `0x180020fe4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599559, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor,
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
0x18001f038  mov     [rsp+arg_8], rbx
0x18001f03d  mov     [rsp+arg_10], rbp
0x18001f042  mov     [rsp+arg_0], rcx
0x18001f047  push    rsi
0x18001f048  push    rdi
0x18001f049  push    r15
0x18001f04b  sub     rsp, 20h
0x18001f04f  mov     rsi, cs:Feature_Standalone_26_04_NonSec__descriptor
0x18001f056  mov     rbx, rdx
0x18001f059  mov     qword ptr [rdx], 0
0x18001f060  mov     eax, [rsi]
0x18001f062  mov     [rdx], eax
0x18001f064  and     eax, 6
0x18001f067  cmp     al, 6
0x18001f069  jz      loc_18001F18F
0x18001f06f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f074  mov     ebp, eax
0x18001f076  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f07e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f085  test    rax, rax
0x18001f088  jz      short loc_18001F0A2
0x18001f08a  lea     r8, [rsp+38h+arg_0]
0x18001f08f  mov     edx, 3
0x18001f094  mov     ecx, 37E2887h
0x18001f099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f09e  mov     edx, eax
0x18001f0a0  jmp     short loc_18001F0B0
0x18001f0a2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001f0a9  test    rax, rax
0x18001f0ac  jnz     short loc_18001F08A
0x18001f0ae  xor     edx, edx
0x18001f0b0  mov     r8d, edx
0x18001f0b3  mov     eax, edx
0x18001f0b5  and     r8d, 0FFFFFF3Fh
0x18001f0bc  and     edx, 80h
0x18001f0c2  mov     ecx, r8d
0x18001f0c5  mov     r15d, 40h ; '@'
0x18001f0cb  and     ecx, 3
0x18001f0ce  and     eax, r15d
0x18001f0d1  shl     ecx, 2
0x18001f0d4  or      ecx, eax
0x18001f0d6  shl     ecx, 2
0x18001f0d9  or      ecx, edx
0x18001f0db  lea     edi, ds:0[rcx*8]
0x18001f0e2  test    r8d, r8d
0x18001f0e5  jnz     short loc_18001F0EC
0x18001f0e7  mov     eax, r15d
0x18001f0ea  jmp     short loc_18001F0F6
0x18001f0ec  xor     eax, eax
0x18001f0ee  cmp     r8d, 2
0x18001f0f2  cmovz   eax, r15d
0x18001f0f6  or      edi, eax
0x18001f0f8  mov     eax, [rbx]
0x18001f0fa  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f0ff  mov     edx, eax
0x18001f101  mov     [rbx], eax
0x18001f103  jz      short loc_18001F12F
0x18001f105  test    dl, 2
0x18001f108  jnz     short loc_18001F12F
0x18001f10a  xor     eax, edi
0x18001f10c  and     eax, 180h
0x18001f111  xor     eax, edx
0x18001f113  mov     ecx, eax
0x18001f115  xor     ecx, edi
0x18001f117  and     ecx, r15d
0x18001f11a  xor     ecx, eax
0x18001f11c  or      ecx, 1
0x18001f11f  mov     eax, ecx
0x18001f121  xor     eax, edi
0x18001f123  and     eax, 800h
0x18001f128  xor     eax, ecx
0x18001f12a  or      eax, 2
0x18001f12d  mov     [rbx], eax
0x18001f12f  mov     r8d, edx
0x18001f132  mov     ecx, eax
0x18001f134  and     r8d, 4
0x18001f138  jnz     short loc_18001F149
0x18001f13a  xor     ecx, edi
0x18001f13c  and     ecx, 400h
0x18001f142  xor     ecx, eax
0x18001f144  or      ecx, 4
0x18001f147  mov     [rbx], ecx
0x18001f149  mov     eax, edx
0x18001f14b  lock cmpxchg [rsi], ecx
0x18001f14f  jnz     short loc_18001F0FA
0x18001f151  test    r8d, r8d
0x18001f154  jnz     short loc_18001F166
0x18001f156  mov     r8d, ebp
0x18001f159  mov     edx, 3
0x18001f15e  mov     rcx, rsi
0x18001f161  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f166  test    byte ptr [rbx], 2
0x18001f169  jnz     short loc_18001F18F
0x18001f16b  mov     eax, [rbx]
0x18001f16d  xor     eax, edi
0x18001f16f  and     eax, 180h
0x18001f174  xor     eax, [rbx]
0x18001f176  mov     ecx, eax
0x18001f178  xor     ecx, edi
0x18001f17a  and     ecx, r15d
0x18001f17d  xor     ecx, eax
0x18001f17f  or      ecx, 1
0x18001f182  mov     eax, ecx
0x18001f184  xor     eax, edi
0x18001f186  and     eax, 800h
0x18001f18b  xor     eax, ecx
0x18001f18d  mov     [rbx], eax
0x18001f18f  mov     rbp, [rsp+38h+arg_10]
0x18001f194  mov     rax, rbx
0x18001f197  mov     rbx, [rsp+38h+arg_8]
0x18001f19c  add     rsp, 20h
0x18001f1a0  pop     r15
0x18001f1a2  pop     rdi
0x18001f1a3  pop     rsi
0x18001f1a4  retn
```

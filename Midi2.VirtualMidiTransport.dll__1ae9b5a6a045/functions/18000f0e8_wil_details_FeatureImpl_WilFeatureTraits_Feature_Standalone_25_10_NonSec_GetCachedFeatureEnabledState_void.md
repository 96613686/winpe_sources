# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f0e8`
- end: `0x18000f255`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010790`

## callees

- `0x18000ee50`
- `0x18000f0e8`
- `0x180011648`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x18000f0e8  mov     [rsp+arg_8], rbx
0x18000f0ed  mov     [rsp+arg_10], rbp
0x18000f0f2  mov     [rsp+arg_0], rcx
0x18000f0f7  push    rsi
0x18000f0f8  push    rdi
0x18000f0f9  push    r15
0x18000f0fb  sub     rsp, 20h
0x18000f0ff  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000f106  mov     rbx, rdx
0x18000f109  mov     qword ptr [rdx], 0
0x18000f110  mov     eax, [rsi]
0x18000f112  mov     [rdx], eax
0x18000f114  and     eax, 6
0x18000f117  cmp     al, 6
0x18000f119  jz      loc_18000F23F
0x18000f11f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f124  mov     ebp, eax
0x18000f126  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f12e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f135  test    rax, rax
0x18000f138  jz      short loc_18000F152
0x18000f13a  lea     r8, [rsp+38h+arg_0]
0x18000f13f  mov     edx, 3
0x18000f144  mov     ecx, 2AF34F8h
0x18000f149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f14e  mov     edx, eax
0x18000f150  jmp     short loc_18000F160
0x18000f152  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f159  test    rax, rax
0x18000f15c  jnz     short loc_18000F13A
0x18000f15e  xor     edx, edx
0x18000f160  mov     r8d, edx
0x18000f163  mov     eax, edx
0x18000f165  and     r8d, 0FFFFFF3Fh
0x18000f16c  and     edx, 80h
0x18000f172  mov     ecx, r8d
0x18000f175  mov     r15d, 40h ; '@'
0x18000f17b  and     ecx, 3
0x18000f17e  and     eax, r15d
0x18000f181  shl     ecx, 2
0x18000f184  or      ecx, eax
0x18000f186  shl     ecx, 2
0x18000f189  or      ecx, edx
0x18000f18b  lea     edi, ds:0[rcx*8]
0x18000f192  test    r8d, r8d
0x18000f195  jnz     short loc_18000F19C
0x18000f197  mov     eax, r15d
0x18000f19a  jmp     short loc_18000F1A6
0x18000f19c  xor     eax, eax
0x18000f19e  cmp     r8d, 2
0x18000f1a2  cmovz   eax, r15d
0x18000f1a6  or      edi, eax
0x18000f1a8  mov     eax, [rbx]
0x18000f1aa  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f1af  mov     edx, eax
0x18000f1b1  mov     [rbx], eax
0x18000f1b3  jz      short loc_18000F1DF
0x18000f1b5  test    dl, 2
0x18000f1b8  jnz     short loc_18000F1DF
0x18000f1ba  xor     eax, edi
0x18000f1bc  and     eax, 180h
0x18000f1c1  xor     eax, edx
0x18000f1c3  mov     ecx, eax
0x18000f1c5  xor     ecx, edi
0x18000f1c7  and     ecx, r15d
0x18000f1ca  xor     ecx, eax
0x18000f1cc  or      ecx, 1
0x18000f1cf  mov     eax, ecx
0x18000f1d1  xor     eax, edi
0x18000f1d3  and     eax, 800h
0x18000f1d8  xor     eax, ecx
0x18000f1da  or      eax, 2
0x18000f1dd  mov     [rbx], eax
0x18000f1df  mov     r8d, edx
0x18000f1e2  mov     ecx, eax
0x18000f1e4  and     r8d, 4
0x18000f1e8  jnz     short loc_18000F1F9
0x18000f1ea  xor     ecx, edi
0x18000f1ec  and     ecx, 400h
0x18000f1f2  xor     ecx, eax
0x18000f1f4  or      ecx, 4
0x18000f1f7  mov     [rbx], ecx
0x18000f1f9  mov     eax, edx
0x18000f1fb  lock cmpxchg [rsi], ecx
0x18000f1ff  jnz     short loc_18000F1AA
0x18000f201  test    r8d, r8d
0x18000f204  jnz     short loc_18000F216
0x18000f206  mov     r8d, ebp
0x18000f209  mov     edx, 3
0x18000f20e  mov     rcx, rsi
0x18000f211  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f216  test    byte ptr [rbx], 2
0x18000f219  jnz     short loc_18000F23F
0x18000f21b  mov     eax, [rbx]
0x18000f21d  xor     eax, edi
0x18000f21f  and     eax, 180h
0x18000f224  xor     eax, [rbx]
0x18000f226  mov     ecx, eax
0x18000f228  xor     ecx, edi
0x18000f22a  and     ecx, r15d
0x18000f22d  xor     ecx, eax
0x18000f22f  or      ecx, 1
0x18000f232  mov     eax, ecx
0x18000f234  xor     eax, edi
0x18000f236  and     eax, 800h
0x18000f23b  xor     eax, ecx
0x18000f23d  mov     [rbx], eax
0x18000f23f  mov     rbp, [rsp+38h+arg_10]
0x18000f244  mov     rax, rbx
0x18000f247  mov     rbx, [rsp+38h+arg_8]
0x18000f24c  add     rsp, 20h
0x18000f250  pop     r15
0x18000f252  pop     rdi
0x18000f253  pop     rsi
0x18000f254  retn
```

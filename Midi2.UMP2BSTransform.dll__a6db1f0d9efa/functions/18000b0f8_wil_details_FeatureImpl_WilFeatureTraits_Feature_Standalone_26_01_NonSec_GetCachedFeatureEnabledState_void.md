# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b0f8`
- end: `0x18000b265`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be14`

## callees

- `0x18000ab78`
- `0x18000b0f8`
- `0x18000d258`
- `0x18000f010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18000b0f8  mov     [rsp+arg_8], rbx
0x18000b0fd  mov     [rsp+arg_10], rbp
0x18000b102  mov     [rsp+arg_0], rcx
0x18000b107  push    rsi
0x18000b108  push    rdi
0x18000b109  push    r15
0x18000b10b  sub     rsp, 20h
0x18000b10f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000b116  mov     rbx, rdx
0x18000b119  mov     qword ptr [rdx], 0
0x18000b120  mov     eax, [rsi]
0x18000b122  mov     [rdx], eax
0x18000b124  and     eax, 6
0x18000b127  cmp     al, 6
0x18000b129  jz      loc_18000B24F
0x18000b12f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b134  mov     ebp, eax
0x18000b136  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b13e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b145  test    rax, rax
0x18000b148  jz      short loc_18000B162
0x18000b14a  lea     r8, [rsp+38h+arg_0]
0x18000b14f  mov     edx, 3
0x18000b154  mov     ecx, 37E286Ch
0x18000b159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b15e  mov     edx, eax
0x18000b160  jmp     short loc_18000B170
0x18000b162  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b169  test    rax, rax
0x18000b16c  jnz     short loc_18000B14A
0x18000b16e  xor     edx, edx
0x18000b170  mov     r8d, edx
0x18000b173  mov     eax, edx
0x18000b175  and     r8d, 0FFFFFF3Fh
0x18000b17c  and     edx, 80h
0x18000b182  mov     ecx, r8d
0x18000b185  mov     r15d, 40h ; '@'
0x18000b18b  and     ecx, 3
0x18000b18e  and     eax, r15d
0x18000b191  shl     ecx, 2
0x18000b194  or      ecx, eax
0x18000b196  shl     ecx, 2
0x18000b199  or      ecx, edx
0x18000b19b  lea     edi, ds:0[rcx*8]
0x18000b1a2  test    r8d, r8d
0x18000b1a5  jnz     short loc_18000B1AC
0x18000b1a7  mov     eax, r15d
0x18000b1aa  jmp     short loc_18000B1B6
0x18000b1ac  xor     eax, eax
0x18000b1ae  cmp     r8d, 2
0x18000b1b2  cmovz   eax, r15d
0x18000b1b6  or      edi, eax
0x18000b1b8  mov     eax, [rbx]
0x18000b1ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b1bf  mov     edx, eax
0x18000b1c1  mov     [rbx], eax
0x18000b1c3  jz      short loc_18000B1EF
0x18000b1c5  test    dl, 2
0x18000b1c8  jnz     short loc_18000B1EF
0x18000b1ca  xor     eax, edi
0x18000b1cc  and     eax, 180h
0x18000b1d1  xor     eax, edx
0x18000b1d3  mov     ecx, eax
0x18000b1d5  xor     ecx, edi
0x18000b1d7  and     ecx, r15d
0x18000b1da  xor     ecx, eax
0x18000b1dc  or      ecx, 1
0x18000b1df  mov     eax, ecx
0x18000b1e1  xor     eax, edi
0x18000b1e3  and     eax, 800h
0x18000b1e8  xor     eax, ecx
0x18000b1ea  or      eax, 2
0x18000b1ed  mov     [rbx], eax
0x18000b1ef  mov     r8d, edx
0x18000b1f2  mov     ecx, eax
0x18000b1f4  and     r8d, 4
0x18000b1f8  jnz     short loc_18000B209
0x18000b1fa  xor     ecx, edi
0x18000b1fc  and     ecx, 400h
0x18000b202  xor     ecx, eax
0x18000b204  or      ecx, 4
0x18000b207  mov     [rbx], ecx
0x18000b209  mov     eax, edx
0x18000b20b  lock cmpxchg [rsi], ecx
0x18000b20f  jnz     short loc_18000B1BA
0x18000b211  test    r8d, r8d
0x18000b214  jnz     short loc_18000B226
0x18000b216  mov     r8d, ebp
0x18000b219  mov     edx, 3
0x18000b21e  mov     rcx, rsi
0x18000b221  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b226  test    byte ptr [rbx], 2
0x18000b229  jnz     short loc_18000B24F
0x18000b22b  mov     eax, [rbx]
0x18000b22d  xor     eax, edi
0x18000b22f  and     eax, 180h
0x18000b234  xor     eax, [rbx]
0x18000b236  mov     ecx, eax
0x18000b238  xor     ecx, edi
0x18000b23a  and     ecx, r15d
0x18000b23d  xor     ecx, eax
0x18000b23f  or      ecx, 1
0x18000b242  mov     eax, ecx
0x18000b244  xor     eax, edi
0x18000b246  and     eax, 800h
0x18000b24b  xor     eax, ecx
0x18000b24d  mov     [rbx], eax
0x18000b24f  mov     rbp, [rsp+38h+arg_10]
0x18000b254  mov     rax, rbx
0x18000b257  mov     rbx, [rsp+38h+arg_8]
0x18000b25c  add     rsp, 20h
0x18000b260  pop     r15
0x18000b262  pop     rdi
0x18000b263  pop     rsi
0x18000b264  retn
```

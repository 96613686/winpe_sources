# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180008410`
- end: `0x18000857d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009060`

## callees

- `0x18000787c`
- `0x180008410`
- `0x180010684`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036797, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v4);
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
0x180008410  mov     [rsp+arg_8], rbx
0x180008415  mov     [rsp+arg_10], rbp
0x18000841a  mov     [rsp+arg_0], rcx
0x18000841f  push    rsi
0x180008420  push    rdi
0x180008421  push    r15
0x180008423  sub     rsp, 20h
0x180008427  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000842e  mov     rbx, rdx
0x180008431  mov     qword ptr [rdx], 0
0x180008438  mov     eax, [rsi]
0x18000843a  mov     [rdx], eax
0x18000843c  and     eax, 6
0x18000843f  cmp     al, 6
0x180008441  jz      loc_180008567
0x180008447  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000844c  mov     ebp, eax
0x18000844e  mov     dword ptr [rsp+38h+arg_0], 0
0x180008456  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000845d  test    rax, rax
0x180008460  jz      short loc_18000847A
0x180008462  lea     r8, [rsp+38h+arg_0]
0x180008467  mov     edx, 3
0x18000846c  mov     ecx, 2AF34FDh
0x180008471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008476  mov     edx, eax
0x180008478  jmp     short loc_180008488
0x18000847a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008481  test    rax, rax
0x180008484  jnz     short loc_180008462
0x180008486  xor     edx, edx
0x180008488  mov     r8d, edx
0x18000848b  mov     eax, edx
0x18000848d  and     r8d, 0FFFFFF3Fh
0x180008494  and     edx, 80h
0x18000849a  mov     ecx, r8d
0x18000849d  mov     r15d, 40h ; '@'
0x1800084a3  and     ecx, 3
0x1800084a6  and     eax, r15d
0x1800084a9  shl     ecx, 2
0x1800084ac  or      ecx, eax
0x1800084ae  shl     ecx, 2
0x1800084b1  or      ecx, edx
0x1800084b3  lea     edi, ds:0[rcx*8]
0x1800084ba  test    r8d, r8d
0x1800084bd  jnz     short loc_1800084C4
0x1800084bf  mov     eax, r15d
0x1800084c2  jmp     short loc_1800084CE
0x1800084c4  xor     eax, eax
0x1800084c6  cmp     r8d, 2
0x1800084ca  cmovz   eax, r15d
0x1800084ce  or      edi, eax
0x1800084d0  mov     eax, [rbx]
0x1800084d2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800084d7  mov     edx, eax
0x1800084d9  mov     [rbx], eax
0x1800084db  jz      short loc_180008507
0x1800084dd  test    dl, 2
0x1800084e0  jnz     short loc_180008507
0x1800084e2  xor     eax, edi
0x1800084e4  and     eax, 180h
0x1800084e9  xor     eax, edx
0x1800084eb  mov     ecx, eax
0x1800084ed  xor     ecx, edi
0x1800084ef  and     ecx, r15d
0x1800084f2  xor     ecx, eax
0x1800084f4  or      ecx, 1
0x1800084f7  mov     eax, ecx
0x1800084f9  xor     eax, edi
0x1800084fb  and     eax, 800h
0x180008500  xor     eax, ecx
0x180008502  or      eax, 2
0x180008505  mov     [rbx], eax
0x180008507  mov     r8d, edx
0x18000850a  mov     ecx, eax
0x18000850c  and     r8d, 4
0x180008510  jnz     short loc_180008521
0x180008512  xor     ecx, edi
0x180008514  and     ecx, 400h
0x18000851a  xor     ecx, eax
0x18000851c  or      ecx, 4
0x18000851f  mov     [rbx], ecx
0x180008521  mov     eax, edx
0x180008523  lock cmpxchg [rsi], ecx
0x180008527  jnz     short loc_1800084D2
0x180008529  test    r8d, r8d
0x18000852c  jnz     short loc_18000853E
0x18000852e  mov     r8d, ebp
0x180008531  mov     edx, 3
0x180008536  mov     rcx, rsi
0x180008539  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000853e  test    byte ptr [rbx], 2
0x180008541  jnz     short loc_180008567
0x180008543  mov     eax, [rbx]
0x180008545  xor     eax, edi
0x180008547  and     eax, 180h
0x18000854c  xor     eax, [rbx]
0x18000854e  mov     ecx, eax
0x180008550  xor     ecx, edi
0x180008552  and     ecx, r15d
0x180008555  xor     ecx, eax
0x180008557  or      ecx, 1
0x18000855a  mov     eax, ecx
0x18000855c  xor     eax, edi
0x18000855e  and     eax, 800h
0x180008563  xor     eax, ecx
0x180008565  mov     [rbx], eax
0x180008567  mov     rbp, [rsp+38h+arg_10]
0x18000856c  mov     rax, rbx
0x18000856f  mov     rbx, [rsp+38h+arg_8]
0x180008574  add     rsp, 20h
0x180008578  pop     r15
0x18000857a  pop     rdi
0x18000857b  pop     rsi
0x18000857c  retn
```

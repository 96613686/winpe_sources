# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180013380`
- end: `0x1800134ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001507c`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013380`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v4);
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
0x180013380  mov     [rsp+arg_8], rbx
0x180013385  mov     [rsp+arg_10], rbp
0x18001338a  mov     [rsp+arg_0], rcx
0x18001338f  push    rsi
0x180013390  push    rdi
0x180013391  push    r15
0x180013393  sub     rsp, 20h
0x180013397  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001339e  mov     rbx, rdx
0x1800133a1  mov     qword ptr [rdx], 0
0x1800133a8  mov     eax, [rsi]
0x1800133aa  mov     [rdx], eax
0x1800133ac  and     eax, 6
0x1800133af  cmp     al, 6
0x1800133b1  jz      loc_1800134D7
0x1800133b7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800133bc  mov     ebp, eax
0x1800133be  mov     dword ptr [rsp+38h+arg_0], 0
0x1800133c6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800133cd  test    rax, rax
0x1800133d0  jz      short loc_1800133EA
0x1800133d2  lea     r8, [rsp+38h+arg_0]
0x1800133d7  mov     edx, 3
0x1800133dc  mov     ecx, 2AF34F8h
0x1800133e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133e6  mov     edx, eax
0x1800133e8  jmp     short loc_1800133F8
0x1800133ea  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800133f1  test    rax, rax
0x1800133f4  jnz     short loc_1800133D2
0x1800133f6  xor     edx, edx
0x1800133f8  mov     r8d, edx
0x1800133fb  mov     eax, edx
0x1800133fd  and     r8d, 0FFFFFF3Fh
0x180013404  and     edx, 80h
0x18001340a  mov     ecx, r8d
0x18001340d  mov     r15d, 40h ; '@'
0x180013413  and     ecx, 3
0x180013416  and     eax, r15d
0x180013419  shl     ecx, 2
0x18001341c  or      ecx, eax
0x18001341e  shl     ecx, 2
0x180013421  or      ecx, edx
0x180013423  lea     edi, ds:0[rcx*8]
0x18001342a  test    r8d, r8d
0x18001342d  jnz     short loc_180013434
0x18001342f  mov     eax, r15d
0x180013432  jmp     short loc_18001343E
0x180013434  xor     eax, eax
0x180013436  cmp     r8d, 2
0x18001343a  cmovz   eax, r15d
0x18001343e  or      edi, eax
0x180013440  mov     eax, [rbx]
0x180013442  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013447  mov     edx, eax
0x180013449  mov     [rbx], eax
0x18001344b  jz      short loc_180013477
0x18001344d  test    dl, 2
0x180013450  jnz     short loc_180013477
0x180013452  xor     eax, edi
0x180013454  and     eax, 180h
0x180013459  xor     eax, edx
0x18001345b  mov     ecx, eax
0x18001345d  xor     ecx, edi
0x18001345f  and     ecx, r15d
0x180013462  xor     ecx, eax
0x180013464  or      ecx, 1
0x180013467  mov     eax, ecx
0x180013469  xor     eax, edi
0x18001346b  and     eax, 800h
0x180013470  xor     eax, ecx
0x180013472  or      eax, 2
0x180013475  mov     [rbx], eax
0x180013477  mov     r8d, edx
0x18001347a  mov     ecx, eax
0x18001347c  and     r8d, 4
0x180013480  jnz     short loc_180013491
0x180013482  xor     ecx, edi
0x180013484  and     ecx, 400h
0x18001348a  xor     ecx, eax
0x18001348c  or      ecx, 4
0x18001348f  mov     [rbx], ecx
0x180013491  mov     eax, edx
0x180013493  lock cmpxchg [rsi], ecx
0x180013497  jnz     short loc_180013442
0x180013499  test    r8d, r8d
0x18001349c  jnz     short loc_1800134AE
0x18001349e  mov     r8d, ebp
0x1800134a1  mov     edx, 3
0x1800134a6  mov     rcx, rsi
0x1800134a9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800134ae  test    byte ptr [rbx], 2
0x1800134b1  jnz     short loc_1800134D7
0x1800134b3  mov     eax, [rbx]
0x1800134b5  xor     eax, edi
0x1800134b7  and     eax, 180h
0x1800134bc  xor     eax, [rbx]
0x1800134be  mov     ecx, eax
0x1800134c0  xor     ecx, edi
0x1800134c2  and     ecx, r15d
0x1800134c5  xor     ecx, eax
0x1800134c7  or      ecx, 1
0x1800134ca  mov     eax, ecx
0x1800134cc  xor     eax, edi
0x1800134ce  and     eax, 800h
0x1800134d3  xor     eax, ecx
0x1800134d5  mov     [rbx], eax
0x1800134d7  mov     rbp, [rsp+38h+arg_10]
0x1800134dc  mov     rax, rbx
0x1800134df  mov     rbx, [rsp+38h+arg_8]
0x1800134e4  add     rsp, 20h
0x1800134e8  pop     r15
0x1800134ea  pop     rdi
0x1800134eb  pop     rsi
0x1800134ec  retn
```

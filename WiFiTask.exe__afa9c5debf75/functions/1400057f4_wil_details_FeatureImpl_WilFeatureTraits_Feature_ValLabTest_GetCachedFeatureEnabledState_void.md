# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1400057f4`
- end: `0x14000596b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005e70`

## callees

- `0x1400049e0`
- `0x1400057f4`
- `0x14000a88c`
- `0x140012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
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
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v4);
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
0x1400057f4  mov     [rsp+arg_8], rbx
0x1400057f9  mov     [rsp+arg_10], rbp
0x1400057fe  mov     [rsp+arg_0], rcx
0x140005803  push    rsi
0x140005804  push    rdi
0x140005805  push    r15
0x140005807  sub     rsp, 20h
0x14000580b  mov     rsi, cs:Feature_ValLabTest__descriptor
0x140005812  mov     rbx, rdx
0x140005815  mov     qword ptr [rdx], 0
0x14000581c  mov     eax, [rsi]
0x14000581e  mov     [rdx], eax
0x140005820  and     eax, 6
0x140005823  cmp     al, 6
0x140005825  jz      loc_140005955
0x14000582b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140005830  mov     ebp, eax
0x140005832  mov     dword ptr [rsp+38h+arg_0], 0
0x14000583a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140005841  test    rax, rax
0x140005844  jz      short loc_14000585E
0x140005846  lea     r8, [rsp+38h+arg_0]
0x14000584b  mov     edx, 3
0x140005850  mov     ecx, 3667CA2h
0x140005855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000585a  mov     edx, eax
0x14000585c  jmp     short loc_14000586C
0x14000585e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005865  test    rax, rax
0x140005868  jnz     short loc_140005846
0x14000586a  xor     edx, edx
0x14000586c  mov     r8d, edx
0x14000586f  mov     eax, edx
0x140005871  and     r8d, 0FFFFFF3Fh
0x140005878  and     edx, 80h
0x14000587e  mov     ecx, r8d
0x140005881  mov     r15d, 40h ; '@'
0x140005887  and     ecx, 3
0x14000588a  and     eax, r15d
0x14000588d  shl     ecx, 2
0x140005890  or      ecx, eax
0x140005892  shl     ecx, 2
0x140005895  or      ecx, edx
0x140005897  lea     edi, ds:0[rcx*8]
0x14000589e  test    r8d, r8d
0x1400058a1  jnz     short loc_1400058A8
0x1400058a3  mov     eax, r15d
0x1400058a6  jmp     short loc_1400058B2
0x1400058a8  xor     eax, eax
0x1400058aa  cmp     r8d, 2
0x1400058ae  cmovz   eax, r15d
0x1400058b2  or      edi, eax
0x1400058b4  mov     eax, [rbx]
0x1400058b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400058bb  mov     edx, eax
0x1400058bd  mov     [rbx], eax
0x1400058bf  jz      short loc_1400058EF
0x1400058c1  test    dl, 2
0x1400058c4  jnz     short loc_1400058EF
0x1400058c6  mov     eax, edi
0x1400058c8  xor     eax, edx
0x1400058ca  and     eax, 180h
0x1400058cf  xor     eax, edx
0x1400058d1  mov     ecx, eax
0x1400058d3  xor     ecx, edi
0x1400058d5  and     ecx, r15d
0x1400058d8  xor     ecx, eax
0x1400058da  or      ecx, 1
0x1400058dd  mov     eax, ecx
0x1400058df  xor     eax, edi
0x1400058e1  and     eax, 800h
0x1400058e6  xor     eax, ecx
0x1400058e8  or      eax, 2
0x1400058eb  mov     [rbx], eax
0x1400058ed  jmp     short loc_1400058F1
0x1400058ef  mov     eax, edx
0x1400058f1  mov     r8d, edx
0x1400058f4  and     r8d, 4
0x1400058f8  jnz     short loc_14000590D
0x1400058fa  mov     ecx, edi
0x1400058fc  xor     ecx, eax
0x1400058fe  and     ecx, 400h
0x140005904  xor     ecx, eax
0x140005906  or      ecx, 4
0x140005909  mov     [rbx], ecx
0x14000590b  jmp     short loc_14000590F
0x14000590d  mov     ecx, eax
0x14000590f  mov     eax, edx
0x140005911  lock cmpxchg [rsi], ecx
0x140005915  jnz     short loc_1400058B6
0x140005917  test    r8d, r8d
0x14000591a  jnz     short loc_14000592C
0x14000591c  mov     r8d, ebp
0x14000591f  mov     edx, 3
0x140005924  mov     rcx, rsi
0x140005927  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000592c  test    byte ptr [rbx], 2
0x14000592f  jnz     short loc_140005955
0x140005931  mov     eax, [rbx]
0x140005933  xor     eax, edi
0x140005935  and     eax, 180h
0x14000593a  xor     eax, [rbx]
0x14000593c  mov     ecx, eax
0x14000593e  xor     ecx, edi
0x140005940  and     ecx, r15d
0x140005943  xor     ecx, eax
0x140005945  or      ecx, 1
0x140005948  mov     eax, ecx
0x14000594a  xor     eax, edi
0x14000594c  and     eax, 800h
0x140005951  xor     eax, ecx
0x140005953  mov     [rbx], eax
0x140005955  mov     rbp, [rsp+38h+arg_10]
0x14000595a  mov     rax, rbx
0x14000595d  mov     rbx, [rsp+38h+arg_8]
0x140005962  add     rsp, 20h
0x140005966  pop     r15
0x140005968  pop     rdi
0x140005969  pop     rsi
0x14000596a  retn
```

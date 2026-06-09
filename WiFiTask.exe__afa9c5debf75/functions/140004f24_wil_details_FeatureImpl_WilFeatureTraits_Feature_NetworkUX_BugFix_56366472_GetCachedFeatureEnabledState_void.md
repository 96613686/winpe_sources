# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::GetCachedFeatureEnabledState(void)

- ea: `0x140004f24`
- end: `0x1400050f1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b5d4`

## callees

- `0x1400049e0`
- `0x140004f24`
- `0x14000a88c`
- `0x14000b710`
- `0x140012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_56366472>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_NetworkUX_BugFix_56366472__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NetworkUX_BugFix_56366472__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56366472, 3, &v20);
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
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_17;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = *(_DWORD *)a2;
  v13 = v8 | v11;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( v14 || (v12 & 2) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v16 = v12
          ^ (v12
           ^ v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ (v12
            ^ v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_NetworkUX_BugFix_56366472__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_NetworkUX_BugFix_56366472__descriptor, 3, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v13
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v13
                    ^ *(_DWORD *)a2
                    ^ (v13
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v13
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v13
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v13
                       ^ *(_BYTE *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140004f24  mov     [rsp+arg_0], rcx
0x140004f29  push    rbx
0x140004f2a  push    rbp
0x140004f2b  push    rsi
0x140004f2c  push    rdi
0x140004f2d  push    r12
0x140004f2f  push    r14
0x140004f31  sub     rsp, 28h
0x140004f35  mov     r14, cs:Feature_NetworkUX_BugFix_56366472__descriptor
0x140004f3c  mov     rdi, rdx
0x140004f3f  mov     qword ptr [rdx], 0
0x140004f46  mov     eax, [r14]
0x140004f49  mov     [rdx], eax
0x140004f4b  and     eax, 6
0x140004f4e  cmp     al, 6
0x140004f50  jz      loc_1400050E1
0x140004f56  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140004f5b  mov     ebp, eax
0x140004f5d  mov     dword ptr [rsp+58h+arg_0], 0
0x140004f65  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140004f6c  test    rax, rax
0x140004f6f  jz      short loc_140004F89
0x140004f71  lea     r8, [rsp+58h+arg_0]
0x140004f76  mov     edx, 3
0x140004f7b  mov     ecx, 35C1588h
0x140004f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f85  mov     edx, eax
0x140004f87  jmp     short loc_140004F97
0x140004f89  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140004f90  test    rax, rax
0x140004f93  jnz     short loc_140004F71
0x140004f95  xor     edx, edx
0x140004f97  mov     r8d, edx
0x140004f9a  mov     eax, edx
0x140004f9c  and     r8d, 0FFFFFF3Fh
0x140004fa3  and     edx, 80h
0x140004fa9  mov     ecx, r8d
0x140004fac  mov     r12d, 40h ; '@'
0x140004fb2  and     ecx, 3
0x140004fb5  and     eax, r12d
0x140004fb8  shl     ecx, 2
0x140004fbb  or      ecx, eax
0x140004fbd  shl     ecx, 2
0x140004fc0  or      ecx, edx
0x140004fc2  lea     ebx, ds:0[rcx*8]
0x140004fc9  test    r8d, r8d
0x140004fcc  jnz     short loc_140004FD3
0x140004fce  mov     eax, r12d
0x140004fd1  jmp     short loc_140004FDD
0x140004fd3  xor     eax, eax
0x140004fd5  cmp     r8d, 2
0x140004fd9  cmovz   eax, r12d
0x140004fdd  or      ebx, eax
0x140004fdf  mov     ecx, 0C00h
0x140004fe4  mov     eax, ebx
0x140004fe6  and     eax, ecx
0x140004fe8  cmp     eax, ecx
0x140004fea  jnz     short loc_140004FF1
0x140004fec  mov     sil, 1
0x140004fef  jmp     short loc_140004FF9
0x140004ff1  xor     sil, sil
0x140004ff4  test    r12b, bl
0x140004ff7  jz      short loc_140005014
0x140004ff9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x140005000  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x140005005  test    sil, sil
0x140005008  jz      short loc_140005016
0x14000500a  test    al, al
0x14000500c  jnz     short loc_140005016
0x14000500e  btr     ebx, 0Ah
0x140005012  jmp     short loc_140005016
0x140005014  xor     al, al
0x140005016  test    r12b, bl
0x140005019  jz      short loc_140005026
0x14000501b  test    al, al
0x14000501d  jz      short loc_140005026
0x14000501f  mov     esi, 1
0x140005024  jmp     short loc_140005028
0x140005026  xor     esi, esi
0x140005028  mov     eax, [rdi]
0x14000502a  or      esi, ebx
0x14000502c  mov     ebx, 180h
0x140005031  cmp     dword ptr [rsp+58h+arg_0], 0
0x140005036  mov     edx, eax
0x140005038  mov     [rdi], eax
0x14000503a  jz      short loc_140005074
0x14000503c  test    dl, 2
0x14000503f  jnz     short loc_140005074
0x140005041  mov     eax, esi
0x140005043  xor     eax, edx
0x140005045  and     eax, ebx
0x140005047  xor     eax, edx
0x140005049  mov     ecx, eax
0x14000504b  xor     ecx, esi
0x14000504d  and     ecx, r12d
0x140005050  xor     ecx, eax
0x140005052  mov     eax, ecx
0x140005054  xor     eax, esi
0x140005056  and     eax, 1
0x140005059  xor     eax, ecx
0x14000505b  mov     r8d, eax
0x14000505e  xor     r8d, esi
0x140005061  and     r8d, 800h
0x140005068  xor     r8d, eax
0x14000506b  or      r8d, 2
0x14000506f  mov     [rdi], r8d
0x140005072  jmp     short loc_140005077
0x140005074  mov     r8d, edx
0x140005077  mov     r9d, edx
0x14000507a  and     r9d, 4
0x14000507e  jnz     short loc_140005095
0x140005080  mov     ecx, esi
0x140005082  xor     ecx, r8d
0x140005085  and     ecx, 400h
0x14000508b  xor     ecx, r8d
0x14000508e  or      ecx, 4
0x140005091  mov     [rdi], ecx
0x140005093  jmp     short loc_140005098
0x140005095  mov     ecx, r8d
0x140005098  mov     eax, edx
0x14000509a  lock cmpxchg [r14], ecx
0x14000509f  jnz     short loc_140005031
0x1400050a1  test    r9d, r9d
0x1400050a4  jnz     short loc_1400050B5
0x1400050a6  mov     r8d, ebp
0x1400050a9  lea     edx, [r9+3]
0x1400050ad  mov     rcx, r14
0x1400050b0  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400050b5  test    byte ptr [rdi], 2
0x1400050b8  jnz     short loc_1400050E1
0x1400050ba  mov     eax, [rdi]
0x1400050bc  xor     eax, esi
0x1400050be  and     eax, ebx
0x1400050c0  xor     eax, [rdi]
0x1400050c2  mov     ecx, eax
0x1400050c4  xor     ecx, esi
0x1400050c6  and     ecx, r12d
0x1400050c9  xor     ecx, eax
0x1400050cb  mov     edx, ecx
0x1400050cd  xor     edx, esi
0x1400050cf  and     edx, 1
0x1400050d2  xor     edx, ecx
0x1400050d4  mov     eax, edx
0x1400050d6  xor     eax, esi
0x1400050d8  and     eax, 800h
0x1400050dd  xor     eax, edx
0x1400050df  mov     [rdi], eax
0x1400050e1  mov     rax, rdi
0x1400050e4  add     rsp, 28h
0x1400050e8  pop     r14
0x1400050ea  pop     r12
0x1400050ec  pop     rdi
0x1400050ed  pop     rsi
0x1400050ee  pop     rbp
0x1400050ef  pop     rbx
0x1400050f0  retn
```

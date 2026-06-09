# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetCachedFeatureEnabledState(void)

- ea: `0x180013cb8`
- end: `0x180013e85`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017930`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000b090`
- `0x180013cb8`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetCachedFeatureEnabledState(
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
  unsigned __int8 IsEnabled; // al
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_RandomLocalAddress__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_RandomLocalAddress__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61736939, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_CLAT_Preview2_RandomLocalAddress__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_CLAT_Preview2_RandomLocalAddress__descriptor,
      3,
      v4);
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
0x180013cb8  mov     [rsp+arg_0], rcx
0x180013cbd  push    rbx
0x180013cbe  push    rbp
0x180013cbf  push    rsi
0x180013cc0  push    rdi
0x180013cc1  push    r12
0x180013cc3  push    r14
0x180013cc5  sub     rsp, 28h
0x180013cc9  mov     r14, cs:Feature_CLAT_Preview2_RandomLocalAddress__descriptor
0x180013cd0  mov     rdi, rdx
0x180013cd3  mov     qword ptr [rdx], 0
0x180013cda  mov     eax, [r14]
0x180013cdd  mov     [rdx], eax
0x180013cdf  and     eax, 6
0x180013ce2  cmp     al, 6
0x180013ce4  jz      loc_180013E75
0x180013cea  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013cef  mov     ebp, eax
0x180013cf1  mov     dword ptr [rsp+58h+arg_0], 0
0x180013cf9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013d00  test    rax, rax
0x180013d03  jz      short loc_180013D1D
0x180013d05  lea     r8, [rsp+58h+arg_0]
0x180013d0a  mov     edx, 3
0x180013d0f  mov     ecx, 3AE07EBh
0x180013d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d19  mov     edx, eax
0x180013d1b  jmp     short loc_180013D2B
0x180013d1d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013d24  test    rax, rax
0x180013d27  jnz     short loc_180013D05
0x180013d29  xor     edx, edx
0x180013d2b  mov     r8d, edx
0x180013d2e  mov     eax, edx
0x180013d30  and     r8d, 0FFFFFF3Fh
0x180013d37  and     edx, 80h
0x180013d3d  mov     ecx, r8d
0x180013d40  mov     r12d, 40h ; '@'
0x180013d46  and     ecx, 3
0x180013d49  and     eax, r12d
0x180013d4c  shl     ecx, 2
0x180013d4f  or      ecx, eax
0x180013d51  shl     ecx, 2
0x180013d54  or      ecx, edx
0x180013d56  lea     ebx, ds:0[rcx*8]
0x180013d5d  test    r8d, r8d
0x180013d60  jnz     short loc_180013D67
0x180013d62  mov     eax, r12d
0x180013d65  jmp     short loc_180013D71
0x180013d67  xor     eax, eax
0x180013d69  cmp     r8d, 2
0x180013d6d  cmovz   eax, r12d
0x180013d71  or      ebx, eax
0x180013d73  mov     ecx, 0C00h
0x180013d78  mov     eax, ebx
0x180013d7a  and     eax, ecx
0x180013d7c  cmp     eax, ecx
0x180013d7e  jnz     short loc_180013D85
0x180013d80  mov     sil, 1
0x180013d83  jmp     short loc_180013D8D
0x180013d85  xor     sil, sil
0x180013d88  test    r12b, bl
0x180013d8b  jz      short loc_180013DA8
0x180013d8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl(void)'::`2'::impl
0x180013d94  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(wil::ReportingKind)
0x180013d99  test    sil, sil
0x180013d9c  jz      short loc_180013DAA
0x180013d9e  test    al, al
0x180013da0  jnz     short loc_180013DAA
0x180013da2  btr     ebx, 0Ah
0x180013da6  jmp     short loc_180013DAA
0x180013da8  xor     al, al
0x180013daa  test    r12b, bl
0x180013dad  jz      short loc_180013DBA
0x180013daf  test    al, al
0x180013db1  jz      short loc_180013DBA
0x180013db3  mov     esi, 1
0x180013db8  jmp     short loc_180013DBC
0x180013dba  xor     esi, esi
0x180013dbc  mov     eax, [rdi]
0x180013dbe  or      esi, ebx
0x180013dc0  mov     ebx, 180h
0x180013dc5  cmp     dword ptr [rsp+58h+arg_0], 0
0x180013dca  mov     edx, eax
0x180013dcc  mov     [rdi], eax
0x180013dce  jz      short loc_180013E08
0x180013dd0  test    dl, 2
0x180013dd3  jnz     short loc_180013E08
0x180013dd5  mov     eax, esi
0x180013dd7  xor     eax, edx
0x180013dd9  and     eax, ebx
0x180013ddb  xor     eax, edx
0x180013ddd  mov     ecx, eax
0x180013ddf  xor     ecx, esi
0x180013de1  and     ecx, r12d
0x180013de4  xor     ecx, eax
0x180013de6  mov     eax, ecx
0x180013de8  xor     eax, esi
0x180013dea  and     eax, 1
0x180013ded  xor     eax, ecx
0x180013def  mov     r8d, eax
0x180013df2  xor     r8d, esi
0x180013df5  and     r8d, 800h
0x180013dfc  xor     r8d, eax
0x180013dff  or      r8d, 2
0x180013e03  mov     [rdi], r8d
0x180013e06  jmp     short loc_180013E0B
0x180013e08  mov     r8d, edx
0x180013e0b  mov     r9d, edx
0x180013e0e  and     r9d, 4
0x180013e12  jnz     short loc_180013E29
0x180013e14  mov     ecx, esi
0x180013e16  xor     ecx, r8d
0x180013e19  and     ecx, 400h
0x180013e1f  xor     ecx, r8d
0x180013e22  or      ecx, 4
0x180013e25  mov     [rdi], ecx
0x180013e27  jmp     short loc_180013E2C
0x180013e29  mov     ecx, r8d
0x180013e2c  mov     eax, edx
0x180013e2e  lock cmpxchg [r14], ecx
0x180013e33  jnz     short loc_180013DC5
0x180013e35  test    r9d, r9d
0x180013e38  jnz     short loc_180013E49
0x180013e3a  mov     r8d, ebp
0x180013e3d  lea     edx, [r9+3]
0x180013e41  mov     rcx, r14
0x180013e44  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013e49  test    byte ptr [rdi], 2
0x180013e4c  jnz     short loc_180013E75
0x180013e4e  mov     eax, [rdi]
0x180013e50  xor     eax, esi
0x180013e52  and     eax, ebx
0x180013e54  xor     eax, [rdi]
0x180013e56  mov     ecx, eax
0x180013e58  xor     ecx, esi
0x180013e5a  and     ecx, r12d
0x180013e5d  xor     ecx, eax
0x180013e5f  mov     edx, ecx
0x180013e61  xor     edx, esi
0x180013e63  and     edx, 1
0x180013e66  xor     edx, ecx
0x180013e68  mov     eax, edx
0x180013e6a  xor     eax, esi
0x180013e6c  and     eax, 800h
0x180013e71  xor     eax, edx
0x180013e73  mov     [rdi], eax
0x180013e75  mov     rax, rdi
0x180013e78  add     rsp, 28h
0x180013e7c  pop     r14
0x180013e7e  pop     r12
0x180013e80  pop     rdi
0x180013e81  pop     rsi
0x180013e82  pop     rbp
0x180013e83  pop     rbx
0x180013e84  retn
```

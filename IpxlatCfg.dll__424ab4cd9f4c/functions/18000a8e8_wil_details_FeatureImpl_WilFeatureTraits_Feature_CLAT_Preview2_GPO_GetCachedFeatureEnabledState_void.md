# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetCachedFeatureEnabledState(void)

- ea: `0x18000a8e8`
- end: `0x18000aab5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac7c`
- `0x18000b12c`
- `0x18000dbe8`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000a8e8`
- `0x18000b090`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_GPO__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_GPO__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(50223335, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Preview2_GPO__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Preview2_GPO__descriptor, 3, v4);
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
0x18000a8e8  mov     [rsp+arg_0], rcx
0x18000a8ed  push    rbx
0x18000a8ee  push    rbp
0x18000a8ef  push    rsi
0x18000a8f0  push    rdi
0x18000a8f1  push    r12
0x18000a8f3  push    r14
0x18000a8f5  sub     rsp, 28h
0x18000a8f9  mov     r14, cs:Feature_CLAT_Preview2_GPO__descriptor
0x18000a900  mov     rdi, rdx
0x18000a903  mov     qword ptr [rdx], 0
0x18000a90a  mov     eax, [r14]
0x18000a90d  mov     [rdx], eax
0x18000a90f  and     eax, 6
0x18000a912  cmp     al, 6
0x18000a914  jz      loc_18000AAA5
0x18000a91a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a91f  mov     ebp, eax
0x18000a921  mov     dword ptr [rsp+58h+arg_0], 0
0x18000a929  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000a930  test    rax, rax
0x18000a933  jz      short loc_18000A94D
0x18000a935  lea     r8, [rsp+58h+arg_0]
0x18000a93a  mov     edx, 3
0x18000a93f  mov     ecx, 2FE58E7h
0x18000a944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a949  mov     edx, eax
0x18000a94b  jmp     short loc_18000A95B
0x18000a94d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000a954  test    rax, rax
0x18000a957  jnz     short loc_18000A935
0x18000a959  xor     edx, edx
0x18000a95b  mov     r8d, edx
0x18000a95e  mov     eax, edx
0x18000a960  and     r8d, 0FFFFFF3Fh
0x18000a967  and     edx, 80h
0x18000a96d  mov     ecx, r8d
0x18000a970  mov     r12d, 40h ; '@'
0x18000a976  and     ecx, 3
0x18000a979  and     eax, r12d
0x18000a97c  shl     ecx, 2
0x18000a97f  or      ecx, eax
0x18000a981  shl     ecx, 2
0x18000a984  or      ecx, edx
0x18000a986  lea     ebx, ds:0[rcx*8]
0x18000a98d  test    r8d, r8d
0x18000a990  jnz     short loc_18000A997
0x18000a992  mov     eax, r12d
0x18000a995  jmp     short loc_18000A9A1
0x18000a997  xor     eax, eax
0x18000a999  cmp     r8d, 2
0x18000a99d  cmovz   eax, r12d
0x18000a9a1  or      ebx, eax
0x18000a9a3  mov     ecx, 0C00h
0x18000a9a8  mov     eax, ebx
0x18000a9aa  and     eax, ecx
0x18000a9ac  cmp     eax, ecx
0x18000a9ae  jnz     short loc_18000A9B5
0x18000a9b0  mov     sil, 1
0x18000a9b3  jmp     short loc_18000A9BD
0x18000a9b5  xor     sil, sil
0x18000a9b8  test    r12b, bl
0x18000a9bb  jz      short loc_18000A9D8
0x18000a9bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl(void)'::`2'::impl
0x18000a9c4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(wil::ReportingKind)
0x18000a9c9  test    sil, sil
0x18000a9cc  jz      short loc_18000A9DA
0x18000a9ce  test    al, al
0x18000a9d0  jnz     short loc_18000A9DA
0x18000a9d2  btr     ebx, 0Ah
0x18000a9d6  jmp     short loc_18000A9DA
0x18000a9d8  xor     al, al
0x18000a9da  test    r12b, bl
0x18000a9dd  jz      short loc_18000A9EA
0x18000a9df  test    al, al
0x18000a9e1  jz      short loc_18000A9EA
0x18000a9e3  mov     esi, 1
0x18000a9e8  jmp     short loc_18000A9EC
0x18000a9ea  xor     esi, esi
0x18000a9ec  mov     eax, [rdi]
0x18000a9ee  or      esi, ebx
0x18000a9f0  mov     ebx, 180h
0x18000a9f5  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000a9fa  mov     edx, eax
0x18000a9fc  mov     [rdi], eax
0x18000a9fe  jz      short loc_18000AA38
0x18000aa00  test    dl, 2
0x18000aa03  jnz     short loc_18000AA38
0x18000aa05  mov     eax, esi
0x18000aa07  xor     eax, edx
0x18000aa09  and     eax, ebx
0x18000aa0b  xor     eax, edx
0x18000aa0d  mov     ecx, eax
0x18000aa0f  xor     ecx, esi
0x18000aa11  and     ecx, r12d
0x18000aa14  xor     ecx, eax
0x18000aa16  mov     eax, ecx
0x18000aa18  xor     eax, esi
0x18000aa1a  and     eax, 1
0x18000aa1d  xor     eax, ecx
0x18000aa1f  mov     r8d, eax
0x18000aa22  xor     r8d, esi
0x18000aa25  and     r8d, 800h
0x18000aa2c  xor     r8d, eax
0x18000aa2f  or      r8d, 2
0x18000aa33  mov     [rdi], r8d
0x18000aa36  jmp     short loc_18000AA3B
0x18000aa38  mov     r8d, edx
0x18000aa3b  mov     r9d, edx
0x18000aa3e  and     r9d, 4
0x18000aa42  jnz     short loc_18000AA59
0x18000aa44  mov     ecx, esi
0x18000aa46  xor     ecx, r8d
0x18000aa49  and     ecx, 400h
0x18000aa4f  xor     ecx, r8d
0x18000aa52  or      ecx, 4
0x18000aa55  mov     [rdi], ecx
0x18000aa57  jmp     short loc_18000AA5C
0x18000aa59  mov     ecx, r8d
0x18000aa5c  mov     eax, edx
0x18000aa5e  lock cmpxchg [r14], ecx
0x18000aa63  jnz     short loc_18000A9F5
0x18000aa65  test    r9d, r9d
0x18000aa68  jnz     short loc_18000AA79
0x18000aa6a  mov     r8d, ebp
0x18000aa6d  lea     edx, [r9+3]
0x18000aa71  mov     rcx, r14
0x18000aa74  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000aa79  test    byte ptr [rdi], 2
0x18000aa7c  jnz     short loc_18000AAA5
0x18000aa7e  mov     eax, [rdi]
0x18000aa80  xor     eax, esi
0x18000aa82  and     eax, ebx
0x18000aa84  xor     eax, [rdi]
0x18000aa86  mov     ecx, eax
0x18000aa88  xor     ecx, esi
0x18000aa8a  and     ecx, r12d
0x18000aa8d  xor     ecx, eax
0x18000aa8f  mov     edx, ecx
0x18000aa91  xor     edx, esi
0x18000aa93  and     edx, 1
0x18000aa96  xor     edx, ecx
0x18000aa98  mov     eax, edx
0x18000aa9a  xor     eax, esi
0x18000aa9c  and     eax, 800h
0x18000aaa1  xor     eax, edx
0x18000aaa3  mov     [rdi], eax
0x18000aaa5  mov     rax, rdi
0x18000aaa8  add     rsp, 28h
0x18000aaac  pop     r14
0x18000aaae  pop     r12
0x18000aab0  pop     rdi
0x18000aab1  pop     rsi
0x18000aab2  pop     rbp
0x18000aab3  pop     rbx
0x18000aab4  retn
```

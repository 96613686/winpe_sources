# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::GetCachedFeatureEnabledState(void)

- ea: `0x18000a714`
- end: `0x18000a8e1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b090`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000a714`
- `0x18000aff4`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58583658, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Preview2__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Preview2__descriptor, 3, v4);
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
0x18000a714  mov     [rsp+arg_0], rcx
0x18000a719  push    rbx
0x18000a71a  push    rbp
0x18000a71b  push    rsi
0x18000a71c  push    rdi
0x18000a71d  push    r12
0x18000a71f  push    r14
0x18000a721  sub     rsp, 28h
0x18000a725  mov     r14, cs:Feature_CLAT_Preview2__descriptor
0x18000a72c  mov     rdi, rdx
0x18000a72f  mov     qword ptr [rdx], 0
0x18000a736  mov     eax, [r14]
0x18000a739  mov     [rdx], eax
0x18000a73b  and     eax, 6
0x18000a73e  cmp     al, 6
0x18000a740  jz      loc_18000A8D1
0x18000a746  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a74b  mov     ebp, eax
0x18000a74d  mov     dword ptr [rsp+58h+arg_0], 0
0x18000a755  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000a75c  test    rax, rax
0x18000a75f  jz      short loc_18000A779
0x18000a761  lea     r8, [rsp+58h+arg_0]
0x18000a766  mov     edx, 3
0x18000a76b  mov     ecx, 37DEA6Ah
0x18000a770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a775  mov     edx, eax
0x18000a777  jmp     short loc_18000A787
0x18000a779  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000a780  test    rax, rax
0x18000a783  jnz     short loc_18000A761
0x18000a785  xor     edx, edx
0x18000a787  mov     r8d, edx
0x18000a78a  mov     eax, edx
0x18000a78c  and     r8d, 0FFFFFF3Fh
0x18000a793  and     edx, 80h
0x18000a799  mov     ecx, r8d
0x18000a79c  mov     r12d, 40h ; '@'
0x18000a7a2  and     ecx, 3
0x18000a7a5  and     eax, r12d
0x18000a7a8  shl     ecx, 2
0x18000a7ab  or      ecx, eax
0x18000a7ad  shl     ecx, 2
0x18000a7b0  or      ecx, edx
0x18000a7b2  lea     ebx, ds:0[rcx*8]
0x18000a7b9  test    r8d, r8d
0x18000a7bc  jnz     short loc_18000A7C3
0x18000a7be  mov     eax, r12d
0x18000a7c1  jmp     short loc_18000A7CD
0x18000a7c3  xor     eax, eax
0x18000a7c5  cmp     r8d, 2
0x18000a7c9  cmovz   eax, r12d
0x18000a7cd  or      ebx, eax
0x18000a7cf  mov     ecx, 0C00h
0x18000a7d4  mov     eax, ebx
0x18000a7d6  and     eax, ecx
0x18000a7d8  cmp     eax, ecx
0x18000a7da  jnz     short loc_18000A7E1
0x18000a7dc  mov     sil, 1
0x18000a7df  jmp     short loc_18000A7E9
0x18000a7e1  xor     sil, sil
0x18000a7e4  test    r12b, bl
0x18000a7e7  jz      short loc_18000A804
0x18000a7e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Core@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl(void)'::`2'::impl
0x18000a7f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled(wil::ReportingKind)
0x18000a7f5  test    sil, sil
0x18000a7f8  jz      short loc_18000A806
0x18000a7fa  test    al, al
0x18000a7fc  jnz     short loc_18000A806
0x18000a7fe  btr     ebx, 0Ah
0x18000a802  jmp     short loc_18000A806
0x18000a804  xor     al, al
0x18000a806  test    r12b, bl
0x18000a809  jz      short loc_18000A816
0x18000a80b  test    al, al
0x18000a80d  jz      short loc_18000A816
0x18000a80f  mov     esi, 1
0x18000a814  jmp     short loc_18000A818
0x18000a816  xor     esi, esi
0x18000a818  mov     eax, [rdi]
0x18000a81a  or      esi, ebx
0x18000a81c  mov     ebx, 180h
0x18000a821  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000a826  mov     edx, eax
0x18000a828  mov     [rdi], eax
0x18000a82a  jz      short loc_18000A864
0x18000a82c  test    dl, 2
0x18000a82f  jnz     short loc_18000A864
0x18000a831  mov     eax, esi
0x18000a833  xor     eax, edx
0x18000a835  and     eax, ebx
0x18000a837  xor     eax, edx
0x18000a839  mov     ecx, eax
0x18000a83b  xor     ecx, esi
0x18000a83d  and     ecx, r12d
0x18000a840  xor     ecx, eax
0x18000a842  mov     eax, ecx
0x18000a844  xor     eax, esi
0x18000a846  and     eax, 1
0x18000a849  xor     eax, ecx
0x18000a84b  mov     r8d, eax
0x18000a84e  xor     r8d, esi
0x18000a851  and     r8d, 800h
0x18000a858  xor     r8d, eax
0x18000a85b  or      r8d, 2
0x18000a85f  mov     [rdi], r8d
0x18000a862  jmp     short loc_18000A867
0x18000a864  mov     r8d, edx
0x18000a867  mov     r9d, edx
0x18000a86a  and     r9d, 4
0x18000a86e  jnz     short loc_18000A885
0x18000a870  mov     ecx, esi
0x18000a872  xor     ecx, r8d
0x18000a875  and     ecx, 400h
0x18000a87b  xor     ecx, r8d
0x18000a87e  or      ecx, 4
0x18000a881  mov     [rdi], ecx
0x18000a883  jmp     short loc_18000A888
0x18000a885  mov     ecx, r8d
0x18000a888  mov     eax, edx
0x18000a88a  lock cmpxchg [r14], ecx
0x18000a88f  jnz     short loc_18000A821
0x18000a891  test    r9d, r9d
0x18000a894  jnz     short loc_18000A8A5
0x18000a896  mov     r8d, ebp
0x18000a899  lea     edx, [r9+3]
0x18000a89d  mov     rcx, r14
0x18000a8a0  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a8a5  test    byte ptr [rdi], 2
0x18000a8a8  jnz     short loc_18000A8D1
0x18000a8aa  mov     eax, [rdi]
0x18000a8ac  xor     eax, esi
0x18000a8ae  and     eax, ebx
0x18000a8b0  xor     eax, [rdi]
0x18000a8b2  mov     ecx, eax
0x18000a8b4  xor     ecx, esi
0x18000a8b6  and     ecx, r12d
0x18000a8b9  xor     ecx, eax
0x18000a8bb  mov     edx, ecx
0x18000a8bd  xor     edx, esi
0x18000a8bf  and     edx, 1
0x18000a8c2  xor     edx, ecx
0x18000a8c4  mov     eax, edx
0x18000a8c6  xor     eax, esi
0x18000a8c8  and     eax, 800h
0x18000a8cd  xor     eax, edx
0x18000a8cf  mov     [rdi], eax
0x18000a8d1  mov     rax, rdi
0x18000a8d4  add     rsp, 28h
0x18000a8d8  pop     r14
0x18000a8da  pop     r12
0x18000a8dc  pop     rdi
0x18000a8dd  pop     rsi
0x18000a8de  pop     rbp
0x18000a8df  pop     rbx
0x18000a8e0  retn
```

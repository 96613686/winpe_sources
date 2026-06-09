# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetCachedFeatureEnabledState(void)

- ea: `0x14000a694`
- end: `0x14000a85c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000af6c`

## callees

- `0x140004568`
- `0x140007e64`
- `0x14000a694`
- `0x14000b00c`
- `0x14000c010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UsageAndQualityInsights__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UsageAndQualityInsights__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(57878850, 3, &v20);
  }
  else
  {
    v6 = 0;
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_11:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_15;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_11;
  IsEnabled = 0;
LABEL_15:
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UsageAndQualityInsights__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UsageAndQualityInsights__descriptor, 3, v4);
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
0x14000a694  mov     [rsp+arg_0], rcx
0x14000a699  push    rbx
0x14000a69a  push    rbp
0x14000a69b  push    rsi
0x14000a69c  push    rdi
0x14000a69d  push    r12
0x14000a69f  push    r14
0x14000a6a1  sub     rsp, 28h
0x14000a6a5  mov     r14, cs:Feature_UsageAndQualityInsights__descriptor
0x14000a6ac  mov     rdi, rdx
0x14000a6af  mov     qword ptr [rdx], 0
0x14000a6b6  mov     eax, [r14]
0x14000a6b9  mov     [rdx], eax
0x14000a6bb  and     eax, 6
0x14000a6be  cmp     al, 6
0x14000a6c0  jz      loc_14000A84C
0x14000a6c6  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000a6cb  mov     ebp, eax
0x14000a6cd  mov     dword ptr [rsp+58h+arg_0], 0
0x14000a6d5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000a6dc  test    rax, rax
0x14000a6df  jz      short loc_14000A6F9
0x14000a6e1  lea     r8, [rsp+58h+arg_0]
0x14000a6e6  mov     edx, 3
0x14000a6eb  mov     ecx, 3732942h
0x14000a6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6f5  mov     edx, eax
0x14000a6f7  jmp     short loc_14000A707
0x14000a6f9  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000a700  test    rax, rax
0x14000a703  jnz     short loc_14000A6E1
0x14000a705  xor     edx, edx
0x14000a707  mov     r8d, edx
0x14000a70a  mov     eax, edx
0x14000a70c  and     r8d, 0FFFFFF3Fh
0x14000a713  and     edx, 80h
0x14000a719  mov     ecx, r8d
0x14000a71c  mov     r12d, 40h ; '@'
0x14000a722  and     ecx, 3
0x14000a725  and     eax, r12d
0x14000a728  shl     ecx, 2
0x14000a72b  or      ecx, eax
0x14000a72d  xor     eax, eax
0x14000a72f  shl     ecx, 2
0x14000a732  or      ecx, edx
0x14000a734  lea     ebx, ds:0[rcx*8]
0x14000a73b  test    r8d, r8d
0x14000a73e  jz      short loc_14000A748
0x14000a740  cmp     r8d, 2
0x14000a744  cmovz   eax, r12d
0x14000a748  or      ebx, eax
0x14000a74a  mov     ecx, 0C00h
0x14000a74f  mov     eax, ebx
0x14000a751  and     eax, ecx
0x14000a753  cmp     eax, ecx
0x14000a755  jnz     short loc_14000A75C
0x14000a757  mov     sil, 1
0x14000a75a  jmp     short loc_14000A764
0x14000a75c  xor     sil, sil
0x14000a75f  test    r12b, bl
0x14000a762  jz      short loc_14000A77F
0x14000a764  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x14000a76b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x14000a770  test    sil, sil
0x14000a773  jz      short loc_14000A781
0x14000a775  test    al, al
0x14000a777  jnz     short loc_14000A781
0x14000a779  btr     ebx, 0Ah
0x14000a77d  jmp     short loc_14000A781
0x14000a77f  xor     al, al
0x14000a781  test    r12b, bl
0x14000a784  jz      short loc_14000A791
0x14000a786  test    al, al
0x14000a788  jz      short loc_14000A791
0x14000a78a  mov     esi, 1
0x14000a78f  jmp     short loc_14000A793
0x14000a791  xor     esi, esi
0x14000a793  mov     eax, [rdi]
0x14000a795  or      esi, ebx
0x14000a797  mov     ebx, 180h
0x14000a79c  cmp     dword ptr [rsp+58h+arg_0], 0
0x14000a7a1  mov     edx, eax
0x14000a7a3  mov     [rdi], eax
0x14000a7a5  jz      short loc_14000A7DF
0x14000a7a7  test    dl, 2
0x14000a7aa  jnz     short loc_14000A7DF
0x14000a7ac  mov     eax, esi
0x14000a7ae  xor     eax, edx
0x14000a7b0  and     eax, ebx
0x14000a7b2  xor     eax, edx
0x14000a7b4  mov     ecx, eax
0x14000a7b6  xor     ecx, esi
0x14000a7b8  and     ecx, r12d
0x14000a7bb  xor     ecx, eax
0x14000a7bd  mov     eax, ecx
0x14000a7bf  xor     eax, esi
0x14000a7c1  and     eax, 1
0x14000a7c4  xor     eax, ecx
0x14000a7c6  mov     r8d, eax
0x14000a7c9  xor     r8d, esi
0x14000a7cc  and     r8d, 800h
0x14000a7d3  xor     r8d, eax
0x14000a7d6  or      r8d, 2
0x14000a7da  mov     [rdi], r8d
0x14000a7dd  jmp     short loc_14000A7E2
0x14000a7df  mov     r8d, edx
0x14000a7e2  mov     r9d, edx
0x14000a7e5  and     r9d, 4
0x14000a7e9  jnz     short loc_14000A800
0x14000a7eb  mov     ecx, esi
0x14000a7ed  xor     ecx, r8d
0x14000a7f0  and     ecx, 400h
0x14000a7f6  xor     ecx, r8d
0x14000a7f9  or      ecx, 4
0x14000a7fc  mov     [rdi], ecx
0x14000a7fe  jmp     short loc_14000A803
0x14000a800  mov     ecx, r8d
0x14000a803  mov     eax, edx
0x14000a805  lock cmpxchg [r14], ecx
0x14000a80a  jnz     short loc_14000A79C
0x14000a80c  test    r9d, r9d
0x14000a80f  jnz     short loc_14000A820
0x14000a811  mov     r8d, ebp
0x14000a814  lea     edx, [r9+3]
0x14000a818  mov     rcx, r14
0x14000a81b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000a820  test    byte ptr [rdi], 2
0x14000a823  jnz     short loc_14000A84C
0x14000a825  mov     eax, [rdi]
0x14000a827  xor     eax, esi
0x14000a829  and     eax, ebx
0x14000a82b  xor     eax, [rdi]
0x14000a82d  mov     ecx, eax
0x14000a82f  xor     ecx, esi
0x14000a831  and     ecx, r12d
0x14000a834  xor     ecx, eax
0x14000a836  mov     edx, ecx
0x14000a838  xor     edx, esi
0x14000a83a  and     edx, 1
0x14000a83d  xor     edx, ecx
0x14000a83f  mov     eax, edx
0x14000a841  xor     eax, esi
0x14000a843  and     eax, 800h
0x14000a848  xor     eax, edx
0x14000a84a  mov     [rdi], eax
0x14000a84c  mov     rax, rdi
0x14000a84f  add     rsp, 28h
0x14000a853  pop     r14
0x14000a855  pop     r12
0x14000a857  pop     rdi
0x14000a858  pop     rsi
0x14000a859  pop     rbp
0x14000a85a  pop     rbx
0x14000a85b  retn
```

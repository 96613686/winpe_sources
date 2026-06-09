# wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD>::GetCachedFeatureEnabledState(void)

- ea: `0x180016eb4`
- end: `0x180017095`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_KSOD@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `481`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001afa4`
- `0x180021af4`

## callees

- `0x180003520`
- `0x180016060`
- `0x180016eb4`
- `0x18001c760`
- `0x180021b30`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, int *); // rax
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
  int v20; // [rsp+20h] [rbp-48h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_KSOD__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_KSOD__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v20 = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(34912776, 3, &v20);
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
    v14 = v20 == 0;
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_KSOD__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_KSOD__descriptor, 3, v4);
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
0x180016eb4  push    rbx
0x180016eb6  push    rbp
0x180016eb7  push    rsi
0x180016eb8  push    rdi
0x180016eb9  push    r12
0x180016ebb  push    r14
0x180016ebd  sub     rsp, 38h
0x180016ec1  mov     rax, cs:__security_cookie
0x180016ec8  xor     rax, rsp
0x180016ecb  mov     [rsp+68h+var_40], rax
0x180016ed0  mov     r14, cs:Feature_KSOD__descriptor
0x180016ed7  mov     rdi, rdx
0x180016eda  mov     qword ptr [rdx], 0
0x180016ee1  mov     eax, [r14]
0x180016ee4  mov     [rdx], eax
0x180016ee6  and     eax, 6
0x180016ee9  cmp     al, 6
0x180016eeb  jz      loc_180017078
0x180016ef1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016ef6  mov     ebp, eax
0x180016ef8  mov     [rsp+68h+var_48], 0
0x180016f00  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180016f07  test    rax, rax
0x180016f0a  jz      short loc_180016F24
0x180016f0c  lea     r8, [rsp+68h+var_48]
0x180016f11  mov     edx, 3
0x180016f16  mov     ecx, 214BA08h
0x180016f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f20  mov     edx, eax
0x180016f22  jmp     short loc_180016F32
0x180016f24  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180016f2b  test    rax, rax
0x180016f2e  jnz     short loc_180016F0C
0x180016f30  xor     edx, edx
0x180016f32  mov     r8d, edx
0x180016f35  mov     eax, edx
0x180016f37  and     r8d, 0FFFFFF3Fh
0x180016f3e  and     edx, 80h
0x180016f44  mov     ecx, r8d
0x180016f47  mov     r12d, 40h ; '@'
0x180016f4d  and     ecx, 3
0x180016f50  and     eax, r12d
0x180016f53  shl     ecx, 2
0x180016f56  or      ecx, eax
0x180016f58  xor     eax, eax
0x180016f5a  shl     ecx, 2
0x180016f5d  or      ecx, edx
0x180016f5f  lea     ebx, ds:0[rcx*8]
0x180016f66  test    r8d, r8d
0x180016f69  jz      short loc_180016F73
0x180016f6b  cmp     r8d, 2
0x180016f6f  cmovz   eax, r12d
0x180016f73  or      ebx, eax
0x180016f75  mov     ecx, 0C00h
0x180016f7a  mov     eax, ebx
0x180016f7c  and     eax, ecx
0x180016f7e  cmp     eax, ecx
0x180016f80  jnz     short loc_180016F87
0x180016f82  mov     sil, 1
0x180016f85  jmp     short loc_180016F8F
0x180016f87  xor     sil, sil
0x180016f8a  test    r12b, bl
0x180016f8d  jz      short loc_180016FAA
0x180016f8f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180016f96  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x180016f9b  test    sil, sil
0x180016f9e  jz      short loc_180016FAC
0x180016fa0  test    al, al
0x180016fa2  jnz     short loc_180016FAC
0x180016fa4  btr     ebx, 0Ah
0x180016fa8  jmp     short loc_180016FAC
0x180016faa  xor     al, al
0x180016fac  test    r12b, bl
0x180016faf  jz      short loc_180016FBC
0x180016fb1  test    al, al
0x180016fb3  jz      short loc_180016FBC
0x180016fb5  mov     esi, 1
0x180016fba  jmp     short loc_180016FBE
0x180016fbc  xor     esi, esi
0x180016fbe  mov     eax, [rdi]
0x180016fc0  or      esi, ebx
0x180016fc2  mov     ebx, 180h
0x180016fc7  cmp     [rsp+68h+var_48], 0
0x180016fcc  mov     edx, eax
0x180016fce  mov     [rdi], eax
0x180016fd0  jz      short loc_18001700A
0x180016fd2  test    dl, 2
0x180016fd5  jnz     short loc_18001700A
0x180016fd7  mov     eax, esi
0x180016fd9  xor     eax, edx
0x180016fdb  and     eax, ebx
0x180016fdd  xor     eax, edx
0x180016fdf  mov     ecx, eax
0x180016fe1  xor     ecx, esi
0x180016fe3  and     ecx, r12d
0x180016fe6  xor     ecx, eax
0x180016fe8  mov     eax, ecx
0x180016fea  xor     eax, esi
0x180016fec  and     eax, 1
0x180016fef  xor     eax, ecx
0x180016ff1  mov     r8d, eax
0x180016ff4  xor     r8d, esi
0x180016ff7  and     r8d, 800h
0x180016ffe  xor     r8d, eax
0x180017001  or      r8d, 2
0x180017005  mov     [rdi], r8d
0x180017008  jmp     short loc_18001700D
0x18001700a  mov     r8d, edx
0x18001700d  mov     r9d, edx
0x180017010  and     r9d, 4
0x180017014  jnz     short loc_18001702B
0x180017016  mov     ecx, esi
0x180017018  xor     ecx, r8d
0x18001701b  and     ecx, 400h
0x180017021  xor     ecx, r8d
0x180017024  or      ecx, 4
0x180017027  mov     [rdi], ecx
0x180017029  jmp     short loc_18001702E
0x18001702b  mov     ecx, r8d
0x18001702e  mov     eax, edx
0x180017030  lock cmpxchg [r14], ecx
0x180017035  jnz     short loc_180016FC7
0x180017037  test    r9d, r9d
0x18001703a  jnz     short loc_18001704B
0x18001703c  mov     r8d, ebp
0x18001703f  lea     edx, [r9+3]
0x180017043  mov     rcx, r14
0x180017046  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001704b  test    byte ptr [rdi], 2
0x18001704e  jnz     short loc_180017078
0x180017050  mov     eax, [rdi]
0x180017052  xor     eax, esi
0x180017054  and     eax, ebx
0x180017056  xor     eax, [rdi]
0x180017058  mov     ecx, eax
0x18001705a  xor     ecx, esi
0x18001705c  and     ecx, r12d
0x18001705f  xor     ecx, eax
0x180017061  mov     edx, ecx
0x180017063  xor     edx, esi
0x180017065  and     edx, 1
0x180017068  xor     edx, ecx
0x18001706a  mov     ecx, edx
0x18001706c  xor     ecx, esi
0x18001706e  and     ecx, 800h
0x180017074  xor     ecx, edx
0x180017076  mov     [rdi], ecx
0x180017078  mov     rax, rdi
0x18001707b  mov     rcx, [rsp+68h+var_40]
0x180017080  xor     rcx, rsp; StackCookie
0x180017083  call    __security_check_cookie
0x180017088  add     rsp, 38h
0x18001708c  pop     r14
0x18001708e  pop     r12
0x180017090  pop     rdi
0x180017091  pop     rsi
0x180017092  pop     rbp
0x180017093  pop     rbx
0x180017094  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d10c`
- end: `0x18000d2d9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000db48`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000d10c`
- `0x18000dbe8`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_AutoEnable__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_AutoEnable__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59996275, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Preview2_AutoEnable__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Preview2_AutoEnable__descriptor, 3, v4);
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
0x18000d10c  mov     [rsp+arg_0], rcx
0x18000d111  push    rbx
0x18000d112  push    rbp
0x18000d113  push    rsi
0x18000d114  push    rdi
0x18000d115  push    r12
0x18000d117  push    r14
0x18000d119  sub     rsp, 28h
0x18000d11d  mov     r14, cs:Feature_CLAT_Preview2_AutoEnable__descriptor
0x18000d124  mov     rdi, rdx
0x18000d127  mov     qword ptr [rdx], 0
0x18000d12e  mov     eax, [r14]
0x18000d131  mov     [rdx], eax
0x18000d133  and     eax, 6
0x18000d136  cmp     al, 6
0x18000d138  jz      loc_18000D2C9
0x18000d13e  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d143  mov     ebp, eax
0x18000d145  mov     dword ptr [rsp+58h+arg_0], 0
0x18000d14d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d154  test    rax, rax
0x18000d157  jz      short loc_18000D171
0x18000d159  lea     r8, [rsp+58h+arg_0]
0x18000d15e  mov     edx, 3
0x18000d163  mov     ecx, 3937873h
0x18000d168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d16d  mov     edx, eax
0x18000d16f  jmp     short loc_18000D17F
0x18000d171  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d178  test    rax, rax
0x18000d17b  jnz     short loc_18000D159
0x18000d17d  xor     edx, edx
0x18000d17f  mov     r8d, edx
0x18000d182  mov     eax, edx
0x18000d184  and     r8d, 0FFFFFF3Fh
0x18000d18b  and     edx, 80h
0x18000d191  mov     ecx, r8d
0x18000d194  mov     r12d, 40h ; '@'
0x18000d19a  and     ecx, 3
0x18000d19d  and     eax, r12d
0x18000d1a0  shl     ecx, 2
0x18000d1a3  or      ecx, eax
0x18000d1a5  shl     ecx, 2
0x18000d1a8  or      ecx, edx
0x18000d1aa  lea     ebx, ds:0[rcx*8]
0x18000d1b1  test    r8d, r8d
0x18000d1b4  jnz     short loc_18000D1BB
0x18000d1b6  mov     eax, r12d
0x18000d1b9  jmp     short loc_18000D1C5
0x18000d1bb  xor     eax, eax
0x18000d1bd  cmp     r8d, 2
0x18000d1c1  cmovz   eax, r12d
0x18000d1c5  or      ebx, eax
0x18000d1c7  mov     ecx, 0C00h
0x18000d1cc  mov     eax, ebx
0x18000d1ce  and     eax, ecx
0x18000d1d0  cmp     eax, ecx
0x18000d1d2  jnz     short loc_18000D1D9
0x18000d1d4  mov     sil, 1
0x18000d1d7  jmp     short loc_18000D1E1
0x18000d1d9  xor     sil, sil
0x18000d1dc  test    r12b, bl
0x18000d1df  jz      short loc_18000D1FC
0x18000d1e1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl(void)'::`2'::impl
0x18000d1e8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(wil::ReportingKind)
0x18000d1ed  test    sil, sil
0x18000d1f0  jz      short loc_18000D1FE
0x18000d1f2  test    al, al
0x18000d1f4  jnz     short loc_18000D1FE
0x18000d1f6  btr     ebx, 0Ah
0x18000d1fa  jmp     short loc_18000D1FE
0x18000d1fc  xor     al, al
0x18000d1fe  test    r12b, bl
0x18000d201  jz      short loc_18000D20E
0x18000d203  test    al, al
0x18000d205  jz      short loc_18000D20E
0x18000d207  mov     esi, 1
0x18000d20c  jmp     short loc_18000D210
0x18000d20e  xor     esi, esi
0x18000d210  mov     eax, [rdi]
0x18000d212  or      esi, ebx
0x18000d214  mov     ebx, 180h
0x18000d219  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000d21e  mov     edx, eax
0x18000d220  mov     [rdi], eax
0x18000d222  jz      short loc_18000D25C
0x18000d224  test    dl, 2
0x18000d227  jnz     short loc_18000D25C
0x18000d229  mov     eax, esi
0x18000d22b  xor     eax, edx
0x18000d22d  and     eax, ebx
0x18000d22f  xor     eax, edx
0x18000d231  mov     ecx, eax
0x18000d233  xor     ecx, esi
0x18000d235  and     ecx, r12d
0x18000d238  xor     ecx, eax
0x18000d23a  mov     eax, ecx
0x18000d23c  xor     eax, esi
0x18000d23e  and     eax, 1
0x18000d241  xor     eax, ecx
0x18000d243  mov     r8d, eax
0x18000d246  xor     r8d, esi
0x18000d249  and     r8d, 800h
0x18000d250  xor     r8d, eax
0x18000d253  or      r8d, 2
0x18000d257  mov     [rdi], r8d
0x18000d25a  jmp     short loc_18000D25F
0x18000d25c  mov     r8d, edx
0x18000d25f  mov     r9d, edx
0x18000d262  and     r9d, 4
0x18000d266  jnz     short loc_18000D27D
0x18000d268  mov     ecx, esi
0x18000d26a  xor     ecx, r8d
0x18000d26d  and     ecx, 400h
0x18000d273  xor     ecx, r8d
0x18000d276  or      ecx, 4
0x18000d279  mov     [rdi], ecx
0x18000d27b  jmp     short loc_18000D280
0x18000d27d  mov     ecx, r8d
0x18000d280  mov     eax, edx
0x18000d282  lock cmpxchg [r14], ecx
0x18000d287  jnz     short loc_18000D219
0x18000d289  test    r9d, r9d
0x18000d28c  jnz     short loc_18000D29D
0x18000d28e  mov     r8d, ebp
0x18000d291  lea     edx, [r9+3]
0x18000d295  mov     rcx, r14
0x18000d298  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d29d  test    byte ptr [rdi], 2
0x18000d2a0  jnz     short loc_18000D2C9
0x18000d2a2  mov     eax, [rdi]
0x18000d2a4  xor     eax, esi
0x18000d2a6  and     eax, ebx
0x18000d2a8  xor     eax, [rdi]
0x18000d2aa  mov     ecx, eax
0x18000d2ac  xor     ecx, esi
0x18000d2ae  and     ecx, r12d
0x18000d2b1  xor     ecx, eax
0x18000d2b3  mov     edx, ecx
0x18000d2b5  xor     edx, esi
0x18000d2b7  and     edx, 1
0x18000d2ba  xor     edx, ecx
0x18000d2bc  mov     eax, edx
0x18000d2be  xor     eax, esi
0x18000d2c0  and     eax, 800h
0x18000d2c5  xor     eax, edx
0x18000d2c7  mov     [rdi], eax
0x18000d2c9  mov     rax, rdi
0x18000d2cc  add     rsp, 28h
0x18000d2d0  pop     r14
0x18000d2d2  pop     r12
0x18000d2d4  pop     rdi
0x18000d2d5  pop     rsi
0x18000d2d6  pop     rbp
0x18000d2d7  pop     rbx
0x18000d2d8  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::GetCachedFeatureEnabledState(void)

- ea: `0x1800106b8`
- end: `0x180010885`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011fdc`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000b090`
- `0x1800106b8`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_ReleaseIPv4>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_ReleaseIPv4__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_ReleaseIPv4__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58604962, 3, &v20);
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
            (volatile signed __int32 *)Feature_CLAT_Preview2_ReleaseIPv4__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Preview2_ReleaseIPv4__descriptor, 3, v4);
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
0x1800106b8  mov     [rsp+arg_0], rcx
0x1800106bd  push    rbx
0x1800106be  push    rbp
0x1800106bf  push    rsi
0x1800106c0  push    rdi
0x1800106c1  push    r12
0x1800106c3  push    r14
0x1800106c5  sub     rsp, 28h
0x1800106c9  mov     r14, cs:Feature_CLAT_Preview2_ReleaseIPv4__descriptor
0x1800106d0  mov     rdi, rdx
0x1800106d3  mov     qword ptr [rdx], 0
0x1800106da  mov     eax, [r14]
0x1800106dd  mov     [rdx], eax
0x1800106df  and     eax, 6
0x1800106e2  cmp     al, 6
0x1800106e4  jz      loc_180010875
0x1800106ea  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800106ef  mov     ebp, eax
0x1800106f1  mov     dword ptr [rsp+58h+arg_0], 0
0x1800106f9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180010700  test    rax, rax
0x180010703  jz      short loc_18001071D
0x180010705  lea     r8, [rsp+58h+arg_0]
0x18001070a  mov     edx, 3
0x18001070f  mov     ecx, 37E3DA2h
0x180010714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010719  mov     edx, eax
0x18001071b  jmp     short loc_18001072B
0x18001071d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180010724  test    rax, rax
0x180010727  jnz     short loc_180010705
0x180010729  xor     edx, edx
0x18001072b  mov     r8d, edx
0x18001072e  mov     eax, edx
0x180010730  and     r8d, 0FFFFFF3Fh
0x180010737  and     edx, 80h
0x18001073d  mov     ecx, r8d
0x180010740  mov     r12d, 40h ; '@'
0x180010746  and     ecx, 3
0x180010749  and     eax, r12d
0x18001074c  shl     ecx, 2
0x18001074f  or      ecx, eax
0x180010751  shl     ecx, 2
0x180010754  or      ecx, edx
0x180010756  lea     ebx, ds:0[rcx*8]
0x18001075d  test    r8d, r8d
0x180010760  jnz     short loc_180010767
0x180010762  mov     eax, r12d
0x180010765  jmp     short loc_180010771
0x180010767  xor     eax, eax
0x180010769  cmp     r8d, 2
0x18001076d  cmovz   eax, r12d
0x180010771  or      ebx, eax
0x180010773  mov     ecx, 0C00h
0x180010778  mov     eax, ebx
0x18001077a  and     eax, ecx
0x18001077c  cmp     eax, ecx
0x18001077e  jnz     short loc_180010785
0x180010780  mov     sil, 1
0x180010783  jmp     short loc_18001078D
0x180010785  xor     sil, sil
0x180010788  test    r12b, bl
0x18001078b  jz      short loc_1800107A8
0x18001078d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl(void)'::`2'::impl
0x180010794  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(wil::ReportingKind)
0x180010799  test    sil, sil
0x18001079c  jz      short loc_1800107AA
0x18001079e  test    al, al
0x1800107a0  jnz     short loc_1800107AA
0x1800107a2  btr     ebx, 0Ah
0x1800107a6  jmp     short loc_1800107AA
0x1800107a8  xor     al, al
0x1800107aa  test    r12b, bl
0x1800107ad  jz      short loc_1800107BA
0x1800107af  test    al, al
0x1800107b1  jz      short loc_1800107BA
0x1800107b3  mov     esi, 1
0x1800107b8  jmp     short loc_1800107BC
0x1800107ba  xor     esi, esi
0x1800107bc  mov     eax, [rdi]
0x1800107be  or      esi, ebx
0x1800107c0  mov     ebx, 180h
0x1800107c5  cmp     dword ptr [rsp+58h+arg_0], 0
0x1800107ca  mov     edx, eax
0x1800107cc  mov     [rdi], eax
0x1800107ce  jz      short loc_180010808
0x1800107d0  test    dl, 2
0x1800107d3  jnz     short loc_180010808
0x1800107d5  mov     eax, esi
0x1800107d7  xor     eax, edx
0x1800107d9  and     eax, ebx
0x1800107db  xor     eax, edx
0x1800107dd  mov     ecx, eax
0x1800107df  xor     ecx, esi
0x1800107e1  and     ecx, r12d
0x1800107e4  xor     ecx, eax
0x1800107e6  mov     eax, ecx
0x1800107e8  xor     eax, esi
0x1800107ea  and     eax, 1
0x1800107ed  xor     eax, ecx
0x1800107ef  mov     r8d, eax
0x1800107f2  xor     r8d, esi
0x1800107f5  and     r8d, 800h
0x1800107fc  xor     r8d, eax
0x1800107ff  or      r8d, 2
0x180010803  mov     [rdi], r8d
0x180010806  jmp     short loc_18001080B
0x180010808  mov     r8d, edx
0x18001080b  mov     r9d, edx
0x18001080e  and     r9d, 4
0x180010812  jnz     short loc_180010829
0x180010814  mov     ecx, esi
0x180010816  xor     ecx, r8d
0x180010819  and     ecx, 400h
0x18001081f  xor     ecx, r8d
0x180010822  or      ecx, 4
0x180010825  mov     [rdi], ecx
0x180010827  jmp     short loc_18001082C
0x180010829  mov     ecx, r8d
0x18001082c  mov     eax, edx
0x18001082e  lock cmpxchg [r14], ecx
0x180010833  jnz     short loc_1800107C5
0x180010835  test    r9d, r9d
0x180010838  jnz     short loc_180010849
0x18001083a  mov     r8d, ebp
0x18001083d  lea     edx, [r9+3]
0x180010841  mov     rcx, r14
0x180010844  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180010849  test    byte ptr [rdi], 2
0x18001084c  jnz     short loc_180010875
0x18001084e  mov     eax, [rdi]
0x180010850  xor     eax, esi
0x180010852  and     eax, ebx
0x180010854  xor     eax, [rdi]
0x180010856  mov     ecx, eax
0x180010858  xor     ecx, esi
0x18001085a  and     ecx, r12d
0x18001085d  xor     ecx, eax
0x18001085f  mov     edx, ecx
0x180010861  xor     edx, esi
0x180010863  and     edx, 1
0x180010866  xor     edx, ecx
0x180010868  mov     eax, edx
0x18001086a  xor     eax, esi
0x18001086c  and     eax, 800h
0x180010871  xor     eax, edx
0x180010873  mov     [rdi], eax
0x180010875  mov     rax, rdi
0x180010878  add     rsp, 28h
0x18001087c  pop     r14
0x18001087e  pop     r12
0x180010880  pop     rdi
0x180010881  pop     rsi
0x180010882  pop     rbp
0x180010883  pop     rbx
0x180010884  retn
```

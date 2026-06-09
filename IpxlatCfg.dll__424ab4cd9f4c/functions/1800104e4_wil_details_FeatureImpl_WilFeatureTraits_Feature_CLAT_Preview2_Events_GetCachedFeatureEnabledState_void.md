# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetCachedFeatureEnabledState(void)

- ea: `0x1800104e4`
- end: `0x1800106b1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011f3c`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000b090`
- `0x1800104e4`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_Events__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_Events__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58687608, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Preview2_Events__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Preview2_Events__descriptor, 3, v4);
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
0x1800104e4  mov     [rsp+arg_0], rcx
0x1800104e9  push    rbx
0x1800104ea  push    rbp
0x1800104eb  push    rsi
0x1800104ec  push    rdi
0x1800104ed  push    r12
0x1800104ef  push    r14
0x1800104f1  sub     rsp, 28h
0x1800104f5  mov     r14, cs:Feature_CLAT_Preview2_Events__descriptor
0x1800104fc  mov     rdi, rdx
0x1800104ff  mov     qword ptr [rdx], 0
0x180010506  mov     eax, [r14]
0x180010509  mov     [rdx], eax
0x18001050b  and     eax, 6
0x18001050e  cmp     al, 6
0x180010510  jz      loc_1800106A1
0x180010516  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001051b  mov     ebp, eax
0x18001051d  mov     dword ptr [rsp+58h+arg_0], 0
0x180010525  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001052c  test    rax, rax
0x18001052f  jz      short loc_180010549
0x180010531  lea     r8, [rsp+58h+arg_0]
0x180010536  mov     edx, 3
0x18001053b  mov     ecx, 37F8078h
0x180010540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010545  mov     edx, eax
0x180010547  jmp     short loc_180010557
0x180010549  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180010550  test    rax, rax
0x180010553  jnz     short loc_180010531
0x180010555  xor     edx, edx
0x180010557  mov     r8d, edx
0x18001055a  mov     eax, edx
0x18001055c  and     r8d, 0FFFFFF3Fh
0x180010563  and     edx, 80h
0x180010569  mov     ecx, r8d
0x18001056c  mov     r12d, 40h ; '@'
0x180010572  and     ecx, 3
0x180010575  and     eax, r12d
0x180010578  shl     ecx, 2
0x18001057b  or      ecx, eax
0x18001057d  shl     ecx, 2
0x180010580  or      ecx, edx
0x180010582  lea     ebx, ds:0[rcx*8]
0x180010589  test    r8d, r8d
0x18001058c  jnz     short loc_180010593
0x18001058e  mov     eax, r12d
0x180010591  jmp     short loc_18001059D
0x180010593  xor     eax, eax
0x180010595  cmp     r8d, 2
0x180010599  cmovz   eax, r12d
0x18001059d  or      ebx, eax
0x18001059f  mov     ecx, 0C00h
0x1800105a4  mov     eax, ebx
0x1800105a6  and     eax, ecx
0x1800105a8  cmp     eax, ecx
0x1800105aa  jnz     short loc_1800105B1
0x1800105ac  mov     sil, 1
0x1800105af  jmp     short loc_1800105B9
0x1800105b1  xor     sil, sil
0x1800105b4  test    r12b, bl
0x1800105b7  jz      short loc_1800105D4
0x1800105b9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl(void)'::`2'::impl
0x1800105c0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(wil::ReportingKind)
0x1800105c5  test    sil, sil
0x1800105c8  jz      short loc_1800105D6
0x1800105ca  test    al, al
0x1800105cc  jnz     short loc_1800105D6
0x1800105ce  btr     ebx, 0Ah
0x1800105d2  jmp     short loc_1800105D6
0x1800105d4  xor     al, al
0x1800105d6  test    r12b, bl
0x1800105d9  jz      short loc_1800105E6
0x1800105db  test    al, al
0x1800105dd  jz      short loc_1800105E6
0x1800105df  mov     esi, 1
0x1800105e4  jmp     short loc_1800105E8
0x1800105e6  xor     esi, esi
0x1800105e8  mov     eax, [rdi]
0x1800105ea  or      esi, ebx
0x1800105ec  mov     ebx, 180h
0x1800105f1  cmp     dword ptr [rsp+58h+arg_0], 0
0x1800105f6  mov     edx, eax
0x1800105f8  mov     [rdi], eax
0x1800105fa  jz      short loc_180010634
0x1800105fc  test    dl, 2
0x1800105ff  jnz     short loc_180010634
0x180010601  mov     eax, esi
0x180010603  xor     eax, edx
0x180010605  and     eax, ebx
0x180010607  xor     eax, edx
0x180010609  mov     ecx, eax
0x18001060b  xor     ecx, esi
0x18001060d  and     ecx, r12d
0x180010610  xor     ecx, eax
0x180010612  mov     eax, ecx
0x180010614  xor     eax, esi
0x180010616  and     eax, 1
0x180010619  xor     eax, ecx
0x18001061b  mov     r8d, eax
0x18001061e  xor     r8d, esi
0x180010621  and     r8d, 800h
0x180010628  xor     r8d, eax
0x18001062b  or      r8d, 2
0x18001062f  mov     [rdi], r8d
0x180010632  jmp     short loc_180010637
0x180010634  mov     r8d, edx
0x180010637  mov     r9d, edx
0x18001063a  and     r9d, 4
0x18001063e  jnz     short loc_180010655
0x180010640  mov     ecx, esi
0x180010642  xor     ecx, r8d
0x180010645  and     ecx, 400h
0x18001064b  xor     ecx, r8d
0x18001064e  or      ecx, 4
0x180010651  mov     [rdi], ecx
0x180010653  jmp     short loc_180010658
0x180010655  mov     ecx, r8d
0x180010658  mov     eax, edx
0x18001065a  lock cmpxchg [r14], ecx
0x18001065f  jnz     short loc_1800105F1
0x180010661  test    r9d, r9d
0x180010664  jnz     short loc_180010675
0x180010666  mov     r8d, ebp
0x180010669  lea     edx, [r9+3]
0x18001066d  mov     rcx, r14
0x180010670  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180010675  test    byte ptr [rdi], 2
0x180010678  jnz     short loc_1800106A1
0x18001067a  mov     eax, [rdi]
0x18001067c  xor     eax, esi
0x18001067e  and     eax, ebx
0x180010680  xor     eax, [rdi]
0x180010682  mov     ecx, eax
0x180010684  xor     ecx, esi
0x180010686  and     ecx, r12d
0x180010689  xor     ecx, eax
0x18001068b  mov     edx, ecx
0x18001068d  xor     edx, esi
0x18001068f  and     edx, 1
0x180010692  xor     edx, ecx
0x180010694  mov     eax, edx
0x180010696  xor     eax, esi
0x180010698  and     eax, 800h
0x18001069d  xor     eax, edx
0x18001069f  mov     [rdi], eax
0x1800106a1  mov     rax, rdi
0x1800106a4  add     rsp, 28h
0x1800106a8  pop     r14
0x1800106aa  pop     r12
0x1800106ac  pop     rdi
0x1800106ad  pop     rsi
0x1800106ae  pop     rbp
0x1800106af  pop     rbx
0x1800106b0  retn
```

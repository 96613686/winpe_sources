# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetCachedFeatureEnabledState(void)

- ea: `0x18001e720`
- end: `0x18001e8ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180021328`

## callees

- `0x18001e65c`
- `0x18001e720`
- `0x180020fe4`
- `0x18002159c`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2ContainerIds__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2ContainerIds__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61091483, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_Servicing_MIDI2ContainerIds__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2ContainerIds__descriptor,
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
0x18001e720  mov     [rsp+arg_0], rcx
0x18001e725  push    rbx
0x18001e726  push    rbp
0x18001e727  push    rsi
0x18001e728  push    rdi
0x18001e729  push    r12
0x18001e72b  push    r14
0x18001e72d  sub     rsp, 28h
0x18001e731  mov     r14, cs:Feature_Servicing_MIDI2ContainerIds__descriptor
0x18001e738  mov     rdi, rdx
0x18001e73b  mov     qword ptr [rdx], 0
0x18001e742  mov     eax, [r14]
0x18001e745  mov     [rdx], eax
0x18001e747  and     eax, 6
0x18001e74a  cmp     al, 6
0x18001e74c  jz      loc_18001E8DD
0x18001e752  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e757  mov     ebp, eax
0x18001e759  mov     dword ptr [rsp+58h+arg_0], 0
0x18001e761  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001e768  test    rax, rax
0x18001e76b  jz      short loc_18001E785
0x18001e76d  lea     r8, [rsp+58h+arg_0]
0x18001e772  mov     edx, 3
0x18001e777  mov     ecx, 3A42E9Bh
0x18001e77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e781  mov     edx, eax
0x18001e783  jmp     short loc_18001E793
0x18001e785  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001e78c  test    rax, rax
0x18001e78f  jnz     short loc_18001E76D
0x18001e791  xor     edx, edx
0x18001e793  mov     r8d, edx
0x18001e796  mov     eax, edx
0x18001e798  and     r8d, 0FFFFFF3Fh
0x18001e79f  and     edx, 80h
0x18001e7a5  mov     ecx, r8d
0x18001e7a8  mov     r12d, 40h ; '@'
0x18001e7ae  and     ecx, 3
0x18001e7b1  and     eax, r12d
0x18001e7b4  shl     ecx, 2
0x18001e7b7  or      ecx, eax
0x18001e7b9  shl     ecx, 2
0x18001e7bc  or      ecx, edx
0x18001e7be  lea     ebx, ds:0[rcx*8]
0x18001e7c5  test    r8d, r8d
0x18001e7c8  jnz     short loc_18001E7CF
0x18001e7ca  mov     eax, r12d
0x18001e7cd  jmp     short loc_18001E7D9
0x18001e7cf  xor     eax, eax
0x18001e7d1  cmp     r8d, 2
0x18001e7d5  cmovz   eax, r12d
0x18001e7d9  or      ebx, eax
0x18001e7db  mov     ecx, 0C00h
0x18001e7e0  mov     eax, ebx
0x18001e7e2  and     eax, ecx
0x18001e7e4  cmp     eax, ecx
0x18001e7e6  jnz     short loc_18001E7ED
0x18001e7e8  mov     sil, 1
0x18001e7eb  jmp     short loc_18001E7F5
0x18001e7ed  xor     sil, sil
0x18001e7f0  test    r12b, bl
0x18001e7f3  jz      short loc_18001E810
0x18001e7f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x18001e7fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18001e801  test    sil, sil
0x18001e804  jz      short loc_18001E812
0x18001e806  test    al, al
0x18001e808  jnz     short loc_18001E812
0x18001e80a  btr     ebx, 0Ah
0x18001e80e  jmp     short loc_18001E812
0x18001e810  xor     al, al
0x18001e812  test    r12b, bl
0x18001e815  jz      short loc_18001E822
0x18001e817  test    al, al
0x18001e819  jz      short loc_18001E822
0x18001e81b  mov     esi, 1
0x18001e820  jmp     short loc_18001E824
0x18001e822  xor     esi, esi
0x18001e824  mov     eax, [rdi]
0x18001e826  or      esi, ebx
0x18001e828  mov     ebx, 180h
0x18001e82d  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001e832  mov     edx, eax
0x18001e834  mov     [rdi], eax
0x18001e836  jz      short loc_18001E870
0x18001e838  test    dl, 2
0x18001e83b  jnz     short loc_18001E870
0x18001e83d  mov     eax, esi
0x18001e83f  xor     eax, edx
0x18001e841  and     eax, ebx
0x18001e843  xor     eax, edx
0x18001e845  mov     ecx, eax
0x18001e847  xor     ecx, esi
0x18001e849  and     ecx, r12d
0x18001e84c  xor     ecx, eax
0x18001e84e  mov     eax, ecx
0x18001e850  xor     eax, esi
0x18001e852  and     eax, 1
0x18001e855  xor     eax, ecx
0x18001e857  mov     r8d, eax
0x18001e85a  xor     r8d, esi
0x18001e85d  and     r8d, 800h
0x18001e864  xor     r8d, eax
0x18001e867  or      r8d, 2
0x18001e86b  mov     [rdi], r8d
0x18001e86e  jmp     short loc_18001E873
0x18001e870  mov     r8d, edx
0x18001e873  mov     r9d, edx
0x18001e876  and     r9d, 4
0x18001e87a  jnz     short loc_18001E891
0x18001e87c  mov     ecx, esi
0x18001e87e  xor     ecx, r8d
0x18001e881  and     ecx, 400h
0x18001e887  xor     ecx, r8d
0x18001e88a  or      ecx, 4
0x18001e88d  mov     [rdi], ecx
0x18001e88f  jmp     short loc_18001E894
0x18001e891  mov     ecx, r8d
0x18001e894  mov     eax, edx
0x18001e896  lock cmpxchg [r14], ecx
0x18001e89b  jnz     short loc_18001E82D
0x18001e89d  test    r9d, r9d
0x18001e8a0  jnz     short loc_18001E8B1
0x18001e8a2  mov     r8d, ebp
0x18001e8a5  lea     edx, [r9+3]
0x18001e8a9  mov     rcx, r14
0x18001e8ac  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001e8b1  test    byte ptr [rdi], 2
0x18001e8b4  jnz     short loc_18001E8DD
0x18001e8b6  mov     eax, [rdi]
0x18001e8b8  xor     eax, esi
0x18001e8ba  and     eax, ebx
0x18001e8bc  xor     eax, [rdi]
0x18001e8be  mov     ecx, eax
0x18001e8c0  xor     ecx, esi
0x18001e8c2  and     ecx, r12d
0x18001e8c5  xor     ecx, eax
0x18001e8c7  mov     edx, ecx
0x18001e8c9  xor     edx, esi
0x18001e8cb  and     edx, 1
0x18001e8ce  xor     edx, ecx
0x18001e8d0  mov     eax, edx
0x18001e8d2  xor     eax, esi
0x18001e8d4  and     eax, 800h
0x18001e8d9  xor     eax, edx
0x18001e8db  mov     [rdi], eax
0x18001e8dd  mov     rax, rdi
0x18001e8e0  add     rsp, 28h
0x18001e8e4  pop     r14
0x18001e8e6  pop     r12
0x18001e8e8  pop     rdi
0x18001e8e9  pop     rsi
0x18001e8ea  pop     rbp
0x18001e8eb  pop     rbx
0x18001e8ec  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2FilterCreations>::GetCachedFeatureEnabledState(void)

- ea: `0x180019068`
- end: `0x180019235`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2FilterCreations@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001fdf8`

## callees

- `0x180007d0c`
- `0x18000b2e0`
- `0x180019068`
- `0x1800201a8`
- `0x180041010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2FilterCreations>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2FilterCreations__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2FilterCreations__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(47571751, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_Servicing_MIDI2FilterCreations__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2FilterCreations__descriptor,
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
0x180019068  mov     [rsp+arg_0], rcx
0x18001906d  push    rbx
0x18001906e  push    rbp
0x18001906f  push    rsi
0x180019070  push    rdi
0x180019071  push    r12
0x180019073  push    r14
0x180019075  sub     rsp, 28h
0x180019079  mov     r14, cs:Feature_Servicing_MIDI2FilterCreations__descriptor
0x180019080  mov     rdi, rdx
0x180019083  mov     qword ptr [rdx], 0
0x18001908a  mov     eax, [r14]
0x18001908d  mov     [rdx], eax
0x18001908f  and     eax, 6
0x180019092  cmp     al, 6
0x180019094  jz      loc_180019225
0x18001909a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001909f  mov     ebp, eax
0x1800190a1  mov     dword ptr [rsp+58h+arg_0], 0
0x1800190a9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800190b0  test    rax, rax
0x1800190b3  jz      short loc_1800190CD
0x1800190b5  lea     r8, [rsp+58h+arg_0]
0x1800190ba  mov     edx, 3
0x1800190bf  mov     ecx, 2D5E327h
0x1800190c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190c9  mov     edx, eax
0x1800190cb  jmp     short loc_1800190DB
0x1800190cd  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800190d4  test    rax, rax
0x1800190d7  jnz     short loc_1800190B5
0x1800190d9  xor     edx, edx
0x1800190db  mov     r8d, edx
0x1800190de  mov     eax, edx
0x1800190e0  and     r8d, 0FFFFFF3Fh
0x1800190e7  and     edx, 80h
0x1800190ed  mov     ecx, r8d
0x1800190f0  mov     r12d, 40h ; '@'
0x1800190f6  and     ecx, 3
0x1800190f9  and     eax, r12d
0x1800190fc  shl     ecx, 2
0x1800190ff  or      ecx, eax
0x180019101  shl     ecx, 2
0x180019104  or      ecx, edx
0x180019106  lea     ebx, ds:0[rcx*8]
0x18001910d  test    r8d, r8d
0x180019110  jnz     short loc_180019117
0x180019112  mov     eax, r12d
0x180019115  jmp     short loc_180019121
0x180019117  xor     eax, eax
0x180019119  cmp     r8d, 2
0x18001911d  cmovz   eax, r12d
0x180019121  or      ebx, eax
0x180019123  mov     ecx, 0C00h
0x180019128  mov     eax, ebx
0x18001912a  and     eax, ecx
0x18001912c  cmp     eax, ecx
0x18001912e  jnz     short loc_180019135
0x180019130  mov     sil, 1
0x180019133  jmp     short loc_18001913D
0x180019135  xor     sil, sil
0x180019138  test    r12b, bl
0x18001913b  jz      short loc_180019158
0x18001913d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x180019144  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x180019149  test    sil, sil
0x18001914c  jz      short loc_18001915A
0x18001914e  test    al, al
0x180019150  jnz     short loc_18001915A
0x180019152  btr     ebx, 0Ah
0x180019156  jmp     short loc_18001915A
0x180019158  xor     al, al
0x18001915a  test    r12b, bl
0x18001915d  jz      short loc_18001916A
0x18001915f  test    al, al
0x180019161  jz      short loc_18001916A
0x180019163  mov     esi, 1
0x180019168  jmp     short loc_18001916C
0x18001916a  xor     esi, esi
0x18001916c  mov     eax, [rdi]
0x18001916e  or      esi, ebx
0x180019170  mov     ebx, 180h
0x180019175  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001917a  mov     edx, eax
0x18001917c  mov     [rdi], eax
0x18001917e  jz      short loc_1800191B8
0x180019180  test    dl, 2
0x180019183  jnz     short loc_1800191B8
0x180019185  mov     eax, esi
0x180019187  xor     eax, edx
0x180019189  and     eax, ebx
0x18001918b  xor     eax, edx
0x18001918d  mov     ecx, eax
0x18001918f  xor     ecx, esi
0x180019191  and     ecx, r12d
0x180019194  xor     ecx, eax
0x180019196  mov     eax, ecx
0x180019198  xor     eax, esi
0x18001919a  and     eax, 1
0x18001919d  xor     eax, ecx
0x18001919f  mov     r8d, eax
0x1800191a2  xor     r8d, esi
0x1800191a5  and     r8d, 800h
0x1800191ac  xor     r8d, eax
0x1800191af  or      r8d, 2
0x1800191b3  mov     [rdi], r8d
0x1800191b6  jmp     short loc_1800191BB
0x1800191b8  mov     r8d, edx
0x1800191bb  mov     r9d, edx
0x1800191be  and     r9d, 4
0x1800191c2  jnz     short loc_1800191D9
0x1800191c4  mov     ecx, esi
0x1800191c6  xor     ecx, r8d
0x1800191c9  and     ecx, 400h
0x1800191cf  xor     ecx, r8d
0x1800191d2  or      ecx, 4
0x1800191d5  mov     [rdi], ecx
0x1800191d7  jmp     short loc_1800191DC
0x1800191d9  mov     ecx, r8d
0x1800191dc  mov     eax, edx
0x1800191de  lock cmpxchg [r14], ecx
0x1800191e3  jnz     short loc_180019175
0x1800191e5  test    r9d, r9d
0x1800191e8  jnz     short loc_1800191F9
0x1800191ea  mov     r8d, ebp
0x1800191ed  lea     edx, [r9+3]
0x1800191f1  mov     rcx, r14
0x1800191f4  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800191f9  test    byte ptr [rdi], 2
0x1800191fc  jnz     short loc_180019225
0x1800191fe  mov     eax, [rdi]
0x180019200  xor     eax, esi
0x180019202  and     eax, ebx
0x180019204  xor     eax, [rdi]
0x180019206  mov     ecx, eax
0x180019208  xor     ecx, esi
0x18001920a  and     ecx, r12d
0x18001920d  xor     ecx, eax
0x18001920f  mov     edx, ecx
0x180019211  xor     edx, esi
0x180019213  and     edx, 1
0x180019216  xor     edx, ecx
0x180019218  mov     eax, edx
0x18001921a  xor     eax, esi
0x18001921c  and     eax, 800h
0x180019221  xor     eax, edx
0x180019223  mov     [rdi], eax
0x180019225  mov     rax, rdi
0x180019228  add     rsp, 28h
0x18001922c  pop     r14
0x18001922e  pop     r12
0x180019230  pop     rdi
0x180019231  pop     rsi
0x180019232  pop     rbp
0x180019233  pop     rbx
0x180019234  retn
```

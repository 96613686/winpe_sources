# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e1cc`
- end: `0x18000e399`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013cd4`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000e1cc`
- `0x180013f48`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(44936384, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFix_44936384__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFix_44936384__descriptor, 3, v4);
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
0x18000e1cc  mov     [rsp+arg_0], rcx
0x18000e1d1  push    rbx
0x18000e1d2  push    rbp
0x18000e1d3  push    rsi
0x18000e1d4  push    rdi
0x18000e1d5  push    r12
0x18000e1d7  push    r14
0x18000e1d9  sub     rsp, 28h
0x18000e1dd  mov     r14, cs:Feature_BugFix_44936384__descriptor
0x18000e1e4  mov     rdi, rdx
0x18000e1e7  mov     qword ptr [rdx], 0
0x18000e1ee  mov     eax, [r14]
0x18000e1f1  mov     [rdx], eax
0x18000e1f3  and     eax, 6
0x18000e1f6  cmp     al, 6
0x18000e1f8  jz      loc_18000E389
0x18000e1fe  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e203  mov     ebp, eax
0x18000e205  mov     dword ptr [rsp+58h+arg_0], 0
0x18000e20d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e214  test    rax, rax
0x18000e217  jz      short loc_18000E231
0x18000e219  lea     r8, [rsp+58h+arg_0]
0x18000e21e  mov     edx, 3
0x18000e223  mov     ecx, 2ADACC0h
0x18000e228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e22d  mov     edx, eax
0x18000e22f  jmp     short loc_18000E23F
0x18000e231  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e238  test    rax, rax
0x18000e23b  jnz     short loc_18000E219
0x18000e23d  xor     edx, edx
0x18000e23f  mov     r8d, edx
0x18000e242  mov     eax, edx
0x18000e244  and     r8d, 0FFFFFF3Fh
0x18000e24b  and     edx, 80h
0x18000e251  mov     ecx, r8d
0x18000e254  mov     r12d, 40h ; '@'
0x18000e25a  and     ecx, 3
0x18000e25d  and     eax, r12d
0x18000e260  shl     ecx, 2
0x18000e263  or      ecx, eax
0x18000e265  shl     ecx, 2
0x18000e268  or      ecx, edx
0x18000e26a  lea     ebx, ds:0[rcx*8]
0x18000e271  test    r8d, r8d
0x18000e274  jnz     short loc_18000E27B
0x18000e276  mov     eax, r12d
0x18000e279  jmp     short loc_18000E285
0x18000e27b  xor     eax, eax
0x18000e27d  cmp     r8d, 2
0x18000e281  cmovz   eax, r12d
0x18000e285  or      ebx, eax
0x18000e287  mov     ecx, 0C00h
0x18000e28c  mov     eax, ebx
0x18000e28e  and     eax, ecx
0x18000e290  cmp     eax, ecx
0x18000e292  jnz     short loc_18000E299
0x18000e294  mov     sil, 1
0x18000e297  jmp     short loc_18000E2A1
0x18000e299  xor     sil, sil
0x18000e29c  test    r12b, bl
0x18000e29f  jz      short loc_18000E2BC
0x18000e2a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18000e2a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18000e2ad  test    sil, sil
0x18000e2b0  jz      short loc_18000E2BE
0x18000e2b2  test    al, al
0x18000e2b4  jnz     short loc_18000E2BE
0x18000e2b6  btr     ebx, 0Ah
0x18000e2ba  jmp     short loc_18000E2BE
0x18000e2bc  xor     al, al
0x18000e2be  test    r12b, bl
0x18000e2c1  jz      short loc_18000E2CE
0x18000e2c3  test    al, al
0x18000e2c5  jz      short loc_18000E2CE
0x18000e2c7  mov     esi, 1
0x18000e2cc  jmp     short loc_18000E2D0
0x18000e2ce  xor     esi, esi
0x18000e2d0  mov     eax, [rdi]
0x18000e2d2  or      esi, ebx
0x18000e2d4  mov     ebx, 180h
0x18000e2d9  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000e2de  mov     edx, eax
0x18000e2e0  mov     [rdi], eax
0x18000e2e2  jz      short loc_18000E31C
0x18000e2e4  test    dl, 2
0x18000e2e7  jnz     short loc_18000E31C
0x18000e2e9  mov     eax, esi
0x18000e2eb  xor     eax, edx
0x18000e2ed  and     eax, ebx
0x18000e2ef  xor     eax, edx
0x18000e2f1  mov     ecx, eax
0x18000e2f3  xor     ecx, esi
0x18000e2f5  and     ecx, r12d
0x18000e2f8  xor     ecx, eax
0x18000e2fa  mov     eax, ecx
0x18000e2fc  xor     eax, esi
0x18000e2fe  and     eax, 1
0x18000e301  xor     eax, ecx
0x18000e303  mov     r8d, eax
0x18000e306  xor     r8d, esi
0x18000e309  and     r8d, 800h
0x18000e310  xor     r8d, eax
0x18000e313  or      r8d, 2
0x18000e317  mov     [rdi], r8d
0x18000e31a  jmp     short loc_18000E31F
0x18000e31c  mov     r8d, edx
0x18000e31f  mov     r9d, edx
0x18000e322  and     r9d, 4
0x18000e326  jnz     short loc_18000E33D
0x18000e328  mov     ecx, esi
0x18000e32a  xor     ecx, r8d
0x18000e32d  and     ecx, 400h
0x18000e333  xor     ecx, r8d
0x18000e336  or      ecx, 4
0x18000e339  mov     [rdi], ecx
0x18000e33b  jmp     short loc_18000E340
0x18000e33d  mov     ecx, r8d
0x18000e340  mov     eax, edx
0x18000e342  lock cmpxchg [r14], ecx
0x18000e347  jnz     short loc_18000E2D9
0x18000e349  test    r9d, r9d
0x18000e34c  jnz     short loc_18000E35D
0x18000e34e  mov     r8d, ebp
0x18000e351  lea     edx, [r9+3]
0x18000e355  mov     rcx, r14
0x18000e358  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e35d  test    byte ptr [rdi], 2
0x18000e360  jnz     short loc_18000E389
0x18000e362  mov     eax, [rdi]
0x18000e364  xor     eax, esi
0x18000e366  and     eax, ebx
0x18000e368  xor     eax, [rdi]
0x18000e36a  mov     ecx, eax
0x18000e36c  xor     ecx, esi
0x18000e36e  and     ecx, r12d
0x18000e371  xor     ecx, eax
0x18000e373  mov     edx, ecx
0x18000e375  xor     edx, esi
0x18000e377  and     edx, 1
0x18000e37a  xor     edx, ecx
0x18000e37c  mov     eax, edx
0x18000e37e  xor     eax, esi
0x18000e380  and     eax, 800h
0x18000e385  xor     eax, edx
0x18000e387  mov     [rdi], eax
0x18000e389  mov     rax, rdi
0x18000e38c  add     rsp, 28h
0x18000e390  pop     r14
0x18000e392  pop     r12
0x18000e394  pop     rdi
0x18000e395  pop     rsi
0x18000e396  pop     rbp
0x18000e397  pop     rbx
0x18000e398  retn
```

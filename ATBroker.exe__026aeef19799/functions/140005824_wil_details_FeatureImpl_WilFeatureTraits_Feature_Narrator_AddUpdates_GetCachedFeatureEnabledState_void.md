# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(void)

- ea: `0x140005824`
- end: `0x1400059db`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000a7e4`

## callees

- `0x140004d18`
- `0x140005824`
- `0x140009b34`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59171042, 1, &v19);
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
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
      goto LABEL_15;
    v9 = 0;
  }
  if ( (v8 & 0x40) == 0 || !v9 )
  {
    v10 = 0;
    goto LABEL_16;
  }
LABEL_15:
  v10 = 1;
LABEL_16:
  v11 = v10 | v8;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Narrator_AddUpdates__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Narrator_AddUpdates__descriptor, 1, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140005824  mov     [rsp+arg_8], rbx
0x140005829  mov     [rsp+arg_10], rbp
0x14000582e  mov     [rsp+arg_0], rcx
0x140005833  push    rsi
0x140005834  push    rdi
0x140005835  push    r12
0x140005837  sub     rsp, 20h
0x14000583b  mov     rsi, cs:Feature_Narrator_AddUpdates__descriptor
0x140005842  mov     rdi, rdx
0x140005845  mov     qword ptr [rdx], 0
0x14000584c  mov     eax, [rsi]
0x14000584e  mov     [rdx], eax
0x140005850  and     eax, 6
0x140005853  cmp     al, 6
0x140005855  jz      loc_1400059C5
0x14000585b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140005860  mov     ebp, eax
0x140005862  mov     dword ptr [rsp+38h+arg_0], 0
0x14000586a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140005871  test    rax, rax
0x140005874  jz      short loc_14000588E
0x140005876  lea     r8, [rsp+38h+arg_0]
0x14000587b  mov     edx, 1
0x140005880  mov     ecx, 386E0E2h
0x140005885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000588a  mov     edx, eax
0x14000588c  jmp     short loc_14000589C
0x14000588e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005895  test    rax, rax
0x140005898  jnz     short loc_140005876
0x14000589a  xor     edx, edx
0x14000589c  mov     r8d, edx
0x14000589f  mov     eax, edx
0x1400058a1  and     r8d, 0FFFFFF3Fh
0x1400058a8  and     edx, 80h
0x1400058ae  mov     ecx, r8d
0x1400058b1  mov     r12d, 40h ; '@'
0x1400058b7  and     ecx, 3
0x1400058ba  and     eax, r12d
0x1400058bd  shl     ecx, 2
0x1400058c0  or      ecx, eax
0x1400058c2  xor     eax, eax
0x1400058c4  shl     ecx, 2
0x1400058c7  or      ecx, edx
0x1400058c9  lea     ebx, ds:0[rcx*8]
0x1400058d0  test    r8d, r8d
0x1400058d3  jz      short loc_1400058DD
0x1400058d5  cmp     r8d, 2
0x1400058d9  cmovz   eax, r12d
0x1400058dd  or      ebx, eax
0x1400058df  mov     edx, 0C00h
0x1400058e4  mov     ecx, ebx
0x1400058e6  mov     eax, ebx
0x1400058e8  and     ecx, r12d
0x1400058eb  and     eax, edx
0x1400058ed  cmp     eax, edx
0x1400058ef  jnz     short loc_1400058F5
0x1400058f1  mov     al, 1
0x1400058f3  jmp     short loc_1400058FB
0x1400058f5  test    ecx, ecx
0x1400058f7  jnz     short loc_140005907
0x1400058f9  xor     al, al
0x1400058fb  test    ecx, ecx
0x1400058fd  jz      short loc_140005903
0x1400058ff  test    al, al
0x140005901  jnz     short loc_140005907
0x140005903  xor     eax, eax
0x140005905  jmp     short loc_14000590C
0x140005907  mov     eax, 1
0x14000590c  or      ebx, eax
0x14000590e  mov     eax, [rdi]
0x140005910  cmp     dword ptr [rsp+38h+arg_0], 0
0x140005915  mov     edx, eax
0x140005917  mov     [rdi], eax
0x140005919  jz      short loc_140005956
0x14000591b  test    dl, 2
0x14000591e  jnz     short loc_140005956
0x140005920  mov     eax, ebx
0x140005922  xor     eax, edx
0x140005924  and     eax, 180h
0x140005929  xor     eax, edx
0x14000592b  mov     ecx, eax
0x14000592d  xor     ecx, ebx
0x14000592f  and     ecx, r12d
0x140005932  xor     ecx, eax
0x140005934  mov     eax, ecx
0x140005936  xor     eax, ebx
0x140005938  and     eax, 1
0x14000593b  xor     eax, ecx
0x14000593d  mov     r8d, eax
0x140005940  xor     r8d, ebx
0x140005943  and     r8d, 800h
0x14000594a  xor     r8d, eax
0x14000594d  or      r8d, 2
0x140005951  mov     [rdi], r8d
0x140005954  jmp     short loc_140005959
0x140005956  mov     r8d, edx
0x140005959  mov     r9d, edx
0x14000595c  and     r9d, 4
0x140005960  jnz     short loc_140005977
0x140005962  mov     ecx, ebx
0x140005964  xor     ecx, r8d
0x140005967  and     ecx, 400h
0x14000596d  xor     ecx, r8d
0x140005970  or      ecx, 4
0x140005973  mov     [rdi], ecx
0x140005975  jmp     short loc_14000597A
0x140005977  mov     ecx, r8d
0x14000597a  mov     eax, edx
0x14000597c  lock cmpxchg [rsi], ecx
0x140005980  jnz     short loc_140005910
0x140005982  test    r9d, r9d
0x140005985  jnz     short loc_140005996
0x140005987  mov     r8d, ebp
0x14000598a  lea     edx, [r9+1]
0x14000598e  mov     rcx, rsi
0x140005991  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140005996  test    byte ptr [rdi], 2
0x140005999  jnz     short loc_1400059C5
0x14000599b  mov     eax, [rdi]
0x14000599d  xor     eax, ebx
0x14000599f  and     eax, 180h
0x1400059a4  xor     eax, [rdi]
0x1400059a6  mov     ecx, eax
0x1400059a8  xor     ecx, ebx
0x1400059aa  and     ecx, r12d
0x1400059ad  xor     ecx, eax
0x1400059af  mov     edx, ecx
0x1400059b1  xor     edx, ebx
0x1400059b3  and     edx, 1
0x1400059b6  xor     edx, ecx
0x1400059b8  mov     eax, edx
0x1400059ba  xor     eax, ebx
0x1400059bc  and     eax, 800h
0x1400059c1  xor     eax, edx
0x1400059c3  mov     [rdi], eax
0x1400059c5  mov     rbx, [rsp+38h+arg_8]
0x1400059ca  mov     rax, rdi
0x1400059cd  mov     rbp, [rsp+38h+arg_10]
0x1400059d2  add     rsp, 20h
0x1400059d6  pop     r12
0x1400059d8  pop     rdi
0x1400059d9  pop     rsi
0x1400059da  retn
```

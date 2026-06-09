# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::GetCachedFeatureEnabledState(void)

- ea: `0x140007140`
- end: `0x1400072fb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `443`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011d74`

## callees

- `0x140006cac`
- `0x140007140`
- `0x1400114d4`
- `0x140014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ChangePathRegistryKeyForMFAFeature>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_ChangePathRegistryKeyForMFAFeature__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ChangePathRegistryKeyForMFAFeature__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(49803604, 0, &v19);
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
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
    {
LABEL_16:
      v10 = 1;
      goto LABEL_17;
    }
    v9 = 0;
  }
  if ( (v8 & 0x40) != 0 && v9 )
    goto LABEL_16;
  v10 = 0;
LABEL_17:
  v11 = v10 | v8;
  if ( !v4 )
    LODWORD(v19) = 0;
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
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_ChangePathRegistryKeyForMFAFeature__descriptor,
            v17,
            v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_ChangePathRegistryKeyForMFAFeature__descriptor,
      0,
      v4);
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
0x140007140  mov     [rsp+arg_8], rbx
0x140007145  mov     [rsp+arg_10], rbp
0x14000714a  mov     [rsp+arg_0], rcx
0x14000714f  push    rsi
0x140007150  push    rdi
0x140007151  push    r15
0x140007153  sub     rsp, 20h
0x140007157  mov     rsi, cs:Feature_ChangePathRegistryKeyForMFAFeature__descriptor
0x14000715e  mov     rdi, rdx
0x140007161  mov     qword ptr [rdx], 0
0x140007168  mov     eax, [rsi]
0x14000716a  mov     [rdx], eax
0x14000716c  and     eax, 6
0x14000716f  cmp     al, 6
0x140007171  jz      loc_1400072E5
0x140007177  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000717c  mov     ebp, eax
0x14000717e  mov     dword ptr [rsp+38h+arg_0], 0
0x140007186  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000718d  xor     edx, edx
0x14000718f  test    rax, rax
0x140007192  jnz     short loc_1400071A0
0x140007194  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000719b  test    rax, rax
0x14000719e  jz      short loc_1400071B1
0x1400071a0  lea     r8, [rsp+38h+arg_0]
0x1400071a5  mov     ecx, 2F7F154h
0x1400071aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071af  mov     edx, eax
0x1400071b1  mov     r8d, edx
0x1400071b4  mov     eax, edx
0x1400071b6  and     r8d, 0FFFFFF3Fh
0x1400071bd  and     edx, 80h
0x1400071c3  mov     ecx, r8d
0x1400071c6  mov     r15d, 40h ; '@'
0x1400071cc  and     ecx, 3
0x1400071cf  and     eax, r15d
0x1400071d2  shl     ecx, 2
0x1400071d5  or      ecx, eax
0x1400071d7  shl     ecx, 2
0x1400071da  or      ecx, edx
0x1400071dc  lea     ebx, ds:0[rcx*8]
0x1400071e3  test    r8d, r8d
0x1400071e6  jnz     short loc_1400071ED
0x1400071e8  mov     eax, r15d
0x1400071eb  jmp     short loc_1400071F7
0x1400071ed  xor     eax, eax
0x1400071ef  cmp     r8d, 2
0x1400071f3  cmovz   eax, r15d
0x1400071f7  or      ebx, eax
0x1400071f9  mov     edx, 0C00h
0x1400071fe  mov     ecx, ebx
0x140007200  mov     eax, ebx
0x140007202  and     ecx, r15d
0x140007205  and     eax, edx
0x140007207  cmp     eax, edx
0x140007209  jnz     short loc_14000720F
0x14000720b  mov     al, 1
0x14000720d  jmp     short loc_140007215
0x14000720f  test    ecx, ecx
0x140007211  jnz     short loc_140007221
0x140007213  xor     al, al
0x140007215  test    ecx, ecx
0x140007217  jz      short loc_14000721D
0x140007219  test    al, al
0x14000721b  jnz     short loc_140007221
0x14000721d  xor     eax, eax
0x14000721f  jmp     short loc_140007226
0x140007221  mov     eax, 1
0x140007226  or      ebx, eax
0x140007228  test    ebp, ebp
0x14000722a  jnz     short loc_140007230
0x14000722c  mov     dword ptr [rsp+38h+arg_0], ebp
0x140007230  mov     eax, [rdi]
0x140007232  cmp     dword ptr [rsp+38h+arg_0], 0
0x140007237  mov     edx, eax
0x140007239  mov     [rdi], eax
0x14000723b  jz      short loc_140007278
0x14000723d  test    dl, 2
0x140007240  jnz     short loc_140007278
0x140007242  mov     eax, ebx
0x140007244  xor     eax, edx
0x140007246  and     eax, 180h
0x14000724b  xor     eax, edx
0x14000724d  mov     ecx, eax
0x14000724f  xor     ecx, ebx
0x140007251  and     ecx, r15d
0x140007254  xor     ecx, eax
0x140007256  mov     eax, ecx
0x140007258  xor     eax, ebx
0x14000725a  and     eax, 1
0x14000725d  xor     eax, ecx
0x14000725f  mov     r8d, eax
0x140007262  xor     r8d, ebx
0x140007265  and     r8d, 800h
0x14000726c  xor     r8d, eax
0x14000726f  or      r8d, 2
0x140007273  mov     [rdi], r8d
0x140007276  jmp     short loc_14000727B
0x140007278  mov     r8d, edx
0x14000727b  mov     r9d, edx
0x14000727e  and     r9d, 4
0x140007282  jnz     short loc_140007299
0x140007284  mov     ecx, ebx
0x140007286  xor     ecx, r8d
0x140007289  and     ecx, 400h
0x14000728f  xor     ecx, r8d
0x140007292  or      ecx, 4
0x140007295  mov     [rdi], ecx
0x140007297  jmp     short loc_14000729C
0x140007299  mov     ecx, r8d
0x14000729c  mov     eax, edx
0x14000729e  lock cmpxchg [rsi], ecx
0x1400072a2  jnz     short loc_140007232
0x1400072a4  test    r9d, r9d
0x1400072a7  jnz     short loc_1400072B6
0x1400072a9  mov     r8d, ebp
0x1400072ac  xor     edx, edx
0x1400072ae  mov     rcx, rsi
0x1400072b1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400072b6  test    byte ptr [rdi], 2
0x1400072b9  jnz     short loc_1400072E5
0x1400072bb  mov     eax, [rdi]
0x1400072bd  xor     eax, ebx
0x1400072bf  and     eax, 180h
0x1400072c4  xor     eax, [rdi]
0x1400072c6  mov     ecx, eax
0x1400072c8  xor     ecx, ebx
0x1400072ca  and     ecx, r15d
0x1400072cd  xor     ecx, eax
0x1400072cf  mov     edx, ecx
0x1400072d1  xor     edx, ebx
0x1400072d3  and     edx, 1
0x1400072d6  xor     edx, ecx
0x1400072d8  mov     eax, edx
0x1400072da  xor     eax, ebx
0x1400072dc  and     eax, 800h
0x1400072e1  xor     eax, edx
0x1400072e3  mov     [rdi], eax
0x1400072e5  mov     rbx, [rsp+38h+arg_8]
0x1400072ea  mov     rax, rdi
0x1400072ed  mov     rbp, [rsp+38h+arg_10]
0x1400072f2  add     rsp, 20h
0x1400072f6  pop     r15
0x1400072f8  pop     rdi
0x1400072f9  pop     rsi
0x1400072fa  retn
```

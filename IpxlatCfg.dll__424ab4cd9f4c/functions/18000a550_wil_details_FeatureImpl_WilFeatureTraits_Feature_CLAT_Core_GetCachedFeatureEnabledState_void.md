# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::GetCachedFeatureEnabledState(void)

- ea: `0x18000a550`
- end: `0x18000a70c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `444`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aff4`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000a550`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Core__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Core__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56662908, 3, &v19);
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
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
      goto LABEL_17;
    v9 = 0;
  }
  if ( (v8 & 0x40) == 0 || !v9 )
  {
    v10 = 0;
    goto LABEL_18;
  }
LABEL_17:
  v10 = 1;
LABEL_18:
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Core__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Core__descriptor, 3, v4);
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
0x18000a550  mov     [rsp+arg_8], rbx
0x18000a555  mov     [rsp+arg_10], rbp
0x18000a55a  mov     [rsp+arg_0], rcx
0x18000a55f  push    rsi
0x18000a560  push    rdi
0x18000a561  push    r15
0x18000a563  sub     rsp, 20h
0x18000a567  mov     rsi, cs:Feature_CLAT_Core__descriptor
0x18000a56e  mov     rdi, rdx
0x18000a571  mov     qword ptr [rdx], 0
0x18000a578  mov     eax, [rsi]
0x18000a57a  mov     [rdx], eax
0x18000a57c  and     eax, 6
0x18000a57f  cmp     al, 6
0x18000a581  jz      loc_18000A6F6
0x18000a587  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a58c  mov     ebp, eax
0x18000a58e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000a596  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000a59d  test    rax, rax
0x18000a5a0  jz      short loc_18000A5BA
0x18000a5a2  lea     r8, [rsp+38h+arg_0]
0x18000a5a7  mov     edx, 3
0x18000a5ac  mov     ecx, 3609B7Ch
0x18000a5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b6  mov     edx, eax
0x18000a5b8  jmp     short loc_18000A5C8
0x18000a5ba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000a5c1  test    rax, rax
0x18000a5c4  jnz     short loc_18000A5A2
0x18000a5c6  xor     edx, edx
0x18000a5c8  mov     r8d, edx
0x18000a5cb  mov     eax, edx
0x18000a5cd  and     r8d, 0FFFFFF3Fh
0x18000a5d4  and     edx, 80h
0x18000a5da  mov     ecx, r8d
0x18000a5dd  mov     r15d, 40h ; '@'
0x18000a5e3  and     ecx, 3
0x18000a5e6  and     eax, r15d
0x18000a5e9  shl     ecx, 2
0x18000a5ec  or      ecx, eax
0x18000a5ee  shl     ecx, 2
0x18000a5f1  or      ecx, edx
0x18000a5f3  lea     ebx, ds:0[rcx*8]
0x18000a5fa  test    r8d, r8d
0x18000a5fd  jnz     short loc_18000A604
0x18000a5ff  mov     eax, r15d
0x18000a602  jmp     short loc_18000A60E
0x18000a604  xor     eax, eax
0x18000a606  cmp     r8d, 2
0x18000a60a  cmovz   eax, r15d
0x18000a60e  or      ebx, eax
0x18000a610  mov     edx, 0C00h
0x18000a615  mov     ecx, ebx
0x18000a617  mov     eax, ebx
0x18000a619  and     ecx, r15d
0x18000a61c  and     eax, edx
0x18000a61e  cmp     eax, edx
0x18000a620  jnz     short loc_18000A626
0x18000a622  mov     al, 1
0x18000a624  jmp     short loc_18000A62C
0x18000a626  test    ecx, ecx
0x18000a628  jnz     short loc_18000A638
0x18000a62a  xor     al, al
0x18000a62c  test    ecx, ecx
0x18000a62e  jz      short loc_18000A634
0x18000a630  test    al, al
0x18000a632  jnz     short loc_18000A638
0x18000a634  xor     eax, eax
0x18000a636  jmp     short loc_18000A63D
0x18000a638  mov     eax, 1
0x18000a63d  or      ebx, eax
0x18000a63f  mov     eax, [rdi]
0x18000a641  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000a646  mov     edx, eax
0x18000a648  mov     [rdi], eax
0x18000a64a  jz      short loc_18000A687
0x18000a64c  test    dl, 2
0x18000a64f  jnz     short loc_18000A687
0x18000a651  mov     eax, ebx
0x18000a653  xor     eax, edx
0x18000a655  and     eax, 180h
0x18000a65a  xor     eax, edx
0x18000a65c  mov     ecx, eax
0x18000a65e  xor     ecx, ebx
0x18000a660  and     ecx, r15d
0x18000a663  xor     ecx, eax
0x18000a665  mov     eax, ecx
0x18000a667  xor     eax, ebx
0x18000a669  and     eax, 1
0x18000a66c  xor     eax, ecx
0x18000a66e  mov     r8d, eax
0x18000a671  xor     r8d, ebx
0x18000a674  and     r8d, 800h
0x18000a67b  xor     r8d, eax
0x18000a67e  or      r8d, 2
0x18000a682  mov     [rdi], r8d
0x18000a685  jmp     short loc_18000A68A
0x18000a687  mov     r8d, edx
0x18000a68a  mov     r9d, edx
0x18000a68d  and     r9d, 4
0x18000a691  jnz     short loc_18000A6A8
0x18000a693  mov     ecx, ebx
0x18000a695  xor     ecx, r8d
0x18000a698  and     ecx, 400h
0x18000a69e  xor     ecx, r8d
0x18000a6a1  or      ecx, 4
0x18000a6a4  mov     [rdi], ecx
0x18000a6a6  jmp     short loc_18000A6AB
0x18000a6a8  mov     ecx, r8d
0x18000a6ab  mov     eax, edx
0x18000a6ad  lock cmpxchg [rsi], ecx
0x18000a6b1  jnz     short loc_18000A641
0x18000a6b3  test    r9d, r9d
0x18000a6b6  jnz     short loc_18000A6C7
0x18000a6b8  mov     r8d, ebp
0x18000a6bb  lea     edx, [r9+3]
0x18000a6bf  mov     rcx, rsi
0x18000a6c2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a6c7  test    byte ptr [rdi], 2
0x18000a6ca  jnz     short loc_18000A6F6
0x18000a6cc  mov     eax, [rdi]
0x18000a6ce  xor     eax, ebx
0x18000a6d0  and     eax, 180h
0x18000a6d5  xor     eax, [rdi]
0x18000a6d7  mov     ecx, eax
0x18000a6d9  xor     ecx, ebx
0x18000a6db  and     ecx, r15d
0x18000a6de  xor     ecx, eax
0x18000a6e0  mov     edx, ecx
0x18000a6e2  xor     edx, ebx
0x18000a6e4  and     edx, 1
0x18000a6e7  xor     edx, ecx
0x18000a6e9  mov     eax, edx
0x18000a6eb  xor     eax, ebx
0x18000a6ed  and     eax, 800h
0x18000a6f2  xor     eax, edx
0x18000a6f4  mov     [rdi], eax
0x18000a6f6  mov     rbx, [rsp+38h+arg_8]
0x18000a6fb  mov     rax, rdi
0x18000a6fe  mov     rbp, [rsp+38h+arg_10]
0x18000a703  add     rsp, 20h
0x18000a707  pop     r15
0x18000a709  pop     rdi
0x18000a70a  pop     rsi
0x18000a70b  retn
```

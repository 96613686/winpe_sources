# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImproveFrequencyToastMfa>::GetCachedFeatureEnabledState(void)

- ea: `0x1400074c0`
- end: `0x14000767b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImproveFrequencyToastMfa@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `443`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011ea4`

## callees

- `0x140006cac`
- `0x1400074c0`
- `0x1400114d4`
- `0x140014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImproveFrequencyToastMfa>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ImproveFrequencyToastMfa__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ImproveFrequencyToastMfa__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(52432863, 0, &v19);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ImproveFrequencyToastMfa__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ImproveFrequencyToastMfa__descriptor, 0, v4);
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
0x1400074c0  mov     [rsp+arg_8], rbx
0x1400074c5  mov     [rsp+arg_10], rbp
0x1400074ca  mov     [rsp+arg_0], rcx
0x1400074cf  push    rsi
0x1400074d0  push    rdi
0x1400074d1  push    r15
0x1400074d3  sub     rsp, 20h
0x1400074d7  mov     rsi, cs:Feature_ImproveFrequencyToastMfa__descriptor
0x1400074de  mov     rdi, rdx
0x1400074e1  mov     qword ptr [rdx], 0
0x1400074e8  mov     eax, [rsi]
0x1400074ea  mov     [rdx], eax
0x1400074ec  and     eax, 6
0x1400074ef  cmp     al, 6
0x1400074f1  jz      loc_140007665
0x1400074f7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400074fc  mov     ebp, eax
0x1400074fe  mov     dword ptr [rsp+38h+arg_0], 0
0x140007506  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000750d  xor     edx, edx
0x14000750f  test    rax, rax
0x140007512  jnz     short loc_140007520
0x140007514  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000751b  test    rax, rax
0x14000751e  jz      short loc_140007531
0x140007520  lea     r8, [rsp+38h+arg_0]
0x140007525  mov     ecx, 3200FDFh
0x14000752a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000752f  mov     edx, eax
0x140007531  mov     r8d, edx
0x140007534  mov     eax, edx
0x140007536  and     r8d, 0FFFFFF3Fh
0x14000753d  and     edx, 80h
0x140007543  mov     ecx, r8d
0x140007546  mov     r15d, 40h ; '@'
0x14000754c  and     ecx, 3
0x14000754f  and     eax, r15d
0x140007552  shl     ecx, 2
0x140007555  or      ecx, eax
0x140007557  shl     ecx, 2
0x14000755a  or      ecx, edx
0x14000755c  lea     ebx, ds:0[rcx*8]
0x140007563  test    r8d, r8d
0x140007566  jnz     short loc_14000756D
0x140007568  mov     eax, r15d
0x14000756b  jmp     short loc_140007577
0x14000756d  xor     eax, eax
0x14000756f  cmp     r8d, 2
0x140007573  cmovz   eax, r15d
0x140007577  or      ebx, eax
0x140007579  mov     edx, 0C00h
0x14000757e  mov     ecx, ebx
0x140007580  mov     eax, ebx
0x140007582  and     ecx, r15d
0x140007585  and     eax, edx
0x140007587  cmp     eax, edx
0x140007589  jnz     short loc_14000758F
0x14000758b  mov     al, 1
0x14000758d  jmp     short loc_140007595
0x14000758f  test    ecx, ecx
0x140007591  jnz     short loc_1400075A1
0x140007593  xor     al, al
0x140007595  test    ecx, ecx
0x140007597  jz      short loc_14000759D
0x140007599  test    al, al
0x14000759b  jnz     short loc_1400075A1
0x14000759d  xor     eax, eax
0x14000759f  jmp     short loc_1400075A6
0x1400075a1  mov     eax, 1
0x1400075a6  or      ebx, eax
0x1400075a8  test    ebp, ebp
0x1400075aa  jnz     short loc_1400075B0
0x1400075ac  mov     dword ptr [rsp+38h+arg_0], ebp
0x1400075b0  mov     eax, [rdi]
0x1400075b2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400075b7  mov     edx, eax
0x1400075b9  mov     [rdi], eax
0x1400075bb  jz      short loc_1400075F8
0x1400075bd  test    dl, 2
0x1400075c0  jnz     short loc_1400075F8
0x1400075c2  mov     eax, ebx
0x1400075c4  xor     eax, edx
0x1400075c6  and     eax, 180h
0x1400075cb  xor     eax, edx
0x1400075cd  mov     ecx, eax
0x1400075cf  xor     ecx, ebx
0x1400075d1  and     ecx, r15d
0x1400075d4  xor     ecx, eax
0x1400075d6  mov     eax, ecx
0x1400075d8  xor     eax, ebx
0x1400075da  and     eax, 1
0x1400075dd  xor     eax, ecx
0x1400075df  mov     r8d, eax
0x1400075e2  xor     r8d, ebx
0x1400075e5  and     r8d, 800h
0x1400075ec  xor     r8d, eax
0x1400075ef  or      r8d, 2
0x1400075f3  mov     [rdi], r8d
0x1400075f6  jmp     short loc_1400075FB
0x1400075f8  mov     r8d, edx
0x1400075fb  mov     r9d, edx
0x1400075fe  and     r9d, 4
0x140007602  jnz     short loc_140007619
0x140007604  mov     ecx, ebx
0x140007606  xor     ecx, r8d
0x140007609  and     ecx, 400h
0x14000760f  xor     ecx, r8d
0x140007612  or      ecx, 4
0x140007615  mov     [rdi], ecx
0x140007617  jmp     short loc_14000761C
0x140007619  mov     ecx, r8d
0x14000761c  mov     eax, edx
0x14000761e  lock cmpxchg [rsi], ecx
0x140007622  jnz     short loc_1400075B2
0x140007624  test    r9d, r9d
0x140007627  jnz     short loc_140007636
0x140007629  mov     r8d, ebp
0x14000762c  xor     edx, edx
0x14000762e  mov     rcx, rsi
0x140007631  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007636  test    byte ptr [rdi], 2
0x140007639  jnz     short loc_140007665
0x14000763b  mov     eax, [rdi]
0x14000763d  xor     eax, ebx
0x14000763f  and     eax, 180h
0x140007644  xor     eax, [rdi]
0x140007646  mov     ecx, eax
0x140007648  xor     ecx, ebx
0x14000764a  and     ecx, r15d
0x14000764d  xor     ecx, eax
0x14000764f  mov     edx, ecx
0x140007651  xor     edx, ebx
0x140007653  and     edx, 1
0x140007656  xor     edx, ecx
0x140007658  mov     eax, edx
0x14000765a  xor     eax, ebx
0x14000765c  and     eax, 800h
0x140007661  xor     eax, edx
0x140007663  mov     [rdi], eax
0x140007665  mov     rbx, [rsp+38h+arg_8]
0x14000766a  mov     rax, rdi
0x14000766d  mov     rbp, [rsp+38h+arg_10]
0x140007672  add     rsp, 20h
0x140007676  pop     r15
0x140007678  pop     rdi
0x140007679  pop     rsi
0x14000767a  retn
```

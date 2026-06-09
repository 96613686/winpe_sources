# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MFACheckInClipRenew>::GetCachedFeatureEnabledState(void)

- ea: `0x140007684`
- end: `0x1400077f3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MFACheckInClipRenew@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `367`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011f3c`
- `0x140012a38`

## callees

- `0x140006cac`
- `0x140007684`
- `0x1400114d4`
- `0x140014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MFACheckInClipRenew>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_MFACheckInClipRenew__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MFACheckInClipRenew__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(38124097, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MFACheckInClipRenew__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_MFACheckInClipRenew__descriptor, 0, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x140007684  mov     [rsp+arg_8], rbx
0x140007689  mov     [rsp+arg_10], rbp
0x14000768e  mov     [rsp+arg_0], rcx
0x140007693  push    rsi
0x140007694  push    rdi
0x140007695  push    r15
0x140007697  sub     rsp, 20h
0x14000769b  mov     rsi, cs:Feature_MFACheckInClipRenew__descriptor
0x1400076a2  mov     rbx, rdx
0x1400076a5  mov     qword ptr [rdx], 0
0x1400076ac  mov     eax, [rsi]
0x1400076ae  mov     [rdx], eax
0x1400076b0  and     eax, 6
0x1400076b3  cmp     al, 6
0x1400076b5  jz      loc_1400077DD
0x1400076bb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400076c0  mov     ebp, eax
0x1400076c2  mov     dword ptr [rsp+38h+arg_0], 0
0x1400076ca  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400076d1  xor     edx, edx
0x1400076d3  test    rax, rax
0x1400076d6  jnz     short loc_1400076E4
0x1400076d8  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400076df  test    rax, rax
0x1400076e2  jz      short loc_1400076F5
0x1400076e4  lea     r8, [rsp+38h+arg_0]
0x1400076e9  mov     ecx, 245BA41h
0x1400076ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400076f3  mov     edx, eax
0x1400076f5  mov     r8d, edx
0x1400076f8  mov     eax, edx
0x1400076fa  and     r8d, 0FFFFFF3Fh
0x140007701  and     edx, 80h
0x140007707  mov     ecx, r8d
0x14000770a  mov     r15d, 40h ; '@'
0x140007710  and     ecx, 3
0x140007713  and     eax, r15d
0x140007716  shl     ecx, 2
0x140007719  or      ecx, eax
0x14000771b  shl     ecx, 2
0x14000771e  or      ecx, edx
0x140007720  lea     edi, ds:0[rcx*8]
0x140007727  test    r8d, r8d
0x14000772a  jnz     short loc_140007731
0x14000772c  mov     eax, r15d
0x14000772f  jmp     short loc_14000773B
0x140007731  xor     eax, eax
0x140007733  cmp     r8d, 2
0x140007737  cmovz   eax, r15d
0x14000773b  or      edi, eax
0x14000773d  test    ebp, ebp
0x14000773f  jnz     short loc_140007745
0x140007741  mov     dword ptr [rsp+38h+arg_0], ebp
0x140007745  mov     eax, [rbx]
0x140007747  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000774c  mov     edx, eax
0x14000774e  mov     [rbx], eax
0x140007750  jz      short loc_14000777C
0x140007752  test    dl, 2
0x140007755  jnz     short loc_14000777C
0x140007757  xor     eax, edi
0x140007759  and     eax, 180h
0x14000775e  xor     eax, edx
0x140007760  mov     ecx, eax
0x140007762  xor     ecx, edi
0x140007764  and     ecx, r15d
0x140007767  xor     ecx, eax
0x140007769  or      ecx, 1
0x14000776c  mov     eax, ecx
0x14000776e  xor     eax, edi
0x140007770  and     eax, 800h
0x140007775  xor     eax, ecx
0x140007777  or      eax, 2
0x14000777a  mov     [rbx], eax
0x14000777c  mov     r8d, edx
0x14000777f  and     r8d, 4
0x140007783  jnz     short loc_140007798
0x140007785  mov     ecx, edi
0x140007787  xor     ecx, eax
0x140007789  and     ecx, 400h
0x14000778f  xor     ecx, eax
0x140007791  or      ecx, 4
0x140007794  mov     [rbx], ecx
0x140007796  jmp     short loc_14000779A
0x140007798  mov     ecx, eax
0x14000779a  mov     eax, edx
0x14000779c  lock cmpxchg [rsi], ecx
0x1400077a0  jnz     short loc_140007747
0x1400077a2  test    r8d, r8d
0x1400077a5  jnz     short loc_1400077B4
0x1400077a7  mov     r8d, ebp
0x1400077aa  xor     edx, edx
0x1400077ac  mov     rcx, rsi
0x1400077af  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400077b4  test    byte ptr [rbx], 2
0x1400077b7  jnz     short loc_1400077DD
0x1400077b9  mov     eax, [rbx]
0x1400077bb  xor     eax, edi
0x1400077bd  and     eax, 180h
0x1400077c2  xor     eax, [rbx]
0x1400077c4  mov     ecx, eax
0x1400077c6  xor     ecx, edi
0x1400077c8  and     ecx, r15d
0x1400077cb  xor     ecx, eax
0x1400077cd  or      ecx, 1
0x1400077d0  mov     eax, ecx
0x1400077d2  xor     eax, edi
0x1400077d4  and     eax, 800h
0x1400077d9  xor     eax, ecx
0x1400077db  mov     [rbx], eax
0x1400077dd  mov     rbp, [rsp+38h+arg_10]
0x1400077e2  mov     rax, rbx
0x1400077e5  mov     rbx, [rsp+38h+arg_8]
0x1400077ea  add     rsp, 20h
0x1400077ee  pop     r15
0x1400077f0  pop     rdi
0x1400077f1  pop     rsi
0x1400077f2  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)

- ea: `0x180013200`
- end: `0x180013377`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014478`
- `0x180018bbc`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013200`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_ImplVal__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ImplVal__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(54237993, 3, &v14);
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
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ImplVal__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ImplVal__descriptor, 3, v4);
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
0x180013200  mov     [rsp+arg_8], rbx
0x180013205  mov     [rsp+arg_10], rbp
0x18001320a  mov     [rsp+arg_0], rcx
0x18001320f  push    rsi
0x180013210  push    rdi
0x180013211  push    r15
0x180013213  sub     rsp, 20h
0x180013217  mov     rsi, cs:Feature_ImplVal__descriptor
0x18001321e  mov     rbx, rdx
0x180013221  mov     qword ptr [rdx], 0
0x180013228  mov     eax, [rsi]
0x18001322a  mov     [rdx], eax
0x18001322c  and     eax, 6
0x18001322f  cmp     al, 6
0x180013231  jz      loc_180013361
0x180013237  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001323c  mov     ebp, eax
0x18001323e  mov     dword ptr [rsp+38h+arg_0], 0
0x180013246  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001324d  test    rax, rax
0x180013250  jz      short loc_18001326A
0x180013252  lea     r8, [rsp+38h+arg_0]
0x180013257  mov     edx, 3
0x18001325c  mov     ecx, 33B9B29h
0x180013261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013266  mov     edx, eax
0x180013268  jmp     short loc_180013278
0x18001326a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013271  test    rax, rax
0x180013274  jnz     short loc_180013252
0x180013276  xor     edx, edx
0x180013278  mov     r8d, edx
0x18001327b  mov     eax, edx
0x18001327d  and     r8d, 0FFFFFF3Fh
0x180013284  and     edx, 80h
0x18001328a  mov     ecx, r8d
0x18001328d  mov     r15d, 40h ; '@'
0x180013293  and     ecx, 3
0x180013296  and     eax, r15d
0x180013299  shl     ecx, 2
0x18001329c  or      ecx, eax
0x18001329e  shl     ecx, 2
0x1800132a1  or      ecx, edx
0x1800132a3  lea     edi, ds:0[rcx*8]
0x1800132aa  test    r8d, r8d
0x1800132ad  jnz     short loc_1800132B4
0x1800132af  mov     eax, r15d
0x1800132b2  jmp     short loc_1800132BE
0x1800132b4  xor     eax, eax
0x1800132b6  cmp     r8d, 2
0x1800132ba  cmovz   eax, r15d
0x1800132be  or      edi, eax
0x1800132c0  mov     eax, [rbx]
0x1800132c2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800132c7  mov     edx, eax
0x1800132c9  mov     [rbx], eax
0x1800132cb  jz      short loc_1800132FB
0x1800132cd  test    dl, 2
0x1800132d0  jnz     short loc_1800132FB
0x1800132d2  mov     eax, edi
0x1800132d4  xor     eax, edx
0x1800132d6  and     eax, 180h
0x1800132db  xor     eax, edx
0x1800132dd  mov     ecx, eax
0x1800132df  xor     ecx, edi
0x1800132e1  and     ecx, r15d
0x1800132e4  xor     ecx, eax
0x1800132e6  or      ecx, 1
0x1800132e9  mov     eax, ecx
0x1800132eb  xor     eax, edi
0x1800132ed  and     eax, 800h
0x1800132f2  xor     eax, ecx
0x1800132f4  or      eax, 2
0x1800132f7  mov     [rbx], eax
0x1800132f9  jmp     short loc_1800132FD
0x1800132fb  mov     eax, edx
0x1800132fd  mov     r8d, edx
0x180013300  and     r8d, 4
0x180013304  jnz     short loc_180013319
0x180013306  mov     ecx, edi
0x180013308  xor     ecx, eax
0x18001330a  and     ecx, 400h
0x180013310  xor     ecx, eax
0x180013312  or      ecx, 4
0x180013315  mov     [rbx], ecx
0x180013317  jmp     short loc_18001331B
0x180013319  mov     ecx, eax
0x18001331b  mov     eax, edx
0x18001331d  lock cmpxchg [rsi], ecx
0x180013321  jnz     short loc_1800132C2
0x180013323  test    r8d, r8d
0x180013326  jnz     short loc_180013338
0x180013328  mov     r8d, ebp
0x18001332b  mov     edx, 3
0x180013330  mov     rcx, rsi
0x180013333  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013338  test    byte ptr [rbx], 2
0x18001333b  jnz     short loc_180013361
0x18001333d  mov     eax, [rbx]
0x18001333f  xor     eax, edi
0x180013341  and     eax, 180h
0x180013346  xor     eax, [rbx]
0x180013348  mov     ecx, eax
0x18001334a  xor     ecx, edi
0x18001334c  and     ecx, r15d
0x18001334f  xor     ecx, eax
0x180013351  or      ecx, 1
0x180013354  mov     eax, ecx
0x180013356  xor     eax, edi
0x180013358  and     eax, 800h
0x18001335d  xor     eax, ecx
0x18001335f  mov     [rbx], eax
0x180013361  mov     rbp, [rsp+38h+arg_10]
0x180013366  mov     rax, rbx
0x180013369  mov     rbx, [rsp+38h+arg_8]
0x18001336e  add     rsp, 20h
0x180013372  pop     r15
0x180013374  pop     rdi
0x180013375  pop     rsi
0x180013376  retn
```

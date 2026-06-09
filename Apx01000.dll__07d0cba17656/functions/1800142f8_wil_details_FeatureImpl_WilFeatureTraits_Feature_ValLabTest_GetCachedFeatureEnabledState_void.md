# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800142f8`
- end: `0x18001446f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001507c`

## callees

- `0x180004a48`
- `0x180008344`
- `0x1800142f8`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v4);
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
0x1800142f8  mov     [rsp+arg_8], rbx
0x1800142fd  mov     [rsp+arg_10], rbp
0x180014302  mov     [rsp+arg_0], rcx
0x180014307  push    rsi
0x180014308  push    rdi
0x180014309  push    r15
0x18001430b  sub     rsp, 20h
0x18001430f  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180014316  mov     rbx, rdx
0x180014319  mov     qword ptr [rdx], 0
0x180014320  mov     eax, [rsi]
0x180014322  mov     [rdx], eax
0x180014324  and     eax, 6
0x180014327  cmp     al, 6
0x180014329  jz      loc_180014459
0x18001432f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014334  mov     ebp, eax
0x180014336  mov     dword ptr [rsp+38h+arg_0], 0
0x18001433e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014345  test    rax, rax
0x180014348  jz      short loc_180014362
0x18001434a  lea     r8, [rsp+38h+arg_0]
0x18001434f  mov     edx, 3
0x180014354  mov     ecx, 3667CA2h
0x180014359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001435e  mov     edx, eax
0x180014360  jmp     short loc_180014370
0x180014362  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014369  test    rax, rax
0x18001436c  jnz     short loc_18001434A
0x18001436e  xor     edx, edx
0x180014370  mov     r8d, edx
0x180014373  mov     eax, edx
0x180014375  and     r8d, 0FFFFFF3Fh
0x18001437c  and     edx, 80h
0x180014382  mov     ecx, r8d
0x180014385  mov     r15d, 40h ; '@'
0x18001438b  and     ecx, 3
0x18001438e  and     eax, r15d
0x180014391  shl     ecx, 2
0x180014394  or      ecx, eax
0x180014396  shl     ecx, 2
0x180014399  or      ecx, edx
0x18001439b  lea     edi, ds:0[rcx*8]
0x1800143a2  test    r8d, r8d
0x1800143a5  jnz     short loc_1800143AC
0x1800143a7  mov     eax, r15d
0x1800143aa  jmp     short loc_1800143B6
0x1800143ac  xor     eax, eax
0x1800143ae  cmp     r8d, 2
0x1800143b2  cmovz   eax, r15d
0x1800143b6  or      edi, eax
0x1800143b8  mov     eax, [rbx]
0x1800143ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800143bf  mov     edx, eax
0x1800143c1  mov     [rbx], eax
0x1800143c3  jz      short loc_1800143F3
0x1800143c5  test    dl, 2
0x1800143c8  jnz     short loc_1800143F3
0x1800143ca  mov     eax, edi
0x1800143cc  xor     eax, edx
0x1800143ce  and     eax, 180h
0x1800143d3  xor     eax, edx
0x1800143d5  mov     ecx, eax
0x1800143d7  xor     ecx, edi
0x1800143d9  and     ecx, r15d
0x1800143dc  xor     ecx, eax
0x1800143de  or      ecx, 1
0x1800143e1  mov     eax, ecx
0x1800143e3  xor     eax, edi
0x1800143e5  and     eax, 800h
0x1800143ea  xor     eax, ecx
0x1800143ec  or      eax, 2
0x1800143ef  mov     [rbx], eax
0x1800143f1  jmp     short loc_1800143F5
0x1800143f3  mov     eax, edx
0x1800143f5  mov     r8d, edx
0x1800143f8  and     r8d, 4
0x1800143fc  jnz     short loc_180014411
0x1800143fe  mov     ecx, edi
0x180014400  xor     ecx, eax
0x180014402  and     ecx, 400h
0x180014408  xor     ecx, eax
0x18001440a  or      ecx, 4
0x18001440d  mov     [rbx], ecx
0x18001440f  jmp     short loc_180014413
0x180014411  mov     ecx, eax
0x180014413  mov     eax, edx
0x180014415  lock cmpxchg [rsi], ecx
0x180014419  jnz     short loc_1800143BA
0x18001441b  test    r8d, r8d
0x18001441e  jnz     short loc_180014430
0x180014420  mov     r8d, ebp
0x180014423  mov     edx, 3
0x180014428  mov     rcx, rsi
0x18001442b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014430  test    byte ptr [rbx], 2
0x180014433  jnz     short loc_180014459
0x180014435  mov     eax, [rbx]
0x180014437  xor     eax, edi
0x180014439  and     eax, 180h
0x18001443e  xor     eax, [rbx]
0x180014440  mov     ecx, eax
0x180014442  xor     ecx, edi
0x180014444  and     ecx, r15d
0x180014447  xor     ecx, eax
0x180014449  or      ecx, 1
0x18001444c  mov     eax, ecx
0x18001444e  xor     eax, edi
0x180014450  and     eax, 800h
0x180014455  xor     eax, ecx
0x180014457  mov     [rbx], eax
0x180014459  mov     rbp, [rsp+38h+arg_10]
0x18001445e  mov     rax, rbx
0x180014461  mov     rbx, [rsp+38h+arg_8]
0x180014466  add     rsp, 20h
0x18001446a  pop     r15
0x18001446c  pop     rdi
0x18001446d  pop     rsi
0x18001446e  retn
```

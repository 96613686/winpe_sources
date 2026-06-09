# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180014098`
- end: `0x18001420f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800145c0`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180014098`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048218, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxLabTest__descriptor, 3, v4);
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
0x180014098  mov     [rsp+arg_8], rbx
0x18001409d  mov     [rsp+arg_10], rbp
0x1800140a2  mov     [rsp+arg_0], rcx
0x1800140a7  push    rsi
0x1800140a8  push    rdi
0x1800140a9  push    r15
0x1800140ab  sub     rsp, 20h
0x1800140af  mov     rsi, cs:Feature_UxLabTest__descriptor
0x1800140b6  mov     rbx, rdx
0x1800140b9  mov     qword ptr [rdx], 0
0x1800140c0  mov     eax, [rsi]
0x1800140c2  mov     [rdx], eax
0x1800140c4  and     eax, 6
0x1800140c7  cmp     al, 6
0x1800140c9  jz      loc_1800141F9
0x1800140cf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800140d4  mov     ebp, eax
0x1800140d6  mov     dword ptr [rsp+38h+arg_0], 0
0x1800140de  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800140e5  test    rax, rax
0x1800140e8  jz      short loc_180014102
0x1800140ea  lea     r8, [rsp+38h+arg_0]
0x1800140ef  mov     edx, 3
0x1800140f4  mov     ecx, 3667C9Ah
0x1800140f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140fe  mov     edx, eax
0x180014100  jmp     short loc_180014110
0x180014102  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014109  test    rax, rax
0x18001410c  jnz     short loc_1800140EA
0x18001410e  xor     edx, edx
0x180014110  mov     r8d, edx
0x180014113  mov     eax, edx
0x180014115  and     r8d, 0FFFFFF3Fh
0x18001411c  and     edx, 80h
0x180014122  mov     ecx, r8d
0x180014125  mov     r15d, 40h ; '@'
0x18001412b  and     ecx, 3
0x18001412e  and     eax, r15d
0x180014131  shl     ecx, 2
0x180014134  or      ecx, eax
0x180014136  shl     ecx, 2
0x180014139  or      ecx, edx
0x18001413b  lea     edi, ds:0[rcx*8]
0x180014142  test    r8d, r8d
0x180014145  jnz     short loc_18001414C
0x180014147  mov     eax, r15d
0x18001414a  jmp     short loc_180014156
0x18001414c  xor     eax, eax
0x18001414e  cmp     r8d, 2
0x180014152  cmovz   eax, r15d
0x180014156  or      edi, eax
0x180014158  mov     eax, [rbx]
0x18001415a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001415f  mov     edx, eax
0x180014161  mov     [rbx], eax
0x180014163  jz      short loc_180014193
0x180014165  test    dl, 2
0x180014168  jnz     short loc_180014193
0x18001416a  mov     eax, edi
0x18001416c  xor     eax, edx
0x18001416e  and     eax, 180h
0x180014173  xor     eax, edx
0x180014175  mov     ecx, eax
0x180014177  xor     ecx, edi
0x180014179  and     ecx, r15d
0x18001417c  xor     ecx, eax
0x18001417e  or      ecx, 1
0x180014181  mov     eax, ecx
0x180014183  xor     eax, edi
0x180014185  and     eax, 800h
0x18001418a  xor     eax, ecx
0x18001418c  or      eax, 2
0x18001418f  mov     [rbx], eax
0x180014191  jmp     short loc_180014195
0x180014193  mov     eax, edx
0x180014195  mov     r8d, edx
0x180014198  and     r8d, 4
0x18001419c  jnz     short loc_1800141B1
0x18001419e  mov     ecx, edi
0x1800141a0  xor     ecx, eax
0x1800141a2  and     ecx, 400h
0x1800141a8  xor     ecx, eax
0x1800141aa  or      ecx, 4
0x1800141ad  mov     [rbx], ecx
0x1800141af  jmp     short loc_1800141B3
0x1800141b1  mov     ecx, eax
0x1800141b3  mov     eax, edx
0x1800141b5  lock cmpxchg [rsi], ecx
0x1800141b9  jnz     short loc_18001415A
0x1800141bb  test    r8d, r8d
0x1800141be  jnz     short loc_1800141D0
0x1800141c0  mov     r8d, ebp
0x1800141c3  mov     edx, 3
0x1800141c8  mov     rcx, rsi
0x1800141cb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800141d0  test    byte ptr [rbx], 2
0x1800141d3  jnz     short loc_1800141F9
0x1800141d5  mov     eax, [rbx]
0x1800141d7  xor     eax, edi
0x1800141d9  and     eax, 180h
0x1800141de  xor     eax, [rbx]
0x1800141e0  mov     ecx, eax
0x1800141e2  xor     ecx, edi
0x1800141e4  and     ecx, r15d
0x1800141e7  xor     ecx, eax
0x1800141e9  or      ecx, 1
0x1800141ec  mov     eax, ecx
0x1800141ee  xor     eax, edi
0x1800141f0  and     eax, 800h
0x1800141f5  xor     eax, ecx
0x1800141f7  mov     [rbx], eax
0x1800141f9  mov     rbp, [rsp+38h+arg_10]
0x1800141fe  mov     rax, rbx
0x180014201  mov     rbx, [rsp+38h+arg_8]
0x180014206  add     rsp, 20h
0x18001420a  pop     r15
0x18001420c  pop     rdi
0x18001420d  pop     rsi
0x18001420e  retn
```

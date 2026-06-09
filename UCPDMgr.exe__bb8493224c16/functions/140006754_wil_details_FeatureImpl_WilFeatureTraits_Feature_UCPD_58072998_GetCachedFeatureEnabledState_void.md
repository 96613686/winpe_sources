# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_58072998>::GetCachedFeatureEnabledState(void)

- ea: `0x140006754`
- end: `0x1400068e4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_58072998@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005550`
- `0x1400068ec`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140006754`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_58072998>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // ebp
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // ebx
  signed __int32 v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  int v17; // ecx
  int v19; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v19 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(58072998, 0, &v19);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      v11 = v9 | v10;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = v9;
LABEL_10:
  v12 = v11 | (v11 >> 6) & 1;
  if ( !v5 )
    v19 = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = v19 == 0;
    v15 = v13;
    *(_DWORD *)a2 = v13;
    v16 = v13;
    if ( !v14 && (v13 & 2) == 0 )
    {
      v17 = v13
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)v12)
          & 0x180
          ^ (v12
           ^ v13
           ^ ((unsigned __int16)v13
            ^ (unsigned __int16)v12)
           & 0x180)
          & 0x40;
      v16 = v17
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)v17)
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v17 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v17) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    if ( (v13 & 4) == 0 )
    {
      v16 = ((unsigned __int16)v16 ^ (unsigned __int16)v12) & 0x400 ^ v16 | 4;
      *(_DWORD *)a2 = v16;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v16, v13);
  }
  while ( v15 != v13 );
  if ( (v15 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v12)
                   & 0x180
                   ^ (v12
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v12)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v12
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v12)
                    & 0x80
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v12
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v12)
                    & 0x180
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v12)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v12)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140006754  mov     [rsp+arg_10], rbx
0x140006759  mov     [rsp+arg_18], rbp
0x14000675e  push    rsi
0x14000675f  push    rdi
0x140006760  push    r15
0x140006762  sub     rsp, 30h
0x140006766  mov     rax, cs:__security_cookie
0x14000676d  xor     rax, rsp
0x140006770  mov     [rsp+48h+var_20], rax
0x140006775  mov     qword ptr [rdx], 0
0x14000677c  mov     rdi, rdx
0x14000677f  mov     eax, [rcx]
0x140006781  mov     rsi, rcx
0x140006784  mov     [rdx], eax
0x140006786  and     eax, 6
0x140006789  cmp     al, 6
0x14000678b  jz      loc_1400068C1
0x140006791  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006796  mov     ebp, eax
0x140006798  mov     [rsp+48h+var_28], 0
0x1400067a0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400067a7  mov     r15d, 40h ; '@'
0x1400067ad  test    rax, rax
0x1400067b0  jnz     short loc_1400067BE
0x1400067b2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400067b9  test    rax, rax
0x1400067bc  jz      short loc_14000680A
0x1400067be  lea     r8, [rsp+48h+var_28]
0x1400067c3  xor     edx, edx
0x1400067c5  mov     ecx, 3761FA6h
0x1400067ca  call    _guard_dispatch_icall
0x1400067cf  mov     r8d, eax
0x1400067d2  mov     edx, eax
0x1400067d4  and     r8d, 0FFFFFF3Fh
0x1400067db  and     eax, r15d
0x1400067de  and     edx, 80h
0x1400067e4  mov     ecx, r8d
0x1400067e7  and     ecx, 3
0x1400067ea  shl     ecx, 2
0x1400067ed  or      ecx, eax
0x1400067ef  shl     ecx, 2
0x1400067f2  or      ecx, edx
0x1400067f4  shl     ecx, 3
0x1400067f7  test    r8d, r8d
0x1400067fa  jz      short loc_14000680C
0x1400067fc  xor     eax, eax
0x1400067fe  cmp     r8d, 2
0x140006802  cmovz   eax, r15d
0x140006806  or      eax, ecx
0x140006808  jmp     short loc_14000680E
0x14000680a  xor     ecx, ecx
0x14000680c  mov     eax, ecx
0x14000680e  mov     ebx, eax
0x140006810  shr     ebx, 6
0x140006813  and     ebx, 1
0x140006816  or      ebx, eax
0x140006818  test    ebp, ebp
0x14000681a  jnz     short loc_140006820
0x14000681c  mov     [rsp+48h+var_28], ebp
0x140006820  mov     eax, [rdi]
0x140006822  cmp     [rsp+48h+var_28], 0
0x140006827  mov     edx, eax
0x140006829  mov     [rdi], eax
0x14000682b  mov     ecx, eax
0x14000682d  jz      short loc_140006862
0x14000682f  test    dl, 2
0x140006832  jnz     short loc_140006862
0x140006834  mov     eax, ebx
0x140006836  xor     eax, ecx
0x140006838  and     eax, 180h
0x14000683d  xor     eax, ecx
0x14000683f  mov     ecx, eax
0x140006841  xor     ecx, ebx
0x140006843  and     ecx, r15d
0x140006846  xor     ecx, eax
0x140006848  mov     eax, ecx
0x14000684a  xor     eax, ebx
0x14000684c  and     eax, 1
0x14000684f  xor     eax, ecx
0x140006851  mov     ecx, eax
0x140006853  xor     ecx, ebx
0x140006855  and     ecx, 800h
0x14000685b  xor     ecx, eax
0x14000685d  or      ecx, 2
0x140006860  mov     [rdi], ecx
0x140006862  test    dl, 4
0x140006865  jnz     short loc_140006877
0x140006867  mov     eax, ebx
0x140006869  xor     eax, ecx
0x14000686b  and     eax, 400h
0x140006870  xor     ecx, eax
0x140006872  or      ecx, 4
0x140006875  mov     [rdi], ecx
0x140006877  mov     eax, edx
0x140006879  lock cmpxchg [rsi], ecx
0x14000687d  jnz     short loc_140006822
0x14000687f  test    dl, 4
0x140006882  jnz     short loc_140006891
0x140006884  mov     r8d, ebp
0x140006887  xor     edx, edx
0x140006889  mov     rcx, rsi
0x14000688c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006891  test    byte ptr [rdi], 2
0x140006894  jnz     short loc_1400068C1
0x140006896  mov     eax, ebx
0x140006898  xor     eax, [rdi]
0x14000689a  and     eax, 180h
0x14000689f  xor     eax, [rdi]
0x1400068a1  mov     ecx, eax
0x1400068a3  xor     ecx, ebx
0x1400068a5  and     ecx, r15d
0x1400068a8  xor     ecx, eax
0x1400068aa  mov     edx, ecx
0x1400068ac  xor     edx, ebx
0x1400068ae  and     edx, 1
0x1400068b1  xor     edx, ecx
0x1400068b3  mov     ecx, edx
0x1400068b5  xor     ecx, ebx
0x1400068b7  and     ecx, 800h
0x1400068bd  xor     ecx, edx
0x1400068bf  mov     [rdi], ecx
0x1400068c1  mov     rax, rdi
0x1400068c4  mov     rcx, [rsp+48h+var_20]
0x1400068c9  xor     rcx, rsp; StackCookie
0x1400068cc  call    __security_check_cookie
0x1400068d1  mov     rbx, [rsp+48h+arg_10]
0x1400068d6  mov     rbp, [rsp+48h+arg_18]
0x1400068db  add     rsp, 30h
0x1400068df  pop     r15
0x1400068e1  pop     rdi
0x1400068e2  pop     rsi
0x1400068e3  retn
```

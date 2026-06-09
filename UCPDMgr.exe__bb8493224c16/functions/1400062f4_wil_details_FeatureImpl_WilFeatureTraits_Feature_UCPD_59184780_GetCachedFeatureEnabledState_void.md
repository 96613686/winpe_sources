# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59184780>::GetCachedFeatureEnabledState(void)

- ea: `0x1400062f4`
- end: `0x140006484`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_59184780@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400054d8`
- `0x14000648c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400062f4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59184780>::GetCachedFeatureEnabledState(
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
    v7 = v6(59184780, 0, &v19);
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
0x1400062f4  mov     [rsp+arg_10], rbx
0x1400062f9  mov     [rsp+arg_18], rbp
0x1400062fe  push    rsi
0x1400062ff  push    rdi
0x140006300  push    r15
0x140006302  sub     rsp, 30h
0x140006306  mov     rax, cs:__security_cookie
0x14000630d  xor     rax, rsp
0x140006310  mov     [rsp+48h+var_20], rax
0x140006315  mov     qword ptr [rdx], 0
0x14000631c  mov     rdi, rdx
0x14000631f  mov     eax, [rcx]
0x140006321  mov     rsi, rcx
0x140006324  mov     [rdx], eax
0x140006326  and     eax, 6
0x140006329  cmp     al, 6
0x14000632b  jz      loc_140006461
0x140006331  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006336  mov     ebp, eax
0x140006338  mov     [rsp+48h+var_28], 0
0x140006340  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006347  mov     r15d, 40h ; '@'
0x14000634d  test    rax, rax
0x140006350  jnz     short loc_14000635E
0x140006352  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140006359  test    rax, rax
0x14000635c  jz      short loc_1400063AA
0x14000635e  lea     r8, [rsp+48h+var_28]
0x140006363  xor     edx, edx
0x140006365  mov     ecx, 387168Ch
0x14000636a  call    _guard_dispatch_icall
0x14000636f  mov     r8d, eax
0x140006372  mov     edx, eax
0x140006374  and     r8d, 0FFFFFF3Fh
0x14000637b  and     eax, r15d
0x14000637e  and     edx, 80h
0x140006384  mov     ecx, r8d
0x140006387  and     ecx, 3
0x14000638a  shl     ecx, 2
0x14000638d  or      ecx, eax
0x14000638f  shl     ecx, 2
0x140006392  or      ecx, edx
0x140006394  shl     ecx, 3
0x140006397  test    r8d, r8d
0x14000639a  jz      short loc_1400063AC
0x14000639c  xor     eax, eax
0x14000639e  cmp     r8d, 2
0x1400063a2  cmovz   eax, r15d
0x1400063a6  or      eax, ecx
0x1400063a8  jmp     short loc_1400063AE
0x1400063aa  xor     ecx, ecx
0x1400063ac  mov     eax, ecx
0x1400063ae  mov     ebx, eax
0x1400063b0  shr     ebx, 6
0x1400063b3  and     ebx, 1
0x1400063b6  or      ebx, eax
0x1400063b8  test    ebp, ebp
0x1400063ba  jnz     short loc_1400063C0
0x1400063bc  mov     [rsp+48h+var_28], ebp
0x1400063c0  mov     eax, [rdi]
0x1400063c2  cmp     [rsp+48h+var_28], 0
0x1400063c7  mov     edx, eax
0x1400063c9  mov     [rdi], eax
0x1400063cb  mov     ecx, eax
0x1400063cd  jz      short loc_140006402
0x1400063cf  test    dl, 2
0x1400063d2  jnz     short loc_140006402
0x1400063d4  mov     eax, ebx
0x1400063d6  xor     eax, ecx
0x1400063d8  and     eax, 180h
0x1400063dd  xor     eax, ecx
0x1400063df  mov     ecx, eax
0x1400063e1  xor     ecx, ebx
0x1400063e3  and     ecx, r15d
0x1400063e6  xor     ecx, eax
0x1400063e8  mov     eax, ecx
0x1400063ea  xor     eax, ebx
0x1400063ec  and     eax, 1
0x1400063ef  xor     eax, ecx
0x1400063f1  mov     ecx, eax
0x1400063f3  xor     ecx, ebx
0x1400063f5  and     ecx, 800h
0x1400063fb  xor     ecx, eax
0x1400063fd  or      ecx, 2
0x140006400  mov     [rdi], ecx
0x140006402  test    dl, 4
0x140006405  jnz     short loc_140006417
0x140006407  mov     eax, ebx
0x140006409  xor     eax, ecx
0x14000640b  and     eax, 400h
0x140006410  xor     ecx, eax
0x140006412  or      ecx, 4
0x140006415  mov     [rdi], ecx
0x140006417  mov     eax, edx
0x140006419  lock cmpxchg [rsi], ecx
0x14000641d  jnz     short loc_1400063C2
0x14000641f  test    dl, 4
0x140006422  jnz     short loc_140006431
0x140006424  mov     r8d, ebp
0x140006427  xor     edx, edx
0x140006429  mov     rcx, rsi
0x14000642c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006431  test    byte ptr [rdi], 2
0x140006434  jnz     short loc_140006461
0x140006436  mov     eax, ebx
0x140006438  xor     eax, [rdi]
0x14000643a  and     eax, 180h
0x14000643f  xor     eax, [rdi]
0x140006441  mov     ecx, eax
0x140006443  xor     ecx, ebx
0x140006445  and     ecx, r15d
0x140006448  xor     ecx, eax
0x14000644a  mov     edx, ecx
0x14000644c  xor     edx, ebx
0x14000644e  and     edx, 1
0x140006451  xor     edx, ecx
0x140006453  mov     ecx, edx
0x140006455  xor     ecx, ebx
0x140006457  and     ecx, 800h
0x14000645d  xor     ecx, edx
0x14000645f  mov     [rdi], ecx
0x140006461  mov     rax, rdi
0x140006464  mov     rcx, [rsp+48h+var_20]
0x140006469  xor     rcx, rsp; StackCookie
0x14000646c  call    __security_check_cookie
0x140006471  mov     rbx, [rsp+48h+arg_10]
0x140006476  mov     rbp, [rsp+48h+arg_18]
0x14000647b  add     rsp, 30h
0x14000647f  pop     r15
0x140006481  pop     rdi
0x140006482  pop     rsi
0x140006483  retn
```

# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59184888>::GetCachedFeatureEnabledState(void)

- ea: `0x140006524`
- end: `0x1400066b4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_59184888@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005514`
- `0x1400066bc`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140006524`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59184888>::GetCachedFeatureEnabledState(
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
    v7 = v6(59184888, 0, &v19);
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
0x140006524  mov     [rsp+arg_10], rbx
0x140006529  mov     [rsp+arg_18], rbp
0x14000652e  push    rsi
0x14000652f  push    rdi
0x140006530  push    r15
0x140006532  sub     rsp, 30h
0x140006536  mov     rax, cs:__security_cookie
0x14000653d  xor     rax, rsp
0x140006540  mov     [rsp+48h+var_20], rax
0x140006545  mov     qword ptr [rdx], 0
0x14000654c  mov     rdi, rdx
0x14000654f  mov     eax, [rcx]
0x140006551  mov     rsi, rcx
0x140006554  mov     [rdx], eax
0x140006556  and     eax, 6
0x140006559  cmp     al, 6
0x14000655b  jz      loc_140006691
0x140006561  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006566  mov     ebp, eax
0x140006568  mov     [rsp+48h+var_28], 0
0x140006570  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006577  mov     r15d, 40h ; '@'
0x14000657d  test    rax, rax
0x140006580  jnz     short loc_14000658E
0x140006582  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140006589  test    rax, rax
0x14000658c  jz      short loc_1400065DA
0x14000658e  lea     r8, [rsp+48h+var_28]
0x140006593  xor     edx, edx
0x140006595  mov     ecx, 38716F8h
0x14000659a  call    _guard_dispatch_icall
0x14000659f  mov     r8d, eax
0x1400065a2  mov     edx, eax
0x1400065a4  and     r8d, 0FFFFFF3Fh
0x1400065ab  and     eax, r15d
0x1400065ae  and     edx, 80h
0x1400065b4  mov     ecx, r8d
0x1400065b7  and     ecx, 3
0x1400065ba  shl     ecx, 2
0x1400065bd  or      ecx, eax
0x1400065bf  shl     ecx, 2
0x1400065c2  or      ecx, edx
0x1400065c4  shl     ecx, 3
0x1400065c7  test    r8d, r8d
0x1400065ca  jz      short loc_1400065DC
0x1400065cc  xor     eax, eax
0x1400065ce  cmp     r8d, 2
0x1400065d2  cmovz   eax, r15d
0x1400065d6  or      eax, ecx
0x1400065d8  jmp     short loc_1400065DE
0x1400065da  xor     ecx, ecx
0x1400065dc  mov     eax, ecx
0x1400065de  mov     ebx, eax
0x1400065e0  shr     ebx, 6
0x1400065e3  and     ebx, 1
0x1400065e6  or      ebx, eax
0x1400065e8  test    ebp, ebp
0x1400065ea  jnz     short loc_1400065F0
0x1400065ec  mov     [rsp+48h+var_28], ebp
0x1400065f0  mov     eax, [rdi]
0x1400065f2  cmp     [rsp+48h+var_28], 0
0x1400065f7  mov     edx, eax
0x1400065f9  mov     [rdi], eax
0x1400065fb  mov     ecx, eax
0x1400065fd  jz      short loc_140006632
0x1400065ff  test    dl, 2
0x140006602  jnz     short loc_140006632
0x140006604  mov     eax, ebx
0x140006606  xor     eax, ecx
0x140006608  and     eax, 180h
0x14000660d  xor     eax, ecx
0x14000660f  mov     ecx, eax
0x140006611  xor     ecx, ebx
0x140006613  and     ecx, r15d
0x140006616  xor     ecx, eax
0x140006618  mov     eax, ecx
0x14000661a  xor     eax, ebx
0x14000661c  and     eax, 1
0x14000661f  xor     eax, ecx
0x140006621  mov     ecx, eax
0x140006623  xor     ecx, ebx
0x140006625  and     ecx, 800h
0x14000662b  xor     ecx, eax
0x14000662d  or      ecx, 2
0x140006630  mov     [rdi], ecx
0x140006632  test    dl, 4
0x140006635  jnz     short loc_140006647
0x140006637  mov     eax, ebx
0x140006639  xor     eax, ecx
0x14000663b  and     eax, 400h
0x140006640  xor     ecx, eax
0x140006642  or      ecx, 4
0x140006645  mov     [rdi], ecx
0x140006647  mov     eax, edx
0x140006649  lock cmpxchg [rsi], ecx
0x14000664d  jnz     short loc_1400065F2
0x14000664f  test    dl, 4
0x140006652  jnz     short loc_140006661
0x140006654  mov     r8d, ebp
0x140006657  xor     edx, edx
0x140006659  mov     rcx, rsi
0x14000665c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006661  test    byte ptr [rdi], 2
0x140006664  jnz     short loc_140006691
0x140006666  mov     eax, ebx
0x140006668  xor     eax, [rdi]
0x14000666a  and     eax, 180h
0x14000666f  xor     eax, [rdi]
0x140006671  mov     ecx, eax
0x140006673  xor     ecx, ebx
0x140006675  and     ecx, r15d
0x140006678  xor     ecx, eax
0x14000667a  mov     edx, ecx
0x14000667c  xor     edx, ebx
0x14000667e  and     edx, 1
0x140006681  xor     edx, ecx
0x140006683  mov     ecx, edx
0x140006685  xor     ecx, ebx
0x140006687  and     ecx, 800h
0x14000668d  xor     ecx, edx
0x14000668f  mov     [rdi], ecx
0x140006691  mov     rax, rdi
0x140006694  mov     rcx, [rsp+48h+var_20]
0x140006699  xor     rcx, rsp; StackCookie
0x14000669c  call    __security_check_cookie
0x1400066a1  mov     rbx, [rsp+48h+arg_10]
0x1400066a6  mov     rbp, [rsp+48h+arg_18]
0x1400066ab  add     rsp, 30h
0x1400066af  pop     r15
0x1400066b1  pop     rdi
0x1400066b2  pop     rsi
0x1400066b3  retn
```

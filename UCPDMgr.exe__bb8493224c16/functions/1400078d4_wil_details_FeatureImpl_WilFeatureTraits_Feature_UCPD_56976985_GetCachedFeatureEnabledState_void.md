# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56976985>::GetCachedFeatureEnabledState(void)

- ea: `0x1400078d4`
- end: `0x140007a64`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_56976985@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005730`
- `0x140007a6c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400078d4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56976985>::GetCachedFeatureEnabledState(
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
    v7 = v6(56976985, 0, &v19);
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
0x1400078d4  mov     [rsp+arg_10], rbx
0x1400078d9  mov     [rsp+arg_18], rbp
0x1400078de  push    rsi
0x1400078df  push    rdi
0x1400078e0  push    r15
0x1400078e2  sub     rsp, 30h
0x1400078e6  mov     rax, cs:__security_cookie
0x1400078ed  xor     rax, rsp
0x1400078f0  mov     [rsp+48h+var_20], rax
0x1400078f5  mov     qword ptr [rdx], 0
0x1400078fc  mov     rdi, rdx
0x1400078ff  mov     eax, [rcx]
0x140007901  mov     rsi, rcx
0x140007904  mov     [rdx], eax
0x140007906  and     eax, 6
0x140007909  cmp     al, 6
0x14000790b  jz      loc_140007A41
0x140007911  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007916  mov     ebp, eax
0x140007918  mov     [rsp+48h+var_28], 0
0x140007920  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140007927  mov     r15d, 40h ; '@'
0x14000792d  test    rax, rax
0x140007930  jnz     short loc_14000793E
0x140007932  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140007939  test    rax, rax
0x14000793c  jz      short loc_14000798A
0x14000793e  lea     r8, [rsp+48h+var_28]
0x140007943  xor     edx, edx
0x140007945  mov     ecx, 3656659h
0x14000794a  call    _guard_dispatch_icall
0x14000794f  mov     r8d, eax
0x140007952  mov     edx, eax
0x140007954  and     r8d, 0FFFFFF3Fh
0x14000795b  and     eax, r15d
0x14000795e  and     edx, 80h
0x140007964  mov     ecx, r8d
0x140007967  and     ecx, 3
0x14000796a  shl     ecx, 2
0x14000796d  or      ecx, eax
0x14000796f  shl     ecx, 2
0x140007972  or      ecx, edx
0x140007974  shl     ecx, 3
0x140007977  test    r8d, r8d
0x14000797a  jz      short loc_14000798C
0x14000797c  xor     eax, eax
0x14000797e  cmp     r8d, 2
0x140007982  cmovz   eax, r15d
0x140007986  or      eax, ecx
0x140007988  jmp     short loc_14000798E
0x14000798a  xor     ecx, ecx
0x14000798c  mov     eax, ecx
0x14000798e  mov     ebx, eax
0x140007990  shr     ebx, 6
0x140007993  and     ebx, 1
0x140007996  or      ebx, eax
0x140007998  test    ebp, ebp
0x14000799a  jnz     short loc_1400079A0
0x14000799c  mov     [rsp+48h+var_28], ebp
0x1400079a0  mov     eax, [rdi]
0x1400079a2  cmp     [rsp+48h+var_28], 0
0x1400079a7  mov     edx, eax
0x1400079a9  mov     [rdi], eax
0x1400079ab  mov     ecx, eax
0x1400079ad  jz      short loc_1400079E2
0x1400079af  test    dl, 2
0x1400079b2  jnz     short loc_1400079E2
0x1400079b4  mov     eax, ebx
0x1400079b6  xor     eax, ecx
0x1400079b8  and     eax, 180h
0x1400079bd  xor     eax, ecx
0x1400079bf  mov     ecx, eax
0x1400079c1  xor     ecx, ebx
0x1400079c3  and     ecx, r15d
0x1400079c6  xor     ecx, eax
0x1400079c8  mov     eax, ecx
0x1400079ca  xor     eax, ebx
0x1400079cc  and     eax, 1
0x1400079cf  xor     eax, ecx
0x1400079d1  mov     ecx, eax
0x1400079d3  xor     ecx, ebx
0x1400079d5  and     ecx, 800h
0x1400079db  xor     ecx, eax
0x1400079dd  or      ecx, 2
0x1400079e0  mov     [rdi], ecx
0x1400079e2  test    dl, 4
0x1400079e5  jnz     short loc_1400079F7
0x1400079e7  mov     eax, ebx
0x1400079e9  xor     eax, ecx
0x1400079eb  and     eax, 400h
0x1400079f0  xor     ecx, eax
0x1400079f2  or      ecx, 4
0x1400079f5  mov     [rdi], ecx
0x1400079f7  mov     eax, edx
0x1400079f9  lock cmpxchg [rsi], ecx
0x1400079fd  jnz     short loc_1400079A2
0x1400079ff  test    dl, 4
0x140007a02  jnz     short loc_140007A11
0x140007a04  mov     r8d, ebp
0x140007a07  xor     edx, edx
0x140007a09  mov     rcx, rsi
0x140007a0c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007a11  test    byte ptr [rdi], 2
0x140007a14  jnz     short loc_140007A41
0x140007a16  mov     eax, ebx
0x140007a18  xor     eax, [rdi]
0x140007a1a  and     eax, 180h
0x140007a1f  xor     eax, [rdi]
0x140007a21  mov     ecx, eax
0x140007a23  xor     ecx, ebx
0x140007a25  and     ecx, r15d
0x140007a28  xor     ecx, eax
0x140007a2a  mov     edx, ecx
0x140007a2c  xor     edx, ebx
0x140007a2e  and     edx, 1
0x140007a31  xor     edx, ecx
0x140007a33  mov     ecx, edx
0x140007a35  xor     ecx, ebx
0x140007a37  and     ecx, 800h
0x140007a3d  xor     ecx, edx
0x140007a3f  mov     [rdi], ecx
0x140007a41  mov     rax, rdi
0x140007a44  mov     rcx, [rsp+48h+var_20]
0x140007a49  xor     rcx, rsp; StackCookie
0x140007a4c  call    __security_check_cookie
0x140007a51  mov     rbx, [rsp+48h+arg_10]
0x140007a56  mov     rbp, [rsp+48h+arg_18]
0x140007a5b  add     rsp, 30h
0x140007a5f  pop     r15
0x140007a61  pop     rdi
0x140007a62  pop     rsi
0x140007a63  retn
```

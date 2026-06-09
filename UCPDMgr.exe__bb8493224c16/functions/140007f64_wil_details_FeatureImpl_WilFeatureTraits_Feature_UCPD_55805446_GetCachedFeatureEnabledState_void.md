# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_55805446>::GetCachedFeatureEnabledState(void)

- ea: `0x140007f64`
- end: `0x1400080f4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_55805446@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400057e4`
- `0x1400080fc`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140007f64`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_55805446>::GetCachedFeatureEnabledState(
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
    v7 = v6(55805446, 0, &v19);
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
0x140007f64  mov     [rsp+arg_10], rbx
0x140007f69  mov     [rsp+arg_18], rbp
0x140007f6e  push    rsi
0x140007f6f  push    rdi
0x140007f70  push    r15
0x140007f72  sub     rsp, 30h
0x140007f76  mov     rax, cs:__security_cookie
0x140007f7d  xor     rax, rsp
0x140007f80  mov     [rsp+48h+var_20], rax
0x140007f85  mov     qword ptr [rdx], 0
0x140007f8c  mov     rdi, rdx
0x140007f8f  mov     eax, [rcx]
0x140007f91  mov     rsi, rcx
0x140007f94  mov     [rdx], eax
0x140007f96  and     eax, 6
0x140007f99  cmp     al, 6
0x140007f9b  jz      loc_1400080D1
0x140007fa1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007fa6  mov     ebp, eax
0x140007fa8  mov     [rsp+48h+var_28], 0
0x140007fb0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140007fb7  mov     r15d, 40h ; '@'
0x140007fbd  test    rax, rax
0x140007fc0  jnz     short loc_140007FCE
0x140007fc2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140007fc9  test    rax, rax
0x140007fcc  jz      short loc_14000801A
0x140007fce  lea     r8, [rsp+48h+var_28]
0x140007fd3  xor     edx, edx
0x140007fd5  mov     ecx, 3538606h
0x140007fda  call    _guard_dispatch_icall
0x140007fdf  mov     r8d, eax
0x140007fe2  mov     edx, eax
0x140007fe4  and     r8d, 0FFFFFF3Fh
0x140007feb  and     eax, r15d
0x140007fee  and     edx, 80h
0x140007ff4  mov     ecx, r8d
0x140007ff7  and     ecx, 3
0x140007ffa  shl     ecx, 2
0x140007ffd  or      ecx, eax
0x140007fff  shl     ecx, 2
0x140008002  or      ecx, edx
0x140008004  shl     ecx, 3
0x140008007  test    r8d, r8d
0x14000800a  jz      short loc_14000801C
0x14000800c  xor     eax, eax
0x14000800e  cmp     r8d, 2
0x140008012  cmovz   eax, r15d
0x140008016  or      eax, ecx
0x140008018  jmp     short loc_14000801E
0x14000801a  xor     ecx, ecx
0x14000801c  mov     eax, ecx
0x14000801e  mov     ebx, eax
0x140008020  shr     ebx, 6
0x140008023  and     ebx, 1
0x140008026  or      ebx, eax
0x140008028  test    ebp, ebp
0x14000802a  jnz     short loc_140008030
0x14000802c  mov     [rsp+48h+var_28], ebp
0x140008030  mov     eax, [rdi]
0x140008032  cmp     [rsp+48h+var_28], 0
0x140008037  mov     edx, eax
0x140008039  mov     [rdi], eax
0x14000803b  mov     ecx, eax
0x14000803d  jz      short loc_140008072
0x14000803f  test    dl, 2
0x140008042  jnz     short loc_140008072
0x140008044  mov     eax, ebx
0x140008046  xor     eax, ecx
0x140008048  and     eax, 180h
0x14000804d  xor     eax, ecx
0x14000804f  mov     ecx, eax
0x140008051  xor     ecx, ebx
0x140008053  and     ecx, r15d
0x140008056  xor     ecx, eax
0x140008058  mov     eax, ecx
0x14000805a  xor     eax, ebx
0x14000805c  and     eax, 1
0x14000805f  xor     eax, ecx
0x140008061  mov     ecx, eax
0x140008063  xor     ecx, ebx
0x140008065  and     ecx, 800h
0x14000806b  xor     ecx, eax
0x14000806d  or      ecx, 2
0x140008070  mov     [rdi], ecx
0x140008072  test    dl, 4
0x140008075  jnz     short loc_140008087
0x140008077  mov     eax, ebx
0x140008079  xor     eax, ecx
0x14000807b  and     eax, 400h
0x140008080  xor     ecx, eax
0x140008082  or      ecx, 4
0x140008085  mov     [rdi], ecx
0x140008087  mov     eax, edx
0x140008089  lock cmpxchg [rsi], ecx
0x14000808d  jnz     short loc_140008032
0x14000808f  test    dl, 4
0x140008092  jnz     short loc_1400080A1
0x140008094  mov     r8d, ebp
0x140008097  xor     edx, edx
0x140008099  mov     rcx, rsi
0x14000809c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400080a1  test    byte ptr [rdi], 2
0x1400080a4  jnz     short loc_1400080D1
0x1400080a6  mov     eax, ebx
0x1400080a8  xor     eax, [rdi]
0x1400080aa  and     eax, 180h
0x1400080af  xor     eax, [rdi]
0x1400080b1  mov     ecx, eax
0x1400080b3  xor     ecx, ebx
0x1400080b5  and     ecx, r15d
0x1400080b8  xor     ecx, eax
0x1400080ba  mov     edx, ecx
0x1400080bc  xor     edx, ebx
0x1400080be  and     edx, 1
0x1400080c1  xor     edx, ecx
0x1400080c3  mov     ecx, edx
0x1400080c5  xor     ecx, ebx
0x1400080c7  and     ecx, 800h
0x1400080cd  xor     ecx, edx
0x1400080cf  mov     [rdi], ecx
0x1400080d1  mov     rax, rdi
0x1400080d4  mov     rcx, [rsp+48h+var_20]
0x1400080d9  xor     rcx, rsp; StackCookie
0x1400080dc  call    __security_check_cookie
0x1400080e1  mov     rbx, [rsp+48h+arg_10]
0x1400080e6  mov     rbp, [rsp+48h+arg_18]
0x1400080eb  add     rsp, 30h
0x1400080ef  pop     r15
0x1400080f1  pop     rdi
0x1400080f2  pop     rsi
0x1400080f3  retn
```

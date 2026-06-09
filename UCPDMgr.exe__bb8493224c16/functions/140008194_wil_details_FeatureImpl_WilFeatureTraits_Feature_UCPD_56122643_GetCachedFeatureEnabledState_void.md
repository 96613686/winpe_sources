# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56122643>::GetCachedFeatureEnabledState(void)

- ea: `0x140008194`
- end: `0x140008324`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_56122643@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005820`
- `0x14000832c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140008194`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56122643>::GetCachedFeatureEnabledState(
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
    v7 = v6(56122643, 0, &v19);
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
0x140008194  mov     [rsp+arg_10], rbx
0x140008199  mov     [rsp+arg_18], rbp
0x14000819e  push    rsi
0x14000819f  push    rdi
0x1400081a0  push    r15
0x1400081a2  sub     rsp, 30h
0x1400081a6  mov     rax, cs:__security_cookie
0x1400081ad  xor     rax, rsp
0x1400081b0  mov     [rsp+48h+var_20], rax
0x1400081b5  mov     qword ptr [rdx], 0
0x1400081bc  mov     rdi, rdx
0x1400081bf  mov     eax, [rcx]
0x1400081c1  mov     rsi, rcx
0x1400081c4  mov     [rdx], eax
0x1400081c6  and     eax, 6
0x1400081c9  cmp     al, 6
0x1400081cb  jz      loc_140008301
0x1400081d1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400081d6  mov     ebp, eax
0x1400081d8  mov     [rsp+48h+var_28], 0
0x1400081e0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400081e7  mov     r15d, 40h ; '@'
0x1400081ed  test    rax, rax
0x1400081f0  jnz     short loc_1400081FE
0x1400081f2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400081f9  test    rax, rax
0x1400081fc  jz      short loc_14000824A
0x1400081fe  lea     r8, [rsp+48h+var_28]
0x140008203  xor     edx, edx
0x140008205  mov     ecx, 3585D13h
0x14000820a  call    _guard_dispatch_icall
0x14000820f  mov     r8d, eax
0x140008212  mov     edx, eax
0x140008214  and     r8d, 0FFFFFF3Fh
0x14000821b  and     eax, r15d
0x14000821e  and     edx, 80h
0x140008224  mov     ecx, r8d
0x140008227  and     ecx, 3
0x14000822a  shl     ecx, 2
0x14000822d  or      ecx, eax
0x14000822f  shl     ecx, 2
0x140008232  or      ecx, edx
0x140008234  shl     ecx, 3
0x140008237  test    r8d, r8d
0x14000823a  jz      short loc_14000824C
0x14000823c  xor     eax, eax
0x14000823e  cmp     r8d, 2
0x140008242  cmovz   eax, r15d
0x140008246  or      eax, ecx
0x140008248  jmp     short loc_14000824E
0x14000824a  xor     ecx, ecx
0x14000824c  mov     eax, ecx
0x14000824e  mov     ebx, eax
0x140008250  shr     ebx, 6
0x140008253  and     ebx, 1
0x140008256  or      ebx, eax
0x140008258  test    ebp, ebp
0x14000825a  jnz     short loc_140008260
0x14000825c  mov     [rsp+48h+var_28], ebp
0x140008260  mov     eax, [rdi]
0x140008262  cmp     [rsp+48h+var_28], 0
0x140008267  mov     edx, eax
0x140008269  mov     [rdi], eax
0x14000826b  mov     ecx, eax
0x14000826d  jz      short loc_1400082A2
0x14000826f  test    dl, 2
0x140008272  jnz     short loc_1400082A2
0x140008274  mov     eax, ebx
0x140008276  xor     eax, ecx
0x140008278  and     eax, 180h
0x14000827d  xor     eax, ecx
0x14000827f  mov     ecx, eax
0x140008281  xor     ecx, ebx
0x140008283  and     ecx, r15d
0x140008286  xor     ecx, eax
0x140008288  mov     eax, ecx
0x14000828a  xor     eax, ebx
0x14000828c  and     eax, 1
0x14000828f  xor     eax, ecx
0x140008291  mov     ecx, eax
0x140008293  xor     ecx, ebx
0x140008295  and     ecx, 800h
0x14000829b  xor     ecx, eax
0x14000829d  or      ecx, 2
0x1400082a0  mov     [rdi], ecx
0x1400082a2  test    dl, 4
0x1400082a5  jnz     short loc_1400082B7
0x1400082a7  mov     eax, ebx
0x1400082a9  xor     eax, ecx
0x1400082ab  and     eax, 400h
0x1400082b0  xor     ecx, eax
0x1400082b2  or      ecx, 4
0x1400082b5  mov     [rdi], ecx
0x1400082b7  mov     eax, edx
0x1400082b9  lock cmpxchg [rsi], ecx
0x1400082bd  jnz     short loc_140008262
0x1400082bf  test    dl, 4
0x1400082c2  jnz     short loc_1400082D1
0x1400082c4  mov     r8d, ebp
0x1400082c7  xor     edx, edx
0x1400082c9  mov     rcx, rsi
0x1400082cc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400082d1  test    byte ptr [rdi], 2
0x1400082d4  jnz     short loc_140008301
0x1400082d6  mov     eax, ebx
0x1400082d8  xor     eax, [rdi]
0x1400082da  and     eax, 180h
0x1400082df  xor     eax, [rdi]
0x1400082e1  mov     ecx, eax
0x1400082e3  xor     ecx, ebx
0x1400082e5  and     ecx, r15d
0x1400082e8  xor     ecx, eax
0x1400082ea  mov     edx, ecx
0x1400082ec  xor     edx, ebx
0x1400082ee  and     edx, 1
0x1400082f1  xor     edx, ecx
0x1400082f3  mov     ecx, edx
0x1400082f5  xor     ecx, ebx
0x1400082f7  and     ecx, 800h
0x1400082fd  xor     ecx, edx
0x1400082ff  mov     [rdi], ecx
0x140008301  mov     rax, rdi
0x140008304  mov     rcx, [rsp+48h+var_20]
0x140008309  xor     rcx, rsp; StackCookie
0x14000830c  call    __security_check_cookie
0x140008311  mov     rbx, [rsp+48h+arg_10]
0x140008316  mov     rbp, [rsp+48h+arg_18]
0x14000831b  add     rsp, 30h
0x14000831f  pop     r15
0x140008321  pop     rdi
0x140008322  pop     rsi
0x140008323  retn
```

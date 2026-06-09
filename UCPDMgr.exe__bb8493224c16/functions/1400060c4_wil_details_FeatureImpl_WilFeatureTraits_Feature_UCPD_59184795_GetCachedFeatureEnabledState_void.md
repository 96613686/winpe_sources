# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59184795>::GetCachedFeatureEnabledState(void)

- ea: `0x1400060c4`
- end: `0x140006254`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_59184795@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000549c`
- `0x14000625c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400060c4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59184795>::GetCachedFeatureEnabledState(
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
    v7 = v6(59184795, 0, &v19);
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
0x1400060c4  mov     [rsp+arg_10], rbx
0x1400060c9  mov     [rsp+arg_18], rbp
0x1400060ce  push    rsi
0x1400060cf  push    rdi
0x1400060d0  push    r15
0x1400060d2  sub     rsp, 30h
0x1400060d6  mov     rax, cs:__security_cookie
0x1400060dd  xor     rax, rsp
0x1400060e0  mov     [rsp+48h+var_20], rax
0x1400060e5  mov     qword ptr [rdx], 0
0x1400060ec  mov     rdi, rdx
0x1400060ef  mov     eax, [rcx]
0x1400060f1  mov     rsi, rcx
0x1400060f4  mov     [rdx], eax
0x1400060f6  and     eax, 6
0x1400060f9  cmp     al, 6
0x1400060fb  jz      loc_140006231
0x140006101  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006106  mov     ebp, eax
0x140006108  mov     [rsp+48h+var_28], 0
0x140006110  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140006117  mov     r15d, 40h ; '@'
0x14000611d  test    rax, rax
0x140006120  jnz     short loc_14000612E
0x140006122  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140006129  test    rax, rax
0x14000612c  jz      short loc_14000617A
0x14000612e  lea     r8, [rsp+48h+var_28]
0x140006133  xor     edx, edx
0x140006135  mov     ecx, 387169Bh
0x14000613a  call    _guard_dispatch_icall
0x14000613f  mov     r8d, eax
0x140006142  mov     edx, eax
0x140006144  and     r8d, 0FFFFFF3Fh
0x14000614b  and     eax, r15d
0x14000614e  and     edx, 80h
0x140006154  mov     ecx, r8d
0x140006157  and     ecx, 3
0x14000615a  shl     ecx, 2
0x14000615d  or      ecx, eax
0x14000615f  shl     ecx, 2
0x140006162  or      ecx, edx
0x140006164  shl     ecx, 3
0x140006167  test    r8d, r8d
0x14000616a  jz      short loc_14000617C
0x14000616c  xor     eax, eax
0x14000616e  cmp     r8d, 2
0x140006172  cmovz   eax, r15d
0x140006176  or      eax, ecx
0x140006178  jmp     short loc_14000617E
0x14000617a  xor     ecx, ecx
0x14000617c  mov     eax, ecx
0x14000617e  mov     ebx, eax
0x140006180  shr     ebx, 6
0x140006183  and     ebx, 1
0x140006186  or      ebx, eax
0x140006188  test    ebp, ebp
0x14000618a  jnz     short loc_140006190
0x14000618c  mov     [rsp+48h+var_28], ebp
0x140006190  mov     eax, [rdi]
0x140006192  cmp     [rsp+48h+var_28], 0
0x140006197  mov     edx, eax
0x140006199  mov     [rdi], eax
0x14000619b  mov     ecx, eax
0x14000619d  jz      short loc_1400061D2
0x14000619f  test    dl, 2
0x1400061a2  jnz     short loc_1400061D2
0x1400061a4  mov     eax, ebx
0x1400061a6  xor     eax, ecx
0x1400061a8  and     eax, 180h
0x1400061ad  xor     eax, ecx
0x1400061af  mov     ecx, eax
0x1400061b1  xor     ecx, ebx
0x1400061b3  and     ecx, r15d
0x1400061b6  xor     ecx, eax
0x1400061b8  mov     eax, ecx
0x1400061ba  xor     eax, ebx
0x1400061bc  and     eax, 1
0x1400061bf  xor     eax, ecx
0x1400061c1  mov     ecx, eax
0x1400061c3  xor     ecx, ebx
0x1400061c5  and     ecx, 800h
0x1400061cb  xor     ecx, eax
0x1400061cd  or      ecx, 2
0x1400061d0  mov     [rdi], ecx
0x1400061d2  test    dl, 4
0x1400061d5  jnz     short loc_1400061E7
0x1400061d7  mov     eax, ebx
0x1400061d9  xor     eax, ecx
0x1400061db  and     eax, 400h
0x1400061e0  xor     ecx, eax
0x1400061e2  or      ecx, 4
0x1400061e5  mov     [rdi], ecx
0x1400061e7  mov     eax, edx
0x1400061e9  lock cmpxchg [rsi], ecx
0x1400061ed  jnz     short loc_140006192
0x1400061ef  test    dl, 4
0x1400061f2  jnz     short loc_140006201
0x1400061f4  mov     r8d, ebp
0x1400061f7  xor     edx, edx
0x1400061f9  mov     rcx, rsi
0x1400061fc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006201  test    byte ptr [rdi], 2
0x140006204  jnz     short loc_140006231
0x140006206  mov     eax, ebx
0x140006208  xor     eax, [rdi]
0x14000620a  and     eax, 180h
0x14000620f  xor     eax, [rdi]
0x140006211  mov     ecx, eax
0x140006213  xor     ecx, ebx
0x140006215  and     ecx, r15d
0x140006218  xor     ecx, eax
0x14000621a  mov     edx, ecx
0x14000621c  xor     edx, ebx
0x14000621e  and     edx, 1
0x140006221  xor     edx, ecx
0x140006223  mov     ecx, edx
0x140006225  xor     ecx, ebx
0x140006227  and     ecx, 800h
0x14000622d  xor     ecx, edx
0x14000622f  mov     [rdi], ecx
0x140006231  mov     rax, rdi
0x140006234  mov     rcx, [rsp+48h+var_20]
0x140006239  xor     rcx, rsp; StackCookie
0x14000623c  call    __security_check_cookie
0x140006241  mov     rbx, [rsp+48h+arg_10]
0x140006246  mov     rbp, [rsp+48h+arg_18]
0x14000624b  add     rsp, 30h
0x14000624f  pop     r15
0x140006251  pop     rdi
0x140006252  pop     rsi
0x140006253  retn
```

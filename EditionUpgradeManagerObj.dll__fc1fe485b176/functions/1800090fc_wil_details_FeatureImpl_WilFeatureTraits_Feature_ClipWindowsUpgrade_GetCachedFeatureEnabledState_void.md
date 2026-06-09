# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetCachedFeatureEnabledState(void)

- ea: `0x1800090fc`
- end: `0x1800092b2`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ClipWindowsUpgrade@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `438`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009a28`

## callees

- `0x180004728`
- `0x180007a78`
- `0x1800090fc`
- `0x180023010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ClipWindowsUpgrade__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ClipWindowsUpgrade__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(52298135, 0, &v19);
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
    {
LABEL_14:
      v10 = 1;
      goto LABEL_15;
    }
    v9 = 0;
  }
  if ( (v8 & 0x40) != 0 && v9 )
    goto LABEL_14;
  v10 = 0;
LABEL_15:
  v11 = v10 | v8;
  if ( !v4 )
    LODWORD(v19) = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ClipWindowsUpgrade__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ClipWindowsUpgrade__descriptor, 0, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x1800090fc  mov     [rsp+arg_8], rbx
0x180009101  mov     [rsp+arg_10], rbp
0x180009106  mov     [rsp+arg_0], rcx
0x18000910b  push    rsi
0x18000910c  push    rdi
0x18000910d  push    r15
0x18000910f  sub     rsp, 20h
0x180009113  mov     rsi, cs:Feature_ClipWindowsUpgrade__descriptor
0x18000911a  mov     rdi, rdx
0x18000911d  mov     qword ptr [rdx], 0
0x180009124  mov     eax, [rsi]
0x180009126  mov     [rdx], eax
0x180009128  and     eax, 6
0x18000912b  cmp     al, 6
0x18000912d  jz      loc_18000929C
0x180009133  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009138  mov     ebp, eax
0x18000913a  mov     dword ptr [rsp+38h+arg_0], 0
0x180009142  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009149  xor     edx, edx
0x18000914b  test    rax, rax
0x18000914e  jnz     short loc_18000915C
0x180009150  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009157  test    rax, rax
0x18000915a  jz      short loc_18000916D
0x18000915c  lea     r8, [rsp+38h+arg_0]
0x180009161  mov     ecx, 31E0197h
0x180009166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916b  mov     edx, eax
0x18000916d  mov     r8d, edx
0x180009170  mov     eax, edx
0x180009172  and     r8d, 0FFFFFF3Fh
0x180009179  and     edx, 80h
0x18000917f  mov     ecx, r8d
0x180009182  mov     r15d, 40h ; '@'
0x180009188  and     ecx, 3
0x18000918b  and     eax, r15d
0x18000918e  shl     ecx, 2
0x180009191  or      ecx, eax
0x180009193  xor     eax, eax
0x180009195  shl     ecx, 2
0x180009198  or      ecx, edx
0x18000919a  lea     ebx, ds:0[rcx*8]
0x1800091a1  test    r8d, r8d
0x1800091a4  jz      short loc_1800091AE
0x1800091a6  cmp     r8d, 2
0x1800091aa  cmovz   eax, r15d
0x1800091ae  or      ebx, eax
0x1800091b0  mov     edx, 0C00h
0x1800091b5  mov     ecx, ebx
0x1800091b7  mov     eax, ebx
0x1800091b9  and     ecx, r15d
0x1800091bc  and     eax, edx
0x1800091be  cmp     eax, edx
0x1800091c0  jnz     short loc_1800091C6
0x1800091c2  mov     al, 1
0x1800091c4  jmp     short loc_1800091CC
0x1800091c6  test    ecx, ecx
0x1800091c8  jnz     short loc_1800091D8
0x1800091ca  xor     al, al
0x1800091cc  test    ecx, ecx
0x1800091ce  jz      short loc_1800091D4
0x1800091d0  test    al, al
0x1800091d2  jnz     short loc_1800091D8
0x1800091d4  xor     eax, eax
0x1800091d6  jmp     short loc_1800091DD
0x1800091d8  mov     eax, 1
0x1800091dd  or      ebx, eax
0x1800091df  test    ebp, ebp
0x1800091e1  jnz     short loc_1800091E7
0x1800091e3  mov     dword ptr [rsp+38h+arg_0], ebp
0x1800091e7  mov     eax, [rdi]
0x1800091e9  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800091ee  mov     edx, eax
0x1800091f0  mov     [rdi], eax
0x1800091f2  jz      short loc_18000922F
0x1800091f4  test    dl, 2
0x1800091f7  jnz     short loc_18000922F
0x1800091f9  mov     eax, ebx
0x1800091fb  xor     eax, edx
0x1800091fd  and     eax, 180h
0x180009202  xor     eax, edx
0x180009204  mov     ecx, eax
0x180009206  xor     ecx, ebx
0x180009208  and     ecx, r15d
0x18000920b  xor     ecx, eax
0x18000920d  mov     eax, ecx
0x18000920f  xor     eax, ebx
0x180009211  and     eax, 1
0x180009214  xor     eax, ecx
0x180009216  mov     r8d, eax
0x180009219  xor     r8d, ebx
0x18000921c  and     r8d, 800h
0x180009223  xor     r8d, eax
0x180009226  or      r8d, 2
0x18000922a  mov     [rdi], r8d
0x18000922d  jmp     short loc_180009232
0x18000922f  mov     r8d, edx
0x180009232  mov     r9d, edx
0x180009235  and     r9d, 4
0x180009239  jnz     short loc_180009250
0x18000923b  mov     ecx, ebx
0x18000923d  xor     ecx, r8d
0x180009240  and     ecx, 400h
0x180009246  xor     ecx, r8d
0x180009249  or      ecx, 4
0x18000924c  mov     [rdi], ecx
0x18000924e  jmp     short loc_180009253
0x180009250  mov     ecx, r8d
0x180009253  mov     eax, edx
0x180009255  lock cmpxchg [rsi], ecx
0x180009259  jnz     short loc_1800091E9
0x18000925b  test    r9d, r9d
0x18000925e  jnz     short loc_18000926D
0x180009260  mov     r8d, ebp
0x180009263  xor     edx, edx
0x180009265  mov     rcx, rsi
0x180009268  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000926d  test    byte ptr [rdi], 2
0x180009270  jnz     short loc_18000929C
0x180009272  mov     eax, [rdi]
0x180009274  xor     eax, ebx
0x180009276  and     eax, 180h
0x18000927b  xor     eax, [rdi]
0x18000927d  mov     ecx, eax
0x18000927f  xor     ecx, ebx
0x180009281  and     ecx, r15d
0x180009284  xor     ecx, eax
0x180009286  mov     edx, ecx
0x180009288  xor     edx, ebx
0x18000928a  and     edx, 1
0x18000928d  xor     edx, ecx
0x18000928f  mov     eax, edx
0x180009291  xor     eax, ebx
0x180009293  and     eax, 800h
0x180009298  xor     eax, edx
0x18000929a  mov     [rdi], eax
0x18000929c  mov     rbx, [rsp+38h+arg_8]
0x1800092a1  mov     rax, rdi
0x1800092a4  mov     rbp, [rsp+38h+arg_10]
0x1800092a9  add     rsp, 20h
0x1800092ad  pop     r15
0x1800092af  pop     rdi
0x1800092b0  pop     rsi
0x1800092b1  retn
```

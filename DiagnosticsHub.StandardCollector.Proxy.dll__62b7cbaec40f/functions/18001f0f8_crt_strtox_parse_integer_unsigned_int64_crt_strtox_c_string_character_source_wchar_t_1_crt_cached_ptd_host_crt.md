# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<wchar_t>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x18001f0f8`
- end: `0x18001f879`
- name: `??$parse_integer@_KV?$c_string_character_source@_W@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1921`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001fab4`
- `0x1800205f8`
- `0x1800206ac`
- `0x180020990`
- `0x180020a44`

## callees

- `0x180007b48`
- `0x180007c00`
- `0x180007ee8`
- `0x18001512c`
- `0x18001e344`
- `0x18001f0f8`
- `0x180021f70`

## pseudocode

```c
unsigned __int64 __fastcall __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<wchar_t>,1>(
        __crt_cached_ptd_host *a1,
        wint_t **a2,
        signed int a3,
        unsigned __int8 a4)
{
  wint_t *v4; // r12
  unsigned int v5; // esi
  signed int v6; // r15d
  wint_t **v8; // rcx
  wint_t v9; // bx
  unsigned __int64 v10; // rbp
  unsigned int v11; // eax
  unsigned int v12; // esi
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  unsigned int v16; // eax
  wint_t *v17; // rcx
  wint_t v18; // dx
  wint_t *v19; // r8
  int v20; // eax
  int v21; // eax
  unsigned __int64 v22; // r10
  unsigned int v23; // ecx
  int v24; // eax
  int v25; // ecx
  wint_t *v26; // r8
  unsigned __int64 v27; // rdx
  BOOL v28; // ecx
  bool v29; // cf
  bool v30; // zf
  wint_t **v31; // rax
  wint_t **v33; // rcx
  wint_t **v34; // rdx
  wint_t *v35; // [rsp+90h] [rbp-48h]

  v4 = *a2;
  v5 = a4;
  v6 = a3;
  v35 = *a2;
  if ( !*a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a1);
LABEL_6:
    v8 = (wint_t **)a2[1];
    if ( v8 )
      *v8 = *a2;
    return 0;
  }
  v9 = *v4;
  *a2 = v4 + 1;
  v10 = 0;
  if ( !*((_BYTE *)a1 + 40) )
    __crt_cached_ptd_host::update_locale_slow(a1);
  while ( iswctype(v9, 8u) )
    v9 = *(*a2)++;
  v11 = v5;
  v12 = v5 | 2;
  if ( v9 != 45 )
    v12 = v11;
  if ( ((v9 - 43) & 0xFFFD) == 0 )
    v9 = *(*a2)++;
  v13 = 48;
  if ( (v6 & 0xFFFFFFEF) != 0 )
    goto LABEL_79;
  if ( v9 >= 0x30u )
  {
    if ( v9 < 0x3Au )
    {
LABEL_19:
      v14 = v9 - v13;
      goto LABEL_60;
    }
    if ( v9 >= 0xFF10u )
    {
      if ( v9 < 0xFF1Au )
      {
        v14 = v9 - 65296;
LABEL_60:
        if ( v14 != -1 )
          goto LABEL_66;
      }
    }
    else if ( v9 >= 0x660u )
    {
      if ( v9 < 0x66Au )
      {
        v14 = v9 - 1632;
        goto LABEL_60;
      }
      if ( v9 >= 0x6F0u )
      {
        if ( v9 < 0x6FAu )
        {
          v14 = v9 - 1776;
          goto LABEL_60;
        }
        if ( v9 >= 0x966u )
        {
          if ( v9 < 0x970u )
          {
            v14 = v9 - 2406;
            goto LABEL_60;
          }
          if ( v9 >= 0x9E6u )
          {
            if ( v9 < 0x9F0u )
            {
              v14 = v9 - 2534;
              goto LABEL_60;
            }
            if ( v9 >= 0xA66u )
            {
              if ( v9 < 0xA70u )
              {
                v14 = v9 - 2662;
                goto LABEL_60;
              }
              v13 = 2790;
              if ( v9 >= 0xAE6u )
              {
                if ( v9 < 0xAF0u )
                  goto LABEL_19;
                v13 = 2918;
                if ( v9 >= 0xB66u )
                {
                  if ( v9 < 0xB70u )
                    goto LABEL_19;
                  v13 = 3174;
                  if ( v9 >= 0xC66u )
                  {
                    if ( v9 < 0xC70u )
                      goto LABEL_19;
                    v13 = 3302;
                    if ( v9 >= 0xCE6u )
                    {
                      if ( v9 < 0xCF0u )
                        goto LABEL_19;
                      v13 = 3430;
                      if ( v9 >= 0xD66u )
                      {
                        if ( v9 < 0xD70u )
                          goto LABEL_19;
                        v13 = 3664;
                        if ( v9 >= 0xE50u )
                        {
                          if ( v9 < 0xE5Au )
                            goto LABEL_19;
                          v13 = 3792;
                          if ( v9 >= 0xED0u )
                          {
                            if ( v9 < 0xEDAu )
                              goto LABEL_19;
                            v13 = 3872;
                            if ( v9 >= 0xF20u )
                            {
                              if ( v9 < 0xF2Au )
                                goto LABEL_19;
                              v13 = 4160;
                              if ( v9 >= 0x1040u )
                              {
                                if ( v9 < 0x104Au )
                                  goto LABEL_19;
                                v13 = 6112;
                                if ( v9 >= 0x17E0u )
                                {
                                  if ( v9 < 0x17EAu )
                                    goto LABEL_19;
                                  v13 = 6160;
                                  if ( (unsigned __int16)(v9 - 6160) <= 9u )
                                    goto LABEL_19;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v15 = v9;
  v16 = v9 - 97;
  if ( (unsigned int)v9 - 65 > 0x19 && v16 > 0x19 )
    goto LABEL_75;
  if ( v16 <= 0x19 )
    v15 = v9 - 32;
  v14 = v15 - 55;
LABEL_66:
  if ( v14 )
  {
LABEL_75:
    v21 = 10;
    goto LABEL_76;
  }
  v17 = *a2;
  v18 = **a2;
  v19 = *a2 + 1;
  *a2 = v19;
  if ( ((v18 - 88) & 0xFFDF) == 0 )
  {
    v9 = *v19;
    *a2 = v19 + 1;
    v21 = 16;
LABEL_76:
    if ( v6 )
      v21 = v6;
    v6 = v21;
    goto LABEL_79;
  }
  *a2 = v17;
  v20 = 8;
  if ( v6 )
    v20 = v6;
  v6 = v20;
  if ( v18 && *v17 != v18 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
LABEL_79:
  v22 = 0xFFFFFFFFFFFFFFFFuLL / v6;
  while ( 1 )
  {
    if ( v9 >= 0x30u )
    {
      if ( v9 < 0x3Au )
      {
        v23 = v9 - 48;
        goto LABEL_120;
      }
      if ( v9 >= 0xFF10u )
      {
        if ( v9 < 0xFF1Au )
        {
          v23 = v9 - 65296;
LABEL_120:
          if ( v23 != -1 )
            goto LABEL_129;
        }
      }
      else if ( v9 >= 0x660u )
      {
        if ( v9 < 0x66Au )
        {
          v23 = v9 - 1632;
          goto LABEL_120;
        }
        v24 = 1776;
        if ( v9 >= 0x6F0u )
        {
          if ( v9 < 0x6FAu )
            goto LABEL_89;
          v24 = 2406;
          if ( v9 >= 0x966u )
          {
            if ( v9 < 0x970u )
              goto LABEL_89;
            v24 = 2534;
            if ( v9 >= 0x9E6u )
            {
              if ( v9 < 0x9F0u )
                goto LABEL_89;
              v24 = 2662;
              if ( v9 >= 0xA66u )
              {
                if ( v9 < 0xA70u )
                  goto LABEL_89;
                v24 = 2790;
                if ( v9 >= 0xAE6u )
                {
                  if ( v9 < 0xAF0u )
                    goto LABEL_89;
                  v24 = 2918;
                  if ( v9 >= 0xB66u )
                  {
                    if ( v9 < 0xB70u )
                      goto LABEL_89;
                    v24 = 3174;
                    if ( v9 >= 0xC66u )
                    {
                      if ( v9 < 0xC70u )
                        goto LABEL_89;
                      v24 = 3302;
                      if ( v9 >= 0xCE6u )
                      {
                        if ( v9 < 0xCF0u )
                          goto LABEL_89;
                        v24 = 3430;
                        if ( v9 >= 0xD66u )
                        {
                          if ( v9 < 0xD70u )
                            goto LABEL_89;
                          v24 = 3664;
                          if ( v9 >= 0xE50u )
                          {
                            if ( v9 < 0xE5Au )
                              goto LABEL_89;
                            v24 = 3792;
                            if ( v9 >= 0xED0u )
                            {
                              if ( v9 < 0xEDAu )
                                goto LABEL_89;
                              v24 = 3872;
                              if ( v9 >= 0xF20u )
                              {
                                if ( v9 < 0xF2Au )
                                  goto LABEL_89;
                                v24 = 4160;
                                if ( v9 >= 0x1040u )
                                {
                                  if ( v9 < 0x104Au )
                                    goto LABEL_89;
                                  v24 = 6112;
                                  if ( v9 >= 0x17E0u )
                                  {
                                    if ( v9 < 0x17EAu )
                                    {
LABEL_89:
                                      v23 = v9 - v24;
                                      goto LABEL_120;
                                    }
                                    if ( (unsigned __int16)(v9 - 6160) <= 9u )
                                    {
                                      v23 = v9 - 6160;
                                      goto LABEL_120;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( ((v25 = v9, v9 < 0x41u) || v9 > 0x5Au) && (v9 < 0x61u || v9 > 0x7Au) )
    {
      v23 = -1;
    }
    else
    {
      if ( (unsigned __int16)(v9 - 97) <= 0x19u )
        v25 = v9 - 32;
      v23 = v25 - 55;
    }
LABEL_129:
    v26 = *a2;
    if ( v23 >= v6 )
      break;
    v9 = *v26;
    v27 = v10 * v6 + v23;
    v28 = v27 < v10 * v6;
    v29 = v10 < v22;
    v30 = v10 == v22;
    v10 = v27;
    *a2 = v26 + 1;
    v12 |= (4 * (!v29 && !v30 || v28)) | 8;
  }
  *a2 = v26 - 1;
  if ( v9 && *(v26 - 1) != v9 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( (v12 & 8) != 0 )
  {
    if ( (unsigned __int8)__crt_strtox::is_overflow_condition<unsigned __int64>(v12, v10) )
    {
      *((_BYTE *)a1 + 48) = 1;
      *((_DWORD *)a1 + 11) = 34;
      if ( (v12 & 1) != 0 )
      {
        v33 = (wint_t **)a2[1];
        if ( (v12 & 2) != 0 )
        {
          if ( v33 )
            *v33 = *a2;
          return 0x8000000000000000uLL;
        }
        else
        {
          if ( v33 )
            *v33 = *a2;
          return 0x7FFFFFFFFFFFFFFFLL;
        }
      }
      v10 = -1;
    }
    else if ( (v12 & 2) != 0 )
    {
      v10 = -(__int64)v10;
    }
    v34 = (wint_t **)a2[1];
    if ( v34 )
      *v34 = *a2;
    return v10;
  }
  v31 = (wint_t **)a2[1];
  *a2 = v35;
  if ( v31 )
    *v31 = v35;
  return 0;
}

```

## disassembly

```asm
0x18001f0f8  mov     [rsp+arg_10], rbx
0x18001f0fd  mov     [rsp+arg_0], rcx
0x18001f102  push    rbp
0x18001f103  push    rsi
0x18001f104  push    rdi
0x18001f105  push    r12
0x18001f107  push    r13
0x18001f109  push    r14
0x18001f10b  push    r15
0x18001f10d  sub     rsp, 0A0h
0x18001f114  mov     r12, [rdx]
0x18001f117  xor     r13d, r13d
0x18001f11a  movzx   esi, r9b
0x18001f11e  mov     r15d, r8d
0x18001f121  mov     [rsp+0D8h+var_48], r12
0x18001f129  mov     rdi, rdx
0x18001f12c  test    r12, r12
0x18001f12f  jnz     short loc_18001F143
0x18001f131  call    _errno
0x18001f136  mov     dword ptr [rax], 16h
0x18001f13c  call    _invalid_parameter_noinfo
0x18001f141  jmp     short loc_18001F175
0x18001f143  test    r15d, r15d
0x18001f146  jz      short loc_18001F18D
0x18001f148  lea     eax, [r8-2]
0x18001f14c  cmp     eax, 22h ; '"'
0x18001f14f  jbe     short loc_18001F18D
0x18001f151  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x18001f156  xor     r9d, r9d; LineNo
0x18001f159  mov     byte ptr [rcx+30h], 1
0x18001f15d  xor     r8d, r8d; FileName
0x18001f160  mov     dword ptr [rcx+2Ch], 16h
0x18001f167  xor     edx, edx; FunctionName
0x18001f169  xor     ecx, ecx; Expression
0x18001f16b  mov     [rsp+0D8h+var_B8], r13; uintptr_t
0x18001f170  call    _invalid_parameter_internal
0x18001f175  mov     rcx, [rdi+8]; this
0x18001f179  test    rcx, rcx
0x18001f17c  jz      loc_18001F7E0
0x18001f182  mov     rax, [rdi]
0x18001f185  mov     [rcx], rax
0x18001f188  jmp     loc_18001F7E0
0x18001f18d  movzx   ebx, word ptr [r12]
0x18001f192  lea     rax, [r12+2]
0x18001f197  mov     [rdx], rax
0x18001f19a  mov     rbp, r13
0x18001f19d  cmp     [rcx+28h], r13b
0x18001f1a1  jnz     short loc_18001F1B7
0x18001f1a3  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001f1a8  jmp     short loc_18001F1B7
0x18001f1aa  mov     rax, [rdi]
0x18001f1ad  movzx   ebx, word ptr [rax]
0x18001f1b0  add     rax, 2
0x18001f1b4  mov     [rdi], rax
0x18001f1b7  mov     edx, 8; Type
0x18001f1bc  movzx   ecx, bx; C
0x18001f1bf  call    iswctype
0x18001f1c4  test    eax, eax
0x18001f1c6  jnz     short loc_18001F1AA
0x18001f1c8  mov     eax, esi
0x18001f1ca  mov     ecx, 0FFFDh
0x18001f1cf  or      esi, 2
0x18001f1d2  cmp     bx, 2Dh ; '-'
0x18001f1d6  cmovnz  esi, eax
0x18001f1d9  lea     eax, [rbx-2Bh]
0x18001f1dc  test    cx, ax
0x18001f1df  jnz     short loc_18001F1EE
0x18001f1e1  mov     rax, [rdi]
0x18001f1e4  movzx   ebx, word ptr [rax]
0x18001f1e7  add     rax, 2
0x18001f1eb  mov     [rdi], rax
0x18001f1ee  mov     [rsp+0D8h+arg_8], 0A70h
0x18001f1f9  mov     eax, 0A66h
0x18001f1fe  mov     [rsp+0D8h+var_A8], 0AE6h
0x18001f206  mov     ecx, 30h ; '0'
0x18001f20b  mov     [rsp+0D8h+var_A4], 0AF0h
0x18001f213  mov     edx, 0FF10h
0x18001f218  mov     [rsp+0D8h+var_A0], 0B66h
0x18001f220  mov     r8d, 660h
0x18001f226  mov     [rsp+0D8h+var_9C], 0B70h
0x18001f22e  lea     r11d, [rax-80h]
0x18001f232  mov     [rsp+0D8h+var_98], 0C66h
0x18001f23a  mov     r9d, 6F0h
0x18001f240  mov     [rsp+0D8h+var_94], 0C70h
0x18001f248  mov     r10d, 966h
0x18001f24e  mov     [rsp+0D8h+var_90], 0CE6h
0x18001f256  mov     [rsp+0D8h+var_8C], 0CF0h
0x18001f25e  mov     [rsp+0D8h+var_88], 0D66h
0x18001f266  mov     [rsp+0D8h+var_84], 0D70h
0x18001f26e  mov     [rsp+0D8h+var_80], 0E50h
0x18001f276  mov     [rsp+0D8h+var_7C], 0E5Ah
0x18001f27e  mov     [rsp+0D8h+var_78], 0ED0h
0x18001f286  mov     [rsp+0D8h+var_74], 0EDAh
0x18001f28e  mov     [rsp+0D8h+var_70], 0F20h
0x18001f296  mov     [rsp+0D8h+var_6C], 0F2Ah
0x18001f29e  mov     [rsp+0D8h+var_68], 1040h
0x18001f2a6  mov     [rsp+0D8h+var_64], 104Ah
0x18001f2ae  mov     [rsp+0D8h+var_60], 17E0h
0x18001f2b6  mov     [rsp+0D8h+var_5C], 17EAh
0x18001f2be  mov     [rsp+0D8h+var_58], 1810h
0x18001f2c9  mov     [rsp+0D8h+var_54], 0FF1Ah
0x18001f2d4  mov     [rsp+0D8h+var_50], 19h
0x18001f2df  test    r15d, 0FFFFFFEFh
0x18001f2e6  jnz     loc_18001F553
0x18001f2ec  cmp     bx, cx
0x18001f2ef  jb      loc_18001F4B6
0x18001f2f5  cmp     bx, 3Ah ; ':'
0x18001f2f9  jnb     short loc_18001F305
0x18001f2fb  movzx   eax, bx
0x18001f2fe  sub     eax, ecx
0x18001f300  jmp     loc_18001F4B1
0x18001f305  cmp     bx, dx
0x18001f308  jnb     loc_18001F4A2
0x18001f30e  cmp     bx, r8w
0x18001f312  jb      loc_18001F4B6
0x18001f318  mov     ecx, 66Ah
0x18001f31d  cmp     bx, cx
0x18001f320  jnb     short loc_18001F32D
0x18001f322  movzx   eax, bx
0x18001f325  sub     eax, r8d
0x18001f328  jmp     loc_18001F4B1
0x18001f32d  cmp     bx, r9w
0x18001f331  jb      loc_18001F4B6
0x18001f337  mov     ecx, 6FAh
0x18001f33c  cmp     bx, cx
0x18001f33f  jnb     short loc_18001F34C
0x18001f341  movzx   eax, bx
0x18001f344  sub     eax, r9d
0x18001f347  jmp     loc_18001F4B1
0x18001f34c  cmp     bx, r10w
0x18001f350  jb      loc_18001F4B6
0x18001f356  mov     ecx, 970h
0x18001f35b  cmp     bx, cx
0x18001f35e  jnb     short loc_18001F36B
0x18001f360  movzx   eax, bx
0x18001f363  sub     eax, r10d
0x18001f366  jmp     loc_18001F4B1
0x18001f36b  cmp     bx, r11w
0x18001f36f  jb      loc_18001F4B6
0x18001f375  mov     ecx, 9F0h
0x18001f37a  cmp     bx, cx
0x18001f37d  jnb     short loc_18001F38A
0x18001f37f  movzx   eax, bx
0x18001f382  sub     eax, r11d
0x18001f385  jmp     loc_18001F4B1
0x18001f38a  cmp     bx, ax
0x18001f38d  jb      loc_18001F4B6
0x18001f393  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x18001f39b  jnb     short loc_18001F3AA
0x18001f39d  movzx   eax, bx
0x18001f3a0  sub     eax, 0A66h
0x18001f3a5  jmp     loc_18001F4B1
0x18001f3aa  mov     ecx, [rsp+0D8h+var_A8]
0x18001f3ae  cmp     bx, cx
0x18001f3b1  jb      loc_18001F4B6
0x18001f3b7  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x18001f3bc  jb      loc_18001F2FB
0x18001f3c2  mov     ecx, [rsp+0D8h+var_A0]
0x18001f3c6  cmp     bx, cx
0x18001f3c9  jb      loc_18001F4B6
0x18001f3cf  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x18001f3d4  jb      loc_18001F2FB
0x18001f3da  mov     ecx, [rsp+0D8h+var_98]
0x18001f3de  cmp     bx, cx
0x18001f3e1  jb      loc_18001F4B6
0x18001f3e7  cmp     bx, word ptr [rsp+0D8h+var_94]
0x18001f3ec  jb      loc_18001F2FB
0x18001f3f2  mov     ecx, [rsp+0D8h+var_90]
0x18001f3f6  cmp     bx, cx
0x18001f3f9  jb      loc_18001F4B6
0x18001f3ff  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x18001f404  jb      loc_18001F2FB
0x18001f40a  mov     ecx, [rsp+0D8h+var_88]
0x18001f40e  cmp     bx, cx
0x18001f411  jb      loc_18001F4B6
0x18001f417  cmp     bx, word ptr [rsp+0D8h+var_84]
0x18001f41c  jb      loc_18001F2FB
0x18001f422  mov     ecx, [rsp+0D8h+var_80]
0x18001f426  cmp     bx, cx
0x18001f429  jb      loc_18001F4B6
0x18001f42f  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x18001f434  jb      loc_18001F2FB
0x18001f43a  mov     ecx, [rsp+0D8h+var_78]
0x18001f43e  cmp     bx, cx
0x18001f441  jb      short loc_18001F4B6
0x18001f443  cmp     bx, word ptr [rsp+0D8h+var_74]
0x18001f448  jb      loc_18001F2FB
0x18001f44e  mov     ecx, [rsp+0D8h+var_70]
0x18001f452  cmp     bx, cx
0x18001f455  jb      short loc_18001F4B6
0x18001f457  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x18001f45c  jb      loc_18001F2FB
0x18001f462  mov     ecx, [rsp+0D8h+var_68]
0x18001f466  cmp     bx, cx
0x18001f469  jb      short loc_18001F4B6
0x18001f46b  cmp     bx, word ptr [rsp+0D8h+var_64]
0x18001f470  jb      loc_18001F2FB
0x18001f476  mov     ecx, [rsp+0D8h+var_60]
0x18001f47a  cmp     bx, cx
0x18001f47d  jb      short loc_18001F4B6
0x18001f47f  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x18001f484  jb      loc_18001F2FB
0x18001f48a  mov     ecx, [rsp+0D8h+var_58]
0x18001f491  movzx   eax, bx
0x18001f494  sub     ax, cx
0x18001f497  cmp     ax, 9
0x18001f49b  ja      short loc_18001F4B6
0x18001f49d  jmp     loc_18001F2FB
0x18001f4a2  cmp     bx, word ptr [rsp+0D8h+var_54]
0x18001f4aa  jnb     short loc_18001F4B6
0x18001f4ac  movzx   eax, bx
0x18001f4af  sub     eax, edx
0x18001f4b1  cmp     eax, 0FFFFFFFFh
0x18001f4b4  jnz     short loc_18001F4D8
0x18001f4b6  mov     edx, [rsp+0D8h+var_50]
0x18001f4bd  movzx   ecx, bx
0x18001f4c0  lea     eax, [rcx-41h]
0x18001f4c3  cmp     eax, edx
0x18001f4c5  lea     eax, [rcx-61h]
0x18001f4c8  jbe     short loc_18001F4CE
0x18001f4ca  cmp     eax, edx
0x18001f4cc  ja      short loc_18001F544
0x18001f4ce  cmp     eax, edx
0x18001f4d0  ja      short loc_18001F4D5
0x18001f4d2  add     ecx, 0FFFFFFE0h
0x18001f4d5  lea     eax, [rcx-37h]
0x18001f4d8  test    eax, eax
0x18001f4da  jnz     short loc_18001F544
0x18001f4dc  mov     rcx, [rdi]
0x18001f4df  mov     r9d, 0FFDFh
0x18001f4e5  movzx   edx, word ptr [rcx]
0x18001f4e8  lea     r8, [rcx+2]
0x18001f4ec  mov     [rdi], r8
0x18001f4ef  lea     eax, [rdx-58h]
0x18001f4f2  test    r9w, ax
0x18001f4f6  jz      short loc_18001F52C
0x18001f4f8  test    r15d, r15d
0x18001f4fb  mov     [rdi], rcx
0x18001f4fe  mov     eax, 8
0x18001f503  cmovnz  eax, r15d
0x18001f507  mov     r15d, eax
0x18001f50a  test    dx, dx
0x18001f50d  jz      short loc_18001F524
0x18001f50f  cmp     [rcx], dx
0x18001f512  jz      short loc_18001F524
0x18001f514  call    _errno
0x18001f519  mov     dword ptr [rax], 16h
0x18001f51f  call    _invalid_parameter_noinfo
0x18001f524  mov     r8d, 660h
0x18001f52a  jmp     short loc_18001F553
0x18001f52c  movzx   ebx, word ptr [r8]
0x18001f530  lea     rax, [r8+2]
0x18001f534  mov     [rdi], rax
0x18001f537  mov     r8d, 660h
0x18001f53d  mov     eax, 10h
0x18001f542  jmp     short loc_18001F549
0x18001f544  mov     eax, 0Ah
0x18001f549  test    r15d, r15d
0x18001f54c  cmovnz  eax, r15d
0x18001f550  mov     r15d, eax
0x18001f553  movsxd  r9, r15d
0x18001f556  xor     edx, edx
0x18001f558  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f55c  mov     r11d, 61h ; 'a'
0x18001f562  div     r9
0x18001f565  lea     r12d, [r11-31h]
0x18001f569  mov     r14d, 0FF10h
0x18001f56f  mov     r10, rax
0x18001f572  cmp     bx, r12w
0x18001f576  jb      loc_18001F71D
0x18001f57c  cmp     bx, 3Ah ; ':'
0x18001f580  jnb     short loc_18001F58D
0x18001f582  movzx   ecx, bx
0x18001f585  sub     ecx, r12d
0x18001f588  jmp     loc_18001F718
0x18001f58d  cmp     bx, r14w
0x18001f591  jnb     loc_18001F708
0x18001f597  cmp     bx, r8w
0x18001f59b  jb      loc_18001F71D
0x18001f5a1  mov     eax, 66Ah
0x18001f5a6  cmp     bx, ax
0x18001f5a9  jnb     short loc_18001F5B6
0x18001f5ab  movzx   ecx, bx
0x18001f5ae  sub     ecx, r8d
0x18001f5b1  jmp     loc_18001F718
0x18001f5b6  mov     eax, 6F0h
0x18001f5bb  cmp     bx, ax
0x18001f5be  jb      loc_18001F71D
0x18001f5c4  lea     ecx, [rax+0Ah]
0x18001f5c7  cmp     bx, cx
0x18001f5ca  jnb     short loc_18001F5D6
0x18001f5cc  movzx   ecx, bx
0x18001f5cf  sub     ecx, eax
0x18001f5d1  jmp     loc_18001F718
0x18001f5d6  mov     eax, 966h
0x18001f5db  cmp     bx, ax
0x18001f5de  jb      loc_18001F71D
0x18001f5e4  lea     ecx, [rax+0Ah]
0x18001f5e7  cmp     bx, cx
0x18001f5ea  jb      short loc_18001F5CC
  ... truncated ...
```

# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x18001e680`
- end: `0x18001ee1a`
- name: `??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$00@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1946`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001f938`
- `0x180020548`
- `0x180020768`
- `0x180020824`
- `0x1800208d4`

## callees

- `0x180007b48`
- `0x180007c00`
- `0x180007ee8`
- `0x18001512c`
- `0x18001e680`
- `0x180021f70`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<wchar_t>,1>(
        __crt_cached_ptd_host *a1,
        wint_t **a2,
        unsigned int a3,
        char a4)
{
  wint_t *v4; // r12
  unsigned int v6; // r15d
  wint_t **v8; // rcx
  wint_t v9; // bx
  unsigned int v10; // ebp
  char v11; // al
  char v12; // si
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  unsigned int v16; // eax
  wint_t *v17; // rcx
  wint_t v18; // dx
  wint_t *v19; // r8
  int v20; // eax
  int v21; // eax
  unsigned int v22; // r9d
  unsigned int v23; // ecx
  int v24; // eax
  int v25; // ecx
  wint_t *v26; // r8
  unsigned int v27; // edx
  bool v28; // cl
  bool v29; // cf
  bool v30; // zf
  wint_t **v31; // rax
  __int64 result; // rax
  wint_t **v33; // rdx
  wint_t **v34; // rdx
  wint_t *v35; // [rsp+90h] [rbp-48h]

  v4 = *a2;
  v6 = a3;
  v35 = *a2;
  if ( !*a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && a3 - 2 > 0x22 )
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
  v11 = a4;
  v12 = a4 | 2;
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
  v22 = 0xFFFFFFFF / v6;
  while ( 1 )
  {
    if ( v9 >= 0x30u )
    {
      if ( v9 < 0x3Au )
      {
        v23 = v9 - 48;
        goto LABEL_121;
      }
      if ( v9 >= 0xFF10u )
      {
        if ( v9 < 0xFF1Au )
        {
          v23 = v9 - 65296;
LABEL_121:
          if ( v23 != -1 )
            goto LABEL_130;
        }
      }
      else if ( v9 >= 0x660u )
      {
        if ( v9 < 0x66Au )
        {
          v23 = v9 - 1632;
          goto LABEL_121;
        }
        if ( v9 >= 0x6F0u )
        {
          if ( v9 < 0x6FAu )
          {
            v23 = v9 - 1776;
            goto LABEL_121;
          }
          v24 = 2406;
          if ( v9 >= 0x966u )
          {
            if ( v9 < 0x970u )
              goto LABEL_92;
            v24 = 2534;
            if ( v9 >= 0x9E6u )
            {
              if ( v9 < 0x9F0u )
                goto LABEL_92;
              v24 = 2662;
              if ( v9 >= 0xA66u )
              {
                if ( v9 < 0xA70u )
                  goto LABEL_92;
                v24 = 2790;
                if ( v9 >= 0xAE6u )
                {
                  if ( v9 < 0xAF0u )
                    goto LABEL_92;
                  v24 = 2918;
                  if ( v9 >= 0xB66u )
                  {
                    if ( v9 < 0xB70u )
                      goto LABEL_92;
                    v24 = 3174;
                    if ( v9 >= 0xC66u )
                    {
                      if ( v9 < 0xC70u )
                        goto LABEL_92;
                      v24 = 3302;
                      if ( v9 >= 0xCE6u )
                      {
                        if ( v9 < 0xCF0u )
                          goto LABEL_92;
                        v24 = 3430;
                        if ( v9 >= 0xD66u )
                        {
                          if ( v9 < 0xD70u )
                            goto LABEL_92;
                          v24 = 3664;
                          if ( v9 >= 0xE50u )
                          {
                            if ( v9 < 0xE5Au )
                              goto LABEL_92;
                            v24 = 3792;
                            if ( v9 >= 0xED0u )
                            {
                              if ( v9 < 0xEDAu )
                                goto LABEL_92;
                              v24 = 3872;
                              if ( v9 >= 0xF20u )
                              {
                                if ( v9 < 0xF2Au )
                                  goto LABEL_92;
                                v24 = 4160;
                                if ( v9 >= 0x1040u )
                                {
                                  if ( v9 < 0x104Au )
                                    goto LABEL_92;
                                  v24 = 6112;
                                  if ( v9 >= 0x17E0u )
                                  {
                                    if ( v9 < 0x17EAu )
                                    {
LABEL_92:
                                      v23 = v9 - v24;
                                      goto LABEL_121;
                                    }
                                    if ( (unsigned __int16)(v9 - 6160) <= 9u )
                                    {
                                      v23 = v9 - 6160;
                                      goto LABEL_121;
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
LABEL_130:
    v26 = *a2;
    if ( v23 >= v6 )
      break;
    v9 = *v26;
    v27 = v6 * v10 + v23;
    v28 = v27 < v6 * v10;
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
    result = 0x7FFFFFFF;
    if ( (v12 & 4) != 0 )
      goto LABEL_143;
    if ( (v12 & 1) != 0 )
    {
      if ( (v12 & 2) == 0 )
      {
        if ( v10 <= 0x7FFFFFFF )
          goto LABEL_145;
        goto LABEL_143;
      }
      if ( v10 > 0x80000000 )
      {
LABEL_143:
        *((_BYTE *)a1 + 48) = 1;
        *((_DWORD *)a1 + 11) = 34;
        if ( (v12 & 1) != 0 )
        {
          v34 = (wint_t **)a2[1];
          if ( (v12 & 2) != 0 )
          {
            if ( v34 )
              *v34 = *a2;
            return 0x80000000LL;
          }
          else if ( v34 )
          {
            *v34 = *a2;
          }
          return result;
        }
        v10 = -1;
LABEL_145:
        v33 = (wint_t **)a2[1];
        if ( v33 )
          *v33 = *a2;
        return v10;
      }
    }
    else if ( (v12 & 2) == 0 )
    {
      goto LABEL_145;
    }
    v10 = -v10;
    goto LABEL_145;
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
0x18001e680  mov     [rsp+arg_10], rbx
0x18001e685  mov     [rsp+arg_0], rcx
0x18001e68a  push    rbp
0x18001e68b  push    rsi
0x18001e68c  push    rdi
0x18001e68d  push    r12
0x18001e68f  push    r13
0x18001e691  push    r14
0x18001e693  push    r15
0x18001e695  sub     rsp, 0A0h
0x18001e69c  mov     r12, [rdx]
0x18001e69f  xor     r13d, r13d
0x18001e6a2  movzx   esi, r9b
0x18001e6a6  mov     r15d, r8d
0x18001e6a9  mov     [rsp+0D8h+var_48], r12
0x18001e6b1  mov     rdi, rdx
0x18001e6b4  test    r12, r12
0x18001e6b7  jnz     short loc_18001E6CB
0x18001e6b9  call    _errno
0x18001e6be  mov     dword ptr [rax], 16h
0x18001e6c4  call    _invalid_parameter_noinfo
0x18001e6c9  jmp     short loc_18001E6FD
0x18001e6cb  test    r15d, r15d
0x18001e6ce  jz      short loc_18001E715
0x18001e6d0  lea     eax, [r8-2]
0x18001e6d4  cmp     eax, 22h ; '"'
0x18001e6d7  jbe     short loc_18001E715
0x18001e6d9  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x18001e6de  xor     r9d, r9d; LineNo
0x18001e6e1  mov     byte ptr [rcx+30h], 1
0x18001e6e5  xor     r8d, r8d; FileName
0x18001e6e8  mov     dword ptr [rcx+2Ch], 16h
0x18001e6ef  xor     edx, edx; FunctionName
0x18001e6f1  xor     ecx, ecx; Expression
0x18001e6f3  mov     [rsp+0D8h+var_B8], r13; uintptr_t
0x18001e6f8  call    _invalid_parameter_internal
0x18001e6fd  mov     rcx, [rdi+8]; this
0x18001e701  test    rcx, rcx
0x18001e704  jz      loc_18001ED78
0x18001e70a  mov     rax, [rdi]
0x18001e70d  mov     [rcx], rax
0x18001e710  jmp     loc_18001ED78
0x18001e715  movzx   ebx, word ptr [r12]
0x18001e71a  lea     rax, [r12+2]
0x18001e71f  mov     [rdx], rax
0x18001e722  mov     ebp, r13d
0x18001e725  cmp     [rcx+28h], r13b
0x18001e729  jnz     short loc_18001E73F
0x18001e72b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001e730  jmp     short loc_18001E73F
0x18001e732  mov     rax, [rdi]
0x18001e735  movzx   ebx, word ptr [rax]
0x18001e738  add     rax, 2
0x18001e73c  mov     [rdi], rax
0x18001e73f  mov     edx, 8; Type
0x18001e744  movzx   ecx, bx; C
0x18001e747  call    iswctype
0x18001e74c  test    eax, eax
0x18001e74e  jnz     short loc_18001E732
0x18001e750  mov     eax, esi
0x18001e752  mov     ecx, 0FFFDh
0x18001e757  or      esi, 2
0x18001e75a  cmp     bx, 2Dh ; '-'
0x18001e75e  cmovnz  esi, eax
0x18001e761  lea     eax, [rbx-2Bh]
0x18001e764  test    cx, ax
0x18001e767  jnz     short loc_18001E776
0x18001e769  mov     rax, [rdi]
0x18001e76c  movzx   ebx, word ptr [rax]
0x18001e76f  add     rax, 2
0x18001e773  mov     [rdi], rax
0x18001e776  mov     [rsp+0D8h+arg_8], 0A70h
0x18001e781  mov     eax, 0A66h
0x18001e786  mov     [rsp+0D8h+var_A8], 0AE6h
0x18001e78e  mov     ecx, 30h ; '0'
0x18001e793  mov     [rsp+0D8h+var_A4], 0AF0h
0x18001e79b  mov     edx, 0FF10h
0x18001e7a0  mov     [rsp+0D8h+var_A0], 0B66h
0x18001e7a8  mov     r8d, 660h
0x18001e7ae  mov     [rsp+0D8h+var_9C], 0B70h
0x18001e7b6  lea     r10d, [rax-80h]
0x18001e7ba  mov     [rsp+0D8h+var_98], 0C66h
0x18001e7c2  mov     r11d, 6F0h
0x18001e7c8  mov     [rsp+0D8h+var_94], 0C70h
0x18001e7d0  mov     r9d, 966h
0x18001e7d6  mov     [rsp+0D8h+var_90], 0CE6h
0x18001e7de  mov     [rsp+0D8h+var_8C], 0CF0h
0x18001e7e6  mov     [rsp+0D8h+var_88], 0D66h
0x18001e7ee  mov     [rsp+0D8h+var_84], 0D70h
0x18001e7f6  mov     [rsp+0D8h+var_80], 0E50h
0x18001e7fe  mov     [rsp+0D8h+var_7C], 0E5Ah
0x18001e806  mov     [rsp+0D8h+var_78], 0ED0h
0x18001e80e  mov     [rsp+0D8h+var_74], 0EDAh
0x18001e816  mov     [rsp+0D8h+var_70], 0F20h
0x18001e81e  mov     [rsp+0D8h+var_6C], 0F2Ah
0x18001e826  mov     [rsp+0D8h+var_68], 1040h
0x18001e82e  mov     [rsp+0D8h+var_64], 104Ah
0x18001e836  mov     [rsp+0D8h+var_60], 17E0h
0x18001e83e  mov     [rsp+0D8h+var_5C], 17EAh
0x18001e846  mov     [rsp+0D8h+var_58], 1810h
0x18001e851  mov     [rsp+0D8h+var_54], 0FF1Ah
0x18001e85c  mov     [rsp+0D8h+var_50], 19h
0x18001e867  test    r15d, 0FFFFFFEFh
0x18001e86e  jnz     loc_18001EAED
0x18001e874  cmp     bx, cx
0x18001e877  jb      loc_18001EA3E
0x18001e87d  cmp     bx, 3Ah ; ':'
0x18001e881  jnb     short loc_18001E88D
0x18001e883  movzx   eax, bx
0x18001e886  sub     eax, ecx
0x18001e888  jmp     loc_18001EA39
0x18001e88d  cmp     bx, dx
0x18001e890  jnb     loc_18001EA2A
0x18001e896  cmp     bx, r8w
0x18001e89a  jb      loc_18001EA3E
0x18001e8a0  mov     ecx, 66Ah
0x18001e8a5  cmp     bx, cx
0x18001e8a8  jnb     short loc_18001E8B5
0x18001e8aa  movzx   eax, bx
0x18001e8ad  sub     eax, r8d
0x18001e8b0  jmp     loc_18001EA39
0x18001e8b5  cmp     bx, r11w
0x18001e8b9  jb      loc_18001EA3E
0x18001e8bf  mov     ecx, 6FAh
0x18001e8c4  cmp     bx, cx
0x18001e8c7  jnb     short loc_18001E8D4
0x18001e8c9  movzx   eax, bx
0x18001e8cc  sub     eax, r11d
0x18001e8cf  jmp     loc_18001EA39
0x18001e8d4  cmp     bx, r9w
0x18001e8d8  jb      loc_18001EA3E
0x18001e8de  mov     ecx, 970h
0x18001e8e3  cmp     bx, cx
0x18001e8e6  jnb     short loc_18001E8F3
0x18001e8e8  movzx   eax, bx
0x18001e8eb  sub     eax, r9d
0x18001e8ee  jmp     loc_18001EA39
0x18001e8f3  cmp     bx, r10w
0x18001e8f7  jb      loc_18001EA3E
0x18001e8fd  mov     ecx, 9F0h
0x18001e902  cmp     bx, cx
0x18001e905  jnb     short loc_18001E912
0x18001e907  movzx   eax, bx
0x18001e90a  sub     eax, r10d
0x18001e90d  jmp     loc_18001EA39
0x18001e912  cmp     bx, ax
0x18001e915  jb      loc_18001EA3E
0x18001e91b  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x18001e923  jnb     short loc_18001E932
0x18001e925  movzx   eax, bx
0x18001e928  sub     eax, 0A66h
0x18001e92d  jmp     loc_18001EA39
0x18001e932  mov     ecx, [rsp+0D8h+var_A8]
0x18001e936  cmp     bx, cx
0x18001e939  jb      loc_18001EA3E
0x18001e93f  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x18001e944  jb      loc_18001E883
0x18001e94a  mov     ecx, [rsp+0D8h+var_A0]
0x18001e94e  cmp     bx, cx
0x18001e951  jb      loc_18001EA3E
0x18001e957  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x18001e95c  jb      loc_18001E883
0x18001e962  mov     ecx, [rsp+0D8h+var_98]
0x18001e966  cmp     bx, cx
0x18001e969  jb      loc_18001EA3E
0x18001e96f  cmp     bx, word ptr [rsp+0D8h+var_94]
0x18001e974  jb      loc_18001E883
0x18001e97a  mov     ecx, [rsp+0D8h+var_90]
0x18001e97e  cmp     bx, cx
0x18001e981  jb      loc_18001EA3E
0x18001e987  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x18001e98c  jb      loc_18001E883
0x18001e992  mov     ecx, [rsp+0D8h+var_88]
0x18001e996  cmp     bx, cx
0x18001e999  jb      loc_18001EA3E
0x18001e99f  cmp     bx, word ptr [rsp+0D8h+var_84]
0x18001e9a4  jb      loc_18001E883
0x18001e9aa  mov     ecx, [rsp+0D8h+var_80]
0x18001e9ae  cmp     bx, cx
0x18001e9b1  jb      loc_18001EA3E
0x18001e9b7  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x18001e9bc  jb      loc_18001E883
0x18001e9c2  mov     ecx, [rsp+0D8h+var_78]
0x18001e9c6  cmp     bx, cx
0x18001e9c9  jb      short loc_18001EA3E
0x18001e9cb  cmp     bx, word ptr [rsp+0D8h+var_74]
0x18001e9d0  jb      loc_18001E883
0x18001e9d6  mov     ecx, [rsp+0D8h+var_70]
0x18001e9da  cmp     bx, cx
0x18001e9dd  jb      short loc_18001EA3E
0x18001e9df  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x18001e9e4  jb      loc_18001E883
0x18001e9ea  mov     ecx, [rsp+0D8h+var_68]
0x18001e9ee  cmp     bx, cx
0x18001e9f1  jb      short loc_18001EA3E
0x18001e9f3  cmp     bx, word ptr [rsp+0D8h+var_64]
0x18001e9f8  jb      loc_18001E883
0x18001e9fe  mov     ecx, [rsp+0D8h+var_60]
0x18001ea02  cmp     bx, cx
0x18001ea05  jb      short loc_18001EA3E
0x18001ea07  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x18001ea0c  jb      loc_18001E883
0x18001ea12  mov     ecx, [rsp+0D8h+var_58]
0x18001ea19  movzx   eax, bx
0x18001ea1c  sub     ax, cx
0x18001ea1f  cmp     ax, 9
0x18001ea23  ja      short loc_18001EA3E
0x18001ea25  jmp     loc_18001E883
0x18001ea2a  cmp     bx, word ptr [rsp+0D8h+var_54]
0x18001ea32  jnb     short loc_18001EA3E
0x18001ea34  movzx   eax, bx
0x18001ea37  sub     eax, edx
0x18001ea39  cmp     eax, 0FFFFFFFFh
0x18001ea3c  jnz     short loc_18001EA64
0x18001ea3e  mov     edx, [rsp+0D8h+var_50]
0x18001ea45  movzx   ecx, bx
0x18001ea48  lea     eax, [rcx-41h]
0x18001ea4b  cmp     eax, edx
0x18001ea4d  lea     eax, [rcx-61h]
0x18001ea50  jbe     short loc_18001EA5A
0x18001ea52  cmp     eax, edx
0x18001ea54  ja      loc_18001EADE
0x18001ea5a  cmp     eax, edx
0x18001ea5c  ja      short loc_18001EA61
0x18001ea5e  add     ecx, 0FFFFFFE0h
0x18001ea61  lea     eax, [rcx-37h]
0x18001ea64  test    eax, eax
0x18001ea66  jnz     short loc_18001EADE
0x18001ea68  mov     rcx, [rdi]
0x18001ea6b  mov     r9d, 0FFDFh
0x18001ea71  movzx   edx, word ptr [rcx]
0x18001ea74  lea     r8, [rcx+2]
0x18001ea78  mov     [rdi], r8
0x18001ea7b  lea     eax, [rdx-58h]
0x18001ea7e  test    r9w, ax
0x18001ea82  jz      short loc_18001EAC6
0x18001ea84  test    r15d, r15d
0x18001ea87  mov     [rdi], rcx
0x18001ea8a  mov     eax, 8
0x18001ea8f  cmovnz  eax, r15d
0x18001ea93  mov     r15d, eax
0x18001ea96  test    dx, dx
0x18001ea99  jz      short loc_18001EABE
0x18001ea9b  cmp     [rcx], dx
0x18001ea9e  jz      short loc_18001EABE
0x18001eaa0  call    _errno
0x18001eaa5  mov     dword ptr [rax], 16h
0x18001eaab  call    _invalid_parameter_noinfo
0x18001eab0  mov     r8d, 660h
0x18001eab6  mov     r11d, 6F0h
0x18001eabc  jmp     short loc_18001EAED
0x18001eabe  mov     r8d, 660h
0x18001eac4  jmp     short loc_18001EAED
0x18001eac6  movzx   ebx, word ptr [r8]
0x18001eaca  lea     rax, [r8+2]
0x18001eace  mov     [rdi], rax
0x18001ead1  mov     r8d, 660h
0x18001ead7  mov     eax, 10h
0x18001eadc  jmp     short loc_18001EAE3
0x18001eade  mov     eax, 0Ah
0x18001eae3  test    r15d, r15d
0x18001eae6  cmovnz  eax, r15d
0x18001eaea  mov     r15d, eax
0x18001eaed  xor     edx, edx
0x18001eaef  or      eax, 0FFFFFFFFh
0x18001eaf2  div     r15d
0x18001eaf5  mov     r10d, 61h ; 'a'
0x18001eafb  mov     r14d, 0FF10h
0x18001eb01  mov     r9d, eax
0x18001eb04  lea     r12d, [r10-31h]
0x18001eb08  cmp     bx, r12w
0x18001eb0c  jb      loc_18001ECBA
0x18001eb12  cmp     bx, 3Ah ; ':'
0x18001eb16  jnb     short loc_18001EB23
0x18001eb18  movzx   ecx, bx
0x18001eb1b  sub     ecx, r12d
0x18001eb1e  jmp     loc_18001ECB5
0x18001eb23  cmp     bx, r14w
0x18001eb27  jnb     loc_18001ECA5
0x18001eb2d  cmp     bx, r8w
0x18001eb31  jb      loc_18001ECBA
0x18001eb37  mov     eax, 66Ah
0x18001eb3c  cmp     bx, ax
0x18001eb3f  jnb     short loc_18001EB4C
0x18001eb41  movzx   ecx, bx
0x18001eb44  sub     ecx, r8d
0x18001eb47  jmp     loc_18001ECB5
0x18001eb4c  cmp     bx, r11w
0x18001eb50  jb      loc_18001ECBA
0x18001eb56  mov     eax, 6FAh
0x18001eb5b  cmp     bx, ax
0x18001eb5e  jnb     short loc_18001EB6B
0x18001eb60  movzx   ecx, bx
0x18001eb63  sub     ecx, r11d
0x18001eb66  jmp     loc_18001ECB5
0x18001eb6b  mov     eax, 966h
0x18001eb70  cmp     bx, ax
0x18001eb73  jb      loc_18001ECBA
0x18001eb79  lea     ecx, [rax+0Ah]
0x18001eb7c  cmp     bx, cx
  ... truncated ...
```

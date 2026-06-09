# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<wchar_t>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x18001e998`
- end: `0x18001f119`
- name: `??$parse_integer@_KV?$c_string_character_source@_W@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1921`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001f354`
- `0x18001fe98`
- `0x18001ff4c`
- `0x180020230`
- `0x1800202e4`

## callees

- `0x1800073e8`
- `0x1800074a0`
- `0x180007788`
- `0x1800149cc`
- `0x18001dbe4`
- `0x18001e998`
- `0x180021810`

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
0x18001e998  mov     [rsp+arg_10], rbx
0x18001e99d  mov     [rsp+arg_0], rcx
0x18001e9a2  push    rbp
0x18001e9a3  push    rsi
0x18001e9a4  push    rdi
0x18001e9a5  push    r12
0x18001e9a7  push    r13
0x18001e9a9  push    r14
0x18001e9ab  push    r15
0x18001e9ad  sub     rsp, 0A0h
0x18001e9b4  mov     r12, [rdx]
0x18001e9b7  xor     r13d, r13d
0x18001e9ba  movzx   esi, r9b
0x18001e9be  mov     r15d, r8d
0x18001e9c1  mov     [rsp+0D8h+var_48], r12
0x18001e9c9  mov     rdi, rdx
0x18001e9cc  test    r12, r12
0x18001e9cf  jnz     short loc_18001E9E3
0x18001e9d1  call    _errno
0x18001e9d6  mov     dword ptr [rax], 16h
0x18001e9dc  call    _invalid_parameter_noinfo
0x18001e9e1  jmp     short loc_18001EA15
0x18001e9e3  test    r15d, r15d
0x18001e9e6  jz      short loc_18001EA2D
0x18001e9e8  lea     eax, [r8-2]
0x18001e9ec  cmp     eax, 22h ; '"'
0x18001e9ef  jbe     short loc_18001EA2D
0x18001e9f1  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x18001e9f6  xor     r9d, r9d; LineNo
0x18001e9f9  mov     byte ptr [rcx+30h], 1
0x18001e9fd  xor     r8d, r8d; FileName
0x18001ea00  mov     dword ptr [rcx+2Ch], 16h
0x18001ea07  xor     edx, edx; FunctionName
0x18001ea09  xor     ecx, ecx; Expression
0x18001ea0b  mov     [rsp+0D8h+var_B8], r13; uintptr_t
0x18001ea10  call    _invalid_parameter_internal
0x18001ea15  mov     rcx, [rdi+8]; this
0x18001ea19  test    rcx, rcx
0x18001ea1c  jz      loc_18001F080
0x18001ea22  mov     rax, [rdi]
0x18001ea25  mov     [rcx], rax
0x18001ea28  jmp     loc_18001F080
0x18001ea2d  movzx   ebx, word ptr [r12]
0x18001ea32  lea     rax, [r12+2]
0x18001ea37  mov     [rdx], rax
0x18001ea3a  mov     rbp, r13
0x18001ea3d  cmp     [rcx+28h], r13b
0x18001ea41  jnz     short loc_18001EA57
0x18001ea43  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001ea48  jmp     short loc_18001EA57
0x18001ea4a  mov     rax, [rdi]
0x18001ea4d  movzx   ebx, word ptr [rax]
0x18001ea50  add     rax, 2
0x18001ea54  mov     [rdi], rax
0x18001ea57  mov     edx, 8; Type
0x18001ea5c  movzx   ecx, bx; C
0x18001ea5f  call    iswctype
0x18001ea64  test    eax, eax
0x18001ea66  jnz     short loc_18001EA4A
0x18001ea68  mov     eax, esi
0x18001ea6a  mov     ecx, 0FFFDh
0x18001ea6f  or      esi, 2
0x18001ea72  cmp     bx, 2Dh ; '-'
0x18001ea76  cmovnz  esi, eax
0x18001ea79  lea     eax, [rbx-2Bh]
0x18001ea7c  test    cx, ax
0x18001ea7f  jnz     short loc_18001EA8E
0x18001ea81  mov     rax, [rdi]
0x18001ea84  movzx   ebx, word ptr [rax]
0x18001ea87  add     rax, 2
0x18001ea8b  mov     [rdi], rax
0x18001ea8e  mov     [rsp+0D8h+arg_8], 0A70h
0x18001ea99  mov     eax, 0A66h
0x18001ea9e  mov     [rsp+0D8h+var_A8], 0AE6h
0x18001eaa6  mov     ecx, 30h ; '0'
0x18001eaab  mov     [rsp+0D8h+var_A4], 0AF0h
0x18001eab3  mov     edx, 0FF10h
0x18001eab8  mov     [rsp+0D8h+var_A0], 0B66h
0x18001eac0  mov     r8d, 660h
0x18001eac6  mov     [rsp+0D8h+var_9C], 0B70h
0x18001eace  lea     r11d, [rax-80h]
0x18001ead2  mov     [rsp+0D8h+var_98], 0C66h
0x18001eada  mov     r9d, 6F0h
0x18001eae0  mov     [rsp+0D8h+var_94], 0C70h
0x18001eae8  mov     r10d, 966h
0x18001eaee  mov     [rsp+0D8h+var_90], 0CE6h
0x18001eaf6  mov     [rsp+0D8h+var_8C], 0CF0h
0x18001eafe  mov     [rsp+0D8h+var_88], 0D66h
0x18001eb06  mov     [rsp+0D8h+var_84], 0D70h
0x18001eb0e  mov     [rsp+0D8h+var_80], 0E50h
0x18001eb16  mov     [rsp+0D8h+var_7C], 0E5Ah
0x18001eb1e  mov     [rsp+0D8h+var_78], 0ED0h
0x18001eb26  mov     [rsp+0D8h+var_74], 0EDAh
0x18001eb2e  mov     [rsp+0D8h+var_70], 0F20h
0x18001eb36  mov     [rsp+0D8h+var_6C], 0F2Ah
0x18001eb3e  mov     [rsp+0D8h+var_68], 1040h
0x18001eb46  mov     [rsp+0D8h+var_64], 104Ah
0x18001eb4e  mov     [rsp+0D8h+var_60], 17E0h
0x18001eb56  mov     [rsp+0D8h+var_5C], 17EAh
0x18001eb5e  mov     [rsp+0D8h+var_58], 1810h
0x18001eb69  mov     [rsp+0D8h+var_54], 0FF1Ah
0x18001eb74  mov     [rsp+0D8h+var_50], 19h
0x18001eb7f  test    r15d, 0FFFFFFEFh
0x18001eb86  jnz     loc_18001EDF3
0x18001eb8c  cmp     bx, cx
0x18001eb8f  jb      loc_18001ED56
0x18001eb95  cmp     bx, 3Ah ; ':'
0x18001eb99  jnb     short loc_18001EBA5
0x18001eb9b  movzx   eax, bx
0x18001eb9e  sub     eax, ecx
0x18001eba0  jmp     loc_18001ED51
0x18001eba5  cmp     bx, dx
0x18001eba8  jnb     loc_18001ED42
0x18001ebae  cmp     bx, r8w
0x18001ebb2  jb      loc_18001ED56
0x18001ebb8  mov     ecx, 66Ah
0x18001ebbd  cmp     bx, cx
0x18001ebc0  jnb     short loc_18001EBCD
0x18001ebc2  movzx   eax, bx
0x18001ebc5  sub     eax, r8d
0x18001ebc8  jmp     loc_18001ED51
0x18001ebcd  cmp     bx, r9w
0x18001ebd1  jb      loc_18001ED56
0x18001ebd7  mov     ecx, 6FAh
0x18001ebdc  cmp     bx, cx
0x18001ebdf  jnb     short loc_18001EBEC
0x18001ebe1  movzx   eax, bx
0x18001ebe4  sub     eax, r9d
0x18001ebe7  jmp     loc_18001ED51
0x18001ebec  cmp     bx, r10w
0x18001ebf0  jb      loc_18001ED56
0x18001ebf6  mov     ecx, 970h
0x18001ebfb  cmp     bx, cx
0x18001ebfe  jnb     short loc_18001EC0B
0x18001ec00  movzx   eax, bx
0x18001ec03  sub     eax, r10d
0x18001ec06  jmp     loc_18001ED51
0x18001ec0b  cmp     bx, r11w
0x18001ec0f  jb      loc_18001ED56
0x18001ec15  mov     ecx, 9F0h
0x18001ec1a  cmp     bx, cx
0x18001ec1d  jnb     short loc_18001EC2A
0x18001ec1f  movzx   eax, bx
0x18001ec22  sub     eax, r11d
0x18001ec25  jmp     loc_18001ED51
0x18001ec2a  cmp     bx, ax
0x18001ec2d  jb      loc_18001ED56
0x18001ec33  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x18001ec3b  jnb     short loc_18001EC4A
0x18001ec3d  movzx   eax, bx
0x18001ec40  sub     eax, 0A66h
0x18001ec45  jmp     loc_18001ED51
0x18001ec4a  mov     ecx, [rsp+0D8h+var_A8]
0x18001ec4e  cmp     bx, cx
0x18001ec51  jb      loc_18001ED56
0x18001ec57  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x18001ec5c  jb      loc_18001EB9B
0x18001ec62  mov     ecx, [rsp+0D8h+var_A0]
0x18001ec66  cmp     bx, cx
0x18001ec69  jb      loc_18001ED56
0x18001ec6f  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x18001ec74  jb      loc_18001EB9B
0x18001ec7a  mov     ecx, [rsp+0D8h+var_98]
0x18001ec7e  cmp     bx, cx
0x18001ec81  jb      loc_18001ED56
0x18001ec87  cmp     bx, word ptr [rsp+0D8h+var_94]
0x18001ec8c  jb      loc_18001EB9B
0x18001ec92  mov     ecx, [rsp+0D8h+var_90]
0x18001ec96  cmp     bx, cx
0x18001ec99  jb      loc_18001ED56
0x18001ec9f  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x18001eca4  jb      loc_18001EB9B
0x18001ecaa  mov     ecx, [rsp+0D8h+var_88]
0x18001ecae  cmp     bx, cx
0x18001ecb1  jb      loc_18001ED56
0x18001ecb7  cmp     bx, word ptr [rsp+0D8h+var_84]
0x18001ecbc  jb      loc_18001EB9B
0x18001ecc2  mov     ecx, [rsp+0D8h+var_80]
0x18001ecc6  cmp     bx, cx
0x18001ecc9  jb      loc_18001ED56
0x18001eccf  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x18001ecd4  jb      loc_18001EB9B
0x18001ecda  mov     ecx, [rsp+0D8h+var_78]
0x18001ecde  cmp     bx, cx
0x18001ece1  jb      short loc_18001ED56
0x18001ece3  cmp     bx, word ptr [rsp+0D8h+var_74]
0x18001ece8  jb      loc_18001EB9B
0x18001ecee  mov     ecx, [rsp+0D8h+var_70]
0x18001ecf2  cmp     bx, cx
0x18001ecf5  jb      short loc_18001ED56
0x18001ecf7  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x18001ecfc  jb      loc_18001EB9B
0x18001ed02  mov     ecx, [rsp+0D8h+var_68]
0x18001ed06  cmp     bx, cx
0x18001ed09  jb      short loc_18001ED56
0x18001ed0b  cmp     bx, word ptr [rsp+0D8h+var_64]
0x18001ed10  jb      loc_18001EB9B
0x18001ed16  mov     ecx, [rsp+0D8h+var_60]
0x18001ed1a  cmp     bx, cx
0x18001ed1d  jb      short loc_18001ED56
0x18001ed1f  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x18001ed24  jb      loc_18001EB9B
0x18001ed2a  mov     ecx, [rsp+0D8h+var_58]
0x18001ed31  movzx   eax, bx
0x18001ed34  sub     ax, cx
0x18001ed37  cmp     ax, 9
0x18001ed3b  ja      short loc_18001ED56
0x18001ed3d  jmp     loc_18001EB9B
0x18001ed42  cmp     bx, word ptr [rsp+0D8h+var_54]
0x18001ed4a  jnb     short loc_18001ED56
0x18001ed4c  movzx   eax, bx
0x18001ed4f  sub     eax, edx
0x18001ed51  cmp     eax, 0FFFFFFFFh
0x18001ed54  jnz     short loc_18001ED78
0x18001ed56  mov     edx, [rsp+0D8h+var_50]
0x18001ed5d  movzx   ecx, bx
0x18001ed60  lea     eax, [rcx-41h]
0x18001ed63  cmp     eax, edx
0x18001ed65  lea     eax, [rcx-61h]
0x18001ed68  jbe     short loc_18001ED6E
0x18001ed6a  cmp     eax, edx
0x18001ed6c  ja      short loc_18001EDE4
0x18001ed6e  cmp     eax, edx
0x18001ed70  ja      short loc_18001ED75
0x18001ed72  add     ecx, 0FFFFFFE0h
0x18001ed75  lea     eax, [rcx-37h]
0x18001ed78  test    eax, eax
0x18001ed7a  jnz     short loc_18001EDE4
0x18001ed7c  mov     rcx, [rdi]
0x18001ed7f  mov     r9d, 0FFDFh
0x18001ed85  movzx   edx, word ptr [rcx]
0x18001ed88  lea     r8, [rcx+2]
0x18001ed8c  mov     [rdi], r8
0x18001ed8f  lea     eax, [rdx-58h]
0x18001ed92  test    r9w, ax
0x18001ed96  jz      short loc_18001EDCC
0x18001ed98  test    r15d, r15d
0x18001ed9b  mov     [rdi], rcx
0x18001ed9e  mov     eax, 8
0x18001eda3  cmovnz  eax, r15d
0x18001eda7  mov     r15d, eax
0x18001edaa  test    dx, dx
0x18001edad  jz      short loc_18001EDC4
0x18001edaf  cmp     [rcx], dx
0x18001edb2  jz      short loc_18001EDC4
0x18001edb4  call    _errno
0x18001edb9  mov     dword ptr [rax], 16h
0x18001edbf  call    _invalid_parameter_noinfo
0x18001edc4  mov     r8d, 660h
0x18001edca  jmp     short loc_18001EDF3
0x18001edcc  movzx   ebx, word ptr [r8]
0x18001edd0  lea     rax, [r8+2]
0x18001edd4  mov     [rdi], rax
0x18001edd7  mov     r8d, 660h
0x18001eddd  mov     eax, 10h
0x18001ede2  jmp     short loc_18001EDE9
0x18001ede4  mov     eax, 0Ah
0x18001ede9  test    r15d, r15d
0x18001edec  cmovnz  eax, r15d
0x18001edf0  mov     r15d, eax
0x18001edf3  movsxd  r9, r15d
0x18001edf6  xor     edx, edx
0x18001edf8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001edfc  mov     r11d, 61h ; 'a'
0x18001ee02  div     r9
0x18001ee05  lea     r12d, [r11-31h]
0x18001ee09  mov     r14d, 0FF10h
0x18001ee0f  mov     r10, rax
0x18001ee12  cmp     bx, r12w
0x18001ee16  jb      loc_18001EFBD
0x18001ee1c  cmp     bx, 3Ah ; ':'
0x18001ee20  jnb     short loc_18001EE2D
0x18001ee22  movzx   ecx, bx
0x18001ee25  sub     ecx, r12d
0x18001ee28  jmp     loc_18001EFB8
0x18001ee2d  cmp     bx, r14w
0x18001ee31  jnb     loc_18001EFA8
0x18001ee37  cmp     bx, r8w
0x18001ee3b  jb      loc_18001EFBD
0x18001ee41  mov     eax, 66Ah
0x18001ee46  cmp     bx, ax
0x18001ee49  jnb     short loc_18001EE56
0x18001ee4b  movzx   ecx, bx
0x18001ee4e  sub     ecx, r8d
0x18001ee51  jmp     loc_18001EFB8
0x18001ee56  mov     eax, 6F0h
0x18001ee5b  cmp     bx, ax
0x18001ee5e  jb      loc_18001EFBD
0x18001ee64  lea     ecx, [rax+0Ah]
0x18001ee67  cmp     bx, cx
0x18001ee6a  jnb     short loc_18001EE76
0x18001ee6c  movzx   ecx, bx
0x18001ee6f  sub     ecx, eax
0x18001ee71  jmp     loc_18001EFB8
0x18001ee76  mov     eax, 966h
0x18001ee7b  cmp     bx, ax
0x18001ee7e  jb      loc_18001EFBD
0x18001ee84  lea     ecx, [rax+0Ah]
0x18001ee87  cmp     bx, cx
0x18001ee8a  jb      short loc_18001EE6C
  ... truncated ...
```

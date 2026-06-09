# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x18001df20`
- end: `0x18001e6ba`
- name: `??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$00@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1946`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001f1d8`
- `0x18001fde8`
- `0x180020008`
- `0x1800200c4`
- `0x180020174`

## callees

- `0x1800073e8`
- `0x1800074a0`
- `0x180007788`
- `0x1800149cc`
- `0x18001df20`
- `0x180021810`

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
0x18001df20  mov     [rsp+arg_10], rbx
0x18001df25  mov     [rsp+arg_0], rcx
0x18001df2a  push    rbp
0x18001df2b  push    rsi
0x18001df2c  push    rdi
0x18001df2d  push    r12
0x18001df2f  push    r13
0x18001df31  push    r14
0x18001df33  push    r15
0x18001df35  sub     rsp, 0A0h
0x18001df3c  mov     r12, [rdx]
0x18001df3f  xor     r13d, r13d
0x18001df42  movzx   esi, r9b
0x18001df46  mov     r15d, r8d
0x18001df49  mov     [rsp+0D8h+var_48], r12
0x18001df51  mov     rdi, rdx
0x18001df54  test    r12, r12
0x18001df57  jnz     short loc_18001DF6B
0x18001df59  call    _errno
0x18001df5e  mov     dword ptr [rax], 16h
0x18001df64  call    _invalid_parameter_noinfo
0x18001df69  jmp     short loc_18001DF9D
0x18001df6b  test    r15d, r15d
0x18001df6e  jz      short loc_18001DFB5
0x18001df70  lea     eax, [r8-2]
0x18001df74  cmp     eax, 22h ; '"'
0x18001df77  jbe     short loc_18001DFB5
0x18001df79  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x18001df7e  xor     r9d, r9d; LineNo
0x18001df81  mov     byte ptr [rcx+30h], 1
0x18001df85  xor     r8d, r8d; FileName
0x18001df88  mov     dword ptr [rcx+2Ch], 16h
0x18001df8f  xor     edx, edx; FunctionName
0x18001df91  xor     ecx, ecx; Expression
0x18001df93  mov     [rsp+0D8h+var_B8], r13; uintptr_t
0x18001df98  call    _invalid_parameter_internal
0x18001df9d  mov     rcx, [rdi+8]; this
0x18001dfa1  test    rcx, rcx
0x18001dfa4  jz      loc_18001E618
0x18001dfaa  mov     rax, [rdi]
0x18001dfad  mov     [rcx], rax
0x18001dfb0  jmp     loc_18001E618
0x18001dfb5  movzx   ebx, word ptr [r12]
0x18001dfba  lea     rax, [r12+2]
0x18001dfbf  mov     [rdx], rax
0x18001dfc2  mov     ebp, r13d
0x18001dfc5  cmp     [rcx+28h], r13b
0x18001dfc9  jnz     short loc_18001DFDF
0x18001dfcb  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001dfd0  jmp     short loc_18001DFDF
0x18001dfd2  mov     rax, [rdi]
0x18001dfd5  movzx   ebx, word ptr [rax]
0x18001dfd8  add     rax, 2
0x18001dfdc  mov     [rdi], rax
0x18001dfdf  mov     edx, 8; Type
0x18001dfe4  movzx   ecx, bx; C
0x18001dfe7  call    iswctype
0x18001dfec  test    eax, eax
0x18001dfee  jnz     short loc_18001DFD2
0x18001dff0  mov     eax, esi
0x18001dff2  mov     ecx, 0FFFDh
0x18001dff7  or      esi, 2
0x18001dffa  cmp     bx, 2Dh ; '-'
0x18001dffe  cmovnz  esi, eax
0x18001e001  lea     eax, [rbx-2Bh]
0x18001e004  test    cx, ax
0x18001e007  jnz     short loc_18001E016
0x18001e009  mov     rax, [rdi]
0x18001e00c  movzx   ebx, word ptr [rax]
0x18001e00f  add     rax, 2
0x18001e013  mov     [rdi], rax
0x18001e016  mov     [rsp+0D8h+arg_8], 0A70h
0x18001e021  mov     eax, 0A66h
0x18001e026  mov     [rsp+0D8h+var_A8], 0AE6h
0x18001e02e  mov     ecx, 30h ; '0'
0x18001e033  mov     [rsp+0D8h+var_A4], 0AF0h
0x18001e03b  mov     edx, 0FF10h
0x18001e040  mov     [rsp+0D8h+var_A0], 0B66h
0x18001e048  mov     r8d, 660h
0x18001e04e  mov     [rsp+0D8h+var_9C], 0B70h
0x18001e056  lea     r10d, [rax-80h]
0x18001e05a  mov     [rsp+0D8h+var_98], 0C66h
0x18001e062  mov     r11d, 6F0h
0x18001e068  mov     [rsp+0D8h+var_94], 0C70h
0x18001e070  mov     r9d, 966h
0x18001e076  mov     [rsp+0D8h+var_90], 0CE6h
0x18001e07e  mov     [rsp+0D8h+var_8C], 0CF0h
0x18001e086  mov     [rsp+0D8h+var_88], 0D66h
0x18001e08e  mov     [rsp+0D8h+var_84], 0D70h
0x18001e096  mov     [rsp+0D8h+var_80], 0E50h
0x18001e09e  mov     [rsp+0D8h+var_7C], 0E5Ah
0x18001e0a6  mov     [rsp+0D8h+var_78], 0ED0h
0x18001e0ae  mov     [rsp+0D8h+var_74], 0EDAh
0x18001e0b6  mov     [rsp+0D8h+var_70], 0F20h
0x18001e0be  mov     [rsp+0D8h+var_6C], 0F2Ah
0x18001e0c6  mov     [rsp+0D8h+var_68], 1040h
0x18001e0ce  mov     [rsp+0D8h+var_64], 104Ah
0x18001e0d6  mov     [rsp+0D8h+var_60], 17E0h
0x18001e0de  mov     [rsp+0D8h+var_5C], 17EAh
0x18001e0e6  mov     [rsp+0D8h+var_58], 1810h
0x18001e0f1  mov     [rsp+0D8h+var_54], 0FF1Ah
0x18001e0fc  mov     [rsp+0D8h+var_50], 19h
0x18001e107  test    r15d, 0FFFFFFEFh
0x18001e10e  jnz     loc_18001E38D
0x18001e114  cmp     bx, cx
0x18001e117  jb      loc_18001E2DE
0x18001e11d  cmp     bx, 3Ah ; ':'
0x18001e121  jnb     short loc_18001E12D
0x18001e123  movzx   eax, bx
0x18001e126  sub     eax, ecx
0x18001e128  jmp     loc_18001E2D9
0x18001e12d  cmp     bx, dx
0x18001e130  jnb     loc_18001E2CA
0x18001e136  cmp     bx, r8w
0x18001e13a  jb      loc_18001E2DE
0x18001e140  mov     ecx, 66Ah
0x18001e145  cmp     bx, cx
0x18001e148  jnb     short loc_18001E155
0x18001e14a  movzx   eax, bx
0x18001e14d  sub     eax, r8d
0x18001e150  jmp     loc_18001E2D9
0x18001e155  cmp     bx, r11w
0x18001e159  jb      loc_18001E2DE
0x18001e15f  mov     ecx, 6FAh
0x18001e164  cmp     bx, cx
0x18001e167  jnb     short loc_18001E174
0x18001e169  movzx   eax, bx
0x18001e16c  sub     eax, r11d
0x18001e16f  jmp     loc_18001E2D9
0x18001e174  cmp     bx, r9w
0x18001e178  jb      loc_18001E2DE
0x18001e17e  mov     ecx, 970h
0x18001e183  cmp     bx, cx
0x18001e186  jnb     short loc_18001E193
0x18001e188  movzx   eax, bx
0x18001e18b  sub     eax, r9d
0x18001e18e  jmp     loc_18001E2D9
0x18001e193  cmp     bx, r10w
0x18001e197  jb      loc_18001E2DE
0x18001e19d  mov     ecx, 9F0h
0x18001e1a2  cmp     bx, cx
0x18001e1a5  jnb     short loc_18001E1B2
0x18001e1a7  movzx   eax, bx
0x18001e1aa  sub     eax, r10d
0x18001e1ad  jmp     loc_18001E2D9
0x18001e1b2  cmp     bx, ax
0x18001e1b5  jb      loc_18001E2DE
0x18001e1bb  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x18001e1c3  jnb     short loc_18001E1D2
0x18001e1c5  movzx   eax, bx
0x18001e1c8  sub     eax, 0A66h
0x18001e1cd  jmp     loc_18001E2D9
0x18001e1d2  mov     ecx, [rsp+0D8h+var_A8]
0x18001e1d6  cmp     bx, cx
0x18001e1d9  jb      loc_18001E2DE
0x18001e1df  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x18001e1e4  jb      loc_18001E123
0x18001e1ea  mov     ecx, [rsp+0D8h+var_A0]
0x18001e1ee  cmp     bx, cx
0x18001e1f1  jb      loc_18001E2DE
0x18001e1f7  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x18001e1fc  jb      loc_18001E123
0x18001e202  mov     ecx, [rsp+0D8h+var_98]
0x18001e206  cmp     bx, cx
0x18001e209  jb      loc_18001E2DE
0x18001e20f  cmp     bx, word ptr [rsp+0D8h+var_94]
0x18001e214  jb      loc_18001E123
0x18001e21a  mov     ecx, [rsp+0D8h+var_90]
0x18001e21e  cmp     bx, cx
0x18001e221  jb      loc_18001E2DE
0x18001e227  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x18001e22c  jb      loc_18001E123
0x18001e232  mov     ecx, [rsp+0D8h+var_88]
0x18001e236  cmp     bx, cx
0x18001e239  jb      loc_18001E2DE
0x18001e23f  cmp     bx, word ptr [rsp+0D8h+var_84]
0x18001e244  jb      loc_18001E123
0x18001e24a  mov     ecx, [rsp+0D8h+var_80]
0x18001e24e  cmp     bx, cx
0x18001e251  jb      loc_18001E2DE
0x18001e257  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x18001e25c  jb      loc_18001E123
0x18001e262  mov     ecx, [rsp+0D8h+var_78]
0x18001e266  cmp     bx, cx
0x18001e269  jb      short loc_18001E2DE
0x18001e26b  cmp     bx, word ptr [rsp+0D8h+var_74]
0x18001e270  jb      loc_18001E123
0x18001e276  mov     ecx, [rsp+0D8h+var_70]
0x18001e27a  cmp     bx, cx
0x18001e27d  jb      short loc_18001E2DE
0x18001e27f  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x18001e284  jb      loc_18001E123
0x18001e28a  mov     ecx, [rsp+0D8h+var_68]
0x18001e28e  cmp     bx, cx
0x18001e291  jb      short loc_18001E2DE
0x18001e293  cmp     bx, word ptr [rsp+0D8h+var_64]
0x18001e298  jb      loc_18001E123
0x18001e29e  mov     ecx, [rsp+0D8h+var_60]
0x18001e2a2  cmp     bx, cx
0x18001e2a5  jb      short loc_18001E2DE
0x18001e2a7  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x18001e2ac  jb      loc_18001E123
0x18001e2b2  mov     ecx, [rsp+0D8h+var_58]
0x18001e2b9  movzx   eax, bx
0x18001e2bc  sub     ax, cx
0x18001e2bf  cmp     ax, 9
0x18001e2c3  ja      short loc_18001E2DE
0x18001e2c5  jmp     loc_18001E123
0x18001e2ca  cmp     bx, word ptr [rsp+0D8h+var_54]
0x18001e2d2  jnb     short loc_18001E2DE
0x18001e2d4  movzx   eax, bx
0x18001e2d7  sub     eax, edx
0x18001e2d9  cmp     eax, 0FFFFFFFFh
0x18001e2dc  jnz     short loc_18001E304
0x18001e2de  mov     edx, [rsp+0D8h+var_50]
0x18001e2e5  movzx   ecx, bx
0x18001e2e8  lea     eax, [rcx-41h]
0x18001e2eb  cmp     eax, edx
0x18001e2ed  lea     eax, [rcx-61h]
0x18001e2f0  jbe     short loc_18001E2FA
0x18001e2f2  cmp     eax, edx
0x18001e2f4  ja      loc_18001E37E
0x18001e2fa  cmp     eax, edx
0x18001e2fc  ja      short loc_18001E301
0x18001e2fe  add     ecx, 0FFFFFFE0h
0x18001e301  lea     eax, [rcx-37h]
0x18001e304  test    eax, eax
0x18001e306  jnz     short loc_18001E37E
0x18001e308  mov     rcx, [rdi]
0x18001e30b  mov     r9d, 0FFDFh
0x18001e311  movzx   edx, word ptr [rcx]
0x18001e314  lea     r8, [rcx+2]
0x18001e318  mov     [rdi], r8
0x18001e31b  lea     eax, [rdx-58h]
0x18001e31e  test    r9w, ax
0x18001e322  jz      short loc_18001E366
0x18001e324  test    r15d, r15d
0x18001e327  mov     [rdi], rcx
0x18001e32a  mov     eax, 8
0x18001e32f  cmovnz  eax, r15d
0x18001e333  mov     r15d, eax
0x18001e336  test    dx, dx
0x18001e339  jz      short loc_18001E35E
0x18001e33b  cmp     [rcx], dx
0x18001e33e  jz      short loc_18001E35E
0x18001e340  call    _errno
0x18001e345  mov     dword ptr [rax], 16h
0x18001e34b  call    _invalid_parameter_noinfo
0x18001e350  mov     r8d, 660h
0x18001e356  mov     r11d, 6F0h
0x18001e35c  jmp     short loc_18001E38D
0x18001e35e  mov     r8d, 660h
0x18001e364  jmp     short loc_18001E38D
0x18001e366  movzx   ebx, word ptr [r8]
0x18001e36a  lea     rax, [r8+2]
0x18001e36e  mov     [rdi], rax
0x18001e371  mov     r8d, 660h
0x18001e377  mov     eax, 10h
0x18001e37c  jmp     short loc_18001E383
0x18001e37e  mov     eax, 0Ah
0x18001e383  test    r15d, r15d
0x18001e386  cmovnz  eax, r15d
0x18001e38a  mov     r15d, eax
0x18001e38d  xor     edx, edx
0x18001e38f  or      eax, 0FFFFFFFFh
0x18001e392  div     r15d
0x18001e395  mov     r10d, 61h ; 'a'
0x18001e39b  mov     r14d, 0FF10h
0x18001e3a1  mov     r9d, eax
0x18001e3a4  lea     r12d, [r10-31h]
0x18001e3a8  cmp     bx, r12w
0x18001e3ac  jb      loc_18001E55A
0x18001e3b2  cmp     bx, 3Ah ; ':'
0x18001e3b6  jnb     short loc_18001E3C3
0x18001e3b8  movzx   ecx, bx
0x18001e3bb  sub     ecx, r12d
0x18001e3be  jmp     loc_18001E555
0x18001e3c3  cmp     bx, r14w
0x18001e3c7  jnb     loc_18001E545
0x18001e3cd  cmp     bx, r8w
0x18001e3d1  jb      loc_18001E55A
0x18001e3d7  mov     eax, 66Ah
0x18001e3dc  cmp     bx, ax
0x18001e3df  jnb     short loc_18001E3EC
0x18001e3e1  movzx   ecx, bx
0x18001e3e4  sub     ecx, r8d
0x18001e3e7  jmp     loc_18001E555
0x18001e3ec  cmp     bx, r11w
0x18001e3f0  jb      loc_18001E55A
0x18001e3f6  mov     eax, 6FAh
0x18001e3fb  cmp     bx, ax
0x18001e3fe  jnb     short loc_18001E40B
0x18001e400  movzx   ecx, bx
0x18001e403  sub     ecx, r11d
0x18001e406  jmp     loc_18001E555
0x18001e40b  mov     eax, 966h
0x18001e410  cmp     bx, ax
0x18001e413  jb      loc_18001E55A
0x18001e419  lea     ecx, [rax+0Ah]
0x18001e41c  cmp     bx, cx
  ... truncated ...
```

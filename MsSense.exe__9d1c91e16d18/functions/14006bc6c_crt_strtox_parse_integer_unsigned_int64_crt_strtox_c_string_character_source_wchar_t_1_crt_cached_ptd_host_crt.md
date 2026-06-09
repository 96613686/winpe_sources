# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<wchar_t>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x14006bc6c`
- end: `0x14006c406`
- name: `??$parse_integer@_KV?$c_string_character_source@_W@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1946`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, wint_t **, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140071b10`

## callees

- `0x14006147c`
- `0x140061534`
- `0x1400616b4`
- `0x140065e50`
- `0x14006bc6c`
- `0x140073ca0`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<wchar_t>,1>(
        __crt_cached_ptd_host *a1,
        wint_t **a2,
        __int64 a3,
        __int64 a4)
{
  wint_t *v4; // r12
  char v5; // si
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
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rcx
  int v25; // eax
  int v26; // ecx
  wint_t *v27; // r8
  bool v28; // cl
  bool v29; // cf
  bool v30; // zf
  wint_t **v31; // rax
  __int64 result; // rax
  wint_t **v33; // rdx
  wint_t **v34; // rdx
  wint_t *v35; // [rsp+90h] [rbp-48h]

  v4 = *a2;
  v5 = a4;
  v6 = a3;
  v35 = *a2;
  if ( !*a2 )
  {
    *(_DWORD *)sub_1400616B4(a1, a2, a3, a4) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( (_DWORD)a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_14006147C(0, 0, 0, 0, 0, a1);
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
    *(_DWORD *)((__int64 (*)(void))sub_1400616B4)() = 22;
    invalid_parameter_noinfo();
  }
LABEL_79:
  v22 = 0xFFFFFFFF % v6;
  v23 = 0xFFFFFFFF / v6;
  while ( 1 )
  {
    if ( v9 >= 0x30u )
    {
      if ( v9 < 0x3Au )
      {
        v24 = (unsigned int)v9 - 48;
        goto LABEL_121;
      }
      if ( v9 >= 0xFF10u )
      {
        if ( v9 < 0xFF1Au )
        {
          v24 = (unsigned int)v9 - 65296;
LABEL_121:
          if ( (_DWORD)v24 != -1 )
            goto LABEL_130;
        }
      }
      else if ( v9 >= 0x660u )
      {
        if ( v9 < 0x66Au )
        {
          v24 = (unsigned int)v9 - 1632;
          goto LABEL_121;
        }
        if ( v9 >= 0x6F0u )
        {
          if ( v9 < 0x6FAu )
          {
            v24 = (unsigned int)v9 - 1776;
            goto LABEL_121;
          }
          v25 = 2406;
          if ( v9 >= 0x966u )
          {
            if ( v9 < 0x970u )
              goto LABEL_92;
            v25 = 2534;
            if ( v9 >= 0x9E6u )
            {
              if ( v9 < 0x9F0u )
                goto LABEL_92;
              v25 = 2662;
              if ( v9 >= 0xA66u )
              {
                if ( v9 < 0xA70u )
                  goto LABEL_92;
                v25 = 2790;
                if ( v9 >= 0xAE6u )
                {
                  if ( v9 < 0xAF0u )
                    goto LABEL_92;
                  v25 = 2918;
                  if ( v9 >= 0xB66u )
                  {
                    if ( v9 < 0xB70u )
                      goto LABEL_92;
                    v25 = 3174;
                    if ( v9 >= 0xC66u )
                    {
                      if ( v9 < 0xC70u )
                        goto LABEL_92;
                      v25 = 3302;
                      if ( v9 >= 0xCE6u )
                      {
                        if ( v9 < 0xCF0u )
                          goto LABEL_92;
                        v25 = 3430;
                        if ( v9 >= 0xD66u )
                        {
                          if ( v9 < 0xD70u )
                            goto LABEL_92;
                          v25 = 3664;
                          if ( v9 >= 0xE50u )
                          {
                            if ( v9 < 0xE5Au )
                              goto LABEL_92;
                            v25 = 3792;
                            if ( v9 >= 0xED0u )
                            {
                              if ( v9 < 0xEDAu )
                                goto LABEL_92;
                              v25 = 3872;
                              if ( v9 >= 0xF20u )
                              {
                                if ( v9 < 0xF2Au )
                                  goto LABEL_92;
                                v25 = 4160;
                                if ( v9 >= 0x1040u )
                                {
                                  if ( v9 < 0x104Au )
                                    goto LABEL_92;
                                  v25 = 6112;
                                  if ( v9 >= 0x17E0u )
                                  {
                                    if ( v9 < 0x17EAu )
                                    {
LABEL_92:
                                      v24 = (unsigned int)v9 - v25;
                                      goto LABEL_121;
                                    }
                                    v22 = 6160;
                                    if ( (unsigned __int16)(v9 - 6160) <= 9u )
                                    {
                                      v24 = (unsigned int)v9 - 6160;
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
    if ( ((v26 = v9, v9 < 0x41u) || v9 > 0x5Au) && (v9 < 0x61u || v9 > 0x7Au) )
    {
      v24 = 0xFFFFFFFFLL;
    }
    else
    {
      if ( (unsigned __int16)(v9 - 97) <= 0x19u )
        v26 = v9 - 32;
      v24 = (unsigned int)(v26 - 55);
    }
LABEL_130:
    v27 = *a2;
    if ( (unsigned int)v24 >= v6 )
      break;
    v9 = *v27;
    v22 = v6 * v10 + (unsigned int)v24;
    v28 = (unsigned int)v22 < v6 * v10;
    v29 = v10 < (unsigned int)v23;
    v30 = v10 == (_DWORD)v23;
    v10 = v22;
    *a2 = v27 + 1;
    v12 |= (4 * (!v29 && !v30 || v28)) | 8;
  }
  *a2 = v27 - 1;
  if ( v9 && *(v27 - 1) != v9 )
  {
    *(_DWORD *)sub_1400616B4(v24, v22, v27, v23) = 22;
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
0x14006bc6c  mov     [rsp+arg_10], rbx
0x14006bc71  mov     [rsp+arg_0], rcx
0x14006bc76  push    rbp
0x14006bc77  push    rsi
0x14006bc78  push    rdi
0x14006bc79  push    r12
0x14006bc7b  push    r13
0x14006bc7d  push    r14
0x14006bc7f  push    r15
0x14006bc81  sub     rsp, 0A0h
0x14006bc88  mov     r12, [rdx]
0x14006bc8b  xor     r13d, r13d
0x14006bc8e  movzx   esi, r9b
0x14006bc92  mov     r15d, r8d
0x14006bc95  mov     [rsp+0D8h+var_48], r12
0x14006bc9d  mov     rdi, rdx
0x14006bca0  test    r12, r12
0x14006bca3  jnz     short loc_14006BCB7
0x14006bca5  call    sub_1400616B4
0x14006bcaa  mov     dword ptr [rax], 16h
0x14006bcb0  call    _invalid_parameter_noinfo
0x14006bcb5  jmp     short loc_14006BCE9
0x14006bcb7  test    r15d, r15d
0x14006bcba  jz      short loc_14006BD01
0x14006bcbc  lea     eax, [r8-2]
0x14006bcc0  cmp     eax, 22h ; '"'
0x14006bcc3  jbe     short loc_14006BD01
0x14006bcc5  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x14006bcca  xor     r9d, r9d; LineNo
0x14006bccd  mov     byte ptr [rcx+30h], 1
0x14006bcd1  xor     r8d, r8d; FileName
0x14006bcd4  mov     dword ptr [rcx+2Ch], 16h
0x14006bcdb  xor     edx, edx; FunctionName
0x14006bcdd  xor     ecx, ecx; Expression
0x14006bcdf  mov     [rsp+0D8h+var_B8], r13; uintptr_t
0x14006bce4  call    sub_14006147C
0x14006bce9  mov     rcx, [rdi+8]; this
0x14006bced  test    rcx, rcx
0x14006bcf0  jz      loc_14006C364
0x14006bcf6  mov     rax, [rdi]
0x14006bcf9  mov     [rcx], rax
0x14006bcfc  jmp     loc_14006C364
0x14006bd01  movzx   ebx, word ptr [r12]
0x14006bd06  lea     rax, [r12+2]
0x14006bd0b  mov     [rdx], rax
0x14006bd0e  mov     ebp, r13d
0x14006bd11  cmp     [rcx+28h], r13b
0x14006bd15  jnz     short loc_14006BD2B
0x14006bd17  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14006bd1c  jmp     short loc_14006BD2B
0x14006bd1e  mov     rax, [rdi]
0x14006bd21  movzx   ebx, word ptr [rax]
0x14006bd24  add     rax, 2
0x14006bd28  mov     [rdi], rax
0x14006bd2b  mov     edx, 8; Type
0x14006bd30  movzx   ecx, bx; C
0x14006bd33  call    iswctype
0x14006bd38  test    eax, eax
0x14006bd3a  jnz     short loc_14006BD1E
0x14006bd3c  mov     eax, esi
0x14006bd3e  mov     ecx, 0FFFDh
0x14006bd43  or      esi, 2
0x14006bd46  cmp     bx, 2Dh ; '-'
0x14006bd4a  cmovnz  esi, eax
0x14006bd4d  lea     eax, [rbx-2Bh]
0x14006bd50  test    cx, ax
0x14006bd53  jnz     short loc_14006BD62
0x14006bd55  mov     rax, [rdi]
0x14006bd58  movzx   ebx, word ptr [rax]
0x14006bd5b  add     rax, 2
0x14006bd5f  mov     [rdi], rax
0x14006bd62  mov     [rsp+0D8h+arg_8], 0A70h
0x14006bd6d  mov     eax, 0A66h
0x14006bd72  mov     [rsp+0D8h+var_A8], 0AE6h
0x14006bd7a  mov     ecx, 30h ; '0'
0x14006bd7f  mov     [rsp+0D8h+var_A4], 0AF0h
0x14006bd87  mov     edx, 0FF10h
0x14006bd8c  mov     [rsp+0D8h+var_A0], 0B66h
0x14006bd94  mov     r8d, 660h
0x14006bd9a  mov     [rsp+0D8h+var_9C], 0B70h
0x14006bda2  lea     r10d, [rax-80h]
0x14006bda6  mov     [rsp+0D8h+var_98], 0C66h
0x14006bdae  mov     r11d, 6F0h
0x14006bdb4  mov     [rsp+0D8h+var_94], 0C70h
0x14006bdbc  mov     r9d, 966h
0x14006bdc2  mov     [rsp+0D8h+var_90], 0CE6h
0x14006bdca  mov     [rsp+0D8h+var_8C], 0CF0h
0x14006bdd2  mov     [rsp+0D8h+var_88], 0D66h
0x14006bdda  mov     [rsp+0D8h+var_84], 0D70h
0x14006bde2  mov     [rsp+0D8h+var_80], 0E50h
0x14006bdea  mov     [rsp+0D8h+var_7C], 0E5Ah
0x14006bdf2  mov     [rsp+0D8h+var_78], 0ED0h
0x14006bdfa  mov     [rsp+0D8h+var_74], 0EDAh
0x14006be02  mov     [rsp+0D8h+var_70], 0F20h
0x14006be0a  mov     [rsp+0D8h+var_6C], 0F2Ah
0x14006be12  mov     [rsp+0D8h+var_68], 1040h
0x14006be1a  mov     [rsp+0D8h+var_64], 104Ah
0x14006be22  mov     [rsp+0D8h+var_60], 17E0h
0x14006be2a  mov     [rsp+0D8h+var_5C], 17EAh
0x14006be32  mov     [rsp+0D8h+var_58], 1810h
0x14006be3d  mov     [rsp+0D8h+var_54], 0FF1Ah
0x14006be48  mov     [rsp+0D8h+var_50], 19h
0x14006be53  test    r15d, 0FFFFFFEFh
0x14006be5a  jnz     loc_14006C0D9
0x14006be60  cmp     bx, cx
0x14006be63  jb      loc_14006C02A
0x14006be69  cmp     bx, 3Ah ; ':'
0x14006be6d  jnb     short loc_14006BE79
0x14006be6f  movzx   eax, bx
0x14006be72  sub     eax, ecx
0x14006be74  jmp     loc_14006C025
0x14006be79  cmp     bx, dx
0x14006be7c  jnb     loc_14006C016
0x14006be82  cmp     bx, r8w
0x14006be86  jb      loc_14006C02A
0x14006be8c  mov     ecx, 66Ah
0x14006be91  cmp     bx, cx
0x14006be94  jnb     short loc_14006BEA1
0x14006be96  movzx   eax, bx
0x14006be99  sub     eax, r8d
0x14006be9c  jmp     loc_14006C025
0x14006bea1  cmp     bx, r11w
0x14006bea5  jb      loc_14006C02A
0x14006beab  mov     ecx, 6FAh
0x14006beb0  cmp     bx, cx
0x14006beb3  jnb     short loc_14006BEC0
0x14006beb5  movzx   eax, bx
0x14006beb8  sub     eax, r11d
0x14006bebb  jmp     loc_14006C025
0x14006bec0  cmp     bx, r9w
0x14006bec4  jb      loc_14006C02A
0x14006beca  mov     ecx, 970h
0x14006becf  cmp     bx, cx
0x14006bed2  jnb     short loc_14006BEDF
0x14006bed4  movzx   eax, bx
0x14006bed7  sub     eax, r9d
0x14006beda  jmp     loc_14006C025
0x14006bedf  cmp     bx, r10w
0x14006bee3  jb      loc_14006C02A
0x14006bee9  mov     ecx, 9F0h
0x14006beee  cmp     bx, cx
0x14006bef1  jnb     short loc_14006BEFE
0x14006bef3  movzx   eax, bx
0x14006bef6  sub     eax, r10d
0x14006bef9  jmp     loc_14006C025
0x14006befe  cmp     bx, ax
0x14006bf01  jb      loc_14006C02A
0x14006bf07  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x14006bf0f  jnb     short loc_14006BF1E
0x14006bf11  movzx   eax, bx
0x14006bf14  sub     eax, 0A66h
0x14006bf19  jmp     loc_14006C025
0x14006bf1e  mov     ecx, [rsp+0D8h+var_A8]
0x14006bf22  cmp     bx, cx
0x14006bf25  jb      loc_14006C02A
0x14006bf2b  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x14006bf30  jb      loc_14006BE6F
0x14006bf36  mov     ecx, [rsp+0D8h+var_A0]
0x14006bf3a  cmp     bx, cx
0x14006bf3d  jb      loc_14006C02A
0x14006bf43  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x14006bf48  jb      loc_14006BE6F
0x14006bf4e  mov     ecx, [rsp+0D8h+var_98]
0x14006bf52  cmp     bx, cx
0x14006bf55  jb      loc_14006C02A
0x14006bf5b  cmp     bx, word ptr [rsp+0D8h+var_94]
0x14006bf60  jb      loc_14006BE6F
0x14006bf66  mov     ecx, [rsp+0D8h+var_90]
0x14006bf6a  cmp     bx, cx
0x14006bf6d  jb      loc_14006C02A
0x14006bf73  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x14006bf78  jb      loc_14006BE6F
0x14006bf7e  mov     ecx, [rsp+0D8h+var_88]
0x14006bf82  cmp     bx, cx
0x14006bf85  jb      loc_14006C02A
0x14006bf8b  cmp     bx, word ptr [rsp+0D8h+var_84]
0x14006bf90  jb      loc_14006BE6F
0x14006bf96  mov     ecx, [rsp+0D8h+var_80]
0x14006bf9a  cmp     bx, cx
0x14006bf9d  jb      loc_14006C02A
0x14006bfa3  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x14006bfa8  jb      loc_14006BE6F
0x14006bfae  mov     ecx, [rsp+0D8h+var_78]
0x14006bfb2  cmp     bx, cx
0x14006bfb5  jb      short loc_14006C02A
0x14006bfb7  cmp     bx, word ptr [rsp+0D8h+var_74]
0x14006bfbc  jb      loc_14006BE6F
0x14006bfc2  mov     ecx, [rsp+0D8h+var_70]
0x14006bfc6  cmp     bx, cx
0x14006bfc9  jb      short loc_14006C02A
0x14006bfcb  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x14006bfd0  jb      loc_14006BE6F
0x14006bfd6  mov     ecx, [rsp+0D8h+var_68]
0x14006bfda  cmp     bx, cx
0x14006bfdd  jb      short loc_14006C02A
0x14006bfdf  cmp     bx, word ptr [rsp+0D8h+var_64]
0x14006bfe4  jb      loc_14006BE6F
0x14006bfea  mov     ecx, [rsp+0D8h+var_60]
0x14006bfee  cmp     bx, cx
0x14006bff1  jb      short loc_14006C02A
0x14006bff3  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x14006bff8  jb      loc_14006BE6F
0x14006bffe  mov     ecx, [rsp+0D8h+var_58]
0x14006c005  movzx   eax, bx
0x14006c008  sub     ax, cx
0x14006c00b  cmp     ax, 9
0x14006c00f  ja      short loc_14006C02A
0x14006c011  jmp     loc_14006BE6F
0x14006c016  cmp     bx, word ptr [rsp+0D8h+var_54]
0x14006c01e  jnb     short loc_14006C02A
0x14006c020  movzx   eax, bx
0x14006c023  sub     eax, edx
0x14006c025  cmp     eax, 0FFFFFFFFh
0x14006c028  jnz     short loc_14006C050
0x14006c02a  mov     edx, [rsp+0D8h+var_50]
0x14006c031  movzx   ecx, bx
0x14006c034  lea     eax, [rcx-41h]
0x14006c037  cmp     eax, edx
0x14006c039  lea     eax, [rcx-61h]
0x14006c03c  jbe     short loc_14006C046
0x14006c03e  cmp     eax, edx
0x14006c040  ja      loc_14006C0CA
0x14006c046  cmp     eax, edx
0x14006c048  ja      short loc_14006C04D
0x14006c04a  add     ecx, 0FFFFFFE0h
0x14006c04d  lea     eax, [rcx-37h]
0x14006c050  test    eax, eax
0x14006c052  jnz     short loc_14006C0CA
0x14006c054  mov     rcx, [rdi]
0x14006c057  mov     r9d, 0FFDFh
0x14006c05d  movzx   edx, word ptr [rcx]
0x14006c060  lea     r8, [rcx+2]
0x14006c064  mov     [rdi], r8
0x14006c067  lea     eax, [rdx-58h]
0x14006c06a  test    r9w, ax
0x14006c06e  jz      short loc_14006C0B2
0x14006c070  test    r15d, r15d
0x14006c073  mov     [rdi], rcx
0x14006c076  mov     eax, 8
0x14006c07b  cmovnz  eax, r15d
0x14006c07f  mov     r15d, eax
0x14006c082  test    dx, dx
0x14006c085  jz      short loc_14006C0AA
0x14006c087  cmp     [rcx], dx
0x14006c08a  jz      short loc_14006C0AA
0x14006c08c  call    sub_1400616B4
0x14006c091  mov     dword ptr [rax], 16h
0x14006c097  call    _invalid_parameter_noinfo
0x14006c09c  mov     r8d, 660h
0x14006c0a2  mov     r11d, 6F0h
0x14006c0a8  jmp     short loc_14006C0D9
0x14006c0aa  mov     r8d, 660h
0x14006c0b0  jmp     short loc_14006C0D9
0x14006c0b2  movzx   ebx, word ptr [r8]
0x14006c0b6  lea     rax, [r8+2]
0x14006c0ba  mov     [rdi], rax
0x14006c0bd  mov     r8d, 660h
0x14006c0c3  mov     eax, 10h
0x14006c0c8  jmp     short loc_14006C0CF
0x14006c0ca  mov     eax, 0Ah
0x14006c0cf  test    r15d, r15d
0x14006c0d2  cmovnz  eax, r15d
0x14006c0d6  mov     r15d, eax
0x14006c0d9  xor     edx, edx
0x14006c0db  or      eax, 0FFFFFFFFh
0x14006c0de  div     r15d
0x14006c0e1  mov     r10d, 61h ; 'a'
0x14006c0e7  mov     r14d, 0FF10h
0x14006c0ed  mov     r9d, eax
0x14006c0f0  lea     r12d, [r10-31h]
0x14006c0f4  cmp     bx, r12w
0x14006c0f8  jb      loc_14006C2A6
0x14006c0fe  cmp     bx, 3Ah ; ':'
0x14006c102  jnb     short loc_14006C10F
0x14006c104  movzx   ecx, bx
0x14006c107  sub     ecx, r12d
0x14006c10a  jmp     loc_14006C2A1
0x14006c10f  cmp     bx, r14w
0x14006c113  jnb     loc_14006C291
0x14006c119  cmp     bx, r8w
0x14006c11d  jb      loc_14006C2A6
0x14006c123  mov     eax, 66Ah
0x14006c128  cmp     bx, ax
0x14006c12b  jnb     short loc_14006C138
0x14006c12d  movzx   ecx, bx
0x14006c130  sub     ecx, r8d
0x14006c133  jmp     loc_14006C2A1
0x14006c138  cmp     bx, r11w
0x14006c13c  jb      loc_14006C2A6
0x14006c142  mov     eax, 6FAh
0x14006c147  cmp     bx, ax
0x14006c14a  jnb     short loc_14006C157
0x14006c14c  movzx   ecx, bx
0x14006c14f  sub     ecx, r11d
0x14006c152  jmp     loc_14006C2A1
0x14006c157  mov     eax, 966h
0x14006c15c  cmp     bx, ax
0x14006c15f  jb      loc_14006C2A6
0x14006c165  lea     ecx, [rax+0Ah]
0x14006c168  cmp     bx, cx
  ... truncated ...
```

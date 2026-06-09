# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<wchar_t>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x140010af0`
- end: `0x140011271`
- name: `??$parse_integer@_KV?$c_string_character_source@_W@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1921`
- prototype: `unsigned __int64 __fastcall(__crt_cached_ptd_host *, wint_t **, signed int, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140011328`

## callees

- `0x140004614`
- `0x1400046cc`
- `0x140004a54`
- `0x14000ad70`
- `0x14000fa6c`
- `0x140010524`
- `0x140010af0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // r10
  __int64 v24; // rcx
  int v25; // eax
  int v26; // ecx
  wint_t *v27; // r8
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
    *(_DWORD *)sub_14000FA6C(a1, a2) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_140004614(0, 0, 0, 0, 0, a1);
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
    *(_DWORD *)((__int64 (*)(void))sub_14000FA6C)() = 22;
    invalid_parameter_noinfo();
  }
LABEL_79:
  v22 = 0xFFFFFFFFFFFFFFFFuLL % v6;
  v23 = 0xFFFFFFFFFFFFFFFFuLL / v6;
  while ( 1 )
  {
    if ( v9 >= 0x30u )
    {
      if ( v9 < 0x3Au )
      {
        v24 = (unsigned int)v9 - 48;
        goto LABEL_120;
      }
      if ( v9 >= 0xFF10u )
      {
        if ( v9 < 0xFF1Au )
        {
          v24 = (unsigned int)v9 - 65296;
LABEL_120:
          if ( (_DWORD)v24 != -1 )
            goto LABEL_129;
        }
      }
      else if ( v9 >= 0x660u )
      {
        if ( v9 < 0x66Au )
        {
          v24 = (unsigned int)v9 - 1632;
          goto LABEL_120;
        }
        v25 = 1776;
        if ( v9 >= 0x6F0u )
        {
          if ( v9 < 0x6FAu )
            goto LABEL_89;
          v25 = 2406;
          if ( v9 >= 0x966u )
          {
            if ( v9 < 0x970u )
              goto LABEL_89;
            v25 = 2534;
            if ( v9 >= 0x9E6u )
            {
              if ( v9 < 0x9F0u )
                goto LABEL_89;
              v25 = 2662;
              if ( v9 >= 0xA66u )
              {
                if ( v9 < 0xA70u )
                  goto LABEL_89;
                v25 = 2790;
                if ( v9 >= 0xAE6u )
                {
                  if ( v9 < 0xAF0u )
                    goto LABEL_89;
                  v25 = 2918;
                  if ( v9 >= 0xB66u )
                  {
                    if ( v9 < 0xB70u )
                      goto LABEL_89;
                    v25 = 3174;
                    if ( v9 >= 0xC66u )
                    {
                      if ( v9 < 0xC70u )
                        goto LABEL_89;
                      v25 = 3302;
                      if ( v9 >= 0xCE6u )
                      {
                        if ( v9 < 0xCF0u )
                          goto LABEL_89;
                        v25 = 3430;
                        if ( v9 >= 0xD66u )
                        {
                          if ( v9 < 0xD70u )
                            goto LABEL_89;
                          v25 = 3664;
                          if ( v9 >= 0xE50u )
                          {
                            if ( v9 < 0xE5Au )
                              goto LABEL_89;
                            v25 = 3792;
                            if ( v9 >= 0xED0u )
                            {
                              if ( v9 < 0xEDAu )
                                goto LABEL_89;
                              v25 = 3872;
                              if ( v9 >= 0xF20u )
                              {
                                if ( v9 < 0xF2Au )
                                  goto LABEL_89;
                                v25 = 4160;
                                if ( v9 >= 0x1040u )
                                {
                                  if ( v9 < 0x104Au )
                                    goto LABEL_89;
                                  v25 = 6112;
                                  if ( v9 >= 0x17E0u )
                                  {
                                    if ( v9 < 0x17EAu )
                                    {
LABEL_89:
                                      v24 = (unsigned int)v9 - v25;
                                      goto LABEL_120;
                                    }
                                    v22 = 6160;
                                    if ( (unsigned __int16)(v9 - 6160) <= 9u )
                                    {
                                      v24 = (unsigned int)v9 - 6160;
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
LABEL_129:
    v27 = *a2;
    if ( (unsigned int)v24 >= v6 )
      break;
    v9 = *v27;
    v22 = v10 * v6 + (unsigned int)v24;
    v28 = v22 < v10 * v6;
    v29 = v10 < v23;
    v30 = v10 == v23;
    v10 = v22;
    *a2 = v27 + 1;
    v12 |= (4 * (!v29 && !v30 || v28)) | 8;
  }
  *a2 = v27 - 1;
  if ( v9 && *(v27 - 1) != v9 )
  {
    *(_DWORD *)sub_14000FA6C(v24, v22) = 22;
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
0x140010af0  mov     [rsp+arg_10], rbx
0x140010af5  mov     [rsp+arg_0], rcx
0x140010afa  push    rbp
0x140010afb  push    rsi
0x140010afc  push    rdi
0x140010afd  push    r12
0x140010aff  push    r13
0x140010b01  push    r14
0x140010b03  push    r15
0x140010b05  sub     rsp, 0A0h
0x140010b0c  mov     r12, [rdx]
0x140010b0f  xor     r13d, r13d
0x140010b12  movzx   esi, r9b
0x140010b16  mov     r15d, r8d
0x140010b19  mov     [rsp+0D8h+var_48], r12
0x140010b21  mov     rdi, rdx
0x140010b24  test    r12, r12
0x140010b27  jnz     short loc_140010B3B
0x140010b29  call    sub_14000FA6C
0x140010b2e  mov     dword ptr [rax], 16h
0x140010b34  call    _invalid_parameter_noinfo
0x140010b39  jmp     short loc_140010B6D
0x140010b3b  test    r15d, r15d
0x140010b3e  jz      short loc_140010B85
0x140010b40  lea     eax, [r8-2]
0x140010b44  cmp     eax, 22h ; '"'
0x140010b47  jbe     short loc_140010B85
0x140010b49  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x140010b4e  xor     r9d, r9d; LineNo
0x140010b51  mov     byte ptr [rcx+30h], 1
0x140010b55  xor     r8d, r8d; FileName
0x140010b58  mov     dword ptr [rcx+2Ch], 16h
0x140010b5f  xor     edx, edx; FunctionName
0x140010b61  xor     ecx, ecx; Expression
0x140010b63  mov     [rsp+0D8h+var_B8], r13; uintptr_t
0x140010b68  call    sub_140004614
0x140010b6d  mov     rcx, [rdi+8]; this
0x140010b71  test    rcx, rcx
0x140010b74  jz      loc_1400111D8
0x140010b7a  mov     rax, [rdi]
0x140010b7d  mov     [rcx], rax
0x140010b80  jmp     loc_1400111D8
0x140010b85  movzx   ebx, word ptr [r12]
0x140010b8a  lea     rax, [r12+2]
0x140010b8f  mov     [rdx], rax
0x140010b92  mov     rbp, r13
0x140010b95  cmp     [rcx+28h], r13b
0x140010b99  jnz     short loc_140010BAF
0x140010b9b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140010ba0  jmp     short loc_140010BAF
0x140010ba2  mov     rax, [rdi]
0x140010ba5  movzx   ebx, word ptr [rax]
0x140010ba8  add     rax, 2
0x140010bac  mov     [rdi], rax
0x140010baf  mov     edx, 8; Type
0x140010bb4  movzx   ecx, bx; C
0x140010bb7  call    iswctype
0x140010bbc  test    eax, eax
0x140010bbe  jnz     short loc_140010BA2
0x140010bc0  mov     eax, esi
0x140010bc2  mov     ecx, 0FFFDh
0x140010bc7  or      esi, 2
0x140010bca  cmp     bx, 2Dh ; '-'
0x140010bce  cmovnz  esi, eax
0x140010bd1  lea     eax, [rbx-2Bh]
0x140010bd4  test    cx, ax
0x140010bd7  jnz     short loc_140010BE6
0x140010bd9  mov     rax, [rdi]
0x140010bdc  movzx   ebx, word ptr [rax]
0x140010bdf  add     rax, 2
0x140010be3  mov     [rdi], rax
0x140010be6  mov     [rsp+0D8h+arg_8], 0A70h
0x140010bf1  mov     eax, 0A66h
0x140010bf6  mov     [rsp+0D8h+var_A8], 0AE6h
0x140010bfe  mov     ecx, 30h ; '0'
0x140010c03  mov     [rsp+0D8h+var_A4], 0AF0h
0x140010c0b  mov     edx, 0FF10h
0x140010c10  mov     [rsp+0D8h+var_A0], 0B66h
0x140010c18  mov     r8d, 660h
0x140010c1e  mov     [rsp+0D8h+var_9C], 0B70h
0x140010c26  lea     r11d, [rax-80h]
0x140010c2a  mov     [rsp+0D8h+var_98], 0C66h
0x140010c32  mov     r9d, 6F0h
0x140010c38  mov     [rsp+0D8h+var_94], 0C70h
0x140010c40  mov     r10d, 966h
0x140010c46  mov     [rsp+0D8h+var_90], 0CE6h
0x140010c4e  mov     [rsp+0D8h+var_8C], 0CF0h
0x140010c56  mov     [rsp+0D8h+var_88], 0D66h
0x140010c5e  mov     [rsp+0D8h+var_84], 0D70h
0x140010c66  mov     [rsp+0D8h+var_80], 0E50h
0x140010c6e  mov     [rsp+0D8h+var_7C], 0E5Ah
0x140010c76  mov     [rsp+0D8h+var_78], 0ED0h
0x140010c7e  mov     [rsp+0D8h+var_74], 0EDAh
0x140010c86  mov     [rsp+0D8h+var_70], 0F20h
0x140010c8e  mov     [rsp+0D8h+var_6C], 0F2Ah
0x140010c96  mov     [rsp+0D8h+var_68], 1040h
0x140010c9e  mov     [rsp+0D8h+var_64], 104Ah
0x140010ca6  mov     [rsp+0D8h+var_60], 17E0h
0x140010cae  mov     [rsp+0D8h+var_5C], 17EAh
0x140010cb6  mov     [rsp+0D8h+var_58], 1810h
0x140010cc1  mov     [rsp+0D8h+var_54], 0FF1Ah
0x140010ccc  mov     [rsp+0D8h+var_50], 19h
0x140010cd7  test    r15d, 0FFFFFFEFh
0x140010cde  jnz     loc_140010F4B
0x140010ce4  cmp     bx, cx
0x140010ce7  jb      loc_140010EAE
0x140010ced  cmp     bx, 3Ah ; ':'
0x140010cf1  jnb     short loc_140010CFD
0x140010cf3  movzx   eax, bx
0x140010cf6  sub     eax, ecx
0x140010cf8  jmp     loc_140010EA9
0x140010cfd  cmp     bx, dx
0x140010d00  jnb     loc_140010E9A
0x140010d06  cmp     bx, r8w
0x140010d0a  jb      loc_140010EAE
0x140010d10  mov     ecx, 66Ah
0x140010d15  cmp     bx, cx
0x140010d18  jnb     short loc_140010D25
0x140010d1a  movzx   eax, bx
0x140010d1d  sub     eax, r8d
0x140010d20  jmp     loc_140010EA9
0x140010d25  cmp     bx, r9w
0x140010d29  jb      loc_140010EAE
0x140010d2f  mov     ecx, 6FAh
0x140010d34  cmp     bx, cx
0x140010d37  jnb     short loc_140010D44
0x140010d39  movzx   eax, bx
0x140010d3c  sub     eax, r9d
0x140010d3f  jmp     loc_140010EA9
0x140010d44  cmp     bx, r10w
0x140010d48  jb      loc_140010EAE
0x140010d4e  mov     ecx, 970h
0x140010d53  cmp     bx, cx
0x140010d56  jnb     short loc_140010D63
0x140010d58  movzx   eax, bx
0x140010d5b  sub     eax, r10d
0x140010d5e  jmp     loc_140010EA9
0x140010d63  cmp     bx, r11w
0x140010d67  jb      loc_140010EAE
0x140010d6d  mov     ecx, 9F0h
0x140010d72  cmp     bx, cx
0x140010d75  jnb     short loc_140010D82
0x140010d77  movzx   eax, bx
0x140010d7a  sub     eax, r11d
0x140010d7d  jmp     loc_140010EA9
0x140010d82  cmp     bx, ax
0x140010d85  jb      loc_140010EAE
0x140010d8b  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x140010d93  jnb     short loc_140010DA2
0x140010d95  movzx   eax, bx
0x140010d98  sub     eax, 0A66h
0x140010d9d  jmp     loc_140010EA9
0x140010da2  mov     ecx, [rsp+0D8h+var_A8]
0x140010da6  cmp     bx, cx
0x140010da9  jb      loc_140010EAE
0x140010daf  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x140010db4  jb      loc_140010CF3
0x140010dba  mov     ecx, [rsp+0D8h+var_A0]
0x140010dbe  cmp     bx, cx
0x140010dc1  jb      loc_140010EAE
0x140010dc7  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x140010dcc  jb      loc_140010CF3
0x140010dd2  mov     ecx, [rsp+0D8h+var_98]
0x140010dd6  cmp     bx, cx
0x140010dd9  jb      loc_140010EAE
0x140010ddf  cmp     bx, word ptr [rsp+0D8h+var_94]
0x140010de4  jb      loc_140010CF3
0x140010dea  mov     ecx, [rsp+0D8h+var_90]
0x140010dee  cmp     bx, cx
0x140010df1  jb      loc_140010EAE
0x140010df7  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x140010dfc  jb      loc_140010CF3
0x140010e02  mov     ecx, [rsp+0D8h+var_88]
0x140010e06  cmp     bx, cx
0x140010e09  jb      loc_140010EAE
0x140010e0f  cmp     bx, word ptr [rsp+0D8h+var_84]
0x140010e14  jb      loc_140010CF3
0x140010e1a  mov     ecx, [rsp+0D8h+var_80]
0x140010e1e  cmp     bx, cx
0x140010e21  jb      loc_140010EAE
0x140010e27  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x140010e2c  jb      loc_140010CF3
0x140010e32  mov     ecx, [rsp+0D8h+var_78]
0x140010e36  cmp     bx, cx
0x140010e39  jb      short loc_140010EAE
0x140010e3b  cmp     bx, word ptr [rsp+0D8h+var_74]
0x140010e40  jb      loc_140010CF3
0x140010e46  mov     ecx, [rsp+0D8h+var_70]
0x140010e4a  cmp     bx, cx
0x140010e4d  jb      short loc_140010EAE
0x140010e4f  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x140010e54  jb      loc_140010CF3
0x140010e5a  mov     ecx, [rsp+0D8h+var_68]
0x140010e5e  cmp     bx, cx
0x140010e61  jb      short loc_140010EAE
0x140010e63  cmp     bx, word ptr [rsp+0D8h+var_64]
0x140010e68  jb      loc_140010CF3
0x140010e6e  mov     ecx, [rsp+0D8h+var_60]
0x140010e72  cmp     bx, cx
0x140010e75  jb      short loc_140010EAE
0x140010e77  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x140010e7c  jb      loc_140010CF3
0x140010e82  mov     ecx, [rsp+0D8h+var_58]
0x140010e89  movzx   eax, bx
0x140010e8c  sub     ax, cx
0x140010e8f  cmp     ax, 9
0x140010e93  ja      short loc_140010EAE
0x140010e95  jmp     loc_140010CF3
0x140010e9a  cmp     bx, word ptr [rsp+0D8h+var_54]
0x140010ea2  jnb     short loc_140010EAE
0x140010ea4  movzx   eax, bx
0x140010ea7  sub     eax, edx
0x140010ea9  cmp     eax, 0FFFFFFFFh
0x140010eac  jnz     short loc_140010ED0
0x140010eae  mov     edx, [rsp+0D8h+var_50]
0x140010eb5  movzx   ecx, bx
0x140010eb8  lea     eax, [rcx-41h]
0x140010ebb  cmp     eax, edx
0x140010ebd  lea     eax, [rcx-61h]
0x140010ec0  jbe     short loc_140010EC6
0x140010ec2  cmp     eax, edx
0x140010ec4  ja      short loc_140010F3C
0x140010ec6  cmp     eax, edx
0x140010ec8  ja      short loc_140010ECD
0x140010eca  add     ecx, 0FFFFFFE0h
0x140010ecd  lea     eax, [rcx-37h]
0x140010ed0  test    eax, eax
0x140010ed2  jnz     short loc_140010F3C
0x140010ed4  mov     rcx, [rdi]
0x140010ed7  mov     r9d, 0FFDFh
0x140010edd  movzx   edx, word ptr [rcx]
0x140010ee0  lea     r8, [rcx+2]
0x140010ee4  mov     [rdi], r8
0x140010ee7  lea     eax, [rdx-58h]
0x140010eea  test    r9w, ax
0x140010eee  jz      short loc_140010F24
0x140010ef0  test    r15d, r15d
0x140010ef3  mov     [rdi], rcx
0x140010ef6  mov     eax, 8
0x140010efb  cmovnz  eax, r15d
0x140010eff  mov     r15d, eax
0x140010f02  test    dx, dx
0x140010f05  jz      short loc_140010F1C
0x140010f07  cmp     [rcx], dx
0x140010f0a  jz      short loc_140010F1C
0x140010f0c  call    sub_14000FA6C
0x140010f11  mov     dword ptr [rax], 16h
0x140010f17  call    _invalid_parameter_noinfo
0x140010f1c  mov     r8d, 660h
0x140010f22  jmp     short loc_140010F4B
0x140010f24  movzx   ebx, word ptr [r8]
0x140010f28  lea     rax, [r8+2]
0x140010f2c  mov     [rdi], rax
0x140010f2f  mov     r8d, 660h
0x140010f35  mov     eax, 10h
0x140010f3a  jmp     short loc_140010F41
0x140010f3c  mov     eax, 0Ah
0x140010f41  test    r15d, r15d
0x140010f44  cmovnz  eax, r15d
0x140010f48  mov     r15d, eax
0x140010f4b  movsxd  r9, r15d
0x140010f4e  xor     edx, edx
0x140010f50  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010f54  mov     r11d, 61h ; 'a'
0x140010f5a  div     r9
0x140010f5d  lea     r12d, [r11-31h]
0x140010f61  mov     r14d, 0FF10h
0x140010f67  mov     r10, rax
0x140010f6a  cmp     bx, r12w
0x140010f6e  jb      loc_140011115
0x140010f74  cmp     bx, 3Ah ; ':'
0x140010f78  jnb     short loc_140010F85
0x140010f7a  movzx   ecx, bx
0x140010f7d  sub     ecx, r12d
0x140010f80  jmp     loc_140011110
0x140010f85  cmp     bx, r14w
0x140010f89  jnb     loc_140011100
0x140010f8f  cmp     bx, r8w
0x140010f93  jb      loc_140011115
0x140010f99  mov     eax, 66Ah
0x140010f9e  cmp     bx, ax
0x140010fa1  jnb     short loc_140010FAE
0x140010fa3  movzx   ecx, bx
0x140010fa6  sub     ecx, r8d
0x140010fa9  jmp     loc_140011110
0x140010fae  mov     eax, 6F0h
0x140010fb3  cmp     bx, ax
0x140010fb6  jb      loc_140011115
0x140010fbc  lea     ecx, [rax+0Ah]
0x140010fbf  cmp     bx, cx
0x140010fc2  jnb     short loc_140010FCE
0x140010fc4  movzx   ecx, bx
0x140010fc7  sub     ecx, eax
0x140010fc9  jmp     loc_140011110
0x140010fce  mov     eax, 966h
0x140010fd3  cmp     bx, ax
0x140010fd6  jb      loc_140011115
0x140010fdc  lea     ecx, [rax+0Ah]
0x140010fdf  cmp     bx, cx
0x140010fe2  jb      short loc_140010FC4
  ... truncated ...
```

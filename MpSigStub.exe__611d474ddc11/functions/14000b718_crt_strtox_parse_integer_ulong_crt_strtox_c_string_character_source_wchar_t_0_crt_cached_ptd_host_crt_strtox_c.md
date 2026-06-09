# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x14000b718`
- end: `0x14000be8d`
- name: `??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1909`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, unsigned __int16 **, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d2d0`

## callees

- `0x140004614`
- `0x1400046cc`
- `0x14000b718`
- `0x14000fa6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<wchar_t>,0>(
        __crt_cached_ptd_host *a1,
        unsigned __int16 **a2,
        unsigned int a3,
        unsigned __int8 a4)
{
  unsigned __int16 *v4; // r12
  unsigned int v5; // r15d
  unsigned __int16 *v7; // rcx
  unsigned __int16 v8; // bx
  unsigned int v9; // r14d
  int v10; // esi
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // eax
  unsigned __int16 *v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // r8
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // r9d
  __int64 v22; // rcx
  int v23; // eax
  int v24; // ecx
  unsigned __int16 *v25; // r8
  BOOL v26; // ecx
  bool v27; // cf
  bool v28; // zf
  unsigned __int16 *v29; // rax
  int v31; // eax
  int v32; // ecx
  unsigned __int16 *v33; // rdx
  unsigned __int16 *v34; // rdx
  unsigned __int16 *v35; // [rsp+98h] [rbp-40h]

  v4 = *a2;
  v35 = *a2;
  v5 = a3;
  if ( !*a2 )
  {
    *(_DWORD *)sub_14000FA6C(a1, a2) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && a3 - 2 > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_140004614(0, 0, 0, 0, 0, a1);
LABEL_6:
    v7 = a2[1];
    if ( v7 )
      *(_QWORD *)v7 = *a2;
    return 0;
  }
  v8 = *v4;
  v9 = 0;
  *a2 = v4 + 1;
  v10 = a4 | 2;
  if ( v8 != 45 )
    v10 = a4;
  if ( ((v8 - 43) & 0xFFFD) == 0 )
  {
    v8 = v4[1];
    *a2 = v4 + 2;
  }
  v11 = 48;
  if ( (a3 & 0xFFFFFFEF) != 0 )
    goto LABEL_73;
  if ( v8 >= 0x30u )
  {
    if ( v8 < 0x3Au )
    {
LABEL_15:
      v12 = v8 - v11;
      goto LABEL_55;
    }
    if ( v8 >= 0xFF10u )
    {
      if ( v8 < 0xFF1Au )
      {
        v12 = v8 - 65296;
LABEL_55:
        if ( v12 != -1 )
          goto LABEL_61;
      }
    }
    else if ( v8 >= 0x660u )
    {
      if ( v8 < 0x66Au )
      {
        v12 = v8 - 1632;
        goto LABEL_55;
      }
      if ( v8 >= 0x6F0u )
      {
        if ( v8 < 0x6FAu )
        {
          v12 = v8 - 1776;
          goto LABEL_55;
        }
        if ( v8 >= 0x966u )
        {
          if ( v8 < 0x970u )
          {
            v12 = v8 - 2406;
            goto LABEL_55;
          }
          if ( v8 >= 0x9E6u )
          {
            if ( v8 < 0x9F0u )
            {
              v12 = v8 - 2534;
              goto LABEL_55;
            }
            v11 = 2662;
            if ( v8 >= 0xA66u )
            {
              if ( v8 < 0xA70u )
                goto LABEL_15;
              v11 = 2790;
              if ( v8 >= 0xAE6u )
              {
                if ( v8 < 0xAF0u )
                  goto LABEL_15;
                v11 = 2918;
                if ( v8 >= 0xB66u )
                {
                  if ( v8 < 0xB70u )
                    goto LABEL_15;
                  v11 = 3174;
                  if ( v8 >= 0xC66u )
                  {
                    if ( v8 < 0xC70u )
                      goto LABEL_15;
                    v11 = 3302;
                    if ( v8 >= 0xCE6u )
                    {
                      if ( v8 < 0xCF0u )
                        goto LABEL_15;
                      v11 = 3430;
                      if ( v8 >= 0xD66u )
                      {
                        if ( v8 < 0xD70u )
                          goto LABEL_15;
                        v11 = 3664;
                        if ( v8 >= 0xE50u )
                        {
                          if ( v8 < 0xE5Au )
                            goto LABEL_15;
                          v11 = 3792;
                          if ( v8 >= 0xED0u )
                          {
                            if ( v8 < 0xEDAu )
                              goto LABEL_15;
                            v11 = 3872;
                            if ( v8 >= 0xF20u )
                            {
                              if ( v8 < 0xF2Au )
                                goto LABEL_15;
                              v11 = 4160;
                              if ( v8 >= 0x1040u )
                              {
                                if ( v8 < 0x104Au )
                                  goto LABEL_15;
                                v11 = 6112;
                                if ( v8 >= 0x17E0u )
                                {
                                  if ( v8 < 0x17EAu )
                                    goto LABEL_15;
                                  v11 = 6160;
                                  if ( (unsigned __int16)(v8 - 6160) <= 9u )
                                    goto LABEL_15;
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
  v13 = v8;
  v14 = v8 - 97;
  if ( (unsigned int)v8 - 65 > 0x19 && v14 > 0x19 )
    goto LABEL_69;
  if ( v14 <= 0x19 )
    v13 = v8 - 32;
  v12 = v13 - 55;
LABEL_61:
  if ( v12 )
  {
LABEL_69:
    v19 = 10;
    goto LABEL_70;
  }
  v15 = *a2;
  v16 = **a2;
  v17 = *a2 + 1;
  *a2 = v17;
  if ( (((_WORD)v16 - 88) & 0xFFDF) == 0 )
  {
    v8 = *v17;
    *a2 = v17 + 1;
    v19 = 16;
LABEL_70:
    if ( v5 )
      v19 = v5;
    v5 = v19;
    goto LABEL_73;
  }
  *a2 = v15;
  v18 = 8;
  if ( v5 )
    v18 = v5;
  v5 = v18;
  if ( (_WORD)v16 && *v15 != (_WORD)v16 )
  {
    *(_DWORD *)sub_14000FA6C(v15, v16) = 22;
    invalid_parameter_noinfo();
  }
LABEL_73:
  v20 = 0xFFFFFFFF % v5;
  v21 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( v8 >= 0x30u )
    {
      if ( v8 < 0x3Au )
      {
        v22 = (unsigned int)v8 - 48;
        goto LABEL_114;
      }
      if ( v8 >= 0xFF10u )
      {
        if ( v8 < 0xFF1Au )
        {
          v22 = (unsigned int)v8 - 65296;
LABEL_114:
          if ( (_DWORD)v22 != -1 )
            goto LABEL_123;
        }
      }
      else if ( v8 >= 0x660u )
      {
        if ( v8 < 0x66Au )
        {
          v22 = (unsigned int)v8 - 1632;
          goto LABEL_114;
        }
        v23 = 1776;
        if ( v8 >= 0x6F0u )
        {
          if ( v8 < 0x6FAu )
            goto LABEL_83;
          v23 = 2406;
          if ( v8 >= 0x966u )
          {
            if ( v8 < 0x970u )
              goto LABEL_83;
            v23 = 2534;
            if ( v8 >= 0x9E6u )
            {
              if ( v8 < 0x9F0u )
                goto LABEL_83;
              v23 = 2662;
              if ( v8 >= 0xA66u )
              {
                if ( v8 < 0xA70u )
                  goto LABEL_83;
                v23 = 2790;
                if ( v8 >= 0xAE6u )
                {
                  if ( v8 < 0xAF0u )
                    goto LABEL_83;
                  v23 = 2918;
                  if ( v8 >= 0xB66u )
                  {
                    if ( v8 < 0xB70u )
                      goto LABEL_83;
                    v23 = 3174;
                    if ( v8 >= 0xC66u )
                    {
                      if ( v8 < 0xC70u )
                        goto LABEL_83;
                      v23 = 3302;
                      if ( v8 >= 0xCE6u )
                      {
                        if ( v8 < 0xCF0u )
                          goto LABEL_83;
                        v23 = 3430;
                        if ( v8 >= 0xD66u )
                        {
                          if ( v8 < 0xD70u )
                            goto LABEL_83;
                          v23 = 3664;
                          if ( v8 >= 0xE50u )
                          {
                            if ( v8 < 0xE5Au )
                              goto LABEL_83;
                            v23 = 3792;
                            if ( v8 >= 0xED0u )
                            {
                              if ( v8 < 0xEDAu )
                                goto LABEL_83;
                              v23 = 3872;
                              if ( v8 >= 0xF20u )
                              {
                                if ( v8 < 0xF2Au )
                                  goto LABEL_83;
                                v23 = 4160;
                                if ( v8 >= 0x1040u )
                                {
                                  if ( v8 < 0x104Au )
                                    goto LABEL_83;
                                  v23 = 6112;
                                  if ( v8 >= 0x17E0u )
                                  {
                                    if ( v8 < 0x17EAu )
                                    {
LABEL_83:
                                      v22 = (unsigned int)v8 - v23;
                                      goto LABEL_114;
                                    }
                                    v20 = 6160;
                                    if ( (unsigned __int16)(v8 - 6160) <= 9u )
                                    {
                                      v22 = (unsigned int)v8 - 6160;
                                      goto LABEL_114;
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
    if ( ((v24 = v8, v8 < 0x41u) || v8 > 0x5Au) && (v8 < 0x61u || v8 > 0x7Au) )
    {
      v22 = 0xFFFFFFFFLL;
    }
    else
    {
      if ( (unsigned __int16)(v8 - 97) <= 0x19u )
        v24 = v8 - 32;
      v22 = (unsigned int)(v24 - 55);
    }
LABEL_123:
    v25 = *a2;
    if ( (unsigned int)v22 >= v5 )
      break;
    v8 = *v25;
    v20 = v5 * v9 + (unsigned int)v22;
    v26 = (unsigned int)v20 < v5 * v9;
    v27 = v9 < v21;
    v28 = v9 == v21;
    v9 = v20;
    *a2 = v25 + 1;
    v10 |= (4 * (!v27 && !v28 || v26)) | 8;
  }
  *a2 = v25 - 1;
  if ( v8 && *(v25 - 1) != v8 )
  {
    *(_DWORD *)sub_14000FA6C(v22, v20) = 22;
    invalid_parameter_noinfo();
  }
  if ( (v10 & 8) != 0 )
  {
    if ( (v10 & 4) != 0 )
    {
      v31 = 1;
      v32 = v10;
LABEL_140:
      *((_BYTE *)a1 + 48) = 1;
      *((_DWORD *)a1 + 11) = 34;
      if ( (v32 & v31) != 0 )
      {
        v33 = a2[1];
        if ( (v10 & 2) != 0 )
        {
          if ( v33 )
            *(_QWORD *)v33 = *a2;
          return 0x80000000LL;
        }
        else
        {
          if ( v33 )
            *(_QWORD *)v33 = *a2;
          return 0x7FFFFFFF;
        }
      }
      v9 = -1;
LABEL_151:
      v34 = a2[1];
      if ( v34 )
        *(_QWORD *)v34 = *a2;
      return v9;
    }
    if ( (v10 & 1) != 0 )
    {
      if ( (v10 & 2) == 0 )
      {
        if ( v9 <= 0x7FFFFFFF )
          goto LABEL_151;
        goto LABEL_139;
      }
      if ( v9 > 0x80000000 )
      {
LABEL_139:
        v32 = 1;
        v31 = v10;
        goto LABEL_140;
      }
    }
    else if ( (v10 & 2) == 0 )
    {
      goto LABEL_151;
    }
    v9 = -v9;
    goto LABEL_151;
  }
  v29 = a2[1];
  *a2 = v35;
  if ( v29 )
    *(_QWORD *)v29 = v35;
  return 0;
}

```

## disassembly

```asm
0x14000b718  mov     [rsp+arg_10], rbx
0x14000b71d  mov     [rsp+arg_0], rcx
0x14000b722  push    rbp
0x14000b723  push    rsi
0x14000b724  push    rdi
0x14000b725  push    r12
0x14000b727  push    r13
0x14000b729  push    r14
0x14000b72b  push    r15
0x14000b72d  sub     rsp, 0A0h
0x14000b734  mov     r12, [rdx]
0x14000b737  xor     r10d, r10d
0x14000b73a  mov     [rsp+0D8h+var_40], r12
0x14000b742  mov     r15d, r8d
0x14000b745  mov     rdi, rdx
0x14000b748  test    r12, r12
0x14000b74b  jnz     short loc_14000B75F
0x14000b74d  call    sub_14000FA6C
0x14000b752  mov     dword ptr [rax], 16h
0x14000b758  call    _invalid_parameter_noinfo
0x14000b75d  jmp     short loc_14000B791
0x14000b75f  test    r15d, r15d
0x14000b762  jz      short loc_14000B7A9
0x14000b764  lea     eax, [r8-2]
0x14000b768  cmp     eax, 22h ; '"'
0x14000b76b  jbe     short loc_14000B7A9
0x14000b76d  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x14000b772  xor     r9d, r9d; LineNo
0x14000b775  mov     byte ptr [rcx+30h], 1
0x14000b779  xor     r8d, r8d; FileName
0x14000b77c  mov     dword ptr [rcx+2Ch], 16h
0x14000b783  xor     edx, edx; FunctionName
0x14000b785  xor     ecx, ecx; Expression
0x14000b787  mov     [rsp+0D8h+var_B8], r10; uintptr_t
0x14000b78c  call    sub_140004614
0x14000b791  mov     rcx, [rdi+8]
0x14000b795  test    rcx, rcx
0x14000b798  jz      loc_14000BDD9
0x14000b79e  mov     rax, [rdi]
0x14000b7a1  mov     [rcx], rax
0x14000b7a4  jmp     loc_14000BDD9
0x14000b7a9  movzx   ebx, word ptr [r12]
0x14000b7ae  lea     rcx, [r12+2]
0x14000b7b3  movzx   eax, r9b
0x14000b7b7  mov     r14d, r10d
0x14000b7ba  mov     esi, eax
0x14000b7bc  mov     [rdx], rcx
0x14000b7bf  or      esi, 2
0x14000b7c2  mov     edx, 0FFFDh
0x14000b7c7  cmp     bx, 2Dh ; '-'
0x14000b7cb  cmovnz  esi, eax
0x14000b7ce  lea     eax, [rbx-2Bh]
0x14000b7d1  test    dx, ax
0x14000b7d4  jnz     short loc_14000B7E0
0x14000b7d6  movzx   ebx, word ptr [rcx]
0x14000b7d9  lea     rax, [rcx+2]
0x14000b7dd  mov     [rdi], rax
0x14000b7e0  mov     [rsp+0D8h+arg_8], 9F0h
0x14000b7eb  mov     eax, 9E6h
0x14000b7f0  mov     [rsp+0D8h+var_A8], 0A66h
0x14000b7f8  mov     ecx, 30h ; '0'
0x14000b7fd  mov     [rsp+0D8h+var_A4], 0A70h
0x14000b805  mov     edx, 0FF10h
0x14000b80a  mov     [rsp+0D8h+var_A0], 0AE6h
0x14000b812  mov     r8d, 660h
0x14000b818  mov     [rsp+0D8h+var_9C], 0AF0h
0x14000b820  lea     r11d, [rax-80h]
0x14000b824  mov     [rsp+0D8h+var_98], 0B66h
0x14000b82c  mov     r9d, 6F0h
0x14000b832  mov     [rsp+0D8h+var_94], 0B70h
0x14000b83a  mov     [rsp+0D8h+var_90], 0C66h
0x14000b842  mov     [rsp+0D8h+var_8C], 0C70h
0x14000b84a  mov     [rsp+0D8h+var_88], 0CE6h
0x14000b852  mov     [rsp+0D8h+var_84], 0CF0h
0x14000b85a  mov     [rsp+0D8h+var_80], 0D66h
0x14000b862  mov     [rsp+0D8h+var_7C], 0D70h
0x14000b86a  mov     [rsp+0D8h+var_78], 0E50h
0x14000b872  mov     [rsp+0D8h+var_74], 0E5Ah
0x14000b87a  mov     [rsp+0D8h+var_70], 0ED0h
0x14000b882  mov     [rsp+0D8h+var_6C], 0EDAh
0x14000b88a  mov     [rsp+0D8h+var_68], 0F20h
0x14000b892  mov     [rsp+0D8h+var_64], 0F2Ah
0x14000b89a  mov     [rsp+0D8h+var_60], 1040h
0x14000b8a2  mov     [rsp+0D8h+var_5C], 104Ah
0x14000b8aa  mov     [rsp+0D8h+var_58], 17E0h
0x14000b8b5  mov     [rsp+0D8h+var_54], 17EAh
0x14000b8c0  mov     [rsp+0D8h+var_50], 1810h
0x14000b8cb  mov     [rsp+0D8h+var_4C], 0FF1Ah
0x14000b8d6  mov     [rsp+0D8h+var_48], 19h
0x14000b8e1  test    r15d, 0FFFFFFEFh
0x14000b8e8  jnz     loc_14000BB4B
0x14000b8ee  cmp     bx, cx
0x14000b8f1  jb      loc_14000BAB7
0x14000b8f7  cmp     bx, 3Ah ; ':'
0x14000b8fb  jnb     short loc_14000B907
0x14000b8fd  movzx   eax, bx
0x14000b900  sub     eax, ecx
0x14000b902  jmp     loc_14000BAB2
0x14000b907  cmp     bx, dx
0x14000b90a  jnb     loc_14000BAA3
0x14000b910  cmp     bx, r8w
0x14000b914  jb      loc_14000BAB7
0x14000b91a  mov     ecx, 66Ah
0x14000b91f  cmp     bx, cx
0x14000b922  jnb     short loc_14000B92F
0x14000b924  movzx   eax, bx
0x14000b927  sub     eax, r8d
0x14000b92a  jmp     loc_14000BAB2
0x14000b92f  cmp     bx, r9w
0x14000b933  jb      loc_14000BAB7
0x14000b939  mov     ecx, 6FAh
0x14000b93e  cmp     bx, cx
0x14000b941  jnb     short loc_14000B94E
0x14000b943  movzx   eax, bx
0x14000b946  sub     eax, r9d
0x14000b949  jmp     loc_14000BAB2
0x14000b94e  cmp     bx, r11w
0x14000b952  jb      loc_14000BAB7
0x14000b958  mov     ecx, 970h
0x14000b95d  cmp     bx, cx
0x14000b960  jnb     short loc_14000B96D
0x14000b962  movzx   eax, bx
0x14000b965  sub     eax, r11d
0x14000b968  jmp     loc_14000BAB2
0x14000b96d  cmp     bx, ax
0x14000b970  jb      loc_14000BAB7
0x14000b976  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x14000b97e  jnb     short loc_14000B98D
0x14000b980  movzx   eax, bx
0x14000b983  sub     eax, 9E6h
0x14000b988  jmp     loc_14000BAB2
0x14000b98d  mov     ecx, [rsp+0D8h+var_A8]
0x14000b991  cmp     bx, cx
0x14000b994  jb      loc_14000BAB7
0x14000b99a  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x14000b99f  jb      loc_14000B8FD
0x14000b9a5  mov     ecx, [rsp+0D8h+var_A0]
0x14000b9a9  cmp     bx, cx
0x14000b9ac  jb      loc_14000BAB7
0x14000b9b2  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x14000b9b7  jb      loc_14000B8FD
0x14000b9bd  mov     ecx, [rsp+0D8h+var_98]
0x14000b9c1  cmp     bx, cx
0x14000b9c4  jb      loc_14000BAB7
0x14000b9ca  cmp     bx, word ptr [rsp+0D8h+var_94]
0x14000b9cf  jb      loc_14000B8FD
0x14000b9d5  mov     ecx, [rsp+0D8h+var_90]
0x14000b9d9  cmp     bx, cx
0x14000b9dc  jb      loc_14000BAB7
0x14000b9e2  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x14000b9e7  jb      loc_14000B8FD
0x14000b9ed  mov     ecx, [rsp+0D8h+var_88]
0x14000b9f1  cmp     bx, cx
0x14000b9f4  jb      loc_14000BAB7
0x14000b9fa  cmp     bx, word ptr [rsp+0D8h+var_84]
0x14000b9ff  jb      loc_14000B8FD
0x14000ba05  mov     ecx, [rsp+0D8h+var_80]
0x14000ba09  cmp     bx, cx
0x14000ba0c  jb      loc_14000BAB7
0x14000ba12  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x14000ba17  jb      loc_14000B8FD
0x14000ba1d  mov     ecx, [rsp+0D8h+var_78]
0x14000ba21  cmp     bx, cx
0x14000ba24  jb      loc_14000BAB7
0x14000ba2a  cmp     bx, word ptr [rsp+0D8h+var_74]
0x14000ba2f  jb      loc_14000B8FD
0x14000ba35  mov     ecx, [rsp+0D8h+var_70]
0x14000ba39  cmp     bx, cx
0x14000ba3c  jb      short loc_14000BAB7
0x14000ba3e  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x14000ba43  jb      loc_14000B8FD
0x14000ba49  mov     ecx, [rsp+0D8h+var_68]
0x14000ba4d  cmp     bx, cx
0x14000ba50  jb      short loc_14000BAB7
0x14000ba52  cmp     bx, word ptr [rsp+0D8h+var_64]
0x14000ba57  jb      loc_14000B8FD
0x14000ba5d  mov     ecx, [rsp+0D8h+var_60]
0x14000ba61  cmp     bx, cx
0x14000ba64  jb      short loc_14000BAB7
0x14000ba66  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x14000ba6b  jb      loc_14000B8FD
0x14000ba71  mov     ecx, [rsp+0D8h+var_58]
0x14000ba78  cmp     bx, cx
0x14000ba7b  jb      short loc_14000BAB7
0x14000ba7d  cmp     bx, word ptr [rsp+0D8h+var_54]
0x14000ba85  jb      loc_14000B8FD
0x14000ba8b  mov     ecx, [rsp+0D8h+var_50]
0x14000ba92  movzx   eax, bx
0x14000ba95  sub     ax, cx
0x14000ba98  cmp     ax, 9
0x14000ba9c  ja      short loc_14000BAB7
0x14000ba9e  jmp     loc_14000B8FD
0x14000baa3  cmp     bx, word ptr [rsp+0D8h+var_4C]
0x14000baab  jnb     short loc_14000BAB7
0x14000baad  movzx   eax, bx
0x14000bab0  sub     eax, edx
0x14000bab2  cmp     eax, 0FFFFFFFFh
0x14000bab5  jnz     short loc_14000BAD9
0x14000bab7  mov     edx, [rsp+0D8h+var_48]
0x14000babe  movzx   ecx, bx
0x14000bac1  lea     eax, [rcx-41h]
0x14000bac4  cmp     eax, edx
0x14000bac6  lea     eax, [rcx-61h]
0x14000bac9  jbe     short loc_14000BACF
0x14000bacb  cmp     eax, edx
0x14000bacd  ja      short loc_14000BB3C
0x14000bacf  cmp     eax, edx
0x14000bad1  ja      short loc_14000BAD6
0x14000bad3  add     ecx, 0FFFFFFE0h
0x14000bad6  lea     eax, [rcx-37h]
0x14000bad9  test    eax, eax
0x14000badb  jnz     short loc_14000BB3C
0x14000badd  mov     rcx, [rdi]
0x14000bae0  mov     r9d, 0FFDFh
0x14000bae6  movzx   edx, word ptr [rcx]
0x14000bae9  lea     r8, [rcx+2]
0x14000baed  mov     [rdi], r8
0x14000baf0  lea     eax, [rdx-58h]
0x14000baf3  test    r9w, ax
0x14000baf7  jz      short loc_14000BB2A
0x14000baf9  test    r15d, r15d
0x14000bafc  mov     [rdi], rcx
0x14000baff  mov     eax, 8
0x14000bb04  cmovnz  eax, r15d
0x14000bb08  mov     r15d, eax
0x14000bb0b  test    dx, dx
0x14000bb0e  jz      short loc_14000BB4B
0x14000bb10  cmp     [rcx], dx
0x14000bb13  jz      short loc_14000BB4B
0x14000bb15  call    sub_14000FA6C
0x14000bb1a  mov     dword ptr [rax], 16h
0x14000bb20  call    _invalid_parameter_noinfo
0x14000bb25  xor     r10d, r10d
0x14000bb28  jmp     short loc_14000BB4B
0x14000bb2a  movzx   ebx, word ptr [r8]
0x14000bb2e  lea     rax, [r8+2]
0x14000bb32  mov     [rdi], rax
0x14000bb35  mov     eax, 10h
0x14000bb3a  jmp     short loc_14000BB41
0x14000bb3c  mov     eax, 0Ah
0x14000bb41  test    r15d, r15d
0x14000bb44  cmovnz  eax, r15d
0x14000bb48  mov     r15d, eax
0x14000bb4b  xor     edx, edx
0x14000bb4d  or      eax, 0FFFFFFFFh
0x14000bb50  div     r15d
0x14000bb53  mov     r11d, 61h ; 'a'
0x14000bb59  mov     ebp, 660h
0x14000bb5e  mov     r9d, eax
0x14000bb61  mov     r12d, 0FF10h
0x14000bb67  lea     r13d, [r11-31h]
0x14000bb6b  cmp     bx, r13w
0x14000bb6f  jb      loc_14000BD1A
0x14000bb75  cmp     bx, 3Ah ; ':'
0x14000bb79  jnb     short loc_14000BB86
0x14000bb7b  movzx   ecx, bx
0x14000bb7e  sub     ecx, r13d
0x14000bb81  jmp     loc_14000BD15
0x14000bb86  cmp     bx, r12w
0x14000bb8a  jnb     loc_14000BD05
0x14000bb90  cmp     bx, bp
0x14000bb93  jb      loc_14000BD1A
0x14000bb99  mov     eax, 66Ah
0x14000bb9e  cmp     bx, ax
0x14000bba1  jnb     short loc_14000BBAD
0x14000bba3  movzx   ecx, bx
0x14000bba6  sub     ecx, ebp
0x14000bba8  jmp     loc_14000BD15
0x14000bbad  mov     eax, 6F0h
0x14000bbb2  cmp     bx, ax
0x14000bbb5  jb      loc_14000BD1A
0x14000bbbb  lea     ecx, [rax+0Ah]
0x14000bbbe  cmp     bx, cx
0x14000bbc1  jnb     short loc_14000BBCD
0x14000bbc3  movzx   ecx, bx
0x14000bbc6  sub     ecx, eax
0x14000bbc8  jmp     loc_14000BD15
0x14000bbcd  mov     eax, 966h
0x14000bbd2  cmp     bx, ax
0x14000bbd5  jb      loc_14000BD1A
0x14000bbdb  lea     ecx, [rax+0Ah]
0x14000bbde  cmp     bx, cx
0x14000bbe1  jb      short loc_14000BBC3
0x14000bbe3  lea     eax, [rcx+76h]
0x14000bbe6  cmp     bx, ax
0x14000bbe9  jb      loc_14000BD1A
0x14000bbef  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x14000bbf7  jb      short loc_14000BBC3
0x14000bbf9  mov     eax, [rsp+0D8h+var_A8]
0x14000bbfd  cmp     bx, ax
0x14000bc00  jb      loc_14000BD1A
0x14000bc06  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x14000bc0b  jb      short loc_14000BBC3
0x14000bc0d  mov     eax, [rsp+0D8h+var_A0]
0x14000bc11  cmp     bx, ax
0x14000bc14  jb      loc_14000BD1A
0x14000bc1a  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x14000bc1f  jb      short loc_14000BBC3
0x14000bc21  mov     eax, [rsp+0D8h+var_98]
0x14000bc25  cmp     bx, ax
  ... truncated ...
```

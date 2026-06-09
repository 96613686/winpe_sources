# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x14000cc98`
- end: `0x14000d402`
- name: `??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1898`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000e844`

## callees

- `0x14000bea4`
- `0x14000bf5c`
- `0x14000cc98`
- `0x1400120dc`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<wchar_t>,0>(
        __crt_cached_ptd_host *a1,
        __int16 **a2,
        unsigned int a3,
        char a4)
{
  __int16 *v4; // r15
  unsigned int v5; // r14d
  __int16 *v7; // rcx
  unsigned __int16 v8; // bx
  unsigned int v9; // ebp
  char v10; // si
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // eax
  __int16 *v15; // rcx
  __int16 v16; // dx
  __int16 *v17; // r8
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r9d
  unsigned int v21; // ecx
  int v22; // eax
  int v23; // ecx
  __int16 *v24; // r8
  unsigned int v25; // edx
  bool v26; // cl
  bool v27; // cf
  bool v28; // zf
  __int16 *v29; // rax
  __int64 result; // rax
  __int16 *v31; // rdx
  __int16 *v32; // rdx
  __int16 *v33; // [rsp+90h] [rbp-48h]

  v4 = *a2;
  v33 = *a2;
  v5 = a3;
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
    goto LABEL_75;
  if ( v8 >= 0x30u )
  {
    if ( v8 < 0x3Au )
    {
LABEL_15:
      v12 = v8 - v11;
      goto LABEL_56;
    }
    if ( v8 >= 0xFF10u )
    {
      if ( v8 < 0xFF1Au )
      {
        v12 = v8 - 65296;
LABEL_56:
        if ( v12 != -1 )
          goto LABEL_62;
      }
    }
    else if ( v8 >= 0x660u )
    {
      if ( v8 < 0x66Au )
      {
        v12 = v8 - 1632;
        goto LABEL_56;
      }
      if ( v8 >= 0x6F0u )
      {
        if ( v8 < 0x6FAu )
        {
          v12 = v8 - 1776;
          goto LABEL_56;
        }
        if ( v8 >= 0x966u )
        {
          if ( v8 < 0x970u )
          {
            v12 = v8 - 2406;
            goto LABEL_56;
          }
          if ( v8 >= 0x9E6u )
          {
            if ( v8 < 0x9F0u )
            {
              v12 = v8 - 2534;
              goto LABEL_56;
            }
            if ( v8 >= 0xA66u )
            {
              if ( v8 < 0xA70u )
              {
                v12 = v8 - 2662;
                goto LABEL_56;
              }
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
    goto LABEL_71;
  if ( v14 <= 0x19 )
    v13 = v8 - 32;
  v12 = v13 - 55;
LABEL_62:
  if ( v12 )
  {
LABEL_71:
    v19 = 10;
    goto LABEL_72;
  }
  v15 = *a2;
  v16 = **a2;
  v17 = *a2 + 1;
  *a2 = v17;
  if ( ((v16 - 88) & 0xFFDF) == 0 )
  {
    v8 = *v17;
    *a2 = v17 + 1;
    v19 = 16;
LABEL_72:
    if ( v5 )
      v19 = v5;
    v5 = v19;
    goto LABEL_75;
  }
  *a2 = v15;
  v18 = 8;
  if ( v5 )
    v18 = v5;
  v5 = v18;
  if ( v16 && *v15 != v16 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
LABEL_75:
  v20 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( v8 >= 0x30u )
    {
      if ( v8 < 0x3Au )
      {
        v21 = v8 - 48;
        goto LABEL_117;
      }
      if ( v8 >= 0xFF10u )
      {
        if ( v8 < 0xFF1Au )
        {
          v21 = v8 - 65296;
LABEL_117:
          if ( v21 != -1 )
            goto LABEL_126;
        }
      }
      else if ( v8 >= 0x660u )
      {
        if ( v8 < 0x66Au )
        {
          v21 = v8 - 1632;
          goto LABEL_117;
        }
        if ( v8 >= 0x6F0u )
        {
          if ( v8 < 0x6FAu )
          {
            v21 = v8 - 1776;
            goto LABEL_117;
          }
          v22 = 2406;
          if ( v8 >= 0x966u )
          {
            if ( v8 < 0x970u )
              goto LABEL_88;
            v22 = 2534;
            if ( v8 >= 0x9E6u )
            {
              if ( v8 < 0x9F0u )
                goto LABEL_88;
              v22 = 2662;
              if ( v8 >= 0xA66u )
              {
                if ( v8 < 0xA70u )
                  goto LABEL_88;
                v22 = 2790;
                if ( v8 >= 0xAE6u )
                {
                  if ( v8 < 0xAF0u )
                    goto LABEL_88;
                  v22 = 2918;
                  if ( v8 >= 0xB66u )
                  {
                    if ( v8 < 0xB70u )
                      goto LABEL_88;
                    v22 = 3174;
                    if ( v8 >= 0xC66u )
                    {
                      if ( v8 < 0xC70u )
                        goto LABEL_88;
                      v22 = 3302;
                      if ( v8 >= 0xCE6u )
                      {
                        if ( v8 < 0xCF0u )
                          goto LABEL_88;
                        v22 = 3430;
                        if ( v8 >= 0xD66u )
                        {
                          if ( v8 < 0xD70u )
                            goto LABEL_88;
                          v22 = 3664;
                          if ( v8 >= 0xE50u )
                          {
                            if ( v8 < 0xE5Au )
                              goto LABEL_88;
                            v22 = 3792;
                            if ( v8 >= 0xED0u )
                            {
                              if ( v8 < 0xEDAu )
                                goto LABEL_88;
                              v22 = 3872;
                              if ( v8 >= 0xF20u )
                              {
                                if ( v8 < 0xF2Au )
                                  goto LABEL_88;
                                v22 = 4160;
                                if ( v8 >= 0x1040u )
                                {
                                  if ( v8 < 0x104Au )
                                    goto LABEL_88;
                                  v22 = 6112;
                                  if ( v8 >= 0x17E0u )
                                  {
                                    if ( v8 < 0x17EAu )
                                    {
LABEL_88:
                                      v21 = v8 - v22;
                                      goto LABEL_117;
                                    }
                                    if ( (unsigned __int16)(v8 - 6160) <= 9u )
                                    {
                                      v21 = v8 - 6160;
                                      goto LABEL_117;
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
    if ( ((v23 = v8, v8 < 0x41u) || v8 > 0x5Au) && (v8 < 0x61u || v8 > 0x7Au) )
    {
      v21 = -1;
    }
    else
    {
      if ( (unsigned __int16)(v8 - 97) <= 0x19u )
        v23 = v8 - 32;
      v21 = v23 - 55;
    }
LABEL_126:
    v24 = *a2;
    if ( v21 >= v5 )
      break;
    v8 = *v24;
    v25 = v5 * v9 + v21;
    v26 = v25 < v5 * v9;
    v27 = v9 < v20;
    v28 = v9 == v20;
    v9 = v25;
    *a2 = v24 + 1;
    v10 |= (4 * (!v27 && !v28 || v26)) | 8;
  }
  *a2 = v24 - 1;
  if ( v8 && *(v24 - 1) != v8 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( (v10 & 8) != 0 )
  {
    result = 0x7FFFFFFF;
    if ( (v10 & 4) != 0 )
      goto LABEL_139;
    if ( (v10 & 1) != 0 )
    {
      if ( (v10 & 2) == 0 )
      {
        if ( v9 <= 0x7FFFFFFF )
          goto LABEL_141;
        goto LABEL_139;
      }
      if ( v9 > 0x80000000 )
      {
LABEL_139:
        *((_BYTE *)a1 + 48) = 1;
        *((_DWORD *)a1 + 11) = 34;
        if ( (v10 & 1) != 0 )
        {
          v32 = a2[1];
          if ( (v10 & 2) != 0 )
          {
            if ( v32 )
              *(_QWORD *)v32 = *a2;
            return 0x80000000LL;
          }
          else if ( v32 )
          {
            *(_QWORD *)v32 = *a2;
          }
          return result;
        }
        v9 = -1;
LABEL_141:
        v31 = a2[1];
        if ( v31 )
          *(_QWORD *)v31 = *a2;
        return v9;
      }
    }
    else if ( (v10 & 2) == 0 )
    {
      goto LABEL_141;
    }
    v9 = -v9;
    goto LABEL_141;
  }
  v29 = a2[1];
  *a2 = v33;
  if ( v29 )
    *(_QWORD *)v29 = v33;
  return 0;
}

```

## disassembly

```asm
0x14000cc98  mov     [rsp+arg_10], rbx
0x14000cc9d  mov     [rsp+arg_0], rcx
0x14000cca2  push    rbp
0x14000cca3  push    rsi
0x14000cca4  push    rdi
0x14000cca5  push    r12
0x14000cca7  push    r13
0x14000cca9  push    r14
0x14000ccab  push    r15
0x14000ccad  sub     rsp, 0A0h
0x14000ccb4  mov     r15, [rdx]
0x14000ccb7  xor     r12d, r12d
0x14000ccba  mov     [rsp+0D8h+var_48], r15
0x14000ccc2  mov     r14d, r8d
0x14000ccc5  mov     rdi, rdx
0x14000ccc8  test    r15, r15
0x14000cccb  jnz     short loc_14000CCDF
0x14000cccd  call    _errno
0x14000ccd2  mov     dword ptr [rax], 16h
0x14000ccd8  call    _invalid_parameter_noinfo
0x14000ccdd  jmp     short loc_14000CD11
0x14000ccdf  test    r14d, r14d
0x14000cce2  jz      short loc_14000CD29
0x14000cce4  lea     eax, [r8-2]
0x14000cce8  cmp     eax, 22h ; '"'
0x14000cceb  jbe     short loc_14000CD29
0x14000cced  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x14000ccf2  xor     r9d, r9d; LineNo
0x14000ccf5  mov     byte ptr [rcx+30h], 1
0x14000ccf9  xor     r8d, r8d; FileName
0x14000ccfc  mov     dword ptr [rcx+2Ch], 16h
0x14000cd03  xor     edx, edx; FunctionName
0x14000cd05  xor     ecx, ecx; Expression
0x14000cd07  mov     [rsp+0D8h+var_B8], r12; uintptr_t
0x14000cd0c  call    _invalid_parameter_internal
0x14000cd11  mov     rcx, [rdi+8]
0x14000cd15  test    rcx, rcx
0x14000cd18  jz      loc_14000D360
0x14000cd1e  mov     rax, [rdi]
0x14000cd21  mov     [rcx], rax
0x14000cd24  jmp     loc_14000D360
0x14000cd29  movzx   ebx, word ptr [r15]
0x14000cd2d  lea     rcx, [r15+2]
0x14000cd31  movzx   eax, r9b
0x14000cd35  mov     ebp, r12d
0x14000cd38  mov     esi, eax
0x14000cd3a  mov     [rdx], rcx
0x14000cd3d  or      esi, 2
0x14000cd40  mov     edx, 0FFFDh
0x14000cd45  cmp     bx, 2Dh ; '-'
0x14000cd49  cmovnz  esi, eax
0x14000cd4c  lea     eax, [rbx-2Bh]
0x14000cd4f  test    dx, ax
0x14000cd52  jnz     short loc_14000CD5E
0x14000cd54  movzx   ebx, word ptr [rcx]
0x14000cd57  lea     rax, [rcx+2]
0x14000cd5b  mov     [rdi], rax
0x14000cd5e  mov     [rsp+0D8h+arg_8], 0A70h
0x14000cd69  mov     eax, 0A66h
0x14000cd6e  mov     [rsp+0D8h+var_A8], 0AE6h
0x14000cd76  mov     ecx, 30h ; '0'
0x14000cd7b  mov     [rsp+0D8h+var_A4], 0AF0h
0x14000cd83  mov     edx, 0FF10h
0x14000cd88  mov     [rsp+0D8h+var_A0], 0B66h
0x14000cd90  mov     r8d, 660h
0x14000cd96  mov     [rsp+0D8h+var_9C], 0B70h
0x14000cd9e  lea     r10d, [rax-80h]
0x14000cda2  mov     [rsp+0D8h+var_98], 0C66h
0x14000cdaa  mov     r11d, 6F0h
0x14000cdb0  mov     [rsp+0D8h+var_94], 0C70h
0x14000cdb8  mov     r9d, 966h
0x14000cdbe  mov     [rsp+0D8h+var_90], 0CE6h
0x14000cdc6  mov     [rsp+0D8h+var_8C], 0CF0h
0x14000cdce  mov     [rsp+0D8h+var_88], 0D66h
0x14000cdd6  mov     [rsp+0D8h+var_84], 0D70h
0x14000cdde  mov     [rsp+0D8h+var_80], 0E50h
0x14000cde6  mov     [rsp+0D8h+var_7C], 0E5Ah
0x14000cdee  mov     [rsp+0D8h+var_78], 0ED0h
0x14000cdf6  mov     [rsp+0D8h+var_74], 0EDAh
0x14000cdfe  mov     [rsp+0D8h+var_70], 0F20h
0x14000ce06  mov     [rsp+0D8h+var_6C], 0F2Ah
0x14000ce0e  mov     [rsp+0D8h+var_68], 1040h
0x14000ce16  mov     [rsp+0D8h+var_64], 104Ah
0x14000ce1e  mov     [rsp+0D8h+var_60], 17E0h
0x14000ce26  mov     [rsp+0D8h+var_5C], 17EAh
0x14000ce2e  mov     [rsp+0D8h+var_58], 1810h
0x14000ce39  mov     [rsp+0D8h+var_54], 0FF1Ah
0x14000ce44  mov     [rsp+0D8h+var_50], 19h
0x14000ce4f  test    r14d, 0FFFFFFEFh
0x14000ce56  jnz     loc_14000D0D5
0x14000ce5c  cmp     bx, cx
0x14000ce5f  jb      loc_14000D026
0x14000ce65  cmp     bx, 3Ah ; ':'
0x14000ce69  jnb     short loc_14000CE75
0x14000ce6b  movzx   eax, bx
0x14000ce6e  sub     eax, ecx
0x14000ce70  jmp     loc_14000D021
0x14000ce75  cmp     bx, dx
0x14000ce78  jnb     loc_14000D012
0x14000ce7e  cmp     bx, r8w
0x14000ce82  jb      loc_14000D026
0x14000ce88  mov     ecx, 66Ah
0x14000ce8d  cmp     bx, cx
0x14000ce90  jnb     short loc_14000CE9D
0x14000ce92  movzx   eax, bx
0x14000ce95  sub     eax, r8d
0x14000ce98  jmp     loc_14000D021
0x14000ce9d  cmp     bx, r11w
0x14000cea1  jb      loc_14000D026
0x14000cea7  mov     ecx, 6FAh
0x14000ceac  cmp     bx, cx
0x14000ceaf  jnb     short loc_14000CEBC
0x14000ceb1  movzx   eax, bx
0x14000ceb4  sub     eax, r11d
0x14000ceb7  jmp     loc_14000D021
0x14000cebc  cmp     bx, r9w
0x14000cec0  jb      loc_14000D026
0x14000cec6  mov     ecx, 970h
0x14000cecb  cmp     bx, cx
0x14000cece  jnb     short loc_14000CEDB
0x14000ced0  movzx   eax, bx
0x14000ced3  sub     eax, r9d
0x14000ced6  jmp     loc_14000D021
0x14000cedb  cmp     bx, r10w
0x14000cedf  jb      loc_14000D026
0x14000cee5  mov     ecx, 9F0h
0x14000ceea  cmp     bx, cx
0x14000ceed  jnb     short loc_14000CEFA
0x14000ceef  movzx   eax, bx
0x14000cef2  sub     eax, r10d
0x14000cef5  jmp     loc_14000D021
0x14000cefa  cmp     bx, ax
0x14000cefd  jb      loc_14000D026
0x14000cf03  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x14000cf0b  jnb     short loc_14000CF1A
0x14000cf0d  movzx   eax, bx
0x14000cf10  sub     eax, 0A66h
0x14000cf15  jmp     loc_14000D021
0x14000cf1a  mov     ecx, [rsp+0D8h+var_A8]
0x14000cf1e  cmp     bx, cx
0x14000cf21  jb      loc_14000D026
0x14000cf27  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x14000cf2c  jb      loc_14000CE6B
0x14000cf32  mov     ecx, [rsp+0D8h+var_A0]
0x14000cf36  cmp     bx, cx
0x14000cf39  jb      loc_14000D026
0x14000cf3f  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x14000cf44  jb      loc_14000CE6B
0x14000cf4a  mov     ecx, [rsp+0D8h+var_98]
0x14000cf4e  cmp     bx, cx
0x14000cf51  jb      loc_14000D026
0x14000cf57  cmp     bx, word ptr [rsp+0D8h+var_94]
0x14000cf5c  jb      loc_14000CE6B
0x14000cf62  mov     ecx, [rsp+0D8h+var_90]
0x14000cf66  cmp     bx, cx
0x14000cf69  jb      loc_14000D026
0x14000cf6f  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x14000cf74  jb      loc_14000CE6B
0x14000cf7a  mov     ecx, [rsp+0D8h+var_88]
0x14000cf7e  cmp     bx, cx
0x14000cf81  jb      loc_14000D026
0x14000cf87  cmp     bx, word ptr [rsp+0D8h+var_84]
0x14000cf8c  jb      loc_14000CE6B
0x14000cf92  mov     ecx, [rsp+0D8h+var_80]
0x14000cf96  cmp     bx, cx
0x14000cf99  jb      loc_14000D026
0x14000cf9f  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x14000cfa4  jb      loc_14000CE6B
0x14000cfaa  mov     ecx, [rsp+0D8h+var_78]
0x14000cfae  cmp     bx, cx
0x14000cfb1  jb      short loc_14000D026
0x14000cfb3  cmp     bx, word ptr [rsp+0D8h+var_74]
0x14000cfb8  jb      loc_14000CE6B
0x14000cfbe  mov     ecx, [rsp+0D8h+var_70]
0x14000cfc2  cmp     bx, cx
0x14000cfc5  jb      short loc_14000D026
0x14000cfc7  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x14000cfcc  jb      loc_14000CE6B
0x14000cfd2  mov     ecx, [rsp+0D8h+var_68]
0x14000cfd6  cmp     bx, cx
0x14000cfd9  jb      short loc_14000D026
0x14000cfdb  cmp     bx, word ptr [rsp+0D8h+var_64]
0x14000cfe0  jb      loc_14000CE6B
0x14000cfe6  mov     ecx, [rsp+0D8h+var_60]
0x14000cfea  cmp     bx, cx
0x14000cfed  jb      short loc_14000D026
0x14000cfef  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x14000cff4  jb      loc_14000CE6B
0x14000cffa  mov     ecx, [rsp+0D8h+var_58]
0x14000d001  movzx   eax, bx
0x14000d004  sub     ax, cx
0x14000d007  cmp     ax, 9
0x14000d00b  ja      short loc_14000D026
0x14000d00d  jmp     loc_14000CE6B
0x14000d012  cmp     bx, word ptr [rsp+0D8h+var_54]
0x14000d01a  jnb     short loc_14000D026
0x14000d01c  movzx   eax, bx
0x14000d01f  sub     eax, edx
0x14000d021  cmp     eax, 0FFFFFFFFh
0x14000d024  jnz     short loc_14000D04C
0x14000d026  mov     edx, [rsp+0D8h+var_50]
0x14000d02d  movzx   ecx, bx
0x14000d030  lea     eax, [rcx-41h]
0x14000d033  cmp     eax, edx
0x14000d035  lea     eax, [rcx-61h]
0x14000d038  jbe     short loc_14000D042
0x14000d03a  cmp     eax, edx
0x14000d03c  ja      loc_14000D0C6
0x14000d042  cmp     eax, edx
0x14000d044  ja      short loc_14000D049
0x14000d046  add     ecx, 0FFFFFFE0h
0x14000d049  lea     eax, [rcx-37h]
0x14000d04c  test    eax, eax
0x14000d04e  jnz     short loc_14000D0C6
0x14000d050  mov     rcx, [rdi]
0x14000d053  mov     r9d, 0FFDFh
0x14000d059  movzx   edx, word ptr [rcx]
0x14000d05c  lea     r8, [rcx+2]
0x14000d060  mov     [rdi], r8
0x14000d063  lea     eax, [rdx-58h]
0x14000d066  test    r9w, ax
0x14000d06a  jz      short loc_14000D0AE
0x14000d06c  test    r14d, r14d
0x14000d06f  mov     [rdi], rcx
0x14000d072  mov     eax, 8
0x14000d077  cmovnz  eax, r14d
0x14000d07b  mov     r14d, eax
0x14000d07e  test    dx, dx
0x14000d081  jz      short loc_14000D0A6
0x14000d083  cmp     [rcx], dx
0x14000d086  jz      short loc_14000D0A6
0x14000d088  call    _errno
0x14000d08d  mov     dword ptr [rax], 16h
0x14000d093  call    _invalid_parameter_noinfo
0x14000d098  mov     r8d, 660h
0x14000d09e  mov     r11d, 6F0h
0x14000d0a4  jmp     short loc_14000D0D5
0x14000d0a6  mov     r8d, 660h
0x14000d0ac  jmp     short loc_14000D0D5
0x14000d0ae  movzx   ebx, word ptr [r8]
0x14000d0b2  lea     rax, [r8+2]
0x14000d0b6  mov     [rdi], rax
0x14000d0b9  mov     r8d, 660h
0x14000d0bf  mov     eax, 10h
0x14000d0c4  jmp     short loc_14000D0CB
0x14000d0c6  mov     eax, 0Ah
0x14000d0cb  test    r14d, r14d
0x14000d0ce  cmovnz  eax, r14d
0x14000d0d2  mov     r14d, eax
0x14000d0d5  xor     edx, edx
0x14000d0d7  or      eax, 0FFFFFFFFh
0x14000d0da  div     r14d
0x14000d0dd  mov     r10d, 61h ; 'a'
0x14000d0e3  mov     r15d, 0FF10h
0x14000d0e9  mov     r9d, eax
0x14000d0ec  lea     r13d, [r10-31h]
0x14000d0f0  cmp     bx, r13w
0x14000d0f4  jb      loc_14000D2A2
0x14000d0fa  cmp     bx, 3Ah ; ':'
0x14000d0fe  jnb     short loc_14000D10B
0x14000d100  movzx   ecx, bx
0x14000d103  sub     ecx, r13d
0x14000d106  jmp     loc_14000D29D
0x14000d10b  cmp     bx, r15w
0x14000d10f  jnb     loc_14000D28D
0x14000d115  cmp     bx, r8w
0x14000d119  jb      loc_14000D2A2
0x14000d11f  mov     eax, 66Ah
0x14000d124  cmp     bx, ax
0x14000d127  jnb     short loc_14000D134
0x14000d129  movzx   ecx, bx
0x14000d12c  sub     ecx, r8d
0x14000d12f  jmp     loc_14000D29D
0x14000d134  cmp     bx, r11w
0x14000d138  jb      loc_14000D2A2
0x14000d13e  mov     eax, 6FAh
0x14000d143  cmp     bx, ax
0x14000d146  jnb     short loc_14000D153
0x14000d148  movzx   ecx, bx
0x14000d14b  sub     ecx, r11d
0x14000d14e  jmp     loc_14000D29D
0x14000d153  mov     eax, 966h
0x14000d158  cmp     bx, ax
0x14000d15b  jb      loc_14000D2A2
0x14000d161  lea     ecx, [rax+0Ah]
0x14000d164  cmp     bx, cx
0x14000d167  jnb     short loc_14000D173
0x14000d169  movzx   ecx, bx
0x14000d16c  sub     ecx, eax
0x14000d16e  jmp     loc_14000D29D
0x14000d173  mov     eax, 9E6h
0x14000d178  cmp     bx, ax
0x14000d17b  jb      loc_14000D2A2
0x14000d181  lea     ecx, [rax+0Ah]
0x14000d184  cmp     bx, cx
0x14000d187  jb      short loc_14000D169
0x14000d189  lea     eax, [rcx+76h]
0x14000d18c  cmp     bx, ax
0x14000d18f  jb      loc_14000D2A2
0x14000d195  cmp     bx, word ptr [rsp+0D8h+arg_8]
  ... truncated ...
```

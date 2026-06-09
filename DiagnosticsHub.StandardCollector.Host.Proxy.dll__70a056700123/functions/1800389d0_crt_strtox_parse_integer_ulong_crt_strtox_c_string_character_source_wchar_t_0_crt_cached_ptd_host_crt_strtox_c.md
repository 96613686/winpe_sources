# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x1800389d0`
- end: `0x18003913a`
- name: `??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1898`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x180033438`
- `0x1800433ec`
- `0x18004347c`
- `0x18004350c`
- `0x18004359c`
- `0x18004362c`
- `0x1800436bc`
- `0x1800523d8`
- `0x180052548`
- `0x1800529e0`
- `0x180052b50`
- `0x18005321c`
- `0x18005336c`

## callees

- `0x1800073e8`
- `0x1800074a0`
- `0x180007788`
- `0x1800389d0`

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
0x1800389d0  mov     [rsp+arg_10], rbx
0x1800389d5  mov     [rsp+arg_0], rcx
0x1800389da  push    rbp
0x1800389db  push    rsi
0x1800389dc  push    rdi
0x1800389dd  push    r12
0x1800389df  push    r13
0x1800389e1  push    r14
0x1800389e3  push    r15
0x1800389e5  sub     rsp, 0A0h
0x1800389ec  mov     r15, [rdx]
0x1800389ef  xor     r12d, r12d
0x1800389f2  mov     [rsp+0D8h+var_48], r15
0x1800389fa  mov     r14d, r8d
0x1800389fd  mov     rdi, rdx
0x180038a00  test    r15, r15
0x180038a03  jnz     short loc_180038A17
0x180038a05  call    _errno
0x180038a0a  mov     dword ptr [rax], 16h
0x180038a10  call    _invalid_parameter_noinfo
0x180038a15  jmp     short loc_180038A49
0x180038a17  test    r14d, r14d
0x180038a1a  jz      short loc_180038A61
0x180038a1c  lea     eax, [r8-2]
0x180038a20  cmp     eax, 22h ; '"'
0x180038a23  jbe     short loc_180038A61
0x180038a25  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x180038a2a  xor     r9d, r9d; LineNo
0x180038a2d  mov     byte ptr [rcx+30h], 1
0x180038a31  xor     r8d, r8d; FileName
0x180038a34  mov     dword ptr [rcx+2Ch], 16h
0x180038a3b  xor     edx, edx; FunctionName
0x180038a3d  xor     ecx, ecx; Expression
0x180038a3f  mov     [rsp+0D8h+var_B8], r12; uintptr_t
0x180038a44  call    _invalid_parameter_internal
0x180038a49  mov     rcx, [rdi+8]
0x180038a4d  test    rcx, rcx
0x180038a50  jz      loc_180039098
0x180038a56  mov     rax, [rdi]
0x180038a59  mov     [rcx], rax
0x180038a5c  jmp     loc_180039098
0x180038a61  movzx   ebx, word ptr [r15]
0x180038a65  lea     rcx, [r15+2]
0x180038a69  movzx   eax, r9b
0x180038a6d  mov     ebp, r12d
0x180038a70  mov     esi, eax
0x180038a72  mov     [rdx], rcx
0x180038a75  or      esi, 2
0x180038a78  mov     edx, 0FFFDh
0x180038a7d  cmp     bx, 2Dh ; '-'
0x180038a81  cmovnz  esi, eax
0x180038a84  lea     eax, [rbx-2Bh]
0x180038a87  test    dx, ax
0x180038a8a  jnz     short loc_180038A96
0x180038a8c  movzx   ebx, word ptr [rcx]
0x180038a8f  lea     rax, [rcx+2]
0x180038a93  mov     [rdi], rax
0x180038a96  mov     [rsp+0D8h+arg_8], 0A70h
0x180038aa1  mov     eax, 0A66h
0x180038aa6  mov     [rsp+0D8h+var_A8], 0AE6h
0x180038aae  mov     ecx, 30h ; '0'
0x180038ab3  mov     [rsp+0D8h+var_A4], 0AF0h
0x180038abb  mov     edx, 0FF10h
0x180038ac0  mov     [rsp+0D8h+var_A0], 0B66h
0x180038ac8  mov     r8d, 660h
0x180038ace  mov     [rsp+0D8h+var_9C], 0B70h
0x180038ad6  lea     r10d, [rax-80h]
0x180038ada  mov     [rsp+0D8h+var_98], 0C66h
0x180038ae2  mov     r11d, 6F0h
0x180038ae8  mov     [rsp+0D8h+var_94], 0C70h
0x180038af0  mov     r9d, 966h
0x180038af6  mov     [rsp+0D8h+var_90], 0CE6h
0x180038afe  mov     [rsp+0D8h+var_8C], 0CF0h
0x180038b06  mov     [rsp+0D8h+var_88], 0D66h
0x180038b0e  mov     [rsp+0D8h+var_84], 0D70h
0x180038b16  mov     [rsp+0D8h+var_80], 0E50h
0x180038b1e  mov     [rsp+0D8h+var_7C], 0E5Ah
0x180038b26  mov     [rsp+0D8h+var_78], 0ED0h
0x180038b2e  mov     [rsp+0D8h+var_74], 0EDAh
0x180038b36  mov     [rsp+0D8h+var_70], 0F20h
0x180038b3e  mov     [rsp+0D8h+var_6C], 0F2Ah
0x180038b46  mov     [rsp+0D8h+var_68], 1040h
0x180038b4e  mov     [rsp+0D8h+var_64], 104Ah
0x180038b56  mov     [rsp+0D8h+var_60], 17E0h
0x180038b5e  mov     [rsp+0D8h+var_5C], 17EAh
0x180038b66  mov     [rsp+0D8h+var_58], 1810h
0x180038b71  mov     [rsp+0D8h+var_54], 0FF1Ah
0x180038b7c  mov     [rsp+0D8h+var_50], 19h
0x180038b87  test    r14d, 0FFFFFFEFh
0x180038b8e  jnz     loc_180038E0D
0x180038b94  cmp     bx, cx
0x180038b97  jb      loc_180038D5E
0x180038b9d  cmp     bx, 3Ah ; ':'
0x180038ba1  jnb     short loc_180038BAD
0x180038ba3  movzx   eax, bx
0x180038ba6  sub     eax, ecx
0x180038ba8  jmp     loc_180038D59
0x180038bad  cmp     bx, dx
0x180038bb0  jnb     loc_180038D4A
0x180038bb6  cmp     bx, r8w
0x180038bba  jb      loc_180038D5E
0x180038bc0  mov     ecx, 66Ah
0x180038bc5  cmp     bx, cx
0x180038bc8  jnb     short loc_180038BD5
0x180038bca  movzx   eax, bx
0x180038bcd  sub     eax, r8d
0x180038bd0  jmp     loc_180038D59
0x180038bd5  cmp     bx, r11w
0x180038bd9  jb      loc_180038D5E
0x180038bdf  mov     ecx, 6FAh
0x180038be4  cmp     bx, cx
0x180038be7  jnb     short loc_180038BF4
0x180038be9  movzx   eax, bx
0x180038bec  sub     eax, r11d
0x180038bef  jmp     loc_180038D59
0x180038bf4  cmp     bx, r9w
0x180038bf8  jb      loc_180038D5E
0x180038bfe  mov     ecx, 970h
0x180038c03  cmp     bx, cx
0x180038c06  jnb     short loc_180038C13
0x180038c08  movzx   eax, bx
0x180038c0b  sub     eax, r9d
0x180038c0e  jmp     loc_180038D59
0x180038c13  cmp     bx, r10w
0x180038c17  jb      loc_180038D5E
0x180038c1d  mov     ecx, 9F0h
0x180038c22  cmp     bx, cx
0x180038c25  jnb     short loc_180038C32
0x180038c27  movzx   eax, bx
0x180038c2a  sub     eax, r10d
0x180038c2d  jmp     loc_180038D59
0x180038c32  cmp     bx, ax
0x180038c35  jb      loc_180038D5E
0x180038c3b  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x180038c43  jnb     short loc_180038C52
0x180038c45  movzx   eax, bx
0x180038c48  sub     eax, 0A66h
0x180038c4d  jmp     loc_180038D59
0x180038c52  mov     ecx, [rsp+0D8h+var_A8]
0x180038c56  cmp     bx, cx
0x180038c59  jb      loc_180038D5E
0x180038c5f  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x180038c64  jb      loc_180038BA3
0x180038c6a  mov     ecx, [rsp+0D8h+var_A0]
0x180038c6e  cmp     bx, cx
0x180038c71  jb      loc_180038D5E
0x180038c77  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x180038c7c  jb      loc_180038BA3
0x180038c82  mov     ecx, [rsp+0D8h+var_98]
0x180038c86  cmp     bx, cx
0x180038c89  jb      loc_180038D5E
0x180038c8f  cmp     bx, word ptr [rsp+0D8h+var_94]
0x180038c94  jb      loc_180038BA3
0x180038c9a  mov     ecx, [rsp+0D8h+var_90]
0x180038c9e  cmp     bx, cx
0x180038ca1  jb      loc_180038D5E
0x180038ca7  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x180038cac  jb      loc_180038BA3
0x180038cb2  mov     ecx, [rsp+0D8h+var_88]
0x180038cb6  cmp     bx, cx
0x180038cb9  jb      loc_180038D5E
0x180038cbf  cmp     bx, word ptr [rsp+0D8h+var_84]
0x180038cc4  jb      loc_180038BA3
0x180038cca  mov     ecx, [rsp+0D8h+var_80]
0x180038cce  cmp     bx, cx
0x180038cd1  jb      loc_180038D5E
0x180038cd7  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x180038cdc  jb      loc_180038BA3
0x180038ce2  mov     ecx, [rsp+0D8h+var_78]
0x180038ce6  cmp     bx, cx
0x180038ce9  jb      short loc_180038D5E
0x180038ceb  cmp     bx, word ptr [rsp+0D8h+var_74]
0x180038cf0  jb      loc_180038BA3
0x180038cf6  mov     ecx, [rsp+0D8h+var_70]
0x180038cfa  cmp     bx, cx
0x180038cfd  jb      short loc_180038D5E
0x180038cff  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x180038d04  jb      loc_180038BA3
0x180038d0a  mov     ecx, [rsp+0D8h+var_68]
0x180038d0e  cmp     bx, cx
0x180038d11  jb      short loc_180038D5E
0x180038d13  cmp     bx, word ptr [rsp+0D8h+var_64]
0x180038d18  jb      loc_180038BA3
0x180038d1e  mov     ecx, [rsp+0D8h+var_60]
0x180038d22  cmp     bx, cx
0x180038d25  jb      short loc_180038D5E
0x180038d27  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x180038d2c  jb      loc_180038BA3
0x180038d32  mov     ecx, [rsp+0D8h+var_58]
0x180038d39  movzx   eax, bx
0x180038d3c  sub     ax, cx
0x180038d3f  cmp     ax, 9
0x180038d43  ja      short loc_180038D5E
0x180038d45  jmp     loc_180038BA3
0x180038d4a  cmp     bx, word ptr [rsp+0D8h+var_54]
0x180038d52  jnb     short loc_180038D5E
0x180038d54  movzx   eax, bx
0x180038d57  sub     eax, edx
0x180038d59  cmp     eax, 0FFFFFFFFh
0x180038d5c  jnz     short loc_180038D84
0x180038d5e  mov     edx, [rsp+0D8h+var_50]
0x180038d65  movzx   ecx, bx
0x180038d68  lea     eax, [rcx-41h]
0x180038d6b  cmp     eax, edx
0x180038d6d  lea     eax, [rcx-61h]
0x180038d70  jbe     short loc_180038D7A
0x180038d72  cmp     eax, edx
0x180038d74  ja      loc_180038DFE
0x180038d7a  cmp     eax, edx
0x180038d7c  ja      short loc_180038D81
0x180038d7e  add     ecx, 0FFFFFFE0h
0x180038d81  lea     eax, [rcx-37h]
0x180038d84  test    eax, eax
0x180038d86  jnz     short loc_180038DFE
0x180038d88  mov     rcx, [rdi]
0x180038d8b  mov     r9d, 0FFDFh
0x180038d91  movzx   edx, word ptr [rcx]
0x180038d94  lea     r8, [rcx+2]
0x180038d98  mov     [rdi], r8
0x180038d9b  lea     eax, [rdx-58h]
0x180038d9e  test    r9w, ax
0x180038da2  jz      short loc_180038DE6
0x180038da4  test    r14d, r14d
0x180038da7  mov     [rdi], rcx
0x180038daa  mov     eax, 8
0x180038daf  cmovnz  eax, r14d
0x180038db3  mov     r14d, eax
0x180038db6  test    dx, dx
0x180038db9  jz      short loc_180038DDE
0x180038dbb  cmp     [rcx], dx
0x180038dbe  jz      short loc_180038DDE
0x180038dc0  call    _errno
0x180038dc5  mov     dword ptr [rax], 16h
0x180038dcb  call    _invalid_parameter_noinfo
0x180038dd0  mov     r8d, 660h
0x180038dd6  mov     r11d, 6F0h
0x180038ddc  jmp     short loc_180038E0D
0x180038dde  mov     r8d, 660h
0x180038de4  jmp     short loc_180038E0D
0x180038de6  movzx   ebx, word ptr [r8]
0x180038dea  lea     rax, [r8+2]
0x180038dee  mov     [rdi], rax
0x180038df1  mov     r8d, 660h
0x180038df7  mov     eax, 10h
0x180038dfc  jmp     short loc_180038E03
0x180038dfe  mov     eax, 0Ah
0x180038e03  test    r14d, r14d
0x180038e06  cmovnz  eax, r14d
0x180038e0a  mov     r14d, eax
0x180038e0d  xor     edx, edx
0x180038e0f  or      eax, 0FFFFFFFFh
0x180038e12  div     r14d
0x180038e15  mov     r10d, 61h ; 'a'
0x180038e1b  mov     r15d, 0FF10h
0x180038e21  mov     r9d, eax
0x180038e24  lea     r13d, [r10-31h]
0x180038e28  cmp     bx, r13w
0x180038e2c  jb      loc_180038FDA
0x180038e32  cmp     bx, 3Ah ; ':'
0x180038e36  jnb     short loc_180038E43
0x180038e38  movzx   ecx, bx
0x180038e3b  sub     ecx, r13d
0x180038e3e  jmp     loc_180038FD5
0x180038e43  cmp     bx, r15w
0x180038e47  jnb     loc_180038FC5
0x180038e4d  cmp     bx, r8w
0x180038e51  jb      loc_180038FDA
0x180038e57  mov     eax, 66Ah
0x180038e5c  cmp     bx, ax
0x180038e5f  jnb     short loc_180038E6C
0x180038e61  movzx   ecx, bx
0x180038e64  sub     ecx, r8d
0x180038e67  jmp     loc_180038FD5
0x180038e6c  cmp     bx, r11w
0x180038e70  jb      loc_180038FDA
0x180038e76  mov     eax, 6FAh
0x180038e7b  cmp     bx, ax
0x180038e7e  jnb     short loc_180038E8B
0x180038e80  movzx   ecx, bx
0x180038e83  sub     ecx, r11d
0x180038e86  jmp     loc_180038FD5
0x180038e8b  mov     eax, 966h
0x180038e90  cmp     bx, ax
0x180038e93  jb      loc_180038FDA
0x180038e99  lea     ecx, [rax+0Ah]
0x180038e9c  cmp     bx, cx
0x180038e9f  jnb     short loc_180038EAB
0x180038ea1  movzx   ecx, bx
0x180038ea4  sub     ecx, eax
0x180038ea6  jmp     loc_180038FD5
0x180038eab  mov     eax, 9E6h
0x180038eb0  cmp     bx, ax
0x180038eb3  jb      loc_180038FDA
0x180038eb9  lea     ecx, [rax+0Ah]
0x180038ebc  cmp     bx, cx
0x180038ebf  jb      short loc_180038EA1
0x180038ec1  lea     eax, [rcx+76h]
0x180038ec4  cmp     bx, ax
0x180038ec7  jb      loc_180038FDA
0x180038ecd  cmp     bx, word ptr [rsp+0D8h+arg_8]
  ... truncated ...
```

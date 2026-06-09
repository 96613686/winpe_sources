# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<wchar_t>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x180038cb0`
- end: `0x18003941a`
- name: `??$parse_integer@KV?$c_string_character_source@_W@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1898`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x180033718`
- `0x1800436cc`
- `0x18004375c`
- `0x1800437ec`
- `0x18004387c`
- `0x18004390c`
- `0x18004399c`
- `0x1800526b8`
- `0x180052828`
- `0x180052cc0`
- `0x180052e30`
- `0x1800534fc`
- `0x18005364c`

## callees

- `0x180007b48`
- `0x180007c00`
- `0x180007ee8`
- `0x180038cb0`

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
0x180038cb0  mov     [rsp+arg_10], rbx
0x180038cb5  mov     [rsp+arg_0], rcx
0x180038cba  push    rbp
0x180038cbb  push    rsi
0x180038cbc  push    rdi
0x180038cbd  push    r12
0x180038cbf  push    r13
0x180038cc1  push    r14
0x180038cc3  push    r15
0x180038cc5  sub     rsp, 0A0h
0x180038ccc  mov     r15, [rdx]
0x180038ccf  xor     r12d, r12d
0x180038cd2  mov     [rsp+0D8h+var_48], r15
0x180038cda  mov     r14d, r8d
0x180038cdd  mov     rdi, rdx
0x180038ce0  test    r15, r15
0x180038ce3  jnz     short loc_180038CF7
0x180038ce5  call    _errno
0x180038cea  mov     dword ptr [rax], 16h
0x180038cf0  call    _invalid_parameter_noinfo
0x180038cf5  jmp     short loc_180038D29
0x180038cf7  test    r14d, r14d
0x180038cfa  jz      short loc_180038D41
0x180038cfc  lea     eax, [r8-2]
0x180038d00  cmp     eax, 22h ; '"'
0x180038d03  jbe     short loc_180038D41
0x180038d05  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x180038d0a  xor     r9d, r9d; LineNo
0x180038d0d  mov     byte ptr [rcx+30h], 1
0x180038d11  xor     r8d, r8d; FileName
0x180038d14  mov     dword ptr [rcx+2Ch], 16h
0x180038d1b  xor     edx, edx; FunctionName
0x180038d1d  xor     ecx, ecx; Expression
0x180038d1f  mov     [rsp+0D8h+var_B8], r12; uintptr_t
0x180038d24  call    _invalid_parameter_internal
0x180038d29  mov     rcx, [rdi+8]
0x180038d2d  test    rcx, rcx
0x180038d30  jz      loc_180039378
0x180038d36  mov     rax, [rdi]
0x180038d39  mov     [rcx], rax
0x180038d3c  jmp     loc_180039378
0x180038d41  movzx   ebx, word ptr [r15]
0x180038d45  lea     rcx, [r15+2]
0x180038d49  movzx   eax, r9b
0x180038d4d  mov     ebp, r12d
0x180038d50  mov     esi, eax
0x180038d52  mov     [rdx], rcx
0x180038d55  or      esi, 2
0x180038d58  mov     edx, 0FFFDh
0x180038d5d  cmp     bx, 2Dh ; '-'
0x180038d61  cmovnz  esi, eax
0x180038d64  lea     eax, [rbx-2Bh]
0x180038d67  test    dx, ax
0x180038d6a  jnz     short loc_180038D76
0x180038d6c  movzx   ebx, word ptr [rcx]
0x180038d6f  lea     rax, [rcx+2]
0x180038d73  mov     [rdi], rax
0x180038d76  mov     [rsp+0D8h+arg_8], 0A70h
0x180038d81  mov     eax, 0A66h
0x180038d86  mov     [rsp+0D8h+var_A8], 0AE6h
0x180038d8e  mov     ecx, 30h ; '0'
0x180038d93  mov     [rsp+0D8h+var_A4], 0AF0h
0x180038d9b  mov     edx, 0FF10h
0x180038da0  mov     [rsp+0D8h+var_A0], 0B66h
0x180038da8  mov     r8d, 660h
0x180038dae  mov     [rsp+0D8h+var_9C], 0B70h
0x180038db6  lea     r10d, [rax-80h]
0x180038dba  mov     [rsp+0D8h+var_98], 0C66h
0x180038dc2  mov     r11d, 6F0h
0x180038dc8  mov     [rsp+0D8h+var_94], 0C70h
0x180038dd0  mov     r9d, 966h
0x180038dd6  mov     [rsp+0D8h+var_90], 0CE6h
0x180038dde  mov     [rsp+0D8h+var_8C], 0CF0h
0x180038de6  mov     [rsp+0D8h+var_88], 0D66h
0x180038dee  mov     [rsp+0D8h+var_84], 0D70h
0x180038df6  mov     [rsp+0D8h+var_80], 0E50h
0x180038dfe  mov     [rsp+0D8h+var_7C], 0E5Ah
0x180038e06  mov     [rsp+0D8h+var_78], 0ED0h
0x180038e0e  mov     [rsp+0D8h+var_74], 0EDAh
0x180038e16  mov     [rsp+0D8h+var_70], 0F20h
0x180038e1e  mov     [rsp+0D8h+var_6C], 0F2Ah
0x180038e26  mov     [rsp+0D8h+var_68], 1040h
0x180038e2e  mov     [rsp+0D8h+var_64], 104Ah
0x180038e36  mov     [rsp+0D8h+var_60], 17E0h
0x180038e3e  mov     [rsp+0D8h+var_5C], 17EAh
0x180038e46  mov     [rsp+0D8h+var_58], 1810h
0x180038e51  mov     [rsp+0D8h+var_54], 0FF1Ah
0x180038e5c  mov     [rsp+0D8h+var_50], 19h
0x180038e67  test    r14d, 0FFFFFFEFh
0x180038e6e  jnz     loc_1800390ED
0x180038e74  cmp     bx, cx
0x180038e77  jb      loc_18003903E
0x180038e7d  cmp     bx, 3Ah ; ':'
0x180038e81  jnb     short loc_180038E8D
0x180038e83  movzx   eax, bx
0x180038e86  sub     eax, ecx
0x180038e88  jmp     loc_180039039
0x180038e8d  cmp     bx, dx
0x180038e90  jnb     loc_18003902A
0x180038e96  cmp     bx, r8w
0x180038e9a  jb      loc_18003903E
0x180038ea0  mov     ecx, 66Ah
0x180038ea5  cmp     bx, cx
0x180038ea8  jnb     short loc_180038EB5
0x180038eaa  movzx   eax, bx
0x180038ead  sub     eax, r8d
0x180038eb0  jmp     loc_180039039
0x180038eb5  cmp     bx, r11w
0x180038eb9  jb      loc_18003903E
0x180038ebf  mov     ecx, 6FAh
0x180038ec4  cmp     bx, cx
0x180038ec7  jnb     short loc_180038ED4
0x180038ec9  movzx   eax, bx
0x180038ecc  sub     eax, r11d
0x180038ecf  jmp     loc_180039039
0x180038ed4  cmp     bx, r9w
0x180038ed8  jb      loc_18003903E
0x180038ede  mov     ecx, 970h
0x180038ee3  cmp     bx, cx
0x180038ee6  jnb     short loc_180038EF3
0x180038ee8  movzx   eax, bx
0x180038eeb  sub     eax, r9d
0x180038eee  jmp     loc_180039039
0x180038ef3  cmp     bx, r10w
0x180038ef7  jb      loc_18003903E
0x180038efd  mov     ecx, 9F0h
0x180038f02  cmp     bx, cx
0x180038f05  jnb     short loc_180038F12
0x180038f07  movzx   eax, bx
0x180038f0a  sub     eax, r10d
0x180038f0d  jmp     loc_180039039
0x180038f12  cmp     bx, ax
0x180038f15  jb      loc_18003903E
0x180038f1b  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x180038f23  jnb     short loc_180038F32
0x180038f25  movzx   eax, bx
0x180038f28  sub     eax, 0A66h
0x180038f2d  jmp     loc_180039039
0x180038f32  mov     ecx, [rsp+0D8h+var_A8]
0x180038f36  cmp     bx, cx
0x180038f39  jb      loc_18003903E
0x180038f3f  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x180038f44  jb      loc_180038E83
0x180038f4a  mov     ecx, [rsp+0D8h+var_A0]
0x180038f4e  cmp     bx, cx
0x180038f51  jb      loc_18003903E
0x180038f57  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x180038f5c  jb      loc_180038E83
0x180038f62  mov     ecx, [rsp+0D8h+var_98]
0x180038f66  cmp     bx, cx
0x180038f69  jb      loc_18003903E
0x180038f6f  cmp     bx, word ptr [rsp+0D8h+var_94]
0x180038f74  jb      loc_180038E83
0x180038f7a  mov     ecx, [rsp+0D8h+var_90]
0x180038f7e  cmp     bx, cx
0x180038f81  jb      loc_18003903E
0x180038f87  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x180038f8c  jb      loc_180038E83
0x180038f92  mov     ecx, [rsp+0D8h+var_88]
0x180038f96  cmp     bx, cx
0x180038f99  jb      loc_18003903E
0x180038f9f  cmp     bx, word ptr [rsp+0D8h+var_84]
0x180038fa4  jb      loc_180038E83
0x180038faa  mov     ecx, [rsp+0D8h+var_80]
0x180038fae  cmp     bx, cx
0x180038fb1  jb      loc_18003903E
0x180038fb7  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x180038fbc  jb      loc_180038E83
0x180038fc2  mov     ecx, [rsp+0D8h+var_78]
0x180038fc6  cmp     bx, cx
0x180038fc9  jb      short loc_18003903E
0x180038fcb  cmp     bx, word ptr [rsp+0D8h+var_74]
0x180038fd0  jb      loc_180038E83
0x180038fd6  mov     ecx, [rsp+0D8h+var_70]
0x180038fda  cmp     bx, cx
0x180038fdd  jb      short loc_18003903E
0x180038fdf  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x180038fe4  jb      loc_180038E83
0x180038fea  mov     ecx, [rsp+0D8h+var_68]
0x180038fee  cmp     bx, cx
0x180038ff1  jb      short loc_18003903E
0x180038ff3  cmp     bx, word ptr [rsp+0D8h+var_64]
0x180038ff8  jb      loc_180038E83
0x180038ffe  mov     ecx, [rsp+0D8h+var_60]
0x180039002  cmp     bx, cx
0x180039005  jb      short loc_18003903E
0x180039007  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x18003900c  jb      loc_180038E83
0x180039012  mov     ecx, [rsp+0D8h+var_58]
0x180039019  movzx   eax, bx
0x18003901c  sub     ax, cx
0x18003901f  cmp     ax, 9
0x180039023  ja      short loc_18003903E
0x180039025  jmp     loc_180038E83
0x18003902a  cmp     bx, word ptr [rsp+0D8h+var_54]
0x180039032  jnb     short loc_18003903E
0x180039034  movzx   eax, bx
0x180039037  sub     eax, edx
0x180039039  cmp     eax, 0FFFFFFFFh
0x18003903c  jnz     short loc_180039064
0x18003903e  mov     edx, [rsp+0D8h+var_50]
0x180039045  movzx   ecx, bx
0x180039048  lea     eax, [rcx-41h]
0x18003904b  cmp     eax, edx
0x18003904d  lea     eax, [rcx-61h]
0x180039050  jbe     short loc_18003905A
0x180039052  cmp     eax, edx
0x180039054  ja      loc_1800390DE
0x18003905a  cmp     eax, edx
0x18003905c  ja      short loc_180039061
0x18003905e  add     ecx, 0FFFFFFE0h
0x180039061  lea     eax, [rcx-37h]
0x180039064  test    eax, eax
0x180039066  jnz     short loc_1800390DE
0x180039068  mov     rcx, [rdi]
0x18003906b  mov     r9d, 0FFDFh
0x180039071  movzx   edx, word ptr [rcx]
0x180039074  lea     r8, [rcx+2]
0x180039078  mov     [rdi], r8
0x18003907b  lea     eax, [rdx-58h]
0x18003907e  test    r9w, ax
0x180039082  jz      short loc_1800390C6
0x180039084  test    r14d, r14d
0x180039087  mov     [rdi], rcx
0x18003908a  mov     eax, 8
0x18003908f  cmovnz  eax, r14d
0x180039093  mov     r14d, eax
0x180039096  test    dx, dx
0x180039099  jz      short loc_1800390BE
0x18003909b  cmp     [rcx], dx
0x18003909e  jz      short loc_1800390BE
0x1800390a0  call    _errno
0x1800390a5  mov     dword ptr [rax], 16h
0x1800390ab  call    _invalid_parameter_noinfo
0x1800390b0  mov     r8d, 660h
0x1800390b6  mov     r11d, 6F0h
0x1800390bc  jmp     short loc_1800390ED
0x1800390be  mov     r8d, 660h
0x1800390c4  jmp     short loc_1800390ED
0x1800390c6  movzx   ebx, word ptr [r8]
0x1800390ca  lea     rax, [r8+2]
0x1800390ce  mov     [rdi], rax
0x1800390d1  mov     r8d, 660h
0x1800390d7  mov     eax, 10h
0x1800390dc  jmp     short loc_1800390E3
0x1800390de  mov     eax, 0Ah
0x1800390e3  test    r14d, r14d
0x1800390e6  cmovnz  eax, r14d
0x1800390ea  mov     r14d, eax
0x1800390ed  xor     edx, edx
0x1800390ef  or      eax, 0FFFFFFFFh
0x1800390f2  div     r14d
0x1800390f5  mov     r10d, 61h ; 'a'
0x1800390fb  mov     r15d, 0FF10h
0x180039101  mov     r9d, eax
0x180039104  lea     r13d, [r10-31h]
0x180039108  cmp     bx, r13w
0x18003910c  jb      loc_1800392BA
0x180039112  cmp     bx, 3Ah ; ':'
0x180039116  jnb     short loc_180039123
0x180039118  movzx   ecx, bx
0x18003911b  sub     ecx, r13d
0x18003911e  jmp     loc_1800392B5
0x180039123  cmp     bx, r15w
0x180039127  jnb     loc_1800392A5
0x18003912d  cmp     bx, r8w
0x180039131  jb      loc_1800392BA
0x180039137  mov     eax, 66Ah
0x18003913c  cmp     bx, ax
0x18003913f  jnb     short loc_18003914C
0x180039141  movzx   ecx, bx
0x180039144  sub     ecx, r8d
0x180039147  jmp     loc_1800392B5
0x18003914c  cmp     bx, r11w
0x180039150  jb      loc_1800392BA
0x180039156  mov     eax, 6FAh
0x18003915b  cmp     bx, ax
0x18003915e  jnb     short loc_18003916B
0x180039160  movzx   ecx, bx
0x180039163  sub     ecx, r11d
0x180039166  jmp     loc_1800392B5
0x18003916b  mov     eax, 966h
0x180039170  cmp     bx, ax
0x180039173  jb      loc_1800392BA
0x180039179  lea     ecx, [rax+0Ah]
0x18003917c  cmp     bx, cx
0x18003917f  jnb     short loc_18003918B
0x180039181  movzx   ecx, bx
0x180039184  sub     ecx, eax
0x180039186  jmp     loc_1800392B5
0x18003918b  mov     eax, 9E6h
0x180039190  cmp     bx, ax
0x180039193  jb      loc_1800392BA
0x180039199  lea     ecx, [rax+0Ah]
0x18003919c  cmp     bx, cx
0x18003919f  jb      short loc_180039181
0x1800391a1  lea     eax, [rcx+76h]
0x1800391a4  cmp     bx, ax
0x1800391a7  jb      loc_1800392BA
0x1800391ad  cmp     bx, word ptr [rsp+0D8h+arg_8]
  ... truncated ...
```

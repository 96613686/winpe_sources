# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<wchar_t>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<wchar_t>,int,bool)

- ea: `0x1400154c8`
- end: `0x140015c62`
- name: `??$parse_integer@_KV?$c_string_character_source@_W@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@_W@0@H_N@Z`
- size: `1946`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, wint_t **, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140015c64`

## callees

- `0x140014130`
- `0x1400154c8`
- `0x140015fe4`
- `0x14001609c`
- `0x140016ea0`
- `0x14001b688`

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
    *(_DWORD *)sub_140016EA0(a1, a2, a3, a4) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( (_DWORD)a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_140015FE4(0, 0, 0, 0, 0, a1);
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
    *(_DWORD *)((__int64 (*)(void))sub_140016EA0)() = 22;
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
    *(_DWORD *)sub_140016EA0(v24, v22, v27, v23) = 22;
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
0x1400154c8  mov     [rsp+arg_10], rbx
0x1400154cd  mov     [rsp+arg_0], rcx
0x1400154d2  push    rbp
0x1400154d3  push    rsi
0x1400154d4  push    rdi
0x1400154d5  push    r12
0x1400154d7  push    r13
0x1400154d9  push    r14
0x1400154db  push    r15
0x1400154dd  sub     rsp, 0A0h
0x1400154e4  mov     r12, [rdx]
0x1400154e7  xor     r13d, r13d
0x1400154ea  movzx   esi, r9b
0x1400154ee  mov     r15d, r8d
0x1400154f1  mov     [rsp+0D8h+var_48], r12
0x1400154f9  mov     rdi, rdx
0x1400154fc  test    r12, r12
0x1400154ff  jnz     short loc_140015513
0x140015501  call    sub_140016EA0
0x140015506  mov     dword ptr [rax], 16h
0x14001550c  call    _invalid_parameter_noinfo
0x140015511  jmp     short loc_140015545
0x140015513  test    r15d, r15d
0x140015516  jz      short loc_14001555D
0x140015518  lea     eax, [r8-2]
0x14001551c  cmp     eax, 22h ; '"'
0x14001551f  jbe     short loc_14001555D
0x140015521  mov     [rsp+0D8h+var_B0], rcx; __crt_cached_ptd_host *
0x140015526  xor     r9d, r9d; LineNo
0x140015529  mov     byte ptr [rcx+30h], 1
0x14001552d  xor     r8d, r8d; FileName
0x140015530  mov     dword ptr [rcx+2Ch], 16h
0x140015537  xor     edx, edx; FunctionName
0x140015539  xor     ecx, ecx; Expression
0x14001553b  mov     [rsp+0D8h+var_B8], r13; uintptr_t
0x140015540  call    sub_140015FE4
0x140015545  mov     rcx, [rdi+8]; this
0x140015549  test    rcx, rcx
0x14001554c  jz      loc_140015BC0
0x140015552  mov     rax, [rdi]
0x140015555  mov     [rcx], rax
0x140015558  jmp     loc_140015BC0
0x14001555d  movzx   ebx, word ptr [r12]
0x140015562  lea     rax, [r12+2]
0x140015567  mov     [rdx], rax
0x14001556a  mov     ebp, r13d
0x14001556d  cmp     [rcx+28h], r13b
0x140015571  jnz     short loc_140015587
0x140015573  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140015578  jmp     short loc_140015587
0x14001557a  mov     rax, [rdi]
0x14001557d  movzx   ebx, word ptr [rax]
0x140015580  add     rax, 2
0x140015584  mov     [rdi], rax
0x140015587  mov     edx, 8; Type
0x14001558c  movzx   ecx, bx; C
0x14001558f  call    iswctype
0x140015594  test    eax, eax
0x140015596  jnz     short loc_14001557A
0x140015598  mov     eax, esi
0x14001559a  mov     ecx, 0FFFDh
0x14001559f  or      esi, 2
0x1400155a2  cmp     bx, 2Dh ; '-'
0x1400155a6  cmovnz  esi, eax
0x1400155a9  lea     eax, [rbx-2Bh]
0x1400155ac  test    cx, ax
0x1400155af  jnz     short loc_1400155BE
0x1400155b1  mov     rax, [rdi]
0x1400155b4  movzx   ebx, word ptr [rax]
0x1400155b7  add     rax, 2
0x1400155bb  mov     [rdi], rax
0x1400155be  mov     [rsp+0D8h+arg_8], 0A70h
0x1400155c9  mov     eax, 0A66h
0x1400155ce  mov     [rsp+0D8h+var_A8], 0AE6h
0x1400155d6  mov     ecx, 30h ; '0'
0x1400155db  mov     [rsp+0D8h+var_A4], 0AF0h
0x1400155e3  mov     edx, 0FF10h
0x1400155e8  mov     [rsp+0D8h+var_A0], 0B66h
0x1400155f0  mov     r8d, 660h
0x1400155f6  mov     [rsp+0D8h+var_9C], 0B70h
0x1400155fe  lea     r10d, [rax-80h]
0x140015602  mov     [rsp+0D8h+var_98], 0C66h
0x14001560a  mov     r11d, 6F0h
0x140015610  mov     [rsp+0D8h+var_94], 0C70h
0x140015618  mov     r9d, 966h
0x14001561e  mov     [rsp+0D8h+var_90], 0CE6h
0x140015626  mov     [rsp+0D8h+var_8C], 0CF0h
0x14001562e  mov     [rsp+0D8h+var_88], 0D66h
0x140015636  mov     [rsp+0D8h+var_84], 0D70h
0x14001563e  mov     [rsp+0D8h+var_80], 0E50h
0x140015646  mov     [rsp+0D8h+var_7C], 0E5Ah
0x14001564e  mov     [rsp+0D8h+var_78], 0ED0h
0x140015656  mov     [rsp+0D8h+var_74], 0EDAh
0x14001565e  mov     [rsp+0D8h+var_70], 0F20h
0x140015666  mov     [rsp+0D8h+var_6C], 0F2Ah
0x14001566e  mov     [rsp+0D8h+var_68], 1040h
0x140015676  mov     [rsp+0D8h+var_64], 104Ah
0x14001567e  mov     [rsp+0D8h+var_60], 17E0h
0x140015686  mov     [rsp+0D8h+var_5C], 17EAh
0x14001568e  mov     [rsp+0D8h+var_58], 1810h
0x140015699  mov     [rsp+0D8h+var_54], 0FF1Ah
0x1400156a4  mov     [rsp+0D8h+var_50], 19h
0x1400156af  test    r15d, 0FFFFFFEFh
0x1400156b6  jnz     loc_140015935
0x1400156bc  cmp     bx, cx
0x1400156bf  jb      loc_140015886
0x1400156c5  cmp     bx, 3Ah ; ':'
0x1400156c9  jnb     short loc_1400156D5
0x1400156cb  movzx   eax, bx
0x1400156ce  sub     eax, ecx
0x1400156d0  jmp     loc_140015881
0x1400156d5  cmp     bx, dx
0x1400156d8  jnb     loc_140015872
0x1400156de  cmp     bx, r8w
0x1400156e2  jb      loc_140015886
0x1400156e8  mov     ecx, 66Ah
0x1400156ed  cmp     bx, cx
0x1400156f0  jnb     short loc_1400156FD
0x1400156f2  movzx   eax, bx
0x1400156f5  sub     eax, r8d
0x1400156f8  jmp     loc_140015881
0x1400156fd  cmp     bx, r11w
0x140015701  jb      loc_140015886
0x140015707  mov     ecx, 6FAh
0x14001570c  cmp     bx, cx
0x14001570f  jnb     short loc_14001571C
0x140015711  movzx   eax, bx
0x140015714  sub     eax, r11d
0x140015717  jmp     loc_140015881
0x14001571c  cmp     bx, r9w
0x140015720  jb      loc_140015886
0x140015726  mov     ecx, 970h
0x14001572b  cmp     bx, cx
0x14001572e  jnb     short loc_14001573B
0x140015730  movzx   eax, bx
0x140015733  sub     eax, r9d
0x140015736  jmp     loc_140015881
0x14001573b  cmp     bx, r10w
0x14001573f  jb      loc_140015886
0x140015745  mov     ecx, 9F0h
0x14001574a  cmp     bx, cx
0x14001574d  jnb     short loc_14001575A
0x14001574f  movzx   eax, bx
0x140015752  sub     eax, r10d
0x140015755  jmp     loc_140015881
0x14001575a  cmp     bx, ax
0x14001575d  jb      loc_140015886
0x140015763  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x14001576b  jnb     short loc_14001577A
0x14001576d  movzx   eax, bx
0x140015770  sub     eax, 0A66h
0x140015775  jmp     loc_140015881
0x14001577a  mov     ecx, [rsp+0D8h+var_A8]
0x14001577e  cmp     bx, cx
0x140015781  jb      loc_140015886
0x140015787  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x14001578c  jb      loc_1400156CB
0x140015792  mov     ecx, [rsp+0D8h+var_A0]
0x140015796  cmp     bx, cx
0x140015799  jb      loc_140015886
0x14001579f  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x1400157a4  jb      loc_1400156CB
0x1400157aa  mov     ecx, [rsp+0D8h+var_98]
0x1400157ae  cmp     bx, cx
0x1400157b1  jb      loc_140015886
0x1400157b7  cmp     bx, word ptr [rsp+0D8h+var_94]
0x1400157bc  jb      loc_1400156CB
0x1400157c2  mov     ecx, [rsp+0D8h+var_90]
0x1400157c6  cmp     bx, cx
0x1400157c9  jb      loc_140015886
0x1400157cf  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x1400157d4  jb      loc_1400156CB
0x1400157da  mov     ecx, [rsp+0D8h+var_88]
0x1400157de  cmp     bx, cx
0x1400157e1  jb      loc_140015886
0x1400157e7  cmp     bx, word ptr [rsp+0D8h+var_84]
0x1400157ec  jb      loc_1400156CB
0x1400157f2  mov     ecx, [rsp+0D8h+var_80]
0x1400157f6  cmp     bx, cx
0x1400157f9  jb      loc_140015886
0x1400157ff  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x140015804  jb      loc_1400156CB
0x14001580a  mov     ecx, [rsp+0D8h+var_78]
0x14001580e  cmp     bx, cx
0x140015811  jb      short loc_140015886
0x140015813  cmp     bx, word ptr [rsp+0D8h+var_74]
0x140015818  jb      loc_1400156CB
0x14001581e  mov     ecx, [rsp+0D8h+var_70]
0x140015822  cmp     bx, cx
0x140015825  jb      short loc_140015886
0x140015827  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x14001582c  jb      loc_1400156CB
0x140015832  mov     ecx, [rsp+0D8h+var_68]
0x140015836  cmp     bx, cx
0x140015839  jb      short loc_140015886
0x14001583b  cmp     bx, word ptr [rsp+0D8h+var_64]
0x140015840  jb      loc_1400156CB
0x140015846  mov     ecx, [rsp+0D8h+var_60]
0x14001584a  cmp     bx, cx
0x14001584d  jb      short loc_140015886
0x14001584f  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x140015854  jb      loc_1400156CB
0x14001585a  mov     ecx, [rsp+0D8h+var_58]
0x140015861  movzx   eax, bx
0x140015864  sub     ax, cx
0x140015867  cmp     ax, 9
0x14001586b  ja      short loc_140015886
0x14001586d  jmp     loc_1400156CB
0x140015872  cmp     bx, word ptr [rsp+0D8h+var_54]
0x14001587a  jnb     short loc_140015886
0x14001587c  movzx   eax, bx
0x14001587f  sub     eax, edx
0x140015881  cmp     eax, 0FFFFFFFFh
0x140015884  jnz     short loc_1400158AC
0x140015886  mov     edx, [rsp+0D8h+var_50]
0x14001588d  movzx   ecx, bx
0x140015890  lea     eax, [rcx-41h]
0x140015893  cmp     eax, edx
0x140015895  lea     eax, [rcx-61h]
0x140015898  jbe     short loc_1400158A2
0x14001589a  cmp     eax, edx
0x14001589c  ja      loc_140015926
0x1400158a2  cmp     eax, edx
0x1400158a4  ja      short loc_1400158A9
0x1400158a6  add     ecx, 0FFFFFFE0h
0x1400158a9  lea     eax, [rcx-37h]
0x1400158ac  test    eax, eax
0x1400158ae  jnz     short loc_140015926
0x1400158b0  mov     rcx, [rdi]
0x1400158b3  mov     r9d, 0FFDFh
0x1400158b9  movzx   edx, word ptr [rcx]
0x1400158bc  lea     r8, [rcx+2]
0x1400158c0  mov     [rdi], r8
0x1400158c3  lea     eax, [rdx-58h]
0x1400158c6  test    r9w, ax
0x1400158ca  jz      short loc_14001590E
0x1400158cc  test    r15d, r15d
0x1400158cf  mov     [rdi], rcx
0x1400158d2  mov     eax, 8
0x1400158d7  cmovnz  eax, r15d
0x1400158db  mov     r15d, eax
0x1400158de  test    dx, dx
0x1400158e1  jz      short loc_140015906
0x1400158e3  cmp     [rcx], dx
0x1400158e6  jz      short loc_140015906
0x1400158e8  call    sub_140016EA0
0x1400158ed  mov     dword ptr [rax], 16h
0x1400158f3  call    _invalid_parameter_noinfo
0x1400158f8  mov     r8d, 660h
0x1400158fe  mov     r11d, 6F0h
0x140015904  jmp     short loc_140015935
0x140015906  mov     r8d, 660h
0x14001590c  jmp     short loc_140015935
0x14001590e  movzx   ebx, word ptr [r8]
0x140015912  lea     rax, [r8+2]
0x140015916  mov     [rdi], rax
0x140015919  mov     r8d, 660h
0x14001591f  mov     eax, 10h
0x140015924  jmp     short loc_14001592B
0x140015926  mov     eax, 0Ah
0x14001592b  test    r15d, r15d
0x14001592e  cmovnz  eax, r15d
0x140015932  mov     r15d, eax
0x140015935  xor     edx, edx
0x140015937  or      eax, 0FFFFFFFFh
0x14001593a  div     r15d
0x14001593d  mov     r10d, 61h ; 'a'
0x140015943  mov     r14d, 0FF10h
0x140015949  mov     r9d, eax
0x14001594c  lea     r12d, [r10-31h]
0x140015950  cmp     bx, r12w
0x140015954  jb      loc_140015B02
0x14001595a  cmp     bx, 3Ah ; ':'
0x14001595e  jnb     short loc_14001596B
0x140015960  movzx   ecx, bx
0x140015963  sub     ecx, r12d
0x140015966  jmp     loc_140015AFD
0x14001596b  cmp     bx, r14w
0x14001596f  jnb     loc_140015AED
0x140015975  cmp     bx, r8w
0x140015979  jb      loc_140015B02
0x14001597f  mov     eax, 66Ah
0x140015984  cmp     bx, ax
0x140015987  jnb     short loc_140015994
0x140015989  movzx   ecx, bx
0x14001598c  sub     ecx, r8d
0x14001598f  jmp     loc_140015AFD
0x140015994  cmp     bx, r11w
0x140015998  jb      loc_140015B02
0x14001599e  mov     eax, 6FAh
0x1400159a3  cmp     bx, ax
0x1400159a6  jnb     short loc_1400159B3
0x1400159a8  movzx   ecx, bx
0x1400159ab  sub     ecx, r11d
0x1400159ae  jmp     loc_140015AFD
0x1400159b3  mov     eax, 966h
0x1400159b8  cmp     bx, ax
0x1400159bb  jb      loc_140015B02
0x1400159c1  lea     ecx, [rax+0Ah]
0x1400159c4  cmp     bx, cx
  ... truncated ...
```

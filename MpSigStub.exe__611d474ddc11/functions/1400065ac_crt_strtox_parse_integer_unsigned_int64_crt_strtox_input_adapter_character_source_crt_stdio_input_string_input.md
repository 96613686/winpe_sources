# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::input_adapter_character_source<__crt_stdio_input::string_input_adapter<wchar_t>>,1>(__crt_cached_ptd_host &,__crt_strtox::input_adapter_character_source<__crt_stdio_input::string_input_adapter<wchar_t>>,int,bool)

- ea: `0x1400065ac`
- end: `0x140006ed6`
- name: `??$parse_integer@_KV?$input_adapter_character_source@V?$string_input_adapter@_W@__crt_stdio_input@@@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$input_adapter_character_source@V?$string_input_adapter@_W@__crt_stdio_input@@@0@H_N@Z`
- size: `2346`
- prototype: `unsigned __int64 __fastcall(__crt_cached_ptd_host *this, _QWORD *, signed int, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140006ed8`

## callees

- `0x140004614`
- `0x1400046cc`
- `0x140004a54`
- `0x1400065ac`
- `0x14000ad70`
- `0x14000fa6c`
- `0x140010524`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::input_adapter_character_source<__crt_stdio_input::string_input_adapter<wchar_t>>,1>(
        __crt_cached_ptd_host *this,
        _QWORD *a2,
        signed int a3,
        unsigned __int8 a4)
{
  unsigned int v5; // esi
  __int64 v6; // rdx
  wint_t v7; // bx
  signed int v8; // ebp
  _QWORD *v9; // r14
  unsigned __int64 v10; // r15
  wint_t *v11; // rax
  unsigned __int64 v12; // rax
  wint_t *v13; // rax
  wint_t v14; // dx
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned __int64 v17; // rax
  wint_t *v18; // rax
  wint_t v19; // dx
  int v20; // ecx
  int v21; // eax
  int v22; // ecx
  unsigned int v23; // eax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  __int16 v26; // r8
  __int16 *v27; // rax
  __int16 v28; // r9
  int v29; // eax
  unsigned __int64 v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  unsigned __int64 v33; // rdx
  wint_t *v34; // rax
  wint_t v35; // dx
  int v36; // eax
  unsigned __int64 v37; // r9
  unsigned int v38; // ecx
  int v39; // eax
  int v40; // ecx
  unsigned int v41; // eax
  unsigned __int64 v42; // rdx
  BOOL v43; // ecx
  bool v44; // cf
  bool v45; // zf
  unsigned __int64 v46; // rax
  wint_t *v47; // rax
  wint_t v48; // dx
  _BYTE **v49; // r14
  unsigned __int64 v50; // rax
  __int64 v51; // rax
  _BYTE *v53; // rax
  __int64 v54; // [rsp+98h] [rbp-40h]

  v5 = a4;
  v6 = *a2;
  v7 = 0;
  v8 = a3;
  v9 = a2 + 3;
  if ( !v6 || !*v9 )
  {
    *(_DWORD *)sub_14000FA6C(this, v6) = 22;
    invalid_parameter_noinfo();
    goto LABEL_7;
  }
  if ( a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)this + 48) = 1;
    *((_DWORD *)this + 11) = 22;
    sub_140004614(0, 0, 0, 0, 0, this);
LABEL_7:
    if ( *v9 )
    {
      if ( !a2[2] )
        *(_BYTE *)*v9 = 0;
    }
    return 0;
  }
  v10 = 0;
  v54 = a2[2];
  a2[2] = v54 + 1;
  if ( !a2[1] || (unsigned __int64)(v54 + 1) <= a2[1] )
  {
    v11 = *(wint_t **)(v6 + 16);
    if ( v11 != *(wint_t **)(v6 + 8) )
    {
      v7 = *v11;
      *(_QWORD *)(v6 + 16) = v11 + 1;
      if ( v7 == 0xFFFF )
        v7 = 0;
    }
  }
  if ( !*((_BYTE *)this + 40) )
    __crt_cached_ptd_host::update_locale_slow(this);
  while ( iswctype(v7, 8u) )
  {
    v12 = a2[2] + 1LL;
    a2[2] = v12;
    if ( !a2[1] || v12 <= a2[1] )
    {
      v13 = *(wint_t **)(*a2 + 16LL);
      if ( v13 != *(wint_t **)(*a2 + 8LL) )
      {
        v14 = *v13;
        *(_QWORD *)(*a2 + 16LL) = v13 + 1;
        v7 = v14;
        if ( v14 != 0xFFFF )
          continue;
      }
    }
    v7 = 0;
  }
  v15 = v5;
  v16 = v5 | 2;
  if ( v7 != 45 )
    v16 = v15;
  if ( ((v7 - 43) & 0xFFFD) == 0 )
  {
    if ( (v17 = a2[2] + 1LL, a2[2] = v17, a2[1]) && v17 > a2[1]
      || (v18 = *(wint_t **)(*a2 + 16LL), v18 == *(wint_t **)(*a2 + 8LL))
      || (v19 = *v18, *(_QWORD *)(*a2 + 16LL) = v18 + 1, v7 = v19, v19 == 0xFFFF) )
    {
      v7 = 0;
    }
  }
  v20 = 48;
  if ( (v8 & 0xFFFFFFEF) != 0 )
    goto LABEL_108;
  if ( v7 >= 0x30u )
  {
    if ( v7 < 0x3Au )
    {
LABEL_35:
      v21 = v7 - v20;
      goto LABEL_75;
    }
    if ( v7 >= 0xFF10u )
    {
      if ( v7 < 0xFF1Au )
      {
        v21 = v7 - 65296;
LABEL_75:
        if ( v21 != -1 )
          goto LABEL_81;
      }
    }
    else if ( v7 >= 0x660u )
    {
      if ( v7 < 0x66Au )
      {
        v21 = v7 - 1632;
        goto LABEL_75;
      }
      if ( v7 >= 0x6F0u )
      {
        if ( v7 < 0x6FAu )
        {
          v21 = v7 - 1776;
          goto LABEL_75;
        }
        if ( v7 >= 0x966u )
        {
          if ( v7 < 0x970u )
          {
            v21 = v7 - 2406;
            goto LABEL_75;
          }
          if ( v7 >= 0x9E6u )
          {
            if ( v7 < 0x9F0u )
            {
              v21 = v7 - 2534;
              goto LABEL_75;
            }
            v20 = 2662;
            if ( v7 >= 0xA66u )
            {
              if ( v7 < 0xA70u )
                goto LABEL_35;
              v20 = 2790;
              if ( v7 >= 0xAE6u )
              {
                if ( v7 < 0xAF0u )
                  goto LABEL_35;
                v20 = 2918;
                if ( v7 >= 0xB66u )
                {
                  if ( v7 < 0xB70u )
                    goto LABEL_35;
                  v20 = 3174;
                  if ( v7 >= 0xC66u )
                  {
                    if ( v7 < 0xC70u )
                      goto LABEL_35;
                    v20 = 3302;
                    if ( v7 >= 0xCE6u )
                    {
                      if ( v7 < 0xCF0u )
                        goto LABEL_35;
                      v20 = 3430;
                      if ( v7 >= 0xD66u )
                      {
                        if ( v7 < 0xD70u )
                          goto LABEL_35;
                        v20 = 3664;
                        if ( v7 >= 0xE50u )
                        {
                          if ( v7 < 0xE5Au )
                            goto LABEL_35;
                          v20 = 3792;
                          if ( v7 >= 0xED0u )
                          {
                            if ( v7 < 0xEDAu )
                              goto LABEL_35;
                            v20 = 3872;
                            if ( v7 >= 0xF20u )
                            {
                              if ( v7 < 0xF2Au )
                                goto LABEL_35;
                              v20 = 4160;
                              if ( v7 >= 0x1040u )
                              {
                                if ( v7 < 0x104Au )
                                  goto LABEL_35;
                                v20 = 6112;
                                if ( v7 >= 0x17E0u )
                                {
                                  if ( v7 < 0x17EAu )
                                    goto LABEL_35;
                                  v20 = 6160;
                                  if ( (unsigned __int16)(v7 - 6160) <= 9u )
                                    goto LABEL_35;
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
  v22 = v7;
  v23 = v7 - 97;
  if ( (unsigned int)v7 - 65 > 0x19 && v23 > 0x19 )
    goto LABEL_105;
  if ( v23 <= 0x19 )
    v22 = v7 - 32;
  v21 = v22 - 55;
LABEL_81:
  if ( v21 )
  {
LABEL_105:
    v36 = 10;
    if ( v8 )
      v36 = v8;
    v8 = v36;
    goto LABEL_108;
  }
  v24 = a2[1];
  v25 = a2[2] + 1LL;
  a2[2] = v25;
  if ( v24 && v25 > v24 )
  {
    v26 = 0;
  }
  else
  {
    v27 = *(__int16 **)(*a2 + 16LL);
    if ( v27 == *(__int16 **)(*a2 + 8LL)
      || (v28 = *v27, *(_QWORD *)(*a2 + 16LL) = v27 + 1, v25 = a2[2], v24 = a2[1], v28 == -1) )
    {
      v26 = 0;
    }
    else if ( v28 == 120 || (v26 = v28, v28 == 88) )
    {
      v32 = 16;
      if ( v8 )
        v32 = v8;
      v33 = v25 + 1;
      a2[2] = v33;
      v8 = v32;
      if ( v24 && v33 > v24
        || (v34 = *(wint_t **)(*a2 + 16LL), v34 == *(wint_t **)(*a2 + 8LL))
        || (v35 = *v34, *(_QWORD *)(*a2 + 16LL) = v34 + 1, v35 == 0xFFFF) )
      {
        v7 = 0;
      }
      else
      {
        v7 = v35;
      }
      goto LABEL_108;
    }
  }
  v29 = 8;
  if ( v8 )
    v29 = v8;
  v30 = v25 - 1;
  a2[2] = v30;
  v8 = v29;
  if ( (!v24 || v30 <= v24) && (unsigned __int16)(v26 - 1) <= 0xFFFDu )
  {
    v31 = *(_QWORD *)(*a2 + 16LL);
    if ( v31 != *(_QWORD *)*a2 )
      *(_QWORD *)(*a2 + 16LL) = v31 - 2;
  }
LABEL_108:
  v37 = 0xFFFFFFFFFFFFFFFFuLL / v8;
  while ( 1 )
  {
    if ( v7 >= 0x30u )
    {
      if ( v7 < 0x3Au )
      {
        v38 = v7 - 48;
        goto LABEL_149;
      }
      if ( v7 >= 0xFF10u )
      {
        if ( v7 < 0xFF1Au )
        {
          v38 = v7 - 65296;
LABEL_149:
          if ( v38 != -1 )
            goto LABEL_156;
        }
      }
      else if ( v7 >= 0x660u )
      {
        if ( v7 < 0x66Au )
        {
          v38 = v7 - 1632;
          goto LABEL_149;
        }
        v39 = 1776;
        if ( v7 >= 0x6F0u )
        {
          if ( v7 < 0x6FAu )
            goto LABEL_118;
          v39 = 2406;
          if ( v7 >= 0x966u )
          {
            if ( v7 < 0x970u )
              goto LABEL_118;
            v39 = 2534;
            if ( v7 >= 0x9E6u )
            {
              if ( v7 < 0x9F0u )
                goto LABEL_118;
              v39 = 2662;
              if ( v7 >= 0xA66u )
              {
                if ( v7 < 0xA70u )
                  goto LABEL_118;
                v39 = 2790;
                if ( v7 >= 0xAE6u )
                {
                  if ( v7 < 0xAF0u )
                    goto LABEL_118;
                  v39 = 2918;
                  if ( v7 >= 0xB66u )
                  {
                    if ( v7 < 0xB70u )
                      goto LABEL_118;
                    v39 = 3174;
                    if ( v7 >= 0xC66u )
                    {
                      if ( v7 < 0xC70u )
                        goto LABEL_118;
                      v39 = 3302;
                      if ( v7 >= 0xCE6u )
                      {
                        if ( v7 < 0xCF0u )
                          goto LABEL_118;
                        v39 = 3430;
                        if ( v7 >= 0xD66u )
                        {
                          if ( v7 < 0xD70u )
                            goto LABEL_118;
                          v39 = 3664;
                          if ( v7 >= 0xE50u )
                          {
                            if ( v7 < 0xE5Au )
                              goto LABEL_118;
                            v39 = 3792;
                            if ( v7 >= 0xED0u )
                            {
                              if ( v7 < 0xEDAu )
                                goto LABEL_118;
                              v39 = 3872;
                              if ( v7 >= 0xF20u )
                              {
                                if ( v7 < 0xF2Au )
                                  goto LABEL_118;
                                v39 = 4160;
                                if ( v7 >= 0x1040u )
                                {
                                  if ( v7 < 0x104Au )
                                    goto LABEL_118;
                                  v39 = 6112;
                                  if ( v7 >= 0x17E0u )
                                  {
                                    if ( v7 < 0x17EAu )
                                    {
LABEL_118:
                                      v38 = v7 - v39;
                                      goto LABEL_149;
                                    }
                                    if ( (unsigned __int16)(v7 - 6160) <= 9u )
                                    {
                                      v38 = v7 - 6160;
                                      goto LABEL_149;
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
    v40 = v7;
    v41 = v7 - 97;
    if ( (unsigned int)v7 - 65 > 0x19 && v41 > 0x19 )
    {
      v38 = -1;
    }
    else
    {
      if ( v41 <= 0x19 )
        v40 = v7 - 32;
      v38 = v40 - 55;
    }
LABEL_156:
    if ( v38 >= v8 )
      break;
    v42 = v10 * v8 + v38;
    v43 = v42 < v10 * v8;
    v44 = v10 < v37;
    v45 = v10 == v37;
    v10 = v42;
    v16 |= (4 * (!v44 && !v45 || v43)) | 8;
    v46 = a2[2] + 1LL;
    a2[2] = v46;
    if ( a2[1] && v46 > a2[1]
      || (v47 = *(wint_t **)(*a2 + 16LL), v47 == *(wint_t **)(*a2 + 8LL))
      || (v48 = *v47, *(_QWORD *)(*a2 + 16LL) = v47 + 1, v48 == 0xFFFF) )
    {
      v7 = 0;
    }
    else
    {
      v7 = v48;
    }
  }
  v49 = (_BYTE **)(a2 + 3);
  v50 = a2[2] - 1LL;
  a2[2] = v50;
  if ( (!a2[1] || v50 <= a2[1]) && (unsigned __int16)(v7 - 1) <= 0xFFFDu )
  {
    v51 = *(_QWORD *)(*a2 + 16LL);
    if ( v51 != *(_QWORD *)*a2 )
      *(_QWORD *)(*a2 + 16LL) = v51 - 2;
  }
  if ( (v16 & 8) != 0 )
  {
    if ( (unsigned __int8)__crt_strtox::is_overflow_condition<unsigned __int64>(v16, v10) )
    {
      *((_BYTE *)this + 48) = 1;
      *((_DWORD *)this + 11) = 34;
      if ( (v16 & 1) != 0 )
      {
        v53 = *v49;
        if ( (v16 & 2) != 0 )
        {
          if ( v53 && !a2[2] )
            *v53 = 0;
          return 0x8000000000000000uLL;
        }
        else
        {
          if ( v53 && !a2[2] )
            *v53 = 0;
          return 0x7FFFFFFFFFFFFFFFLL;
        }
      }
      v10 = -1;
    }
    else if ( (v16 & 2) != 0 )
    {
      v10 = -(__int64)v10;
    }
    if ( *v49 && !a2[2] )
      **v49 = 0;
    return v10;
  }
  if ( v54 != a2[2] )
    **v49 = 0;
  if ( *v49 && !a2[2] )
    **v49 = 0;
  return 0;
}

```

## disassembly

```asm
0x1400065ac  mov     [rsp+arg_10], rbx
0x1400065b1  mov     [rsp+arg_0], rcx
0x1400065b6  push    rbp
0x1400065b7  push    rsi
0x1400065b8  push    rdi
0x1400065b9  push    r12
0x1400065bb  push    r13
0x1400065bd  push    r14
0x1400065bf  push    r15
0x1400065c1  sub     rsp, 0A0h
0x1400065c8  mov     rdi, rdx
0x1400065cb  movzx   esi, r9b
0x1400065cf  mov     rdx, [rdx]
0x1400065d2  xor     ebx, ebx
0x1400065d4  mov     ebp, r8d
0x1400065d7  mov     r13, rcx
0x1400065da  lea     r14, [rdi+18h]
0x1400065de  test    rdx, rdx
0x1400065e1  jz      short loc_1400065E8
0x1400065e3  cmp     [r14], rbx
0x1400065e6  jnz     short loc_1400065FA
0x1400065e8  call    sub_14000FA6C
0x1400065ed  mov     dword ptr [rax], 16h
0x1400065f3  call    _invalid_parameter_noinfo
0x1400065f8  jmp     short loc_14000662B
0x1400065fa  test    ebp, ebp
0x1400065fc  jz      short loc_140006648
0x1400065fe  lea     eax, [r8-2]
0x140006602  cmp     eax, 22h ; '"'
0x140006605  jbe     short loc_140006648
0x140006607  mov     byte ptr [rcx+30h], 1
0x14000660b  xor     r9d, r9d; LineNo
0x14000660e  mov     dword ptr [rcx+2Ch], 16h
0x140006615  xor     r8d, r8d; FileName
0x140006618  xor     ecx, ecx; Expression
0x14000661a  mov     [rsp+0D8h+var_B0], r13; __crt_cached_ptd_host *
0x14000661f  xor     edx, edx; FunctionName
0x140006621  mov     [rsp+0D8h+var_B8], rbx; uintptr_t
0x140006626  call    sub_140004614
0x14000662b  mov     rax, [r14]
0x14000662e  test    rax, rax
0x140006631  jz      loc_140006E34
0x140006637  cmp     [rdi+10h], rbx
0x14000663b  jnz     loc_140006E34
0x140006641  mov     [rax], bl
0x140006643  jmp     loc_140006E34
0x140006648  mov     r15, rbx
0x14000664b  mov     r12, [rdi+10h]
0x14000664f  mov     ecx, 0FFFFh
0x140006654  mov     [rsp+0D8h+var_40], r12
0x14000665c  lea     rax, [r12+1]
0x140006661  mov     [rdi+10h], rax
0x140006665  cmp     [rdi+8], rbx
0x140006669  jz      short loc_140006671
0x14000666b  cmp     rax, [rdi+8]
0x14000666f  ja      short loc_14000668D
0x140006671  mov     rax, [rdx+10h]
0x140006675  cmp     rax, [rdx+8]
0x140006679  jz      short loc_14000668D
0x14000667b  movzx   ebx, word ptr [rax]
0x14000667e  add     rax, 2
0x140006682  mov     [rdx+10h], rax
0x140006686  cmp     bx, cx
0x140006689  jnz     short loc_14000668D
0x14000668b  xor     ebx, ebx
0x14000668d  xor     edx, edx
0x14000668f  cmp     [r13+28h], dl
0x140006693  jnz     short loc_14000669D
0x140006695  mov     rcx, r13; this
0x140006698  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14000669d  mov     edx, 8; Type
0x1400066a2  movzx   ecx, bx; C
0x1400066a5  call    iswctype
0x1400066aa  xor     r10d, r10d
0x1400066ad  test    eax, eax
0x1400066af  jz      short loc_140006707
0x1400066b1  mov     r14d, 0FFFFh
0x1400066b7  mov     rax, [rdi+10h]
0x1400066bb  inc     rax
0x1400066be  mov     [rdi+10h], rax
0x1400066c2  cmp     [rdi+8], r10
0x1400066c6  jz      short loc_1400066CE
0x1400066c8  cmp     rax, [rdi+8]
0x1400066cc  ja      short loc_1400066EF
0x1400066ce  mov     rcx, [rdi]
0x1400066d1  mov     rax, [rcx+10h]
0x1400066d5  cmp     rax, [rcx+8]
0x1400066d9  jz      short loc_1400066EF
0x1400066db  movzx   edx, word ptr [rax]
0x1400066de  add     rax, 2
0x1400066e2  mov     [rcx+10h], rax
0x1400066e6  movzx   ebx, dx
0x1400066e9  cmp     dx, r14w
0x1400066ed  jnz     short loc_1400066F3
0x1400066ef  movzx   ebx, r10w
0x1400066f3  mov     edx, 8; Type
0x1400066f8  movzx   ecx, bx; C
0x1400066fb  call    iswctype
0x140006700  xor     r10d, r10d
0x140006703  test    eax, eax
0x140006705  jnz     short loc_1400066B7
0x140006707  mov     eax, esi
0x140006709  mov     ecx, 0FFFDh
0x14000670e  or      esi, 2
0x140006711  cmp     bx, 2Dh ; '-'
0x140006715  cmovnz  esi, eax
0x140006718  lea     eax, [rbx-2Bh]
0x14000671b  test    cx, ax
0x14000671e  jnz     short loc_140006760
0x140006720  mov     rax, [rdi+10h]
0x140006724  inc     rax
0x140006727  mov     [rdi+10h], rax
0x14000672b  cmp     [rdi+8], r10
0x14000672f  jz      short loc_140006737
0x140006731  cmp     rax, [rdi+8]
0x140006735  ja      short loc_14000675C
0x140006737  mov     rcx, [rdi]
0x14000673a  mov     rax, [rcx+10h]
0x14000673e  cmp     rax, [rcx+8]
0x140006742  jz      short loc_14000675C
0x140006744  movzx   edx, word ptr [rax]
0x140006747  add     rax, 2
0x14000674b  mov     [rcx+10h], rax
0x14000674f  movzx   ebx, dx
0x140006752  mov     eax, 0FFFFh
0x140006757  cmp     dx, ax
0x14000675a  jnz     short loc_140006760
0x14000675c  movzx   ebx, r10w
0x140006760  mov     [rsp+0D8h+arg_8], 9F0h
0x14000676b  mov     eax, 9E6h
0x140006770  mov     [rsp+0D8h+var_A8], 0A66h
0x140006778  mov     ecx, 30h ; '0'
0x14000677d  mov     [rsp+0D8h+var_A4], 0A70h
0x140006785  mov     edx, 0FF10h
0x14000678a  mov     [rsp+0D8h+var_A0], 0AE6h
0x140006792  mov     r8d, 660h
0x140006798  mov     [rsp+0D8h+var_9C], 0AF0h
0x1400067a0  lea     r11d, [rax-80h]
0x1400067a4  mov     [rsp+0D8h+var_98], 0B66h
0x1400067ac  mov     r9d, 6F0h
0x1400067b2  mov     [rsp+0D8h+var_94], 0B70h
0x1400067ba  mov     [rsp+0D8h+var_90], 0C66h
0x1400067c2  mov     [rsp+0D8h+var_8C], 0C70h
0x1400067ca  mov     [rsp+0D8h+var_88], 0CE6h
0x1400067d2  mov     [rsp+0D8h+var_84], 0CF0h
0x1400067da  mov     [rsp+0D8h+var_80], 0D66h
0x1400067e2  mov     [rsp+0D8h+var_7C], 0D70h
0x1400067ea  mov     [rsp+0D8h+var_78], 0E50h
0x1400067f2  mov     [rsp+0D8h+var_74], 0E5Ah
0x1400067fa  mov     [rsp+0D8h+var_70], 0ED0h
0x140006802  mov     [rsp+0D8h+var_6C], 0EDAh
0x14000680a  mov     [rsp+0D8h+var_68], 0F20h
0x140006812  mov     [rsp+0D8h+var_64], 0F2Ah
0x14000681a  mov     [rsp+0D8h+var_60], 1040h
0x140006822  mov     [rsp+0D8h+var_5C], 104Ah
0x14000682a  mov     [rsp+0D8h+var_58], 17E0h
0x140006835  mov     [rsp+0D8h+var_54], 17EAh
0x140006840  mov     [rsp+0D8h+var_50], 1810h
0x14000684b  mov     [rsp+0D8h+var_4C], 0FF1Ah
0x140006856  test    ebp, 0FFFFFFEFh
0x14000685c  jnz     loc_140006B55
0x140006862  cmp     bx, cx
0x140006865  jb      loc_140006A2B
0x14000686b  cmp     bx, 3Ah ; ':'
0x14000686f  jnb     short loc_14000687B
0x140006871  movzx   eax, bx
0x140006874  sub     eax, ecx
0x140006876  jmp     loc_140006A26
0x14000687b  cmp     bx, dx
0x14000687e  jnb     loc_140006A17
0x140006884  cmp     bx, r8w
0x140006888  jb      loc_140006A2B
0x14000688e  mov     ecx, 66Ah
0x140006893  cmp     bx, cx
0x140006896  jnb     short loc_1400068A3
0x140006898  movzx   eax, bx
0x14000689b  sub     eax, r8d
0x14000689e  jmp     loc_140006A26
0x1400068a3  cmp     bx, r9w
0x1400068a7  jb      loc_140006A2B
0x1400068ad  mov     ecx, 6FAh
0x1400068b2  cmp     bx, cx
0x1400068b5  jnb     short loc_1400068C2
0x1400068b7  movzx   eax, bx
0x1400068ba  sub     eax, r9d
0x1400068bd  jmp     loc_140006A26
0x1400068c2  cmp     bx, r11w
0x1400068c6  jb      loc_140006A2B
0x1400068cc  mov     ecx, 970h
0x1400068d1  cmp     bx, cx
0x1400068d4  jnb     short loc_1400068E1
0x1400068d6  movzx   eax, bx
0x1400068d9  sub     eax, r11d
0x1400068dc  jmp     loc_140006A26
0x1400068e1  cmp     bx, ax
0x1400068e4  jb      loc_140006A2B
0x1400068ea  cmp     bx, word ptr [rsp+0D8h+arg_8]
0x1400068f2  jnb     short loc_140006901
0x1400068f4  movzx   eax, bx
0x1400068f7  sub     eax, 9E6h
0x1400068fc  jmp     loc_140006A26
0x140006901  mov     ecx, [rsp+0D8h+var_A8]
0x140006905  cmp     bx, cx
0x140006908  jb      loc_140006A2B
0x14000690e  cmp     bx, word ptr [rsp+0D8h+var_A4]
0x140006913  jb      loc_140006871
0x140006919  mov     ecx, [rsp+0D8h+var_A0]
0x14000691d  cmp     bx, cx
0x140006920  jb      loc_140006A2B
0x140006926  cmp     bx, word ptr [rsp+0D8h+var_9C]
0x14000692b  jb      loc_140006871
0x140006931  mov     ecx, [rsp+0D8h+var_98]
0x140006935  cmp     bx, cx
0x140006938  jb      loc_140006A2B
0x14000693e  cmp     bx, word ptr [rsp+0D8h+var_94]
0x140006943  jb      loc_140006871
0x140006949  mov     ecx, [rsp+0D8h+var_90]
0x14000694d  cmp     bx, cx
0x140006950  jb      loc_140006A2B
0x140006956  cmp     bx, word ptr [rsp+0D8h+var_8C]
0x14000695b  jb      loc_140006871
0x140006961  mov     ecx, [rsp+0D8h+var_88]
0x140006965  cmp     bx, cx
0x140006968  jb      loc_140006A2B
0x14000696e  cmp     bx, word ptr [rsp+0D8h+var_84]
0x140006973  jb      loc_140006871
0x140006979  mov     ecx, [rsp+0D8h+var_80]
0x14000697d  cmp     bx, cx
0x140006980  jb      loc_140006A2B
0x140006986  cmp     bx, word ptr [rsp+0D8h+var_7C]
0x14000698b  jb      loc_140006871
0x140006991  mov     ecx, [rsp+0D8h+var_78]
0x140006995  cmp     bx, cx
0x140006998  jb      loc_140006A2B
0x14000699e  cmp     bx, word ptr [rsp+0D8h+var_74]
0x1400069a3  jb      loc_140006871
0x1400069a9  mov     ecx, [rsp+0D8h+var_70]
0x1400069ad  cmp     bx, cx
0x1400069b0  jb      short loc_140006A2B
0x1400069b2  cmp     bx, word ptr [rsp+0D8h+var_6C]
0x1400069b7  jb      loc_140006871
0x1400069bd  mov     ecx, [rsp+0D8h+var_68]
0x1400069c1  cmp     bx, cx
0x1400069c4  jb      short loc_140006A2B
0x1400069c6  cmp     bx, word ptr [rsp+0D8h+var_64]
0x1400069cb  jb      loc_140006871
0x1400069d1  mov     ecx, [rsp+0D8h+var_60]
0x1400069d5  cmp     bx, cx
0x1400069d8  jb      short loc_140006A2B
0x1400069da  cmp     bx, word ptr [rsp+0D8h+var_5C]
0x1400069df  jb      loc_140006871
0x1400069e5  mov     ecx, [rsp+0D8h+var_58]
0x1400069ec  cmp     bx, cx
0x1400069ef  jb      short loc_140006A2B
0x1400069f1  cmp     bx, word ptr [rsp+0D8h+var_54]
0x1400069f9  jb      loc_140006871
0x1400069ff  mov     ecx, [rsp+0D8h+var_50]
0x140006a06  movzx   eax, bx
0x140006a09  sub     ax, cx
0x140006a0c  cmp     ax, 9
0x140006a10  ja      short loc_140006A2B
0x140006a12  jmp     loc_140006871
0x140006a17  cmp     bx, word ptr [rsp+0D8h+var_4C]
0x140006a1f  jnb     short loc_140006A2B
0x140006a21  movzx   eax, bx
0x140006a24  sub     eax, edx
0x140006a26  cmp     eax, 0FFFFFFFFh
0x140006a29  jnz     short loc_140006A4D
0x140006a2b  movzx   ecx, bx
0x140006a2e  lea     eax, [rcx-41h]
0x140006a31  cmp     eax, 19h
0x140006a34  lea     eax, [rcx-61h]
0x140006a37  jbe     short loc_140006A42
0x140006a39  cmp     eax, 19h
0x140006a3c  ja      loc_140006B49
0x140006a42  cmp     eax, 19h
0x140006a45  ja      short loc_140006A4A
0x140006a47  add     ecx, 0FFFFFFE0h
0x140006a4a  lea     eax, [rcx-37h]
0x140006a4d  test    eax, eax
0x140006a4f  jnz     loc_140006B49
0x140006a55  mov     rdx, [rdi+10h]
0x140006a59  mov     rcx, [rdi+8]
0x140006a5d  inc     rdx
0x140006a60  mov     [rdi+10h], rdx
0x140006a64  test    rcx, rcx
0x140006a67  jz      short loc_140006A74
0x140006a69  cmp     rdx, rcx
0x140006a6c  jbe     short loc_140006A74
0x140006a6e  movzx   r8d, r10w
0x140006a72  jmp     short loc_140006AB8
0x140006a74  mov     r8, [rdi]
0x140006a77  mov     rax, [r8+10h]
0x140006a7b  cmp     rax, [r8+8]
0x140006a7f  jz      short loc_140006AA1
0x140006a81  movzx   r9d, word ptr [rax]
0x140006a85  mov     r11d, 0FFFFh
0x140006a8b  add     rax, 2
0x140006a8f  mov     [r8+10h], rax
0x140006a93  mov     rdx, [rdi+10h]
  ... truncated ...
```

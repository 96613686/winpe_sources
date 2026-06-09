# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,float>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,float,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)

- ea: `0x18002c554`
- end: `0x18002cbca`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@MAEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `1654`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002ff18`

## callees

- `0x180005020`
- `0x18002a334`
- `0x18002c554`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180034bdc`
- `0x1800433e4`
- `0x1800434dc`
- `0x1800435e0`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002c86d`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002c86d`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18002c670`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18002c670`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,float>(
        _QWORD *a1,
        __int64 a2,
        double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // di
  char v8; // r13
  __int64 v9; // rdx
  char v10; // r15
  int v11; // esi
  int v12; // r12d
  __int64 v13; // rcx
  _OWORD *v14; // rax
  char *v15; // r9
  char *v16; // rdx
  unsigned int v17; // ecx
  bool v18; // al
  char v19; // di
  char *v20; // r10
  char *v21; // r11
  int v22; // r8d
  char v23; // r12
  _BYTE *v24; // r15
  char *v25; // rax
  char *v26; // rax
  struct std::locale::_Locimp *v27; // rdi
  __int64 v28; // rax
  void (__fastcall ***v29)(_QWORD, __int64); // rax
  char *v30; // rax
  int v31; // r8d
  unsigned __int64 v32; // r9
  unsigned __int64 v33; // r11
  char *v34; // r10
  int v35; // esi
  int v36; // esi
  int v37; // eax
  signed int v38; // ecx
  bool v39; // al
  int v41; // esi
  int v42; // edi
  char v43; // al
  int v44; // edi
  __int64 v45; // rax
  _QWORD *v46; // rbx
  char v47; // [rsp+39h] [rbp-CFh] BYREF
  char v48; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v49; // [rsp+3Bh] [rbp-CDh] BYREF
  int v50; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v51; // [rsp+40h] [rbp-C8h] BYREF
  int v52; // [rsp+44h] [rbp-C4h] BYREF
  int v53; // [rsp+48h] [rbp-C0h]
  int v54; // [rsp+4Ch] [rbp-BCh] BYREF
  char *v55; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v56[3]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v57; // [rsp+70h] [rbp-98h] BYREF
  struct std::locale::_Locimp *v58; // [rsp+78h] [rbp-90h]
  char *v59; // [rsp+80h] [rbp-88h] BYREF
  _DWORD v60[4]; // [rsp+88h] [rbp-80h] BYREF
  char *v61; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v62; // [rsp+A0h] [rbp-68h]
  _QWORD v63[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v64; // [rsp+128h] [rbp+20h] BYREF
  __int64 v65; // [rsp+138h] [rbp+30h]
  unsigned __int64 v66; // [rsp+140h] [rbp+38h]
  _BYTE v67[32]; // [rsp+148h] [rbp+40h] BYREF
  char v68; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v69[1384]; // [rsp+169h] [rbp+61h] BYREF
  _BYTE v70[7]; // [rsp+6D1h] [rbp+5C9h] BYREF

  v62 = a1;
  v47 = *(_BYTE *)(a4 + 10);
  if ( !v47 )
    v47 = 2;
  v7 = 0;
  v8 = 101;
  v9 = *(unsigned int *)(a4 + 4);
  v10 = 0;
  v11 = 4;
  switch ( *(_BYTE *)(a4 + 8) )
  {
    case 'A':
      v7 = 1;
      goto LABEL_27;
    case 'E':
      v7 = 1;
      goto LABEL_23;
    case 'F':
      v7 = 1;
LABEL_19:
      if ( (_DWORD)v9 == -1 )
        v9 = 6;
      v11 = 2;
      goto LABEL_28;
    case 'G':
      v7 = 1;
LABEL_13:
      if ( (_DWORD)v9 == -1 )
      {
        v9 = 6;
      }
      else if ( !(_DWORD)v9 )
      {
        v9 = 1;
      }
      v11 = 3;
      goto LABEL_28;
    case 'a':
LABEL_27:
      v8 = 112;
      goto LABEL_28;
  }
  if ( *(_BYTE *)(a4 + 8) != 101 )
  {
    if ( *(_BYTE *)(a4 + 8) != 102 )
    {
      if ( *(_BYTE *)(a4 + 8) != 103 )
      {
        v11 = 3;
        v10 = 1;
        goto LABEL_28;
      }
      goto LABEL_13;
    }
    goto LABEL_19;
  }
LABEL_23:
  if ( (_DWORD)v9 == -1 )
    v9 = 6;
  v11 = 1;
LABEL_28:
  *(_OWORD *)&v56[1] = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  v60[0] = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v53 = v13;
  v49 = (unsigned int)_o__fdsign(v13, v9, 1074, 2) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      v14 = (_OWORD *)std::to_chars(&v57, &v68, v70);
    else
      v14 = (_OWORD *)std::to_chars(&v57, &v68, v70);
  }
  else
  {
    v14 = (_OWORD *)std::to_chars(&v57, &v68, v70);
  }
  *(_OWORD *)&v56[1] = *v14;
  v15 = (char *)v56[1];
  v16 = &v68;
  v55 = &v68;
  v17 = LODWORD(v56[1]) - (unsigned int)&v68;
  v51 = v17;
  if ( v49 )
  {
    v16 = v69;
    v55 = v69;
  }
  else if ( v47 != 2 )
  {
    v51 = ++v17;
  }
  if ( v7 )
  {
    if ( v16 != (char *)v56[1] )
    {
      do
      {
        if ( (unsigned __int8)(*v16 - 97) <= 0x19u )
          *v16 -= 32;
        ++v16;
      }
      while ( v16 != v15 );
      v15 = (char *)v56[1];
      v16 = v55;
      v17 = v51;
    }
    v8 -= 32;
  }
  v18 = (_mm_cvtsi128_si32(*(__m128i *)&a3) & 0x7F800000) == 2139095040;
  v19 = 0;
  v48 = 0;
  v20 = v15;
  v56[0] = v15;
  v21 = v15;
  v61 = v15;
  v59 = v15;
  v22 = 0;
  v52 = 0;
  v54 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 15;
  LOBYTE(v64) = 0;
  if ( !v18 )
  {
    v23 = *(_BYTE *)(a4 + 11);
    if ( v23 || (v24 = (_BYTE *)(a4 + 12), *(_BYTE *)(a4 + 12)) )
    {
      v25 = v16;
      if ( v16 >= v15 )
        goto LABEL_58;
      do
      {
        if ( *v25 == 46 )
        {
          v21 = v25;
          v61 = v25;
        }
        else if ( *v25 == v8 )
        {
          v20 = v25;
          v56[0] = v25;
        }
        ++v25;
      }
      while ( v25 < v15 );
      v26 = v20;
      if ( v20 >= v21 )
LABEL_58:
        v26 = v21;
      v59 = v26;
      if ( v23 && v21 == v15 )
      {
        v51 = ++v17;
        v19 = 1;
        v48 = 1;
      }
      v24 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          v27 = *(struct std::locale::_Locimp **)(a5 + 8);
          v58 = v27;
          (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v27 + 8LL))(v27);
        }
        else
        {
          v27 = std::locale::_Init(1);
          v58 = v27;
        }
        v28 = std::use_facet<std::numpunct<unsigned short>>(&v57);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v28 + 40LL))(v28, v67);
        std::string::operator=(&v64, v67);
        std::string::~string(v67);
        if ( v27 )
        {
          v29 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v29 )
            (**v29)(v29, 1);
        }
        v30 = (char *)&v64;
        if ( v66 > 0xF )
          v30 = (char *)v64;
        v16 = v55;
        v31 = 0;
        if ( v65 )
        {
          v32 = v59 - v55;
          v33 = *v30;
          if ( v59 - v55 > v33 )
          {
            v34 = &v30[v65];
            do
            {
              v32 -= (char)v33;
              ++v31;
              if ( v30 + 1 != v34 )
                ++v30;
              v33 = *v30;
            }
            while ( v32 > v33 );
          }
        }
        v54 = v31;
        v17 = v31 + v51;
        v51 += v31;
        v15 = (char *)v56[1];
        v19 = v48;
        v20 = (char *)v56[0];
        v22 = v52;
      }
    }
    v35 = v11 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( !v36 )
      {
        v22 = v53;
LABEL_101:
        v52 = v22;
LABEL_102:
        v18 = 0;
        goto LABEL_103;
      }
      if ( v36 == 1 )
      {
        if ( *(_BYTE *)(a4 + 11) && ((*(_BYTE *)(a4 + 8) - 71) & 0xDF) == 0 )
        {
          v37 = (_DWORD)v20 - (_DWORD)v16;
          if ( !v19 )
            --v37;
          v22 = v60[0] + v53 - v37;
          v52 = v22;
          if ( v20 == v15 && COERCE_FLOAT(LODWORD(a3) & _xmm) < 1.0 && *(float *)&a3 != 0.0 )
          {
            while ( v16 < v15 )
            {
              if ( *v16 == 48 )
              {
                v52 = ++v22;
              }
              else if ( *v16 != 46 )
              {
                goto LABEL_102;
              }
              ++v16;
            }
          }
        }
        goto LABEL_102;
      }
    }
    v22 = v53;
    if ( v53 && !*(_BYTE *)(a4 + 11) && !*v24 )
    {
      do
        v56[0] = --v20;
      while ( *v20 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v38 = v22 + v17;
  v51 = v38;
  v39 = *(_BYTE *)(a4 + 13) && !*(_BYTE *)(a4 + 9) && !v18;
  LOBYTE(v50) = v39;
  v63[0] = &v47;
  v63[1] = &v49;
  v63[2] = &v50;
  v63[3] = &v51;
  v63[4] = a4;
  v63[5] = &a5;
  v63[6] = &v55;
  v63[7] = &v59;
  v63[8] = &v64;
  v63[9] = &v54;
  v63[10] = &v61;
  v63[11] = &v56[1];
  v63[12] = &v48;
  v63[13] = v56;
  v63[14] = &v52;
  if ( v39 )
  {
    `std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
      v63,
      v62,
      a2);
    std::string::~string(&v64);
    return v62;
  }
  v41 = 0;
  v42 = 0;
  v43 = *(_BYTE *)(a4 + 9);
  if ( !v43 )
    v43 = 2;
  if ( v38 < *(_DWORD *)a4 )
  {
    switch ( v43 )
    {
      case 1:
        v44 = *(_DWORD *)a4;
        break;
      case 2:
        v41 = *(_DWORD *)a4 - v38;
        goto LABEL_120;
      case 3:
        v41 = (*(_DWORD *)a4 - v38) / 2;
        v44 = *(_DWORD *)a4 - v41;
        break;
      default:
        goto LABEL_120;
    }
    v42 = v44 - v38;
  }
LABEL_120:
  v57 = a4 + 16;
  v58 = (struct std::locale::_Locimp *)*(unsigned __int8 *)(a4 + 14);
  while ( v41 > 0 )
  {
    a2 = *(_QWORD *)(std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                       v60,
                       &v57,
                       a2)
                   + 8);
    --v41;
  }
  v45 = *(_QWORD *)`std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
                     v63,
                     v60,
                     a2);
  while ( v42 > 0 )
  {
    v45 = *(_QWORD *)(std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                        v60,
                        &v57,
                        v45)
                    + 8);
    --v42;
  }
  v46 = v62;
  *v62 = v45;
  std::string::~string(&v64);
  return v46;
}

```

## disassembly

```asm
0x18002c554  mov     rax, rsp
0x18002c557  mov     [rax+10h], rbx
0x18002c55b  push    rbp
0x18002c55c  push    rsi
0x18002c55d  push    rdi
0x18002c55e  push    r12
0x18002c560  push    r13
0x18002c562  push    r14
0x18002c564  push    r15
0x18002c566  lea     rbp, [rax-628h]
0x18002c56d  sub     rsp, 6F0h
0x18002c574  movaps  xmmword ptr [rax-48h], xmm6
0x18002c578  mov     rax, cs:__security_cookie
0x18002c57f  xor     rax, rsp
0x18002c582  mov     [rbp+620h+var_50], rax
0x18002c589  mov     r14, r9
0x18002c58c  movaps  xmm6, xmm2
0x18002c58f  mov     rbx, rdx
0x18002c592  mov     [rbp+620h+var_688], rcx
0x18002c596  mov     al, [r9+0Ah]
0x18002c59a  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18002c59e  mov     r9d, 2
0x18002c5a4  test    al, al
0x18002c5a6  jnz     short loc_18002C5AD
0x18002c5a8  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18002c5ad  xor     dil, dil
0x18002c5b0  mov     r13b, 65h ; 'e'
0x18002c5b3  mov     edx, [r14+4]
0x18002c5b7  xor     r15b, r15b
0x18002c5ba  movsx   ecx, byte ptr [r14+8]
0x18002c5bf  mov     esi, 4
0x18002c5c4  lea     r8d, [rsi-3]
0x18002c5c8  sub     ecx, 41h ; 'A'
0x18002c5cb  jz      short loc_18002C639
0x18002c5cd  sub     ecx, esi
0x18002c5cf  jz      short loc_18002C626
0x18002c5d1  sub     ecx, r8d
0x18002c5d4  jz      short loc_18002C613
0x18002c5d6  sub     ecx, r8d
0x18002c5d9  jz      short loc_18002C5F7
0x18002c5db  sub     ecx, 1Ah
0x18002c5de  jz      short loc_18002C63C
0x18002c5e0  sub     ecx, esi
0x18002c5e2  jz      short loc_18002C629
0x18002c5e4  sub     ecx, r8d
0x18002c5e7  jz      short loc_18002C616
0x18002c5e9  cmp     ecx, r8d
0x18002c5ec  jz      short loc_18002C5FA
0x18002c5ee  lea     esi, [r8+2]
0x18002c5f2  mov     r15b, r8b
0x18002c5f5  jmp     short loc_18002C63F
0x18002c5f7  mov     dil, r8b
0x18002c5fa  cmp     edx, 0FFFFFFFFh
0x18002c5fd  jnz     short loc_18002C606
0x18002c5ff  mov     edx, 6
0x18002c604  jmp     short loc_18002C60C
0x18002c606  test    edx, edx
0x18002c608  cmovz   edx, r8d
0x18002c60c  mov     esi, 3
0x18002c611  jmp     short loc_18002C63F
0x18002c613  mov     dil, r8b
0x18002c616  mov     eax, 6
0x18002c61b  cmp     edx, 0FFFFFFFFh
0x18002c61e  cmovz   edx, eax
0x18002c621  mov     esi, r9d
0x18002c624  jmp     short loc_18002C63F
0x18002c626  mov     dil, r8b
0x18002c629  mov     eax, 6
0x18002c62e  cmp     edx, 0FFFFFFFFh
0x18002c631  cmovz   edx, eax
0x18002c634  mov     esi, r8d
0x18002c637  jmp     short loc_18002C63F
0x18002c639  mov     dil, r8b
0x18002c63c  mov     r13b, 70h ; 'p'
0x18002c63f  xorps   xmm0, xmm0
0x18002c642  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18002c647  mov     r12d, edx
0x18002c64a  mov     r8d, 432h
0x18002c650  cmp     edx, r8d
0x18002c653  cmovg   r12d, r8d
0x18002c657  mov     [rbp+620h+var_6A0], r12d
0x18002c65b  lea     ecx, [rdx-432h]
0x18002c661  xor     eax, eax
0x18002c663  cmp     edx, r8d
0x18002c666  cmovle  ecx, eax
0x18002c669  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18002c66d  movaps  xmm0, xmm6
0x18002c670  call    cs:__imp__o__fdsign
0x18002c676  mov     edx, eax
0x18002c678  test    eax, eax
0x18002c67a  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18002c67f  ucomiss xmm6, xmm6
0x18002c682  setp    al
0x18002c685  cmp     al, 1
0x18002c687  jnz     short loc_18002C6BE
0x18002c689  lea     rax, [rbp+620h+var_5C0]
0x18002c68d  lea     rcx, [rbp+620h+var_5BF]
0x18002c691  test    edx, edx
0x18002c693  cmovz   rcx, rax
0x18002c697  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x18002c69c  mov     eax, dword ptr cs:aNan; "nan"
0x18002c6a2  mov     [rcx], ax
0x18002c6a5  mov     al, byte ptr cs:aNan+2; "n"
0x18002c6ab  mov     [rcx+2], al
0x18002c6ae  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002c6b3  add     r9, 3
0x18002c6b7  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x18002c6bc  jmp     short loc_18002C709
0x18002c6be  movaps  xmm3, xmm6
0x18002c6c1  lea     r8, [rbp+620h+var_57]
0x18002c6c8  lea     rdx, [rbp+620h+var_5C0]
0x18002c6cc  lea     rcx, [rsp+720h+var_6B8]
0x18002c6d1  cmp     r12d, 0FFFFFFFFh
0x18002c6d5  jnz     short loc_18002C6EE
0x18002c6d7  test    r15b, r15b
0x18002c6da  jz      short loc_18002C6E3
0x18002c6dc  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x18002c6e1  jmp     short loc_18002C6FC
0x18002c6e3  mov     [rsp+720h+var_700], esi
0x18002c6e7  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x18002c6ec  jmp     short loc_18002C6FC
0x18002c6ee  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18002c6f3  mov     [rsp+720h+var_700], esi
0x18002c6f7  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x18002c6fc  movups  xmm0, xmmword ptr [rax]
0x18002c6ff  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18002c704  movq    r9, xmm0
0x18002c709  lea     rdx, [rbp+620h+var_5C0]
0x18002c70d  mov     [rsp+720h+var_6D8], rdx
0x18002c712  mov     ecx, r9d
0x18002c715  sub     ecx, edx
0x18002c717  mov     [rsp+720h+var_6E8], ecx
0x18002c71b  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18002c720  jz      short loc_18002C72D
0x18002c722  lea     rdx, [rbp+620h+var_5BF]
0x18002c726  mov     [rsp+720h+var_6D8], rdx
0x18002c72b  jmp     short loc_18002C73A
0x18002c72d  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18002c732  jz      short loc_18002C73A
0x18002c734  inc     ecx
0x18002c736  mov     [rsp+720h+var_6E8], ecx
0x18002c73a  test    dil, dil
0x18002c73d  jz      short loc_18002C76C
0x18002c73f  cmp     rdx, r9
0x18002c742  jz      short loc_18002C768
0x18002c744  mov     cl, [rdx]
0x18002c746  lea     eax, [rcx-61h]
0x18002c749  cmp     al, 19h
0x18002c74b  ja      short loc_18002C752
0x18002c74d  sub     cl, 20h ; ' '
0x18002c750  mov     [rdx], cl
0x18002c752  inc     rdx
0x18002c755  cmp     rdx, r9
0x18002c758  jnz     short loc_18002C744
0x18002c75a  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002c75f  mov     rdx, [rsp+720h+var_6D8]
0x18002c764  mov     ecx, [rsp+720h+var_6E8]
0x18002c768  add     r13b, 0E0h
0x18002c76c  movd    eax, xmm6
0x18002c770  mov     r8d, 7F800000h
0x18002c776  and     eax, r8d
0x18002c779  cmp     eax, r8d
0x18002c77c  setnz   al
0x18002c77f  xor     al, 1
0x18002c781  mov     byte ptr [rsp+720h+var_6F0], al
0x18002c785  mov     dil, 0
0x18002c788  mov     byte ptr [rsp+720h+var_6F0+2], dil
0x18002c78d  mov     r10, r9
0x18002c790  mov     qword ptr [rsp+720h+var_6D0], r9
0x18002c795  mov     r11, r9
0x18002c798  mov     [rbp+620h+var_690], r9
0x18002c79c  mov     [rsp+720h+var_6A8], r9
0x18002c7a1  mov     r8d, 0
0x18002c7a7  mov     [rsp+720h+var_6E4], r8d
0x18002c7ac  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002c7b1  xorps   xmm0, xmm0
0x18002c7b4  movups  [rbp+620h+var_600], xmm0
0x18002c7b8  mov     [rbp+620h+var_5F0], r8
0x18002c7bc  mov     [rbp+620h+var_5E8], 0Fh
0x18002c7c4  mov     byte ptr [rbp+620h+var_600], dil
0x18002c7c8  jnz     loc_18002CA18
0x18002c7ce  mov     r12b, [r14+0Bh]
0x18002c7d2  test    r12b, r12b
0x18002c7d5  jnz     short loc_18002C7E4
0x18002c7d7  lea     r15, [r14+0Ch]
0x18002c7db  cmp     [r15], r12b
0x18002c7de  jz      loc_18002C950
0x18002c7e4  mov     rax, rdx
0x18002c7e7  cmp     rdx, r9
0x18002c7ea  jnb     short loc_18002C817
0x18002c7ec  cmp     byte ptr [rax], 2Eh ; '.'
0x18002c7ef  jnz     short loc_18002C7FA
0x18002c7f1  mov     r11, rax
0x18002c7f4  mov     [rbp+620h+var_690], rax
0x18002c7f8  jmp     short loc_18002C807
0x18002c7fa  cmp     [rax], r13b
0x18002c7fd  jnz     short loc_18002C807
0x18002c7ff  mov     r10, rax
0x18002c802  mov     qword ptr [rsp+720h+var_6D0], rax
0x18002c807  inc     rax
0x18002c80a  cmp     rax, r9
0x18002c80d  jb      short loc_18002C7EC
0x18002c80f  cmp     r10, r11
0x18002c812  mov     rax, r10
0x18002c815  jb      short loc_18002C81A
0x18002c817  mov     rax, r11
0x18002c81a  mov     [rsp+720h+var_6A8], rax
0x18002c81f  test    r12b, r12b
0x18002c822  jz      short loc_18002C837
0x18002c824  cmp     r11, r9
0x18002c827  jnz     short loc_18002C837
0x18002c829  inc     ecx
0x18002c82b  mov     [rsp+720h+var_6E8], ecx
0x18002c82f  mov     dil, 1
0x18002c832  mov     byte ptr [rsp+720h+var_6F0+2], dil
0x18002c837  lea     r15, [r14+0Ch]
0x18002c83b  cmp     byte ptr [r15], 0
0x18002c83f  jz      loc_18002C950
0x18002c845  mov     rax, [rbp+620h+arg_20]
0x18002c84c  test    rax, rax
0x18002c84f  jz      short loc_18002C86B
0x18002c851  mov     rdi, [rax+8]
0x18002c855  mov     [rsp+720h+var_6B0], rdi
0x18002c85a  mov     rax, [rdi]
0x18002c85d  mov     rcx, rdi
0x18002c860  mov     rax, [rax+8]
0x18002c864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c869  jmp     short loc_18002C87B
0x18002c86b  mov     cl, 1
0x18002c86d  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002c873  mov     rdi, rax
0x18002c876  mov     [rsp+720h+var_6B0], rax
0x18002c87b  lea     rcx, [rsp+720h+var_6B8]
0x18002c880  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x18002c885  mov     rcx, rax
0x18002c888  mov     rax, [rax]
0x18002c88b  lea     rdx, [rbp+620h+var_5E0]
0x18002c88f  mov     rax, [rax+28h]
0x18002c893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c898  lea     rdx, [rbp+620h+var_5E0]
0x18002c89c  lea     rcx, [rbp+620h+var_600]
0x18002c8a0  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002c8a5  lea     rcx, [rbp+620h+var_5E0]
0x18002c8a9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c8ae  nop
0x18002c8af  test    rdi, rdi
0x18002c8b2  jz      short loc_18002C8DB
0x18002c8b4  mov     rax, [rdi]
0x18002c8b7  mov     rcx, rdi
0x18002c8ba  mov     rax, [rax+10h]
0x18002c8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8c3  mov     rcx, rax
0x18002c8c6  test    rax, rax
0x18002c8c9  jz      short loc_18002C8DB
0x18002c8cb  mov     rax, [rax]
0x18002c8ce  mov     edx, 1
0x18002c8d3  mov     rax, [rax]
0x18002c8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8db  lea     rax, [rbp+620h+var_600]
0x18002c8df  cmp     [rbp+620h+var_5E8], 0Fh
0x18002c8e4  cmova   rax, qword ptr [rbp+620h+var_600]
0x18002c8e9  mov     r10, [rbp+620h+var_5F0]
0x18002c8ed  mov     rdx, [rsp+720h+var_6D8]
0x18002c8f2  xor     r8d, r8d
0x18002c8f5  test    r10, r10
0x18002c8f8  jz      short loc_18002C92C
0x18002c8fa  mov     r9, [rsp+720h+var_6A8]
0x18002c8ff  sub     r9, rdx
0x18002c902  movsx   r11, byte ptr [rax]
0x18002c906  cmp     r9, r11
0x18002c909  jbe     short loc_18002C92C
0x18002c90b  add     r10, rax
0x18002c90e  movsx   rcx, r11b
0x18002c912  sub     r9, rcx
0x18002c915  inc     r8d
0x18002c918  lea     rcx, [rax+1]
0x18002c91c  cmp     rcx, r10
0x18002c91f  cmovnz  rax, rcx
0x18002c923  movsx   r11, byte ptr [rax]
0x18002c927  cmp     r9, r11
0x18002c92a  ja      short loc_18002C90E
0x18002c92c  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002c931  mov     ecx, [rsp+720h+var_6E8]
0x18002c935  add     ecx, r8d
0x18002c938  mov     [rsp+720h+var_6E8], ecx
0x18002c93c  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002c941  mov     dil, byte ptr [rsp+720h+var_6F0+2]
0x18002c946  mov     r10, qword ptr [rsp+720h+var_6D0]
0x18002c94b  mov     r8d, [rsp+720h+var_6E4]
0x18002c950  sub     esi, 1
0x18002c953  jz      loc_18002C9E4
0x18002c959  sub     esi, 1
0x18002c95c  jz      loc_18002CA0A
0x18002c962  cmp     esi, 1
0x18002c965  jnz     short loc_18002C9E4
0x18002c967  cmp     byte ptr [r14+0Bh], 0
0x18002c96c  jz      loc_18002CA14
0x18002c972  mov     al, [r14+8]
0x18002c976  sub     al, 47h ; 'G'
0x18002c978  test    al, 0DFh
  ... truncated ...
```

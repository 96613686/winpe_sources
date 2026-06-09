# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,float>(std::back_insert_iterator<std::_Fmt_buffer<char>>,float,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x180024284`
- end: `0x180024946`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@MAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1730`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180024284`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002b39c`
- `0x18002f880`
- `0x18002f978`
- `0x18002fa7c`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180024599`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180024599`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x1800243a1`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x1800243a1`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,float>(
        _QWORD *a1,
        __int64 a2,
        double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // si
  char v8; // r13
  __int64 v9; // rdx
  char v10; // r15
  int v11; // edi
  int v12; // r12d
  __int64 v13; // rcx
  _OWORD *v14; // rax
  char *v15; // r9
  char *v16; // rdx
  unsigned int v17; // ecx
  bool v18; // al
  char v19; // r15
  char *v20; // r10
  char *v21; // r11
  int v22; // r8d
  char v23; // r12
  _BYTE *v24; // rsi
  char *v25; // rax
  char *v26; // rax
  __int64 v27; // rax
  void (__fastcall ***v28)(_QWORD, __int64); // rax
  char *v29; // rax
  int v30; // r8d
  unsigned __int64 v31; // r9
  unsigned __int64 v32; // r11
  char *v33; // r10
  char *v34; // rcx
  int v35; // edi
  int v36; // edi
  int v37; // eax
  signed int v38; // ecx
  bool v39; // al
  int v41; // esi
  int v42; // edi
  char v43; // al
  int v44; // edi
  char *v45; // r15
  __int64 v46; // r14
  char *i; // r12
  char v48; // r13
  __int64 v49; // rbx
  char *j; // rsi
  char v51; // r12
  _QWORD *v52; // rdi
  char v53; // [rsp+39h] [rbp-CFh] BYREF
  char v54; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v55; // [rsp+3Bh] [rbp-CDh] BYREF
  int v56; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v57; // [rsp+40h] [rbp-C8h] BYREF
  int v58; // [rsp+44h] [rbp-C4h] BYREF
  int v59; // [rsp+48h] [rbp-C0h]
  int v60; // [rsp+4Ch] [rbp-BCh] BYREF
  char *v61; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v62[3]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+70h] [rbp-98h] BYREF
  char *v64; // [rsp+78h] [rbp-90h] BYREF
  char v65[8]; // [rsp+80h] [rbp-88h] BYREF
  struct std::locale::_Locimp *v66; // [rsp+88h] [rbp-80h]
  char *v67; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v68; // [rsp+98h] [rbp-70h]
  _QWORD v69[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v70; // [rsp+128h] [rbp+20h] BYREF
  __int64 v71; // [rsp+138h] [rbp+30h]
  unsigned __int64 v72; // [rsp+140h] [rbp+38h]
  _BYTE v73[32]; // [rsp+148h] [rbp+40h] BYREF
  char v74; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v75[1384]; // [rsp+169h] [rbp+61h] BYREF
  _BYTE v76[7]; // [rsp+6D1h] [rbp+5C9h] BYREF

  v68 = a1;
  v53 = *(_BYTE *)(a4 + 10);
  if ( !v53 )
    v53 = 2;
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
  *(_OWORD *)&v62[1] = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  LODWORD(v63) = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v59 = v13;
  v55 = (unsigned int)_o__fdsign(v13, v9, 1074, 2) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      v14 = (_OWORD *)std::to_chars(v65, &v74, v76);
    else
      v14 = (_OWORD *)std::to_chars(v65, &v74, v76);
  }
  else
  {
    v14 = (_OWORD *)std::to_chars(v65, &v74, v76);
  }
  *(_OWORD *)&v62[1] = *v14;
  v15 = (char *)v62[1];
  v16 = &v74;
  v61 = &v74;
  v17 = LODWORD(v62[1]) - (unsigned int)&v74;
  v57 = v17;
  if ( v55 )
  {
    v16 = v75;
    v61 = v75;
  }
  else if ( v53 != 2 )
  {
    v57 = ++v17;
  }
  if ( v7 )
  {
    if ( v16 != (char *)v62[1] )
    {
      do
      {
        if ( (unsigned __int8)(*v16 - 97) <= 0x19u )
          *v16 -= 32;
        ++v16;
      }
      while ( v16 != v15 );
      v15 = (char *)v62[1];
      v16 = v61;
      v17 = v57;
    }
    v8 -= 32;
  }
  v18 = (_mm_cvtsi128_si32(*(__m128i *)&a3) & 0x7F800000) == 2139095040;
  v19 = 0;
  v54 = 0;
  v20 = v15;
  v62[0] = v15;
  v21 = v15;
  v67 = v15;
  v64 = v15;
  v22 = 0;
  v58 = 0;
  v60 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 15;
  LOBYTE(v70) = 0;
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
          v67 = v25;
        }
        else if ( *v25 == v8 )
        {
          v20 = v25;
          v62[0] = v25;
        }
        ++v25;
      }
      while ( v25 < v15 );
      v26 = v20;
      if ( v20 >= v21 )
LABEL_58:
        v26 = v21;
      v64 = v26;
      if ( v23 && v21 == v15 )
      {
        v57 = ++v17;
        v19 = 1;
        v54 = 1;
      }
      v24 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          v66 = *(struct std::locale::_Locimp **)(a5 + 8);
          (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v66 + 8LL))(v66);
        }
        else
        {
          v66 = std::locale::_Init(1);
        }
        v27 = std::use_facet<std::numpunct<char>>(v65);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 40LL))(v27, v73);
        std::string::operator=(&v70, v73);
        std::string::~string(v73);
        if ( v66 )
        {
          v28 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v66 + 16LL))(v66);
          if ( v28 )
            (**v28)(v28, 1);
        }
        v29 = (char *)&v70;
        if ( v72 > 0xF )
          v29 = (char *)v70;
        v16 = v61;
        v30 = 0;
        if ( v71 )
        {
          v31 = v64 - v61;
          v32 = *v29;
          if ( v64 - v61 > v32 )
          {
            v33 = &v29[v71];
            do
            {
              v31 -= (char)v32;
              ++v30;
              v34 = v29 + 1;
              if ( v29 + 1 == v33 )
                v34 = v29;
              v29 = v34;
              v32 = *v34;
            }
            while ( v31 > v32 );
          }
        }
        v60 = v30;
        v17 = v30 + v57;
        v57 += v30;
        v15 = (char *)v62[1];
        v19 = v54;
        v20 = (char *)v62[0];
        v22 = v58;
      }
    }
    v35 = v11 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( !v36 )
      {
        v22 = v59;
LABEL_101:
        v58 = v22;
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
          v22 = v63 + v59 - v37;
          v58 = v22;
          if ( v20 == v15 && COERCE_FLOAT(LODWORD(a3) & _xmm) < 1.0 && *(float *)&a3 != 0.0 )
          {
            while ( v16 < v15 )
            {
              if ( *v16 == 48 )
              {
                v58 = ++v22;
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
    v22 = v59;
    if ( v59 && !*(_BYTE *)(a4 + 11) && !*v24 )
    {
      do
        v62[0] = --v20;
      while ( *v20 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v38 = v22 + v17;
  v57 = v38;
  v39 = *(_BYTE *)(a4 + 13) && !*(_BYTE *)(a4 + 9) && !v18;
  LOBYTE(v56) = v39;
  v69[0] = &v53;
  v69[1] = &v55;
  v69[2] = &v56;
  v69[3] = &v57;
  v69[4] = a4;
  v69[5] = &a5;
  v69[6] = &v61;
  v69[7] = &v64;
  v69[8] = &v70;
  v69[9] = &v60;
  v69[10] = &v67;
  v69[11] = &v62[1];
  v69[12] = &v54;
  v69[13] = v62;
  v69[14] = &v58;
  if ( v39 )
  {
    `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
      v69,
      v68,
      a2);
    std::string::~string(&v70);
    return v68;
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
  v45 = (char *)(a4 + 15);
  v46 = a4 + 15 + *(unsigned __int8 *)(a4 + 14);
  while ( v41 > 0 )
  {
    for ( i = v45; i != (char *)v46; ++i )
    {
      v48 = *i;
      if ( (unsigned __int64)(*(_QWORD *)(a2 + 16) + 1LL) > *(_QWORD *)(a2 + 24) )
        (**(void (__fastcall ***)(__int64))a2)(a2);
      *(_BYTE *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 8)) = v48;
      ++*(_QWORD *)(a2 + 16);
    }
    --v41;
  }
  v49 = *(_QWORD *)`std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
                     v69,
                     &v63,
                     a2);
  while ( v42 > 0 )
  {
    for ( j = v45; j != (char *)v46; ++j )
    {
      v51 = *j;
      if ( (unsigned __int64)(*(_QWORD *)(v49 + 16) + 1LL) > *(_QWORD *)(v49 + 24) )
        (**(void (__fastcall ***)(__int64))v49)(v49);
      *(_BYTE *)(*(_QWORD *)(v49 + 8) + (*(_QWORD *)(v49 + 16))++) = v51;
    }
    --v42;
  }
  v52 = v68;
  *v68 = v49;
  std::string::~string(&v70);
  return v52;
}

```

## disassembly

```asm
0x180024284  mov     rax, rsp
0x180024287  mov     [rax+10h], rbx
0x18002428b  push    rbp
0x18002428c  push    rsi
0x18002428d  push    rdi
0x18002428e  push    r12
0x180024290  push    r13
0x180024292  push    r14
0x180024294  push    r15
0x180024296  lea     rbp, [rax-628h]
0x18002429d  sub     rsp, 6F0h
0x1800242a4  movaps  xmmword ptr [rax-48h], xmm6
0x1800242a8  mov     rax, cs:__security_cookie
0x1800242af  xor     rax, rsp
0x1800242b2  mov     [rbp+620h+var_50], rax
0x1800242b9  mov     r14, r9
0x1800242bc  movaps  xmm6, xmm2
0x1800242bf  mov     rbx, rdx
0x1800242c2  mov     [rbp+620h+var_690], rcx
0x1800242c6  mov     al, [r9+0Ah]
0x1800242ca  mov     byte ptr [rsp+720h+var_6F0+1], al
0x1800242ce  mov     r9d, 2
0x1800242d4  test    al, al
0x1800242d6  jnz     short loc_1800242DD
0x1800242d8  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x1800242dd  xor     sil, sil
0x1800242e0  mov     r13b, 65h ; 'e'
0x1800242e3  mov     edx, [r14+4]
0x1800242e7  xor     r15b, r15b
0x1800242ea  movsx   ecx, byte ptr [r14+8]
0x1800242ef  mov     edi, 4
0x1800242f4  lea     r8d, [rdi-3]
0x1800242f8  sub     ecx, 41h ; 'A'
0x1800242fb  jz      short loc_180024369
0x1800242fd  sub     ecx, edi
0x1800242ff  jz      short loc_180024356
0x180024301  sub     ecx, r8d
0x180024304  jz      short loc_180024343
0x180024306  sub     ecx, r8d
0x180024309  jz      short loc_180024327
0x18002430b  sub     ecx, 1Ah
0x18002430e  jz      short loc_18002436C
0x180024310  sub     ecx, edi
0x180024312  jz      short loc_180024359
0x180024314  sub     ecx, r8d
0x180024317  jz      short loc_180024346
0x180024319  cmp     ecx, r8d
0x18002431c  jz      short loc_18002432A
0x18002431e  lea     edi, [r8+2]
0x180024322  mov     r15b, r8b
0x180024325  jmp     short loc_18002436F
0x180024327  mov     sil, r8b
0x18002432a  cmp     edx, 0FFFFFFFFh
0x18002432d  jnz     short loc_180024336
0x18002432f  mov     edx, 6
0x180024334  jmp     short loc_18002433C
0x180024336  test    edx, edx
0x180024338  cmovz   edx, r8d
0x18002433c  mov     edi, 3
0x180024341  jmp     short loc_18002436F
0x180024343  mov     sil, r8b
0x180024346  mov     eax, 6
0x18002434b  cmp     edx, 0FFFFFFFFh
0x18002434e  cmovz   edx, eax
0x180024351  mov     edi, r9d
0x180024354  jmp     short loc_18002436F
0x180024356  mov     sil, r8b
0x180024359  mov     eax, 6
0x18002435e  cmp     edx, 0FFFFFFFFh
0x180024361  cmovz   edx, eax
0x180024364  mov     edi, r8d
0x180024367  jmp     short loc_18002436F
0x180024369  mov     sil, r8b
0x18002436c  mov     r13b, 70h ; 'p'
0x18002436f  xorps   xmm0, xmm0
0x180024372  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x180024377  mov     r12d, edx
0x18002437a  mov     r8d, 432h
0x180024380  cmp     edx, r8d
0x180024383  cmovg   r12d, r8d
0x180024387  mov     dword ptr [rsp+720h+var_6B8], r12d
0x18002438c  lea     ecx, [rdx-432h]
0x180024392  xor     eax, eax
0x180024394  cmp     edx, r8d
0x180024397  cmovle  ecx, eax
0x18002439a  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18002439e  movaps  xmm0, xmm6
0x1800243a1  call    cs:__imp__o__fdsign
0x1800243a7  mov     edx, eax
0x1800243a9  test    eax, eax
0x1800243ab  setnz   byte ptr [rsp+720h+var_6F0+3]
0x1800243b0  ucomiss xmm6, xmm6
0x1800243b3  setp    al
0x1800243b6  cmp     al, 1
0x1800243b8  jnz     short loc_1800243EF
0x1800243ba  lea     rax, [rbp+620h+var_5C0]
0x1800243be  lea     rcx, [rbp+620h+var_5BF]
0x1800243c2  test    edx, edx
0x1800243c4  cmovz   rcx, rax
0x1800243c8  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x1800243cd  mov     eax, dword ptr cs:aNan; "nan"
0x1800243d3  mov     [rcx], ax
0x1800243d6  mov     al, byte ptr cs:aNan+2; "n"
0x1800243dc  mov     [rcx+2], al
0x1800243df  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x1800243e4  add     r9, 3
0x1800243e8  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x1800243ed  jmp     short loc_18002443A
0x1800243ef  movaps  xmm3, xmm6
0x1800243f2  lea     r8, [rbp+620h+var_57]
0x1800243f9  lea     rdx, [rbp+620h+var_5C0]
0x1800243fd  lea     rcx, [rsp+720h+var_6A8]
0x180024402  cmp     r12d, 0FFFFFFFFh
0x180024406  jnz     short loc_18002441F
0x180024408  test    r15b, r15b
0x18002440b  jz      short loc_180024414
0x18002440d  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x180024412  jmp     short loc_18002442D
0x180024414  mov     [rsp+720h+var_700], edi
0x180024418  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x18002441d  jmp     short loc_18002442D
0x18002441f  mov     dword ptr [rsp+720h+var_6F8], r12d
0x180024424  mov     [rsp+720h+var_700], edi
0x180024428  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x18002442d  movups  xmm0, xmmword ptr [rax]
0x180024430  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x180024435  movq    r9, xmm0
0x18002443a  lea     rdx, [rbp+620h+var_5C0]
0x18002443e  mov     [rsp+720h+var_6D8], rdx
0x180024443  mov     ecx, r9d
0x180024446  sub     ecx, edx
0x180024448  mov     [rsp+720h+var_6E8], ecx
0x18002444c  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x180024451  jz      short loc_18002445E
0x180024453  lea     rdx, [rbp+620h+var_5BF]
0x180024457  mov     [rsp+720h+var_6D8], rdx
0x18002445c  jmp     short loc_18002446B
0x18002445e  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x180024463  jz      short loc_18002446B
0x180024465  inc     ecx
0x180024467  mov     [rsp+720h+var_6E8], ecx
0x18002446b  test    sil, sil
0x18002446e  jz      short loc_18002449D
0x180024470  cmp     rdx, r9
0x180024473  jz      short loc_180024499
0x180024475  mov     cl, [rdx]
0x180024477  lea     eax, [rcx-61h]
0x18002447a  cmp     al, 19h
0x18002447c  ja      short loc_180024483
0x18002447e  sub     cl, 20h ; ' '
0x180024481  mov     [rdx], cl
0x180024483  inc     rdx
0x180024486  cmp     rdx, r9
0x180024489  jnz     short loc_180024475
0x18002448b  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x180024490  mov     rdx, [rsp+720h+var_6D8]
0x180024495  mov     ecx, [rsp+720h+var_6E8]
0x180024499  add     r13b, 0E0h
0x18002449d  movd    eax, xmm6
0x1800244a1  mov     r8d, 7F800000h
0x1800244a7  and     eax, r8d
0x1800244aa  cmp     eax, r8d
0x1800244ad  setnz   al
0x1800244b0  xor     al, 1
0x1800244b2  mov     byte ptr [rsp+720h+var_6F0], al
0x1800244b6  mov     r15b, 0
0x1800244b9  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x1800244be  mov     r10, r9
0x1800244c1  mov     qword ptr [rsp+720h+var_6D0], r9
0x1800244c6  mov     r11, r9
0x1800244c9  mov     [rbp+620h+var_698], r9
0x1800244cd  mov     [rsp+720h+var_6B0], r9
0x1800244d2  mov     r8d, 0
0x1800244d8  mov     [rsp+720h+var_6E4], r8d
0x1800244dd  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x1800244e2  xorps   xmm0, xmm0
0x1800244e5  movups  [rbp+620h+var_600], xmm0
0x1800244e9  mov     [rbp+620h+var_5F0], r8
0x1800244ed  mov     [rbp+620h+var_5E8], 0Fh
0x1800244f5  mov     byte ptr [rbp+620h+var_600], r8b
0x1800244f9  jnz     loc_180024744
0x1800244ff  mov     r12b, [r14+0Bh]
0x180024503  test    r12b, r12b
0x180024506  jnz     short loc_180024515
0x180024508  lea     rsi, [r14+0Ch]
0x18002450c  cmp     [rsi], r12b
0x18002450f  jz      loc_18002467C
0x180024515  mov     rax, rdx
0x180024518  cmp     rdx, r9
0x18002451b  jnb     short loc_180024548
0x18002451d  cmp     byte ptr [rax], 2Eh ; '.'
0x180024520  jnz     short loc_18002452B
0x180024522  mov     r11, rax
0x180024525  mov     [rbp+620h+var_698], rax
0x180024529  jmp     short loc_180024538
0x18002452b  cmp     [rax], r13b
0x18002452e  jnz     short loc_180024538
0x180024530  mov     r10, rax
0x180024533  mov     qword ptr [rsp+720h+var_6D0], rax
0x180024538  inc     rax
0x18002453b  cmp     rax, r9
0x18002453e  jb      short loc_18002451D
0x180024540  cmp     r10, r11
0x180024543  mov     rax, r10
0x180024546  jb      short loc_18002454B
0x180024548  mov     rax, r11
0x18002454b  mov     [rsp+720h+var_6B0], rax
0x180024550  test    r12b, r12b
0x180024553  jz      short loc_180024568
0x180024555  cmp     r11, r9
0x180024558  jnz     short loc_180024568
0x18002455a  inc     ecx
0x18002455c  mov     [rsp+720h+var_6E8], ecx
0x180024560  mov     r15b, 1
0x180024563  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x180024568  lea     rsi, [r14+0Ch]
0x18002456c  cmp     byte ptr [rsi], 0
0x18002456f  jz      loc_18002467C
0x180024575  mov     rax, [rbp+620h+arg_20]
0x18002457c  test    rax, rax
0x18002457f  jz      short loc_180024597
0x180024581  mov     rcx, [rax+8]
0x180024585  mov     [rbp+620h+var_6A0], rcx
0x180024589  mov     rax, [rcx]
0x18002458c  mov     rax, [rax+8]
0x180024590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024595  jmp     short loc_1800245A3
0x180024597  mov     cl, 1
0x180024599  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002459f  mov     [rbp+620h+var_6A0], rax
0x1800245a3  lea     rcx, [rsp+720h+var_6A8]
0x1800245a8  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x1800245ad  mov     rcx, rax
0x1800245b0  mov     rax, [rax]
0x1800245b3  lea     rdx, [rbp+620h+var_5E0]
0x1800245b7  mov     rax, [rax+28h]
0x1800245bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245c0  lea     rdx, [rbp+620h+var_5E0]
0x1800245c4  lea     rcx, [rbp+620h+var_600]
0x1800245c8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800245cd  lea     rcx, [rbp+620h+var_5E0]
0x1800245d1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800245d6  nop
0x1800245d7  mov     rcx, [rbp+620h+var_6A0]
0x1800245db  test    rcx, rcx
0x1800245de  jz      short loc_180024604
0x1800245e0  mov     rax, [rcx]
0x1800245e3  mov     rax, [rax+10h]
0x1800245e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245ec  mov     rcx, rax
0x1800245ef  test    rax, rax
0x1800245f2  jz      short loc_180024604
0x1800245f4  mov     rax, [rax]
0x1800245f7  mov     edx, 1
0x1800245fc  mov     rax, [rax]
0x1800245ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024604  lea     rax, [rbp+620h+var_600]
0x180024608  cmp     [rbp+620h+var_5E8], 0Fh
0x18002460d  cmova   rax, qword ptr [rbp+620h+var_600]
0x180024612  mov     r10, [rbp+620h+var_5F0]
0x180024616  mov     rdx, [rsp+720h+var_6D8]
0x18002461b  xor     r8d, r8d
0x18002461e  test    r10, r10
0x180024621  jz      short loc_180024658
0x180024623  mov     r9, [rsp+720h+var_6B0]
0x180024628  sub     r9, rdx
0x18002462b  movsx   r11, byte ptr [rax]
0x18002462f  cmp     r9, r11
0x180024632  jbe     short loc_180024658
0x180024634  add     r10, rax
0x180024637  movsx   rcx, r11b
0x18002463b  sub     r9, rcx
0x18002463e  inc     r8d
0x180024641  lea     rcx, [rax+1]
0x180024645  cmp     rcx, r10
0x180024648  cmovz   rcx, rax
0x18002464c  mov     rax, rcx
0x18002464f  movsx   r11, byte ptr [rcx]
0x180024653  cmp     r9, r11
0x180024656  ja      short loc_180024637
0x180024658  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002465d  mov     ecx, [rsp+720h+var_6E8]
0x180024661  add     ecx, r8d
0x180024664  mov     [rsp+720h+var_6E8], ecx
0x180024668  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002466d  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x180024672  mov     r10, qword ptr [rsp+720h+var_6D0]
0x180024677  mov     r8d, [rsp+720h+var_6E4]
0x18002467c  sub     edi, 1
0x18002467f  jz      loc_180024711
0x180024685  sub     edi, 1
0x180024688  jz      loc_180024736
0x18002468e  cmp     edi, 1
0x180024691  jnz     short loc_180024711
0x180024693  cmp     byte ptr [r14+0Bh], 0
0x180024698  jz      loc_180024740
0x18002469e  mov     al, [r14+8]
0x1800246a2  sub     al, 47h ; 'G'
0x1800246a4  test    al, 0DFh
0x1800246a6  jnz     loc_180024740
  ... truncated ...
```

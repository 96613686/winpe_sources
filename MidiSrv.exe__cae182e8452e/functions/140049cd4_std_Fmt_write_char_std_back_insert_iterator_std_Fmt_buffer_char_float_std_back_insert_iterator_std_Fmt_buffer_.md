# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,float>(std::back_insert_iterator<std::_Fmt_buffer<char>>,float,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x140049cd4`
- end: `0x14004a396`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@MAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1730`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, double, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14004cc34`

## callees

- `0x1400054c0`
- `0x140049cd4`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x140051154`
- `0x140055c40`
- `0x140055d38`
- `0x140055e3c`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140049fe9`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140049fe9`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x140049df1`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x140049df1`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
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
0x140049cd4  mov     rax, rsp
0x140049cd7  mov     [rax+10h], rbx
0x140049cdb  push    rbp
0x140049cdc  push    rsi
0x140049cdd  push    rdi
0x140049cde  push    r12
0x140049ce0  push    r13
0x140049ce2  push    r14
0x140049ce4  push    r15
0x140049ce6  lea     rbp, [rax-628h]
0x140049ced  sub     rsp, 6F0h
0x140049cf4  movaps  xmmword ptr [rax-48h], xmm6
0x140049cf8  mov     rax, cs:__security_cookie
0x140049cff  xor     rax, rsp
0x140049d02  mov     [rbp+620h+var_50], rax
0x140049d09  mov     r14, r9
0x140049d0c  movaps  xmm6, xmm2
0x140049d0f  mov     rbx, rdx
0x140049d12  mov     [rbp+620h+var_690], rcx
0x140049d16  mov     al, [r9+0Ah]
0x140049d1a  mov     byte ptr [rsp+720h+var_6F0+1], al
0x140049d1e  mov     r9d, 2
0x140049d24  test    al, al
0x140049d26  jnz     short loc_140049D2D
0x140049d28  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x140049d2d  xor     sil, sil
0x140049d30  mov     r13b, 65h ; 'e'
0x140049d33  mov     edx, [r14+4]
0x140049d37  xor     r15b, r15b
0x140049d3a  movsx   ecx, byte ptr [r14+8]
0x140049d3f  mov     edi, 4
0x140049d44  lea     r8d, [rdi-3]
0x140049d48  sub     ecx, 41h ; 'A'
0x140049d4b  jz      short loc_140049DB9
0x140049d4d  sub     ecx, edi
0x140049d4f  jz      short loc_140049DA6
0x140049d51  sub     ecx, r8d
0x140049d54  jz      short loc_140049D93
0x140049d56  sub     ecx, r8d
0x140049d59  jz      short loc_140049D77
0x140049d5b  sub     ecx, 1Ah
0x140049d5e  jz      short loc_140049DBC
0x140049d60  sub     ecx, edi
0x140049d62  jz      short loc_140049DA9
0x140049d64  sub     ecx, r8d
0x140049d67  jz      short loc_140049D96
0x140049d69  cmp     ecx, r8d
0x140049d6c  jz      short loc_140049D7A
0x140049d6e  lea     edi, [r8+2]
0x140049d72  mov     r15b, r8b
0x140049d75  jmp     short loc_140049DBF
0x140049d77  mov     sil, r8b
0x140049d7a  cmp     edx, 0FFFFFFFFh
0x140049d7d  jnz     short loc_140049D86
0x140049d7f  mov     edx, 6
0x140049d84  jmp     short loc_140049D8C
0x140049d86  test    edx, edx
0x140049d88  cmovz   edx, r8d
0x140049d8c  mov     edi, 3
0x140049d91  jmp     short loc_140049DBF
0x140049d93  mov     sil, r8b
0x140049d96  mov     eax, 6
0x140049d9b  cmp     edx, 0FFFFFFFFh
0x140049d9e  cmovz   edx, eax
0x140049da1  mov     edi, r9d
0x140049da4  jmp     short loc_140049DBF
0x140049da6  mov     sil, r8b
0x140049da9  mov     eax, 6
0x140049dae  cmp     edx, 0FFFFFFFFh
0x140049db1  cmovz   edx, eax
0x140049db4  mov     edi, r8d
0x140049db7  jmp     short loc_140049DBF
0x140049db9  mov     sil, r8b
0x140049dbc  mov     r13b, 70h ; 'p'
0x140049dbf  xorps   xmm0, xmm0
0x140049dc2  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x140049dc7  mov     r12d, edx
0x140049dca  mov     r8d, 432h
0x140049dd0  cmp     edx, r8d
0x140049dd3  cmovg   r12d, r8d
0x140049dd7  mov     dword ptr [rsp+720h+var_6B8], r12d
0x140049ddc  lea     ecx, [rdx-432h]
0x140049de2  xor     eax, eax
0x140049de4  cmp     edx, r8d
0x140049de7  cmovle  ecx, eax
0x140049dea  mov     dword ptr [rsp+720h+var_6E0], ecx
0x140049dee  movaps  xmm0, xmm6
0x140049df1  call    cs:__imp__o__fdsign
0x140049df7  mov     edx, eax
0x140049df9  test    eax, eax
0x140049dfb  setnz   byte ptr [rsp+720h+var_6F0+3]
0x140049e00  ucomiss xmm6, xmm6
0x140049e03  setp    al
0x140049e06  cmp     al, 1
0x140049e08  jnz     short loc_140049E3F
0x140049e0a  lea     rax, [rbp+620h+var_5C0]
0x140049e0e  lea     rcx, [rbp+620h+var_5BF]
0x140049e12  test    edx, edx
0x140049e14  cmovz   rcx, rax
0x140049e18  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x140049e1d  mov     eax, dword ptr cs:aNan; "nan"
0x140049e23  mov     [rcx], ax
0x140049e26  mov     al, byte ptr cs:aNan+2; "n"
0x140049e2c  mov     [rcx+2], al
0x140049e2f  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x140049e34  add     r9, 3
0x140049e38  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x140049e3d  jmp     short loc_140049E8A
0x140049e3f  movaps  xmm3, xmm6
0x140049e42  lea     r8, [rbp+620h+var_57]
0x140049e49  lea     rdx, [rbp+620h+var_5C0]
0x140049e4d  lea     rcx, [rsp+720h+var_6A8]
0x140049e52  cmp     r12d, 0FFFFFFFFh
0x140049e56  jnz     short loc_140049E6F
0x140049e58  test    r15b, r15b
0x140049e5b  jz      short loc_140049E64
0x140049e5d  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x140049e62  jmp     short loc_140049E7D
0x140049e64  mov     [rsp+720h+var_700], edi
0x140049e68  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x140049e6d  jmp     short loc_140049E7D
0x140049e6f  mov     dword ptr [rsp+720h+var_6F8], r12d
0x140049e74  mov     [rsp+720h+var_700], edi
0x140049e78  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x140049e7d  movups  xmm0, xmmword ptr [rax]
0x140049e80  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x140049e85  movq    r9, xmm0
0x140049e8a  lea     rdx, [rbp+620h+var_5C0]
0x140049e8e  mov     [rsp+720h+var_6D8], rdx
0x140049e93  mov     ecx, r9d
0x140049e96  sub     ecx, edx
0x140049e98  mov     [rsp+720h+var_6E8], ecx
0x140049e9c  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x140049ea1  jz      short loc_140049EAE
0x140049ea3  lea     rdx, [rbp+620h+var_5BF]
0x140049ea7  mov     [rsp+720h+var_6D8], rdx
0x140049eac  jmp     short loc_140049EBB
0x140049eae  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x140049eb3  jz      short loc_140049EBB
0x140049eb5  inc     ecx
0x140049eb7  mov     [rsp+720h+var_6E8], ecx
0x140049ebb  test    sil, sil
0x140049ebe  jz      short loc_140049EED
0x140049ec0  cmp     rdx, r9
0x140049ec3  jz      short loc_140049EE9
0x140049ec5  mov     cl, [rdx]
0x140049ec7  lea     eax, [rcx-61h]
0x140049eca  cmp     al, 19h
0x140049ecc  ja      short loc_140049ED3
0x140049ece  sub     cl, 20h ; ' '
0x140049ed1  mov     [rdx], cl
0x140049ed3  inc     rdx
0x140049ed6  cmp     rdx, r9
0x140049ed9  jnz     short loc_140049EC5
0x140049edb  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x140049ee0  mov     rdx, [rsp+720h+var_6D8]
0x140049ee5  mov     ecx, [rsp+720h+var_6E8]
0x140049ee9  add     r13b, 0E0h
0x140049eed  movd    eax, xmm6
0x140049ef1  mov     r8d, 7F800000h
0x140049ef7  and     eax, r8d
0x140049efa  cmp     eax, r8d
0x140049efd  setnz   al
0x140049f00  xor     al, 1
0x140049f02  mov     byte ptr [rsp+720h+var_6F0], al
0x140049f06  mov     r15b, 0
0x140049f09  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x140049f0e  mov     r10, r9
0x140049f11  mov     qword ptr [rsp+720h+var_6D0], r9
0x140049f16  mov     r11, r9
0x140049f19  mov     [rbp+620h+var_698], r9
0x140049f1d  mov     [rsp+720h+var_6B0], r9
0x140049f22  mov     r8d, 0
0x140049f28  mov     [rsp+720h+var_6E4], r8d
0x140049f2d  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x140049f32  xorps   xmm0, xmm0
0x140049f35  movups  [rbp+620h+var_600], xmm0
0x140049f39  mov     [rbp+620h+var_5F0], r8
0x140049f3d  mov     [rbp+620h+var_5E8], 0Fh
0x140049f45  mov     byte ptr [rbp+620h+var_600], r8b
0x140049f49  jnz     loc_14004A194
0x140049f4f  mov     r12b, [r14+0Bh]
0x140049f53  test    r12b, r12b
0x140049f56  jnz     short loc_140049F65
0x140049f58  lea     rsi, [r14+0Ch]
0x140049f5c  cmp     [rsi], r12b
0x140049f5f  jz      loc_14004A0CC
0x140049f65  mov     rax, rdx
0x140049f68  cmp     rdx, r9
0x140049f6b  jnb     short loc_140049F98
0x140049f6d  cmp     byte ptr [rax], 2Eh ; '.'
0x140049f70  jnz     short loc_140049F7B
0x140049f72  mov     r11, rax
0x140049f75  mov     [rbp+620h+var_698], rax
0x140049f79  jmp     short loc_140049F88
0x140049f7b  cmp     [rax], r13b
0x140049f7e  jnz     short loc_140049F88
0x140049f80  mov     r10, rax
0x140049f83  mov     qword ptr [rsp+720h+var_6D0], rax
0x140049f88  inc     rax
0x140049f8b  cmp     rax, r9
0x140049f8e  jb      short loc_140049F6D
0x140049f90  cmp     r10, r11
0x140049f93  mov     rax, r10
0x140049f96  jb      short loc_140049F9B
0x140049f98  mov     rax, r11
0x140049f9b  mov     [rsp+720h+var_6B0], rax
0x140049fa0  test    r12b, r12b
0x140049fa3  jz      short loc_140049FB8
0x140049fa5  cmp     r11, r9
0x140049fa8  jnz     short loc_140049FB8
0x140049faa  inc     ecx
0x140049fac  mov     [rsp+720h+var_6E8], ecx
0x140049fb0  mov     r15b, 1
0x140049fb3  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x140049fb8  lea     rsi, [r14+0Ch]
0x140049fbc  cmp     byte ptr [rsi], 0
0x140049fbf  jz      loc_14004A0CC
0x140049fc5  mov     rax, [rbp+620h+arg_20]
0x140049fcc  test    rax, rax
0x140049fcf  jz      short loc_140049FE7
0x140049fd1  mov     rcx, [rax+8]
0x140049fd5  mov     [rbp+620h+var_6A0], rcx
0x140049fd9  mov     rax, [rcx]
0x140049fdc  mov     rax, [rax+8]
0x140049fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049fe5  jmp     short loc_140049FF3
0x140049fe7  mov     cl, 1
0x140049fe9  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x140049fef  mov     [rbp+620h+var_6A0], rax
0x140049ff3  lea     rcx, [rsp+720h+var_6A8]
0x140049ff8  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x140049ffd  mov     rcx, rax
0x14004a000  mov     rax, [rax]
0x14004a003  lea     rdx, [rbp+620h+var_5E0]
0x14004a007  mov     rax, [rax+28h]
0x14004a00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a010  lea     rdx, [rbp+620h+var_5E0]
0x14004a014  lea     rcx, [rbp+620h+var_600]
0x14004a018  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004a01d  lea     rcx, [rbp+620h+var_5E0]
0x14004a021  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004a026  nop
0x14004a027  mov     rcx, [rbp+620h+var_6A0]
0x14004a02b  test    rcx, rcx
0x14004a02e  jz      short loc_14004A054
0x14004a030  mov     rax, [rcx]
0x14004a033  mov     rax, [rax+10h]
0x14004a037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a03c  mov     rcx, rax
0x14004a03f  test    rax, rax
0x14004a042  jz      short loc_14004A054
0x14004a044  mov     rax, [rax]
0x14004a047  mov     edx, 1
0x14004a04c  mov     rax, [rax]
0x14004a04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a054  lea     rax, [rbp+620h+var_600]
0x14004a058  cmp     [rbp+620h+var_5E8], 0Fh
0x14004a05d  cmova   rax, qword ptr [rbp+620h+var_600]
0x14004a062  mov     r10, [rbp+620h+var_5F0]
0x14004a066  mov     rdx, [rsp+720h+var_6D8]
0x14004a06b  xor     r8d, r8d
0x14004a06e  test    r10, r10
0x14004a071  jz      short loc_14004A0A8
0x14004a073  mov     r9, [rsp+720h+var_6B0]
0x14004a078  sub     r9, rdx
0x14004a07b  movsx   r11, byte ptr [rax]
0x14004a07f  cmp     r9, r11
0x14004a082  jbe     short loc_14004A0A8
0x14004a084  add     r10, rax
0x14004a087  movsx   rcx, r11b
0x14004a08b  sub     r9, rcx
0x14004a08e  inc     r8d
0x14004a091  lea     rcx, [rax+1]
0x14004a095  cmp     rcx, r10
0x14004a098  cmovz   rcx, rax
0x14004a09c  mov     rax, rcx
0x14004a09f  movsx   r11, byte ptr [rcx]
0x14004a0a3  cmp     r9, r11
0x14004a0a6  ja      short loc_14004A087
0x14004a0a8  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x14004a0ad  mov     ecx, [rsp+720h+var_6E8]
0x14004a0b1  add     ecx, r8d
0x14004a0b4  mov     [rsp+720h+var_6E8], ecx
0x14004a0b8  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x14004a0bd  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x14004a0c2  mov     r10, qword ptr [rsp+720h+var_6D0]
0x14004a0c7  mov     r8d, [rsp+720h+var_6E4]
0x14004a0cc  sub     edi, 1
0x14004a0cf  jz      loc_14004A161
0x14004a0d5  sub     edi, 1
0x14004a0d8  jz      loc_14004A186
0x14004a0de  cmp     edi, 1
0x14004a0e1  jnz     short loc_14004A161
0x14004a0e3  cmp     byte ptr [r14+0Bh], 0
0x14004a0e8  jz      loc_14004A190
0x14004a0ee  mov     al, [r14+8]
0x14004a0f2  sub     al, 47h ; 'G'
0x14004a0f4  test    al, 0DFh
0x14004a0f6  jnz     loc_14004A190
  ... truncated ...
```

# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,float>(std::back_insert_iterator<std::_Fmt_buffer<char>>,float,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18004eca8`
- end: `0x18004f36a`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@MAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1730`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180051498`

## callees

- `0x180005020`
- `0x1800342a8`
- `0x180034450`
- `0x1800433e4`
- `0x1800434dc`
- `0x1800435e0`
- `0x18004eca8`
- `0x180053d44`
- `0x180054654`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004efbd`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004efbd`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18004edc5`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18004edc5`

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
0x18004eca8  mov     rax, rsp
0x18004ecab  mov     [rax+10h], rbx
0x18004ecaf  push    rbp
0x18004ecb0  push    rsi
0x18004ecb1  push    rdi
0x18004ecb2  push    r12
0x18004ecb4  push    r13
0x18004ecb6  push    r14
0x18004ecb8  push    r15
0x18004ecba  lea     rbp, [rax-628h]
0x18004ecc1  sub     rsp, 6F0h
0x18004ecc8  movaps  xmmword ptr [rax-48h], xmm6
0x18004eccc  mov     rax, cs:__security_cookie
0x18004ecd3  xor     rax, rsp
0x18004ecd6  mov     [rbp+620h+var_50], rax
0x18004ecdd  mov     r14, r9
0x18004ece0  movaps  xmm6, xmm2
0x18004ece3  mov     rbx, rdx
0x18004ece6  mov     [rbp+620h+var_690], rcx
0x18004ecea  mov     al, [r9+0Ah]
0x18004ecee  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18004ecf2  mov     r9d, 2
0x18004ecf8  test    al, al
0x18004ecfa  jnz     short loc_18004ED01
0x18004ecfc  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18004ed01  xor     sil, sil
0x18004ed04  mov     r13b, 65h ; 'e'
0x18004ed07  mov     edx, [r14+4]
0x18004ed0b  xor     r15b, r15b
0x18004ed0e  movsx   ecx, byte ptr [r14+8]
0x18004ed13  mov     edi, 4
0x18004ed18  lea     r8d, [rdi-3]
0x18004ed1c  sub     ecx, 41h ; 'A'
0x18004ed1f  jz      short loc_18004ED8D
0x18004ed21  sub     ecx, edi
0x18004ed23  jz      short loc_18004ED7A
0x18004ed25  sub     ecx, r8d
0x18004ed28  jz      short loc_18004ED67
0x18004ed2a  sub     ecx, r8d
0x18004ed2d  jz      short loc_18004ED4B
0x18004ed2f  sub     ecx, 1Ah
0x18004ed32  jz      short loc_18004ED90
0x18004ed34  sub     ecx, edi
0x18004ed36  jz      short loc_18004ED7D
0x18004ed38  sub     ecx, r8d
0x18004ed3b  jz      short loc_18004ED6A
0x18004ed3d  cmp     ecx, r8d
0x18004ed40  jz      short loc_18004ED4E
0x18004ed42  lea     edi, [r8+2]
0x18004ed46  mov     r15b, r8b
0x18004ed49  jmp     short loc_18004ED93
0x18004ed4b  mov     sil, r8b
0x18004ed4e  cmp     edx, 0FFFFFFFFh
0x18004ed51  jnz     short loc_18004ED5A
0x18004ed53  mov     edx, 6
0x18004ed58  jmp     short loc_18004ED60
0x18004ed5a  test    edx, edx
0x18004ed5c  cmovz   edx, r8d
0x18004ed60  mov     edi, 3
0x18004ed65  jmp     short loc_18004ED93
0x18004ed67  mov     sil, r8b
0x18004ed6a  mov     eax, 6
0x18004ed6f  cmp     edx, 0FFFFFFFFh
0x18004ed72  cmovz   edx, eax
0x18004ed75  mov     edi, r9d
0x18004ed78  jmp     short loc_18004ED93
0x18004ed7a  mov     sil, r8b
0x18004ed7d  mov     eax, 6
0x18004ed82  cmp     edx, 0FFFFFFFFh
0x18004ed85  cmovz   edx, eax
0x18004ed88  mov     edi, r8d
0x18004ed8b  jmp     short loc_18004ED93
0x18004ed8d  mov     sil, r8b
0x18004ed90  mov     r13b, 70h ; 'p'
0x18004ed93  xorps   xmm0, xmm0
0x18004ed96  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18004ed9b  mov     r12d, edx
0x18004ed9e  mov     r8d, 432h
0x18004eda4  cmp     edx, r8d
0x18004eda7  cmovg   r12d, r8d
0x18004edab  mov     dword ptr [rsp+720h+var_6B8], r12d
0x18004edb0  lea     ecx, [rdx-432h]
0x18004edb6  xor     eax, eax
0x18004edb8  cmp     edx, r8d
0x18004edbb  cmovle  ecx, eax
0x18004edbe  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18004edc2  movaps  xmm0, xmm6
0x18004edc5  call    cs:__imp__o__fdsign
0x18004edcb  mov     edx, eax
0x18004edcd  test    eax, eax
0x18004edcf  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18004edd4  ucomiss xmm6, xmm6
0x18004edd7  setp    al
0x18004edda  cmp     al, 1
0x18004eddc  jnz     short loc_18004EE13
0x18004edde  lea     rax, [rbp+620h+var_5C0]
0x18004ede2  lea     rcx, [rbp+620h+var_5BF]
0x18004ede6  test    edx, edx
0x18004ede8  cmovz   rcx, rax
0x18004edec  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x18004edf1  mov     eax, dword ptr cs:aNan; "nan"
0x18004edf7  mov     [rcx], ax
0x18004edfa  mov     al, byte ptr cs:aNan+2; "n"
0x18004ee00  mov     [rcx+2], al
0x18004ee03  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18004ee08  add     r9, 3
0x18004ee0c  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x18004ee11  jmp     short loc_18004EE5E
0x18004ee13  movaps  xmm3, xmm6
0x18004ee16  lea     r8, [rbp+620h+var_57]
0x18004ee1d  lea     rdx, [rbp+620h+var_5C0]
0x18004ee21  lea     rcx, [rsp+720h+var_6A8]
0x18004ee26  cmp     r12d, 0FFFFFFFFh
0x18004ee2a  jnz     short loc_18004EE43
0x18004ee2c  test    r15b, r15b
0x18004ee2f  jz      short loc_18004EE38
0x18004ee31  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x18004ee36  jmp     short loc_18004EE51
0x18004ee38  mov     [rsp+720h+var_700], edi
0x18004ee3c  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x18004ee41  jmp     short loc_18004EE51
0x18004ee43  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18004ee48  mov     [rsp+720h+var_700], edi
0x18004ee4c  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x18004ee51  movups  xmm0, xmmword ptr [rax]
0x18004ee54  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18004ee59  movq    r9, xmm0
0x18004ee5e  lea     rdx, [rbp+620h+var_5C0]
0x18004ee62  mov     [rsp+720h+var_6D8], rdx
0x18004ee67  mov     ecx, r9d
0x18004ee6a  sub     ecx, edx
0x18004ee6c  mov     [rsp+720h+var_6E8], ecx
0x18004ee70  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18004ee75  jz      short loc_18004EE82
0x18004ee77  lea     rdx, [rbp+620h+var_5BF]
0x18004ee7b  mov     [rsp+720h+var_6D8], rdx
0x18004ee80  jmp     short loc_18004EE8F
0x18004ee82  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18004ee87  jz      short loc_18004EE8F
0x18004ee89  inc     ecx
0x18004ee8b  mov     [rsp+720h+var_6E8], ecx
0x18004ee8f  test    sil, sil
0x18004ee92  jz      short loc_18004EEC1
0x18004ee94  cmp     rdx, r9
0x18004ee97  jz      short loc_18004EEBD
0x18004ee99  mov     cl, [rdx]
0x18004ee9b  lea     eax, [rcx-61h]
0x18004ee9e  cmp     al, 19h
0x18004eea0  ja      short loc_18004EEA7
0x18004eea2  sub     cl, 20h ; ' '
0x18004eea5  mov     [rdx], cl
0x18004eea7  inc     rdx
0x18004eeaa  cmp     rdx, r9
0x18004eead  jnz     short loc_18004EE99
0x18004eeaf  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18004eeb4  mov     rdx, [rsp+720h+var_6D8]
0x18004eeb9  mov     ecx, [rsp+720h+var_6E8]
0x18004eebd  add     r13b, 0E0h
0x18004eec1  movd    eax, xmm6
0x18004eec5  mov     r8d, 7F800000h
0x18004eecb  and     eax, r8d
0x18004eece  cmp     eax, r8d
0x18004eed1  setnz   al
0x18004eed4  xor     al, 1
0x18004eed6  mov     byte ptr [rsp+720h+var_6F0], al
0x18004eeda  mov     r15b, 0
0x18004eedd  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18004eee2  mov     r10, r9
0x18004eee5  mov     qword ptr [rsp+720h+var_6D0], r9
0x18004eeea  mov     r11, r9
0x18004eeed  mov     [rbp+620h+var_698], r9
0x18004eef1  mov     [rsp+720h+var_6B0], r9
0x18004eef6  mov     r8d, 0
0x18004eefc  mov     [rsp+720h+var_6E4], r8d
0x18004ef01  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18004ef06  xorps   xmm0, xmm0
0x18004ef09  movups  [rbp+620h+var_600], xmm0
0x18004ef0d  mov     [rbp+620h+var_5F0], r8
0x18004ef11  mov     [rbp+620h+var_5E8], 0Fh
0x18004ef19  mov     byte ptr [rbp+620h+var_600], r8b
0x18004ef1d  jnz     loc_18004F168
0x18004ef23  mov     r12b, [r14+0Bh]
0x18004ef27  test    r12b, r12b
0x18004ef2a  jnz     short loc_18004EF39
0x18004ef2c  lea     rsi, [r14+0Ch]
0x18004ef30  cmp     [rsi], r12b
0x18004ef33  jz      loc_18004F0A0
0x18004ef39  mov     rax, rdx
0x18004ef3c  cmp     rdx, r9
0x18004ef3f  jnb     short loc_18004EF6C
0x18004ef41  cmp     byte ptr [rax], 2Eh ; '.'
0x18004ef44  jnz     short loc_18004EF4F
0x18004ef46  mov     r11, rax
0x18004ef49  mov     [rbp+620h+var_698], rax
0x18004ef4d  jmp     short loc_18004EF5C
0x18004ef4f  cmp     [rax], r13b
0x18004ef52  jnz     short loc_18004EF5C
0x18004ef54  mov     r10, rax
0x18004ef57  mov     qword ptr [rsp+720h+var_6D0], rax
0x18004ef5c  inc     rax
0x18004ef5f  cmp     rax, r9
0x18004ef62  jb      short loc_18004EF41
0x18004ef64  cmp     r10, r11
0x18004ef67  mov     rax, r10
0x18004ef6a  jb      short loc_18004EF6F
0x18004ef6c  mov     rax, r11
0x18004ef6f  mov     [rsp+720h+var_6B0], rax
0x18004ef74  test    r12b, r12b
0x18004ef77  jz      short loc_18004EF8C
0x18004ef79  cmp     r11, r9
0x18004ef7c  jnz     short loc_18004EF8C
0x18004ef7e  inc     ecx
0x18004ef80  mov     [rsp+720h+var_6E8], ecx
0x18004ef84  mov     r15b, 1
0x18004ef87  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18004ef8c  lea     rsi, [r14+0Ch]
0x18004ef90  cmp     byte ptr [rsi], 0
0x18004ef93  jz      loc_18004F0A0
0x18004ef99  mov     rax, [rbp+620h+arg_20]
0x18004efa0  test    rax, rax
0x18004efa3  jz      short loc_18004EFBB
0x18004efa5  mov     rcx, [rax+8]
0x18004efa9  mov     [rbp+620h+var_6A0], rcx
0x18004efad  mov     rax, [rcx]
0x18004efb0  mov     rax, [rax+8]
0x18004efb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efb9  jmp     short loc_18004EFC7
0x18004efbb  mov     cl, 1
0x18004efbd  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18004efc3  mov     [rbp+620h+var_6A0], rax
0x18004efc7  lea     rcx, [rsp+720h+var_6A8]
0x18004efcc  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18004efd1  mov     rcx, rax
0x18004efd4  mov     rax, [rax]
0x18004efd7  lea     rdx, [rbp+620h+var_5E0]
0x18004efdb  mov     rax, [rax+28h]
0x18004efdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efe4  lea     rdx, [rbp+620h+var_5E0]
0x18004efe8  lea     rcx, [rbp+620h+var_600]
0x18004efec  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18004eff1  lea     rcx, [rbp+620h+var_5E0]
0x18004eff5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004effa  nop
0x18004effb  mov     rcx, [rbp+620h+var_6A0]
0x18004efff  test    rcx, rcx
0x18004f002  jz      short loc_18004F028
0x18004f004  mov     rax, [rcx]
0x18004f007  mov     rax, [rax+10h]
0x18004f00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f010  mov     rcx, rax
0x18004f013  test    rax, rax
0x18004f016  jz      short loc_18004F028
0x18004f018  mov     rax, [rax]
0x18004f01b  mov     edx, 1
0x18004f020  mov     rax, [rax]
0x18004f023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f028  lea     rax, [rbp+620h+var_600]
0x18004f02c  cmp     [rbp+620h+var_5E8], 0Fh
0x18004f031  cmova   rax, qword ptr [rbp+620h+var_600]
0x18004f036  mov     r10, [rbp+620h+var_5F0]
0x18004f03a  mov     rdx, [rsp+720h+var_6D8]
0x18004f03f  xor     r8d, r8d
0x18004f042  test    r10, r10
0x18004f045  jz      short loc_18004F07C
0x18004f047  mov     r9, [rsp+720h+var_6B0]
0x18004f04c  sub     r9, rdx
0x18004f04f  movsx   r11, byte ptr [rax]
0x18004f053  cmp     r9, r11
0x18004f056  jbe     short loc_18004F07C
0x18004f058  add     r10, rax
0x18004f05b  movsx   rcx, r11b
0x18004f05f  sub     r9, rcx
0x18004f062  inc     r8d
0x18004f065  lea     rcx, [rax+1]
0x18004f069  cmp     rcx, r10
0x18004f06c  cmovz   rcx, rax
0x18004f070  mov     rax, rcx
0x18004f073  movsx   r11, byte ptr [rcx]
0x18004f077  cmp     r9, r11
0x18004f07a  ja      short loc_18004F05B
0x18004f07c  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18004f081  mov     ecx, [rsp+720h+var_6E8]
0x18004f085  add     ecx, r8d
0x18004f088  mov     [rsp+720h+var_6E8], ecx
0x18004f08c  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18004f091  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18004f096  mov     r10, qword ptr [rsp+720h+var_6D0]
0x18004f09b  mov     r8d, [rsp+720h+var_6E4]
0x18004f0a0  sub     edi, 1
0x18004f0a3  jz      loc_18004F135
0x18004f0a9  sub     edi, 1
0x18004f0ac  jz      loc_18004F15A
0x18004f0b2  cmp     edi, 1
0x18004f0b5  jnz     short loc_18004F135
0x18004f0b7  cmp     byte ptr [r14+0Bh], 0
0x18004f0bc  jz      loc_18004F164
0x18004f0c2  mov     al, [r14+8]
0x18004f0c6  sub     al, 47h ; 'G'
0x18004f0c8  test    al, 0DFh
0x18004f0ca  jnz     loc_18004F164
  ... truncated ...
```

# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x1800300e0`
- end: `0x1800307aa`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@OAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180032164`

## callees

- `0x180004410`
- `0x18002dd8c`
- `0x18002deb8`
- `0x18002e064`
- `0x1800300e0`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x1800369ac`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800303fb`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800303fb`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x1800301fc`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x1800301fc`

## pseudocode

```c
_QWORD *__fastcall std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(
        _QWORD *a1,
        __int64 a2,
        long double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // si
  char v8; // r13
  int v9; // edx
  char v10; // r15
  int v11; // edi
  int v12; // r12d
  int v13; // ecx
  char *v14; // r9
  char *v15; // rdx
  int v16; // ecx
  bool v17; // al
  char v18; // r15
  char *v19; // r10
  char *v20; // r11
  int v21; // r8d
  char v22; // r12
  _BYTE *v23; // rsi
  char *v24; // rax
  char *v25; // rax
  __int64 v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64); // rax
  char *v28; // rax
  int v29; // r8d
  unsigned __int64 v30; // r9
  unsigned __int64 v31; // r11
  char *v32; // r10
  char *v33; // rcx
  int v34; // edi
  int v35; // edi
  int v36; // eax
  int v37; // ecx
  bool v38; // al
  int v40; // esi
  int v41; // edi
  char v42; // al
  char *v43; // r15
  __int64 v44; // r14
  char *i; // r12
  char v46; // r13
  __int64 v47; // rbx
  char *j; // rsi
  char v49; // r12
  _QWORD *v50; // rdi
  char v51; // [rsp+39h] [rbp-CFh] BYREF
  char v52; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v53; // [rsp+3Bh] [rbp-CDh] BYREF
  int v54; // [rsp+3Ch] [rbp-CCh] BYREF
  int v55; // [rsp+40h] [rbp-C8h] BYREF
  int v56; // [rsp+44h] [rbp-C4h] BYREF
  int v57; // [rsp+48h] [rbp-C0h]
  int v58; // [rsp+4Ch] [rbp-BCh] BYREF
  char *v59; // [rsp+50h] [rbp-B8h] BYREF
  char *v60; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v61; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v62; // [rsp+78h] [rbp-90h] BYREF
  int v63; // [rsp+88h] [rbp-80h] BYREF
  char *v64; // [rsp+90h] [rbp-78h] BYREF
  char *v65; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v66; // [rsp+A0h] [rbp-68h]
  _QWORD v67[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v68; // [rsp+128h] [rbp+20h] BYREF
  __int64 v69; // [rsp+138h] [rbp+30h]
  unsigned __int64 v70; // [rsp+140h] [rbp+38h]
  _BYTE v71[32]; // [rsp+148h] [rbp+40h] BYREF
  char v72; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v73[1384]; // [rsp+169h] [rbp+61h] BYREF
  _BYTE v74[7]; // [rsp+6D1h] [rbp+5C9h] BYREF

  v66 = a1;
  v51 = *(_BYTE *)(a4 + 10);
  if ( !v51 )
    v51 = 2;
  v7 = 0;
  v8 = 101;
  v9 = *(_DWORD *)(a4 + 4);
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
      if ( v9 == -1 )
        v9 = 6;
      v11 = 2;
      goto LABEL_28;
    case 'G':
      v7 = 1;
LABEL_13:
      if ( v9 == -1 )
      {
        v9 = 6;
      }
      else if ( !v9 )
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
  if ( v9 == -1 )
    v9 = 6;
  v11 = 1;
LABEL_28:
  v61 = 0;
  v12 = v9;
  if ( v9 > 1074 )
    v12 = 1074;
  v63 = v12;
  v13 = v9 - 1074;
  if ( v9 <= 1074 )
    v13 = 0;
  v57 = v13;
  v53 = _ldsign(a3) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      std::_Floating_to_chars<0,double>(&v62, &v72, v74);
    else
      std::_Floating_to_chars<1,double>(&v62, &v72, v74);
  }
  else
  {
    std::_Floating_to_chars<2,double>(&v62, &v72, v74);
  }
  v61 = v62;
  v14 = (char *)v62;
  v15 = &v72;
  v59 = &v72;
  v16 = v62 - (unsigned int)&v72;
  v55 = v16;
  if ( v53 )
  {
    v15 = v73;
    v59 = v73;
  }
  else if ( v51 != 2 )
  {
    v55 = ++v16;
  }
  if ( v7 )
  {
    if ( v15 != (char *)v62 )
    {
      do
      {
        if ( (unsigned __int8)(*v15 - 97) <= 0x19u )
          *v15 -= 32;
        ++v15;
      }
      while ( v15 != v14 );
      v14 = (char *)v61;
      v15 = v59;
      v16 = v55;
    }
    v8 -= 32;
  }
  v17 = ((*(_QWORD *)&a3 >> 52) & 0x7FF) == 2047;
  v18 = 0;
  v52 = 0;
  v19 = v14;
  v60 = v14;
  v20 = v14;
  v65 = v14;
  v64 = v14;
  v21 = 0;
  v56 = 0;
  v58 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 15;
  LOBYTE(v68) = 0;
  if ( ((*(_QWORD *)&a3 >> 52) & 0x7FF) != 0x7FF )
  {
    v22 = *(_BYTE *)(a4 + 11);
    if ( v22 || (v23 = (_BYTE *)(a4 + 12), *(_BYTE *)(a4 + 12)) )
    {
      v24 = v15;
      if ( v15 >= v14 )
        goto LABEL_58;
      do
      {
        if ( *v24 == 46 )
        {
          v20 = v24;
          v65 = v24;
        }
        else if ( *v24 == v8 )
        {
          v19 = v24;
          v60 = v24;
        }
        ++v24;
      }
      while ( v24 < v14 );
      v25 = v19;
      if ( v19 >= v20 )
LABEL_58:
        v25 = v20;
      v64 = v25;
      if ( v22 && v20 == v14 )
      {
        v55 = ++v16;
        v18 = 1;
        v52 = 1;
      }
      v23 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          *((_QWORD *)&v62 + 1) = *(_QWORD *)(a5 + 8);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v62 + 1) + 8LL))(*((_QWORD *)&v62 + 1));
        }
        else
        {
          *((_QWORD *)&v62 + 1) = std::locale::_Init(1);
        }
        v26 = std::use_facet<std::numpunct<char>>(&v62);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v26 + 40LL))(v26, v71);
        std::string::operator=(&v68, v71);
        std::string::~string(v71);
        if ( *((_QWORD *)&v62 + 1) )
        {
          v27 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v62 + 1)
                                                                                          + 16LL))(*((_QWORD *)&v62 + 1));
          if ( v27 )
            (**v27)(v27, 1);
        }
        v28 = (char *)&v68;
        if ( v70 > 0xF )
          v28 = (char *)v68;
        v15 = v59;
        v29 = 0;
        if ( v69 )
        {
          v30 = v64 - v59;
          v31 = *v28;
          if ( v64 - v59 > v31 )
          {
            v32 = &v28[v69];
            do
            {
              v30 -= (char)v31;
              ++v29;
              v33 = v28 + 1;
              if ( v28 + 1 == v32 )
                v33 = v28;
              v28 = v33;
              v31 = *v33;
            }
            while ( v30 > v31 );
          }
        }
        v58 = v29;
        v16 = v29 + v55;
        v55 += v29;
        v14 = (char *)v61;
        v18 = v52;
        v19 = v60;
        v21 = v56;
      }
    }
    v34 = v11 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        v21 = v57;
LABEL_101:
        v56 = v21;
LABEL_102:
        v17 = 0;
        goto LABEL_103;
      }
      if ( v35 == 1 )
      {
        if ( *(_BYTE *)(a4 + 11) && ((*(_BYTE *)(a4 + 8) - 71) & 0xDF) == 0 )
        {
          v36 = (_DWORD)v19 - (_DWORD)v15;
          if ( !v18 )
            --v36;
          v21 = v63 + v57 - v36;
          v56 = v21;
          if ( v19 == v14 && COERCE_DOUBLE(*(_QWORD *)&a3 & _xmm) < 1.0 && a3 != 0.0 )
          {
            while ( v15 < v14 )
            {
              if ( *v15 == 48 )
              {
                v56 = ++v21;
              }
              else if ( *v15 != 46 )
              {
                goto LABEL_102;
              }
              ++v15;
            }
          }
        }
        goto LABEL_102;
      }
    }
    v21 = v57;
    if ( v57 && !*(_BYTE *)(a4 + 11) && !*v23 )
    {
      do
        v60 = --v19;
      while ( *v19 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v37 = v21 + v16;
  v55 = v37;
  v38 = *(_BYTE *)(a4 + 13) && !*(_BYTE *)(a4 + 9) && !v17;
  LOBYTE(v54) = v38;
  v67[0] = &v51;
  v67[1] = &v53;
  v67[2] = &v54;
  v67[3] = &v55;
  v67[4] = a4;
  v67[5] = &a5;
  v67[6] = &v59;
  v67[7] = &v64;
  v67[8] = &v68;
  v67[9] = &v58;
  v67[10] = &v65;
  v67[11] = &v61;
  v67[12] = &v52;
  v67[13] = &v60;
  v67[14] = &v56;
  if ( v38 )
  {
    `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
      v67,
      v66,
      a2);
    std::string::~string(&v68);
    return v66;
  }
  else
  {
    v40 = 0;
    v41 = 0;
    v42 = *(_BYTE *)(a4 + 9);
    if ( !v42 )
      v42 = 2;
    if ( v37 < *(_DWORD *)a4 )
    {
      switch ( v42 )
      {
        case 1:
          v41 = *(_DWORD *)a4 - v37;
          break;
        case 2:
          v40 = *(_DWORD *)a4 - v37;
          break;
        case 3:
          v40 = (*(_DWORD *)a4 - v37) / 2;
          v41 = *(_DWORD *)a4 - v37 - v40;
          break;
      }
    }
    v43 = (char *)(a4 + 15);
    v44 = a4 + 15 + *(unsigned __int8 *)(a4 + 14);
    while ( v40 > 0 )
    {
      for ( i = v43; i != (char *)v44; ++i )
      {
        v46 = *i;
        if ( (unsigned __int64)(*(_QWORD *)(a2 + 16) + 1LL) > *(_QWORD *)(a2 + 24) )
          (**(void (__fastcall ***)(__int64))a2)(a2);
        *(_BYTE *)(*(_QWORD *)(a2 + 8) + (*(_QWORD *)(a2 + 16))++) = v46;
      }
      --v40;
    }
    v47 = *(_QWORD *)`std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
                       v67,
                       &v63,
                       a2);
    while ( v41 > 0 )
    {
      for ( j = v43; j != (char *)v44; ++j )
      {
        v49 = *j;
        if ( (unsigned __int64)(*(_QWORD *)(v47 + 16) + 1LL) > *(_QWORD *)(v47 + 24) )
          (**(void (__fastcall ***)(__int64))v47)(v47);
        *(_BYTE *)(*(_QWORD *)(v47 + 16) + *(_QWORD *)(v47 + 8)) = v49;
        ++*(_QWORD *)(v47 + 16);
      }
      --v41;
    }
    v50 = v66;
    *v66 = v47;
    std::string::~string(&v68);
    return v50;
  }
}

```

## disassembly

```asm
0x1800300e0  mov     rax, rsp
0x1800300e3  mov     [rax+10h], rbx
0x1800300e7  push    rbp
0x1800300e8  push    rsi
0x1800300e9  push    rdi
0x1800300ea  push    r12
0x1800300ec  push    r13
0x1800300ee  push    r14
0x1800300f0  push    r15
0x1800300f2  lea     rbp, [rax-628h]
0x1800300f9  sub     rsp, 6F0h
0x180030100  movaps  xmmword ptr [rax-48h], xmm6
0x180030104  mov     rax, cs:__security_cookie
0x18003010b  xor     rax, rsp
0x18003010e  mov     [rbp+620h+var_50], rax
0x180030115  mov     r14, r9
0x180030118  movaps  xmm6, xmm2
0x18003011b  mov     rbx, rdx
0x18003011e  mov     [rbp+620h+var_688], rcx
0x180030122  mov     al, [r9+0Ah]
0x180030126  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18003012a  mov     r9d, 2
0x180030130  test    al, al
0x180030132  jnz     short loc_180030139
0x180030134  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x180030139  xor     sil, sil
0x18003013c  mov     r13b, 65h ; 'e'
0x18003013f  mov     edx, [r14+4]
0x180030143  xor     r15b, r15b
0x180030146  movsx   ecx, byte ptr [r14+8]
0x18003014b  mov     edi, 4
0x180030150  lea     r8d, [rdi-3]
0x180030154  sub     ecx, 41h ; 'A'
0x180030157  jz      short loc_1800301C5
0x180030159  sub     ecx, edi
0x18003015b  jz      short loc_1800301B2
0x18003015d  sub     ecx, r8d
0x180030160  jz      short loc_18003019F
0x180030162  sub     ecx, r8d
0x180030165  jz      short loc_180030183
0x180030167  sub     ecx, 1Ah
0x18003016a  jz      short loc_1800301C8
0x18003016c  sub     ecx, edi
0x18003016e  jz      short loc_1800301B5
0x180030170  sub     ecx, r8d
0x180030173  jz      short loc_1800301A2
0x180030175  cmp     ecx, r8d
0x180030178  jz      short loc_180030186
0x18003017a  lea     edi, [r8+2]
0x18003017e  mov     r15b, r8b
0x180030181  jmp     short loc_1800301CB
0x180030183  mov     sil, r8b
0x180030186  cmp     edx, 0FFFFFFFFh
0x180030189  jnz     short loc_180030192
0x18003018b  mov     edx, 6
0x180030190  jmp     short loc_180030198
0x180030192  test    edx, edx
0x180030194  cmovz   edx, r8d
0x180030198  mov     edi, 3
0x18003019d  jmp     short loc_1800301CB
0x18003019f  mov     sil, r8b
0x1800301a2  mov     eax, 6
0x1800301a7  cmp     edx, 0FFFFFFFFh
0x1800301aa  cmovz   edx, eax
0x1800301ad  mov     edi, r9d
0x1800301b0  jmp     short loc_1800301CB
0x1800301b2  mov     sil, r8b
0x1800301b5  mov     eax, 6
0x1800301ba  cmp     edx, 0FFFFFFFFh
0x1800301bd  cmovz   edx, eax
0x1800301c0  mov     edi, r8d
0x1800301c3  jmp     short loc_1800301CB
0x1800301c5  mov     sil, r8b
0x1800301c8  mov     r13b, 70h ; 'p'
0x1800301cb  xorps   xmm0, xmm0
0x1800301ce  movups  [rsp+720h+var_6C8+8], xmm0
0x1800301d3  mov     r12d, edx
0x1800301d6  mov     r8d, 432h
0x1800301dc  cmp     edx, r8d
0x1800301df  cmovg   r12d, r8d
0x1800301e3  mov     [rbp+620h+var_6A0], r12d
0x1800301e7  lea     ecx, [rdx-432h]
0x1800301ed  xor     eax, eax
0x1800301ef  cmp     edx, r8d
0x1800301f2  cmovle  ecx, eax
0x1800301f5  mov     dword ptr [rsp+720h+var_6E0], ecx
0x1800301f9  movaps  xmm0, xmm6; X
0x1800301fc  call    cs:__imp__ldsign
0x180030202  mov     edx, eax
0x180030204  test    eax, eax
0x180030206  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18003020b  ucomisd xmm6, xmm6
0x18003020f  setp    al
0x180030212  cmp     al, 1
0x180030214  jnz     short loc_18003024B
0x180030216  lea     rax, [rbp+620h+var_5C0]
0x18003021a  lea     rcx, [rbp+620h+var_5BF]
0x18003021e  test    edx, edx
0x180030220  cmovz   rcx, rax
0x180030224  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x180030229  mov     eax, dword ptr cs:aNan; "nan"
0x18003022f  mov     [rcx], ax
0x180030232  mov     al, byte ptr cs:aNan+2; "n"
0x180030238  mov     [rcx+2], al
0x18003023b  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x180030240  add     r9, 3
0x180030244  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x180030249  jmp     short loc_180030298
0x18003024b  movaps  xmm3, xmm6
0x18003024e  lea     r8, [rbp+620h+var_57]
0x180030255  lea     rdx, [rbp+620h+var_5C0]
0x180030259  lea     rcx, [rsp+720h+var_6B8+8]
0x18003025e  cmp     r12d, 0FFFFFFFFh
0x180030262  jnz     short loc_18003027B
0x180030264  test    r15b, r15b
0x180030267  jz      short loc_180030270
0x180030269  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18003026e  jmp     short loc_180030289
0x180030270  mov     [rsp+720h+var_700], edi
0x180030274  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x180030279  jmp     short loc_180030289
0x18003027b  mov     dword ptr [rsp+720h+var_6F8], r12d
0x180030280  mov     [rsp+720h+var_700], edi
0x180030284  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x180030289  movaps  xmm0, [rsp+720h+var_6B8+8]
0x18003028e  movaps  [rsp+720h+var_6C8+8], xmm0
0x180030293  movq    r9, xmm0
0x180030298  lea     rdx, [rbp+620h+var_5C0]
0x18003029c  mov     [rsp+720h+var_6D8], rdx
0x1800302a1  mov     ecx, r9d
0x1800302a4  sub     ecx, edx
0x1800302a6  mov     [rsp+720h+var_6E8], ecx
0x1800302aa  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x1800302af  jz      short loc_1800302BC
0x1800302b1  lea     rdx, [rbp+620h+var_5BF]
0x1800302b5  mov     [rsp+720h+var_6D8], rdx
0x1800302ba  jmp     short loc_1800302C9
0x1800302bc  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x1800302c1  jz      short loc_1800302C9
0x1800302c3  inc     ecx
0x1800302c5  mov     [rsp+720h+var_6E8], ecx
0x1800302c9  test    sil, sil
0x1800302cc  jz      short loc_1800302FB
0x1800302ce  cmp     rdx, r9
0x1800302d1  jz      short loc_1800302F7
0x1800302d3  mov     cl, [rdx]
0x1800302d5  lea     eax, [rcx-61h]
0x1800302d8  cmp     al, 19h
0x1800302da  ja      short loc_1800302E1
0x1800302dc  sub     cl, 20h ; ' '
0x1800302df  mov     [rdx], cl
0x1800302e1  inc     rdx
0x1800302e4  cmp     rdx, r9
0x1800302e7  jnz     short loc_1800302D3
0x1800302e9  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x1800302ee  mov     rdx, [rsp+720h+var_6D8]
0x1800302f3  mov     ecx, [rsp+720h+var_6E8]
0x1800302f7  add     r13b, 0E0h
0x1800302fb  movq    rax, xmm6
0x180030300  shr     rax, 34h
0x180030304  mov     r8d, 7FFh
0x18003030a  and     eax, r8d
0x18003030d  cmp     eax, r8d
0x180030310  setnz   al
0x180030313  xor     al, 1
0x180030315  mov     byte ptr [rsp+720h+var_6F0], al
0x180030319  mov     r15b, 0
0x18003031c  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x180030321  mov     r10, r9
0x180030324  mov     [rsp+720h+var_6D0], r9
0x180030329  mov     r11, r9
0x18003032c  mov     [rbp+620h+var_690], r9
0x180030330  mov     [rbp+620h+var_698], r9
0x180030334  mov     r8d, 0
0x18003033a  mov     [rsp+720h+var_6E4], r8d
0x18003033f  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x180030344  xorps   xmm0, xmm0
0x180030347  movups  [rbp+620h+var_600], xmm0
0x18003034b  mov     [rbp+620h+var_5F0], r8
0x18003034f  mov     [rbp+620h+var_5E8], 0Fh
0x180030357  mov     byte ptr [rbp+620h+var_600], r8b
0x18003035b  jnz     loc_1800305A8
0x180030361  mov     r12b, [r14+0Bh]
0x180030365  test    r12b, r12b
0x180030368  jnz     short loc_180030377
0x18003036a  lea     rsi, [r14+0Ch]
0x18003036e  cmp     [rsi], r12b
0x180030371  jz      loc_1800304DF
0x180030377  mov     rax, rdx
0x18003037a  cmp     rdx, r9
0x18003037d  jnb     short loc_1800303AA
0x18003037f  cmp     byte ptr [rax], 2Eh ; '.'
0x180030382  jnz     short loc_18003038D
0x180030384  mov     r11, rax
0x180030387  mov     [rbp+620h+var_690], rax
0x18003038b  jmp     short loc_18003039A
0x18003038d  cmp     [rax], r13b
0x180030390  jnz     short loc_18003039A
0x180030392  mov     r10, rax
0x180030395  mov     [rsp+720h+var_6D0], rax
0x18003039a  inc     rax
0x18003039d  cmp     rax, r9
0x1800303a0  jb      short loc_18003037F
0x1800303a2  cmp     r10, r11
0x1800303a5  mov     rax, r10
0x1800303a8  jb      short loc_1800303AD
0x1800303aa  mov     rax, r11
0x1800303ad  mov     [rbp+620h+var_698], rax
0x1800303b1  test    r12b, r12b
0x1800303b4  jz      short loc_1800303C9
0x1800303b6  cmp     r11, r9
0x1800303b9  jnz     short loc_1800303C9
0x1800303bb  inc     ecx
0x1800303bd  mov     [rsp+720h+var_6E8], ecx
0x1800303c1  mov     r15b, 1
0x1800303c4  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x1800303c9  lea     rsi, [r14+0Ch]
0x1800303cd  cmp     byte ptr [rsi], 0
0x1800303d0  jz      loc_1800304DF
0x1800303d6  mov     rax, [rbp+620h+arg_20]
0x1800303dd  test    rax, rax
0x1800303e0  jz      short loc_1800303F9
0x1800303e2  mov     rcx, [rax+8]
0x1800303e6  mov     [rsp+720h+var_6A8], rcx
0x1800303eb  mov     rax, [rcx]
0x1800303ee  mov     rax, [rax+8]
0x1800303f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303f7  jmp     short loc_180030406
0x1800303f9  mov     cl, 1
0x1800303fb  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180030401  mov     [rsp+720h+var_6A8], rax
0x180030406  lea     rcx, [rsp+720h+var_6B8+8]
0x18003040b  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180030410  mov     rcx, rax
0x180030413  mov     rax, [rax]
0x180030416  lea     rdx, [rbp+620h+var_5E0]
0x18003041a  mov     rax, [rax+28h]
0x18003041e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030423  lea     rdx, [rbp+620h+var_5E0]
0x180030427  lea     rcx, [rbp+620h+var_600]
0x18003042b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180030430  lea     rcx, [rbp+620h+var_5E0]
0x180030434  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180030439  nop
0x18003043a  mov     rcx, [rsp+720h+var_6A8]
0x18003043f  test    rcx, rcx
0x180030442  jz      short loc_180030468
0x180030444  mov     rax, [rcx]
0x180030447  mov     rax, [rax+10h]
0x18003044b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030450  mov     rcx, rax
0x180030453  test    rax, rax
0x180030456  jz      short loc_180030468
0x180030458  mov     rax, [rax]
0x18003045b  mov     edx, 1
0x180030460  mov     rax, [rax]
0x180030463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030468  lea     rax, [rbp+620h+var_600]
0x18003046c  cmp     [rbp+620h+var_5E8], 0Fh
0x180030471  cmova   rax, qword ptr [rbp+620h+var_600]
0x180030476  mov     r10, [rbp+620h+var_5F0]
0x18003047a  mov     rdx, [rsp+720h+var_6D8]
0x18003047f  xor     r8d, r8d
0x180030482  test    r10, r10
0x180030485  jz      short loc_1800304BB
0x180030487  mov     r9, [rbp+620h+var_698]
0x18003048b  sub     r9, rdx
0x18003048e  movsx   r11, byte ptr [rax]
0x180030492  cmp     r9, r11
0x180030495  jbe     short loc_1800304BB
0x180030497  add     r10, rax
0x18003049a  movsx   rcx, r11b
0x18003049e  sub     r9, rcx
0x1800304a1  inc     r8d
0x1800304a4  lea     rcx, [rax+1]
0x1800304a8  cmp     rcx, r10
0x1800304ab  cmovz   rcx, rax
0x1800304af  mov     rax, rcx
0x1800304b2  movsx   r11, byte ptr [rcx]
0x1800304b6  cmp     r9, r11
0x1800304b9  ja      short loc_18003049A
0x1800304bb  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x1800304c0  mov     ecx, [rsp+720h+var_6E8]
0x1800304c4  add     ecx, r8d
0x1800304c7  mov     [rsp+720h+var_6E8], ecx
0x1800304cb  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x1800304d0  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x1800304d5  mov     r10, [rsp+720h+var_6D0]
0x1800304da  mov     r8d, [rsp+720h+var_6E4]
0x1800304df  sub     edi, 1
0x1800304e2  jz      loc_180030575
0x1800304e8  sub     edi, 1
0x1800304eb  jz      loc_18003059A
0x1800304f1  cmp     edi, 1
0x1800304f4  jnz     short loc_180030575
0x1800304f6  cmp     byte ptr [r14+0Bh], 0
0x1800304fb  jz      loc_1800305A4
0x180030501  mov     al, [r14+8]
0x180030505  sub     al, 47h ; 'G'
0x180030507  test    al, 0DFh
  ... truncated ...
```

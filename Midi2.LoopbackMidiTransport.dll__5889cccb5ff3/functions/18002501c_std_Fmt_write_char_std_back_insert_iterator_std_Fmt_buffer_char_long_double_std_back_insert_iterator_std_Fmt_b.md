# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18002501c`
- end: `0x1800256e6`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@OAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180022cc8`
- `0x180022df4`
- `0x180022fa0`
- `0x18002501c`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002b39c`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180025337`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180025337`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x180025138`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x180025138`

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
0x18002501c  mov     rax, rsp
0x18002501f  mov     [rax+10h], rbx
0x180025023  push    rbp
0x180025024  push    rsi
0x180025025  push    rdi
0x180025026  push    r12
0x180025028  push    r13
0x18002502a  push    r14
0x18002502c  push    r15
0x18002502e  lea     rbp, [rax-628h]
0x180025035  sub     rsp, 6F0h
0x18002503c  movaps  xmmword ptr [rax-48h], xmm6
0x180025040  mov     rax, cs:__security_cookie
0x180025047  xor     rax, rsp
0x18002504a  mov     [rbp+620h+var_50], rax
0x180025051  mov     r14, r9
0x180025054  movaps  xmm6, xmm2
0x180025057  mov     rbx, rdx
0x18002505a  mov     [rbp+620h+var_688], rcx
0x18002505e  mov     al, [r9+0Ah]
0x180025062  mov     byte ptr [rsp+720h+var_6F0+1], al
0x180025066  mov     r9d, 2
0x18002506c  test    al, al
0x18002506e  jnz     short loc_180025075
0x180025070  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x180025075  xor     sil, sil
0x180025078  mov     r13b, 65h ; 'e'
0x18002507b  mov     edx, [r14+4]
0x18002507f  xor     r15b, r15b
0x180025082  movsx   ecx, byte ptr [r14+8]
0x180025087  mov     edi, 4
0x18002508c  lea     r8d, [rdi-3]
0x180025090  sub     ecx, 41h ; 'A'
0x180025093  jz      short loc_180025101
0x180025095  sub     ecx, edi
0x180025097  jz      short loc_1800250EE
0x180025099  sub     ecx, r8d
0x18002509c  jz      short loc_1800250DB
0x18002509e  sub     ecx, r8d
0x1800250a1  jz      short loc_1800250BF
0x1800250a3  sub     ecx, 1Ah
0x1800250a6  jz      short loc_180025104
0x1800250a8  sub     ecx, edi
0x1800250aa  jz      short loc_1800250F1
0x1800250ac  sub     ecx, r8d
0x1800250af  jz      short loc_1800250DE
0x1800250b1  cmp     ecx, r8d
0x1800250b4  jz      short loc_1800250C2
0x1800250b6  lea     edi, [r8+2]
0x1800250ba  mov     r15b, r8b
0x1800250bd  jmp     short loc_180025107
0x1800250bf  mov     sil, r8b
0x1800250c2  cmp     edx, 0FFFFFFFFh
0x1800250c5  jnz     short loc_1800250CE
0x1800250c7  mov     edx, 6
0x1800250cc  jmp     short loc_1800250D4
0x1800250ce  test    edx, edx
0x1800250d0  cmovz   edx, r8d
0x1800250d4  mov     edi, 3
0x1800250d9  jmp     short loc_180025107
0x1800250db  mov     sil, r8b
0x1800250de  mov     eax, 6
0x1800250e3  cmp     edx, 0FFFFFFFFh
0x1800250e6  cmovz   edx, eax
0x1800250e9  mov     edi, r9d
0x1800250ec  jmp     short loc_180025107
0x1800250ee  mov     sil, r8b
0x1800250f1  mov     eax, 6
0x1800250f6  cmp     edx, 0FFFFFFFFh
0x1800250f9  cmovz   edx, eax
0x1800250fc  mov     edi, r8d
0x1800250ff  jmp     short loc_180025107
0x180025101  mov     sil, r8b
0x180025104  mov     r13b, 70h ; 'p'
0x180025107  xorps   xmm0, xmm0
0x18002510a  movups  [rsp+720h+var_6C8+8], xmm0
0x18002510f  mov     r12d, edx
0x180025112  mov     r8d, 432h
0x180025118  cmp     edx, r8d
0x18002511b  cmovg   r12d, r8d
0x18002511f  mov     [rbp+620h+var_6A0], r12d
0x180025123  lea     ecx, [rdx-432h]
0x180025129  xor     eax, eax
0x18002512b  cmp     edx, r8d
0x18002512e  cmovle  ecx, eax
0x180025131  mov     dword ptr [rsp+720h+var_6E0], ecx
0x180025135  movaps  xmm0, xmm6; X
0x180025138  call    cs:__imp__ldsign
0x18002513e  mov     edx, eax
0x180025140  test    eax, eax
0x180025142  setnz   byte ptr [rsp+720h+var_6F0+3]
0x180025147  ucomisd xmm6, xmm6
0x18002514b  setp    al
0x18002514e  cmp     al, 1
0x180025150  jnz     short loc_180025187
0x180025152  lea     rax, [rbp+620h+var_5C0]
0x180025156  lea     rcx, [rbp+620h+var_5BF]
0x18002515a  test    edx, edx
0x18002515c  cmovz   rcx, rax
0x180025160  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x180025165  mov     eax, dword ptr cs:aNan; "nan"
0x18002516b  mov     [rcx], ax
0x18002516e  mov     al, byte ptr cs:aNan+2; "n"
0x180025174  mov     [rcx+2], al
0x180025177  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002517c  add     r9, 3
0x180025180  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x180025185  jmp     short loc_1800251D4
0x180025187  movaps  xmm3, xmm6
0x18002518a  lea     r8, [rbp+620h+var_57]
0x180025191  lea     rdx, [rbp+620h+var_5C0]
0x180025195  lea     rcx, [rsp+720h+var_6B8+8]
0x18002519a  cmp     r12d, 0FFFFFFFFh
0x18002519e  jnz     short loc_1800251B7
0x1800251a0  test    r15b, r15b
0x1800251a3  jz      short loc_1800251AC
0x1800251a5  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x1800251aa  jmp     short loc_1800251C5
0x1800251ac  mov     [rsp+720h+var_700], edi
0x1800251b0  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x1800251b5  jmp     short loc_1800251C5
0x1800251b7  mov     dword ptr [rsp+720h+var_6F8], r12d
0x1800251bc  mov     [rsp+720h+var_700], edi
0x1800251c0  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x1800251c5  movaps  xmm0, [rsp+720h+var_6B8+8]
0x1800251ca  movaps  [rsp+720h+var_6C8+8], xmm0
0x1800251cf  movq    r9, xmm0
0x1800251d4  lea     rdx, [rbp+620h+var_5C0]
0x1800251d8  mov     [rsp+720h+var_6D8], rdx
0x1800251dd  mov     ecx, r9d
0x1800251e0  sub     ecx, edx
0x1800251e2  mov     [rsp+720h+var_6E8], ecx
0x1800251e6  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x1800251eb  jz      short loc_1800251F8
0x1800251ed  lea     rdx, [rbp+620h+var_5BF]
0x1800251f1  mov     [rsp+720h+var_6D8], rdx
0x1800251f6  jmp     short loc_180025205
0x1800251f8  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x1800251fd  jz      short loc_180025205
0x1800251ff  inc     ecx
0x180025201  mov     [rsp+720h+var_6E8], ecx
0x180025205  test    sil, sil
0x180025208  jz      short loc_180025237
0x18002520a  cmp     rdx, r9
0x18002520d  jz      short loc_180025233
0x18002520f  mov     cl, [rdx]
0x180025211  lea     eax, [rcx-61h]
0x180025214  cmp     al, 19h
0x180025216  ja      short loc_18002521D
0x180025218  sub     cl, 20h ; ' '
0x18002521b  mov     [rdx], cl
0x18002521d  inc     rdx
0x180025220  cmp     rdx, r9
0x180025223  jnz     short loc_18002520F
0x180025225  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002522a  mov     rdx, [rsp+720h+var_6D8]
0x18002522f  mov     ecx, [rsp+720h+var_6E8]
0x180025233  add     r13b, 0E0h
0x180025237  movq    rax, xmm6
0x18002523c  shr     rax, 34h
0x180025240  mov     r8d, 7FFh
0x180025246  and     eax, r8d
0x180025249  cmp     eax, r8d
0x18002524c  setnz   al
0x18002524f  xor     al, 1
0x180025251  mov     byte ptr [rsp+720h+var_6F0], al
0x180025255  mov     r15b, 0
0x180025258  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002525d  mov     r10, r9
0x180025260  mov     [rsp+720h+var_6D0], r9
0x180025265  mov     r11, r9
0x180025268  mov     [rbp+620h+var_690], r9
0x18002526c  mov     [rbp+620h+var_698], r9
0x180025270  mov     r8d, 0
0x180025276  mov     [rsp+720h+var_6E4], r8d
0x18002527b  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x180025280  xorps   xmm0, xmm0
0x180025283  movups  [rbp+620h+var_600], xmm0
0x180025287  mov     [rbp+620h+var_5F0], r8
0x18002528b  mov     [rbp+620h+var_5E8], 0Fh
0x180025293  mov     byte ptr [rbp+620h+var_600], r8b
0x180025297  jnz     loc_1800254E4
0x18002529d  mov     r12b, [r14+0Bh]
0x1800252a1  test    r12b, r12b
0x1800252a4  jnz     short loc_1800252B3
0x1800252a6  lea     rsi, [r14+0Ch]
0x1800252aa  cmp     [rsi], r12b
0x1800252ad  jz      loc_18002541B
0x1800252b3  mov     rax, rdx
0x1800252b6  cmp     rdx, r9
0x1800252b9  jnb     short loc_1800252E6
0x1800252bb  cmp     byte ptr [rax], 2Eh ; '.'
0x1800252be  jnz     short loc_1800252C9
0x1800252c0  mov     r11, rax
0x1800252c3  mov     [rbp+620h+var_690], rax
0x1800252c7  jmp     short loc_1800252D6
0x1800252c9  cmp     [rax], r13b
0x1800252cc  jnz     short loc_1800252D6
0x1800252ce  mov     r10, rax
0x1800252d1  mov     [rsp+720h+var_6D0], rax
0x1800252d6  inc     rax
0x1800252d9  cmp     rax, r9
0x1800252dc  jb      short loc_1800252BB
0x1800252de  cmp     r10, r11
0x1800252e1  mov     rax, r10
0x1800252e4  jb      short loc_1800252E9
0x1800252e6  mov     rax, r11
0x1800252e9  mov     [rbp+620h+var_698], rax
0x1800252ed  test    r12b, r12b
0x1800252f0  jz      short loc_180025305
0x1800252f2  cmp     r11, r9
0x1800252f5  jnz     short loc_180025305
0x1800252f7  inc     ecx
0x1800252f9  mov     [rsp+720h+var_6E8], ecx
0x1800252fd  mov     r15b, 1
0x180025300  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x180025305  lea     rsi, [r14+0Ch]
0x180025309  cmp     byte ptr [rsi], 0
0x18002530c  jz      loc_18002541B
0x180025312  mov     rax, [rbp+620h+arg_20]
0x180025319  test    rax, rax
0x18002531c  jz      short loc_180025335
0x18002531e  mov     rcx, [rax+8]
0x180025322  mov     [rsp+720h+var_6A8], rcx
0x180025327  mov     rax, [rcx]
0x18002532a  mov     rax, [rax+8]
0x18002532e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025333  jmp     short loc_180025342
0x180025335  mov     cl, 1
0x180025337  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002533d  mov     [rsp+720h+var_6A8], rax
0x180025342  lea     rcx, [rsp+720h+var_6B8+8]
0x180025347  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002534c  mov     rcx, rax
0x18002534f  mov     rax, [rax]
0x180025352  lea     rdx, [rbp+620h+var_5E0]
0x180025356  mov     rax, [rax+28h]
0x18002535a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002535f  lea     rdx, [rbp+620h+var_5E0]
0x180025363  lea     rcx, [rbp+620h+var_600]
0x180025367  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002536c  lea     rcx, [rbp+620h+var_5E0]
0x180025370  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180025375  nop
0x180025376  mov     rcx, [rsp+720h+var_6A8]
0x18002537b  test    rcx, rcx
0x18002537e  jz      short loc_1800253A4
0x180025380  mov     rax, [rcx]
0x180025383  mov     rax, [rax+10h]
0x180025387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002538c  mov     rcx, rax
0x18002538f  test    rax, rax
0x180025392  jz      short loc_1800253A4
0x180025394  mov     rax, [rax]
0x180025397  mov     edx, 1
0x18002539c  mov     rax, [rax]
0x18002539f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253a4  lea     rax, [rbp+620h+var_600]
0x1800253a8  cmp     [rbp+620h+var_5E8], 0Fh
0x1800253ad  cmova   rax, qword ptr [rbp+620h+var_600]
0x1800253b2  mov     r10, [rbp+620h+var_5F0]
0x1800253b6  mov     rdx, [rsp+720h+var_6D8]
0x1800253bb  xor     r8d, r8d
0x1800253be  test    r10, r10
0x1800253c1  jz      short loc_1800253F7
0x1800253c3  mov     r9, [rbp+620h+var_698]
0x1800253c7  sub     r9, rdx
0x1800253ca  movsx   r11, byte ptr [rax]
0x1800253ce  cmp     r9, r11
0x1800253d1  jbe     short loc_1800253F7
0x1800253d3  add     r10, rax
0x1800253d6  movsx   rcx, r11b
0x1800253da  sub     r9, rcx
0x1800253dd  inc     r8d
0x1800253e0  lea     rcx, [rax+1]
0x1800253e4  cmp     rcx, r10
0x1800253e7  cmovz   rcx, rax
0x1800253eb  mov     rax, rcx
0x1800253ee  movsx   r11, byte ptr [rcx]
0x1800253f2  cmp     r9, r11
0x1800253f5  ja      short loc_1800253D6
0x1800253f7  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x1800253fc  mov     ecx, [rsp+720h+var_6E8]
0x180025400  add     ecx, r8d
0x180025403  mov     [rsp+720h+var_6E8], ecx
0x180025407  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002540c  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x180025411  mov     r10, [rsp+720h+var_6D0]
0x180025416  mov     r8d, [rsp+720h+var_6E4]
0x18002541b  sub     edi, 1
0x18002541e  jz      loc_1800254B1
0x180025424  sub     edi, 1
0x180025427  jz      loc_1800254D6
0x18002542d  cmp     edi, 1
0x180025430  jnz     short loc_1800254B1
0x180025432  cmp     byte ptr [r14+0Bh], 0
0x180025437  jz      loc_1800254E0
0x18002543d  mov     al, [r14+8]
0x180025441  sub     al, 47h ; 'G'
0x180025443  test    al, 0DFh
  ... truncated ...
```

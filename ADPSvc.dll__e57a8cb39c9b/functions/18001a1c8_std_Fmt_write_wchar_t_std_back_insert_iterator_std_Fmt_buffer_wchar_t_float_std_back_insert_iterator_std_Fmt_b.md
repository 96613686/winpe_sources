# std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,float>(std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,float,std::_Basic_format_specs<wchar_t> const &,std::_Lazy_locale)

- ea: `0x18001a1c8`
- end: `0x18001a83e`
- name: `??$_Fmt_write@_WV?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@0@V10@MAEBU?$_Basic_format_specs@_W@0@V_Lazy_locale@0@@Z`
- size: `1654`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, double, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001cf28`

## callees

- `0x180002250`
- `0x180013830`
- `0x180018970`
- `0x18001a1c8`
- `0x180020724`
- `0x180020b94`
- `0x180020fac`
- `0x180023d0c`
- `0x180023e04`
- `0x180023f08`
- `0x1800ca010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18001a4e1`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18001a4e1`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18001a2e4`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18001a2e4`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int16 **__fastcall std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,float>(
        __int16 **a1,
        __int16 *a2,
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
  __int16 *v45; // rax
  __int16 **v46; // rbx
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
  __int16 *v60[2]; // [rsp+88h] [rbp-80h] BYREF
  char *v61; // [rsp+98h] [rbp-70h] BYREF
  __int16 **v62; // [rsp+A0h] [rbp-68h]
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
  LODWORD(v60[0]) = v12;
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
        v28 = std::use_facet<std::numpunct<wchar_t>>(&v57);
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
          v22 = LODWORD(v60[0]) + v53 - v37;
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
    `std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,double>'::`2'::_lambda_1_::operator()(
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
    a2 = std::ranges::_Copy_fn::operator()<std::wstring_view const &,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>>(
           v60,
           (__int64)&v57,
           (__int64)a2)[1];
    --v41;
  }
  v45 = *(__int16 **)`std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,double>'::`2'::_lambda_1_::operator()(
                       v63,
                       v60,
                       a2);
  while ( v42 > 0 )
  {
    v45 = std::ranges::_Copy_fn::operator()<std::wstring_view const &,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>>(
            v60,
            (__int64)&v57,
            (__int64)v45)[1];
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
0x18001a1c8  mov     rax, rsp
0x18001a1cb  mov     [rax+10h], rbx
0x18001a1cf  push    rbp
0x18001a1d0  push    rsi
0x18001a1d1  push    rdi
0x18001a1d2  push    r12
0x18001a1d4  push    r13
0x18001a1d6  push    r14
0x18001a1d8  push    r15
0x18001a1da  lea     rbp, [rax-628h]
0x18001a1e1  sub     rsp, 6F0h
0x18001a1e8  movaps  xmmword ptr [rax-48h], xmm6
0x18001a1ec  mov     rax, cs:__security_cookie
0x18001a1f3  xor     rax, rsp
0x18001a1f6  mov     [rbp+620h+var_50], rax
0x18001a1fd  mov     r14, r9
0x18001a200  movaps  xmm6, xmm2
0x18001a203  mov     rbx, rdx
0x18001a206  mov     [rbp+620h+var_688], rcx
0x18001a20a  mov     al, [r9+0Ah]
0x18001a20e  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18001a212  mov     r9d, 2
0x18001a218  test    al, al
0x18001a21a  jnz     short loc_18001A221
0x18001a21c  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18001a221  xor     dil, dil
0x18001a224  mov     r13b, 65h ; 'e'
0x18001a227  mov     edx, [r14+4]
0x18001a22b  xor     r15b, r15b
0x18001a22e  movsx   ecx, byte ptr [r14+8]
0x18001a233  mov     esi, 4
0x18001a238  lea     r8d, [rsi-3]
0x18001a23c  sub     ecx, 41h ; 'A'
0x18001a23f  jz      short loc_18001A2AD
0x18001a241  sub     ecx, esi
0x18001a243  jz      short loc_18001A29A
0x18001a245  sub     ecx, r8d
0x18001a248  jz      short loc_18001A287
0x18001a24a  sub     ecx, r8d
0x18001a24d  jz      short loc_18001A26B
0x18001a24f  sub     ecx, 1Ah
0x18001a252  jz      short loc_18001A2B0
0x18001a254  sub     ecx, esi
0x18001a256  jz      short loc_18001A29D
0x18001a258  sub     ecx, r8d
0x18001a25b  jz      short loc_18001A28A
0x18001a25d  cmp     ecx, r8d
0x18001a260  jz      short loc_18001A26E
0x18001a262  lea     esi, [r8+2]
0x18001a266  mov     r15b, r8b
0x18001a269  jmp     short loc_18001A2B3
0x18001a26b  mov     dil, r8b
0x18001a26e  cmp     edx, 0FFFFFFFFh
0x18001a271  jnz     short loc_18001A27A
0x18001a273  mov     edx, 6
0x18001a278  jmp     short loc_18001A280
0x18001a27a  test    edx, edx
0x18001a27c  cmovz   edx, r8d
0x18001a280  mov     esi, 3
0x18001a285  jmp     short loc_18001A2B3
0x18001a287  mov     dil, r8b
0x18001a28a  mov     eax, 6
0x18001a28f  cmp     edx, 0FFFFFFFFh
0x18001a292  cmovz   edx, eax
0x18001a295  mov     esi, r9d
0x18001a298  jmp     short loc_18001A2B3
0x18001a29a  mov     dil, r8b
0x18001a29d  mov     eax, 6
0x18001a2a2  cmp     edx, 0FFFFFFFFh
0x18001a2a5  cmovz   edx, eax
0x18001a2a8  mov     esi, r8d
0x18001a2ab  jmp     short loc_18001A2B3
0x18001a2ad  mov     dil, r8b
0x18001a2b0  mov     r13b, 70h ; 'p'
0x18001a2b3  xorps   xmm0, xmm0
0x18001a2b6  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18001a2bb  mov     r12d, edx
0x18001a2be  mov     r8d, 432h
0x18001a2c4  cmp     edx, r8d
0x18001a2c7  cmovg   r12d, r8d
0x18001a2cb  mov     [rbp+620h+var_6A0], r12d
0x18001a2cf  lea     ecx, [rdx-432h]
0x18001a2d5  xor     eax, eax
0x18001a2d7  cmp     edx, r8d
0x18001a2da  cmovle  ecx, eax
0x18001a2dd  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18001a2e1  movaps  xmm0, xmm6
0x18001a2e4  call    cs:__imp__o__fdsign
0x18001a2ea  mov     edx, eax
0x18001a2ec  test    eax, eax
0x18001a2ee  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18001a2f3  ucomiss xmm6, xmm6
0x18001a2f6  setp    al
0x18001a2f9  cmp     al, 1
0x18001a2fb  jnz     short loc_18001A332
0x18001a2fd  lea     rax, [rbp+620h+var_5C0]
0x18001a301  lea     rcx, [rbp+620h+var_5BF]
0x18001a305  test    edx, edx
0x18001a307  cmovz   rcx, rax
0x18001a30b  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x18001a310  mov     eax, dword ptr cs:aNan; "nan"
0x18001a316  mov     [rcx], ax
0x18001a319  mov     al, byte ptr cs:aNan+2; "n"
0x18001a31f  mov     [rcx+2], al
0x18001a322  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18001a327  add     r9, 3
0x18001a32b  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x18001a330  jmp     short loc_18001A37D
0x18001a332  movaps  xmm3, xmm6
0x18001a335  lea     r8, [rbp+620h+var_57]
0x18001a33c  lea     rdx, [rbp+620h+var_5C0]
0x18001a340  lea     rcx, [rsp+720h+var_6B8]
0x18001a345  cmp     r12d, 0FFFFFFFFh
0x18001a349  jnz     short loc_18001A362
0x18001a34b  test    r15b, r15b
0x18001a34e  jz      short loc_18001A357
0x18001a350  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x18001a355  jmp     short loc_18001A370
0x18001a357  mov     [rsp+720h+var_700], esi
0x18001a35b  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x18001a360  jmp     short loc_18001A370
0x18001a362  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18001a367  mov     [rsp+720h+var_700], esi
0x18001a36b  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x18001a370  movups  xmm0, xmmword ptr [rax]
0x18001a373  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18001a378  movq    r9, xmm0
0x18001a37d  lea     rdx, [rbp+620h+var_5C0]
0x18001a381  mov     [rsp+720h+var_6D8], rdx
0x18001a386  mov     ecx, r9d
0x18001a389  sub     ecx, edx
0x18001a38b  mov     [rsp+720h+var_6E8], ecx
0x18001a38f  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18001a394  jz      short loc_18001A3A1
0x18001a396  lea     rdx, [rbp+620h+var_5BF]
0x18001a39a  mov     [rsp+720h+var_6D8], rdx
0x18001a39f  jmp     short loc_18001A3AE
0x18001a3a1  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18001a3a6  jz      short loc_18001A3AE
0x18001a3a8  inc     ecx
0x18001a3aa  mov     [rsp+720h+var_6E8], ecx
0x18001a3ae  test    dil, dil
0x18001a3b1  jz      short loc_18001A3E0
0x18001a3b3  cmp     rdx, r9
0x18001a3b6  jz      short loc_18001A3DC
0x18001a3b8  mov     cl, [rdx]
0x18001a3ba  lea     eax, [rcx-61h]
0x18001a3bd  cmp     al, 19h
0x18001a3bf  ja      short loc_18001A3C6
0x18001a3c1  sub     cl, 20h ; ' '
0x18001a3c4  mov     [rdx], cl
0x18001a3c6  inc     rdx
0x18001a3c9  cmp     rdx, r9
0x18001a3cc  jnz     short loc_18001A3B8
0x18001a3ce  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18001a3d3  mov     rdx, [rsp+720h+var_6D8]
0x18001a3d8  mov     ecx, [rsp+720h+var_6E8]
0x18001a3dc  add     r13b, 0E0h
0x18001a3e0  movd    eax, xmm6
0x18001a3e4  mov     r8d, 7F800000h
0x18001a3ea  and     eax, r8d
0x18001a3ed  cmp     eax, r8d
0x18001a3f0  setnz   al
0x18001a3f3  xor     al, 1
0x18001a3f5  mov     byte ptr [rsp+720h+var_6F0], al
0x18001a3f9  mov     dil, 0
0x18001a3fc  mov     byte ptr [rsp+720h+var_6F0+2], dil
0x18001a401  mov     r10, r9
0x18001a404  mov     qword ptr [rsp+720h+var_6D0], r9
0x18001a409  mov     r11, r9
0x18001a40c  mov     [rbp+620h+var_690], r9
0x18001a410  mov     [rsp+720h+var_6A8], r9
0x18001a415  mov     r8d, 0
0x18001a41b  mov     [rsp+720h+var_6E4], r8d
0x18001a420  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18001a425  xorps   xmm0, xmm0
0x18001a428  movups  [rbp+620h+var_600], xmm0
0x18001a42c  mov     [rbp+620h+var_5F0], r8
0x18001a430  mov     [rbp+620h+var_5E8], 0Fh
0x18001a438  mov     byte ptr [rbp+620h+var_600], dil
0x18001a43c  jnz     loc_18001A68C
0x18001a442  mov     r12b, [r14+0Bh]
0x18001a446  test    r12b, r12b
0x18001a449  jnz     short loc_18001A458
0x18001a44b  lea     r15, [r14+0Ch]
0x18001a44f  cmp     [r15], r12b
0x18001a452  jz      loc_18001A5C4
0x18001a458  mov     rax, rdx
0x18001a45b  cmp     rdx, r9
0x18001a45e  jnb     short loc_18001A48B
0x18001a460  cmp     byte ptr [rax], 2Eh ; '.'
0x18001a463  jnz     short loc_18001A46E
0x18001a465  mov     r11, rax
0x18001a468  mov     [rbp+620h+var_690], rax
0x18001a46c  jmp     short loc_18001A47B
0x18001a46e  cmp     [rax], r13b
0x18001a471  jnz     short loc_18001A47B
0x18001a473  mov     r10, rax
0x18001a476  mov     qword ptr [rsp+720h+var_6D0], rax
0x18001a47b  inc     rax
0x18001a47e  cmp     rax, r9
0x18001a481  jb      short loc_18001A460
0x18001a483  cmp     r10, r11
0x18001a486  mov     rax, r10
0x18001a489  jb      short loc_18001A48E
0x18001a48b  mov     rax, r11
0x18001a48e  mov     [rsp+720h+var_6A8], rax
0x18001a493  test    r12b, r12b
0x18001a496  jz      short loc_18001A4AB
0x18001a498  cmp     r11, r9
0x18001a49b  jnz     short loc_18001A4AB
0x18001a49d  inc     ecx
0x18001a49f  mov     [rsp+720h+var_6E8], ecx
0x18001a4a3  mov     dil, 1
0x18001a4a6  mov     byte ptr [rsp+720h+var_6F0+2], dil
0x18001a4ab  lea     r15, [r14+0Ch]
0x18001a4af  cmp     byte ptr [r15], 0
0x18001a4b3  jz      loc_18001A5C4
0x18001a4b9  mov     rax, [rbp+620h+arg_20]
0x18001a4c0  test    rax, rax
0x18001a4c3  jz      short loc_18001A4DF
0x18001a4c5  mov     rdi, [rax+8]
0x18001a4c9  mov     [rsp+720h+var_6B0], rdi
0x18001a4ce  mov     rax, [rdi]
0x18001a4d1  mov     rcx, rdi
0x18001a4d4  mov     rax, [rax+8]
0x18001a4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4dd  jmp     short loc_18001A4EF
0x18001a4df  mov     cl, 1
0x18001a4e1  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18001a4e7  mov     rdi, rax
0x18001a4ea  mov     [rsp+720h+var_6B0], rax
0x18001a4ef  lea     rcx, [rsp+720h+var_6B8]
0x18001a4f4  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<wchar_t>>(std::locale const &)
0x18001a4f9  mov     rcx, rax
0x18001a4fc  mov     rax, [rax]
0x18001a4ff  lea     rdx, [rbp+620h+var_5E0]
0x18001a503  mov     rax, [rax+28h]
0x18001a507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a50c  lea     rdx, [rbp+620h+var_5E0]
0x18001a510  lea     rcx, [rbp+620h+var_600]
0x18001a514  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001a519  lea     rcx, [rbp+620h+var_5E0]
0x18001a51d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001a522  nop
0x18001a523  test    rdi, rdi
0x18001a526  jz      short loc_18001A54F
0x18001a528  mov     rax, [rdi]
0x18001a52b  mov     rcx, rdi
0x18001a52e  mov     rax, [rax+10h]
0x18001a532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a537  mov     rcx, rax
0x18001a53a  test    rax, rax
0x18001a53d  jz      short loc_18001A54F
0x18001a53f  mov     rax, [rax]
0x18001a542  mov     edx, 1
0x18001a547  mov     rax, [rax]
0x18001a54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a54f  lea     rax, [rbp+620h+var_600]
0x18001a553  cmp     [rbp+620h+var_5E8], 0Fh
0x18001a558  cmova   rax, qword ptr [rbp+620h+var_600]
0x18001a55d  mov     r10, [rbp+620h+var_5F0]
0x18001a561  mov     rdx, [rsp+720h+var_6D8]
0x18001a566  xor     r8d, r8d
0x18001a569  test    r10, r10
0x18001a56c  jz      short loc_18001A5A0
0x18001a56e  mov     r9, [rsp+720h+var_6A8]
0x18001a573  sub     r9, rdx
0x18001a576  movsx   r11, byte ptr [rax]
0x18001a57a  cmp     r9, r11
0x18001a57d  jbe     short loc_18001A5A0
0x18001a57f  add     r10, rax
0x18001a582  movsx   rcx, r11b
0x18001a586  sub     r9, rcx
0x18001a589  inc     r8d
0x18001a58c  lea     rcx, [rax+1]
0x18001a590  cmp     rcx, r10
0x18001a593  cmovnz  rax, rcx
0x18001a597  movsx   r11, byte ptr [rax]
0x18001a59b  cmp     r9, r11
0x18001a59e  ja      short loc_18001A582
0x18001a5a0  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18001a5a5  mov     ecx, [rsp+720h+var_6E8]
0x18001a5a9  add     ecx, r8d
0x18001a5ac  mov     [rsp+720h+var_6E8], ecx
0x18001a5b0  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18001a5b5  mov     dil, byte ptr [rsp+720h+var_6F0+2]
0x18001a5ba  mov     r10, qword ptr [rsp+720h+var_6D0]
0x18001a5bf  mov     r8d, [rsp+720h+var_6E4]
0x18001a5c4  sub     esi, 1
0x18001a5c7  jz      loc_18001A658
0x18001a5cd  sub     esi, 1
0x18001a5d0  jz      loc_18001A67E
0x18001a5d6  cmp     esi, 1
0x18001a5d9  jnz     short loc_18001A658
0x18001a5db  cmp     byte ptr [r14+0Bh], 0
0x18001a5e0  jz      loc_18001A688
0x18001a5e6  mov     al, [r14+8]
0x18001a5ea  sub     al, 47h ; 'G'
0x18001a5ec  test    al, 0DFh
  ... truncated ...
```

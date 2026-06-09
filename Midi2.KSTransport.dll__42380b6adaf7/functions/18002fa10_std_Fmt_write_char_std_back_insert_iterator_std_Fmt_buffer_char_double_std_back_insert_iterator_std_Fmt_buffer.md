# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18002fa10`
- end: `0x1800300da`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@NAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
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
- `0x18002fa10`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x1800369ac`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002fd2b`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002fd2b`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18002fb2c`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18002fb2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,double>(
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
  v61 = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  v63 = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v57 = v13;
  v53 = (unsigned int)_o__dsign(v13, v9, 1074, 2) != 0;
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
        *(_BYTE *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 8)) = v46;
        ++*(_QWORD *)(a2 + 16);
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
0x18002fa10  mov     rax, rsp
0x18002fa13  mov     [rax+10h], rbx
0x18002fa17  push    rbp
0x18002fa18  push    rsi
0x18002fa19  push    rdi
0x18002fa1a  push    r12
0x18002fa1c  push    r13
0x18002fa1e  push    r14
0x18002fa20  push    r15
0x18002fa22  lea     rbp, [rax-628h]
0x18002fa29  sub     rsp, 6F0h
0x18002fa30  movaps  xmmword ptr [rax-48h], xmm6
0x18002fa34  mov     rax, cs:__security_cookie
0x18002fa3b  xor     rax, rsp
0x18002fa3e  mov     [rbp+620h+var_50], rax
0x18002fa45  mov     r14, r9
0x18002fa48  movaps  xmm6, xmm2
0x18002fa4b  mov     rbx, rdx
0x18002fa4e  mov     [rbp+620h+var_688], rcx
0x18002fa52  mov     al, [r9+0Ah]
0x18002fa56  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18002fa5a  mov     r9d, 2
0x18002fa60  test    al, al
0x18002fa62  jnz     short loc_18002FA69
0x18002fa64  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18002fa69  xor     sil, sil
0x18002fa6c  mov     r13b, 65h ; 'e'
0x18002fa6f  mov     edx, [r14+4]
0x18002fa73  xor     r15b, r15b
0x18002fa76  movsx   ecx, byte ptr [r14+8]
0x18002fa7b  mov     edi, 4
0x18002fa80  lea     r8d, [rdi-3]
0x18002fa84  sub     ecx, 41h ; 'A'
0x18002fa87  jz      short loc_18002FAF5
0x18002fa89  sub     ecx, edi
0x18002fa8b  jz      short loc_18002FAE2
0x18002fa8d  sub     ecx, r8d
0x18002fa90  jz      short loc_18002FACF
0x18002fa92  sub     ecx, r8d
0x18002fa95  jz      short loc_18002FAB3
0x18002fa97  sub     ecx, 1Ah
0x18002fa9a  jz      short loc_18002FAF8
0x18002fa9c  sub     ecx, edi
0x18002fa9e  jz      short loc_18002FAE5
0x18002faa0  sub     ecx, r8d
0x18002faa3  jz      short loc_18002FAD2
0x18002faa5  cmp     ecx, r8d
0x18002faa8  jz      short loc_18002FAB6
0x18002faaa  lea     edi, [r8+2]
0x18002faae  mov     r15b, r8b
0x18002fab1  jmp     short loc_18002FAFB
0x18002fab3  mov     sil, r8b
0x18002fab6  cmp     edx, 0FFFFFFFFh
0x18002fab9  jnz     short loc_18002FAC2
0x18002fabb  mov     edx, 6
0x18002fac0  jmp     short loc_18002FAC8
0x18002fac2  test    edx, edx
0x18002fac4  cmovz   edx, r8d
0x18002fac8  mov     edi, 3
0x18002facd  jmp     short loc_18002FAFB
0x18002facf  mov     sil, r8b
0x18002fad2  mov     eax, 6
0x18002fad7  cmp     edx, 0FFFFFFFFh
0x18002fada  cmovz   edx, eax
0x18002fadd  mov     edi, r9d
0x18002fae0  jmp     short loc_18002FAFB
0x18002fae2  mov     sil, r8b
0x18002fae5  mov     eax, 6
0x18002faea  cmp     edx, 0FFFFFFFFh
0x18002faed  cmovz   edx, eax
0x18002faf0  mov     edi, r8d
0x18002faf3  jmp     short loc_18002FAFB
0x18002faf5  mov     sil, r8b
0x18002faf8  mov     r13b, 70h ; 'p'
0x18002fafb  xorps   xmm0, xmm0
0x18002fafe  movups  [rsp+720h+var_6C8+8], xmm0
0x18002fb03  mov     r12d, edx
0x18002fb06  mov     r8d, 432h
0x18002fb0c  cmp     edx, r8d
0x18002fb0f  cmovg   r12d, r8d
0x18002fb13  mov     [rbp+620h+var_6A0], r12d
0x18002fb17  lea     ecx, [rdx-432h]
0x18002fb1d  xor     eax, eax
0x18002fb1f  cmp     edx, r8d
0x18002fb22  cmovle  ecx, eax
0x18002fb25  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18002fb29  movaps  xmm0, xmm6
0x18002fb2c  call    cs:__imp__o__dsign
0x18002fb32  mov     edx, eax
0x18002fb34  test    eax, eax
0x18002fb36  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18002fb3b  ucomisd xmm6, xmm6
0x18002fb3f  setp    al
0x18002fb42  cmp     al, 1
0x18002fb44  jnz     short loc_18002FB7B
0x18002fb46  lea     rax, [rbp+620h+var_5C0]
0x18002fb4a  lea     rcx, [rbp+620h+var_5BF]
0x18002fb4e  test    edx, edx
0x18002fb50  cmovz   rcx, rax
0x18002fb54  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x18002fb59  mov     eax, dword ptr cs:aNan; "nan"
0x18002fb5f  mov     [rcx], ax
0x18002fb62  mov     al, byte ptr cs:aNan+2; "n"
0x18002fb68  mov     [rcx+2], al
0x18002fb6b  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002fb70  add     r9, 3
0x18002fb74  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x18002fb79  jmp     short loc_18002FBC8
0x18002fb7b  movaps  xmm3, xmm6
0x18002fb7e  lea     r8, [rbp+620h+var_57]
0x18002fb85  lea     rdx, [rbp+620h+var_5C0]
0x18002fb89  lea     rcx, [rsp+720h+var_6B8+8]
0x18002fb8e  cmp     r12d, 0FFFFFFFFh
0x18002fb92  jnz     short loc_18002FBAB
0x18002fb94  test    r15b, r15b
0x18002fb97  jz      short loc_18002FBA0
0x18002fb99  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18002fb9e  jmp     short loc_18002FBB9
0x18002fba0  mov     [rsp+720h+var_700], edi
0x18002fba4  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18002fba9  jmp     short loc_18002FBB9
0x18002fbab  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18002fbb0  mov     [rsp+720h+var_700], edi
0x18002fbb4  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18002fbb9  movaps  xmm0, [rsp+720h+var_6B8+8]
0x18002fbbe  movaps  [rsp+720h+var_6C8+8], xmm0
0x18002fbc3  movq    r9, xmm0
0x18002fbc8  lea     rdx, [rbp+620h+var_5C0]
0x18002fbcc  mov     [rsp+720h+var_6D8], rdx
0x18002fbd1  mov     ecx, r9d
0x18002fbd4  sub     ecx, edx
0x18002fbd6  mov     [rsp+720h+var_6E8], ecx
0x18002fbda  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18002fbdf  jz      short loc_18002FBEC
0x18002fbe1  lea     rdx, [rbp+620h+var_5BF]
0x18002fbe5  mov     [rsp+720h+var_6D8], rdx
0x18002fbea  jmp     short loc_18002FBF9
0x18002fbec  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18002fbf1  jz      short loc_18002FBF9
0x18002fbf3  inc     ecx
0x18002fbf5  mov     [rsp+720h+var_6E8], ecx
0x18002fbf9  test    sil, sil
0x18002fbfc  jz      short loc_18002FC2B
0x18002fbfe  cmp     rdx, r9
0x18002fc01  jz      short loc_18002FC27
0x18002fc03  mov     cl, [rdx]
0x18002fc05  lea     eax, [rcx-61h]
0x18002fc08  cmp     al, 19h
0x18002fc0a  ja      short loc_18002FC11
0x18002fc0c  sub     cl, 20h ; ' '
0x18002fc0f  mov     [rdx], cl
0x18002fc11  inc     rdx
0x18002fc14  cmp     rdx, r9
0x18002fc17  jnz     short loc_18002FC03
0x18002fc19  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002fc1e  mov     rdx, [rsp+720h+var_6D8]
0x18002fc23  mov     ecx, [rsp+720h+var_6E8]
0x18002fc27  add     r13b, 0E0h
0x18002fc2b  movq    rax, xmm6
0x18002fc30  shr     rax, 34h
0x18002fc34  mov     r8d, 7FFh
0x18002fc3a  and     eax, r8d
0x18002fc3d  cmp     eax, r8d
0x18002fc40  setnz   al
0x18002fc43  xor     al, 1
0x18002fc45  mov     byte ptr [rsp+720h+var_6F0], al
0x18002fc49  mov     r15b, 0
0x18002fc4c  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002fc51  mov     r10, r9
0x18002fc54  mov     [rsp+720h+var_6D0], r9
0x18002fc59  mov     r11, r9
0x18002fc5c  mov     [rbp+620h+var_690], r9
0x18002fc60  mov     [rbp+620h+var_698], r9
0x18002fc64  mov     r8d, 0
0x18002fc6a  mov     [rsp+720h+var_6E4], r8d
0x18002fc6f  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002fc74  xorps   xmm0, xmm0
0x18002fc77  movups  [rbp+620h+var_600], xmm0
0x18002fc7b  mov     [rbp+620h+var_5F0], r8
0x18002fc7f  mov     [rbp+620h+var_5E8], 0Fh
0x18002fc87  mov     byte ptr [rbp+620h+var_600], r8b
0x18002fc8b  jnz     loc_18002FED8
0x18002fc91  mov     r12b, [r14+0Bh]
0x18002fc95  test    r12b, r12b
0x18002fc98  jnz     short loc_18002FCA7
0x18002fc9a  lea     rsi, [r14+0Ch]
0x18002fc9e  cmp     [rsi], r12b
0x18002fca1  jz      loc_18002FE0F
0x18002fca7  mov     rax, rdx
0x18002fcaa  cmp     rdx, r9
0x18002fcad  jnb     short loc_18002FCDA
0x18002fcaf  cmp     byte ptr [rax], 2Eh ; '.'
0x18002fcb2  jnz     short loc_18002FCBD
0x18002fcb4  mov     r11, rax
0x18002fcb7  mov     [rbp+620h+var_690], rax
0x18002fcbb  jmp     short loc_18002FCCA
0x18002fcbd  cmp     [rax], r13b
0x18002fcc0  jnz     short loc_18002FCCA
0x18002fcc2  mov     r10, rax
0x18002fcc5  mov     [rsp+720h+var_6D0], rax
0x18002fcca  inc     rax
0x18002fccd  cmp     rax, r9
0x18002fcd0  jb      short loc_18002FCAF
0x18002fcd2  cmp     r10, r11
0x18002fcd5  mov     rax, r10
0x18002fcd8  jb      short loc_18002FCDD
0x18002fcda  mov     rax, r11
0x18002fcdd  mov     [rbp+620h+var_698], rax
0x18002fce1  test    r12b, r12b
0x18002fce4  jz      short loc_18002FCF9
0x18002fce6  cmp     r11, r9
0x18002fce9  jnz     short loc_18002FCF9
0x18002fceb  inc     ecx
0x18002fced  mov     [rsp+720h+var_6E8], ecx
0x18002fcf1  mov     r15b, 1
0x18002fcf4  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002fcf9  lea     rsi, [r14+0Ch]
0x18002fcfd  cmp     byte ptr [rsi], 0
0x18002fd00  jz      loc_18002FE0F
0x18002fd06  mov     rax, [rbp+620h+arg_20]
0x18002fd0d  test    rax, rax
0x18002fd10  jz      short loc_18002FD29
0x18002fd12  mov     rcx, [rax+8]
0x18002fd16  mov     [rsp+720h+var_6A8], rcx
0x18002fd1b  mov     rax, [rcx]
0x18002fd1e  mov     rax, [rax+8]
0x18002fd22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd27  jmp     short loc_18002FD36
0x18002fd29  mov     cl, 1
0x18002fd2b  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002fd31  mov     [rsp+720h+var_6A8], rax
0x18002fd36  lea     rcx, [rsp+720h+var_6B8+8]
0x18002fd3b  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002fd40  mov     rcx, rax
0x18002fd43  mov     rax, [rax]
0x18002fd46  lea     rdx, [rbp+620h+var_5E0]
0x18002fd4a  mov     rax, [rax+28h]
0x18002fd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd53  lea     rdx, [rbp+620h+var_5E0]
0x18002fd57  lea     rcx, [rbp+620h+var_600]
0x18002fd5b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002fd60  lea     rcx, [rbp+620h+var_5E0]
0x18002fd64  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002fd69  nop
0x18002fd6a  mov     rcx, [rsp+720h+var_6A8]
0x18002fd6f  test    rcx, rcx
0x18002fd72  jz      short loc_18002FD98
0x18002fd74  mov     rax, [rcx]
0x18002fd77  mov     rax, [rax+10h]
0x18002fd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd80  mov     rcx, rax
0x18002fd83  test    rax, rax
0x18002fd86  jz      short loc_18002FD98
0x18002fd88  mov     rax, [rax]
0x18002fd8b  mov     edx, 1
0x18002fd90  mov     rax, [rax]
0x18002fd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd98  lea     rax, [rbp+620h+var_600]
0x18002fd9c  cmp     [rbp+620h+var_5E8], 0Fh
0x18002fda1  cmova   rax, qword ptr [rbp+620h+var_600]
0x18002fda6  mov     r10, [rbp+620h+var_5F0]
0x18002fdaa  mov     rdx, [rsp+720h+var_6D8]
0x18002fdaf  xor     r8d, r8d
0x18002fdb2  test    r10, r10
0x18002fdb5  jz      short loc_18002FDEB
0x18002fdb7  mov     r9, [rbp+620h+var_698]
0x18002fdbb  sub     r9, rdx
0x18002fdbe  movsx   r11, byte ptr [rax]
0x18002fdc2  cmp     r9, r11
0x18002fdc5  jbe     short loc_18002FDEB
0x18002fdc7  add     r10, rax
0x18002fdca  movsx   rcx, r11b
0x18002fdce  sub     r9, rcx
0x18002fdd1  inc     r8d
0x18002fdd4  lea     rcx, [rax+1]
0x18002fdd8  cmp     rcx, r10
0x18002fddb  cmovz   rcx, rax
0x18002fddf  mov     rax, rcx
0x18002fde2  movsx   r11, byte ptr [rcx]
0x18002fde6  cmp     r9, r11
0x18002fde9  ja      short loc_18002FDCA
0x18002fdeb  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002fdf0  mov     ecx, [rsp+720h+var_6E8]
0x18002fdf4  add     ecx, r8d
0x18002fdf7  mov     [rsp+720h+var_6E8], ecx
0x18002fdfb  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002fe00  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18002fe05  mov     r10, [rsp+720h+var_6D0]
0x18002fe0a  mov     r8d, [rsp+720h+var_6E4]
0x18002fe0f  sub     edi, 1
0x18002fe12  jz      loc_18002FEA5
0x18002fe18  sub     edi, 1
0x18002fe1b  jz      loc_18002FECA
0x18002fe21  cmp     edi, 1
0x18002fe24  jnz     short loc_18002FEA5
0x18002fe26  cmp     byte ptr [r14+0Bh], 0
0x18002fe2b  jz      loc_18002FED4
0x18002fe31  mov     al, [r14+8]
0x18002fe35  sub     al, 47h ; 'G'
0x18002fe37  test    al, 0DFh
  ... truncated ...
```

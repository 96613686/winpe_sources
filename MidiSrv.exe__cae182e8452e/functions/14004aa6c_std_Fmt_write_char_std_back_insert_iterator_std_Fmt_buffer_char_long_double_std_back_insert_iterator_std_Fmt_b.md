# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x14004aa6c`
- end: `0x14004b136`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@OAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, long double, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14004cc34`

## callees

- `0x1400054c0`
- `0x140048718`
- `0x140048844`
- `0x1400489f0`
- `0x14004aa6c`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x140051154`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004ad87`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004ad87`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x14004ab88`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x14004ab88`

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
0x14004aa6c  mov     rax, rsp
0x14004aa6f  mov     [rax+10h], rbx
0x14004aa73  push    rbp
0x14004aa74  push    rsi
0x14004aa75  push    rdi
0x14004aa76  push    r12
0x14004aa78  push    r13
0x14004aa7a  push    r14
0x14004aa7c  push    r15
0x14004aa7e  lea     rbp, [rax-628h]
0x14004aa85  sub     rsp, 6F0h
0x14004aa8c  movaps  xmmword ptr [rax-48h], xmm6
0x14004aa90  mov     rax, cs:__security_cookie
0x14004aa97  xor     rax, rsp
0x14004aa9a  mov     [rbp+620h+var_50], rax
0x14004aaa1  mov     r14, r9
0x14004aaa4  movaps  xmm6, xmm2
0x14004aaa7  mov     rbx, rdx
0x14004aaaa  mov     [rbp+620h+var_688], rcx
0x14004aaae  mov     al, [r9+0Ah]
0x14004aab2  mov     byte ptr [rsp+720h+var_6F0+1], al
0x14004aab6  mov     r9d, 2
0x14004aabc  test    al, al
0x14004aabe  jnz     short loc_14004AAC5
0x14004aac0  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x14004aac5  xor     sil, sil
0x14004aac8  mov     r13b, 65h ; 'e'
0x14004aacb  mov     edx, [r14+4]
0x14004aacf  xor     r15b, r15b
0x14004aad2  movsx   ecx, byte ptr [r14+8]
0x14004aad7  mov     edi, 4
0x14004aadc  lea     r8d, [rdi-3]
0x14004aae0  sub     ecx, 41h ; 'A'
0x14004aae3  jz      short loc_14004AB51
0x14004aae5  sub     ecx, edi
0x14004aae7  jz      short loc_14004AB3E
0x14004aae9  sub     ecx, r8d
0x14004aaec  jz      short loc_14004AB2B
0x14004aaee  sub     ecx, r8d
0x14004aaf1  jz      short loc_14004AB0F
0x14004aaf3  sub     ecx, 1Ah
0x14004aaf6  jz      short loc_14004AB54
0x14004aaf8  sub     ecx, edi
0x14004aafa  jz      short loc_14004AB41
0x14004aafc  sub     ecx, r8d
0x14004aaff  jz      short loc_14004AB2E
0x14004ab01  cmp     ecx, r8d
0x14004ab04  jz      short loc_14004AB12
0x14004ab06  lea     edi, [r8+2]
0x14004ab0a  mov     r15b, r8b
0x14004ab0d  jmp     short loc_14004AB57
0x14004ab0f  mov     sil, r8b
0x14004ab12  cmp     edx, 0FFFFFFFFh
0x14004ab15  jnz     short loc_14004AB1E
0x14004ab17  mov     edx, 6
0x14004ab1c  jmp     short loc_14004AB24
0x14004ab1e  test    edx, edx
0x14004ab20  cmovz   edx, r8d
0x14004ab24  mov     edi, 3
0x14004ab29  jmp     short loc_14004AB57
0x14004ab2b  mov     sil, r8b
0x14004ab2e  mov     eax, 6
0x14004ab33  cmp     edx, 0FFFFFFFFh
0x14004ab36  cmovz   edx, eax
0x14004ab39  mov     edi, r9d
0x14004ab3c  jmp     short loc_14004AB57
0x14004ab3e  mov     sil, r8b
0x14004ab41  mov     eax, 6
0x14004ab46  cmp     edx, 0FFFFFFFFh
0x14004ab49  cmovz   edx, eax
0x14004ab4c  mov     edi, r8d
0x14004ab4f  jmp     short loc_14004AB57
0x14004ab51  mov     sil, r8b
0x14004ab54  mov     r13b, 70h ; 'p'
0x14004ab57  xorps   xmm0, xmm0
0x14004ab5a  movups  [rsp+720h+var_6C8+8], xmm0
0x14004ab5f  mov     r12d, edx
0x14004ab62  mov     r8d, 432h
0x14004ab68  cmp     edx, r8d
0x14004ab6b  cmovg   r12d, r8d
0x14004ab6f  mov     [rbp+620h+var_6A0], r12d
0x14004ab73  lea     ecx, [rdx-432h]
0x14004ab79  xor     eax, eax
0x14004ab7b  cmp     edx, r8d
0x14004ab7e  cmovle  ecx, eax
0x14004ab81  mov     dword ptr [rsp+720h+var_6E0], ecx
0x14004ab85  movaps  xmm0, xmm6; X
0x14004ab88  call    cs:__imp__ldsign
0x14004ab8e  mov     edx, eax
0x14004ab90  test    eax, eax
0x14004ab92  setnz   byte ptr [rsp+720h+var_6F0+3]
0x14004ab97  ucomisd xmm6, xmm6
0x14004ab9b  setp    al
0x14004ab9e  cmp     al, 1
0x14004aba0  jnz     short loc_14004ABD7
0x14004aba2  lea     rax, [rbp+620h+var_5C0]
0x14004aba6  lea     rcx, [rbp+620h+var_5BF]
0x14004abaa  test    edx, edx
0x14004abac  cmovz   rcx, rax
0x14004abb0  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x14004abb5  mov     eax, dword ptr cs:aNan; "nan"
0x14004abbb  mov     [rcx], ax
0x14004abbe  mov     al, byte ptr cs:aNan+2; "n"
0x14004abc4  mov     [rcx+2], al
0x14004abc7  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x14004abcc  add     r9, 3
0x14004abd0  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x14004abd5  jmp     short loc_14004AC24
0x14004abd7  movaps  xmm3, xmm6
0x14004abda  lea     r8, [rbp+620h+var_57]
0x14004abe1  lea     rdx, [rbp+620h+var_5C0]
0x14004abe5  lea     rcx, [rsp+720h+var_6B8+8]
0x14004abea  cmp     r12d, 0FFFFFFFFh
0x14004abee  jnz     short loc_14004AC07
0x14004abf0  test    r15b, r15b
0x14004abf3  jz      short loc_14004ABFC
0x14004abf5  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x14004abfa  jmp     short loc_14004AC15
0x14004abfc  mov     [rsp+720h+var_700], edi
0x14004ac00  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x14004ac05  jmp     short loc_14004AC15
0x14004ac07  mov     dword ptr [rsp+720h+var_6F8], r12d
0x14004ac0c  mov     [rsp+720h+var_700], edi
0x14004ac10  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x14004ac15  movaps  xmm0, [rsp+720h+var_6B8+8]
0x14004ac1a  movaps  [rsp+720h+var_6C8+8], xmm0
0x14004ac1f  movq    r9, xmm0
0x14004ac24  lea     rdx, [rbp+620h+var_5C0]
0x14004ac28  mov     [rsp+720h+var_6D8], rdx
0x14004ac2d  mov     ecx, r9d
0x14004ac30  sub     ecx, edx
0x14004ac32  mov     [rsp+720h+var_6E8], ecx
0x14004ac36  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x14004ac3b  jz      short loc_14004AC48
0x14004ac3d  lea     rdx, [rbp+620h+var_5BF]
0x14004ac41  mov     [rsp+720h+var_6D8], rdx
0x14004ac46  jmp     short loc_14004AC55
0x14004ac48  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x14004ac4d  jz      short loc_14004AC55
0x14004ac4f  inc     ecx
0x14004ac51  mov     [rsp+720h+var_6E8], ecx
0x14004ac55  test    sil, sil
0x14004ac58  jz      short loc_14004AC87
0x14004ac5a  cmp     rdx, r9
0x14004ac5d  jz      short loc_14004AC83
0x14004ac5f  mov     cl, [rdx]
0x14004ac61  lea     eax, [rcx-61h]
0x14004ac64  cmp     al, 19h
0x14004ac66  ja      short loc_14004AC6D
0x14004ac68  sub     cl, 20h ; ' '
0x14004ac6b  mov     [rdx], cl
0x14004ac6d  inc     rdx
0x14004ac70  cmp     rdx, r9
0x14004ac73  jnz     short loc_14004AC5F
0x14004ac75  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x14004ac7a  mov     rdx, [rsp+720h+var_6D8]
0x14004ac7f  mov     ecx, [rsp+720h+var_6E8]
0x14004ac83  add     r13b, 0E0h
0x14004ac87  movq    rax, xmm6
0x14004ac8c  shr     rax, 34h
0x14004ac90  mov     r8d, 7FFh
0x14004ac96  and     eax, r8d
0x14004ac99  cmp     eax, r8d
0x14004ac9c  setnz   al
0x14004ac9f  xor     al, 1
0x14004aca1  mov     byte ptr [rsp+720h+var_6F0], al
0x14004aca5  mov     r15b, 0
0x14004aca8  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x14004acad  mov     r10, r9
0x14004acb0  mov     [rsp+720h+var_6D0], r9
0x14004acb5  mov     r11, r9
0x14004acb8  mov     [rbp+620h+var_690], r9
0x14004acbc  mov     [rbp+620h+var_698], r9
0x14004acc0  mov     r8d, 0
0x14004acc6  mov     [rsp+720h+var_6E4], r8d
0x14004accb  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x14004acd0  xorps   xmm0, xmm0
0x14004acd3  movups  [rbp+620h+var_600], xmm0
0x14004acd7  mov     [rbp+620h+var_5F0], r8
0x14004acdb  mov     [rbp+620h+var_5E8], 0Fh
0x14004ace3  mov     byte ptr [rbp+620h+var_600], r8b
0x14004ace7  jnz     loc_14004AF34
0x14004aced  mov     r12b, [r14+0Bh]
0x14004acf1  test    r12b, r12b
0x14004acf4  jnz     short loc_14004AD03
0x14004acf6  lea     rsi, [r14+0Ch]
0x14004acfa  cmp     [rsi], r12b
0x14004acfd  jz      loc_14004AE6B
0x14004ad03  mov     rax, rdx
0x14004ad06  cmp     rdx, r9
0x14004ad09  jnb     short loc_14004AD36
0x14004ad0b  cmp     byte ptr [rax], 2Eh ; '.'
0x14004ad0e  jnz     short loc_14004AD19
0x14004ad10  mov     r11, rax
0x14004ad13  mov     [rbp+620h+var_690], rax
0x14004ad17  jmp     short loc_14004AD26
0x14004ad19  cmp     [rax], r13b
0x14004ad1c  jnz     short loc_14004AD26
0x14004ad1e  mov     r10, rax
0x14004ad21  mov     [rsp+720h+var_6D0], rax
0x14004ad26  inc     rax
0x14004ad29  cmp     rax, r9
0x14004ad2c  jb      short loc_14004AD0B
0x14004ad2e  cmp     r10, r11
0x14004ad31  mov     rax, r10
0x14004ad34  jb      short loc_14004AD39
0x14004ad36  mov     rax, r11
0x14004ad39  mov     [rbp+620h+var_698], rax
0x14004ad3d  test    r12b, r12b
0x14004ad40  jz      short loc_14004AD55
0x14004ad42  cmp     r11, r9
0x14004ad45  jnz     short loc_14004AD55
0x14004ad47  inc     ecx
0x14004ad49  mov     [rsp+720h+var_6E8], ecx
0x14004ad4d  mov     r15b, 1
0x14004ad50  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x14004ad55  lea     rsi, [r14+0Ch]
0x14004ad59  cmp     byte ptr [rsi], 0
0x14004ad5c  jz      loc_14004AE6B
0x14004ad62  mov     rax, [rbp+620h+arg_20]
0x14004ad69  test    rax, rax
0x14004ad6c  jz      short loc_14004AD85
0x14004ad6e  mov     rcx, [rax+8]
0x14004ad72  mov     [rsp+720h+var_6A8], rcx
0x14004ad77  mov     rax, [rcx]
0x14004ad7a  mov     rax, [rax+8]
0x14004ad7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ad83  jmp     short loc_14004AD92
0x14004ad85  mov     cl, 1
0x14004ad87  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14004ad8d  mov     [rsp+720h+var_6A8], rax
0x14004ad92  lea     rcx, [rsp+720h+var_6B8+8]
0x14004ad97  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x14004ad9c  mov     rcx, rax
0x14004ad9f  mov     rax, [rax]
0x14004ada2  lea     rdx, [rbp+620h+var_5E0]
0x14004ada6  mov     rax, [rax+28h]
0x14004adaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004adaf  lea     rdx, [rbp+620h+var_5E0]
0x14004adb3  lea     rcx, [rbp+620h+var_600]
0x14004adb7  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004adbc  lea     rcx, [rbp+620h+var_5E0]
0x14004adc0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004adc5  nop
0x14004adc6  mov     rcx, [rsp+720h+var_6A8]
0x14004adcb  test    rcx, rcx
0x14004adce  jz      short loc_14004ADF4
0x14004add0  mov     rax, [rcx]
0x14004add3  mov     rax, [rax+10h]
0x14004add7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004addc  mov     rcx, rax
0x14004addf  test    rax, rax
0x14004ade2  jz      short loc_14004ADF4
0x14004ade4  mov     rax, [rax]
0x14004ade7  mov     edx, 1
0x14004adec  mov     rax, [rax]
0x14004adef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004adf4  lea     rax, [rbp+620h+var_600]
0x14004adf8  cmp     [rbp+620h+var_5E8], 0Fh
0x14004adfd  cmova   rax, qword ptr [rbp+620h+var_600]
0x14004ae02  mov     r10, [rbp+620h+var_5F0]
0x14004ae06  mov     rdx, [rsp+720h+var_6D8]
0x14004ae0b  xor     r8d, r8d
0x14004ae0e  test    r10, r10
0x14004ae11  jz      short loc_14004AE47
0x14004ae13  mov     r9, [rbp+620h+var_698]
0x14004ae17  sub     r9, rdx
0x14004ae1a  movsx   r11, byte ptr [rax]
0x14004ae1e  cmp     r9, r11
0x14004ae21  jbe     short loc_14004AE47
0x14004ae23  add     r10, rax
0x14004ae26  movsx   rcx, r11b
0x14004ae2a  sub     r9, rcx
0x14004ae2d  inc     r8d
0x14004ae30  lea     rcx, [rax+1]
0x14004ae34  cmp     rcx, r10
0x14004ae37  cmovz   rcx, rax
0x14004ae3b  mov     rax, rcx
0x14004ae3e  movsx   r11, byte ptr [rcx]
0x14004ae42  cmp     r9, r11
0x14004ae45  ja      short loc_14004AE26
0x14004ae47  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x14004ae4c  mov     ecx, [rsp+720h+var_6E8]
0x14004ae50  add     ecx, r8d
0x14004ae53  mov     [rsp+720h+var_6E8], ecx
0x14004ae57  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x14004ae5c  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x14004ae61  mov     r10, [rsp+720h+var_6D0]
0x14004ae66  mov     r8d, [rsp+720h+var_6E4]
0x14004ae6b  sub     edi, 1
0x14004ae6e  jz      loc_14004AF01
0x14004ae74  sub     edi, 1
0x14004ae77  jz      loc_14004AF26
0x14004ae7d  cmp     edi, 1
0x14004ae80  jnz     short loc_14004AF01
0x14004ae82  cmp     byte ptr [r14+0Bh], 0
0x14004ae87  jz      loc_14004AF30
0x14004ae8d  mov     al, [r14+8]
0x14004ae91  sub     al, 47h ; 'G'
0x14004ae93  test    al, 0DFh
  ... truncated ...
```

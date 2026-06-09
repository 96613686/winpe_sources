# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,float>(std::back_insert_iterator<std::_Fmt_buffer<char>>,float,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18002aebc`
- end: `0x18002b57e`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@MAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1730`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, double, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002daf4`

## callees

- `0x180002250`
- `0x180013830`
- `0x180020b94`
- `0x180023d0c`
- `0x180023e04`
- `0x180023f08`
- `0x18002aebc`
- `0x180030078`
- `0x180030f80`
- `0x1800ca010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b1d1`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b1d1`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18002afd9`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18002afd9`

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
0x18002aebc  mov     rax, rsp
0x18002aebf  mov     [rax+10h], rbx
0x18002aec3  push    rbp
0x18002aec4  push    rsi
0x18002aec5  push    rdi
0x18002aec6  push    r12
0x18002aec8  push    r13
0x18002aeca  push    r14
0x18002aecc  push    r15
0x18002aece  lea     rbp, [rax-628h]
0x18002aed5  sub     rsp, 6F0h
0x18002aedc  movaps  xmmword ptr [rax-48h], xmm6
0x18002aee0  mov     rax, cs:__security_cookie
0x18002aee7  xor     rax, rsp
0x18002aeea  mov     [rbp+620h+var_50], rax
0x18002aef1  mov     r14, r9
0x18002aef4  movaps  xmm6, xmm2
0x18002aef7  mov     rbx, rdx
0x18002aefa  mov     [rbp+620h+var_690], rcx
0x18002aefe  mov     al, [r9+0Ah]
0x18002af02  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18002af06  mov     r9d, 2
0x18002af0c  test    al, al
0x18002af0e  jnz     short loc_18002AF15
0x18002af10  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18002af15  xor     sil, sil
0x18002af18  mov     r13b, 65h ; 'e'
0x18002af1b  mov     edx, [r14+4]
0x18002af1f  xor     r15b, r15b
0x18002af22  movsx   ecx, byte ptr [r14+8]
0x18002af27  mov     edi, 4
0x18002af2c  lea     r8d, [rdi-3]
0x18002af30  sub     ecx, 41h ; 'A'
0x18002af33  jz      short loc_18002AFA1
0x18002af35  sub     ecx, edi
0x18002af37  jz      short loc_18002AF8E
0x18002af39  sub     ecx, r8d
0x18002af3c  jz      short loc_18002AF7B
0x18002af3e  sub     ecx, r8d
0x18002af41  jz      short loc_18002AF5F
0x18002af43  sub     ecx, 1Ah
0x18002af46  jz      short loc_18002AFA4
0x18002af48  sub     ecx, edi
0x18002af4a  jz      short loc_18002AF91
0x18002af4c  sub     ecx, r8d
0x18002af4f  jz      short loc_18002AF7E
0x18002af51  cmp     ecx, r8d
0x18002af54  jz      short loc_18002AF62
0x18002af56  lea     edi, [r8+2]
0x18002af5a  mov     r15b, r8b
0x18002af5d  jmp     short loc_18002AFA7
0x18002af5f  mov     sil, r8b
0x18002af62  cmp     edx, 0FFFFFFFFh
0x18002af65  jnz     short loc_18002AF6E
0x18002af67  mov     edx, 6
0x18002af6c  jmp     short loc_18002AF74
0x18002af6e  test    edx, edx
0x18002af70  cmovz   edx, r8d
0x18002af74  mov     edi, 3
0x18002af79  jmp     short loc_18002AFA7
0x18002af7b  mov     sil, r8b
0x18002af7e  mov     eax, 6
0x18002af83  cmp     edx, 0FFFFFFFFh
0x18002af86  cmovz   edx, eax
0x18002af89  mov     edi, r9d
0x18002af8c  jmp     short loc_18002AFA7
0x18002af8e  mov     sil, r8b
0x18002af91  mov     eax, 6
0x18002af96  cmp     edx, 0FFFFFFFFh
0x18002af99  cmovz   edx, eax
0x18002af9c  mov     edi, r8d
0x18002af9f  jmp     short loc_18002AFA7
0x18002afa1  mov     sil, r8b
0x18002afa4  mov     r13b, 70h ; 'p'
0x18002afa7  xorps   xmm0, xmm0
0x18002afaa  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18002afaf  mov     r12d, edx
0x18002afb2  mov     r8d, 432h
0x18002afb8  cmp     edx, r8d
0x18002afbb  cmovg   r12d, r8d
0x18002afbf  mov     dword ptr [rsp+720h+var_6B8], r12d
0x18002afc4  lea     ecx, [rdx-432h]
0x18002afca  xor     eax, eax
0x18002afcc  cmp     edx, r8d
0x18002afcf  cmovle  ecx, eax
0x18002afd2  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18002afd6  movaps  xmm0, xmm6
0x18002afd9  call    cs:__imp__o__fdsign
0x18002afdf  mov     edx, eax
0x18002afe1  test    eax, eax
0x18002afe3  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18002afe8  ucomiss xmm6, xmm6
0x18002afeb  setp    al
0x18002afee  cmp     al, 1
0x18002aff0  jnz     short loc_18002B027
0x18002aff2  lea     rax, [rbp+620h+var_5C0]
0x18002aff6  lea     rcx, [rbp+620h+var_5BF]
0x18002affa  test    edx, edx
0x18002affc  cmovz   rcx, rax
0x18002b000  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x18002b005  mov     eax, dword ptr cs:aNan; "nan"
0x18002b00b  mov     [rcx], ax
0x18002b00e  mov     al, byte ptr cs:aNan+2; "n"
0x18002b014  mov     [rcx+2], al
0x18002b017  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002b01c  add     r9, 3
0x18002b020  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x18002b025  jmp     short loc_18002B072
0x18002b027  movaps  xmm3, xmm6
0x18002b02a  lea     r8, [rbp+620h+var_57]
0x18002b031  lea     rdx, [rbp+620h+var_5C0]
0x18002b035  lea     rcx, [rsp+720h+var_6A8]
0x18002b03a  cmp     r12d, 0FFFFFFFFh
0x18002b03e  jnz     short loc_18002B057
0x18002b040  test    r15b, r15b
0x18002b043  jz      short loc_18002B04C
0x18002b045  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x18002b04a  jmp     short loc_18002B065
0x18002b04c  mov     [rsp+720h+var_700], edi
0x18002b050  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x18002b055  jmp     short loc_18002B065
0x18002b057  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18002b05c  mov     [rsp+720h+var_700], edi
0x18002b060  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x18002b065  movups  xmm0, xmmword ptr [rax]
0x18002b068  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18002b06d  movq    r9, xmm0
0x18002b072  lea     rdx, [rbp+620h+var_5C0]
0x18002b076  mov     [rsp+720h+var_6D8], rdx
0x18002b07b  mov     ecx, r9d
0x18002b07e  sub     ecx, edx
0x18002b080  mov     [rsp+720h+var_6E8], ecx
0x18002b084  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18002b089  jz      short loc_18002B096
0x18002b08b  lea     rdx, [rbp+620h+var_5BF]
0x18002b08f  mov     [rsp+720h+var_6D8], rdx
0x18002b094  jmp     short loc_18002B0A3
0x18002b096  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18002b09b  jz      short loc_18002B0A3
0x18002b09d  inc     ecx
0x18002b09f  mov     [rsp+720h+var_6E8], ecx
0x18002b0a3  test    sil, sil
0x18002b0a6  jz      short loc_18002B0D5
0x18002b0a8  cmp     rdx, r9
0x18002b0ab  jz      short loc_18002B0D1
0x18002b0ad  mov     cl, [rdx]
0x18002b0af  lea     eax, [rcx-61h]
0x18002b0b2  cmp     al, 19h
0x18002b0b4  ja      short loc_18002B0BB
0x18002b0b6  sub     cl, 20h ; ' '
0x18002b0b9  mov     [rdx], cl
0x18002b0bb  inc     rdx
0x18002b0be  cmp     rdx, r9
0x18002b0c1  jnz     short loc_18002B0AD
0x18002b0c3  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002b0c8  mov     rdx, [rsp+720h+var_6D8]
0x18002b0cd  mov     ecx, [rsp+720h+var_6E8]
0x18002b0d1  add     r13b, 0E0h
0x18002b0d5  movd    eax, xmm6
0x18002b0d9  mov     r8d, 7F800000h
0x18002b0df  and     eax, r8d
0x18002b0e2  cmp     eax, r8d
0x18002b0e5  setnz   al
0x18002b0e8  xor     al, 1
0x18002b0ea  mov     byte ptr [rsp+720h+var_6F0], al
0x18002b0ee  mov     r15b, 0
0x18002b0f1  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002b0f6  mov     r10, r9
0x18002b0f9  mov     qword ptr [rsp+720h+var_6D0], r9
0x18002b0fe  mov     r11, r9
0x18002b101  mov     [rbp+620h+var_698], r9
0x18002b105  mov     [rsp+720h+var_6B0], r9
0x18002b10a  mov     r8d, 0
0x18002b110  mov     [rsp+720h+var_6E4], r8d
0x18002b115  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002b11a  xorps   xmm0, xmm0
0x18002b11d  movups  [rbp+620h+var_600], xmm0
0x18002b121  mov     [rbp+620h+var_5F0], r8
0x18002b125  mov     [rbp+620h+var_5E8], 0Fh
0x18002b12d  mov     byte ptr [rbp+620h+var_600], r8b
0x18002b131  jnz     loc_18002B37C
0x18002b137  mov     r12b, [r14+0Bh]
0x18002b13b  test    r12b, r12b
0x18002b13e  jnz     short loc_18002B14D
0x18002b140  lea     rsi, [r14+0Ch]
0x18002b144  cmp     [rsi], r12b
0x18002b147  jz      loc_18002B2B4
0x18002b14d  mov     rax, rdx
0x18002b150  cmp     rdx, r9
0x18002b153  jnb     short loc_18002B180
0x18002b155  cmp     byte ptr [rax], 2Eh ; '.'
0x18002b158  jnz     short loc_18002B163
0x18002b15a  mov     r11, rax
0x18002b15d  mov     [rbp+620h+var_698], rax
0x18002b161  jmp     short loc_18002B170
0x18002b163  cmp     [rax], r13b
0x18002b166  jnz     short loc_18002B170
0x18002b168  mov     r10, rax
0x18002b16b  mov     qword ptr [rsp+720h+var_6D0], rax
0x18002b170  inc     rax
0x18002b173  cmp     rax, r9
0x18002b176  jb      short loc_18002B155
0x18002b178  cmp     r10, r11
0x18002b17b  mov     rax, r10
0x18002b17e  jb      short loc_18002B183
0x18002b180  mov     rax, r11
0x18002b183  mov     [rsp+720h+var_6B0], rax
0x18002b188  test    r12b, r12b
0x18002b18b  jz      short loc_18002B1A0
0x18002b18d  cmp     r11, r9
0x18002b190  jnz     short loc_18002B1A0
0x18002b192  inc     ecx
0x18002b194  mov     [rsp+720h+var_6E8], ecx
0x18002b198  mov     r15b, 1
0x18002b19b  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002b1a0  lea     rsi, [r14+0Ch]
0x18002b1a4  cmp     byte ptr [rsi], 0
0x18002b1a7  jz      loc_18002B2B4
0x18002b1ad  mov     rax, [rbp+620h+arg_20]
0x18002b1b4  test    rax, rax
0x18002b1b7  jz      short loc_18002B1CF
0x18002b1b9  mov     rcx, [rax+8]
0x18002b1bd  mov     [rbp+620h+var_6A0], rcx
0x18002b1c1  mov     rax, [rcx]
0x18002b1c4  mov     rax, [rax+8]
0x18002b1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1cd  jmp     short loc_18002B1DB
0x18002b1cf  mov     cl, 1
0x18002b1d1  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002b1d7  mov     [rbp+620h+var_6A0], rax
0x18002b1db  lea     rcx, [rsp+720h+var_6A8]
0x18002b1e0  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002b1e5  mov     rcx, rax
0x18002b1e8  mov     rax, [rax]
0x18002b1eb  lea     rdx, [rbp+620h+var_5E0]
0x18002b1ef  mov     rax, [rax+28h]
0x18002b1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1f8  lea     rdx, [rbp+620h+var_5E0]
0x18002b1fc  lea     rcx, [rbp+620h+var_600]
0x18002b200  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002b205  lea     rcx, [rbp+620h+var_5E0]
0x18002b209  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b20e  nop
0x18002b20f  mov     rcx, [rbp+620h+var_6A0]
0x18002b213  test    rcx, rcx
0x18002b216  jz      short loc_18002B23C
0x18002b218  mov     rax, [rcx]
0x18002b21b  mov     rax, [rax+10h]
0x18002b21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b224  mov     rcx, rax
0x18002b227  test    rax, rax
0x18002b22a  jz      short loc_18002B23C
0x18002b22c  mov     rax, [rax]
0x18002b22f  mov     edx, 1
0x18002b234  mov     rax, [rax]
0x18002b237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b23c  lea     rax, [rbp+620h+var_600]
0x18002b240  cmp     [rbp+620h+var_5E8], 0Fh
0x18002b245  cmova   rax, qword ptr [rbp+620h+var_600]
0x18002b24a  mov     r10, [rbp+620h+var_5F0]
0x18002b24e  mov     rdx, [rsp+720h+var_6D8]
0x18002b253  xor     r8d, r8d
0x18002b256  test    r10, r10
0x18002b259  jz      short loc_18002B290
0x18002b25b  mov     r9, [rsp+720h+var_6B0]
0x18002b260  sub     r9, rdx
0x18002b263  movsx   r11, byte ptr [rax]
0x18002b267  cmp     r9, r11
0x18002b26a  jbe     short loc_18002B290
0x18002b26c  add     r10, rax
0x18002b26f  movsx   rcx, r11b
0x18002b273  sub     r9, rcx
0x18002b276  inc     r8d
0x18002b279  lea     rcx, [rax+1]
0x18002b27d  cmp     rcx, r10
0x18002b280  cmovz   rcx, rax
0x18002b284  mov     rax, rcx
0x18002b287  movsx   r11, byte ptr [rcx]
0x18002b28b  cmp     r9, r11
0x18002b28e  ja      short loc_18002B26F
0x18002b290  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002b295  mov     ecx, [rsp+720h+var_6E8]
0x18002b299  add     ecx, r8d
0x18002b29c  mov     [rsp+720h+var_6E8], ecx
0x18002b2a0  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002b2a5  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18002b2aa  mov     r10, qword ptr [rsp+720h+var_6D0]
0x18002b2af  mov     r8d, [rsp+720h+var_6E4]
0x18002b2b4  sub     edi, 1
0x18002b2b7  jz      loc_18002B349
0x18002b2bd  sub     edi, 1
0x18002b2c0  jz      loc_18002B36E
0x18002b2c6  cmp     edi, 1
0x18002b2c9  jnz     short loc_18002B349
0x18002b2cb  cmp     byte ptr [r14+0Bh], 0
0x18002b2d0  jz      loc_18002B378
0x18002b2d6  mov     al, [r14+8]
0x18002b2da  sub     al, 47h ; 'G'
0x18002b2dc  test    al, 0DFh
0x18002b2de  jnz     loc_18002B378
  ... truncated ...
```

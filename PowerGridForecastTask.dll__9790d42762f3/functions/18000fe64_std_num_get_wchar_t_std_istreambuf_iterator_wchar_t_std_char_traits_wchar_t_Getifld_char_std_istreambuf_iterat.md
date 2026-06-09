# std::num_get<wchar_t,std::istreambuf_iterator<wchar_t,std::char_traits<wchar_t>>>::_Getifld(char *,std::istreambuf_iterator<wchar_t,std::char_traits<wchar_t>> &,std::istreambuf_iterator<wchar_t,std::char_traits<wchar_t>> &,int,std::locale const &)

- ea: `0x18000fe64`
- end: `0x18001029a`
- name: `?_Getifld@?$num_get@_WV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@2@1HAEBVlocale@2@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(__int64, char *, __int64 *, __int64, __int16, __int64 *)`
- caller_count: `8`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180017580`
- `0x1800176d0`
- `0x180017820`
- `0x180017950`
- `0x180017d80`
- `0x180017eb0`
- `0x180017fe0`
- `0x180018110`

## callees

- `0x180009c10`
- `0x18000b050`
- `0x18000b754`
- `0x18000fe64`
- `0x180011cac`
- `0x18001c5d8`
- `0x180026609`
- `0x180034120`
- `0x1800350e0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall std::num_get<wchar_t,std::istreambuf_iterator<wchar_t>>::_Getifld(
        __int64 a1,
        char *a2,
        __int64 *a3,
        __int64 a4,
        __int16 a5,
        __int64 *a6)
{
  char *v8; // r13
  struct std::_Facet_base *v9; // rdi
  unsigned __int8 v10; // di
  struct std::_Facet_base *v11; // rax
  char *v12; // r14
  _WORD *v13; // rax
  __int64 *v14; // rcx
  _WORD *v15; // rax
  int v16; // ecx
  unsigned int v17; // esi
  _WORD *v18; // rax
  _WORD *v19; // rax
  _WORD *v20; // rax
  __int64 v21; // r15
  unsigned __int64 v22; // r12
  __int64 v23; // rdi
  void **v24; // r15
  __int16 v25; // cx
  char *v26; // rax
  unsigned __int64 v27; // rax
  char v28; // cl
  void **v29; // rax
  void **v30; // rax
  void **v31; // rax
  void **v32; // rax
  char v33; // al
  void **v34; // rcx
  void *v35; // rdx
  unsigned __int64 v36; // r8
  char v37; // r9
  void **v38; // rax
  void **v40; // rax
  char v41; // [rsp+38h] [rbp-A9h]
  char v42; // [rsp+39h] [rbp-A8h]
  int v43; // [rsp+3Ch] [rbp-A5h]
  __int16 v44; // [rsp+40h] [rbp-A1h]
  unsigned __int64 v45; // [rsp+48h] [rbp-99h]
  __int64 v48; // [rsp+68h] [rbp-79h]
  void *v49[3]; // [rsp+70h] [rbp-71h] BYREF
  __int64 v50; // [rsp+88h] [rbp-59h]
  void *v51[3]; // [rsp+90h] [rbp-51h] BYREF
  unsigned __int64 v52; // [rsp+A8h] [rbp-39h]
  _WORD v53[26]; // [rsp+B0h] [rbp-31h] BYREF
  char v54; // [rsp+E4h] [rbp+3h] BYREF

  HIBYTE(v48) = -1;
  v8 = a2;
  v9 = std::use_facet<std::numpunct<wchar_t>>(a6);
  (*(void (__fastcall **)(struct std::_Facet_base *, void **))(*(_QWORD *)v9 + 40LL))(v9, v51);
  if ( v51[2] )
  {
    v44 = (*(__int64 (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v9 + 32LL))(v9);
    v10 = 0;
  }
  else
  {
    v10 = 0;
    v44 = 0;
  }
  v11 = std::use_facet<std::ctype<wchar_t>>(a6);
  (*(void (__fastcall **)(struct std::_Facet_base *, const char *, char *, _WORD *))(*(_QWORD *)v11 + 88LL))(
    v11,
    "0123456789ABCDEFabcdef-+Xx",
    "",
    v53);
  v12 = v8;
  if ( !(unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
  {
    v13 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
    v14 = a3;
    if ( *v13 == v53[23] )
    {
      *v8 = 43;
    }
    else
    {
      v15 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
      if ( *v15 != v53[22] )
        goto LABEL_10;
      *v8 = 45;
      v14 = a3;
    }
    v12 = v8 + 1;
    std::istreambuf_iterator<unsigned short>::_Inc(v14);
  }
LABEL_10:
  v16 = a5 & 0xE00;
  v45 = 10;
  v17 = v16 != 0 ? 0xA : 0;
  if ( v16 == 2048 )
    v17 = 16;
  if ( v16 == 1024 )
    v17 = 8;
  v43 = v17;
  v41 = 0;
  v42 = 0;
  if ( (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4)
    || (v18 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3), *v18 != v53[0]) )
  {
    if ( !v17 )
      goto LABEL_29;
  }
  else
  {
    std::istreambuf_iterator<unsigned short>::_Inc(a3);
    if ( !(unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
    {
      v19 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
      if ( *v19 == v53[25] || (v20 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3), *v20 == v53[24]) )
      {
        if ( (v17 & 0xFFFFFFEF) == 0 )
        {
          v17 = 16;
          v43 = 16;
          v41 = 0;
          std::istreambuf_iterator<unsigned short>::_Inc(a3);
          goto LABEL_26;
        }
      }
    }
    v10 = 1;
    v41 = 1;
    if ( !v17 )
    {
      v17 = 8;
      v43 = 8;
      goto LABEL_26;
    }
  }
  if ( v17 == 10 )
    goto LABEL_29;
  v43 = v17;
LABEL_26:
  v21 = 22;
  if ( v17 == 8 )
    v21 = 8;
  v45 = v21;
LABEL_29:
  v22 = 15;
  v50 = 15;
  LOWORD(v49[0]) = v10;
  v49[2] = (void *)1;
  v23 = 0;
  v24 = (void **)v49[0];
  if ( (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
    goto LABEL_58;
  while ( 1 )
  {
    v25 = *(_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
    v26 = (char *)v53;
    do
    {
      if ( *(_WORD *)v26 == v25 )
        break;
      v26 += 2;
    }
    while ( v26 != &v54 );
    v27 = (v26 - (char *)v53) >> 1;
    if ( v27 >= v45 )
      break;
    v28 = `std::num_get<wchar_t,std::istreambuf_iterator<wchar_t>>::_Getifld'::`2'::_Src[v27];
    *v12 = v28;
    if ( (v42 || v28 != 48) && v12 < v8 + 31 )
    {
      ++v12;
      v42 = 1;
    }
    v41 = 1;
    v29 = v49;
    if ( v22 >= 0x10 )
      v29 = v24;
    if ( *((_BYTE *)v29 + v23) == 127 )
      goto LABEL_51;
    v30 = v49;
    if ( v22 >= 0x10 )
      v30 = v24;
    ++*((_BYTE *)v30 + v23);
LABEL_50:
    v24 = (void **)v49[0];
    v22 = v50;
LABEL_51:
    std::istreambuf_iterator<unsigned short>::_Inc(a3);
    if ( (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
      goto LABEL_52;
  }
  v31 = v49;
  if ( v22 >= 0x10 )
    v31 = v24;
  if ( *((_BYTE *)v31 + v23) && v44 && *(_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3) == v44 )
  {
    std::string::append(v49, 1);
    ++v23;
    goto LABEL_50;
  }
LABEL_52:
  v17 = v43;
  v8 = a2;
  if ( !v23 )
    goto LABEL_58;
  v32 = v49;
  if ( v22 >= 0x10 )
    v32 = v24;
  if ( *((char *)v32 + v23) <= 0 )
  {
    v33 = 0;
  }
  else
  {
    ++v23;
LABEL_58:
    v33 = v41;
  }
  v34 = v51;
  v35 = v51[0];
  v36 = v52;
  if ( v52 >= 0x10 )
    v34 = (void **)v51[0];
  if ( v33 )
  {
    while ( v23 )
    {
      v37 = *(_BYTE *)v34;
      if ( *(_BYTE *)v34 == 127 )
        break;
      if ( --v23 )
      {
        v38 = v49;
        if ( v22 >= 0x10 )
          v38 = v24;
        if ( v37 != *((_BYTE *)v38 + v23) )
          goto LABEL_68;
      }
      else
      {
        v40 = v49;
        if ( v22 >= 0x10 )
          v40 = v24;
        if ( v37 < *(char *)v40 )
          goto LABEL_68;
      }
      if ( *((char *)v34 + 1) > 0 )
        v34 = (void **)((char *)v34 + 1);
    }
    if ( !v42 )
      *v12++ = 48;
  }
  else
  {
LABEL_68:
    v12 = v8;
  }
  *v12 = 0;
  if ( v22 >= 0x10 )
  {
    operator delete(v24);
    v36 = v52;
    v35 = v51[0];
  }
  if ( v36 >= 0x10 )
    operator delete(v35);
  return v17;
}

```

## disassembly

```asm
0x18000fe64  mov     rax, rsp
0x18000fe67  push    rbp
0x18000fe68  push    rsi
0x18000fe69  push    rdi
0x18000fe6a  push    r12
0x18000fe6c  push    r13
0x18000fe6e  push    r14
0x18000fe70  push    r15
0x18000fe72  lea     rbp, [rax-4Fh]
0x18000fe76  sub     rsp, 0F0h
0x18000fe7d  mov     [rbp+47h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18000fe85  mov     [rax+8], rbx
0x18000fe89  mov     rax, cs:__security_cookie
0x18000fe90  xor     rax, rsp
0x18000fe93  mov     [rbp+47h+var_40], rax
0x18000fe97  mov     r12, r9
0x18000fe9a  mov     [rsp+120h+var_D8], r9
0x18000fe9f  mov     rbx, r8
0x18000fea2  mov     r13, rdx
0x18000fea5  mov     [rsp+58h], rdx
0x18000feaa  mov     rsi, [rbp+47h+arg_28]
0x18000feae  xor     r14d, r14d
0x18000feb1  mov     rcx, rsi
0x18000feb4  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z
0x18000feb9  mov     rdi, rax
0x18000febc  mov     rcx, [rax]
0x18000febf  mov     rax, [rcx+28h]
0x18000fec3  lea     rdx, [rbp+47h+var_98]
0x18000fec7  mov     rcx, rdi
0x18000feca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fecf  nop
0x18000fed0  cmp     [rbp+47h+var_88], r14
0x18000fed4  jnz     short loc_18000FEDE
0x18000fed6  xor     edi, edi
0x18000fed8  mov     dword ptr [rsp+120h+var_E8], edi
0x18000fedc  jmp     short loc_18000FEF4
0x18000fede  mov     rax, [rdi]
0x18000fee1  mov     rcx, rdi
0x18000fee4  mov     rax, [rax+20h]
0x18000fee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feed  mov     word ptr [rsp+120h+var_E8], ax
0x18000fef2  xor     edi, edi
0x18000fef4  mov     rcx, rsi
0x18000fef7  call    ??$use_facet@V?$ctype@_W@std@@@std@@YAAEBV?$ctype@_W@0@AEBVlocale@0@@Z
0x18000fefc  mov     r10, rax
0x18000feff  mov     rcx, [rax]
0x18000ff02  mov     rax, [rcx+58h]
0x18000ff06  lea     r9, [rbp+47h+var_78]
0x18000ff0a  lea     r8, ?_Src@?1??_Getifld@?$num_get@_WV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@3@1HAEBVlocale@3@@Z@4QBDB+1Ah
0x18000ff11  lea     rdx, ?_Src@?1??_Getifld@?$num_get@_WV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@3@1HAEBVlocale@3@@Z@4QBDB
0x18000ff18  mov     rcx, r10
0x18000ff1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff20  mov     r14, r13
0x18000ff23  mov     rdx, r12
0x18000ff26  mov     rcx, rbx
0x18000ff29  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000ff2e  test    al, al
0x18000ff30  jnz     short loc_18000FF6C
0x18000ff32  mov     rcx, rbx
0x18000ff35  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000ff3a  movzx   ecx, [rbp+47h+var_4A]
0x18000ff3e  cmp     [rax], cx
0x18000ff41  mov     rcx, rbx
0x18000ff44  jnz     short loc_18000FF4D
0x18000ff46  mov     byte ptr [r13+0], 2Bh ; '+'
0x18000ff4b  jmp     short loc_18000FF63
0x18000ff4d  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000ff52  movzx   ecx, [rbp+47h+var_4C]
0x18000ff56  cmp     [rax], cx
0x18000ff59  jnz     short loc_18000FF6C
0x18000ff5b  mov     byte ptr [r13+0], 2Dh ; '-'
0x18000ff60  mov     rcx, rbx
0x18000ff63  lea     r14, [r13+1]
0x18000ff67  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18000ff6c  mov     ecx, dword ptr [rbp+47h+arg_20]
0x18000ff6f  and     ecx, 0E00h
0x18000ff75  mov     eax, ecx
0x18000ff77  neg     eax
0x18000ff79  sbb     esi, esi
0x18000ff7b  mov     r15d, 0Ah
0x18000ff81  mov     [rsp+120h+var_E0], r15
0x18000ff86  and     esi, r15d
0x18000ff89  lea     eax, [r15+6]
0x18000ff8d  cmp     ecx, 800h
0x18000ff93  cmovz   esi, eax
0x18000ff96  lea     eax, [r15-2]
0x18000ff9a  cmp     ecx, 400h
0x18000ffa0  cmovz   esi, eax
0x18000ffa3  mov     [rsp+34h], esi
0x18000ffa7  mov     byte ptr [rsp+120h+var_F0], dil
0x18000ffac  mov     byte ptr [rsp+120h+var_F0+1], dil
0x18000ffb1  mov     rdx, r12
0x18000ffb4  mov     rcx, rbx
0x18000ffb7  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000ffbc  test    al, al
0x18000ffbe  jnz     loc_180010045
0x18000ffc4  mov     rcx, rbx
0x18000ffc7  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000ffcc  movzx   ecx, [rbp+47h+var_78]
0x18000ffd0  cmp     [rax], cx
0x18000ffd3  jnz     short loc_180010045
0x18000ffd5  mov     rcx, rbx
0x18000ffd8  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18000ffdd  mov     rdx, r12
0x18000ffe0  mov     rcx, rbx
0x18000ffe3  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000ffe8  test    al, al
0x18000ffea  jnz     short loc_18001002E
0x18000ffec  mov     rcx, rbx
0x18000ffef  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fff4  movzx   ecx, [rbp+47h+var_46]
0x18000fff8  cmp     [rax], cx
0x18000fffb  jz      short loc_18001000E
0x18000fffd  mov     rcx, rbx
0x180010000  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x180010005  movzx   ecx, [rbp+47h+var_48]
0x180010009  cmp     [rax], cx
0x18001000c  jnz     short loc_18001002E
0x18001000e  test    esi, 0FFFFFFEFh
0x180010014  jnz     short loc_18001002E
0x180010016  mov     esi, 10h
0x18001001b  mov     [rsp+34h], esi
0x18001001f  mov     byte ptr [rsp+120h+var_F0], dil
0x180010024  mov     rcx, rbx
0x180010027  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18001002c  jmp     short loc_180010052
0x18001002e  mov     dil, 1
0x180010031  mov     byte ptr [rsp+120h+var_F0], dil
0x180010036  test    esi, esi
0x180010038  jnz     short loc_180010049
0x18001003a  lea     eax, [rsi+8]
0x18001003d  mov     esi, eax
0x18001003f  mov     [rsp+34h], eax
0x180010043  jmp     short loc_180010057
0x180010045  test    esi, esi
0x180010047  jz      short loc_180010068
0x180010049  cmp     esi, r15d
0x18001004c  jz      short loc_180010068
0x18001004e  mov     [rsp+34h], esi
0x180010052  mov     eax, 8
0x180010057  mov     r15d, 16h
0x18001005d  cmp     esi, eax
0x18001005f  cmovz   r15, rax
0x180010063  mov     [rsp+120h+var_E0], r15
0x180010068  mov     r12d, 0Fh
0x18001006e  mov     [rbp+47h+var_A0], r12
0x180010072  mov     byte ptr [rbp+47h+var_B8], dil
0x180010076  mov     [rbp+47h+var_A8], 1
0x18001007e  xor     r15d, r15d
0x180010081  mov     byte ptr [rbp+47h+var_B8+1], r15b
0x180010085  mov     edi, r15d
0x180010088  lea     rax, [r13+1Fh]
0x18001008c  mov     [rsp+120h+var_D0], rax
0x180010091  mov     rdx, [rsp+120h+var_D8]
0x180010096  mov     rcx, rbx
0x180010099  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18001009e  mov     r15, [rbp+47h+var_B8]
0x1800100a2  test    al, al
0x1800100a4  jnz     loc_1800101BA
0x1800100aa  mov     r13, [rsp+120h+var_E0]
0x1800100af  mov     esi, dword ptr [rsp+120h+var_E8]
0x1800100b3  mov     rcx, rbx
0x1800100b6  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x1800100bb  movzx   ecx, word ptr [rax]
0x1800100be  lea     rax, [rbp+47h+var_78]
0x1800100c2  cmp     [rax], cx
0x1800100c5  jz      short loc_1800100D4
0x1800100c7  add     rax, 2
0x1800100cb  lea     rdx, [rbp+47h+var_44]
0x1800100cf  cmp     rax, rdx
0x1800100d2  jnz     short loc_1800100C2
0x1800100d4  lea     rcx, [rbp+47h+var_78]
0x1800100d8  sub     rax, rcx
0x1800100db  sar     rax, 1
0x1800100de  cmp     rax, r13
0x1800100e1  jnb     short loc_180010133
0x1800100e3  lea     rcx, ?_Src@?1??_Getifld@?$num_get@_WV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@_WU?$char_traits@_W@std@@@3@1HAEBVlocale@3@@Z@4QBDB
0x1800100ea  mov     cl, [rax+rcx]
0x1800100ed  mov     [r14], cl
0x1800100f0  cmp     byte ptr [rsp+120h+var_F0+1], 0
0x1800100f5  jnz     short loc_1800100FC
0x1800100f7  cmp     cl, 30h ; '0'
0x1800100fa  jz      short loc_18001010B
0x1800100fc  cmp     r14, [rsp+120h+var_D0]
0x180010101  jnb     short loc_18001010B
0x180010103  inc     r14
0x180010106  mov     byte ptr [rsp+120h+var_F0+1], 1
0x18001010b  mov     byte ptr [rsp+120h+var_F0], 1
0x180010110  lea     rax, [rbp+47h+var_B8]
0x180010114  cmp     r12, 10h
0x180010118  cmovnb  rax, r15
0x18001011c  cmp     byte ptr [rax+rdi], 7Fh
0x180010120  jz      short loc_180010173
0x180010122  lea     rax, [rbp+47h+var_B8]
0x180010126  cmp     r12, 10h
0x18001012a  cmovnb  rax, r15
0x18001012e  inc     byte ptr [rax+rdi]
0x180010131  jmp     short loc_18001016B
0x180010133  lea     rax, [rbp+47h+var_B8]
0x180010137  cmp     r12, 10h
0x18001013b  cmovnb  rax, r15
0x18001013f  xor     ecx, ecx
0x180010141  cmp     [rax+rdi], cl
0x180010144  jz      short loc_180010190
0x180010146  test    si, si
0x180010149  jz      short loc_180010190
0x18001014b  mov     rcx, rbx
0x18001014e  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x180010153  cmp     [rax], si
0x180010156  jnz     short loc_180010190
0x180010158  xor     r8d, r8d
0x18001015b  lea     edx, [r8+1]
0x18001015f  lea     rcx, [rbp+47h+var_B8]
0x180010163  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z
0x180010168  inc     rdi
0x18001016b  mov     r15, [rbp+47h+var_B8]
0x18001016f  mov     r12, [rbp+47h+var_A0]
0x180010173  mov     rcx, rbx
0x180010176  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18001017b  mov     rdx, [rsp+120h+var_D8]
0x180010180  mov     rcx, rbx
0x180010183  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x180010188  test    al, al
0x18001018a  jz      loc_1800100B3
0x180010190  xor     ebx, ebx
0x180010192  test    rdi, rdi
0x180010195  mov     esi, [rsp+34h]
0x180010199  mov     r13, [rsp+58h]
0x18001019e  jz      short loc_1800101BC
0x1800101a0  lea     rax, [rbp+47h+var_B8]
0x1800101a4  cmp     r12, 10h
0x1800101a8  cmovnb  rax, r15
0x1800101ac  cmp     [rax+rdi], bl
0x1800101af  jle     short loc_1800101B6
0x1800101b1  inc     rdi
0x1800101b4  jmp     short loc_1800101BC
0x1800101b6  mov     al, bl
0x1800101b8  jmp     short loc_1800101C0
0x1800101ba  xor     ebx, ebx
0x1800101bc  mov     al, byte ptr [rsp+120h+var_F0]
0x1800101c0  lea     rcx, [rbp+47h+var_98]
0x1800101c4  mov     rdx, [rbp+47h+var_98]
0x1800101c8  mov     r8, [rbp+47h+var_80]
0x1800101cc  mov     r10d, 10h
0x1800101d2  cmp     r8, r10
0x1800101d5  cmovnb  rcx, rdx
0x1800101d9  test    al, al
0x1800101db  jz      short loc_18001020A
0x1800101dd  test    rdi, rdi
0x1800101e0  jz      loc_180010287
0x1800101e6  mov     r9b, [rcx]
0x1800101e9  cmp     r9b, 7Fh
0x1800101ed  jz      loc_180010287
0x1800101f3  sub     rdi, 1
0x1800101f7  jz      short loc_180010261
0x1800101f9  lea     rax, [rbp+47h+var_B8]
0x1800101fd  cmp     r12, r10
0x180010200  cmovnb  rax, r15
0x180010204  cmp     r9b, [rax+rdi]
0x180010208  jz      short loc_180010276
0x18001020a  mov     r14, r13
0x18001020d  mov     [r14], bl
0x180010210  cmp     r12, r10
0x180010213  jb      short loc_18001022B
0x180010215  mov     rcx, r15; void *
0x180010218  call    ??3@YAXPEAX@Z_0
0x18001021d  mov     r8, [rbp+47h+var_80]
0x180010221  mov     rdx, [rbp+47h+var_98]
0x180010225  mov     r10d, 10h
0x18001022b  cmp     r8, r10
0x18001022e  jb      short loc_180010238
0x180010230  mov     rcx, rdx; void *
0x180010233  call    ??3@YAXPEAX@Z_0
0x180010238  mov     eax, esi
0x18001023a  mov     rcx, [rbp+47h+var_40]
0x18001023e  xor     rcx, rsp; StackCookie
0x180010241  call    __security_check_cookie
0x180010246  mov     rbx, [rsp+120h+arg_0]
0x18001024e  add     rsp, 0F0h
0x180010255  pop     r15
0x180010257  pop     r14
0x180010259  pop     r13
0x18001025b  pop     r12
0x18001025d  pop     rdi
0x18001025e  pop     rsi
0x18001025f  pop     rbp
0x180010260  retn
0x180010261  test    rdi, rdi
0x180010264  jnz     short loc_180010276
0x180010266  lea     rax, [rbp+47h+var_B8]
0x18001026a  cmp     r12, r10
0x18001026d  cmovnb  rax, r15
0x180010271  cmp     r9b, [rax]
0x180010274  jl      short loc_18001020A
0x180010276  cmp     [rcx+1], bl
0x180010279  jle     loc_1800101DD
0x18001027f  inc     rcx
0x180010282  jmp     loc_1800101DD
0x180010287  cmp     byte ptr [rsp+120h+var_F0+1], bl
0x18001028b  jnz     short loc_18001020D
  ... truncated ...
```

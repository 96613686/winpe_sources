# std::num_get<char,std::istreambuf_iterator<char,std::char_traits<char>>>::_Getifld(char *,std::istreambuf_iterator<char,std::char_traits<char>> &,std::istreambuf_iterator<char,std::char_traits<char>> &,int,std::locale const &)

- ea: `0x1800053b4`
- end: `0x18000599d`
- name: `?_Getifld@?$num_get@DV?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@DU?$char_traits@D@std@@@2@1HAEBVlocale@2@@Z`
- size: `1513`
- prototype: `__int64 __fastcall(__int64, char *, __int64, __int64, __int16, __int64 *)`
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180006920`
- `0x180006a70`
- `0x180006bc0`
- `0x180006cf0`
- `0x180007120`
- `0x180007250`
- `0x180007380`
- `0x1800074b0`

## callees

- `0x180002d80`
- `0x18000314c`
- `0x180003290`
- `0x1800053b4`
- `0x180008284`
- `0x180026609`
- `0x180034120`
- `0x1800350e0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall std::num_get<char,std::istreambuf_iterator<char>>::_Getifld(
        __int64 a1,
        char *a2,
        __int64 a3,
        __int64 a4,
        __int16 a5,
        __int64 *a6)
{
  struct std::_Facet_base *v8; // rdi
  struct std::_Facet_base *v9; // rax
  char *v10; // r13
  __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v13; // eax
  int v14; // ecx
  unsigned int v15; // r12d
  unsigned __int8 v16; // r15
  __int64 v17; // rcx
  unsigned __int8 *v18; // rdx
  int v19; // eax
  __int64 v20; // rcx
  unsigned __int8 *v21; // rdx
  int v22; // eax
  char v23; // al
  __int64 v24; // rsi
  unsigned __int64 v25; // r14
  __int64 v26; // rdi
  void **v27; // rsi
  __int64 v28; // rcx
  unsigned __int8 *v29; // rdx
  int v30; // eax
  char *v31; // rax
  unsigned __int64 v32; // rax
  char v33; // cl
  void **v34; // rax
  void **v35; // rax
  void **v36; // rax
  char v37; // r8
  __int64 v38; // rcx
  unsigned __int8 *v39; // rdx
  int v40; // eax
  void **v41; // rax
  void **v42; // rcx
  void *v43; // rdx
  unsigned __int64 v44; // r8
  char v45; // r9
  void **v46; // rax
  void **v47; // rax
  char v49; // [rsp+38h] [rbp-89h]
  char v50; // [rsp+39h] [rbp-88h]
  int v51; // [rsp+3Ch] [rbp-85h]
  unsigned __int64 v53; // [rsp+48h] [rbp-79h]
  __int64 v55; // [rsp+60h] [rbp-61h]
  void *v56[3]; // [rsp+68h] [rbp-59h] BYREF
  __int64 v57; // [rsp+80h] [rbp-41h]
  void *v58[3]; // [rsp+88h] [rbp-39h] BYREF
  unsigned __int64 v59; // [rsp+A0h] [rbp-21h]
  _BYTE v60[26]; // [rsp+A8h] [rbp-19h] BYREF
  char v61; // [rsp+C2h] [rbp+1h] BYREF

  HIBYTE(v55) = -1;
  v8 = std::use_facet<std::numpunct<char>>(a6);
  (*(void (__fastcall **)(struct std::_Facet_base *, void **))(*(_QWORD *)v8 + 40LL))(v8, v58);
  if ( v58[2] )
    v49 = (*(__int64 (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v8 + 32LL))(v8);
  else
    v49 = 0;
  v9 = std::use_facet<std::ctype<char>>(a6);
  (*(void (__fastcall **)(struct std::_Facet_base *, const char *, char *, _BYTE *))(*(_QWORD *)v9 + 56LL))(
    v9,
    "0123456789ABCDEFabcdef-+Xx",
    "",
    v60);
  v10 = a2;
  if ( !(unsigned __int8)std::istreambuf_iterator<char>::equal(a3, a4) )
  {
    if ( !*(_BYTE *)(a3 + 8) )
    {
      v11 = *(_QWORD *)a3;
      if ( !*(_QWORD *)a3
        || ((v12 = **(unsigned __int8 ***)(v11 + 56)) == 0 || **(int **)(v11 + 80) <= 0
          ? (v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 48LL))(v11))
          : (v13 = *v12),
            v13 == -1) )
      {
        *(_QWORD *)a3 = 0;
      }
      else
      {
        *(_BYTE *)(a3 + 9) = v13;
      }
      *(_BYTE *)(a3 + 8) = 1;
    }
    if ( *(_BYTE *)(a3 + 9) == v60[23] )
    {
      *a2 = 43;
    }
    else
    {
      if ( *(_BYTE *)(a3 + 9) != v60[22] )
        goto LABEL_20;
      *a2 = 45;
    }
    v10 = a2 + 1;
    std::istreambuf_iterator<char>::operator++((__int64 *)a3);
  }
LABEL_20:
  v14 = a5 & 0xE00;
  v53 = 10;
  v15 = v14 != 0 ? 0xA : 0;
  if ( v14 == 2048 )
    v15 = 16;
  if ( v14 == 1024 )
    v15 = 8;
  v51 = v15;
  v16 = 0;
  v50 = 0;
  if ( (unsigned __int8)std::istreambuf_iterator<char>::equal(a3, a4) )
    goto LABEL_53;
  if ( !*(_BYTE *)(a3 + 8) )
  {
    v17 = *(_QWORD *)a3;
    if ( !*(_QWORD *)a3
      || ((v18 = **(unsigned __int8 ***)(v17 + 56)) == 0 || **(int **)(v17 + 80) <= 0
        ? (v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 48LL))(v17))
        : (v19 = *v18),
          v19 == -1) )
    {
      *(_QWORD *)a3 = 0;
    }
    else
    {
      *(_BYTE *)(a3 + 9) = v19;
    }
    *(_BYTE *)(a3 + 8) = 1;
  }
  if ( *(_BYTE *)(a3 + 9) != v60[0] )
  {
LABEL_53:
    if ( !v15 )
      goto LABEL_58;
    goto LABEL_54;
  }
  std::istreambuf_iterator<char>::operator++((__int64 *)a3);
  if ( (unsigned __int8)std::istreambuf_iterator<char>::equal(a3, a4) )
    goto LABEL_51;
  if ( !*(_BYTE *)(a3 + 8) )
  {
    v20 = *(_QWORD *)a3;
    if ( !*(_QWORD *)a3
      || ((v21 = **(unsigned __int8 ***)(v20 + 56)) == 0 || **(int **)(v20 + 80) <= 0
        ? (v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 48LL))(v20))
        : (v22 = *v21),
          v22 == -1) )
    {
      *(_QWORD *)a3 = 0;
    }
    else
    {
      *(_BYTE *)(a3 + 9) = v22;
    }
    *(_BYTE *)(a3 + 8) = 1;
  }
  if ( (v23 = *(_BYTE *)(a3 + 9), v23 != v60[25]) && v23 != v60[24] || (v15 & 0xFFFFFFEF) != 0 )
  {
LABEL_51:
    v16 = 1;
    if ( !v15 )
    {
      v15 = 8;
      v51 = 8;
      goto LABEL_55;
    }
LABEL_54:
    if ( v15 != 10 )
      goto LABEL_55;
LABEL_58:
    v51 = v15;
    goto LABEL_59;
  }
  v15 = 16;
  v51 = 16;
  std::istreambuf_iterator<char>::operator++((__int64 *)a3);
LABEL_55:
  v24 = 22;
  if ( v15 == 8 )
    v24 = 8;
  v53 = v24;
LABEL_59:
  v25 = 15;
  v57 = 15;
  LOWORD(v56[0]) = v16;
  v56[2] = (void *)1;
  v26 = 0;
  v27 = (void **)v56[0];
  if ( (unsigned __int8)std::istreambuf_iterator<char>::equal(a3, a4) )
    goto LABEL_108;
  while ( 1 )
  {
    if ( !*(_BYTE *)(a3 + 8) )
    {
      v28 = *(_QWORD *)a3;
      if ( !*(_QWORD *)a3
        || ((v29 = **(unsigned __int8 ***)(v28 + 56)) == 0 || **(int **)(v28 + 80) <= 0
          ? (v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28))
          : (v30 = *v29),
            v30 == -1) )
      {
        *(_QWORD *)a3 = 0;
      }
      else
      {
        *(_BYTE *)(a3 + 9) = v30;
      }
      *(_BYTE *)(a3 + 8) = 1;
    }
    v31 = v60;
    do
    {
      if ( *v31 == *(_BYTE *)(a3 + 9) )
        break;
      ++v31;
    }
    while ( v31 != &v61 );
    v32 = v31 - v60;
    if ( v32 >= v53 )
      break;
    v33 = `std::num_get<char,std::istreambuf_iterator<char>>::_Getifld'::`2'::_Src[v32];
    *v10 = v33;
    if ( (v50 || v33 != 48) && v10 < a2 + 31 )
    {
      ++v10;
      v50 = 1;
    }
    v16 = 1;
    v34 = v56;
    if ( v25 >= 0x10 )
      v34 = v27;
    if ( *((_BYTE *)v34 + v26) == 127 )
      goto LABEL_101;
    v35 = v56;
    if ( v25 >= 0x10 )
      v35 = v27;
    ++*((_BYTE *)v35 + v26);
LABEL_100:
    v27 = (void **)v56[0];
    v25 = v57;
LABEL_101:
    std::istreambuf_iterator<char>::operator++((__int64 *)a3);
    if ( (unsigned __int8)std::istreambuf_iterator<char>::equal(a3, a4) )
      goto LABEL_102;
  }
  v36 = v56;
  if ( v25 >= 0x10 )
    v36 = v27;
  if ( *((_BYTE *)v36 + v26) )
  {
    v37 = v49;
    if ( v49 )
    {
      if ( !*(_BYTE *)(a3 + 8) )
      {
        v38 = *(_QWORD *)a3;
        if ( !*(_QWORD *)a3
          || ((v39 = **(unsigned __int8 ***)(v38 + 56)) == 0 || **(int **)(v38 + 80) <= 0
            ? (v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 48LL))(v38), v37 = v49)
            : (v40 = *v39),
              v40 == -1) )
        {
          *(_QWORD *)a3 = 0;
        }
        else
        {
          *(_BYTE *)(a3 + 9) = v40;
        }
        *(_BYTE *)(a3 + 8) = 1;
      }
      if ( *(_BYTE *)(a3 + 9) == v37 )
      {
        std::string::append(v56, 1);
        ++v26;
        goto LABEL_100;
      }
    }
  }
LABEL_102:
  v15 = v51;
  if ( v26 )
  {
    v41 = v56;
    if ( v25 >= 0x10 )
      v41 = v27;
    if ( *((char *)v41 + v26) <= 0 )
      v16 = 0;
    else
      ++v26;
  }
LABEL_108:
  v42 = v58;
  v43 = v58[0];
  v44 = v59;
  if ( v59 >= 0x10 )
    v42 = (void **)v58[0];
  if ( v16 )
  {
    while ( v26 )
    {
      v45 = *(_BYTE *)v42;
      if ( *(_BYTE *)v42 == 127 )
        break;
      if ( --v26 )
      {
        v46 = v56;
        if ( v25 >= 0x10 )
          v46 = v27;
        if ( v45 != *((_BYTE *)v46 + v26) )
          goto LABEL_125;
      }
      if ( !v26 )
      {
        v47 = v56;
        if ( v25 >= 0x10 )
          v47 = v27;
        if ( v45 < *(char *)v47 )
          goto LABEL_125;
      }
      if ( *((char *)v42 + 1) > 0 )
        v42 = (void **)((char *)v42 + 1);
    }
    if ( !v50 )
      *v10++ = 48;
  }
  else
  {
LABEL_125:
    v10 = a2;
  }
  *v10 = 0;
  if ( v25 >= 0x10 )
  {
    operator delete(v27);
    v44 = v59;
    v43 = v58[0];
  }
  if ( v44 >= 0x10 )
    operator delete(v43);
  return v15;
}

```

## disassembly

```asm
0x1800053b4  mov     rax, rsp
0x1800053b7  push    rbp
0x1800053b8  push    rsi
0x1800053b9  push    rdi
0x1800053ba  push    r12
0x1800053bc  push    r13
0x1800053be  push    r14
0x1800053c0  push    r15
0x1800053c2  lea     rbp, [rax-4Fh]
0x1800053c6  sub     rsp, 0D0h
0x1800053cd  mov     [rbp+47h+var_A8], 0FFFFFFFFFFFFFFFEh
0x1800053d5  mov     [rax+8], rbx
0x1800053d9  mov     rax, cs:__security_cookie
0x1800053e0  xor     rax, rsp
0x1800053e3  mov     [rbp+47h+var_40], rax
0x1800053e7  mov     [rsp+38h], r9
0x1800053ec  mov     rbx, r8
0x1800053ef  mov     r14, rdx
0x1800053f2  mov     [rbp+47h+var_B8], rdx
0x1800053f6  mov     rsi, [rbp+47h+arg_28]
0x1800053fa  xor     r15d, r15d
0x1800053fd  mov     rcx, rsi
0x180005400  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180005405  mov     rdi, rax
0x180005408  mov     rcx, [rax]
0x18000540b  mov     rax, [rcx+28h]
0x18000540f  lea     rdx, [rbp+47h+var_80]
0x180005413  mov     rcx, rdi
0x180005416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000541b  nop
0x18000541c  cmp     [rbp+47h+var_70], r15
0x180005420  jnz     short loc_180005429
0x180005422  mov     byte ptr [rsp+100h+var_D0], r15b
0x180005427  jmp     short loc_18000543C
0x180005429  mov     rax, [rdi]
0x18000542c  mov     rcx, rdi
0x18000542f  mov     rax, [rax+20h]
0x180005433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005438  mov     byte ptr [rsp+100h+var_D0], al
0x18000543c  mov     rcx, rsi
0x18000543f  call    ??$use_facet@V?$ctype@D@std@@@std@@YAAEBV?$ctype@D@0@AEBVlocale@0@@Z; std::use_facet<std::ctype<char>>(std::locale const &)
0x180005444  mov     r10, rax
0x180005447  mov     rcx, [rax]
0x18000544a  mov     rax, [rcx+38h]
0x18000544e  lea     r9, [rbp+47h+var_60]
0x180005452  lea     r8, ?_Src@?1??_Getifld@?$num_get@DV?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@DU?$char_traits@D@std@@@3@1HAEBVlocale@3@@Z@4QBDB+1Ah; ""
0x180005459  lea     rdx, ?_Src@?1??_Getifld@?$num_get@DV?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@DU?$char_traits@D@std@@@3@1HAEBVlocale@3@@Z@4QBDB; "0123456789ABCDEFabcdef-+Xx"
0x180005460  mov     rcx, r10
0x180005463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005468  mov     r13, r14
0x18000546b  mov     rdi, [rsp+38h]
0x180005470  mov     rdx, rdi
0x180005473  mov     rcx, rbx
0x180005476  call    ?equal@?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEBA_NAEBV12@@Z; std::istreambuf_iterator<char>::equal(std::istreambuf_iterator<char> const &)
0x18000547b  test    al, al
0x18000547d  jnz     loc_180005538
0x180005483  mov     al, [rbx+8]
0x180005486  test    al, al
0x180005488  jnz     short loc_1800054CB
0x18000548a  mov     rcx, [rbx]
0x18000548d  test    rcx, rcx
0x180005490  jz      short loc_1800054C2
0x180005492  mov     rax, [rcx+38h]
0x180005496  mov     rdx, [rax]
0x180005499  test    rdx, rdx
0x18000549c  jz      short loc_1800054AC
0x18000549e  mov     rax, [rcx+50h]
0x1800054a2  cmp     [rax], r15d
0x1800054a5  jle     short loc_1800054AC
0x1800054a7  movzx   eax, byte ptr [rdx]
0x1800054aa  jmp     short loc_1800054B8
0x1800054ac  mov     rax, [rcx]
0x1800054af  mov     rax, [rax+30h]
0x1800054b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b8  cmp     eax, 0FFFFFFFFh
0x1800054bb  jz      short loc_1800054C2
0x1800054bd  mov     [rbx+9], al
0x1800054c0  jmp     short loc_1800054C5
0x1800054c2  mov     [rbx], r15
0x1800054c5  mov     byte ptr [rbx+8], 1
0x1800054c9  mov     al, 1
0x1800054cb  mov     cl, [rbx+9]
0x1800054ce  cmp     cl, [rbp+47h+var_49]
0x1800054d1  jnz     short loc_1800054D9
0x1800054d3  mov     byte ptr [r14], 2Bh ; '+'
0x1800054d7  jmp     short loc_18000552C
0x1800054d9  test    al, al
0x1800054db  jnz     short loc_180005521
0x1800054dd  mov     rcx, [rbx]
0x1800054e0  test    rcx, rcx
0x1800054e3  jz      short loc_180005515
0x1800054e5  mov     rax, [rcx+38h]
0x1800054e9  mov     rdx, [rax]
0x1800054ec  test    rdx, rdx
0x1800054ef  jz      short loc_1800054FF
0x1800054f1  mov     rax, [rcx+50h]
0x1800054f5  cmp     [rax], r15d
0x1800054f8  jle     short loc_1800054FF
0x1800054fa  movzx   eax, byte ptr [rdx]
0x1800054fd  jmp     short loc_18000550B
0x1800054ff  mov     rax, [rcx]
0x180005502  mov     rax, [rax+30h]
0x180005506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000550b  cmp     eax, 0FFFFFFFFh
0x18000550e  jz      short loc_180005515
0x180005510  mov     [rbx+9], al
0x180005513  jmp     short loc_18000551B
0x180005515  mov     [rbx], r15
0x180005518  mov     al, [rbx+9]
0x18000551b  mov     byte ptr [rbx+8], 1
0x18000551f  jmp     short loc_180005523
0x180005521  mov     al, cl
0x180005523  cmp     al, [rbp+47h+var_4A]
0x180005526  jnz     short loc_180005538
0x180005528  mov     byte ptr [r14], 2Dh ; '-'
0x18000552c  lea     r13, [r14+1]
0x180005530  mov     rcx, rbx
0x180005533  call    ??E?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEAAAEAV01@XZ; std::istreambuf_iterator<char>::operator++(void)
0x180005538  mov     ecx, dword ptr [rbp+47h+arg_20]
0x18000553b  and     ecx, 0E00h
0x180005541  mov     eax, ecx
0x180005543  neg     eax
0x180005545  sbb     r12d, r12d
0x180005548  mov     esi, 0Ah
0x18000554d  mov     [rbp+47h+var_C0], rsi
0x180005551  and     r12d, esi
0x180005554  lea     eax, [rsi+6]
0x180005557  cmp     ecx, 800h
0x18000555d  cmovz   r12d, eax
0x180005561  lea     eax, [rsi-2]
0x180005564  cmp     ecx, 400h
0x18000556a  cmovz   r12d, eax
0x18000556e  mov     dword ptr [rsp+100h+var_D0+4], r12d
0x180005573  xor     r14d, r14d
0x180005576  mov     r15b, r14b
0x180005579  mov     byte ptr [rsp+100h+var_D0+1], r14b
0x18000557e  mov     rdx, rdi
0x180005581  mov     rcx, rbx
0x180005584  call    ?equal@?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEBA_NAEBV12@@Z; std::istreambuf_iterator<char>::equal(std::istreambuf_iterator<char> const &)
0x180005589  test    al, al
0x18000558b  jnz     loc_1800056CC
0x180005591  cmp     [rbx+8], r14b
0x180005595  jnz     short loc_1800055D6
0x180005597  mov     rcx, [rbx]
0x18000559a  test    rcx, rcx
0x18000559d  jz      short loc_1800055CF
0x18000559f  mov     rax, [rcx+38h]
0x1800055a3  mov     rdx, [rax]
0x1800055a6  test    rdx, rdx
0x1800055a9  jz      short loc_1800055B9
0x1800055ab  mov     rax, [rcx+50h]
0x1800055af  cmp     [rax], r14d
0x1800055b2  jle     short loc_1800055B9
0x1800055b4  movzx   eax, byte ptr [rdx]
0x1800055b7  jmp     short loc_1800055C5
0x1800055b9  mov     rax, [rcx]
0x1800055bc  mov     rax, [rax+30h]
0x1800055c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c5  cmp     eax, 0FFFFFFFFh
0x1800055c8  jz      short loc_1800055CF
0x1800055ca  mov     [rbx+9], al
0x1800055cd  jmp     short loc_1800055D2
0x1800055cf  mov     [rbx], r14
0x1800055d2  mov     byte ptr [rbx+8], 1
0x1800055d6  mov     al, [rbp+47h+var_60]
0x1800055d9  cmp     [rbx+9], al
0x1800055dc  jnz     loc_1800056CC
0x1800055e2  mov     rcx, rbx
0x1800055e5  call    ??E?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEAAAEAV01@XZ; std::istreambuf_iterator<char>::operator++(void)
0x1800055ea  mov     rdx, rdi
0x1800055ed  mov     rcx, rbx
0x1800055f0  call    ?equal@?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEBA_NAEBV12@@Z; std::istreambuf_iterator<char>::equal(std::istreambuf_iterator<char> const &)
0x1800055f5  test    al, al
0x1800055f7  jnz     loc_1800056B6
0x1800055fd  mov     cl, [rbx+8]
0x180005600  test    cl, cl
0x180005602  jnz     short loc_180005645
0x180005604  mov     rcx, [rbx]
0x180005607  test    rcx, rcx
0x18000560a  jz      short loc_18000563C
0x18000560c  mov     rax, [rcx+38h]
0x180005610  mov     rdx, [rax]
0x180005613  test    rdx, rdx
0x180005616  jz      short loc_180005626
0x180005618  mov     rax, [rcx+50h]
0x18000561c  cmp     [rax], r14d
0x18000561f  jle     short loc_180005626
0x180005621  movzx   eax, byte ptr [rdx]
0x180005624  jmp     short loc_180005632
0x180005626  mov     rax, [rcx]
0x180005629  mov     rax, [rax+30h]
0x18000562d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005632  cmp     eax, 0FFFFFFFFh
0x180005635  jz      short loc_18000563C
0x180005637  mov     [rbx+9], al
0x18000563a  jmp     short loc_18000563F
0x18000563c  mov     [rbx], r14
0x18000563f  mov     byte ptr [rbx+8], 1
0x180005643  mov     cl, 1
0x180005645  mov     al, [rbx+9]
0x180005648  cmp     al, [rbp+47h+var_47]
0x18000564b  jz      short loc_180005698
0x18000564d  test    cl, cl
0x18000564f  jnz     short loc_180005693
0x180005651  mov     rcx, [rbx]
0x180005654  test    rcx, rcx
0x180005657  jz      short loc_180005689
0x180005659  mov     rax, [rcx+38h]
0x18000565d  mov     rdx, [rax]
0x180005660  test    rdx, rdx
0x180005663  jz      short loc_180005673
0x180005665  mov     rax, [rcx+50h]
0x180005669  cmp     [rax], r14d
0x18000566c  jle     short loc_180005673
0x18000566e  movzx   eax, byte ptr [rdx]
0x180005671  jmp     short loc_18000567F
0x180005673  mov     rax, [rcx]
0x180005676  mov     rax, [rax+30h]
0x18000567a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000567f  cmp     eax, 0FFFFFFFFh
0x180005682  jz      short loc_180005689
0x180005684  mov     [rbx+9], al
0x180005687  jmp     short loc_18000568F
0x180005689  mov     [rbx], r14
0x18000568c  mov     al, [rbx+9]
0x18000568f  mov     byte ptr [rbx+8], 1
0x180005693  cmp     al, [rbp+47h+var_48]
0x180005696  jnz     short loc_1800056B6
0x180005698  test    r12d, 0FFFFFFEFh
0x18000569f  jnz     short loc_1800056B6
0x1800056a1  mov     r12d, 10h
0x1800056a7  mov     dword ptr [rsp+100h+var_D0+4], r12d
0x1800056ac  mov     rcx, rbx
0x1800056af  call    ??E?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEAAAEAV01@XZ; std::istreambuf_iterator<char>::operator++(void)
0x1800056b4  jmp     short loc_1800056D6
0x1800056b6  mov     r15b, 1
0x1800056b9  test    r12d, r12d
0x1800056bc  jnz     short loc_1800056D1
0x1800056be  lea     eax, [r12+8]
0x1800056c3  mov     r12d, eax
0x1800056c6  mov     dword ptr [rsp+100h+var_D0+4], eax
0x1800056ca  jmp     short loc_1800056DB
0x1800056cc  test    r12d, r12d
0x1800056cf  jz      short loc_1800056ED
0x1800056d1  cmp     r12d, esi
0x1800056d4  jz      short loc_1800056ED
0x1800056d6  mov     eax, 8
0x1800056db  mov     esi, 16h
0x1800056e0  cmp     r12d, eax
0x1800056e3  cmovz   rsi, rax
0x1800056e7  mov     [rbp+47h+var_C0], rsi
0x1800056eb  jmp     short loc_1800056F2
0x1800056ed  mov     dword ptr [rsp+100h+var_D0+4], r12d
0x1800056f2  mov     r14d, 0Fh
0x1800056f8  mov     [rbp+47h+var_88], r14
0x1800056fc  mov     byte ptr [rbp+47h+var_A0], r15b
0x180005700  mov     [rbp+47h+var_90], 1
0x180005708  mov     byte ptr [rbp+47h+var_A0+1], 0
0x18000570c  xor     edi, edi
0x18000570e  mov     rax, [rbp+47h+var_B8]
0x180005712  add     rax, 1Fh
0x180005716  mov     [rbp+47h+var_B0], rax
0x18000571a  mov     rdx, [rsp+38h]
0x18000571f  mov     rcx, rbx
0x180005722  call    ?equal@?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEBA_NAEBV12@@Z; std::istreambuf_iterator<char>::equal(std::istreambuf_iterator<char> const &)
0x180005727  xor     r10d, r10d
0x18000572a  mov     rsi, [rbp+47h+var_A0]
0x18000572e  test    al, al
0x180005730  jnz     loc_1800058D6
0x180005736  mov     r12, [rbp+47h+var_B0]
0x18000573a  cmp     [rbx+8], r10b
0x18000573e  jnz     short loc_180005782
0x180005740  mov     rcx, [rbx]
0x180005743  test    rcx, rcx
0x180005746  jz      short loc_18000577B
0x180005748  mov     rax, [rcx+38h]
0x18000574c  mov     rdx, [rax]
0x18000574f  test    rdx, rdx
0x180005752  jz      short loc_180005762
0x180005754  mov     rax, [rcx+50h]
0x180005758  cmp     [rax], r10d
0x18000575b  jle     short loc_180005762
0x18000575d  movzx   eax, byte ptr [rdx]
0x180005760  jmp     short loc_180005771
0x180005762  mov     rax, [rcx]
0x180005765  mov     rax, [rax+30h]
0x180005769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000576e  xor     r10d, r10d
0x180005771  cmp     eax, 0FFFFFFFFh
0x180005774  jz      short loc_18000577B
0x180005776  mov     [rbx+9], al
0x180005779  jmp     short loc_18000577E
0x18000577b  mov     [rbx], r10
0x18000577e  mov     byte ptr [rbx+8], 1
0x180005782  mov     cl, [rbx+9]
0x180005785  lea     rax, [rbp+47h+var_60]
0x180005789  cmp     [rax], cl
0x18000578b  jz      short loc_180005799
0x18000578d  inc     rax
0x180005790  lea     rdx, [rbp+47h+var_46]
  ... truncated ...
```

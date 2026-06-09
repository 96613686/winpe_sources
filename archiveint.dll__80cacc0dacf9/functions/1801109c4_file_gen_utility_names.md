# file_gen_utility_names

- ea: `0x1801109c4`
- end: `0x180110dff`
- name: `file_gen_utility_names`
- size: `1083`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x180111004`
- `0x180113000`

## callees

- `0x180006c00`
- `0x18000a2d0`
- `0x1800aba6c`
- `0x1800b0b0c`
- `0x1800b1f40`
- `0x1800b2770`
- `0x1800ed038`
- `0x1800ed434`
- `0x18010fd54`
- `0x1801109c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180110a48`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180110ccd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180110a48`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180110ccd`

## string_xrefs

- `0x180110a53`: `Can't allocate memory for Pathname`
- `0x180110cd8`: `Can't allocate memory for Linkname`
- `0x180110a7d`: `Can't translate pathname '%s' to UTF-8`
- `0x180110d0d`: `Can't translate symlink '%s' to UTF-8`

## pseudocode

```c
__int64 __fastcall file_gen_utility_names(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  unsigned int v6; // r12d
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  char *v10; // r14
  unsigned __int64 v11; // rbp
  char *v12; // rdi
  char v13; // r8
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbx
  _BYTE *v16; // rcx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  __int64 v19; // rbp
  char *i; // rcx
  __int64 v21; // r8
  const void *v22; // rdx
  _BYTE *v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rcx
  const char *v26; // rax
  __int64 v27; // r8
  __int64 v28; // rdx
  char v29; // dl
  char *v30; // rcx
  char *v31; // r8
  char *v32; // rax
  _BYTE *v33; // rcx
  _BYTE *v34; // rdx
  __int64 v35; // [rsp+70h] [rbp+8h] BYREF
  __int64 v36; // [rsp+78h] [rbp+10h] BYREF
  __int64 v37; // [rsp+80h] [rbp+18h]

  v2 = *(_QWORD *)(a1 + 248);
  v35 = 0;
  v36 = 0;
  v37 = v2;
  a2[15] = 0;
  a2[18] = 0;
  a2[21] = 0;
  if ( (_QWORD *)a2[11] == a2 )
    return 0;
  v6 = 0;
  if ( (unsigned int)archive_mstring_get_mbs_l(
                       *(_QWORD *)a2[4],
                       (unsigned int)a2[4] + 488,
                       (unsigned int)&v35,
                       (unsigned int)&v36,
                       *(_QWORD *)(v2 + 344)) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Pathname");
      return 4294967266LL;
    }
    v7 = (const char *)archive_entry_pathname(a2[4]);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to UTF-8", v7);
    v6 = -20;
  }
  v8 = v36;
  v9 = v35;
  a2[15] = 0;
  archive_strncat(a2 + 14, v9, v8);
  v10 = (char *)a2[14];
  v11 = a2[15];
  v12 = v10;
  cleanup_backslash(v10, v11);
  v13 = *v10;
  if ( !*v10 )
  {
    v15 = v11;
    goto LABEL_27;
  }
  v14 = v11;
  while ( 1 )
  {
    if ( v13 == 47 )
    {
      ++v12;
      v11 = v14 - 1;
      goto LABEL_20;
    }
    v15 = v14;
    if ( *v12 != 46 )
      goto LABEL_24;
    v16 = v12 + 1;
    if ( v12[1] != 46 )
      break;
    if ( v12[2] != 47 )
    {
      if ( v12[2] )
        goto LABEL_24;
      goto LABEL_19;
    }
    v12 += 3;
    v11 = v14 - 3;
LABEL_20:
    v13 = *v12;
    v14 = v11;
    v15 = v11;
    if ( !*v12 )
      goto LABEL_24;
  }
  if ( *v16 == 47 )
  {
LABEL_19:
    v12 += 2;
    v11 = v14 - 2;
    goto LABEL_20;
  }
  if ( !*v16 )
  {
    v11 = v14 - 1;
    ++v12;
    v15 = v14 - 1;
  }
LABEL_24:
  if ( v12 != v10 )
  {
    memmove_0(v10, v12, v15 + 1);
    v12 = v10;
  }
  do
  {
LABEL_27:
    if ( !v11 )
      break;
    v17 = v15;
    if ( v12[v15 - 1] == 47 )
    {
      v11 = v15 - 1;
      v12[v15 - 1] = 0;
      v18 = --v15;
    }
    else
    {
      v18 = v15;
    }
    if ( v18 > 1 )
    {
      if ( v12[v15 - 2] == 47 && v12[v15 - 1] == 46 )
      {
        v11 = v18 - 2;
        v12[v15 - 2] = 0;
        v18 = v11;
        v15 = v11;
      }
      if ( v18 > 2 && v12[v15 - 3] == 47 && v12[v15 - 2] == 46 && v12[v15 - 1] == 46 )
      {
        v11 = v18 - 3;
        v12[v15 - 3] = 0;
        v15 = v18 - 3;
      }
    }
  }
  while ( v17 != v15 );
  v19 = -1;
  while ( *v12 )
  {
    i = v12 + 1;
    if ( *v12 != 47 )
      goto LABEL_61;
    if ( *i == 47 )
    {
      v21 = -1;
      do
        ++v21;
      while ( i[v21] );
      v22 = v12 + 1;
LABEL_52:
      memmove_0(v12, v22, v21 + 1);
      continue;
    }
    if ( *i != 46 )
      goto LABEL_61;
    v23 = v12 + 2;
    if ( v12[2] == 47 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v23[v21] );
      v22 = v12 + 2;
      goto LABEL_52;
    }
    if ( *v23 != 46 || v12[3] != 47 )
      goto LABEL_61;
    for ( i = v12 - 1; i >= v10 && *i != 47; --i )
      ;
    if ( i > v10 )
    {
      strcpy(i, v12 + 3);
LABEL_61:
      v12 = i;
      continue;
    }
    v12 = strcpy(v10, v12 + 4);
  }
  v24 = -1;
  do
    ++v24;
  while ( v10[v24] );
  v25 = a2[4];
  if ( (*(_WORD *)(v25 + 1032) & 0xF000) != 0xA000 )
  {
LABEL_72:
    v29 = *v10;
    v30 = 0;
    if ( *v10 )
    {
      v31 = v10;
      do
      {
        v32 = v31;
        if ( v29 != 47 )
          v32 = v30;
        ++v31;
        v30 = v32;
        v29 = *v31;
      }
      while ( *v31 );
    }
    if ( v30 )
    {
      *v30 = 0;
      v34 = v30 + 1;
      a2[18] = 0;
      a2[15] = v30 - v10;
      if ( v30 == (char *)-1LL )
      {
        v19 = 0;
      }
      else
      {
        do
          ++v19;
        while ( v34[v19] );
      }
      archive_strncat(a2 + 17, v34, v19);
    }
    else
    {
      a2[15] = v24;
      a2[18] = 0;
      archive_string_concat(a2 + 17, a2 + 14);
      v33 = (_BYTE *)a2[14];
      a2[15] = 0;
      *v33 = 0;
    }
    return v6;
  }
  v36 = 0;
  if ( !(unsigned int)archive_entry_symlink_l(v25, &v35, &v36, *(_QWORD *)(v37 + 344)) )
  {
LABEL_71:
    v27 = v36;
    v28 = v35;
    a2[21] = 0;
    archive_strncat(a2 + 20, v28, v27);
    cleanup_backslash(a2[20], a2[21]);
    goto LABEL_72;
  }
  if ( *(_DWORD *)_o__errno() != 12 )
  {
    v26 = (const char *)archive_entry_symlink(a2[4]);
    archive_set_error(a1, 42, "Can't translate symlink '%s' to UTF-8", v26);
    v6 = -20;
    goto LABEL_71;
  }
  archive_set_error(a1, 12, "Can't allocate memory for Linkname");
  return 4294967266LL;
}

```

## disassembly

```asm
0x1801109c4  mov     [rsp+arg_18], rbx
0x1801109c9  push    rbp
0x1801109ca  push    rsi
0x1801109cb  push    rdi
0x1801109cc  push    r12
0x1801109ce  push    r13
0x1801109d0  push    r14
0x1801109d2  push    r15
0x1801109d4  sub     rsp, 30h
0x1801109d8  mov     rax, [rcx+0F8h]
0x1801109df  xor     ebx, ebx
0x1801109e1  mov     rsi, rdx
0x1801109e4  mov     r15, rcx
0x1801109e7  mov     [rsp+68h+arg_0], rbx
0x1801109ec  mov     [rsp+68h+arg_8], rbx
0x1801109f1  mov     [rsp+68h+arg_10], rax
0x1801109f9  mov     [rdx+78h], rbx
0x1801109fd  mov     [rdx+90h], rbx
0x180110a04  mov     [rdx+0A8h], rbx
0x180110a0b  cmp     [rdx+58h], rdx
0x180110a0f  jnz     short loc_180110A18
0x180110a11  xor     eax, eax
0x180110a13  jmp     loc_180110DE7
0x180110a18  mov     rcx, [rdx+20h]
0x180110a1c  lea     r9, [rsp+68h+arg_8]
0x180110a21  mov     rax, [rax+158h]
0x180110a28  lea     r8, [rsp+68h+arg_0]
0x180110a2d  mov     r12d, ebx
0x180110a30  mov     [rsp+68h+var_48], rax
0x180110a35  lea     rdx, [rcx+1E8h]
0x180110a3c  mov     rcx, [rcx]
0x180110a3f  call    archive_mstring_get_mbs_l
0x180110a44  test    eax, eax
0x180110a46  jz      short loc_180110A97
0x180110a48  call    cs:__imp__o__errno
0x180110a4e  cmp     dword ptr [rax], 0Ch
0x180110a51  jnz     short loc_180110A71
0x180110a53  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x180110a5a  mov     edx, 0Ch
0x180110a5f  mov     rcx, r15
0x180110a62  call    archive_set_error
0x180110a67  mov     eax, 0FFFFFFE2h
0x180110a6c  jmp     loc_180110DE7
0x180110a71  mov     rcx, [rsi+20h]
0x180110a75  call    archive_entry_pathname
0x180110a7a  mov     r9, rax
0x180110a7d  lea     r8, aCanTTranslateP_0; "Can't translate pathname '%s' to UTF-8"
0x180110a84  mov     edx, 2Ah ; '*'
0x180110a89  mov     rcx, r15
0x180110a8c  call    archive_set_error
0x180110a91  mov     r12d, 0FFFFFFECh
0x180110a97  mov     r8, [rsp+68h+arg_8]
0x180110a9c  lea     r13, [rsi+70h]
0x180110aa0  mov     rdx, [rsp+68h+arg_0]
0x180110aa5  mov     rcx, r13
0x180110aa8  mov     [rsi+78h], rbx
0x180110aac  call    archive_strncat
0x180110ab1  mov     r14, [r13+0]
0x180110ab5  mov     rbp, [rsi+78h]
0x180110ab9  mov     rcx, r14
0x180110abc  mov     rdx, rbp
0x180110abf  mov     rdi, r14
0x180110ac2  call    cleanup_backslash
0x180110ac7  mov     r8b, [r14]
0x180110aca  xor     r9d, r9d
0x180110acd  mov     dl, 2Fh ; '/'
0x180110acf  mov     r10b, 2Eh ; '.'
0x180110ad2  test    r8b, r8b
0x180110ad5  jz      loc_180110B60
0x180110adb  mov     rax, rbp
0x180110ade  cmp     r8b, dl
0x180110ae1  jnz     short loc_180110AEC
0x180110ae3  inc     rdi
0x180110ae6  lea     rbp, [rax-1]
0x180110aea  jmp     short loc_180110B20
0x180110aec  mov     rbx, rax
0x180110aef  cmp     [rdi], r10b
0x180110af2  jnz     short loc_180110B3F
0x180110af4  lea     rcx, [rdi+1]
0x180110af8  cmp     [rcx], r10b
0x180110afb  jnz     short loc_180110B14
0x180110afd  cmp     [rdi+2], dl
0x180110b00  jnz     short loc_180110B0C
0x180110b02  add     rdi, 3
0x180110b06  lea     rbp, [rax-3]
0x180110b0a  jmp     short loc_180110B20
0x180110b0c  cmp     [rdi+2], r9b
0x180110b10  jnz     short loc_180110B3F
0x180110b12  jmp     short loc_180110B18
0x180110b14  cmp     [rcx], dl
0x180110b16  jnz     short loc_180110B30
0x180110b18  add     rdi, 2
0x180110b1c  lea     rbp, [rax-2]
0x180110b20  mov     r8b, [rdi]
0x180110b23  mov     rax, rbp
0x180110b26  mov     rbx, rbp
0x180110b29  test    r8b, r8b
0x180110b2c  jnz     short loc_180110ADE
0x180110b2e  jmp     short loc_180110B3F
0x180110b30  cmp     [rcx], r9b
0x180110b33  jnz     short loc_180110B3F
0x180110b35  lea     rbp, [rax-1]
0x180110b39  mov     rdi, rcx
0x180110b3c  mov     rbx, rbp
0x180110b3f  cmp     rdi, r14
0x180110b42  jz      short loc_180110B63
0x180110b44  lea     r8, [rbx+1]; Size
0x180110b48  mov     rdx, rdi; Src
0x180110b4b  mov     rcx, r14; void *
0x180110b4e  call    memmove_0
0x180110b53  xor     r9d, r9d
0x180110b56  mov     dl, 2Fh ; '/'
0x180110b58  mov     r10b, 2Eh ; '.'
0x180110b5b  mov     rdi, r14
0x180110b5e  jmp     short loc_180110B63
0x180110b60  mov     rbx, rbp
0x180110b63  test    rbp, rbp
0x180110b66  jz      short loc_180110BD2
0x180110b68  mov     rcx, rbx
0x180110b6b  cmp     [rdi+rbx-1], dl
0x180110b6f  jnz     short loc_180110B82
0x180110b71  lea     rbp, [rbx-1]
0x180110b75  mov     [rdi+rbx-1], r9b
0x180110b7a  mov     rax, rbp
0x180110b7d  mov     rbx, rbp
0x180110b80  jmp     short loc_180110B85
0x180110b82  mov     rax, rbx
0x180110b85  cmp     rax, 1
0x180110b89  jbe     short loc_180110BCD
0x180110b8b  cmp     [rdi+rbx-2], dl
0x180110b8f  jnz     short loc_180110BA7
0x180110b91  cmp     [rdi+rbx-1], r10b
0x180110b96  jnz     short loc_180110BA7
0x180110b98  lea     rbp, [rax-2]
0x180110b9c  mov     [rdi+rbx-2], r9b
0x180110ba1  mov     rax, rbp
0x180110ba4  mov     rbx, rbp
0x180110ba7  cmp     rax, 2
0x180110bab  jbe     short loc_180110BCD
0x180110bad  cmp     [rdi+rbx-3], dl
0x180110bb1  jnz     short loc_180110BCD
0x180110bb3  cmp     [rdi+rbx-2], r10b
0x180110bb8  jnz     short loc_180110BCD
0x180110bba  cmp     [rdi+rbx-1], r10b
0x180110bbf  jnz     short loc_180110BCD
0x180110bc1  lea     rbp, [rax-3]
0x180110bc5  mov     [rdi+rbx-3], r9b
0x180110bca  mov     rbx, rbp
0x180110bcd  cmp     rcx, rbx
0x180110bd0  jnz     short loc_180110B63
0x180110bd2  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180110bd6  jmp     loc_180110C6D
0x180110bdb  lea     rcx, [rdi+1]
0x180110bdf  cmp     al, dl
0x180110be1  jnz     loc_180110C67
0x180110be7  cmp     [rcx], dl
0x180110be9  jnz     short loc_180110BFC
0x180110beb  mov     r8, rbp
0x180110bee  inc     r8
0x180110bf1  cmp     [rcx+r8], r9b
0x180110bf5  jnz     short loc_180110BEE
0x180110bf7  mov     rdx, rcx
0x180110bfa  jmp     short loc_180110C18
0x180110bfc  cmp     [rcx], r10b
0x180110bff  jnz     short loc_180110C67
0x180110c01  lea     rax, [rdi+2]
0x180110c05  cmp     [rax], dl
0x180110c07  jnz     short loc_180110C2A
0x180110c09  mov     r8, rbp
0x180110c0c  inc     r8
0x180110c0f  cmp     [rax+r8], r9b
0x180110c13  jnz     short loc_180110C0C
0x180110c15  mov     rdx, rax; Src
0x180110c18  inc     r8; Size
0x180110c1b  mov     rcx, rdi; void *
0x180110c1e  call    memmove_0
0x180110c23  xor     r9d, r9d
0x180110c26  mov     dl, 2Fh ; '/'
0x180110c28  jmp     short loc_180110C6A
0x180110c2a  cmp     [rax], r10b
0x180110c2d  jnz     short loc_180110C67
0x180110c2f  lea     r8, [rdi+3]
0x180110c33  cmp     [r8], dl
0x180110c36  jnz     short loc_180110C67
0x180110c38  lea     rcx, [rdi-1]
0x180110c3c  jmp     short loc_180110C45
0x180110c3e  cmp     [rcx], dl
0x180110c40  jz      short loc_180110C4A
0x180110c42  dec     rcx
0x180110c45  cmp     rcx, r14
0x180110c48  jnb     short loc_180110C3E
0x180110c4a  cmp     rcx, r14
0x180110c4d  jbe     loc_180110CE4
0x180110c53  mov     rdx, rcx
0x180110c56  mov     al, [r8]
0x180110c59  inc     r8
0x180110c5c  mov     [rdx], al
0x180110c5e  inc     rdx
0x180110c61  test    al, al
0x180110c63  jnz     short loc_180110C56
0x180110c65  mov     dl, 2Fh ; '/'
0x180110c67  mov     rdi, rcx
0x180110c6a  mov     r10b, 2Eh ; '.'
0x180110c6d  mov     al, [rdi]
0x180110c6f  test    al, al
0x180110c71  jnz     loc_180110BDB
0x180110c77  mov     rdi, rbp
0x180110c7a  inc     rdi
0x180110c7d  cmp     [r14+rdi], r9b
0x180110c81  jnz     short loc_180110C7A
0x180110c83  mov     rcx, [rsi+20h]
0x180110c87  mov     edx, 0F000h
0x180110c8c  movzx   eax, word ptr [rcx+408h]
0x180110c93  and     ax, dx
0x180110c96  mov     edx, 0A000h
0x180110c9b  cmp     ax, dx
0x180110c9e  jnz     loc_180110D59
0x180110ca4  mov     [rsp+68h+arg_8], r9
0x180110ca9  lea     r8, [rsp+68h+arg_8]
0x180110cae  mov     r9, [rsp+68h+arg_10]
0x180110cb6  lea     rdx, [rsp+68h+arg_0]
0x180110cbb  mov     r9, [r9+158h]
0x180110cc2  call    _archive_entry_symlink_l
0x180110cc7  xor     ebx, ebx
0x180110cc9  test    eax, eax
0x180110ccb  jz      short loc_180110D27
0x180110ccd  call    cs:__imp__o__errno
0x180110cd3  cmp     dword ptr [rax], 0Ch
0x180110cd6  jnz     short loc_180110D01
0x180110cd8  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x180110cdf  jmp     loc_180110A5A
0x180110ce4  add     rdi, 4
0x180110ce8  mov     rcx, r14
0x180110ceb  mov     al, [rdi]
0x180110ced  inc     rdi
0x180110cf0  mov     [rcx], al
0x180110cf2  inc     rcx
0x180110cf5  test    al, al
0x180110cf7  jnz     short loc_180110CEB
0x180110cf9  mov     rdi, r14
0x180110cfc  jmp     loc_180110C6A
0x180110d01  mov     rcx, [rsi+20h]
0x180110d05  call    archive_entry_symlink
0x180110d0a  mov     r9, rax
0x180110d0d  lea     r8, aCanTTranslateS; "Can't translate symlink '%s' to UTF-8"
0x180110d14  mov     edx, 2Ah ; '*'
0x180110d19  mov     rcx, r15
0x180110d1c  call    archive_set_error
0x180110d21  mov     r12d, 0FFFFFFECh
0x180110d27  mov     r8, [rsp+68h+arg_8]
0x180110d2c  mov     rdx, [rsp+68h+arg_0]
0x180110d31  mov     [rsi+0A8h], rbx
0x180110d38  lea     rbx, [rsi+0A0h]
0x180110d3f  mov     rcx, rbx
0x180110d42  call    archive_strncat
0x180110d47  mov     rdx, [rsi+0A8h]
0x180110d4e  mov     rcx, [rbx]
0x180110d51  call    cleanup_backslash
0x180110d56  xor     r9d, r9d
0x180110d59  mov     dl, [r14]
0x180110d5c  mov     rcx, r9
0x180110d5f  test    dl, dl
0x180110d61  jz      short loc_180110D7D
0x180110d63  mov     r8, r14
0x180110d66  cmp     dl, 2Fh ; '/'
0x180110d69  mov     rax, r8
0x180110d6c  cmovnz  rax, rcx
0x180110d70  inc     r8
0x180110d73  mov     rcx, rax
0x180110d76  mov     dl, [r8]
0x180110d79  test    dl, dl
0x180110d7b  jnz     short loc_180110D66
0x180110d7d  test    rcx, rcx
0x180110d80  jnz     short loc_180110DAA
0x180110d82  lea     rcx, [rsi+88h]
0x180110d89  mov     [rsi+78h], rdi
0x180110d8d  mov     rdx, r13
0x180110d90  mov     [rsi+90h], r9
0x180110d97  call    archive_string_concat
0x180110d9c  mov     rcx, [r13+0]
0x180110da0  xor     ebx, ebx
0x180110da2  mov     [rsi+78h], rbx
0x180110da6  mov     [rcx], bl
0x180110da8  jmp     short loc_180110DE4
0x180110daa  mov     [rcx], r9b
0x180110dad  lea     rdx, [rcx+1]
0x180110db1  mov     rax, rcx
0x180110db4  mov     [rsi+90h], r9
0x180110dbb  sub     rax, r14
0x180110dbe  mov     [rsi+78h], rax
0x180110dc2  test    rdx, rdx
0x180110dc5  jnz     short loc_180110DCC
0x180110dc7  mov     rbp, r9
0x180110dca  jmp     short loc_180110DD5
0x180110dcc  inc     rbp
0x180110dcf  cmp     [rdx+rbp], r9b
0x180110dd3  jnz     short loc_180110DCC
0x180110dd5  lea     rcx, [rsi+88h]
0x180110ddc  mov     r8, rbp
0x180110ddf  call    archive_strncat
  ... truncated ...
```

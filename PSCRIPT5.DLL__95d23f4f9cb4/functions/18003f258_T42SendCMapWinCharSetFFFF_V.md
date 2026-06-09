# T42SendCMapWinCharSetFFFF_V

- ea: `0x18003f258`
- end: `0x18003fa6b`
- name: `T42SendCMapWinCharSetFFFF_V`
- size: `2067`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, __int64, STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003d7e4`

## callees

- `0x1800055e0`
- `0x180038968`
- `0x1800389cc`
- `0x18003f258`

## string_xrefs

- `0x18003f2db`: `/Registry (%s) def`

## pseudocode

```c
__int64 __fastcall T42SendCMapWinCharSetFFFF_V(
        __int64 a1,
        unsigned __int16 *a2,
        __int16 a3,
        const char *a4,
        const char *a5,
        unsigned int a6,
        __int64 a7,
        STRSAFE_LPSTR pszDest)
{
  unsigned __int16 v11; // bx
  unsigned int v12; // ebp
  const char *v13; // r8
  unsigned __int16 v14; // dx
  __int64 v15; // r9
  __int16 v16; // r8
  __int16 v17; // r14
  __int16 v18; // cx
  int v19; // r15d
  __int16 v20; // r13
  unsigned __int16 v21; // r12
  unsigned __int16 *v22; // rcx
  int v23; // ebp
  int v24; // r9d
  char *v25; // r12
  int v26; // r12d
  __int16 i; // r14
  unsigned __int16 v28; // r15
  __int16 v29; // bp
  unsigned __int16 v30; // r15
  __int64 v31; // r9
  __int16 v32; // r12
  unsigned __int16 *v33; // rcx
  unsigned int v34; // r14d
  __int64 v35; // r9
  int v36; // r9d
  __int16 v38; // [rsp+70h] [rbp+8h]

  StringCchPrintfA(pszDest, 0x100u, "/CIDInit /ProcSet findresource begin 12 dict begin begincmap /%s usecmap", a4);
  v11 = StrmPutStringEOL(a7, pszDest);
  if ( !v11 )
    v11 = StrmPutStringEOL(a7, "/CIDSystemInfo [3 dict dup begin");
  StringCchPrintfA(pszDest, 0x100u, "/Registry (%s) def", a4 + 36);
  if ( !v11 )
    v11 = StrmPutStringEOL(a7, pszDest);
  StringCchPrintfA(pszDest, 0x100u, "/Ordering (%s) def", a5);
  if ( !v11 )
  {
    v11 = StrmPutStringEOL(a7, pszDest);
    if ( !v11 )
      v11 = StrmPutStringEOL(a7, "/Supplement 0 def");
  }
  v12 = a6;
  v13 = "end dup] def";
  if ( a6 > 0x7F00 )
    v13 = "end dup dup dup] def";
  StringCchPrintfA(pszDest, 0x100u, v13);
  if ( !v11 )
    v11 = StrmPutStringEOL(a7, pszDest);
  StringCchPrintfA(pszDest, 0x100u, "/CMapName /%s def", a5);
  if ( !v11 )
  {
    v11 = StrmPutStringEOL(a7, pszDest);
    if ( !v11 )
    {
      v11 = StrmPutStringEOL(a7, "/WMode 1 def");
      if ( !v11 )
      {
        v11 = StrmPutStringEOL(a7, "0 beginusematrix [0 1 -1 0 0 0] endusematrix");
        if ( !v11 && a4 == aWincharsetffff_0 )
          v11 = StrmPutStringEOL(a7, "2 beginusematrix [0 1 -1 0 0 0] endusematrix");
      }
    }
  }
  if ( !a3 )
    goto LABEL_118;
  v14 = *a2;
  v15 = 1;
  v16 = *a2 > 0x7F00u;
  v17 = *a2 <= 0x7F00u;
  if ( a3 > 0 )
  {
    v18 = 0;
    do
    {
      if ( v14 != a2[2 * (unsigned __int16)v18] )
      {
        v14 = a2[2 * (unsigned __int16)v18];
        if ( v14 <= 0x7F00u )
          ++v17;
        else
          ++v16;
      }
      ++v18;
    }
    while ( v18 < a3 );
  }
  v38 = v16;
  if ( !v11 )
    v11 = StrmPutStringEOL(a7, "1 usefont");
  if ( v17 <= 100 )
    StringCchPrintfA(pszDest, 0x100u, "%d begincidrange", v17);
  else
    StringCchPrintfA(pszDest, 0x100u, "100 begincidrange", v15);
  v19 = *a2;
  if ( !v11 )
  {
    v11 = StrmPutStringEOL(a7, pszDest);
    if ( !v11 )
    {
      v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)v19);
      if ( !v11 )
        v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)v19);
    }
    StringCchPrintfA(pszDest, 0x100u, "%u", v19);
    if ( !v11 )
      v11 = StrmPutStringEOL(a7, pszDest);
  }
  v20 = 1;
  v21 = 1;
  if ( a3 > 1 )
  {
    v22 = a2;
    do
    {
      v23 = v22[2 * v21];
      if ( (unsigned __int16)v23 > 0x7F00u )
        break;
      if ( (_WORD)v19 != (_WORD)v23 )
      {
        ++v20;
        LOWORD(v19) = v22[2 * v21];
        if ( !v11 )
        {
          v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)v23);
          if ( !v11 )
            v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)v23);
          StringCchPrintfA(pszDest, 0x100u, "%u", v23);
          if ( !v11 )
            v11 = StrmPutStringEOL(a7, pszDest);
        }
        if ( v20 == 100 * (v20 / 100) )
        {
          v24 = v17 - v20;
          if ( v24 <= 100 )
          {
            if ( v24 <= 0 )
              StringCchPrintfA(pszDest, 0x100u, " ");
            else
              StringCchPrintfA(pszDest, 0x100u, "endcidrange\n%d begincidrange", v24);
          }
          else
          {
            StringCchPrintfA(pszDest, 0x100u, "endcidrange\n100 begincidrange");
          }
          if ( !v11 )
            v11 = StrmPutStringEOL(a7, pszDest);
        }
        v22 = a2;
      }
      ++v21;
    }
    while ( (__int16)v21 < a3 );
    v12 = a6;
  }
  if ( !v11 )
    v11 = StrmPutStringEOL(a7, "endcidrange");
  if ( v12 <= 0x7F00 )
    goto LABEL_118;
  v25 = (char *)a4;
  if ( a4 == aWincharsetffff_0 )
  {
    if ( !v11 )
      v11 = StrmPutStringEOL(a7, "2 usefont");
    v26 = (int)(v12 - 32258) / 255;
    StringCchPrintfA(pszDest, 0x100u, "%d begincidrange", (__int16)v26);
    if ( !v11 )
      v11 = StrmPutStringEOL(a7, pszDest);
    for ( i = 0; i < (__int16)v26; ++i )
    {
      v28 = i << 8;
      if ( !v11 )
      {
        v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)(v28 + 32512));
        if ( !v11 )
          v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)(v28 + 0x7FFF));
      }
      StringCchPrintfA(pszDest, 0x100u, "%u", v28);
      if ( !v11 )
        v11 = StrmPutStringEOL(a7, pszDest);
    }
    if ( !v11 )
      v11 = StrmPutStringEOL(a7, "endcidrange");
    v25 = (char *)a4;
  }
  if ( v38 <= 0 )
    goto LABEL_118;
  if ( !v11 && v25 == aWincharsetffff_0 )
    v11 = StrmPutStringEOL(a7, "3 usefont");
  v29 = 0;
  if ( a3 <= 0 )
  {
    v30 = *a2;
  }
  else
  {
    do
    {
      v30 = a2[2 * (unsigned __int16)v29];
      if ( v30 > 0x7F00u )
        break;
      ++v29;
    }
    while ( v29 < a3 );
  }
  if ( v38 <= 100 )
    StringCchPrintfA(pszDest, 0x100u, "%d begincidrange", v38);
  else
    StringCchPrintfA(pszDest, 0x100u, "100 begincidrange");
  if ( !v11 )
  {
    v11 = StrmPutStringEOL(a7, pszDest);
    if ( !v11 )
    {
      v11 = StrmPutWordAsciiHex(a7, v30);
      if ( !v11 )
        v11 = StrmPutWordAsciiHex(a7, v30);
    }
    v31 = (unsigned int)v30 - 32512;
    if ( v25 != aWincharsetffff_0 )
      v31 = v30;
    StringCchPrintfA(pszDest, 0x100u, "%u", v31);
    if ( !v11 )
      v11 = StrmPutStringEOL(a7, pszDest);
  }
  v32 = 1;
  if ( v29 < a3 )
  {
    v33 = a2;
    do
    {
      v34 = v33[2 * v29];
      if ( v30 != (_WORD)v34 )
      {
        ++v32;
        v30 = v33[2 * v29];
        if ( !v11 )
        {
          v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)v34);
          if ( !v11 )
            v11 = StrmPutWordAsciiHex(a7, (unsigned __int16)v34);
          v35 = v34 - 32512;
          if ( a4 != aWincharsetffff_0 )
            v35 = v34;
          StringCchPrintfA(pszDest, 0x100u, "%u", v35);
          if ( !v11 )
            v11 = StrmPutStringEOL(a7, pszDest);
        }
        if ( v32 == 100 * (v32 / 100) )
        {
          v36 = v38 - v32;
          if ( v36 <= 100 )
          {
            if ( v36 <= 0 )
              StringCchPrintfA(pszDest, 0x100u, " ");
            else
              StringCchPrintfA(pszDest, 0x100u, "endcidrange %d begincidrange", v36);
          }
          else
          {
            StringCchPrintfA(pszDest, 0x100u, "endcidrange 100 begincidrange");
          }
          if ( !v11 )
            v11 = StrmPutStringEOL(a7, pszDest);
        }
        v33 = a2;
      }
      ++v29;
    }
    while ( v29 < a3 );
  }
  if ( !v11 )
  {
    v11 = StrmPutStringEOL(a7, "endcidrange");
LABEL_118:
    if ( !v11 )
      return (unsigned __int16)StrmPutStringEOL(a7, "endcmap CMapName currentdict /CMap defineresource pop end end");
  }
  return v11;
}

```

## disassembly

```asm
0x18003f258  mov     rax, rsp
0x18003f25b  mov     [rax+20h], r9
0x18003f25f  mov     [rax+18h], r8w
0x18003f264  mov     [rax+10h], rdx
0x18003f268  mov     [rax+8], rcx
0x18003f26c  push    rbx
0x18003f26d  push    rbp
0x18003f26e  push    rsi
0x18003f26f  push    rdi
0x18003f270  push    r12
0x18003f272  push    r13
0x18003f274  push    r14
0x18003f276  push    r15
0x18003f278  sub     rsp, 28h
0x18003f27c  mov     rsi, [rsp+68h+pszDest]
0x18003f284  movzx   r15d, r8w
0x18003f288  mov     r12, rdx
0x18003f28b  lea     r8, aCidinitProcset; "/CIDInit /ProcSet findresource begin 12"...
0x18003f292  mov     ebp, 100h
0x18003f297  mov     rcx, rsi; pszDest
0x18003f29a  mov     edx, ebp; cchDest
0x18003f29c  mov     r14, r9
0x18003f29f  call    StringCchPrintfA
0x18003f2a4  mov     rdi, [rsp+68h+arg_30]
0x18003f2ac  mov     rdx, rsi
0x18003f2af  mov     rcx, rdi
0x18003f2b2  call    StrmPutStringEOL
0x18003f2b7  xor     r13d, r13d
0x18003f2ba  movzx   ebx, ax
0x18003f2bd  test    ax, ax
0x18003f2c0  jnz     short loc_18003F2D4
0x18003f2c2  lea     rdx, aCidsysteminfo3_0; "/CIDSystemInfo [3 dict dup begin"
0x18003f2c9  mov     rcx, rdi
0x18003f2cc  call    StrmPutStringEOL
0x18003f2d1  movzx   ebx, ax
0x18003f2d4  lea     r9, [r14+24h]
0x18003f2d8  mov     rdx, rbp; cchDest
0x18003f2db  lea     r8, aRegistrySDef; "/Registry (%s) def"
0x18003f2e2  mov     rcx, rsi; pszDest
0x18003f2e5  call    StringCchPrintfA
0x18003f2ea  test    bx, bx
0x18003f2ed  jnz     short loc_18003F2FD
0x18003f2ef  mov     rdx, rsi
0x18003f2f2  mov     rcx, rdi
0x18003f2f5  call    StrmPutStringEOL
0x18003f2fa  movzx   ebx, ax
0x18003f2fd  mov     r9, [rsp+68h+arg_20]
0x18003f305  lea     r8, aOrderingSDef; "/Ordering (%s) def"
0x18003f30c  mov     rdx, rbp; cchDest
0x18003f30f  mov     rcx, rsi; pszDest
0x18003f312  call    StringCchPrintfA
0x18003f317  test    bx, bx
0x18003f31a  jnz     short loc_18003F341
0x18003f31c  mov     rdx, rsi
0x18003f31f  mov     rcx, rdi
0x18003f322  call    StrmPutStringEOL
0x18003f327  movzx   ebx, ax
0x18003f32a  test    ax, ax
0x18003f32d  jnz     short loc_18003F341
0x18003f32f  lea     rdx, aSupplement0Def; "/Supplement 0 def"
0x18003f336  mov     rcx, rdi
0x18003f339  call    StrmPutStringEOL
0x18003f33e  movzx   ebx, ax
0x18003f341  mov     ebp, [rsp+68h+arg_28]
0x18003f348  lea     rax, aEndDupDupDupDe; "end dup dup dup] def"
0x18003f34f  cmp     ebp, 7F00h
0x18003f355  lea     r8, aEndDupDef; "end dup] def"
0x18003f35c  mov     edx, 100h; cchDest
0x18003f361  mov     rcx, rsi; pszDest
0x18003f364  cmova   r8, rax; pszFormat
0x18003f368  call    StringCchPrintfA
0x18003f36d  test    bx, bx
0x18003f370  jnz     short loc_18003F380
0x18003f372  mov     rdx, rsi
0x18003f375  mov     rcx, rdi
0x18003f378  call    StrmPutStringEOL
0x18003f37d  movzx   ebx, ax
0x18003f380  mov     r9, [rsp+68h+arg_20]
0x18003f388  lea     r8, aCmapnameSDef; "/CMapName /%s def"
0x18003f38f  mov     edx, 100h; cchDest
0x18003f394  mov     rcx, rsi; pszDest
0x18003f397  call    StringCchPrintfA
0x18003f39c  test    bx, bx
0x18003f39f  jnz     short loc_18003F400
0x18003f3a1  mov     rdx, rsi
0x18003f3a4  mov     rcx, rdi
0x18003f3a7  call    StrmPutStringEOL
0x18003f3ac  movzx   ebx, ax
0x18003f3af  test    ax, ax
0x18003f3b2  jnz     short loc_18003F400
0x18003f3b4  lea     rdx, aWmode1Def; "/WMode 1 def"
0x18003f3bb  mov     rcx, rdi
0x18003f3be  call    StrmPutStringEOL
0x18003f3c3  movzx   ebx, ax
0x18003f3c6  test    ax, ax
0x18003f3c9  jnz     short loc_18003F400
0x18003f3cb  lea     rdx, a0Beginusematri; "0 beginusematrix [0 1 -1 0 0 0] endusem"...
0x18003f3d2  mov     rcx, rdi
0x18003f3d5  call    StrmPutStringEOL
0x18003f3da  movzx   ebx, ax
0x18003f3dd  test    ax, ax
0x18003f3e0  jnz     short loc_18003F400
0x18003f3e2  lea     rax, aWincharsetffff_0; "WinCharSetFFFF-V2"
0x18003f3e9  cmp     r14, rax
0x18003f3ec  jnz     short loc_18003F400
0x18003f3ee  lea     rdx, a2Beginusematri; "2 beginusematrix [0 1 -1 0 0 0] endusem"...
0x18003f3f5  mov     rcx, rdi
0x18003f3f8  call    StrmPutStringEOL
0x18003f3fd  movzx   ebx, ax
0x18003f400  test    r15w, r15w
0x18003f404  jz      loc_18003FA40
0x18003f40a  movzx   edx, word ptr [r12]
0x18003f40f  mov     r8d, r13d
0x18003f412  mov     r10d, 7F00h
0x18003f418  mov     r14d, r13d
0x18003f41b  cmp     dx, r10w
0x18003f41f  mov     r9d, 1
0x18003f425  setnbe  r8b
0x18003f429  setbe   r14b
0x18003f42d  mov     [rsp+68h+arg_0], r8d
0x18003f432  cmp     r13w, r15w
0x18003f436  jge     short loc_18003F464
0x18003f438  mov     ecx, r13d
0x18003f43b  movzx   eax, cx
0x18003f43e  cmp     dx, [r12+rax*4]
0x18003f443  jz      short loc_18003F45A
0x18003f445  movzx   edx, word ptr [r12+rax*4]
0x18003f44a  cmp     dx, r10w
0x18003f44e  jbe     short loc_18003F456
0x18003f450  add     r8w, r9w
0x18003f454  jmp     short loc_18003F45A
0x18003f456  add     r14w, r9w
0x18003f45a  add     cx, r9w
0x18003f45e  cmp     cx, r15w
0x18003f462  jl      short loc_18003F43B
0x18003f464  mov     [rsp+68h+arg_0], r8d
0x18003f469  test    bx, bx
0x18003f46c  jnz     short loc_18003F480
0x18003f46e  lea     rdx, a1Usefont; "1 usefont"
0x18003f475  mov     rcx, rdi
0x18003f478  call    StrmPutStringEOL
0x18003f47d  movzx   ebx, ax
0x18003f480  mov     eax, 64h ; 'd'
0x18003f485  mov     edx, 100h; cchDest
0x18003f48a  mov     rcx, rsi; pszDest
0x18003f48d  cmp     ax, r14w
0x18003f491  jge     short loc_18003F4A1
0x18003f493  lea     r8, a100Begincidran; "100 begincidrange"
0x18003f49a  call    StringCchPrintfA
0x18003f49f  jmp     short loc_18003F4B1
0x18003f4a1  movsx   r9d, r14w
0x18003f4a5  lea     r8, aDBegincidrange; "%d begincidrange"
0x18003f4ac  call    StringCchPrintfA
0x18003f4b1  movzx   r15d, word ptr [r12]
0x18003f4b6  test    bx, bx
0x18003f4b9  jnz     short loc_18003F51E
0x18003f4bb  mov     rdx, rsi
0x18003f4be  mov     rcx, rdi
0x18003f4c1  call    StrmPutStringEOL
0x18003f4c6  movzx   ebx, ax
0x18003f4c9  cmp     r13w, ax
0x18003f4cd  jnz     short loc_18003F4F3
0x18003f4cf  movzx   edx, r15w
0x18003f4d3  mov     rcx, rdi
0x18003f4d6  call    StrmPutWordAsciiHex
0x18003f4db  movzx   ebx, ax
0x18003f4de  cmp     r13w, ax
0x18003f4e2  jnz     short loc_18003F4F3
0x18003f4e4  movzx   edx, r15w
0x18003f4e8  mov     rcx, rdi
0x18003f4eb  call    StrmPutWordAsciiHex
0x18003f4f0  movzx   ebx, ax
0x18003f4f3  mov     r9d, r15d
0x18003f4f6  lea     r8, aU_1; "%u"
0x18003f4fd  mov     edx, 100h; cchDest
0x18003f502  mov     rcx, rsi; pszDest
0x18003f505  call    StringCchPrintfA
0x18003f50a  cmp     r13w, bx
0x18003f50e  jnz     short loc_18003F51E
0x18003f510  mov     rdx, rsi
0x18003f513  mov     rcx, rdi
0x18003f516  call    StrmPutStringEOL
0x18003f51b  movzx   ebx, ax
0x18003f51e  mov     r9d, 1
0x18003f524  movzx   r13d, r9w
0x18003f528  movzx   r12d, r9w
0x18003f52c  cmp     r9w, [rsp+68h+arg_10]
0x18003f535  jge     loc_18003F65D
0x18003f53b  mov     rcx, [rsp+68h+arg_8]
0x18003f540  movzx   eax, r12w
0x18003f544  movzx   ebp, word ptr [rcx+rax*4]
0x18003f548  mov     eax, 7F00h
0x18003f54d  cmp     bp, ax
0x18003f550  ja      loc_18003F656
0x18003f556  cmp     r15w, bp
0x18003f55a  jz      loc_18003F643
0x18003f560  add     r13w, r9w
0x18003f564  movzx   r15d, bp
0x18003f568  test    bx, bx
0x18003f56b  jnz     short loc_18003F5C2
0x18003f56d  movzx   edx, bp
0x18003f570  mov     rcx, rdi
0x18003f573  call    StrmPutWordAsciiHex
0x18003f578  movzx   ebx, ax
0x18003f57b  xor     eax, eax
0x18003f57d  cmp     ax, bx
0x18003f580  jnz     short loc_18003F590
0x18003f582  movzx   edx, bp
0x18003f585  mov     rcx, rdi
0x18003f588  call    StrmPutWordAsciiHex
0x18003f58d  movzx   ebx, ax
0x18003f590  mov     r9d, ebp
0x18003f593  lea     r8, aU_1; "%u"
0x18003f59a  mov     edx, 100h; cchDest
0x18003f59f  mov     rcx, rsi; pszDest
0x18003f5a2  call    StringCchPrintfA
0x18003f5a7  xor     ebp, ebp
0x18003f5a9  cmp     bp, bx
0x18003f5ac  jnz     short loc_18003F5BC
0x18003f5ae  mov     rdx, rsi
0x18003f5b1  mov     rcx, rdi
0x18003f5b4  call    StrmPutStringEOL
0x18003f5b9  movzx   ebx, ax
0x18003f5bc  mov     r9d, 1
0x18003f5c2  movsx   r8d, r13w
0x18003f5c6  mov     eax, 51EB851Fh
0x18003f5cb  imul    r8d
0x18003f5ce  sar     edx, 5
0x18003f5d1  mov     eax, edx
0x18003f5d3  shr     eax, 1Fh
0x18003f5d6  add     edx, eax
0x18003f5d8  imul    ecx, edx, 64h ; 'd'
0x18003f5db  cmp     r8d, ecx
0x18003f5de  jnz     short loc_18003F63E
0x18003f5e0  movsx   r9d, r14w
0x18003f5e4  sub     r9d, r8d
0x18003f5e7  cmp     r9d, 64h ; 'd'
0x18003f5eb  jle     short loc_18003F5F6
0x18003f5ed  lea     r8, aEndcidrange100; "endcidrange\n100 begincidrange"
0x18003f5f4  jmp     short loc_18003F618
0x18003f5f6  test    r9d, r9d
0x18003f5f9  jle     short loc_18003F611
0x18003f5fb  lea     r8, aEndcidrangeDBe; "endcidrange\n%d begincidrange"
0x18003f602  mov     edx, 100h; cchDest
0x18003f607  mov     rcx, rsi; pszDest
0x18003f60a  call    StringCchPrintfA
0x18003f60f  jmp     short loc_18003F625
0x18003f611  lea     r8, asc_180062A20; " "
0x18003f618  mov     edx, 100h; cchDest
0x18003f61d  mov     rcx, rsi; pszDest
0x18003f620  call    StringCchPrintfA
0x18003f625  test    bx, bx
0x18003f628  jnz     short loc_18003F638
0x18003f62a  mov     rdx, rsi
0x18003f62d  mov     rcx, rdi
0x18003f630  call    StrmPutStringEOL
0x18003f635  movzx   ebx, ax
0x18003f638  mov     r9d, 1
0x18003f63e  mov     rcx, [rsp+68h+arg_8]
0x18003f643  add     r12w, r9w
0x18003f647  cmp     r12w, [rsp+68h+arg_10]
0x18003f650  jl      loc_18003F540
0x18003f656  mov     ebp, [rsp+68h+arg_28]
0x18003f65d  xor     r13d, r13d
0x18003f660  test    bx, bx
0x18003f663  jnz     short loc_18003F677
0x18003f665  lea     rdx, aEndcidrange; "endcidrange"
0x18003f66c  mov     rcx, rdi
0x18003f66f  call    StrmPutStringEOL
0x18003f674  movzx   ebx, ax
0x18003f677  cmp     ebp, 7F00h
0x18003f67d  jbe     loc_18003FA40
0x18003f683  mov     r12, [rsp+68h+arg_18]
0x18003f68b  lea     rcx, aWincharsetffff_0; "WinCharSetFFFF-V2"
0x18003f692  cmp     r12, rcx
0x18003f695  jnz     loc_18003F7A8
0x18003f69b  test    bx, bx
0x18003f69e  jnz     short loc_18003F6B2
0x18003f6a0  lea     rdx, a2Usefont; "2 usefont"
0x18003f6a7  mov     rcx, rdi
0x18003f6aa  call    StrmPutStringEOL
0x18003f6af  movzx   ebx, ax
0x18003f6b2  lea     ecx, [rbp-7E02h]
0x18003f6b8  mov     eax, 80808081h
0x18003f6bd  imul    ecx
0x18003f6bf  mov     r15d, 100h
0x18003f6c5  lea     r8, aDBegincidrange; "%d begincidrange"
0x18003f6cc  lea     r12d, [rcx+rdx]
0x18003f6d0  mov     edx, r15d; cchDest
0x18003f6d3  sar     r12d, 7
0x18003f6d7  mov     rcx, rsi; pszDest
0x18003f6da  mov     eax, r12d
0x18003f6dd  shr     eax, 1Fh
0x18003f6e0  add     r12d, eax
0x18003f6e3  movsx   r9d, r12w
0x18003f6e7  call    StringCchPrintfA
0x18003f6ec  test    bx, bx
0x18003f6ef  jnz     short loc_18003F6FF
0x18003f6f1  mov     rdx, rsi
0x18003f6f4  mov     rcx, rdi
  ... truncated ...
```

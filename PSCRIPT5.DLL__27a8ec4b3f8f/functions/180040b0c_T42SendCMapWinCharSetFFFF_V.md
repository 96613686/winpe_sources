# T42SendCMapWinCharSetFFFF_V

- ea: `0x180040b0c`
- end: `0x180041320`
- name: `T42SendCMapWinCharSetFFFF_V`
- size: `2068`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int16, const char *, const char *, unsigned int, __int64, STRSAFE_LPSTR pszDest)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003f09c`

## callees

- `0x180005670`
- `0x18003a1f4`
- `0x18003a25c`
- `0x180040b0c`

## string_xrefs

- `0x180040b8f`: `/Registry (%s) def`

## pseudocode

```c
__int64 __fastcall T42SendCMapWinCharSetFFFF_V(
        __int64 a1,
        unsigned __int16 *a2,
        __int16 a3,
        char *a4,
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
      v11 = StrmPutWordAsciiHex(a7, v19);
      if ( !v11 )
        v11 = StrmPutWordAsciiHex(a7, v19);
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
          v11 = StrmPutWordAsciiHex(a7, v23);
          if ( !v11 )
            v11 = StrmPutWordAsciiHex(a7, v23);
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
  v25 = a4;
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
        v11 = StrmPutWordAsciiHex(a7, v28 + 32512);
        if ( !v11 )
          v11 = StrmPutWordAsciiHex(a7, v28 + 0x7FFF);
      }
      StringCchPrintfA(pszDest, 0x100u, "%u", v28);
      if ( !v11 )
        v11 = StrmPutStringEOL(a7, pszDest);
    }
    if ( !v11 )
      v11 = StrmPutStringEOL(a7, "endcidrange");
    v25 = a4;
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
          v11 = StrmPutWordAsciiHex(a7, v34);
          if ( !v11 )
            v11 = StrmPutWordAsciiHex(a7, v34);
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
0x180040b0c  mov     rax, rsp
0x180040b0f  mov     [rax+20h], r9
0x180040b13  mov     [rax+18h], r8w
0x180040b18  mov     [rax+10h], rdx
0x180040b1c  mov     [rax+8], rcx
0x180040b20  push    rbx
0x180040b21  push    rbp
0x180040b22  push    rsi
0x180040b23  push    rdi
0x180040b24  push    r12
0x180040b26  push    r13
0x180040b28  push    r14
0x180040b2a  push    r15
0x180040b2c  sub     rsp, 28h
0x180040b30  mov     rsi, [rsp+68h+pszDest]
0x180040b38  movzx   r15d, r8w
0x180040b3c  mov     r12, rdx
0x180040b3f  lea     r8, aCidinitProcset; "/CIDInit /ProcSet findresource begin 12"...
0x180040b46  mov     ebp, 100h
0x180040b4b  mov     rcx, rsi; pszDest
0x180040b4e  mov     edx, ebp; cchDest
0x180040b50  mov     r14, r9
0x180040b53  call    StringCchPrintfA
0x180040b58  mov     rdi, [rsp+68h+arg_30]
0x180040b60  mov     rdx, rsi
0x180040b63  mov     rcx, rdi
0x180040b66  call    StrmPutStringEOL
0x180040b6b  xor     r13d, r13d
0x180040b6e  movzx   ebx, ax
0x180040b71  test    ax, ax
0x180040b74  jnz     short loc_180040B88
0x180040b76  lea     rdx, aCidsysteminfo3_0; "/CIDSystemInfo [3 dict dup begin"
0x180040b7d  mov     rcx, rdi
0x180040b80  call    StrmPutStringEOL
0x180040b85  movzx   ebx, ax
0x180040b88  lea     r9, [r14+24h]
0x180040b8c  mov     rdx, rbp; cchDest
0x180040b8f  lea     r8, aRegistrySDef; "/Registry (%s) def"
0x180040b96  mov     rcx, rsi; pszDest
0x180040b99  call    StringCchPrintfA
0x180040b9e  test    bx, bx
0x180040ba1  jnz     short loc_180040BB1
0x180040ba3  mov     rdx, rsi
0x180040ba6  mov     rcx, rdi
0x180040ba9  call    StrmPutStringEOL
0x180040bae  movzx   ebx, ax
0x180040bb1  mov     r9, [rsp+68h+arg_20]
0x180040bb9  lea     r8, aOrderingSDef; "/Ordering (%s) def"
0x180040bc0  mov     rdx, rbp; cchDest
0x180040bc3  mov     rcx, rsi; pszDest
0x180040bc6  call    StringCchPrintfA
0x180040bcb  test    bx, bx
0x180040bce  jnz     short loc_180040BF5
0x180040bd0  mov     rdx, rsi
0x180040bd3  mov     rcx, rdi
0x180040bd6  call    StrmPutStringEOL
0x180040bdb  movzx   ebx, ax
0x180040bde  test    ax, ax
0x180040be1  jnz     short loc_180040BF5
0x180040be3  lea     rdx, aSupplement0Def; "/Supplement 0 def"
0x180040bea  mov     rcx, rdi
0x180040bed  call    StrmPutStringEOL
0x180040bf2  movzx   ebx, ax
0x180040bf5  mov     ebp, [rsp+68h+arg_28]
0x180040bfc  lea     rax, aEndDupDupDupDe; "end dup dup dup] def"
0x180040c03  cmp     ebp, 7F00h
0x180040c09  lea     r8, aEndDupDef; "end dup] def"
0x180040c10  mov     edx, 100h; cchDest
0x180040c15  mov     rcx, rsi; pszDest
0x180040c18  cmova   r8, rax; pszFormat
0x180040c1c  call    StringCchPrintfA
0x180040c21  test    bx, bx
0x180040c24  jnz     short loc_180040C34
0x180040c26  mov     rdx, rsi
0x180040c29  mov     rcx, rdi
0x180040c2c  call    StrmPutStringEOL
0x180040c31  movzx   ebx, ax
0x180040c34  mov     r9, [rsp+68h+arg_20]
0x180040c3c  lea     r8, aCmapnameSDef; "/CMapName /%s def"
0x180040c43  mov     edx, 100h; cchDest
0x180040c48  mov     rcx, rsi; pszDest
0x180040c4b  call    StringCchPrintfA
0x180040c50  test    bx, bx
0x180040c53  jnz     short loc_180040CB4
0x180040c55  mov     rdx, rsi
0x180040c58  mov     rcx, rdi
0x180040c5b  call    StrmPutStringEOL
0x180040c60  movzx   ebx, ax
0x180040c63  test    ax, ax
0x180040c66  jnz     short loc_180040CB4
0x180040c68  lea     rdx, aWmode1Def; "/WMode 1 def"
0x180040c6f  mov     rcx, rdi
0x180040c72  call    StrmPutStringEOL
0x180040c77  movzx   ebx, ax
0x180040c7a  test    ax, ax
0x180040c7d  jnz     short loc_180040CB4
0x180040c7f  lea     rdx, a0Beginusematri; "0 beginusematrix [0 1 -1 0 0 0] endusem"...
0x180040c86  mov     rcx, rdi
0x180040c89  call    StrmPutStringEOL
0x180040c8e  movzx   ebx, ax
0x180040c91  test    ax, ax
0x180040c94  jnz     short loc_180040CB4
0x180040c96  lea     rax, aWincharsetffff_0; "WinCharSetFFFF-V2"
0x180040c9d  cmp     r14, rax
0x180040ca0  jnz     short loc_180040CB4
0x180040ca2  lea     rdx, a2Beginusematri; "2 beginusematrix [0 1 -1 0 0 0] endusem"...
0x180040ca9  mov     rcx, rdi
0x180040cac  call    StrmPutStringEOL
0x180040cb1  movzx   ebx, ax
0x180040cb4  test    r15w, r15w
0x180040cb8  jz      loc_1800412F4
0x180040cbe  movzx   edx, word ptr [r12]
0x180040cc3  mov     r8d, r13d
0x180040cc6  mov     r10d, 7F00h
0x180040ccc  mov     r14d, r13d
0x180040ccf  cmp     dx, r10w
0x180040cd3  mov     r9d, 1
0x180040cd9  setnbe  r8b
0x180040cdd  setbe   r14b
0x180040ce1  mov     [rsp+68h+arg_0], r8d
0x180040ce6  cmp     r13w, r15w
0x180040cea  jge     short loc_180040D18
0x180040cec  mov     ecx, r13d
0x180040cef  movzx   eax, cx
0x180040cf2  cmp     dx, [r12+rax*4]
0x180040cf7  jz      short loc_180040D0E
0x180040cf9  movzx   edx, word ptr [r12+rax*4]
0x180040cfe  cmp     dx, r10w
0x180040d02  jbe     short loc_180040D0A
0x180040d04  add     r8w, r9w
0x180040d08  jmp     short loc_180040D0E
0x180040d0a  add     r14w, r9w
0x180040d0e  add     cx, r9w
0x180040d12  cmp     cx, r15w
0x180040d16  jl      short loc_180040CEF
0x180040d18  mov     [rsp+68h+arg_0], r8d
0x180040d1d  test    bx, bx
0x180040d20  jnz     short loc_180040D34
0x180040d22  lea     rdx, a1Usefont; "1 usefont"
0x180040d29  mov     rcx, rdi
0x180040d2c  call    StrmPutStringEOL
0x180040d31  movzx   ebx, ax
0x180040d34  mov     eax, 64h ; 'd'
0x180040d39  mov     edx, 100h; cchDest
0x180040d3e  mov     rcx, rsi; pszDest
0x180040d41  cmp     ax, r14w
0x180040d45  jge     short loc_180040D55
0x180040d47  lea     r8, a100Begincidran; "100 begincidrange"
0x180040d4e  call    StringCchPrintfA
0x180040d53  jmp     short loc_180040D65
0x180040d55  movsx   r9d, r14w
0x180040d59  lea     r8, aDBegincidrange; "%d begincidrange"
0x180040d60  call    StringCchPrintfA
0x180040d65  movzx   r15d, word ptr [r12]
0x180040d6a  test    bx, bx
0x180040d6d  jnz     short loc_180040DD2
0x180040d6f  mov     rdx, rsi
0x180040d72  mov     rcx, rdi
0x180040d75  call    StrmPutStringEOL
0x180040d7a  movzx   ebx, ax
0x180040d7d  cmp     r13w, ax
0x180040d81  jnz     short loc_180040DA7
0x180040d83  movzx   edx, r15w
0x180040d87  mov     rcx, rdi
0x180040d8a  call    StrmPutWordAsciiHex
0x180040d8f  movzx   ebx, ax
0x180040d92  cmp     r13w, ax
0x180040d96  jnz     short loc_180040DA7
0x180040d98  movzx   edx, r15w
0x180040d9c  mov     rcx, rdi
0x180040d9f  call    StrmPutWordAsciiHex
0x180040da4  movzx   ebx, ax
0x180040da7  mov     r9d, r15d
0x180040daa  lea     r8, aU_1; "%u"
0x180040db1  mov     edx, 100h; cchDest
0x180040db6  mov     rcx, rsi; pszDest
0x180040db9  call    StringCchPrintfA
0x180040dbe  cmp     r13w, bx
0x180040dc2  jnz     short loc_180040DD2
0x180040dc4  mov     rdx, rsi
0x180040dc7  mov     rcx, rdi
0x180040dca  call    StrmPutStringEOL
0x180040dcf  movzx   ebx, ax
0x180040dd2  mov     r9d, 1
0x180040dd8  movzx   r13d, r9w
0x180040ddc  movzx   r12d, r9w
0x180040de0  cmp     r9w, [rsp+68h+arg_10]
0x180040de9  jge     loc_180040F11
0x180040def  mov     rcx, [rsp+68h+arg_8]
0x180040df4  movzx   eax, r12w
0x180040df8  movzx   ebp, word ptr [rcx+rax*4]
0x180040dfc  mov     eax, 7F00h
0x180040e01  cmp     bp, ax
0x180040e04  ja      loc_180040F0A
0x180040e0a  cmp     r15w, bp
0x180040e0e  jz      loc_180040EF7
0x180040e14  add     r13w, r9w
0x180040e18  movzx   r15d, bp
0x180040e1c  test    bx, bx
0x180040e1f  jnz     short loc_180040E76
0x180040e21  movzx   edx, bp
0x180040e24  mov     rcx, rdi
0x180040e27  call    StrmPutWordAsciiHex
0x180040e2c  movzx   ebx, ax
0x180040e2f  xor     eax, eax
0x180040e31  cmp     ax, bx
0x180040e34  jnz     short loc_180040E44
0x180040e36  movzx   edx, bp
0x180040e39  mov     rcx, rdi
0x180040e3c  call    StrmPutWordAsciiHex
0x180040e41  movzx   ebx, ax
0x180040e44  mov     r9d, ebp
0x180040e47  lea     r8, aU_1; "%u"
0x180040e4e  mov     edx, 100h; cchDest
0x180040e53  mov     rcx, rsi; pszDest
0x180040e56  call    StringCchPrintfA
0x180040e5b  xor     ebp, ebp
0x180040e5d  cmp     bp, bx
0x180040e60  jnz     short loc_180040E70
0x180040e62  mov     rdx, rsi
0x180040e65  mov     rcx, rdi
0x180040e68  call    StrmPutStringEOL
0x180040e6d  movzx   ebx, ax
0x180040e70  mov     r9d, 1
0x180040e76  movsx   r8d, r13w
0x180040e7a  mov     eax, 51EB851Fh
0x180040e7f  imul    r8d
0x180040e82  sar     edx, 5
0x180040e85  mov     eax, edx
0x180040e87  shr     eax, 1Fh
0x180040e8a  add     edx, eax
0x180040e8c  imul    ecx, edx, 64h ; 'd'
0x180040e8f  cmp     r8d, ecx
0x180040e92  jnz     short loc_180040EF2
0x180040e94  movsx   r9d, r14w
0x180040e98  sub     r9d, r8d
0x180040e9b  cmp     r9d, 64h ; 'd'
0x180040e9f  jle     short loc_180040EAA
0x180040ea1  lea     r8, aEndcidrange100; "endcidrange\n100 begincidrange"
0x180040ea8  jmp     short loc_180040ECC
0x180040eaa  test    r9d, r9d
0x180040ead  jle     short loc_180040EC5
0x180040eaf  lea     r8, aEndcidrangeDBe; "endcidrange\n%d begincidrange"
0x180040eb6  mov     edx, 100h; cchDest
0x180040ebb  mov     rcx, rsi; pszDest
0x180040ebe  call    StringCchPrintfA
0x180040ec3  jmp     short loc_180040ED9
0x180040ec5  lea     r8, asc_180064A10; " "
0x180040ecc  mov     edx, 100h; cchDest
0x180040ed1  mov     rcx, rsi; pszDest
0x180040ed4  call    StringCchPrintfA
0x180040ed9  test    bx, bx
0x180040edc  jnz     short loc_180040EEC
0x180040ede  mov     rdx, rsi
0x180040ee1  mov     rcx, rdi
0x180040ee4  call    StrmPutStringEOL
0x180040ee9  movzx   ebx, ax
0x180040eec  mov     r9d, 1
0x180040ef2  mov     rcx, [rsp+68h+arg_8]
0x180040ef7  add     r12w, r9w
0x180040efb  cmp     r12w, [rsp+68h+arg_10]
0x180040f04  jl      loc_180040DF4
0x180040f0a  mov     ebp, [rsp+68h+arg_28]
0x180040f11  xor     r13d, r13d
0x180040f14  test    bx, bx
0x180040f17  jnz     short loc_180040F2B
0x180040f19  lea     rdx, aEndcidrange; "endcidrange"
0x180040f20  mov     rcx, rdi
0x180040f23  call    StrmPutStringEOL
0x180040f28  movzx   ebx, ax
0x180040f2b  cmp     ebp, 7F00h
0x180040f31  jbe     loc_1800412F4
0x180040f37  mov     r12, [rsp+68h+arg_18]
0x180040f3f  lea     rcx, aWincharsetffff_0; "WinCharSetFFFF-V2"
0x180040f46  cmp     r12, rcx
0x180040f49  jnz     loc_18004105C
0x180040f4f  test    bx, bx
0x180040f52  jnz     short loc_180040F66
0x180040f54  lea     rdx, a2Usefont; "2 usefont"
0x180040f5b  mov     rcx, rdi
0x180040f5e  call    StrmPutStringEOL
0x180040f63  movzx   ebx, ax
0x180040f66  lea     ecx, [rbp-7E02h]
0x180040f6c  mov     eax, 80808081h
0x180040f71  imul    ecx
0x180040f73  mov     r15d, 100h
0x180040f79  lea     r8, aDBegincidrange; "%d begincidrange"
0x180040f80  lea     r12d, [rcx+rdx]
0x180040f84  mov     edx, r15d; cchDest
0x180040f87  sar     r12d, 7
0x180040f8b  mov     rcx, rsi; pszDest
0x180040f8e  mov     eax, r12d
0x180040f91  shr     eax, 1Fh
0x180040f94  add     r12d, eax
0x180040f97  movsx   r9d, r12w
0x180040f9b  call    StringCchPrintfA
0x180040fa0  test    bx, bx
0x180040fa3  jnz     short loc_180040FB3
0x180040fa5  mov     rdx, rsi
0x180040fa8  mov     rcx, rdi
  ... truncated ...
```

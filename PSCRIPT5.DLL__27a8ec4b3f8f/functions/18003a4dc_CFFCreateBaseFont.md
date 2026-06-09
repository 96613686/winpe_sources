# CFFCreateBaseFont

- ea: `0x18003a4dc`
- end: `0x18003aa9d`
- name: `CFFCreateBaseFont`
- size: `1473`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180038370`
- `0x18003ab30`

## callees

- `0x180001f20`
- `0x180005670`
- `0x180039e10`
- `0x18003a1f4`
- `0x18003a4dc`
- `0x180049828`
- `0x18005f010`

## string_xrefs

- `0x18003a8d6`: `[/%s%s] composefont pop`
- `0x18003a85f`: `[/%s] composefont pop`
- `0x18003a9a0`: ` /90msp-RKSJ-H [/%s%s] composefont pop`
- `0x18003a9bc`: ` /90msp-RKSJ-H [/%s%s] composefont pop`
- `0x18003a990`: ` /90msp-RKSJ-H [/%s] composefont pop`
- `0x18003aa3c`: ` /90msp-RKSJ-QV [/%s%s dup dup] composefont pop`
- `0x18003aa00`: ` /90msp-RKSJ-QV [/%s dup dup] composefont pop`

## pseudocode

```c
__int64 __fastcall CFFCreateBaseFont(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v8; // r12
  __int64 v9; // rdx
  int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int8 (__fastcall *v13)(__int64, __int64, _QWORD); // rax
  unsigned __int16 v14; // di
  __int64 v15; // r9
  int v16; // eax
  const char *v17; // r9
  __int64 v18; // r15
  char *v19; // rdx
  unsigned __int16 v20; // ax
  const char *v21; // r8
  const char *v22; // r9
  unsigned __int16 v23; // si
  __int64 v24; // r8
  __int64 v25; // rax
  const char *v26; // r9
  const char *v27; // rax
  const char *v28; // r8
  const char *v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  __int16 v31; // [rsp+40h] [rbp-C0h]
  char pszDest[512]; // [rsp+50h] [rbp-B0h] BYREF

  if ( *(int *)(a1 + 8) < 1 )
    return 4;
  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
  if ( v8 && *(_QWORD *)v8 )
  {
    v9 = *(_QWORD *)(a1 + 40);
    v30 = *(_QWORD *)(v9 + 168);
    v10 = *(_DWORD *)(a1 + 4) - 4;
    if ( v10 )
    {
      if ( (unsigned int)(v10 - 1) > 1 )
        goto LABEL_11;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(v9 + 160) + 8LL))(
              *(_QWORD *)(v9 + 160),
              4,
              0) )
        return 13;
      if ( !*(_BYTE *)(a1 + 152) )
      {
LABEL_11:
        v14 = 0;
        if ( *(_DWORD *)(a1 + 8) != 2 )
        {
          *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) = *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) & 0xFF7F
                                                  | ((*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _WORD))(*(_QWORD *)(a1 + 40) + 88LL))(
                                                       *(_QWORD *)(a1 + 16),
                                                       2020896118,
                                                       0,
                                                       0,
                                                       0,
                                                       *(_WORD *)(v8 + 64)) != 0
                                                   ? 0x80
                                                   : 0);
          if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
          {
            if ( !a2 )
              return 18;
            LODWORD(v15) = 0;
            if ( *(_QWORD *)(a2 + 16) )
              v15 = *(_QWORD *)(a2 + 24);
            v16 = XCF_DownloadFontIncr(*(_QWORD *)v8, *(_DWORD *)a2, *(_QWORD *)(a2 + 8), v15, a3);
            v14 = v16 != 0 ? 0x12 : 0;
            if ( v16 )
              return v14;
          }
        }
        if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 && *(_DWORD *)(a1 + 8) != 2 )
        {
          v17 = "font";
          if ( *(_DWORD *)(a1 + 4) != 4 )
            v17 = "CIDFont";
          StringCchPrintfA(pszDest, 0x200u, "\n%%%%IncludeResource: %s %s", v17, a4);
          v18 = v30;
          v14 = StrmPutStringEOL(v30, pszDest);
          if ( v14 )
            return v14;
        }
        else
        {
          v18 = v30;
        }
        if ( *(_DWORD *)(a1 + 4) == 5 )
        {
          v14 = StrmPutStringEOL(v18, "CMAP-WinCharSetFFFF-H");
          if ( !v14 )
          {
            if ( !*(_BYTE *)(a1 + 152) )
              goto LABEL_44;
            v19 = "CMAP-90msp-RKSJ-H";
LABEL_42:
            v20 = StrmPutStringEOL(v18, v19);
            if ( v20 )
              return v20;
LABEL_44:
            v21 = "/%s /WinCharSetFFFF-H";
            v31 = *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) & 0x80;
            if ( *(_DWORD *)(a1 + 4) != 5 )
              v21 = "/%s /WinCharSetFFFF-V";
            StringCchPrintfA(pszDest, 0x200u, v21, *(_QWORD *)(a1 + 56));
            v14 = StrmPutStringEOL(v18, pszDest);
            if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
            {
              if ( v31 )
              {
                if ( *(_DWORD *)(a1 + 8) == 2 )
                  StringCchPrintfA(pszDest, 0x200u, "[/%s%s] composefont pop", a4, "-hf");
                else
                  StringCchPrintfA(pszDest, 0x200u, "/%s%s %s /%s hfMkCIDFont", a4, "-hf", "{pop 4 index add}bind", a4);
              }
              else
              {
                StringCchPrintfA(pszDest, 0x200u, "[/%s] composefont pop", a4);
              }
            }
            else
            {
              if ( *(_DWORD *)(a1 + 136) )
              {
                v22 = "ADBCFF+";
              }
              else
              {
                v22 = "ADBCFA+";
                if ( *(_DWORD *)(a1 + 4) != 5 )
                  v22 = "ADBCFB+";
              }
              StringCchPrintfA(pszDest, 0x200u, "[/%s%s] composefont pop", v22, (const char *)(v8 + 92));
            }
            v23 = 0;
            if ( v14 )
              return v14;
            v14 = StrmPutStringEOL(v18, pszDest);
            if ( v14 )
              return v14;
            if ( !*(_BYTE *)(a1 + 152) )
              goto LABEL_87;
            StringCchPrintfA(pszDest, 0x200u, "/%sQ", *(const char **)(a1 + 56));
            if ( pszDest[0] )
            {
              v24 = -1;
              do
                ++v24;
              while ( pszDest[v24] );
              v23 = StrmPutBytes(v18, (__int64)pszDest, v24, 1);
            }
            v14 = v23;
            v25 = *(_QWORD *)(a1 + 160);
            if ( *(_DWORD *)(a1 + 4) == 5 )
            {
              if ( !v25 || (*(_BYTE *)(a1 + 28) & 8) == 0 )
              {
                v29 = (const char *)(v8 + 92);
                v28 = " /90msp-RKSJ-H [/%s%s] composefont pop";
                if ( *(_DWORD *)(a1 + 136) )
                  v26 = "ADBCFF+";
                else
                  v26 = "ADBCFA+";
                goto LABEL_84;
              }
              v26 = a4;
              if ( !v31 )
              {
                StringCchPrintfA(pszDest, 0x200u, " /90msp-RKSJ-H [/%s] composefont pop", a4);
                goto LABEL_85;
              }
              v27 = "-hf";
              v28 = " /90msp-RKSJ-H [/%s%s] composefont pop";
            }
            else
            {
              if ( v25 && (*(_BYTE *)(a1 + 28) & 8) != 0 )
              {
                v26 = a4;
                if ( !v31 )
                {
                  StringCchPrintfA(pszDest, 0x200u, " /90msp-RKSJ-QV [/%s dup dup] composefont pop", a4);
                  goto LABEL_85;
                }
                v27 = "-hf";
              }
              else
              {
                v27 = (const char *)(v8 + 92);
                v26 = "ADBCFB+";
                if ( *(_DWORD *)(a1 + 136) )
                  v26 = "ADBCFF+";
              }
              v28 = " /90msp-RKSJ-QV [/%s%s dup dup] composefont pop";
            }
            v29 = v27;
LABEL_84:
            StringCchPrintfA(pszDest, 0x200u, v28, v26, v29);
LABEL_85:
            if ( v23 )
              return v14;
            goto LABEL_86;
          }
        }
        else
        {
          if ( *(_DWORD *)(a1 + 4) != 6 )
          {
            if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 )
              goto LABEL_87;
            StringCchPrintfA(pszDest, 0x200u, "/%s false /%s hfRedefFont", *(const char **)(a1 + 56), a4);
LABEL_86:
            v14 = StrmPutStringEOL(v18, pszDest);
            if ( v14 )
              return v14;
LABEL_87:
            *(_DWORD *)(a1 + 8) = 4;
            return v14;
          }
          v14 = StrmPutStringEOL(v18, "CMAP-WinCharSetFFFF-V");
          if ( !v14 )
          {
            if ( !*(_BYTE *)(a1 + 152) )
              goto LABEL_44;
            v19 = "CMAP-90msp-RKSJ-H CMAP-90msp-RKSJ-QV";
            goto LABEL_42;
          }
        }
        return v14;
      }
      v11 = 5;
      v12 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 160LL);
      v13 = *(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD))(v12 + 8);
    }
    else
    {
      if ( *(int *)(v9 + 148) > 51 )
        goto LABEL_11;
      v12 = *(_QWORD *)(v9 + 160);
      v13 = *(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD))(v12 + 8);
      if ( !v13 )
        return 13;
      v11 = 2;
    }
    if ( v13(v12, v11, 0) )
      goto LABEL_11;
    return 13;
  }
  return 2;
}

```

## disassembly

```asm
0x18003a4dc  push    rbp
0x18003a4de  push    rbx
0x18003a4df  push    rsi
0x18003a4e0  push    rdi
0x18003a4e1  push    r12
0x18003a4e3  push    r13
0x18003a4e5  push    r14
0x18003a4e7  push    r15
0x18003a4e9  lea     rbp, [rsp-168h]
0x18003a4f1  sub     rsp, 268h
0x18003a4f8  mov     rax, cs:__security_cookie
0x18003a4ff  xor     rax, rsp
0x18003a502  mov     [rbp+1A0h+var_50], rax
0x18003a509  cmp     dword ptr [rcx+8], 1
0x18003a50d  mov     r14, r9
0x18003a510  mov     [rsp+2A0h+var_258], r8
0x18003a515  mov     r15, rdx
0x18003a518  mov     rbx, rcx
0x18003a51b  jge     short loc_18003A527
0x18003a51d  mov     eax, 4
0x18003a522  jmp     loc_18003AA79
0x18003a527  mov     rax, [rcx+30h]
0x18003a52b  xor     r8d, r8d
0x18003a52e  mov     r12, [rax+8]
0x18003a532  test    r12, r12
0x18003a535  jz      loc_18003AA74
0x18003a53b  cmp     [r12], r8
0x18003a53f  jz      loc_18003AA74
0x18003a545  mov     rdx, [rcx+28h]
0x18003a549  lea     r13d, [r8+4]
0x18003a54d  mov     ecx, [rcx+4]
0x18003a550  lea     esi, [r8+2]
0x18003a554  mov     rax, [rdx+0A8h]
0x18003a55b  mov     [rsp+2A0h+var_260], rax
0x18003a560  sub     ecx, r13d
0x18003a563  jz      loc_18003A6EE
0x18003a569  sub     ecx, 1
0x18003a56c  jz      short loc_18003A573
0x18003a56e  cmp     ecx, 1
0x18003a571  jnz     short loc_18003A5BD
0x18003a573  mov     rcx, [rdx+0A0h]
0x18003a57a  mov     edx, r13d
0x18003a57d  mov     rax, [rcx+8]
0x18003a581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a586  xor     r8d, r8d
0x18003a589  test    al, al
0x18003a58b  jz      loc_18003A712
0x18003a591  cmp     [rbx+98h], r8b
0x18003a598  jz      short loc_18003A5BD
0x18003a59a  mov     rax, [rbx+28h]
0x18003a59e  lea     edx, [r8+5]
0x18003a5a2  mov     rcx, [rax+0A0h]
0x18003a5a9  mov     rax, [rcx+8]
0x18003a5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5b2  xor     r8d, r8d
0x18003a5b5  test    al, al
0x18003a5b7  jz      loc_18003A712
0x18003a5bd  mov     edi, r8d
0x18003a5c0  cmp     [rbx+8], esi
0x18003a5c3  jz      loc_18003A679
0x18003a5c9  movzx   ecx, word ptr [r12+40h]
0x18003a5cf  xor     r9d, r9d
0x18003a5d2  mov     rax, [rbx+28h]
0x18003a5d6  mov     edx, 78746D76h
0x18003a5db  mov     word ptr [rsp+2A0h+var_278], cx
0x18003a5e0  mov     rcx, [rbx+10h]
0x18003a5e4  mov     dword ptr [rsp+2A0h+var_280], r8d
0x18003a5e9  xor     r8d, r8d
0x18003a5ec  mov     rax, [rax+58h]
0x18003a5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5f5  mov     rdx, [rbx+30h]
0x18003a5f9  neg     eax
0x18003a5fb  mov     eax, 80h
0x18003a600  mov     r8d, 0FF7Fh
0x18003a606  sbb     cx, cx
0x18003a609  and     cx, ax
0x18003a60c  movzx   eax, word ptr [rdx+44h]
0x18003a610  and     ax, r8w
0x18003a614  xor     r8d, r8d
0x18003a617  or      cx, ax
0x18003a61a  mov     [rdx+44h], cx
0x18003a61e  cmp     [rbx+0A0h], r8
0x18003a625  jz      short loc_18003A62D
0x18003a627  test    byte ptr [rbx+1Ch], 8
0x18003a62b  jnz     short loc_18003A679
0x18003a62d  test    r15, r15
0x18003a630  jz      loc_18003A71C
0x18003a636  mov     r9, r8
0x18003a639  cmp     [r15+10h], r8
0x18003a63d  jz      short loc_18003A643
0x18003a63f  mov     r9, [r15+18h]
0x18003a643  mov     rax, [rsp+2A0h+var_258]
0x18003a648  mov     r8, [r15+8]
0x18003a64c  mov     edx, [r15]
0x18003a64f  mov     rcx, [r12]
0x18003a653  mov     [rsp+2A0h+var_280], rax
0x18003a658  call    XCF_DownloadFontIncr
0x18003a65d  xor     r8d, r8d
0x18003a660  mov     ecx, r8d
0x18003a663  sub     ecx, eax
0x18003a665  neg     ecx
0x18003a667  lea     edi, [r8+12h]
0x18003a66b  sbb     dx, dx
0x18003a66e  and     di, dx
0x18003a671  test    eax, eax
0x18003a673  jnz     loc_18003AA6F
0x18003a679  cmp     [rbx+0A0h], r8
0x18003a680  jz      loc_18003A726
0x18003a686  test    byte ptr [rbx+1Ch], 8
0x18003a68a  jz      loc_18003A726
0x18003a690  cmp     [rbx+8], esi
0x18003a693  jz      loc_18003A726
0x18003a699  cmp     [rbx+4], r13d
0x18003a69d  lea     rax, aCidfont_0; "CIDFont"
0x18003a6a4  lea     r9, aFont_1; "font"
0x18003a6ab  mov     [rsp+2A0h+var_280], r14
0x18003a6b0  cmovnz  r9, rax
0x18003a6b4  lea     r8, aIncluderesourc_2; "\n%%%%IncludeResource: %s %s"
0x18003a6bb  mov     edx, 200h; cchDest
0x18003a6c0  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003a6c5  call    StringCchPrintfA
0x18003a6ca  mov     r15, [rsp+2A0h+var_260]
0x18003a6cf  lea     rdx, [rsp+2A0h+pszDest]
0x18003a6d4  mov     rcx, r15
0x18003a6d7  call    StrmPutStringEOL
0x18003a6dc  xor     r8d, r8d
0x18003a6df  movzx   edi, ax
0x18003a6e2  cmp     r8w, ax
0x18003a6e6  jnz     loc_18003AA6F
0x18003a6ec  jmp     short loc_18003A72B
0x18003a6ee  cmp     dword ptr [rdx+94h], 33h ; '3'
0x18003a6f5  jg      loc_18003A5BD
0x18003a6fb  mov     rcx, [rdx+0A0h]
0x18003a702  mov     rax, [rcx+8]
0x18003a706  test    rax, rax
0x18003a709  jz      short loc_18003A712
0x18003a70b  mov     edx, esi
0x18003a70d  jmp     loc_18003A5AD
0x18003a712  mov     eax, 0Dh
0x18003a717  jmp     loc_18003AA79
0x18003a71c  mov     edi, 12h
0x18003a721  jmp     loc_18003AA6F
0x18003a726  mov     r15, [rsp+2A0h+var_260]
0x18003a72b  cmp     dword ptr [rbx+4], 5
0x18003a72f  jz      short loc_18003A7A4
0x18003a731  cmp     dword ptr [rbx+4], 6
0x18003a735  jnz     short loc_18003A769
0x18003a737  lea     rdx, aCmapWincharset; "CMAP-WinCharSetFFFF-V"
0x18003a73e  mov     rcx, r15
0x18003a741  call    StrmPutStringEOL
0x18003a746  xor     ecx, ecx
0x18003a748  movzx   edi, ax
0x18003a74b  cmp     cx, ax
0x18003a74e  jnz     loc_18003AA6F
0x18003a754  cmp     [rbx+98h], cl
0x18003a75a  jz      loc_18003A7E7
0x18003a760  lea     rdx, aCmap90mspRksjH; "CMAP-90msp-RKSJ-H CMAP-90msp-RKSJ-QV"
0x18003a767  jmp     short loc_18003A7D0
0x18003a769  cmp     [rbx+0A0h], r8
0x18003a770  jz      loc_18003AA6B
0x18003a776  test    byte ptr [rbx+1Ch], 8
0x18003a77a  jz      loc_18003AA6B
0x18003a780  mov     r9, [rbx+38h]
0x18003a784  lea     r8, aSFalseSHfredef; "/%s false /%s hfRedefFont"
0x18003a78b  mov     edx, 200h; cchDest
0x18003a790  mov     [rsp+2A0h+var_280], r14
0x18003a795  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003a79a  call    StringCchPrintfA
0x18003a79f  jmp     loc_18003AA54
0x18003a7a4  lea     rdx, aCmapWincharset_0; "CMAP-WinCharSetFFFF-H"
0x18003a7ab  mov     rcx, r15
0x18003a7ae  call    StrmPutStringEOL
0x18003a7b3  xor     ecx, ecx
0x18003a7b5  movzx   edi, ax
0x18003a7b8  cmp     cx, ax
0x18003a7bb  jnz     loc_18003AA6F
0x18003a7c1  cmp     [rbx+98h], cl
0x18003a7c7  jz      short loc_18003A7E7
0x18003a7c9  lea     rdx, aCmap90mspRksjH_0; "CMAP-90msp-RKSJ-H"
0x18003a7d0  mov     rcx, r15
0x18003a7d3  call    StrmPutStringEOL
0x18003a7d8  xor     ecx, ecx
0x18003a7da  cmp     cx, ax
0x18003a7dd  jz      short loc_18003A7E7
0x18003a7df  movzx   edi, ax
0x18003a7e2  jmp     loc_18003AA6F
0x18003a7e7  mov     rax, [rbx+30h]
0x18003a7eb  lea     r8, aSWincharsetfff; "/%s /WinCharSetFFFF-H"
0x18003a7f2  mov     r9, [rbx+38h]
0x18003a7f6  mov     ecx, 80h
0x18003a7fb  mov     edx, 200h; cchDest
0x18003a800  and     cx, [rax+44h]
0x18003a804  lea     rax, aSWincharsetfff_0; "/%s /WinCharSetFFFF-V"
0x18003a80b  cmp     dword ptr [rbx+4], 5
0x18003a80f  mov     dword ptr [rsp+2A0h+var_260], ecx
0x18003a813  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003a818  cmovnz  r8, rax; pszFormat
0x18003a81c  call    StringCchPrintfA
0x18003a821  lea     rdx, [rsp+2A0h+pszDest]
0x18003a826  mov     rcx, r15
0x18003a829  call    StrmPutStringEOL
0x18003a82e  xor     ecx, ecx
0x18003a830  lea     rdx, aHf; "-hf"
0x18003a837  lea     r8, aAdbcfb; "ADBCFB+"
0x18003a83e  movzx   edi, ax
0x18003a841  cmp     [rbx+0A0h], rcx
0x18003a848  jz      short loc_18003A8A7
0x18003a84a  test    byte ptr [rbx+1Ch], 8
0x18003a84e  jz      short loc_18003A8A7
0x18003a850  cmp     word ptr [rsp+2A0h+var_260], cx
0x18003a855  mov     r9, r14
0x18003a858  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003a85d  jnz     short loc_18003A872
0x18003a85f  lea     r8, aSComposefontPo; "[/%s] composefont pop"
0x18003a866  mov     edx, 200h; cchDest
0x18003a86b  call    StringCchPrintfA
0x18003a870  jmp     short loc_18003A8E7
0x18003a872  cmp     [rbx+8], esi
0x18003a875  jz      short loc_18003A8A0
0x18003a877  lea     rax, aPop4IndexAddBi; "{pop 4 index add}bind"
0x18003a87e  mov     [rsp+2A0h+var_270], r14
0x18003a883  mov     [rsp+2A0h+var_278], rax
0x18003a888  lea     r8, aSSSSHfmkcidfon; "/%s%s %s /%s hfMkCIDFont"
0x18003a88f  mov     [rsp+2A0h+var_280], rdx
0x18003a894  mov     edx, 200h; cchDest
0x18003a899  call    StringCchPrintfA
0x18003a89e  jmp     short loc_18003A8E7
0x18003a8a0  mov     [rsp+2A0h+var_280], rdx
0x18003a8a5  jmp     short loc_18003A8D6
0x18003a8a7  cmp     [rbx+88h], ecx
0x18003a8ad  lea     rax, [r12+5Ch]
0x18003a8b2  mov     [rsp+2A0h+var_280], rax
0x18003a8b7  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003a8bc  jnz     short loc_18003A8CF
0x18003a8be  cmp     dword ptr [rbx+4], 5
0x18003a8c2  lea     r9, aAdbcfa; "ADBCFA+"
0x18003a8c9  cmovnz  r9, r8
0x18003a8cd  jmp     short loc_18003A8D6
0x18003a8cf  lea     r9, aAdbcff; "ADBCFF+"
0x18003a8d6  lea     r8, aSSComposefontP_0; "[/%s%s] composefont pop"
0x18003a8dd  mov     edx, 200h; cchDest
0x18003a8e2  call    StringCchPrintfA
0x18003a8e7  xor     esi, esi
0x18003a8e9  cmp     si, di
0x18003a8ec  jnz     loc_18003AA6F
0x18003a8f2  lea     rdx, [rsp+2A0h+pszDest]
0x18003a8f7  mov     rcx, r15
0x18003a8fa  call    StrmPutStringEOL
0x18003a8ff  movzx   edi, ax
0x18003a902  cmp     si, ax
0x18003a905  jnz     loc_18003AA6F
0x18003a90b  cmp     [rbx+98h], sil
0x18003a912  jz      loc_18003AA6B
0x18003a918  mov     r9, [rbx+38h]
0x18003a91c  lea     r8, aSq; "/%sQ"
0x18003a923  mov     edx, 200h; cchDest
0x18003a928  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003a92d  call    StringCchPrintfA
0x18003a932  xor     ecx, ecx
0x18003a934  cmp     [rsp+2A0h+pszDest], cl
0x18003a938  jz      short loc_18003A961
0x18003a93a  lea     rax, [rsp+2A0h+pszDest]
0x18003a93f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a943  inc     r8
0x18003a946  cmp     [rax+r8], cl
0x18003a94a  jnz     short loc_18003A943
0x18003a94c  mov     r9b, 1
0x18003a94f  lea     rdx, [rsp+2A0h+pszDest]
0x18003a954  mov     rcx, r15
0x18003a957  call    StrmPutBytes
0x18003a95c  movzx   esi, ax
0x18003a95f  xor     ecx, ecx
0x18003a961  cmp     dword ptr [rbx+4], 5
0x18003a965  movzx   edi, si
0x18003a968  mov     rax, [rbx+0A0h]
0x18003a96f  jnz     short loc_18003A9E1
0x18003a971  test    rax, rax
0x18003a974  jz      short loc_18003A9AC
0x18003a976  test    byte ptr [rbx+1Ch], 8
0x18003a97a  jz      short loc_18003A9AC
0x18003a97c  cmp     word ptr [rsp+2A0h+var_260], cx
0x18003a981  mov     r9, r14
0x18003a984  lea     rcx, [rsp+2A0h+pszDest]
0x18003a989  mov     edx, 200h
0x18003a98e  jnz     short loc_18003A999
0x18003a990  lea     r8, a90mspRksjHSCom; " /90msp-RKSJ-H [/%s] composefont pop"
0x18003a997  jmp     short loc_18003AA07
0x18003a999  lea     rax, aHf; "-hf"
0x18003a9a0  lea     r8, a90mspRksjHSSCo; " /90msp-RKSJ-H [/%s%s] composefont pop"
0x18003a9a7  jmp     loc_18003AA43
0x18003a9ac  cmp     [rbx+88h], ecx
0x18003a9b2  lea     rax, [r12+5Ch]
0x18003a9b7  mov     [rsp+2A0h+var_280], rax
0x18003a9bc  lea     r8, a90mspRksjHSSCo; " /90msp-RKSJ-H [/%s%s] composefont pop"
0x18003a9c3  mov     edx, 200h
0x18003a9c8  lea     rcx, [rsp+2A0h+pszDest]
0x18003a9cd  jnz     short loc_18003A9D8
0x18003a9cf  lea     r9, aAdbcfa; "ADBCFA+"
0x18003a9d6  jmp     short loc_18003AA48
0x18003a9d8  lea     r9, aAdbcff; "ADBCFF+"
  ... truncated ...
```

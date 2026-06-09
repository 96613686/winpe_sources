# CFFCreateBaseFont

- ea: `0x180038c4c`
- end: `0x18003920c`
- name: `CFFCreateBaseFont`
- size: `1472`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180036b00`
- `0x1800392a0`

## callees

- `0x180001ee0`
- `0x1800055e0`
- `0x18003858c`
- `0x180038968`
- `0x180038c4c`
- `0x180047fb8`
- `0x18005d010`

## string_xrefs

- `0x180039046`: `[/%s%s] composefont pop`
- `0x180038fcf`: `[/%s] composefont pop`
- `0x180039110`: ` /90msp-RKSJ-H [/%s%s] composefont pop`
- `0x18003912c`: ` /90msp-RKSJ-H [/%s%s] composefont pop`
- `0x180039100`: ` /90msp-RKSJ-H [/%s] composefont pop`
- `0x1800391ac`: ` /90msp-RKSJ-QV [/%s%s dup dup] composefont pop`
- `0x180039170`: ` /90msp-RKSJ-QV [/%s dup dup] composefont pop`

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
  const char *v19; // rdx
  unsigned __int16 v20; // ax
  const char *v21; // r8
  const char *v22; // r9
  unsigned __int16 v23; // si
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rax
  const char *v27; // r9
  const char *v28; // rax
  const char *v29; // r8
  const char *v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+40h] [rbp-C0h]
  __int16 v32; // [rsp+40h] [rbp-C0h]
  char pszDest[512]; // [rsp+50h] [rbp-B0h] BYREF

  if ( *(int *)(a1 + 8) < 1 )
    return 4;
  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
  if ( v8 && *(_QWORD *)v8 )
  {
    v9 = *(_QWORD *)(a1 + 40);
    v31 = *(_QWORD *)(v9 + 168);
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
          v18 = v31;
          v14 = StrmPutStringEOL(v31, pszDest);
          if ( v14 )
            return v14;
        }
        else
        {
          v18 = v31;
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
            v32 = *(_WORD *)(*(_QWORD *)(a1 + 48) + 68LL) & 0x80;
            if ( *(_DWORD *)(a1 + 4) != 5 )
              v21 = "/%s /WinCharSetFFFF-V";
            StringCchPrintfA(pszDest, 0x200u, v21, *(_QWORD *)(a1 + 56));
            v14 = StrmPutStringEOL(v18, pszDest);
            if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
            {
              if ( v32 )
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
              v25 = -1;
              do
                ++v25;
              while ( pszDest[v25] );
              LOBYTE(v24) = 1;
              v23 = StrmPutBytes(v18, pszDest, v25, v24);
            }
            v14 = v23;
            v26 = *(_QWORD *)(a1 + 160);
            if ( *(_DWORD *)(a1 + 4) == 5 )
            {
              if ( !v26 || (*(_BYTE *)(a1 + 28) & 8) == 0 )
              {
                v30 = (const char *)(v8 + 92);
                v29 = " /90msp-RKSJ-H [/%s%s] composefont pop";
                if ( *(_DWORD *)(a1 + 136) )
                  v27 = "ADBCFF+";
                else
                  v27 = "ADBCFA+";
                goto LABEL_84;
              }
              v27 = a4;
              if ( !v32 )
              {
                StringCchPrintfA(pszDest, 0x200u, " /90msp-RKSJ-H [/%s] composefont pop", a4);
                goto LABEL_85;
              }
              v28 = "-hf";
              v29 = " /90msp-RKSJ-H [/%s%s] composefont pop";
            }
            else
            {
              if ( v26 && (*(_BYTE *)(a1 + 28) & 8) != 0 )
              {
                v27 = a4;
                if ( !v32 )
                {
                  StringCchPrintfA(pszDest, 0x200u, " /90msp-RKSJ-QV [/%s dup dup] composefont pop", a4);
                  goto LABEL_85;
                }
                v28 = "-hf";
              }
              else
              {
                v28 = (const char *)(v8 + 92);
                v27 = "ADBCFB+";
                if ( *(_DWORD *)(a1 + 136) )
                  v27 = "ADBCFF+";
              }
              v29 = " /90msp-RKSJ-QV [/%s%s dup dup] composefont pop";
            }
            v30 = v28;
LABEL_84:
            StringCchPrintfA(pszDest, 0x200u, v29, v27, v30);
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
0x180038c4c  push    rbp
0x180038c4e  push    rbx
0x180038c4f  push    rsi
0x180038c50  push    rdi
0x180038c51  push    r12
0x180038c53  push    r13
0x180038c55  push    r14
0x180038c57  push    r15
0x180038c59  lea     rbp, [rsp-168h]
0x180038c61  sub     rsp, 268h
0x180038c68  mov     rax, cs:__security_cookie
0x180038c6f  xor     rax, rsp
0x180038c72  mov     [rbp+1A0h+var_50], rax
0x180038c79  cmp     dword ptr [rcx+8], 1
0x180038c7d  mov     r14, r9
0x180038c80  mov     [rsp+2A0h+var_258], r8
0x180038c85  mov     r15, rdx
0x180038c88  mov     rbx, rcx
0x180038c8b  jge     short loc_180038C97
0x180038c8d  mov     eax, 4
0x180038c92  jmp     loc_1800391E9
0x180038c97  mov     rax, [rcx+30h]
0x180038c9b  xor     r8d, r8d
0x180038c9e  mov     r12, [rax+8]
0x180038ca2  test    r12, r12
0x180038ca5  jz      loc_1800391E4
0x180038cab  cmp     [r12], r8
0x180038caf  jz      loc_1800391E4
0x180038cb5  mov     rdx, [rcx+28h]
0x180038cb9  lea     r13d, [r8+4]
0x180038cbd  mov     ecx, [rcx+4]
0x180038cc0  lea     esi, [r8+2]
0x180038cc4  mov     rax, [rdx+0A8h]
0x180038ccb  mov     [rsp+2A0h+var_260], rax
0x180038cd0  sub     ecx, r13d
0x180038cd3  jz      loc_180038E5E
0x180038cd9  sub     ecx, 1
0x180038cdc  jz      short loc_180038CE3
0x180038cde  cmp     ecx, 1
0x180038ce1  jnz     short loc_180038D2D
0x180038ce3  mov     rcx, [rdx+0A0h]
0x180038cea  mov     edx, r13d
0x180038ced  mov     rax, [rcx+8]
0x180038cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cf6  xor     r8d, r8d
0x180038cf9  test    al, al
0x180038cfb  jz      loc_180038E82
0x180038d01  cmp     [rbx+98h], r8b
0x180038d08  jz      short loc_180038D2D
0x180038d0a  mov     rax, [rbx+28h]
0x180038d0e  lea     edx, [r8+5]
0x180038d12  mov     rcx, [rax+0A0h]
0x180038d19  mov     rax, [rcx+8]
0x180038d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d22  xor     r8d, r8d
0x180038d25  test    al, al
0x180038d27  jz      loc_180038E82
0x180038d2d  mov     edi, r8d
0x180038d30  cmp     [rbx+8], esi
0x180038d33  jz      loc_180038DE9
0x180038d39  movzx   ecx, word ptr [r12+40h]
0x180038d3f  xor     r9d, r9d
0x180038d42  mov     rax, [rbx+28h]
0x180038d46  mov     edx, 78746D76h
0x180038d4b  mov     word ptr [rsp+2A0h+var_278], cx
0x180038d50  mov     rcx, [rbx+10h]
0x180038d54  mov     dword ptr [rsp+2A0h+var_280], r8d
0x180038d59  xor     r8d, r8d
0x180038d5c  mov     rax, [rax+58h]
0x180038d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d65  mov     rdx, [rbx+30h]
0x180038d69  neg     eax
0x180038d6b  mov     eax, 80h
0x180038d70  mov     r8d, 0FF7Fh
0x180038d76  sbb     cx, cx
0x180038d79  and     cx, ax
0x180038d7c  movzx   eax, word ptr [rdx+44h]
0x180038d80  and     ax, r8w
0x180038d84  xor     r8d, r8d
0x180038d87  or      cx, ax
0x180038d8a  mov     [rdx+44h], cx
0x180038d8e  cmp     [rbx+0A0h], r8
0x180038d95  jz      short loc_180038D9D
0x180038d97  test    byte ptr [rbx+1Ch], 8
0x180038d9b  jnz     short loc_180038DE9
0x180038d9d  test    r15, r15
0x180038da0  jz      loc_180038E8C
0x180038da6  mov     r9, r8
0x180038da9  cmp     [r15+10h], r8
0x180038dad  jz      short loc_180038DB3
0x180038daf  mov     r9, [r15+18h]
0x180038db3  mov     rax, [rsp+2A0h+var_258]
0x180038db8  mov     r8, [r15+8]
0x180038dbc  mov     edx, [r15]
0x180038dbf  mov     rcx, [r12]
0x180038dc3  mov     [rsp+2A0h+var_280], rax
0x180038dc8  call    XCF_DownloadFontIncr
0x180038dcd  xor     r8d, r8d
0x180038dd0  mov     ecx, r8d
0x180038dd3  sub     ecx, eax
0x180038dd5  neg     ecx
0x180038dd7  lea     edi, [r8+12h]
0x180038ddb  sbb     dx, dx
0x180038dde  and     di, dx
0x180038de1  test    eax, eax
0x180038de3  jnz     loc_1800391DF
0x180038de9  cmp     [rbx+0A0h], r8
0x180038df0  jz      loc_180038E96
0x180038df6  test    byte ptr [rbx+1Ch], 8
0x180038dfa  jz      loc_180038E96
0x180038e00  cmp     [rbx+8], esi
0x180038e03  jz      loc_180038E96
0x180038e09  cmp     [rbx+4], r13d
0x180038e0d  lea     rax, aCidfont_0; "CIDFont"
0x180038e14  lea     r9, aFont_1; "font"
0x180038e1b  mov     [rsp+2A0h+var_280], r14
0x180038e20  cmovnz  r9, rax
0x180038e24  lea     r8, aIncluderesourc_2; "\n%%%%IncludeResource: %s %s"
0x180038e2b  mov     edx, 200h; cchDest
0x180038e30  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x180038e35  call    StringCchPrintfA
0x180038e3a  mov     r15, [rsp+2A0h+var_260]
0x180038e3f  lea     rdx, [rsp+2A0h+pszDest]
0x180038e44  mov     rcx, r15
0x180038e47  call    StrmPutStringEOL
0x180038e4c  xor     r8d, r8d
0x180038e4f  movzx   edi, ax
0x180038e52  cmp     r8w, ax
0x180038e56  jnz     loc_1800391DF
0x180038e5c  jmp     short loc_180038E9B
0x180038e5e  cmp     dword ptr [rdx+94h], 33h ; '3'
0x180038e65  jg      loc_180038D2D
0x180038e6b  mov     rcx, [rdx+0A0h]
0x180038e72  mov     rax, [rcx+8]
0x180038e76  test    rax, rax
0x180038e79  jz      short loc_180038E82
0x180038e7b  mov     edx, esi
0x180038e7d  jmp     loc_180038D1D
0x180038e82  mov     eax, 0Dh
0x180038e87  jmp     loc_1800391E9
0x180038e8c  mov     edi, 12h
0x180038e91  jmp     loc_1800391DF
0x180038e96  mov     r15, [rsp+2A0h+var_260]
0x180038e9b  cmp     dword ptr [rbx+4], 5
0x180038e9f  jz      short loc_180038F14
0x180038ea1  cmp     dword ptr [rbx+4], 6
0x180038ea5  jnz     short loc_180038ED9
0x180038ea7  lea     rdx, aCmapWincharset; "CMAP-WinCharSetFFFF-V"
0x180038eae  mov     rcx, r15
0x180038eb1  call    StrmPutStringEOL
0x180038eb6  xor     ecx, ecx
0x180038eb8  movzx   edi, ax
0x180038ebb  cmp     cx, ax
0x180038ebe  jnz     loc_1800391DF
0x180038ec4  cmp     [rbx+98h], cl
0x180038eca  jz      loc_180038F57
0x180038ed0  lea     rdx, aCmap90mspRksjH; "CMAP-90msp-RKSJ-H CMAP-90msp-RKSJ-QV"
0x180038ed7  jmp     short loc_180038F40
0x180038ed9  cmp     [rbx+0A0h], r8
0x180038ee0  jz      loc_1800391DB
0x180038ee6  test    byte ptr [rbx+1Ch], 8
0x180038eea  jz      loc_1800391DB
0x180038ef0  mov     r9, [rbx+38h]
0x180038ef4  lea     r8, aSFalseSHfredef; "/%s false /%s hfRedefFont"
0x180038efb  mov     edx, 200h; cchDest
0x180038f00  mov     [rsp+2A0h+var_280], r14
0x180038f05  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x180038f0a  call    StringCchPrintfA
0x180038f0f  jmp     loc_1800391C4
0x180038f14  lea     rdx, aCmapWincharset_0; "CMAP-WinCharSetFFFF-H"
0x180038f1b  mov     rcx, r15
0x180038f1e  call    StrmPutStringEOL
0x180038f23  xor     ecx, ecx
0x180038f25  movzx   edi, ax
0x180038f28  cmp     cx, ax
0x180038f2b  jnz     loc_1800391DF
0x180038f31  cmp     [rbx+98h], cl
0x180038f37  jz      short loc_180038F57
0x180038f39  lea     rdx, aCmap90mspRksjH_0; "CMAP-90msp-RKSJ-H"
0x180038f40  mov     rcx, r15
0x180038f43  call    StrmPutStringEOL
0x180038f48  xor     ecx, ecx
0x180038f4a  cmp     cx, ax
0x180038f4d  jz      short loc_180038F57
0x180038f4f  movzx   edi, ax
0x180038f52  jmp     loc_1800391DF
0x180038f57  mov     rax, [rbx+30h]
0x180038f5b  lea     r8, aSWincharsetfff; "/%s /WinCharSetFFFF-H"
0x180038f62  mov     r9, [rbx+38h]
0x180038f66  mov     ecx, 80h
0x180038f6b  mov     edx, 200h; cchDest
0x180038f70  and     cx, [rax+44h]
0x180038f74  lea     rax, aSWincharsetfff_0; "/%s /WinCharSetFFFF-V"
0x180038f7b  cmp     dword ptr [rbx+4], 5
0x180038f7f  mov     dword ptr [rsp+2A0h+var_260], ecx
0x180038f83  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x180038f88  cmovnz  r8, rax; pszFormat
0x180038f8c  call    StringCchPrintfA
0x180038f91  lea     rdx, [rsp+2A0h+pszDest]
0x180038f96  mov     rcx, r15
0x180038f99  call    StrmPutStringEOL
0x180038f9e  xor     ecx, ecx
0x180038fa0  lea     rdx, aHf; "-hf"
0x180038fa7  lea     r8, aAdbcfb; "ADBCFB+"
0x180038fae  movzx   edi, ax
0x180038fb1  cmp     [rbx+0A0h], rcx
0x180038fb8  jz      short loc_180039017
0x180038fba  test    byte ptr [rbx+1Ch], 8
0x180038fbe  jz      short loc_180039017
0x180038fc0  cmp     word ptr [rsp+2A0h+var_260], cx
0x180038fc5  mov     r9, r14
0x180038fc8  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x180038fcd  jnz     short loc_180038FE2
0x180038fcf  lea     r8, aSComposefontPo; "[/%s] composefont pop"
0x180038fd6  mov     edx, 200h; cchDest
0x180038fdb  call    StringCchPrintfA
0x180038fe0  jmp     short loc_180039057
0x180038fe2  cmp     [rbx+8], esi
0x180038fe5  jz      short loc_180039010
0x180038fe7  lea     rax, aPop4IndexAddBi; "{pop 4 index add}bind"
0x180038fee  mov     [rsp+2A0h+var_270], r14
0x180038ff3  mov     [rsp+2A0h+var_278], rax
0x180038ff8  lea     r8, aSSSSHfmkcidfon; "/%s%s %s /%s hfMkCIDFont"
0x180038fff  mov     [rsp+2A0h+var_280], rdx
0x180039004  mov     edx, 200h; cchDest
0x180039009  call    StringCchPrintfA
0x18003900e  jmp     short loc_180039057
0x180039010  mov     [rsp+2A0h+var_280], rdx
0x180039015  jmp     short loc_180039046
0x180039017  cmp     [rbx+88h], ecx
0x18003901d  lea     rax, [r12+5Ch]
0x180039022  mov     [rsp+2A0h+var_280], rax
0x180039027  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003902c  jnz     short loc_18003903F
0x18003902e  cmp     dword ptr [rbx+4], 5
0x180039032  lea     r9, aAdbcfa; "ADBCFA+"
0x180039039  cmovnz  r9, r8
0x18003903d  jmp     short loc_180039046
0x18003903f  lea     r9, aAdbcff; "ADBCFF+"
0x180039046  lea     r8, aSSComposefontP_0; "[/%s%s] composefont pop"
0x18003904d  mov     edx, 200h; cchDest
0x180039052  call    StringCchPrintfA
0x180039057  xor     esi, esi
0x180039059  cmp     si, di
0x18003905c  jnz     loc_1800391DF
0x180039062  lea     rdx, [rsp+2A0h+pszDest]
0x180039067  mov     rcx, r15
0x18003906a  call    StrmPutStringEOL
0x18003906f  movzx   edi, ax
0x180039072  cmp     si, ax
0x180039075  jnz     loc_1800391DF
0x18003907b  cmp     [rbx+98h], sil
0x180039082  jz      loc_1800391DB
0x180039088  mov     r9, [rbx+38h]
0x18003908c  lea     r8, aSq; "/%sQ"
0x180039093  mov     edx, 200h; cchDest
0x180039098  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18003909d  call    StringCchPrintfA
0x1800390a2  xor     ecx, ecx
0x1800390a4  cmp     [rsp+2A0h+pszDest], cl
0x1800390a8  jz      short loc_1800390D1
0x1800390aa  lea     rax, [rsp+2A0h+pszDest]
0x1800390af  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800390b3  inc     r8
0x1800390b6  cmp     [rax+r8], cl
0x1800390ba  jnz     short loc_1800390B3
0x1800390bc  mov     r9b, 1
0x1800390bf  lea     rdx, [rsp+2A0h+pszDest]
0x1800390c4  mov     rcx, r15
0x1800390c7  call    StrmPutBytes
0x1800390cc  movzx   esi, ax
0x1800390cf  xor     ecx, ecx
0x1800390d1  cmp     dword ptr [rbx+4], 5
0x1800390d5  movzx   edi, si
0x1800390d8  mov     rax, [rbx+0A0h]
0x1800390df  jnz     short loc_180039151
0x1800390e1  test    rax, rax
0x1800390e4  jz      short loc_18003911C
0x1800390e6  test    byte ptr [rbx+1Ch], 8
0x1800390ea  jz      short loc_18003911C
0x1800390ec  cmp     word ptr [rsp+2A0h+var_260], cx
0x1800390f1  mov     r9, r14
0x1800390f4  lea     rcx, [rsp+2A0h+pszDest]
0x1800390f9  mov     edx, 200h
0x1800390fe  jnz     short loc_180039109
0x180039100  lea     r8, a90mspRksjHSCom; " /90msp-RKSJ-H [/%s] composefont pop"
0x180039107  jmp     short loc_180039177
0x180039109  lea     rax, aHf; "-hf"
0x180039110  lea     r8, a90mspRksjHSSCo; " /90msp-RKSJ-H [/%s%s] composefont pop"
0x180039117  jmp     loc_1800391B3
0x18003911c  cmp     [rbx+88h], ecx
0x180039122  lea     rax, [r12+5Ch]
0x180039127  mov     [rsp+2A0h+var_280], rax
0x18003912c  lea     r8, a90mspRksjHSSCo; " /90msp-RKSJ-H [/%s%s] composefont pop"
0x180039133  mov     edx, 200h
0x180039138  lea     rcx, [rsp+2A0h+pszDest]
0x18003913d  jnz     short loc_180039148
0x18003913f  lea     r9, aAdbcfa; "ADBCFA+"
0x180039146  jmp     short loc_1800391B8
0x180039148  lea     r9, aAdbcff; "ADBCFF+"
  ... truncated ...
```

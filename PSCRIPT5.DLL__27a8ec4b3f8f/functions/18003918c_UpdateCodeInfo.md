# UpdateCodeInfo

- ea: `0x18003918c`
- end: `0x1800396e3`
- name: `UpdateCodeInfo`
- size: `1367`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18003b20c`
- `0x18003e878`
- `0x1800433b0`
- `0x180046500`

## callees

- `0x180001f20`
- `0x180005670`
- `0x18003886c`
- `0x18003918c`
- `0x180039e10`
- `0x18003a1f4`
- `0x180041914`
- `0x180042424`

## pseudocode

```c
__int64 __fastcall UpdateCodeInfo(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  unsigned __int16 v6; // bx
  __int64 v7; // r15
  char v8; // r12
  __int64 v9; // rax
  __int64 v10; // rax
  int i; // r13d
  unsigned int v12; // edi
  __int64 v13; // rax
  int v14; // ecx
  unsigned __int16 v15; // r9
  __int64 v16; // rax
  unsigned __int16 v17; // si
  unsigned __int16 v18; // dx
  _QWORD *v19; // rcx
  __int64 v20; // rax
  int v21; // edx
  __int64 v22; // r8
  const char *v23; // rdx
  int v24; // r8d
  __int64 v25; // rcx
  const char *v26; // r9
  __int64 v27; // r8
  __int64 v28; // rcx
  char *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // r8
  unsigned __int16 v33; // ax
  char v35; // [rsp+30h] [rbp-D0h]
  char v36; // [rsp+31h] [rbp-CFh]
  _WORD v37[2]; // [rsp+34h] [rbp-CCh] BYREF
  char v38; // [rsp+38h] [rbp-C8h]
  __int64 v39; // [rsp+40h] [rbp-C0h]
  int v40; // [rsp+48h] [rbp-B8h]
  const char *v41; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v43; // [rsp+60h] [rbp-A0h]
  char pszDest[64]; // [rsp+70h] [rbp-90h] BYREF
  char v45[256]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = *(_QWORD *)(a1 + 40);
  v38 = a3;
  v4 = a2;
  v39 = a2;
  v6 = 0;
  v36 = 0;
  v7 = *(_QWORD *)(v3 + 168);
  v8 = 0;
  v42 = *(_QWORD *)(a2 + 8);
  if ( (unsigned __int16)GetTablesFromTTFont((_QWORD *)a1) )
  {
    v9 = *(_QWORD *)(a1 + 48);
    if ( !*(_DWORD *)(v9 + 88) || *(_DWORD *)(v9 + 88) == 5 )
      v8 = 1;
  }
  v10 = *(_QWORD *)(v4 + 32);
  if ( v10 && !v8 )
  {
    v35 = 0;
LABEL_9:
    v8 = 1;
    goto LABEL_10;
  }
  v35 = 1;
  if ( v10 )
    goto LABEL_9;
LABEL_10:
  for ( i = 0; i < *(_DWORD *)v4; ++i )
  {
    v37[0] = 0;
    v12 = *(unsigned __int16 *)(v42 + 4LL * i);
    if ( v12 >= *(_DWORD *)(*(_QWORD *)(a1 + 120) + 4LL) )
      goto LABEL_86;
    v13 = *(_QWORD *)(a1 + 48);
    v43 = (unsigned __int64)*(unsigned __int16 *)(v42 + 4LL * i) >> 3;
    v40 = v12 & 7;
    if ( (*(_BYTE *)(v43 + *(_QWORD *)(v13 + 48)) & (unsigned __int8)(1 << (v12 & 7))) != 0 )
      goto LABEL_86;
    v14 = *(_DWORD *)(a1 + 4);
    if ( (unsigned int)(v14 - 13) <= 3 || (unsigned int)(v14 - 5) <= 1 )
    {
      StringCchPrintfA(pszDest, 0x40u, "%d ", v12);
      v20 = *(_QWORD *)(v39 + 32);
      if ( !v20 || (v17 = *(_WORD *)(v20 + 2LL * i)) == 0 )
      {
        if ( !v35 )
          goto LABEL_86;
        v18 = v12;
        v19 = (_QWORD *)a1;
        goto LABEL_25;
      }
    }
    else
    {
      v41 = 0;
      FindGlyphName(a1, v39, i, v12, (__int64 *)&v41);
      StringCchPrintfA(pszDest, 0x40u, "/%s ", v41);
      v16 = *(_QWORD *)(v39 + 32);
      if ( !v16 || (v17 = *(_WORD *)(v16 + 2LL * i)) == 0 )
      {
        if ( !v35 )
          goto LABEL_86;
        v18 = v12;
        v19 = (_QWORD *)a1;
        if ( v8 )
          ParseTTTablesForUnicode((_QWORD *)a1, v12, v37, v15, 1);
        else
LABEL_25:
          ParseTTTablesForUnicode(v19, v18, v37, v15, 2);
        v17 = v37[0];
      }
    }
    if ( v17 )
    {
      if ( v36 )
        goto LABEL_76;
      v21 = *(_DWORD *)(a1 + 4);
      v36 = 1;
      if ( (unsigned int)(v21 - 13) <= 1 )
      {
        StringCchPrintfA(
          v45,
          0x100u,
          " /%s%s",
          (const char *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL) + 150LL),
          gcidSuffix[0]);
      }
      else
      {
        if ( (unsigned int)(v21 - 15) > 1 )
        {
          if ( (unsigned int)(v21 - 5) > 1 )
          {
            if ( v38 )
              StrmPutStringEOL(v7, "Is2016andT32? not {");
            StringCchPrintfA(v45, 0x100u, " /%s", *(const char **)(a1 + 56));
            if ( !v45[0] )
              goto LABEL_38;
            v22 = -1;
            do
              ++v22;
            while ( v45[v22] );
            v6 = StrmPutBytes(v7, (__int64)v45, v22, 1);
            if ( !v6 )
            {
LABEL_38:
              v23 = " /Font";
              v24 = 6;
              goto LABEL_58;
            }
            goto LABEL_76;
          }
          v25 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
          if ( (*(_BYTE *)(v25 + 90) & 0x40) != 0 )
          {
            StringCchPrintfA(v45, 0x100u, "/%s", (const char *)(v25 + 92));
          }
          else
          {
            if ( *(_DWORD *)(a1 + 136) )
            {
              v26 = "ADBCFF+";
            }
            else
            {
              v26 = "ADBCFA+";
              if ( v21 != 5 )
                v26 = "ADBCFB+";
            }
            StringCchPrintfA(v45, 0x100u, "/%s%s", v26, v25 + 92);
          }
          if ( v45[0] )
          {
            v27 = -1;
            do
              ++v27;
            while ( v45[v27] );
LABEL_56:
            v6 = StrmPutBytes(v7, (__int64)v45, v27, 1);
            if ( v6 )
              goto LABEL_76;
          }
          goto LABEL_57;
        }
        StringCchPrintfA(v45, 0x100u, " /%s", *(const char **)(a1 + 56));
      }
      if ( v45[0] )
      {
        v27 = -1;
        do
          ++v27;
        while ( v45[v27] );
        goto LABEL_56;
      }
LABEL_57:
      v24 = 9;
      v23 = " /CIDFont";
LABEL_58:
      v6 = StrmPutBytes(v7, (__int64)v23, v24, 1);
      if ( !v6 )
      {
        v28 = v7;
        if ( v8 )
        {
          v29 = " G2UBegin";
        }
        else
        {
          v6 = StrmPutStringEOL(v7, " G2CCBegin");
          v30 = *(_QWORD *)(a1 + 48);
          if ( !v30 )
            goto LABEL_76;
          v31 = *(_DWORD *)(v30 + 88);
          switch ( v31 )
          {
            case 3:
            case 8:
              v29 = "/WinCharSet 128 def";
              break;
            case 1:
            case 6:
              v29 = "/WinCharSet 134 def";
              break;
            case 2:
            case 7:
              v29 = "/WinCharSet 136 def";
              break;
            case 4:
            case 9:
              v29 = "/WinCharSet 129 def";
              break;
            default:
              goto LABEL_76;
          }
          v28 = v7;
        }
        v6 = StrmPutStringEOL(v28, v29);
      }
LABEL_76:
      if ( !v6 )
      {
        if ( pszDest[0] )
        {
          v32 = -1;
          do
            ++v32;
          while ( pszDest[v32] );
          v33 = StrmPutBytes(v7, (__int64)pszDest, v32, 1);
        }
        else
        {
          v33 = 0;
        }
        v6 = v33;
      }
      StringCchPrintfA(v45, 0x100u, "<%04X> def", v17);
      if ( !v6 )
        v6 = StrmPutStringEOL(v7, v45);
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 48LL) + v43) |= 1 << v40;
    }
LABEL_86:
    v4 = v39;
    if ( v6 )
      return v6;
  }
  if ( v36 )
  {
    v6 = StrmPutStringEOL(v7, "G2UEnd");
    if ( v38 )
      StrmPutStringEOL(v7, "} if");
  }
  return v6;
}

```

## disassembly

```asm
0x18003918c  mov     [rsp-8+arg_10], rbx
0x180039191  push    rbp
0x180039192  push    rsi
0x180039193  push    rdi
0x180039194  push    r12
0x180039196  push    r13
0x180039198  push    r14
0x18003919a  push    r15
0x18003919c  lea     rbp, [rsp-0C0h]
0x1800391a4  sub     rsp, 1C0h
0x1800391ab  mov     rax, cs:__security_cookie
0x1800391b2  xor     rax, rsp
0x1800391b5  mov     [rbp+0F0h+var_40], rax
0x1800391bc  mov     rax, [rcx+28h]
0x1800391c0  xor     esi, esi
0x1800391c2  mov     [rsp+1F0h+var_1B8], r8b
0x1800391c7  mov     rdi, rdx
0x1800391ca  mov     [rsp+1F0h+var_1B0], rdx
0x1800391cf  mov     r14, rcx
0x1800391d2  mov     ebx, esi
0x1800391d4  mov     [rsp+1F0h+var_1BF], sil
0x1800391d9  mov     r15, [rax+0A8h]
0x1800391e0  mov     r12b, sil
0x1800391e3  mov     rax, [rdx+8]
0x1800391e7  mov     [rsp+1F0h+var_198], rax
0x1800391ec  call    GetTablesFromTTFont
0x1800391f1  test    ax, ax
0x1800391f4  jz      short loc_180039208
0x1800391f6  mov     rax, [r14+30h]
0x1800391fa  cmp     [rax+58h], esi
0x1800391fd  jz      short loc_180039205
0x1800391ff  cmp     dword ptr [rax+58h], 5
0x180039203  jnz     short loc_180039208
0x180039205  mov     r12b, 1
0x180039208  mov     rax, [rdi+20h]
0x18003920c  test    rax, rax
0x18003920f  jz      short loc_18003921D
0x180039211  test    r12b, r12b
0x180039214  jnz     short loc_18003921D
0x180039216  mov     [rsp+1F0h+var_1C0], sil
0x18003921b  jmp     short loc_180039227
0x18003921d  mov     [rsp+1F0h+var_1C0], 1
0x180039222  test    rax, rax
0x180039225  jz      short loc_18003922A
0x180039227  mov     r12b, 1
0x18003922a  mov     r13d, esi
0x18003922d  cmp     r13d, [rdi]
0x180039230  jge     loc_180039686
0x180039236  mov     rax, [rsp+1F0h+var_198]
0x18003923b  mov     [rsp+1F0h+var_1BC], si
0x180039240  movsxd  rsi, r13d
0x180039243  movzx   edi, word ptr [rax+rsi*4]
0x180039247  mov     rax, [r14+78h]
0x18003924b  cmp     edi, [rax+4]
0x18003924e  jnb     loc_18003966E
0x180039254  mov     rax, [r14+30h]
0x180039258  mov     edx, edi
0x18003925a  shr     rdx, 3
0x18003925e  mov     r8d, edi
0x180039261  and     r8d, 7
0x180039265  mov     [rsp+1F0h+var_190], rdx
0x18003926a  mov     [rsp+1F0h+var_1A8], r8d
0x18003926f  mov     rcx, [rax+30h]
0x180039273  mov     eax, 1
0x180039278  mov     dl, [rdx+rcx]
0x18003927b  mov     ecx, r8d
0x18003927e  shl     eax, cl
0x180039280  test    al, dl
0x180039282  jnz     loc_18003966E
0x180039288  mov     ecx, [r14+4]
0x18003928c  lea     eax, [rcx-0Dh]
0x18003928f  cmp     eax, 3
0x180039292  jbe     loc_18003931D
0x180039298  lea     eax, [rcx-5]
0x18003929b  cmp     eax, 1
0x18003929e  jbe     short loc_18003931D
0x1800392a0  mov     rdx, [rsp+1F0h+var_1B0]
0x1800392a5  lea     rax, [rsp+1F0h+var_1A0]
0x1800392aa  xor     ecx, ecx
0x1800392ac  mov     [rsp+1F0h+var_1D0], rax
0x1800392b1  mov     [rsp+1F0h+var_1A0], rcx
0x1800392b6  movzx   r9d, di
0x1800392ba  mov     rcx, r14
0x1800392bd  mov     r8d, r13d
0x1800392c0  call    FindGlyphName
0x1800392c5  mov     r9, [rsp+1F0h+var_1A0]
0x1800392ca  lea     r8, aS_2; "/%s "
0x1800392d1  mov     edx, 40h ; '@'; cchDest
0x1800392d6  lea     rcx, [rsp+1F0h+pszDest]; pszDest
0x1800392db  call    StringCchPrintfA
0x1800392e0  mov     rcx, [rsp+1F0h+var_1B0]
0x1800392e5  mov     rax, [rcx+20h]
0x1800392e9  xor     ecx, ecx
0x1800392eb  test    rax, rax
0x1800392ee  jz      short loc_1800392F9
0x1800392f0  movzx   esi, word ptr [rax+rsi*2]
0x1800392f4  test    si, si
0x1800392f7  jnz     short loc_180039376
0x1800392f9  cmp     [rsp+1F0h+var_1C0], cl
0x1800392fd  jz      loc_18003966E
0x180039303  lea     r8, [rsp+1F0h+var_1BC]
0x180039308  movzx   edx, di
0x18003930b  mov     rcx, r14
0x18003930e  test    r12b, r12b
0x180039311  jz      short loc_180039364
0x180039313  mov     dword ptr [rsp+1F0h+var_1D0], 1
0x18003931b  jmp     short loc_18003936C
0x18003931d  mov     r9d, edi
0x180039320  lea     r8, aD_0; "%d "
0x180039327  mov     edx, 40h ; '@'; cchDest
0x18003932c  lea     rcx, [rsp+1F0h+pszDest]; pszDest
0x180039331  call    StringCchPrintfA
0x180039336  mov     rcx, [rsp+1F0h+var_1B0]
0x18003933b  mov     rax, [rcx+20h]
0x18003933f  xor     ecx, ecx
0x180039341  test    rax, rax
0x180039344  jz      short loc_18003934F
0x180039346  movzx   esi, word ptr [rax+rsi*2]
0x18003934a  test    si, si
0x18003934d  jnz     short loc_180039376
0x18003934f  cmp     [rsp+1F0h+var_1C0], cl
0x180039353  jz      loc_18003966E
0x180039359  lea     r8, [rsp+1F0h+var_1BC]
0x18003935e  movzx   edx, di
0x180039361  mov     rcx, r14
0x180039364  mov     dword ptr [rsp+1F0h+var_1D0], 2
0x18003936c  call    ParseTTTablesForUnicode
0x180039371  movzx   esi, [rsp+1F0h+var_1BC]
0x180039376  xor     edi, edi
0x180039378  test    si, si
0x18003937b  jz      loc_18003966E
0x180039381  cmp     [rsp+1F0h+var_1BF], dil
0x180039386  jnz     loc_1800395EF
0x18003938c  mov     edx, [r14+4]
0x180039390  mov     [rsp+1F0h+var_1BF], 1
0x180039395  lea     eax, [rdx-0Dh]
0x180039398  cmp     eax, 1
0x18003939b  jbe     loc_1800394DF
0x1800393a1  lea     eax, [rdx-0Fh]
0x1800393a4  cmp     eax, 1
0x1800393a7  jbe     loc_1800394C4
0x1800393ad  lea     eax, [rdx-5]
0x1800393b0  cmp     eax, 1
0x1800393b3  jbe     short loc_180039431
0x1800393b5  cmp     [rsp+1F0h+var_1B8], dil
0x1800393ba  jz      short loc_1800393CB
0x1800393bc  lea     rdx, aIs2016andt32No; "Is2016andT32? not {"
0x1800393c3  mov     rcx, r15
0x1800393c6  call    StrmPutStringEOL
0x1800393cb  mov     r9, [r14+38h]
0x1800393cf  lea     r8, aS; " /%s"
0x1800393d6  mov     edx, 100h; cchDest
0x1800393db  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x1800393df  call    StringCchPrintfA
0x1800393e4  cmp     di, bx
0x1800393e7  jnz     loc_1800395EF
0x1800393ed  cmp     [rbp+0F0h+var_140], dil
0x1800393f1  jz      short loc_18003941F
0x1800393f3  lea     rax, [rbp+0F0h+var_140]
0x1800393f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800393fb  inc     r8
0x1800393fe  cmp     [rax+r8], dil
0x180039402  jnz     short loc_1800393FB
0x180039404  mov     r9b, 1
0x180039407  lea     rdx, [rbp+0F0h+var_140]
0x18003940b  mov     rcx, r15
0x18003940e  call    StrmPutBytes
0x180039413  movzx   ebx, ax
0x180039416  cmp     di, ax
0x180039419  jnz     loc_1800395EF
0x18003941f  lea     rdx, aFont; " /Font"
0x180039426  mov     r8d, 6
0x18003942c  jmp     loc_180039557
0x180039431  mov     rax, [r14+30h]
0x180039435  mov     rcx, [rax+8]
0x180039439  test    byte ptr [rcx+5Ah], 40h
0x18003943d  lea     rax, [rcx+5Ch]
0x180039441  jz      short loc_18003945D
0x180039443  mov     r9, rax
0x180039446  lea     r8, aS_4; "/%s"
0x18003944d  mov     edx, 100h; cchDest
0x180039452  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x180039456  call    StringCchPrintfA
0x18003945b  jmp     short loc_18003949E
0x18003945d  lea     r8, aSS_0; "/%s%s"
0x180039464  mov     [rsp+1F0h+var_1D0], rax
0x180039469  cmp     [r14+88h], edi
0x180039470  jnz     short loc_180039489
0x180039472  cmp     edx, 5
0x180039475  lea     rcx, aAdbcfb; "ADBCFB+"
0x18003947c  lea     r9, aAdbcfa; "ADBCFA+"
0x180039483  cmovnz  r9, rcx
0x180039487  jmp     short loc_180039490
0x180039489  lea     r9, aAdbcff; "ADBCFF+"
0x180039490  mov     edx, 100h; cchDest
0x180039495  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x180039499  call    StringCchPrintfA
0x18003949e  cmp     di, bx
0x1800394a1  jnz     loc_1800395EF
0x1800394a7  cmp     [rbp+0F0h+var_140], dil
0x1800394ab  jz      loc_18003954A
0x1800394b1  lea     rax, [rbp+0F0h+var_140]
0x1800394b5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800394b9  inc     r8
0x1800394bc  cmp     [rax+r8], dil
0x1800394c0  jnz     short loc_1800394B9
0x1800394c2  jmp     short loc_18003952F
0x1800394c4  mov     r9, [r14+38h]
0x1800394c8  lea     r8, aS; " /%s"
0x1800394cf  mov     edx, 100h; cchDest
0x1800394d4  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x1800394d8  call    StringCchPrintfA
0x1800394dd  jmp     short loc_18003950F
0x1800394df  mov     rax, [r14+30h]
0x1800394e3  lea     r8, aSS_1; " /%s%s"
0x1800394ea  mov     edx, 100h; cchDest
0x1800394ef  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x1800394f3  mov     r9, [rax+8]
0x1800394f7  mov     rax, cs:gcidSuffix
0x1800394fe  add     r9, 96h
0x180039505  mov     [rsp+1F0h+var_1D0], rax
0x18003950a  call    StringCchPrintfA
0x18003950f  cmp     di, bx
0x180039512  jnz     loc_1800395EF
0x180039518  cmp     [rbp+0F0h+var_140], dil
0x18003951c  jz      short loc_18003954A
0x18003951e  lea     rax, [rbp+0F0h+var_140]
0x180039522  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039526  inc     r8
0x180039529  cmp     [rax+r8], dil
0x18003952d  jnz     short loc_180039526
0x18003952f  mov     r9b, 1
0x180039532  lea     rdx, [rbp+0F0h+var_140]
0x180039536  mov     rcx, r15
0x180039539  call    StrmPutBytes
0x18003953e  movzx   ebx, ax
0x180039541  cmp     di, ax
0x180039544  jnz     loc_1800395EF
0x18003954a  mov     r8d, 9
0x180039550  lea     rdx, aCidfont; " /CIDFont"
0x180039557  mov     r9b, 1
0x18003955a  mov     rcx, r15
0x18003955d  call    StrmPutBytes
0x180039562  movzx   ebx, ax
0x180039565  cmp     di, ax
0x180039568  jnz     loc_1800395EF
0x18003956e  mov     rcx, r15
0x180039571  test    r12b, r12b
0x180039574  jz      short loc_18003957F
0x180039576  lea     rdx, aG2ubegin; " G2UBegin"
0x18003957d  jmp     short loc_1800395E7
0x18003957f  lea     rdx, aG2ccbegin; " G2CCBegin"
0x180039586  call    StrmPutStringEOL
0x18003958b  movzx   ebx, ax
0x18003958e  mov     rax, [r14+30h]
0x180039592  test    rax, rax
0x180039595  jz      short loc_1800395EF
0x180039597  mov     eax, [rax+58h]
0x18003959a  cmp     eax, 3
0x18003959d  jz      short loc_1800395DD
0x18003959f  cmp     eax, 8
0x1800395a2  jz      short loc_1800395DD
0x1800395a4  cmp     eax, 1
0x1800395a7  jz      short loc_1800395D4
0x1800395a9  cmp     eax, 6
0x1800395ac  jz      short loc_1800395D4
0x1800395ae  cmp     eax, 2
0x1800395b1  jz      short loc_1800395CB
0x1800395b3  cmp     eax, 7
0x1800395b6  jz      short loc_1800395CB
0x1800395b8  cmp     eax, 4
0x1800395bb  jz      short loc_1800395C2
0x1800395bd  cmp     eax, 9
0x1800395c0  jnz     short loc_1800395EF
0x1800395c2  lea     rdx, aWincharset129D; "/WinCharSet 129 def"
0x1800395c9  jmp     short loc_1800395E4
0x1800395cb  lea     rdx, aWincharset136D; "/WinCharSet 136 def"
0x1800395d2  jmp     short loc_1800395E4
0x1800395d4  lea     rdx, aWincharset134D; "/WinCharSet 134 def"
0x1800395db  jmp     short loc_1800395E4
0x1800395dd  lea     rdx, aWincharset128D; "/WinCharSet 128 def"
0x1800395e4  mov     rcx, r15
0x1800395e7  call    StrmPutStringEOL
0x1800395ec  movzx   ebx, ax
0x1800395ef  test    bx, bx
0x1800395f2  jnz     short loc_180039624
0x1800395f4  cmp     [rsp+1F0h+pszDest], dil
0x1800395f9  jz      short loc_18003961F
0x1800395fb  lea     rax, [rsp+1F0h+pszDest]
0x180039600  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039604  inc     r8
0x180039607  cmp     [rax+r8], dil
0x18003960b  jnz     short loc_180039604
0x18003960d  mov     r9b, 1
0x180039610  lea     rdx, [rsp+1F0h+pszDest]
0x180039615  mov     rcx, r15
0x180039618  call    StrmPutBytes
0x18003961d  jmp     short loc_180039621
0x18003961f  mov     eax, edi
0x180039621  movzx   ebx, ax
  ... truncated ...
```

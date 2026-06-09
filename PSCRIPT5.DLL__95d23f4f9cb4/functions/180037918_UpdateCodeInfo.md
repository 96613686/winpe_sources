# UpdateCodeInfo

- ea: `0x180037918`
- end: `0x180037e6e`
- name: `UpdateCodeInfo`
- size: `1366`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18003997c`
- `0x18003cfc0`
- `0x180041ab0`
- `0x180044be0`

## callees

- `0x180001ee0`
- `0x1800055e0`
- `0x180036ffc`
- `0x180037918`
- `0x18003858c`
- `0x180038968`
- `0x180040054`
- `0x180040b5c`

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
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned __int16 v17; // si
  int v18; // edx
  int v19; // ecx
  __int64 v20; // rax
  int v21; // edx
  __int64 v22; // r8
  const char *v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  const char *v26; // r9
  __int64 v27; // r8
  __int64 v28; // rcx
  const char *v29; // rdx
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
  if ( (unsigned __int16)GetTablesFromTTFont() )
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
        v18 = (unsigned __int16)v12;
        v19 = a1;
        goto LABEL_25;
      }
    }
    else
    {
      v41 = 0;
      FindGlyphName(a1, v39, i, (unsigned __int16)v12, (__int64)&v41);
      StringCchPrintfA(pszDest, 0x40u, "/%s ", v41);
      v16 = *(_QWORD *)(v39 + 32);
      if ( !v16 || (v17 = *(_WORD *)(v16 + 2LL * i)) == 0 )
      {
        if ( !v35 )
          goto LABEL_86;
        v18 = (unsigned __int16)v12;
        v19 = a1;
        if ( v8 )
          ParseTTTablesForUnicode(a1, (unsigned __int16)v12, (unsigned int)v37, v15, 1);
        else
LABEL_25:
          ParseTTTablesForUnicode(v19, v18, (unsigned int)v37, v15, 2);
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
            LOBYTE(v15) = 1;
            v6 = StrmPutBytes(v7, v45, v22, v15);
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
            LOBYTE(v15) = 1;
            v6 = StrmPutBytes(v7, v45, v27, v15);
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
      LOBYTE(v15) = 1;
      v6 = StrmPutBytes(v7, v23, v24, v15);
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
          LOBYTE(v15) = 1;
          v33 = StrmPutBytes(v7, pszDest, v32, v15);
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
0x180037918  mov     [rsp-8+arg_10], rbx
0x18003791d  push    rbp
0x18003791e  push    rsi
0x18003791f  push    rdi
0x180037920  push    r12
0x180037922  push    r13
0x180037924  push    r14
0x180037926  push    r15
0x180037928  lea     rbp, [rsp-0C0h]
0x180037930  sub     rsp, 1C0h
0x180037937  mov     rax, cs:__security_cookie
0x18003793e  xor     rax, rsp
0x180037941  mov     [rbp+0F0h+var_40], rax
0x180037948  mov     rax, [rcx+28h]
0x18003794c  xor     esi, esi
0x18003794e  mov     [rsp+1F0h+var_1B8], r8b
0x180037953  mov     rdi, rdx
0x180037956  mov     [rsp+1F0h+var_1B0], rdx
0x18003795b  mov     r14, rcx
0x18003795e  mov     ebx, esi
0x180037960  mov     [rsp+1F0h+var_1BF], sil
0x180037965  mov     r15, [rax+0A8h]
0x18003796c  mov     r12b, sil
0x18003796f  mov     rax, [rdx+8]
0x180037973  mov     [rsp+1F0h+var_198], rax
0x180037978  call    GetTablesFromTTFont
0x18003797d  test    ax, ax
0x180037980  jz      short loc_180037994
0x180037982  mov     rax, [r14+30h]
0x180037986  cmp     [rax+58h], esi
0x180037989  jz      short loc_180037991
0x18003798b  cmp     dword ptr [rax+58h], 5
0x18003798f  jnz     short loc_180037994
0x180037991  mov     r12b, 1
0x180037994  mov     rax, [rdi+20h]
0x180037998  test    rax, rax
0x18003799b  jz      short loc_1800379A9
0x18003799d  test    r12b, r12b
0x1800379a0  jnz     short loc_1800379A9
0x1800379a2  mov     [rsp+1F0h+var_1C0], sil
0x1800379a7  jmp     short loc_1800379B3
0x1800379a9  mov     [rsp+1F0h+var_1C0], 1
0x1800379ae  test    rax, rax
0x1800379b1  jz      short loc_1800379B6
0x1800379b3  mov     r12b, 1
0x1800379b6  mov     r13d, esi
0x1800379b9  cmp     r13d, [rdi]
0x1800379bc  jge     loc_180037E12
0x1800379c2  mov     rax, [rsp+1F0h+var_198]
0x1800379c7  mov     [rsp+1F0h+var_1BC], si
0x1800379cc  movsxd  rsi, r13d
0x1800379cf  movzx   edi, word ptr [rax+rsi*4]
0x1800379d3  mov     rax, [r14+78h]
0x1800379d7  cmp     edi, [rax+4]
0x1800379da  jnb     loc_180037DFA
0x1800379e0  mov     rax, [r14+30h]
0x1800379e4  mov     edx, edi
0x1800379e6  shr     rdx, 3
0x1800379ea  mov     r8d, edi
0x1800379ed  and     r8d, 7
0x1800379f1  mov     [rsp+1F0h+var_190], rdx
0x1800379f6  mov     [rsp+1F0h+var_1A8], r8d
0x1800379fb  mov     rcx, [rax+30h]
0x1800379ff  mov     eax, 1
0x180037a04  mov     dl, [rdx+rcx]
0x180037a07  mov     ecx, r8d
0x180037a0a  shl     eax, cl
0x180037a0c  test    al, dl
0x180037a0e  jnz     loc_180037DFA
0x180037a14  mov     ecx, [r14+4]
0x180037a18  lea     eax, [rcx-0Dh]
0x180037a1b  cmp     eax, 3
0x180037a1e  jbe     loc_180037AA9
0x180037a24  lea     eax, [rcx-5]
0x180037a27  cmp     eax, 1
0x180037a2a  jbe     short loc_180037AA9
0x180037a2c  mov     rdx, [rsp+1F0h+var_1B0]
0x180037a31  lea     rax, [rsp+1F0h+var_1A0]
0x180037a36  xor     ecx, ecx
0x180037a38  mov     [rsp+1F0h+var_1D0], rax
0x180037a3d  mov     [rsp+1F0h+var_1A0], rcx
0x180037a42  movzx   r9d, di
0x180037a46  mov     rcx, r14
0x180037a49  mov     r8d, r13d
0x180037a4c  call    FindGlyphName
0x180037a51  mov     r9, [rsp+1F0h+var_1A0]
0x180037a56  lea     r8, aS_2; "/%s "
0x180037a5d  mov     edx, 40h ; '@'; cchDest
0x180037a62  lea     rcx, [rsp+1F0h+pszDest]; pszDest
0x180037a67  call    StringCchPrintfA
0x180037a6c  mov     rcx, [rsp+1F0h+var_1B0]
0x180037a71  mov     rax, [rcx+20h]
0x180037a75  xor     ecx, ecx
0x180037a77  test    rax, rax
0x180037a7a  jz      short loc_180037A85
0x180037a7c  movzx   esi, word ptr [rax+rsi*2]
0x180037a80  test    si, si
0x180037a83  jnz     short loc_180037B02
0x180037a85  cmp     [rsp+1F0h+var_1C0], cl
0x180037a89  jz      loc_180037DFA
0x180037a8f  lea     r8, [rsp+1F0h+var_1BC]
0x180037a94  movzx   edx, di
0x180037a97  mov     rcx, r14
0x180037a9a  test    r12b, r12b
0x180037a9d  jz      short loc_180037AF0
0x180037a9f  mov     dword ptr [rsp+1F0h+var_1D0], 1
0x180037aa7  jmp     short loc_180037AF8
0x180037aa9  mov     r9d, edi
0x180037aac  lea     r8, aD_0; "%d "
0x180037ab3  mov     edx, 40h ; '@'; cchDest
0x180037ab8  lea     rcx, [rsp+1F0h+pszDest]; pszDest
0x180037abd  call    StringCchPrintfA
0x180037ac2  mov     rcx, [rsp+1F0h+var_1B0]
0x180037ac7  mov     rax, [rcx+20h]
0x180037acb  xor     ecx, ecx
0x180037acd  test    rax, rax
0x180037ad0  jz      short loc_180037ADB
0x180037ad2  movzx   esi, word ptr [rax+rsi*2]
0x180037ad6  test    si, si
0x180037ad9  jnz     short loc_180037B02
0x180037adb  cmp     [rsp+1F0h+var_1C0], cl
0x180037adf  jz      loc_180037DFA
0x180037ae5  lea     r8, [rsp+1F0h+var_1BC]
0x180037aea  movzx   edx, di
0x180037aed  mov     rcx, r14
0x180037af0  mov     dword ptr [rsp+1F0h+var_1D0], 2
0x180037af8  call    ParseTTTablesForUnicode
0x180037afd  movzx   esi, [rsp+1F0h+var_1BC]
0x180037b02  xor     edi, edi
0x180037b04  test    si, si
0x180037b07  jz      loc_180037DFA
0x180037b0d  cmp     [rsp+1F0h+var_1BF], dil
0x180037b12  jnz     loc_180037D7B
0x180037b18  mov     edx, [r14+4]
0x180037b1c  mov     [rsp+1F0h+var_1BF], 1
0x180037b21  lea     eax, [rdx-0Dh]
0x180037b24  cmp     eax, 1
0x180037b27  jbe     loc_180037C6B
0x180037b2d  lea     eax, [rdx-0Fh]
0x180037b30  cmp     eax, 1
0x180037b33  jbe     loc_180037C50
0x180037b39  lea     eax, [rdx-5]
0x180037b3c  cmp     eax, 1
0x180037b3f  jbe     short loc_180037BBD
0x180037b41  cmp     [rsp+1F0h+var_1B8], dil
0x180037b46  jz      short loc_180037B57
0x180037b48  lea     rdx, aIs2016andt32No; "Is2016andT32? not {"
0x180037b4f  mov     rcx, r15
0x180037b52  call    StrmPutStringEOL
0x180037b57  mov     r9, [r14+38h]
0x180037b5b  lea     r8, aS; " /%s"
0x180037b62  mov     edx, 100h; cchDest
0x180037b67  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x180037b6b  call    StringCchPrintfA
0x180037b70  cmp     di, bx
0x180037b73  jnz     loc_180037D7B
0x180037b79  cmp     [rbp+0F0h+var_140], dil
0x180037b7d  jz      short loc_180037BAB
0x180037b7f  lea     rax, [rbp+0F0h+var_140]
0x180037b83  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037b87  inc     r8
0x180037b8a  cmp     [rax+r8], dil
0x180037b8e  jnz     short loc_180037B87
0x180037b90  mov     r9b, 1
0x180037b93  lea     rdx, [rbp+0F0h+var_140]
0x180037b97  mov     rcx, r15
0x180037b9a  call    StrmPutBytes
0x180037b9f  movzx   ebx, ax
0x180037ba2  cmp     di, ax
0x180037ba5  jnz     loc_180037D7B
0x180037bab  lea     rdx, aFont; " /Font"
0x180037bb2  mov     r8d, 6
0x180037bb8  jmp     loc_180037CE3
0x180037bbd  mov     rax, [r14+30h]
0x180037bc1  mov     rcx, [rax+8]
0x180037bc5  test    byte ptr [rcx+5Ah], 40h
0x180037bc9  lea     rax, [rcx+5Ch]
0x180037bcd  jz      short loc_180037BE9
0x180037bcf  mov     r9, rax
0x180037bd2  lea     r8, aS_4; "/%s"
0x180037bd9  mov     edx, 100h; cchDest
0x180037bde  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x180037be2  call    StringCchPrintfA
0x180037be7  jmp     short loc_180037C2A
0x180037be9  lea     r8, aSS_0; "/%s%s"
0x180037bf0  mov     [rsp+1F0h+var_1D0], rax
0x180037bf5  cmp     [r14+88h], edi
0x180037bfc  jnz     short loc_180037C15
0x180037bfe  cmp     edx, 5
0x180037c01  lea     rcx, aAdbcfb; "ADBCFB+"
0x180037c08  lea     r9, aAdbcfa; "ADBCFA+"
0x180037c0f  cmovnz  r9, rcx
0x180037c13  jmp     short loc_180037C1C
0x180037c15  lea     r9, aAdbcff; "ADBCFF+"
0x180037c1c  mov     edx, 100h; cchDest
0x180037c21  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x180037c25  call    StringCchPrintfA
0x180037c2a  cmp     di, bx
0x180037c2d  jnz     loc_180037D7B
0x180037c33  cmp     [rbp+0F0h+var_140], dil
0x180037c37  jz      loc_180037CD6
0x180037c3d  lea     rax, [rbp+0F0h+var_140]
0x180037c41  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037c45  inc     r8
0x180037c48  cmp     [rax+r8], dil
0x180037c4c  jnz     short loc_180037C45
0x180037c4e  jmp     short loc_180037CBB
0x180037c50  mov     r9, [r14+38h]
0x180037c54  lea     r8, aS; " /%s"
0x180037c5b  mov     edx, 100h; cchDest
0x180037c60  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x180037c64  call    StringCchPrintfA
0x180037c69  jmp     short loc_180037C9B
0x180037c6b  mov     rax, [r14+30h]
0x180037c6f  lea     r8, aSS_1; " /%s%s"
0x180037c76  mov     edx, 100h; cchDest
0x180037c7b  lea     rcx, [rbp+0F0h+var_140]; pszDest
0x180037c7f  mov     r9, [rax+8]
0x180037c83  mov     rax, cs:gcidSuffix
0x180037c8a  add     r9, 96h
0x180037c91  mov     [rsp+1F0h+var_1D0], rax
0x180037c96  call    StringCchPrintfA
0x180037c9b  cmp     di, bx
0x180037c9e  jnz     loc_180037D7B
0x180037ca4  cmp     [rbp+0F0h+var_140], dil
0x180037ca8  jz      short loc_180037CD6
0x180037caa  lea     rax, [rbp+0F0h+var_140]
0x180037cae  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037cb2  inc     r8
0x180037cb5  cmp     [rax+r8], dil
0x180037cb9  jnz     short loc_180037CB2
0x180037cbb  mov     r9b, 1
0x180037cbe  lea     rdx, [rbp+0F0h+var_140]
0x180037cc2  mov     rcx, r15
0x180037cc5  call    StrmPutBytes
0x180037cca  movzx   ebx, ax
0x180037ccd  cmp     di, ax
0x180037cd0  jnz     loc_180037D7B
0x180037cd6  mov     r8d, 9
0x180037cdc  lea     rdx, aCidfont; " /CIDFont"
0x180037ce3  mov     r9b, 1
0x180037ce6  mov     rcx, r15
0x180037ce9  call    StrmPutBytes
0x180037cee  movzx   ebx, ax
0x180037cf1  cmp     di, ax
0x180037cf4  jnz     loc_180037D7B
0x180037cfa  mov     rcx, r15
0x180037cfd  test    r12b, r12b
0x180037d00  jz      short loc_180037D0B
0x180037d02  lea     rdx, aG2ubegin; " G2UBegin"
0x180037d09  jmp     short loc_180037D73
0x180037d0b  lea     rdx, aG2ccbegin; " G2CCBegin"
0x180037d12  call    StrmPutStringEOL
0x180037d17  movzx   ebx, ax
0x180037d1a  mov     rax, [r14+30h]
0x180037d1e  test    rax, rax
0x180037d21  jz      short loc_180037D7B
0x180037d23  mov     eax, [rax+58h]
0x180037d26  cmp     eax, 3
0x180037d29  jz      short loc_180037D69
0x180037d2b  cmp     eax, 8
0x180037d2e  jz      short loc_180037D69
0x180037d30  cmp     eax, 1
0x180037d33  jz      short loc_180037D60
0x180037d35  cmp     eax, 6
0x180037d38  jz      short loc_180037D60
0x180037d3a  cmp     eax, 2
0x180037d3d  jz      short loc_180037D57
0x180037d3f  cmp     eax, 7
0x180037d42  jz      short loc_180037D57
0x180037d44  cmp     eax, 4
0x180037d47  jz      short loc_180037D4E
0x180037d49  cmp     eax, 9
0x180037d4c  jnz     short loc_180037D7B
0x180037d4e  lea     rdx, aWincharset129D; "/WinCharSet 129 def"
0x180037d55  jmp     short loc_180037D70
0x180037d57  lea     rdx, aWincharset136D; "/WinCharSet 136 def"
0x180037d5e  jmp     short loc_180037D70
0x180037d60  lea     rdx, aWincharset134D; "/WinCharSet 134 def"
0x180037d67  jmp     short loc_180037D70
0x180037d69  lea     rdx, aWincharset128D; "/WinCharSet 128 def"
0x180037d70  mov     rcx, r15
0x180037d73  call    StrmPutStringEOL
0x180037d78  movzx   ebx, ax
0x180037d7b  test    bx, bx
0x180037d7e  jnz     short loc_180037DB0
0x180037d80  cmp     [rsp+1F0h+pszDest], dil
0x180037d85  jz      short loc_180037DAB
0x180037d87  lea     rax, [rsp+1F0h+pszDest]
0x180037d8c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037d90  inc     r8
0x180037d93  cmp     [rax+r8], dil
0x180037d97  jnz     short loc_180037D90
0x180037d99  mov     r9b, 1
0x180037d9c  lea     rdx, [rsp+1F0h+pszDest]
0x180037da1  mov     rcx, r15
0x180037da4  call    StrmPutBytes
0x180037da9  jmp     short loc_180037DAD
0x180037dab  mov     eax, edi
0x180037dad  movzx   ebx, ax
  ... truncated ...
```

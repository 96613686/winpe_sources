# sqlite3CreateForeignKey

- ea: `0x18000d01c`
- end: `0x18000d478`
- name: `sqlite3CreateForeignKey`
- size: `1116`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180031b38`

## callees

- `0x180005810`
- `0x18000aa60`
- `0x18000aac0`
- `0x18000c500`
- `0x18000cb64`
- `0x18000d01c`
- `0x18000eb10`
- `0x18000f720`
- `0x180060ce8`
- `0x180064ef0`
- `0x180068404`
- `0x180086e98`
- `0x180099814`

## pseudocode

```c
void __fastcall sqlite3CreateForeignKey(__int64 a1, _DWORD *a2, __int64 a3, _DWORD *a4, __int16 a5)
{
  __int64 v5; // r13
  _QWORD *v7; // rsi
  _DWORD *v9; // rbp
  int v11; // r12d
  __int64 v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rax
  int j; // r10d
  int v21; // edx
  __int64 v22; // r8
  unsigned __int8 *v23; // rbx
  _BYTE *k; // r11
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r12
  char *v28; // r12
  __int64 v29; // rsi
  __int64 v30; // r9
  __int64 v31; // rax
  __int64 v32; // rbp
  __int64 v33; // rbp
  int i; // r8d
  int v35; // eax
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rdx
  _QWORD *v39; // [rsp+28h] [rbp-40h]
  int v40; // [rsp+70h] [rbp+8h]
  int v42; // [rsp+88h] [rbp+20h]
  int v43; // [rsp+88h] [rbp+20h]

  v5 = *(_QWORD *)(a1 + 352);
  v7 = *(_QWORD **)a1;
  v39 = *(_QWORD **)a1;
  v9 = a2;
  if ( !v5 || *(_BYTE *)(a1 + 308) == 1 )
    goto LABEL_42;
  if ( a2 )
  {
    if ( a4 && *a4 != *a2 )
    {
      sqlite3ErrorMsg(
        a1,
        "number of columns in foreign key does not match the number of columns in the referenced table");
LABEL_43:
      exprListDeleteNN((__int64)v7, v9);
LABEL_44:
      if ( !a4 )
        return;
      goto LABEL_45;
    }
    v11 = *a2;
LABEL_7:
    v12 = 16LL * (v11 - 1) + *(unsigned int *)(a3 + 8) + 81LL;
    v40 = v11;
    if ( a4 )
    {
      for ( i = 0; i < *a4; v12 = v37 + v35 + v38 )
      {
        v35 = sqlite3Strlen30(*(_QWORD *)&a4[8 * i + 4]);
        i = v37 + v36;
      }
    }
    v13 = (_QWORD *)sqlite3DbMallocZero(v7, v12);
    v14 = v13;
    if ( v13 )
    {
      *v13 = v5;
      v13[1] = *(_QWORD *)(v5 + 72);
      v15 = &v13[2 * v11 + 8];
      v14[2] = v15;
      if ( *(_BYTE *)(a1 + 308) >= 2u )
      {
        sqlite3RenameTokenMap(a1, &v14[2 * v11 + 8], a3);
        v15 = &v14[2 * v11 + 8];
      }
      memcpy_0(v15, *(const void **)a3, *(unsigned int *)(a3 + 8));
      *((_BYTE *)&v14[2 * v11 + 8] + *(unsigned int *)(a3 + 8)) = 0;
      sqlite3Dequote();
      v42 = *(_DWORD *)(a3 + 8);
      *((_DWORD *)v14 + 10) = v11;
      if ( v9 )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= v11 )
          {
            v16 = &v14[2 * v11 + 8];
            goto LABEL_13;
          }
          v21 = 0;
          v22 = 8LL * j;
LABEL_21:
          if ( v21 < *(__int16 *)(v5 + 54) )
          {
            v23 = *(unsigned __int8 **)&v9[v22 + 4];
            for ( k = *(_BYTE **)(*(_QWORD *)(v5 + 8) + 24LL * v21); ; ++k )
            {
              v17 = (unsigned __int8)*k;
              v25 = *v23;
              if ( (_DWORD)v17 == (_DWORD)v25 )
              {
                if ( !*k )
                {
                  v26 = j;
                  LODWORD(v14[2 * j + 8]) = v21;
                  goto LABEL_29;
                }
              }
              else
              {
                v17 = (unsigned __int64)qword_18009E760;
                if ( *((unsigned __int8 *)qword_18009E760 + (unsigned __int8)*k) != *((unsigned __int8 *)qword_18009E760
                                                                                    + v25) )
                {
                  ++v21;
                  goto LABEL_21;
                }
              }
              ++v23;
            }
          }
          v26 = j;
LABEL_29:
          if ( v21 >= *(__int16 *)(v5 + 54) )
            break;
          if ( *(_BYTE *)(a1 + 308) >= 2u )
            sqlite3RenameTokenRemap(a1, &v14[2 * v26 + 8], *(_QWORD *)&v9[v22 + 4], v17);
        }
        sqlite3ErrorMsg(a1, "unknown column \"%s\" in foreign key definition", *(const char **)&v9[v22 + 4]);
      }
      else
      {
        *((_DWORD *)v14 + 16) = *(__int16 *)(v5 + 54) - 1;
LABEL_13:
        if ( a4 )
        {
          v27 = (unsigned int)(v42 + 1);
          v43 = 0;
          v28 = (char *)v16 + v27;
          if ( v40 > 0 )
          {
            v29 = 0;
            do
            {
              v30 = 8 * v29;
              v31 = *(_QWORD *)&a4[8 * v29 + 4];
              if ( v31 )
              {
                v32 = -1;
                do
                  ++v32;
                while ( *(_BYTE *)(v31 + v32) );
                v33 = v32 & 0x3FFFFFFF;
              }
              else
              {
                v33 = 0;
              }
              v14[2 * v29 + 9] = v28;
              if ( *(_BYTE *)(a1 + 308) >= 2u )
                sqlite3RenameTokenRemap(a1, v28, *(_QWORD *)&a4[v30 + 4], v30 * 4);
              memcpy_0(v28, *(const void **)&a4[v30 + 4], (unsigned int)v33);
              v28[v33] = 0;
              v28 += (unsigned int)(v33 + 1);
              ++v29;
              ++v43;
            }
            while ( v43 < v40 );
            v7 = v39;
            v9 = a2;
          }
        }
        v18 = v14[2];
        *(_WORD *)((char *)v14 + 45) = a5;
        *((_BYTE *)v14 + 44) = 0;
        v19 = sqlite3HashInsert(*(_QWORD *)(v5 + 96) + 80LL, v18, v14);
        if ( (_QWORD *)v19 != v14 )
        {
          if ( v19 )
          {
            v14[3] = v19;
            *(_QWORD *)(v19 + 32) = v14;
          }
          *(_QWORD *)(v5 + 72) = v14;
          goto LABEL_42;
        }
        sqlite3OomFault(v7);
      }
      if ( v7 )
      {
        if ( (unsigned __int64)v14 < v7[62] )
        {
          if ( (unsigned __int64)v14 >= v7[60] )
          {
            *v14 = v7[59];
            v7[59] = v14;
            goto LABEL_42;
          }
          if ( (unsigned __int64)v14 >= v7[61] )
          {
            *v14 = v7[57];
            v7[57] = v14;
            goto LABEL_42;
          }
        }
        if ( v7[97] )
        {
          measureAllocationSize(v7, v14);
          goto LABEL_42;
        }
      }
      sqlite3_free(v14);
    }
LABEL_42:
    if ( !v9 )
      goto LABEL_44;
    goto LABEL_43;
  }
  if ( *(__int16 *)(v5 + 54) < 1 )
    goto LABEL_44;
  if ( !a4 || *a4 == 1 )
  {
    v11 = 1;
    goto LABEL_7;
  }
  sqlite3ErrorMsg(
    a1,
    "foreign key on %s should reference only one column of table %T",
    *(_QWORD *)(*(_QWORD *)(v5 + 8) + 24LL * *(__int16 *)(v5 + 54) - 24),
    a3);
LABEL_45:
  exprListDeleteNN((__int64)v7, a4);
}

```

## disassembly

```asm
0x18000d01c  mov     [rsp+arg_10], rbx
0x18000d021  mov     [rsp+arg_8], rdx
0x18000d026  push    rbp
0x18000d027  push    rsi
0x18000d028  push    rdi
0x18000d029  push    r12
0x18000d02b  push    r13
0x18000d02d  push    r14
0x18000d02f  push    r15
0x18000d031  sub     rsp, 30h
0x18000d035  mov     r13, [rcx+160h]
0x18000d03c  mov     r14, r9
0x18000d03f  mov     rsi, [rcx]
0x18000d042  mov     rbx, r8
0x18000d045  mov     [rsp+68h+var_40], rsi
0x18000d04a  mov     rbp, rdx
0x18000d04d  mov     r15, rcx
0x18000d050  test    r13, r13
0x18000d053  jz      loc_18000D26C
0x18000d059  mov     r9d, 1
0x18000d05f  cmp     [rcx+134h], r9b
0x18000d066  jz      loc_18000D26C
0x18000d06c  test    rdx, rdx
0x18000d06f  jz      loc_18000D229
0x18000d075  test    r14, r14
0x18000d078  jz      short loc_18000D085
0x18000d07a  mov     eax, [rdx]
0x18000d07c  cmp     [r14], eax
0x18000d07f  jnz     loc_18000D416
0x18000d085  mov     r12d, [rdx]
0x18000d088  mov     edx, [r8+8]
0x18000d08c  lea     eax, [r12-1]
0x18000d091  add     rdx, 51h ; 'Q'
0x18000d095  movsxd  rcx, eax
0x18000d098  shl     rcx, 4
0x18000d09c  add     rdx, rcx
0x18000d09f  mov     [rsp+68h+arg_0], r12d
0x18000d0a4  test    r14, r14
0x18000d0a7  jnz     loc_18000D399
0x18000d0ad  mov     rcx, rsi
0x18000d0b0  call    sqlite3DbMallocZero
0x18000d0b5  mov     rdi, rax
0x18000d0b8  test    rax, rax
0x18000d0bb  jz      loc_18000D26C
0x18000d0c1  mov     [rax], r13
0x18000d0c4  mov     rax, [r13+48h]
0x18000d0c8  mov     [rdi+8], rax
0x18000d0cc  movsxd  rax, r12d
0x18000d0cf  add     rax, 4
0x18000d0d3  shl     rax, 4
0x18000d0d7  add     rax, rdi
0x18000d0da  mov     [rdi+10h], rax
0x18000d0de  cmp     byte ptr [r15+134h], 2
0x18000d0e6  mov     [rsp+68h+var_48], rax
0x18000d0eb  jnb     loc_18000D427
0x18000d0f1  mov     r8d, [rbx+8]; Size
0x18000d0f5  mov     rcx, rax; void *
0x18000d0f8  mov     rdx, [rbx]; Src
0x18000d0fb  call    memcpy_0
0x18000d100  mov     eax, [rbx+8]
0x18000d103  mov     rcx, [rsp+68h+var_48]
0x18000d108  mov     byte ptr [rax+rcx], 0
0x18000d10c  call    sqlite3Dequote
0x18000d111  mov     eax, [rbx+8]
0x18000d114  mov     [rsp+68h+arg_18], eax
0x18000d11b  mov     [rdi+28h], r12d
0x18000d11f  test    rbp, rbp
0x18000d122  jnz     short loc_18000D17E
0x18000d124  movsx   eax, word ptr [r13+36h]
0x18000d129  dec     eax
0x18000d12b  mov     [rdi+40h], eax
0x18000d12e  test    r14, r14
0x18000d131  jnz     loc_18000D2EE
0x18000d137  mov     eax, [rsp+68h+arg_20]
0x18000d13e  mov     r8, rdi
0x18000d141  mov     rdx, [rdi+10h]
0x18000d145  mov     [rdi+2Dh], al
0x18000d148  sar     eax, 8
0x18000d14b  mov     [rdi+2Eh], al
0x18000d14e  mov     byte ptr [rdi+2Ch], 0
0x18000d152  mov     rcx, [r13+60h]
0x18000d156  add     rcx, 50h ; 'P'
0x18000d15a  call    sqlite3HashInsert
0x18000d15f  cmp     rax, rdi
0x18000d162  jz      loc_18000D241
0x18000d168  test    rax, rax
0x18000d16b  jz      short loc_18000D175
0x18000d16d  mov     [rdi+18h], rax
0x18000d171  mov     [rax+20h], rdi
0x18000d175  mov     [r13+48h], rdi
0x18000d179  jmp     loc_18000D26C
0x18000d17e  xor     r10d, r10d
0x18000d181  cmp     r10d, r12d
0x18000d184  jge     loc_18000D21F
0x18000d18a  xor     edx, edx
0x18000d18c  movsxd  r8, r10d
0x18000d18f  shl     r8, 5
0x18000d193  movsx   eax, word ptr [r13+36h]
0x18000d198  cmp     edx, eax
0x18000d19a  jge     loc_18000D2E6
0x18000d1a0  mov     rbx, [r8+rbp+10h]
0x18000d1a5  movsxd  rax, edx
0x18000d1a8  lea     rcx, [rax+rax*2]
0x18000d1ac  mov     rax, [r13+8]
0x18000d1b0  mov     r11, [rax+rcx*8]
0x18000d1b4  movzx   r9d, byte ptr [r11]
0x18000d1b8  movzx   eax, byte ptr [rbx]
0x18000d1bb  cmp     r9d, eax
0x18000d1be  jnz     short loc_18000D1CD
0x18000d1c0  test    r9d, r9d
0x18000d1c3  jz      short loc_18000D1EF
0x18000d1c5  inc     r11
0x18000d1c8  inc     rbx
0x18000d1cb  jmp     short loc_18000D1B4
0x18000d1cd  lea     rcx, qword_18009E760
0x18000d1d4  movzx   ecx, byte ptr [rax+rcx]
0x18000d1d8  mov     rax, r9
0x18000d1db  lea     r9, qword_18009E760
0x18000d1e2  movzx   eax, byte ptr [rax+r9]
0x18000d1e7  cmp     eax, ecx
0x18000d1e9  jz      short loc_18000D1C5
0x18000d1eb  inc     edx
0x18000d1ed  jmp     short loc_18000D193
0x18000d1ef  movsxd  rcx, r10d
0x18000d1f2  lea     rax, [rcx+4]
0x18000d1f6  add     rax, rax
0x18000d1f9  mov     [rdi+rax*8], edx
0x18000d1fc  movsx   eax, word ptr [r13+36h]
0x18000d201  cmp     edx, eax
0x18000d203  jge     loc_18000D3CB
0x18000d209  cmp     byte ptr [r15+134h], 2
0x18000d211  jnb     loc_18000D43F
0x18000d217  inc     r10d
0x18000d21a  jmp     loc_18000D181
0x18000d21f  mov     rcx, [rsp+68h+var_48]
0x18000d224  jmp     loc_18000D12E
0x18000d229  cmp     [r13+36h], r9w
0x18000d22e  jl      short loc_18000D27C
0x18000d230  test    r14, r14
0x18000d233  jnz     loc_18000D3E4
0x18000d239  mov     r12d, r9d
0x18000d23c  jmp     loc_18000D088
0x18000d241  mov     rcx, rsi
0x18000d244  call    sqlite3OomFault
0x18000d249  test    rsi, rsi
0x18000d24c  jz      short loc_18000D2C9
0x18000d24e  cmp     rdi, [rsi+1F0h]
0x18000d255  jb      short loc_18000D2A4
0x18000d257  cmp     qword ptr [rsi+308h], 0
0x18000d25f  jz      short loc_18000D2C9
0x18000d261  mov     rdx, rdi
0x18000d264  mov     rcx, rsi
0x18000d267  call    measureAllocationSize
0x18000d26c  test    rbp, rbp
0x18000d26f  jz      short loc_18000D27C
0x18000d271  mov     rdx, rbp
0x18000d274  mov     rcx, rsi
0x18000d277  call    exprListDeleteNN
0x18000d27c  test    r14, r14
0x18000d27f  jz      short loc_18000D28C
0x18000d281  mov     rdx, r14
0x18000d284  mov     rcx, rsi
0x18000d287  call    exprListDeleteNN
0x18000d28c  mov     rbx, [rsp+68h+arg_10]
0x18000d294  add     rsp, 30h
0x18000d298  pop     r15
0x18000d29a  pop     r14
0x18000d29c  pop     r13
0x18000d29e  pop     r12
0x18000d2a0  pop     rdi
0x18000d2a1  pop     rsi
0x18000d2a2  pop     rbp
0x18000d2a3  retn
0x18000d2a4  cmp     rdi, [rsi+1E0h]
0x18000d2ab  jnb     short loc_18000D2D3
0x18000d2ad  cmp     rdi, [rsi+1E8h]
0x18000d2b4  jb      short loc_18000D257
0x18000d2b6  mov     rax, [rsi+1C8h]
0x18000d2bd  mov     [rdi], rax
0x18000d2c0  mov     [rsi+1C8h], rdi
0x18000d2c7  jmp     short loc_18000D26C
0x18000d2c9  mov     rcx, rdi
0x18000d2cc  call    sqlite3_free
0x18000d2d1  jmp     short loc_18000D26C
0x18000d2d3  mov     rax, [rsi+1D8h]
0x18000d2da  mov     [rdi], rax
0x18000d2dd  mov     [rsi+1D8h], rdi
0x18000d2e4  jmp     short loc_18000D26C
0x18000d2e6  movsxd  rcx, r10d
0x18000d2e9  jmp     loc_18000D1FC
0x18000d2ee  mov     r12d, [rsp+68h+arg_18]
0x18000d2f6  inc     r12d
0x18000d2f9  mov     [rsp+68h+arg_18], 0
0x18000d304  add     r12, rcx
0x18000d307  cmp     [rsp+68h+arg_0], 0
0x18000d30c  jle     loc_18000D137
0x18000d312  xor     esi, esi
0x18000d314  mov     r9, rsi
0x18000d317  shl     r9, 5
0x18000d31b  mov     rax, [r9+r14+10h]
0x18000d320  test    rax, rax
0x18000d323  jz      loc_18000D45C
0x18000d329  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000d32d  inc     rbp
0x18000d330  cmp     byte ptr [rax+rbp], 0
0x18000d334  jnz     short loc_18000D32D
0x18000d336  and     ebp, 3FFFFFFFh
0x18000d33c  mov     rax, rsi
0x18000d33f  add     rax, rax
0x18000d342  mov     [rdi+rax*8+48h], r12
0x18000d347  cmp     byte ptr [r15+134h], 2
0x18000d34f  jnb     loc_18000D463
0x18000d355  mov     rdx, [r9+r14+10h]; Src
0x18000d35a  mov     rcx, r12; void *
0x18000d35d  mov     r8d, ebp; Size
0x18000d360  call    memcpy_0
0x18000d365  lea     ecx, [rbp+1]
0x18000d368  mov     byte ptr [rbp+r12+0], 0
0x18000d36e  add     r12, rcx
0x18000d371  inc     rsi
0x18000d374  mov     ecx, [rsp+68h+arg_18]
0x18000d37b  inc     ecx
0x18000d37d  mov     [rsp+68h+arg_18], ecx
0x18000d384  cmp     ecx, [rsp+68h+arg_0]
0x18000d388  jl      short loc_18000D314
0x18000d38a  mov     rsi, [rsp+68h+var_40]
0x18000d38f  mov     rbp, [rsp+68h+arg_8]
0x18000d394  jmp     loc_18000D137
0x18000d399  xor     r8d, r8d
0x18000d39c  cmp     [r14], r8d
0x18000d39f  jle     loc_18000D0AD
0x18000d3a5  mov     ecx, r8d
0x18000d3a8  shl     rcx, 5
0x18000d3ac  mov     rcx, [rcx+r14+10h]
0x18000d3b1  call    sqlite3Strlen30
0x18000d3b6  add     eax, r9d
0x18000d3b9  add     r8d, r9d
0x18000d3bc  cdqe
0x18000d3be  add     rdx, rax
0x18000d3c1  cmp     r8d, [r14]
0x18000d3c4  jl      short loc_18000D3A5
0x18000d3c6  jmp     loc_18000D0AD
0x18000d3cb  mov     r8, [r8+rbp+10h]
0x18000d3d0  lea     rdx, aUnknownColumnS; "unknown column \"%s\" in foreign key de"...
0x18000d3d7  mov     rcx, r15
0x18000d3da  call    sqlite3ErrorMsg
0x18000d3df  jmp     loc_18000D249
0x18000d3e4  cmp     [r14], r9d
0x18000d3e7  jz      loc_18000D239
0x18000d3ed  movsx   rax, word ptr [r13+36h]
0x18000d3f2  lea     rdx, aForeignKeyOnSS; "foreign key on %s should reference only"...
0x18000d3f9  mov     r8, [r13+8]
0x18000d3fd  mov     r9, rbx
0x18000d400  lea     rcx, [rax+rax*2]
0x18000d404  mov     r8, [r8+rcx*8-18h]
0x18000d409  mov     rcx, r15
0x18000d40c  call    sqlite3ErrorMsg
0x18000d411  jmp     loc_18000D281
0x18000d416  lea     rdx, aNumberOfColumn; "number of columns in foreign key does n"...
0x18000d41d  call    sqlite3ErrorMsg
0x18000d422  jmp     loc_18000D271
0x18000d427  mov     r8, rbx
0x18000d42a  mov     rdx, rax
0x18000d42d  mov     rcx, r15
0x18000d430  call    sqlite3RenameTokenMap
0x18000d435  mov     rax, [rsp+68h+var_48]
0x18000d43a  jmp     loc_18000D0F1
0x18000d43f  mov     r8, [r8+rbp+10h]
0x18000d444  lea     rdx, [rcx+4]
0x18000d448  shl     rdx, 4
0x18000d44c  mov     rcx, r15
0x18000d44f  add     rdx, rdi
0x18000d452  call    sqlite3RenameTokenRemap
0x18000d457  jmp     loc_18000D217
0x18000d45c  xor     ebp, ebp
0x18000d45e  jmp     loc_18000D33C
0x18000d463  mov     r8, [r9+r14+10h]
0x18000d468  mov     rdx, r12
0x18000d46b  mov     rcx, r15
0x18000d46e  call    sqlite3RenameTokenRemap
0x18000d473  jmp     loc_18000D355
```

# sqlite3CreateForeignKey

- ea: `0x180073198`
- end: `0x18007350a`
- name: `sqlite3CreateForeignKey`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18000213c`

## callees

- `0x18000a710`
- `0x180011bcc`
- `0x18001bc40`
- `0x18001eb90`
- `0x18003bc90`
- `0x18003d110`
- `0x18003d310`
- `0x18003d380`
- `0x180041d10`
- `0x18005df58`
- `0x18006dc30`
- `0x180073198`
- `0x1800af620`

## pseudocode

```c
__int64 __fastcall sqlite3CreateForeignKey(__int64 a1, int *a2, __int64 a3, _DWORD *a4, __int16 a5)
{
  __int64 v5; // rbp
  _QWORD *v6; // rdi
  _QWORD *v7; // r15
  int v12; // r13d
  __int64 v13; // rdx
  int i; // r8d
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  char *v21; // r15
  __int64 v22; // rdx
  __int64 v23; // r9
  size_t v24; // r10
  __int64 v25; // rdx
  size_t v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // rax
  int j; // r9d
  int v30; // r11d
  __int64 v31; // rbx
  __int64 v32; // rcx
  int v34; // [rsp+20h] [rbp-68h]
  _QWORD *v35; // [rsp+28h] [rbp-60h]
  __int64 v36; // [rsp+30h] [rbp-58h]
  __int64 v37; // [rsp+30h] [rbp-58h]
  _QWORD *v38; // [rsp+38h] [rbp-50h]
  int v39; // [rsp+90h] [rbp+8h]
  int v40; // [rsp+90h] [rbp+8h]

  v5 = *(_QWORD *)(a1 + 352);
  v6 = 0;
  v7 = *(_QWORD **)a1;
  v38 = *(_QWORD **)a1;
  if ( v5 && *(_BYTE *)(a1 + 308) != 1 )
  {
    if ( a2 )
    {
      if ( a4 && *a4 != *a2 )
      {
        sqlite3ErrorMsg(
          a1,
          "number of columns in foreign key does not match the number of columns in the referenced table");
        goto LABEL_46;
      }
      v12 = *a2;
    }
    else
    {
      if ( *(__int16 *)(v5 + 54) < 1 )
        goto LABEL_46;
      if ( a4 && *a4 != 1 )
      {
        sqlite3ErrorMsg(
          a1,
          "foreign key on %s should reference only one column of table %T",
          *(_QWORD *)(*(_QWORD *)(v5 + 8) + 24LL * *(__int16 *)(v5 + 54) - 24),
          a3);
        goto LABEL_46;
      }
      v12 = 1;
    }
    v13 = 16LL * (v12 - 1) + *(unsigned int *)(a3 + 8) + 81LL;
    if ( a4 )
    {
      for ( i = 0; i < *a4; v13 = v17 + v15 + v18 )
      {
        v15 = sqlite3Strlen30(*(_QWORD *)&a4[8 * i + 4]);
        i = v17 + v16;
      }
    }
    v19 = (_QWORD *)sqlite3DbMallocZero(v7, v13);
    v6 = v19;
    if ( v19 )
    {
      *v19 = v5;
      v19[1] = *(_QWORD *)(v5 + 72);
      v20 = &v19[2 * v12 + 8];
      v6[2] = v20;
      v35 = &v6[2 * v12 + 8];
      if ( *(_BYTE *)(a1 + 308) >= 2u )
      {
        sqlite3RenameTokenMap(a1, &v6[2 * v12 + 8], a3);
        v20 = &v6[2 * v12 + 8];
      }
      memcpy_0(v20, *(const void **)a3, *(unsigned int *)(a3 + 8));
      *((_BYTE *)v35 + *(unsigned int *)(a3 + 8)) = 0;
      sqlite3Dequote(v35);
      v34 = *(_DWORD *)(a3 + 8);
      *((_DWORD *)v6 + 10) = v12;
      if ( a2 )
      {
        for ( j = 0; ; j = v40 + 1 )
        {
          v40 = j;
          if ( j >= v12 )
            break;
          v30 = 0;
          v37 = j;
          v31 = 8LL * j;
          while ( v30 < *(__int16 *)(v5 + 54) )
          {
            if ( !(unsigned int)sqlite3StrICmp(*(_QWORD *)(*(_QWORD *)(v5 + 8) + 24LL * v30), *(_QWORD *)&a2[v31 + 4]) )
            {
              v32 = v37;
              LODWORD(v6[2 * v37 + 8]) = v30;
              goto LABEL_38;
            }
            ++v30;
          }
          v32 = v37;
LABEL_38:
          if ( v30 >= *(__int16 *)(v5 + 54) )
          {
            sqlite3ErrorMsg(a1, "unknown column \"%s\" in foreign key definition", *(const char **)&a2[v31 + 4]);
            goto LABEL_46;
          }
          if ( *(_BYTE *)(a1 + 308) >= 2u )
            sqlite3RenameTokenRemap(a1, &v6[2 * v32 + 8]);
        }
      }
      else
      {
        *((_DWORD *)v6 + 16) = *(__int16 *)(v5 + 54) - 1;
      }
      if ( a4 )
      {
        v39 = 0;
        v21 = (char *)v35 + (unsigned int)(v34 + 1);
        if ( v12 > 0 )
        {
          v22 = 0;
          v36 = 0;
          do
          {
            v24 = (int)sqlite3Strlen30(*(_QWORD *)&a4[8 * v22 + 4]);
            v6[2 * v25 + 9] = v21;
            if ( *(_BYTE *)(a1 + 308) >= 2u )
              sqlite3RenameTokenRemap(a1, v21);
            v26 = v24;
            memcpy_0(v21, *(const void **)((char *)a4 + v23 + 16), v24);
            v22 = v36 + 1;
            v21[v26] = 0;
            v21 += (int)v26 + 1;
            ++v39;
            ++v36;
          }
          while ( v39 < v12 );
        }
        v7 = v38;
      }
      v27 = v6[2];
      *(_WORD *)((char *)v6 + 45) = a5;
      *((_BYTE *)v6 + 44) = 0;
      v28 = sqlite3HashInsert(*(_QWORD *)(v5 + 96) + 80LL, v27, v6);
      if ( (_QWORD *)v28 == v6 )
      {
        sqlite3OomFault(v7);
      }
      else
      {
        if ( v28 )
        {
          v6[3] = v28;
          *(_QWORD *)(v28 + 32) = v6;
        }
        *(_QWORD *)(v5 + 72) = v6;
        v6 = 0;
      }
    }
  }
LABEL_46:
  sqlite3DbFree(v7, v6);
  sqlite3ExprListDeleteGeneric(v7, a2);
  return sqlite3ExprListDeleteGeneric(v7, a4);
}

```

## disassembly

```asm
0x180073198  push    rbx
0x18007319a  push    rbp
0x18007319b  push    rsi
0x18007319c  push    rdi
0x18007319d  push    r12
0x18007319f  push    r13
0x1800731a1  push    r14
0x1800731a3  push    r15
0x1800731a5  sub     rsp, 48h
0x1800731a9  mov     rbp, [rcx+160h]
0x1800731b0  xor     edi, edi
0x1800731b2  mov     r15, [rcx]
0x1800731b5  mov     rsi, r9
0x1800731b8  mov     [rsp+88h+var_50], r15
0x1800731bd  mov     rbx, r8
0x1800731c0  mov     r12, rdx
0x1800731c3  mov     r14, rcx
0x1800731c6  test    rbp, rbp
0x1800731c9  jz      loc_1800734D9
0x1800731cf  lea     r9d, [rdi+1]
0x1800731d3  cmp     [rcx+134h], r9b
0x1800731da  jz      loc_1800734D9
0x1800731e0  test    rdx, rdx
0x1800731e3  jnz     short loc_180073228
0x1800731e5  cmp     [rbp+36h], r9w
0x1800731ea  jl      loc_1800734D9
0x1800731f0  test    rsi, rsi
0x1800731f3  jz      short loc_180073223
0x1800731f5  cmp     [rsi], r9d
0x1800731f8  jz      short loc_180073223
0x1800731fa  movsx   rax, word ptr [rbp+36h]
0x1800731ff  lea     rdx, aForeignKeyOnSS; "foreign key on %s should reference only"...
0x180073206  mov     r8, [rbp+8]
0x18007320a  mov     r9, rbx
0x18007320d  lea     rcx, [rax+rax*2]
0x180073211  mov     r8, [r8+rcx*8-18h]
0x180073216  mov     rcx, r14
0x180073219  call    sqlite3ErrorMsg
0x18007321e  jmp     loc_1800734D9
0x180073223  mov     r13d, r9d
0x180073226  jmp     short loc_180073247
0x180073228  test    rsi, rsi
0x18007322b  jz      short loc_180073244
0x18007322d  mov     eax, [rdx]
0x18007322f  cmp     [rsi], eax
0x180073231  jz      short loc_180073244
0x180073233  lea     rdx, aNumberOfColumn; "number of columns in foreign key does n"...
0x18007323a  call    sqlite3ErrorMsg
0x18007323f  jmp     loc_1800734D9
0x180073244  mov     r13d, [rdx]
0x180073247  mov     edx, [r8+8]
0x18007324b  lea     eax, [r13-1]
0x18007324f  add     rdx, 51h ; 'Q'
0x180073253  movsxd  rcx, eax
0x180073256  shl     rcx, 4
0x18007325a  add     rdx, rcx
0x18007325d  test    rsi, rsi
0x180073260  jz      short loc_18007328A
0x180073262  xor     r8d, r8d
0x180073265  cmp     [rsi], edi
0x180073267  jle     short loc_18007328A
0x180073269  mov     ecx, r8d
0x18007326c  shl     rcx, 5
0x180073270  mov     rcx, [rcx+rsi+10h]
0x180073275  call    sqlite3Strlen30
0x18007327a  add     eax, r9d
0x18007327d  add     r8d, r9d
0x180073280  cdqe
0x180073282  add     rdx, rax
0x180073285  cmp     r8d, [rsi]
0x180073288  jl      short loc_180073269
0x18007328a  mov     rcx, r15
0x18007328d  call    sqlite3DbMallocZero
0x180073292  mov     rdi, rax
0x180073295  test    rax, rax
0x180073298  jz      loc_1800734D9
0x18007329e  mov     [rax], rbp
0x1800732a1  mov     rax, [rbp+48h]
0x1800732a5  mov     [rdi+8], rax
0x1800732a9  movsxd  rax, r13d
0x1800732ac  add     rax, 4
0x1800732b0  shl     rax, 4
0x1800732b4  add     rax, rdi
0x1800732b7  mov     [rdi+10h], rax
0x1800732bb  cmp     byte ptr [r14+134h], 2
0x1800732c3  mov     [rsp+88h+var_60], rax
0x1800732c8  jb      short loc_1800732DD
0x1800732ca  mov     r8, rbx
0x1800732cd  mov     rdx, rax
0x1800732d0  mov     rcx, r14
0x1800732d3  call    sqlite3RenameTokenMap
0x1800732d8  mov     rax, [rsp+88h+var_60]
0x1800732dd  mov     r8d, [rbx+8]; Size
0x1800732e1  mov     rcx, rax; void *
0x1800732e4  mov     rdx, [rbx]; Src
0x1800732e7  call    memcpy_0
0x1800732ec  mov     eax, [rbx+8]
0x1800732ef  mov     rcx, [rsp+88h+var_60]
0x1800732f4  mov     byte ptr [rax+rcx], 0
0x1800732f8  call    sqlite3Dequote
0x1800732fd  mov     eax, [rbx+8]
0x180073300  mov     [rsp+88h+var_68], eax
0x180073304  mov     [rdi+28h], r13d
0x180073308  test    r12, r12
0x18007330b  jnz     loc_18007340D
0x180073311  movsx   eax, word ptr [rbp+36h]
0x180073315  dec     eax
0x180073317  mov     [rdi+40h], eax
0x18007331a  test    rsi, rsi
0x18007331d  jz      loc_1800733CF
0x180073323  mov     r15d, [rsp+88h+var_68]
0x180073328  inc     r15d
0x18007332b  mov     [rsp+88h+arg_0], 0
0x180073336  add     r15, [rsp+88h+var_60]
0x18007333b  test    r13d, r13d
0x18007333e  jle     loc_1800733CA
0x180073344  xor     edx, edx
0x180073346  mov     [rsp+88h+var_58], rdx
0x18007334b  mov     r9, rdx
0x18007334e  shl     r9, 5
0x180073352  mov     rcx, [r9+rsi+10h]
0x180073357  call    sqlite3Strlen30
0x18007335c  mov     rcx, rdx
0x18007335f  movsxd  r10, eax
0x180073362  add     rcx, rcx
0x180073365  mov     [rdi+rcx*8+48h], r15
0x18007336a  cmp     byte ptr [r14+134h], 2
0x180073372  jb      short loc_180073384
0x180073374  mov     r8, [r9+rsi+10h]
0x180073379  mov     rdx, r15
0x18007337c  mov     rcx, r14
0x18007337f  call    sqlite3RenameTokenRemap
0x180073384  mov     rdx, [r9+rsi+10h]; Src
0x180073389  mov     r8, r10; Size
0x18007338c  mov     rcx, r15; void *
0x18007338f  mov     rbx, r10
0x180073392  call    memcpy_0
0x180073397  mov     r8d, [rsp+88h+arg_0]
0x18007339f  lea     eax, [rbx+1]
0x1800733a2  mov     rdx, [rsp+88h+var_58]
0x1800733a7  inc     r8d
0x1800733aa  inc     rdx
0x1800733ad  movsxd  rcx, eax
0x1800733b0  mov     byte ptr [rbx+r15], 0
0x1800733b5  add     r15, rcx
0x1800733b8  mov     [rsp+88h+arg_0], r8d
0x1800733c0  mov     [rsp+88h+var_58], rdx
0x1800733c5  cmp     r8d, r13d
0x1800733c8  jl      short loc_18007334B
0x1800733ca  mov     r15, [rsp+88h+var_50]
0x1800733cf  mov     eax, [rsp+88h+arg_20]
0x1800733d6  mov     r8, rdi
0x1800733d9  mov     rdx, [rdi+10h]
0x1800733dd  mov     [rdi+2Dh], al
0x1800733e0  sar     eax, 8
0x1800733e3  mov     [rdi+2Eh], al
0x1800733e6  mov     byte ptr [rdi+2Ch], 0
0x1800733ea  mov     rcx, [rbp+60h]
0x1800733ee  add     rcx, 50h ; 'P'
0x1800733f2  call    sqlite3HashInsert
0x1800733f7  cmp     rax, rdi
0x1800733fa  jnz     loc_1800734C6
0x180073400  mov     rcx, r15
0x180073403  call    sqlite3OomFault
0x180073408  jmp     loc_1800734D9
0x18007340d  xor     r9d, r9d
0x180073410  mov     [rsp+88h+arg_0], r9d
0x180073418  cmp     r9d, r13d
0x18007341b  jge     loc_18007331A
0x180073421  movsxd  rcx, r9d
0x180073424  xor     r11d, r11d
0x180073427  mov     rbx, rcx
0x18007342a  mov     [rsp+88h+var_58], rcx
0x18007342f  shl     rbx, 5
0x180073433  movsx   eax, word ptr [rbp+36h]
0x180073437  cmp     r11d, eax
0x18007343a  jge     short loc_180073470
0x18007343c  mov     rcx, [rbp+8]
0x180073440  mov     rdx, [rbx+r12+10h]
0x180073445  movsxd  rax, r11d
0x180073448  lea     r8, [rax+rax*2]
0x18007344c  mov     rcx, [rcx+r8*8]
0x180073450  call    sqlite3StrICmp
0x180073455  test    eax, eax
0x180073457  jz      short loc_18007345E
0x180073459  inc     r11d
0x18007345c  jmp     short loc_180073433
0x18007345e  mov     rcx, [rsp+88h+var_58]
0x180073463  lea     rax, [rcx+4]
0x180073467  add     rax, rax
0x18007346a  mov     [rdi+rax*8], r11d
0x18007346e  jmp     short loc_180073475
0x180073470  mov     rcx, [rsp+88h+var_58]
0x180073475  movsx   eax, word ptr [rbp+36h]
0x180073479  cmp     r11d, eax
0x18007347c  jge     short loc_1800734B0
0x18007347e  cmp     byte ptr [r14+134h], 2
0x180073486  jb      short loc_1800734A0
0x180073488  mov     r8, [rbx+r12+10h]
0x18007348d  lea     rdx, [rcx+4]
0x180073491  shl     rdx, 4
0x180073495  mov     rcx, r14
0x180073498  add     rdx, rdi
0x18007349b  call    sqlite3RenameTokenRemap
0x1800734a0  mov     r9d, [rsp+88h+arg_0]
0x1800734a8  inc     r9d
0x1800734ab  jmp     loc_180073410
0x1800734b0  mov     r8, [rbx+r12+10h]
0x1800734b5  lea     rdx, aUnknownColumnS; "unknown column \"%s\" in foreign key de"...
0x1800734bc  mov     rcx, r14
0x1800734bf  call    sqlite3ErrorMsg
0x1800734c4  jmp     short loc_1800734D9
0x1800734c6  test    rax, rax
0x1800734c9  jz      short loc_1800734D3
0x1800734cb  mov     [rdi+18h], rax
0x1800734cf  mov     [rax+20h], rdi
0x1800734d3  mov     [rbp+48h], rdi
0x1800734d7  xor     edi, edi
0x1800734d9  mov     rdx, rdi
0x1800734dc  mov     rcx, r15
0x1800734df  call    sqlite3DbFree
0x1800734e4  mov     rdx, r12
0x1800734e7  mov     rcx, r15
0x1800734ea  call    sqlite3ExprListDeleteGeneric
0x1800734ef  mov     rdx, rsi
0x1800734f2  mov     rcx, r15
0x1800734f5  add     rsp, 48h
0x1800734f9  pop     r15
0x1800734fb  pop     r14
0x1800734fd  pop     r13
0x1800734ff  pop     r12
0x180073501  pop     rdi
0x180073502  pop     rsi
0x180073503  pop     rbp
0x180073504  pop     rbx
0x180073505  jmp     sqlite3ExprListDeleteGeneric
```

# sqlite3EndTable

- ea: `0x180073a20`
- end: `0x18007433a`
- name: `sqlite3EndTable`
- size: `2330`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `installer_update`

## callers

- `0x180070f50`
- `0x1800d8b00`

## callees

- `0x180005980`
- `0x1800335c0`
- `0x180034640`
- `0x180035360`
- `0x180035f60`
- `0x18003a790`
- `0x180044640`
- `0x18004dba0`
- `0x18006b630`
- `0x18006db60`
- `0x180071400`
- `0x180073a20`
- `0x1800743d0`
- `0x1800838f0`
- `0x180088240`
- `0x180088530`
- `0x180088ea0`
- `0x180089210`
- `0x180095710`
- `0x180095830`
- `0x1800971f0`
- `0x18009b840`
- `0x18009d820`
- `0x1800a2fd0`
- `0x1800a3040`
- `0x1800a30b0`
- `0x1800a3370`
- `0x1800a3b40`
- `0x1800a4140`
- `0x1800aded0`
- `0x1800ae640`
- `0x1800e4dc2`
- `0x1800e4dce`

## string_xrefs

- `0x180074151`: `CREATE %s %.*s`
- `0x180074168`: `UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d`
- `0x180074242`: `CREATE TABLE %Q.sqlite_sequence(name,seq)`

## pseudocode

```c
void __fastcall sqlite3EndTable(__int64 *a1, __int64 *a2, unsigned __int64 a3, int a4, __int64 a5)
{
  __int64 v5; // r12
  _DWORD *v6; // r13
  const char **v8; // rbx
  __int64 v9; // rbp
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // eax
  int v14; // eax
  const char *v15; // rdi
  size_t v16; // rax
  const char *v17; // rcx
  int v18; // r15d
  __int64 v19; // rdx
  const char *v20; // rdx
  int v21; // r12d
  int v22; // edi
  const char *v23; // rax
  __int64 v24; // r14
  __int64 v25; // rcx
  const char *v26; // r9
  __int64 v27; // r9
  int v28; // edx
  int v29; // r8d
  const char *v30; // rcx
  int v31; // r9d
  int v32; // r10d
  int v33; // eax
  __int16 v34; // ax
  const char *v35; // rdi
  __int64 v36; // r14
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  const char *v41; // r8
  __int64 *v42; // rcx
  unsigned int v43; // edi
  __int64 v44; // rax
  unsigned int v45; // r12d
  __int64 v46; // r8
  __int64 v47; // rax
  __int16 v48; // cx
  bool v49; // zf
  unsigned int v50; // edi
  __int64 TableStmt; // rax
  _DWORD *v52; // rcx
  int v53; // r9d
  _QWORD *v54; // rdi
  __int64 v55; // r12
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // [rsp+20h] [rbp-A8h]
  const char *v60; // [rsp+20h] [rbp-A8h]
  const char *v61; // [rsp+28h] [rbp-A0h]
  int v62; // [rsp+30h] [rbp-98h]
  char v63[4]; // [rsp+58h] [rbp-70h] BYREF
  unsigned int v64; // [rsp+5Ch] [rbp-6Ch]
  __int64 v65; // [rsp+60h] [rbp-68h]
  int v66; // [rsp+68h] [rbp-60h]
  __int64 v67; // [rsp+70h] [rbp-58h]
  int v68; // [rsp+D0h] [rbp+8h]
  _DWORD *v70; // [rsp+E0h] [rbp+18h]
  int v71; // [rsp+E8h] [rbp+20h]

  v71 = a4;
  v70 = (_DWORD *)a3;
  v5 = a5;
  v6 = (_DWORD *)a3;
  if ( !a3 && !a5 )
    return;
  v8 = (const char **)a1[43];
  if ( !v8 )
    return;
  v9 = *a1;
  if ( !a5 )
  {
    v10 = sqlite3ShadowTableName(*a1, *v8);
    a4 = v71;
    if ( v10 )
      *((_DWORD *)v8 + 12) |= 0x1000u;
  }
  if ( *(_BYTE *)(v9 + 197) )
  {
    if ( a5 )
      goto LABEL_27;
    if ( *((_BYTE *)v8 + 63) )
    {
      if ( !*(_DWORD *)(v9 + 192) )
      {
        *((_DWORD *)v8 + 10) = *(_DWORD *)(v9 + 192);
        goto LABEL_12;
      }
LABEL_27:
      sqlite3ErrorMsg(a1, byte_180122168);
      return;
    }
    v14 = *(_DWORD *)(v9 + 192);
    *((_DWORD *)v8 + 10) = v14;
    if ( v14 == 1 )
      *((_DWORD *)v8 + 12) |= 1u;
  }
LABEL_12:
  if ( (a4 & 0x10000) != 0 )
  {
    *((_DWORD *)v8 + 12) |= 0x10000u;
    a3 = 0;
    if ( *((__int16 *)v8 + 27) > 0 )
    {
      while ( 1 )
      {
        v11 = (__int64)&v8[1][24 * (int)a3];
        v12 = *(_DWORD *)(v11 + 8);
        if ( (v12 & 0xF0) == 0 )
          break;
        if ( (*(_DWORD *)(v11 + 8) & 0xF0) == 0x10 )
          *(_BYTE *)(v11 + 12) = 65;
        if ( (*(_BYTE *)(v11 + 18) & 1) != 0 && *((__int16 *)v8 + 26) != (_DWORD)a3 && (v12 & 0xF) == 0 )
        {
          *(_DWORD *)(v11 + 8) = v12 & 0xFFFFFFF0 | 2;
          *((_DWORD *)v8 + 12) |= 0x800u;
        }
        a3 = (unsigned int)(a3 + 1);
        if ( (int)a3 >= *((__int16 *)v8 + 27) )
          goto LABEL_22;
      }
      v15 = *(const char **)v11;
      if ( (*(_BYTE *)(v11 + 18) & 4) != 0 )
      {
        v16 = strlen_0(*(const char **)v11);
        sqlite3ErrorMsg(a1, "unknown datatype for %s.%s: \"%s\"", *v8, v15, &v15[v16 + 1]);
      }
      else
      {
        sqlite3ErrorMsg(a1, "missing datatype for %s.%s", *v8, v15);
      }
      return;
    }
  }
LABEL_22:
  if ( (a4 & 0x80u) != 0 )
  {
    v13 = *((_DWORD *)v8 + 12);
    if ( (v13 & 8) != 0 )
    {
      sqlite3ErrorMsg(a1, "AUTOINCREMENT not allowed on WITHOUT ROWID tables", a3);
      return;
    }
    if ( (v13 & 4) == 0 )
    {
      sqlite3ErrorMsg(a1, "PRIMARY KEY missing on table %s", *v8);
      return;
    }
    *((_DWORD *)v8 + 12) = v13 | 0x280;
    convertToWithoutRowidTable(a1, v8, a3);
  }
  v17 = v8[12];
  v18 = -32768;
  if ( v17 )
  {
    v19 = *(_QWORD *)(v9 + 32);
    v18 = 0;
    if ( *(const char **)(v19 + 24) != v17 )
    {
      do
        ++v18;
      while ( *(const char **)(32LL * v18 + v19 + 24) != v17 );
    }
  }
  if ( v8[4] )
  {
    sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v8, 4, 0, (__int64)v8[4]);
    if ( *((_DWORD *)a1 + 12) )
    {
      v20 = v8[4];
      if ( v20 )
        exprListDeleteNN(v9, v20);
      v8[4] = 0;
    }
  }
  if ( ((_BYTE)v8[6] & 0x60) != 0 )
  {
    v21 = 0;
    v22 = 0;
    if ( *((__int16 *)v8 + 27) <= 0 )
      goto LABEL_77;
    do
    {
      v23 = v8[1];
      v24 = 24LL * v22;
      if ( (v23[v24 + 18] & 0x60) != 0 )
      {
        v25 = *(unsigned __int16 *)&v23[v24 + 16];
        if ( (_WORD)v25 )
        {
          if ( *((_BYTE *)v8 + 63) )
          {
            LODWORD(v26) = 0;
          }
          else
          {
            v26 = v8[10];
            if ( v26 )
            {
              if ( *(_DWORD *)v26 >= (int)v25 )
                v26 = *(const char **)&v26[32 * v25 - 24];
              else
                LODWORD(v26) = 0;
            }
          }
        }
        else
        {
          LODWORD(v26) = 0;
        }
        if ( (unsigned int)sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v8, 8, (_DWORD)v26, 0) )
        {
          v27 = sqlite3DbMallocRawNN(v9, 72);
          if ( v27 )
          {
            *(_OWORD *)v27 = 0;
            *(_OWORD *)(v27 + 16) = 0;
            *(_OWORD *)(v27 + 32) = 0;
            *(_OWORD *)(v27 + 48) = 0;
            *(_QWORD *)(v27 + 64) = 0;
            *(_BYTE *)v27 = 121;
            *(_WORD *)(v27 + 50) = -1;
            *(_DWORD *)(v27 + 40) = 1;
          }
          sqlite3ColumnSetExpr(a1, v8, &v8[1][v24], v27);
        }
      }
      else
      {
        ++v21;
      }
      ++v22;
    }
    while ( v22 < *((__int16 *)v8 + 27) );
    v6 = v70;
    if ( !v21 )
    {
LABEL_77:
      sqlite3ErrorMsg(a1, "must have at least one non-generated column", a3);
      return;
    }
    v5 = a5;
  }
  v28 = *((__int16 *)v8 + 27);
  v29 = 0;
  v30 = v8[1];
  v31 = 0;
  v32 = 0;
  if ( v28 >= 2 )
  {
    do
    {
      v28 -= 2;
      v29 += *((unsigned __int8 *)v30 + 13);
      v31 += *((unsigned __int8 *)v30 + 37);
      v30 += 48;
    }
    while ( v28 > 1 );
  }
  if ( v28 > 0 )
    v32 = *((unsigned __int8 *)v30 + 13);
  v33 = v32 + v31 + v29 + 1;
  if ( *((__int16 *)v8 + 26) >= 0 )
    v33 = v32 + v31 + v29;
  v34 = sqlite3LogEst((unsigned int)(4 * v33));
  v35 = v8[2];
  for ( *((_WORD *)v8 + 30) = v34; v35; v35 = (const char *)*((_QWORD *)v35 + 5) )
    estimateIndexWidth(v35);
  if ( *(_BYTE *)(v9 + 197) )
    goto LABEL_114;
  v36 = a1[2];
  if ( !v36 )
  {
    if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v36 = sqlite3VdbeCreate(a1);
    if ( !v36 )
      return;
  }
  v37 = *(int *)(v36 + 144);
  if ( *(_DWORD *)(v36 + 148) > (int)v37 )
  {
    *(_DWORD *)(v36 + 144) = v37 + 1;
    v38 = 3 * v37;
    v39 = *(_QWORD *)(v36 + 136);
    *(_QWORD *)(v39 + 8 * v38) = 122;
    v40 = v39 + 8 * v38;
    *(_QWORD *)(v40 + 8) = 0;
    *(_QWORD *)(v40 + 16) = 0;
  }
  else
  {
    LODWORD(v59) = 0;
    growOp3(v36, 122, 0, 0, v59);
  }
  v41 = "TABLE";
  if ( *((_BYTE *)v8 + 63) )
    v41 = "VIEW";
  if ( !v5 )
  {
    v52 = a1 + 35;
    if ( !v71 )
      v52 = v70;
    v53 = *v52 - *((_DWORD *)a1 + 66);
    if ( **(_BYTE **)v52 != 59 )
      v53 += v52[2];
    TableStmt = sqlite3MPrintf(v9, "CREATE %s %.*s", v41, v53, (const char *)a1[33]);
LABEL_100:
    v54 = (_QWORD *)TableStmt;
    v62 = *((_DWORD *)a1 + 33);
    v61 = *v8;
    v60 = *v8;
    v55 = 32LL * v18;
    sqlite3NestedParse(
      a1,
      "UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d",
      *(_QWORD *)(*(_QWORD *)(v9 + 32) + v55));
    if ( v54 )
    {
      if ( (unsigned __int64)v54 < *(_QWORD *)(v9 + 496) )
      {
        if ( (unsigned __int64)v54 >= *(_QWORD *)(v9 + 480) )
        {
          *v54 = *(_QWORD *)(v9 + 472);
          *(_QWORD *)(v9 + 472) = v54;
          goto LABEL_109;
        }
        if ( (unsigned __int64)v54 >= *(_QWORD *)(v9 + 488) )
        {
          *v54 = *(_QWORD *)(v9 + 456);
          *(_QWORD *)(v9 + 456) = v54;
          goto LABEL_109;
        }
      }
      if ( *(_QWORD *)(v9 + 776) )
        measureAllocationSize(v9, v54);
      else
        sqlite3_free(v54);
    }
LABEL_109:
    sqlite3ChangeCookie(a1, (unsigned int)v18);
    if ( ((_BYTE)v8[6] & 8) != 0 && !*((_BYTE *)a1 + 300) )
    {
      v56 = *(_QWORD *)(v9 + 32);
      if ( !*(_QWORD *)(*(_QWORD *)(v56 + v55 + 24) + 104LL) )
        sqlite3NestedParse(a1, "CREATE TABLE %Q.sqlite_sequence(name,seq)", *(_QWORD *)(v56 + 32LL * v18));
    }
    v57 = sqlite3MPrintf(v9, "tbl_name='%q' AND type!='trigger'", *v8);
    sqlite3VdbeAddParseSchemaOp(v36, (unsigned int)v18, v57, 0, v60, (_DWORD)v61, v62);
    v6 = v70;
    if ( !*(_BYTE *)(v9 + 197) )
    {
LABEL_118:
      if ( !a5 && !*((_BYTE *)v8 + 63) )
      {
        v58 = *a2;
        if ( !*a2 )
          LODWORD(v58) = *v6;
        *((_DWORD *)v8 + 16) = v58 - *((_DWORD *)a1 + 66) + 13;
      }
      return;
    }
LABEL_114:
    if ( sqlite3HashInsert(v8[12] + 8, *v8, v8) )
    {
      sqlite3OomFault(v9);
      return;
    }
    a1[43] = 0;
    *(_DWORD *)(v9 + 44) |= 1u;
    if ( !strcmp_0(*v8, "sqlite_sequence") )
      *((_QWORD *)v8[12] + 13) = v8;
    goto LABEL_118;
  }
  if ( *((_BYTE *)a1 + 300) )
  {
    ++*((_DWORD *)a1 + 12);
    *((_DWORD *)a1 + 6) = 1;
    return;
  }
  v42 = a1;
  v43 = *((_DWORD *)a1 + 14) + 1;
  v68 = *((_DWORD *)a1 + 14) + 2;
  *((_DWORD *)a1 + 14) += 3;
  if ( a1[21] )
    v42 = (__int64 *)a1[21];
  *((_BYTE *)v42 + 33) = 1;
  sqlite3VdbeAddOp3(v36, 113, 1, *((_DWORD *)a1 + 33), v18);
  v44 = *(int *)(v36 + 144);
  if ( (int)v44 > 0 )
    *(_WORD *)(*(_QWORD *)(v36 + 136) + 24 * v44 - 22) = 16;
  *((_DWORD *)a1 + 13) = 2;
  v45 = *(_DWORD *)(v36 + 144);
  sqlite3VdbeAddOp3(v36, 11, v43, 0, v45 + 1);
  if ( !*((_DWORD *)a1 + 12) )
  {
    LOBYTE(v46) = 65;
    v47 = sqlite3ResultSetOfSelect(a1, a5, v46);
    if ( v47 )
    {
      v48 = *(_WORD *)(v47 + 54);
      *((_WORD *)v8 + 28) = v48;
      *((_WORD *)v8 + 27) = v48;
      v8[1] = *(const char **)(v47 + 8);
      *(_WORD *)(v47 + 54) = 0;
      *(_QWORD *)(v47 + 8) = 0;
      if ( *(_QWORD *)(v9 + 776) || (v49 = *(_DWORD *)(v47 + 44) == 1, --*(_DWORD *)(v47 + 44), v49) )
        deleteTable(v9, v47);
      v67 = 0;
      v66 = 0;
      v63[0] = 13;
      v64 = v43;
      v65 = 0;
      sqlite3Select(a1, a5, v63);
      if ( !*((_DWORD *)a1 + 12) )
      {
        sqlite3VdbeEndCoroutine(v36, v43);
        sqlite3VdbeJumpHere(v36, v45);
        v50 = sqlite3VdbeAddOp1(v36, 12, v64);
        sqlite3VdbeAddOp3(v36, 97, HIDWORD(v65), v66, v68);
        sqlite3TableAffinity(v36, v8, 0);
        sqlite3VdbeAddOp2(v36, 127, 1, (unsigned int)(v68 + 1));
        sqlite3VdbeAddOp3(v36, 128, 1, v68, v68 + 1);
        sqlite3VdbeGoto(v36, v50);
        sqlite3VdbeJumpHere(v36, v50);
        sqlite3VdbeAddOp1(v36, 122, 1);
        TableStmt = createTableStmt(v9, v8);
        goto LABEL_100;
      }
    }
  }
}

```

## disassembly

```asm
0x180073a20  mov     [rsp+arg_18], r9d
0x180073a25  mov     [rsp+arg_10], r8
0x180073a2a  mov     [rsp+arg_8], rdx
0x180073a2f  push    rsi
0x180073a30  push    r12
0x180073a32  push    r13
0x180073a34  sub     rsp, 0B0h
0x180073a3b  mov     r12, [rsp+0C8h+arg_20]
0x180073a43  mov     r13, r8
0x180073a46  mov     rsi, rcx
0x180073a49  test    r8, r8
0x180073a4c  jnz     short loc_180073A57
0x180073a4e  test    r12, r12
0x180073a51  jz      loc_18007432D
0x180073a57  mov     [rsp+0C8h+var_20], rbx
0x180073a5f  mov     rbx, [rcx+158h]
0x180073a66  test    rbx, rbx
0x180073a69  jz      loc_180074325
0x180073a6f  mov     [rsp+0C8h+var_28], rbp
0x180073a77  mov     rbp, [rcx]
0x180073a7a  test    r12, r12
0x180073a7d  jnz     short loc_180073A9D
0x180073a7f  mov     rdx, [rbx]
0x180073a82  mov     rcx, rbp
0x180073a85  call    sqlite3ShadowTableName
0x180073a8a  mov     r9d, [rsp+0C8h+arg_18]
0x180073a92  test    eax, eax
0x180073a94  jz      short loc_180073A9D
0x180073a96  or      dword ptr [rbx+30h], 1000h
0x180073a9d  cmp     byte ptr [rbp+0C5h], 0
0x180073aa4  jz      short loc_180073ACF
0x180073aa6  test    r12, r12
0x180073aa9  jnz     loc_180073B8B
0x180073aaf  cmp     [rbx+3Fh], r12b
0x180073ab3  jz      loc_180073B71
0x180073ab9  cmp     [rbp+0C0h], r12d
0x180073ac0  jnz     loc_180073B8B
0x180073ac6  mov     eax, [rbp+0C0h]
0x180073acc  mov     [rbx+28h], eax
0x180073acf  mov     [rsp+0C8h+var_30], rdi
0x180073ad7  bt      r9d, 10h
0x180073adc  jnb     short loc_180073B49
0x180073ade  or      dword ptr [rbx+30h], 10000h
0x180073ae5  xor     r8d, r8d
0x180073ae8  xor     eax, eax
0x180073aea  cmp     ax, [rbx+36h]
0x180073aee  jge     short loc_180073B49
0x180073af0  movsxd  rax, r8d
0x180073af3  lea     rcx, [rax+rax*2]
0x180073af7  mov     rax, [rbx+8]
0x180073afb  lea     rdx, [rax+rcx*8]
0x180073aff  mov     ecx, [rax+rcx*8+8]
0x180073b03  mov     eax, ecx
0x180073b05  and     eax, 0F0h
0x180073b0a  jz      loc_180073B9F
0x180073b10  cmp     eax, 10h
0x180073b13  jnz     short loc_180073B19
0x180073b15  mov     byte ptr [rdx+0Ch], 41h ; 'A'
0x180073b19  test    byte ptr [rdx+12h], 1
0x180073b1d  jz      short loc_180073B3D
0x180073b1f  movsx   eax, word ptr [rbx+34h]
0x180073b23  cmp     eax, r8d
0x180073b26  jz      short loc_180073B3D
0x180073b28  test    cl, 0Fh
0x180073b2b  jnz     short loc_180073B3D
0x180073b2d  and     ecx, 0FFFFFFF2h
0x180073b30  or      ecx, 2
0x180073b33  mov     [rdx+8], ecx
0x180073b36  or      dword ptr [rbx+30h], 800h
0x180073b3d  movsx   eax, word ptr [rbx+36h]
0x180073b41  inc     r8d
0x180073b44  cmp     r8d, eax
0x180073b47  jl      short loc_180073AF0
0x180073b49  test    r9b, r9b
0x180073b4c  jns     loc_180073C18
0x180073b52  mov     eax, [rbx+30h]
0x180073b55  mov     rcx, rsi
0x180073b58  test    al, 8
0x180073b5a  jz      loc_180073BF0
0x180073b60  lea     rdx, aAutoincrementN; "AUTOINCREMENT not allowed on WITHOUT RO"...
0x180073b67  call    sqlite3ErrorMsg
0x180073b6c  jmp     loc_180074315
0x180073b71  mov     eax, [rbp+0C0h]
0x180073b77  mov     [rbx+28h], eax
0x180073b7a  cmp     eax, 1
0x180073b7d  jnz     loc_180073ACF
0x180073b83  or      [rbx+30h], eax
0x180073b86  jmp     loc_180073ACF
0x180073b8b  lea     rdx, byte_180122168
0x180073b92  mov     rcx, rsi
0x180073b95  call    sqlite3ErrorMsg
0x180073b9a  jmp     loc_18007431D
0x180073b9f  test    byte ptr [rdx+12h], 4
0x180073ba3  mov     rdi, [rdx]
0x180073ba6  jz      short loc_180073BD6
0x180073ba8  mov     rcx, rdi; Str
0x180073bab  call    strlen_0
0x180073bb0  mov     r8, [rbx]
0x180073bb3  lea     rdx, aUnknownDatatyp; "unknown datatype for %s.%s: \"%s\""
0x180073bba  mov     r9, rdi
0x180073bbd  lea     rcx, [rax+1]
0x180073bc1  add     rcx, rdi
0x180073bc4  mov     [rsp+0C8h+var_A8], rcx
0x180073bc9  mov     rcx, rsi
0x180073bcc  call    sqlite3ErrorMsg
0x180073bd1  jmp     loc_180074315
0x180073bd6  mov     r8, [rbx]
0x180073bd9  lea     rdx, aMissingDatatyp; "missing datatype for %s.%s"
0x180073be0  mov     r9, rdi
0x180073be3  mov     rcx, rsi
0x180073be6  call    sqlite3ErrorMsg
0x180073beb  jmp     loc_180074315
0x180073bf0  test    al, 4
0x180073bf2  jnz     short loc_180073C08
0x180073bf4  mov     r8, [rbx]
0x180073bf7  lea     rdx, aPrimaryKeyMiss; "PRIMARY KEY missing on table %s"
0x180073bfe  call    sqlite3ErrorMsg
0x180073c03  jmp     loc_180074315
0x180073c08  or      eax, 280h
0x180073c0d  mov     rdx, rbx
0x180073c10  mov     [rbx+30h], eax
0x180073c13  call    convertToWithoutRowidTable
0x180073c18  mov     rcx, [rbx+60h]
0x180073c1c  mov     [rsp+0C8h+var_40], r15
0x180073c24  mov     r15d, 0FFFF8000h
0x180073c2a  test    rcx, rcx
0x180073c2d  jz      short loc_180073C51
0x180073c2f  mov     rdx, [rbp+20h]
0x180073c33  xor     r15d, r15d
0x180073c36  cmp     [rdx+18h], rcx
0x180073c3a  jz      short loc_180073C51
0x180073c3c  nop     dword ptr [rax+00h]
0x180073c40  inc     r15d
0x180073c43  movsxd  rax, r15d
0x180073c46  shl     rax, 5
0x180073c4a  cmp     [rax+rdx+18h], rcx
0x180073c4f  jnz     short loc_180073C40
0x180073c51  mov     rax, [rbx+20h]
0x180073c55  test    rax, rax
0x180073c58  jz      short loc_180073C92
0x180073c5a  xor     r9d, r9d
0x180073c5d  mov     [rsp+0C8h+var_A8], rax
0x180073c62  mov     r8d, 4
0x180073c68  mov     rdx, rbx
0x180073c6b  mov     rcx, rsi
0x180073c6e  call    sqlite3ResolveSelfReference
0x180073c73  cmp     dword ptr [rsi+30h], 0
0x180073c77  jz      short loc_180073C92
0x180073c79  mov     rdx, [rbx+20h]
0x180073c7d  test    rdx, rdx
0x180073c80  jz      short loc_180073C8A
0x180073c82  mov     rcx, rbp
0x180073c85  call    exprListDeleteNN
0x180073c8a  mov     qword ptr [rbx+20h], 0
0x180073c92  test    byte ptr [rbx+30h], 60h
0x180073c96  mov     [rsp+0C8h+var_38], r14
0x180073c9e  jz      loc_180073DAE
0x180073ca4  xor     r12d, r12d
0x180073ca7  xor     edi, edi
0x180073ca9  xor     eax, eax
0x180073cab  cmp     ax, [rbx+36h]
0x180073caf  jge     loc_180073E9E
0x180073cb5  movsxd  rax, edi
0x180073cb8  lea     rcx, [rax+rax*2]
0x180073cbc  mov     rax, [rbx+8]
0x180073cc0  lea     r14, ds:0[rcx*8]
0x180073cc8  test    byte ptr [r14+rax+12h], 60h
0x180073cce  jz      loc_180073D84
0x180073cd4  movzx   ecx, word ptr [r14+rax+10h]
0x180073cda  test    cx, cx
0x180073cdd  jnz     short loc_180073CE4
0x180073cdf  xor     r9d, r9d
0x180073ce2  jmp     short loc_180073D0E
0x180073ce4  cmp     byte ptr [rbx+3Fh], 0
0x180073ce8  jz      short loc_180073CEF
0x180073cea  xor     r9d, r9d
0x180073ced  jmp     short loc_180073D0E
0x180073cef  mov     r9, [rbx+50h]
0x180073cf3  test    r9, r9
0x180073cf6  jz      short loc_180073D0E
0x180073cf8  mov     rax, rcx
0x180073cfb  cmp     [r9], ecx
0x180073cfe  jge     short loc_180073D05
0x180073d00  xor     r9d, r9d
0x180073d03  jmp     short loc_180073D0E
0x180073d05  shl     rax, 5
0x180073d09  mov     r9, [rax+r9-18h]
0x180073d0e  mov     r8d, 8
0x180073d14  mov     [rsp+0C8h+var_A8], 0
0x180073d1d  mov     rdx, rbx
0x180073d20  mov     rcx, rsi
0x180073d23  call    sqlite3ResolveSelfReference
0x180073d28  test    eax, eax
0x180073d2a  jz      short loc_180073D87
0x180073d2c  mov     edx, 48h ; 'H'
0x180073d31  mov     rcx, rbp
0x180073d34  call    sqlite3DbMallocRawNN
0x180073d39  mov     r9, rax
0x180073d3c  test    rax, rax
0x180073d3f  jz      short loc_180073D70
0x180073d41  xorps   xmm0, xmm0
0x180073d44  xor     eax, eax
0x180073d46  movups  xmmword ptr [r9], xmm0
0x180073d4a  movups  xmmword ptr [r9+10h], xmm0
0x180073d4f  movups  xmmword ptr [r9+20h], xmm0
0x180073d54  movups  xmmword ptr [r9+30h], xmm0
0x180073d59  mov     [r9+40h], rax
0x180073d5d  mov     byte ptr [r9], 79h ; 'y'
0x180073d61  mov     word ptr [r9+32h], 0FFFFh
0x180073d68  mov     dword ptr [r9+28h], 1
0x180073d70  mov     r8, [rbx+8]
0x180073d74  mov     rdx, rbx
0x180073d77  add     r8, r14
0x180073d7a  mov     rcx, rsi
0x180073d7d  call    sqlite3ColumnSetExpr
0x180073d82  jmp     short loc_180073D87
0x180073d84  inc     r12d
0x180073d87  movsx   eax, word ptr [rbx+36h]
0x180073d8b  inc     edi
0x180073d8d  cmp     edi, eax
0x180073d8f  jl      loc_180073CB5
0x180073d95  mov     r13, [rsp+0C8h+arg_10]
0x180073d9d  test    r12d, r12d
0x180073da0  jz      loc_180073E9E
0x180073da6  mov     r12, [rsp+0C8h+arg_20]
0x180073dae  movsx   edx, word ptr [rbx+36h]
0x180073db2  xor     r8d, r8d
0x180073db5  mov     rcx, [rbx+8]
0x180073db9  xor     r9d, r9d
0x180073dbc  xor     r10d, r10d
0x180073dbf  cmp     edx, 2
0x180073dc2  jl      short loc_180073DEA
0x180073dc4  nop     dword ptr [rax+00h]
0x180073dc8  nop     dword ptr [rax+rax+00000000h]
0x180073dd0  movzx   eax, byte ptr [rcx+0Dh]
0x180073dd4  sub     edx, 2
0x180073dd7  add     r8d, eax
0x180073dda  movzx   eax, byte ptr [rcx+25h]
0x180073dde  add     r9d, eax
0x180073de1  add     rcx, 30h ; '0'
0x180073de5  cmp     edx, 1
0x180073de8  jg      short loc_180073DD0
0x180073dea  test    edx, edx
0x180073dec  jle     short loc_180073DF3
0x180073dee  movzx   r10d, byte ptr [rcx+0Dh]
0x180073df3  lea     ecx, [r9+r8]
0x180073df7  add     ecx, r10d
0x180073dfa  cmp     word ptr [rbx+34h], 0
0x180073dff  lea     eax, [rcx+1]
0x180073e02  cmovge  eax, ecx
0x180073e05  shl     eax, 2
0x180073e08  mov     ecx, eax
0x180073e0a  call    sqlite3LogEst
0x180073e0f  mov     rdi, [rbx+10h]
0x180073e13  mov     [rbx+3Ch], ax
0x180073e17  test    rdi, rdi
0x180073e1a  jz      short loc_180073E31
0x180073e1c  nop     dword ptr [rax+00h]
0x180073e20  mov     rcx, rdi
0x180073e23  call    estimateIndexWidth
0x180073e28  mov     rdi, [rdi+28h]
0x180073e2c  test    rdi, rdi
0x180073e2f  jnz     short loc_180073E20
0x180073e31  cmp     byte ptr [rbp+0C5h], 0
0x180073e38  jnz     loc_180074288
0x180073e3e  mov     r14, [rsi+10h]
0x180073e42  test    r14, r14
0x180073e45  jnz     short loc_180073E71
0x180073e47  cmp     [rsi+0A8h], r14
0x180073e4e  jnz     short loc_180073E5D
0x180073e50  mov     rax, [rsi]
0x180073e53  test    byte ptr [rax+60h], 8
0x180073e57  jnz     short loc_180073E5D
0x180073e59  mov     byte ptr [rsi+23h], 1
0x180073e5d  mov     rcx, rsi
0x180073e60  call    sqlite3VdbeCreate
0x180073e65  mov     r14, rax
0x180073e68  test    rax, rax
0x180073e6b  jz      loc_180074305
0x180073e71  movsxd  rcx, dword ptr [r14+90h]
0x180073e78  cmp     [r14+94h], ecx
0x180073e7f  jg      short loc_180073EB2
0x180073e81  xor     r9d, r9d
0x180073e84  mov     dword ptr [rsp+0C8h+var_A8], 0
0x180073e8c  xor     r8d, r8d
0x180073e8f  mov     edx, 7Ah ; 'z'
0x180073e94  mov     rcx, r14
0x180073e97  call    growOp3
0x180073e9c  jmp     short loc_180073EDD
0x180073e9e  lea     rdx, aMustHaveAtLeas; "must have at least one non-generated co"...
0x180073ea5  mov     rcx, rsi
0x180073ea8  call    sqlite3ErrorMsg
0x180073ead  jmp     loc_180074305
0x180073eb2  lea     eax, [rcx+1]
0x180073eb5  mov     [r14+90h], eax
0x180073ebc  lea     rcx, [rcx+rcx*2]
0x180073ec0  mov     rax, [r14+88h]
0x180073ec7  mov     qword ptr [rax+rcx*8], 7Ah ; 'z'
0x180073ecf  lea     rdx, [rax+rcx*8]
0x180073ed3  xor     ecx, ecx
  ... truncated ...
```

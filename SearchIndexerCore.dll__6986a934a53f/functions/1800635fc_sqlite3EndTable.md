# sqlite3EndTable

- ea: `0x1800635fc`
- end: `0x180063d54`
- name: `sqlite3EndTable`
- size: `1880`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x18000213c`
- `0x18007243c`

## callees

- `0x18000506c`
- `0x180005650`
- `0x180008be8`
- `0x180009f6c`
- `0x180011bcc`
- `0x180014d90`
- `0x180015700`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001bc40`
- `0x18001e2e8`
- `0x18001f418`
- `0x18001f92c`
- `0x18003bc90`
- `0x180040e00`
- `0x180041d10`
- `0x18004a9b8`
- `0x18004e908`
- `0x18004e97c`
- `0x180050460`
- `0x180051fd0`
- `0x1800583d0`
- `0x180058730`
- `0x1800595c4`
- `0x18005a234`
- `0x1800635fc`
- `0x18006da4c`
- `0x18006dc30`
- `0x180070e90`
- `0x1800af5e4`

## string_xrefs

- `0x180063b8b`: `CREATE %s %.*s`
- `0x180063ba6`: `UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d`
- `0x180063c47`: `CREATE TABLE %Q.sqlite_sequence(name,seq)`

## pseudocode

```c
int __fastcall sqlite3EndTable(_QWORD *a1, _QWORD *a2, _DWORD *a3, int a4, __int64 a5)
{
  const char *Vdbe; // rax
  int v6; // r15d
  _DWORD *v7; // r12
  const char **v9; // rdi
  __int64 v10; // r14
  int v11; // eax
  int v12; // eax
  int i; // edx
  __int64 v14; // r9
  int v15; // ecx
  const char *v16; // rax
  const char **v17; // r9
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // ecx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rax
  const char *j; // rbx
  const char *v27; // r15
  char v28; // cl
  const char *v29; // r8
  const char *v30; // rax
  _QWORD *v31; // rcx
  int v32; // r8d
  unsigned int v33; // r12d
  int v34; // ebx
  int v35; // ecx
  __int64 v36; // r8
  __int16 v37; // cx
  __int64 v38; // r8
  int v39; // r9d
  unsigned int v40; // ebx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 TableStmt; // rax
  _DWORD *v44; // rcx
  int v45; // r9d
  __int64 v46; // rbx
  __int64 v47; // r12
  __int64 v48; // r8
  __int64 v49; // rax
  __int64 v50; // rax
  int v52; // [rsp+58h] [rbp-31h]
  int v53; // [rsp+58h] [rbp-31h]
  int v54; // [rsp+5Ch] [rbp-2Dh]
  int v55; // [rsp+60h] [rbp-29h]
  unsigned int v56; // [rsp+64h] [rbp-25h]
  const char *v57; // [rsp+68h] [rbp-21h]
  _OWORD v58[6]; // [rsp+70h] [rbp-19h] BYREF
  _UNKNOWN *retaddr; // [rsp+E0h] [rbp+57h] BYREF
  unsigned int v60; // [rsp+E8h] [rbp+5Fh]
  int v63; // [rsp+100h] [rbp+77h]

  Vdbe = (const char *)&retaddr;
  v63 = a4;
  v6 = 0;
  v7 = a3;
  if ( !a3 && !a5 )
    return (int)Vdbe;
  v9 = (const char **)a1[44];
  if ( !v9 )
    return (int)Vdbe;
  v10 = *a1;
  if ( !a5 )
  {
    v11 = sqlite3ShadowTableName(*a1, *v9);
    a4 = v63;
    if ( v11 )
      *((_DWORD *)v9 + 12) |= 0x1000u;
  }
  if ( *(_BYTE *)(v10 + 197) )
  {
    if ( a5 || *((_BYTE *)v9 + 63) && *(_DWORD *)(v10 + 192) )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, (const char *)&Src);
      return (int)Vdbe;
    }
    v12 = *(_DWORD *)(v10 + 192);
    *((_DWORD *)v9 + 10) = v12;
    if ( v12 == 1 )
      *((_DWORD *)v9 + 12) |= 1u;
  }
  if ( (a4 & 0x10000) != 0 )
  {
    *((_DWORD *)v9 + 12) |= 0x10000u;
    for ( i = 0; ; ++i )
    {
      if ( i >= *((__int16 *)v9 + 27) )
      {
        LOBYTE(a4) = v63;
        goto LABEL_30;
      }
      v14 = (__int64)&v9[1][24 * i];
      v15 = *(_DWORD *)(v14 + 8);
      if ( (v15 & 0xF0) == 0 )
        break;
      if ( (*(_DWORD *)(v14 + 8) & 0xF0) == 0x10 )
        *(_BYTE *)(v14 + 12) = 65;
      if ( (*(_BYTE *)(v14 + 18) & 1) != 0 && *((__int16 *)v9 + 26) != i && (v15 & 0xF) == 0 )
      {
        *(_DWORD *)(v14 + 8) = v15 & 0xFFFFFFF0 | 2;
        *((_DWORD *)v9 + 12) |= 0x800u;
      }
    }
    if ( (*(_BYTE *)(v14 + 18) & 4) != 0 )
    {
      v16 = (const char *)sqlite3ColumnType(v14, &Src);
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "unknown datatype for %s.%s: \"%s\"", *v9, *v17, v16);
    }
    else
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "missing datatype for %s.%s", *v9, *(const char **)v14);
    }
    return (int)Vdbe;
  }
LABEL_30:
  if ( (a4 & 0x80u) != 0 )
  {
    v18 = *((_DWORD *)v9 + 12);
    if ( (v18 & 8) != 0 )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "AUTOINCREMENT not allowed on WITHOUT ROWID tables");
      return (int)Vdbe;
    }
    if ( (v18 & 4) == 0 )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "PRIMARY KEY missing on table %s", *v9);
      return (int)Vdbe;
    }
    *((_DWORD *)v9 + 12) = v18 | 0x280;
    convertToWithoutRowidTable(a1, v9);
  }
  v60 = sqlite3SchemaToIndex(v10, v9[12]);
  if ( v9[4] )
  {
    sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v9, 4, 0, (__int64)v9[4]);
    if ( *((_DWORD *)a1 + 12) )
    {
      sqlite3ExprListDeleteGeneric(v10, v9[4]);
      v9[4] = 0;
    }
  }
  if ( ((_BYTE)v9[6] & 0x60) != 0 )
  {
    v21 = 0;
    v52 = 0;
    if ( *((__int16 *)v9 + 27) <= 0 )
      goto LABEL_47;
    do
    {
      v22 = (__int64)&v9[1][24 * v6];
      if ( (*(_BYTE *)(v22 + 18) & 0x60) != 0 )
      {
        v23 = sqlite3ColumnExpr(v9, v22, v19, v20);
        if ( (unsigned int)sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v9, 8, v23, 0) )
        {
          v24 = (__int64)&v9[1][24 * v6];
          v25 = sqlite3ExprAlloc(v10, 121, 0);
          sqlite3ColumnSetExpr(a1, v9, v24, v25);
        }
        v21 = v52;
      }
      else
      {
        v52 = ++v21;
      }
      ++v6;
    }
    while ( v6 < *((__int16 *)v9 + 27) );
    if ( !v21 )
    {
LABEL_47:
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "must have at least one non-generated column");
      return (int)Vdbe;
    }
  }
  estimateTableWidth(v9);
  for ( j = v9[2]; j; j = (const char *)*((_QWORD *)j + 5) )
    estimateIndexWidth(j);
  if ( *(_BYTE *)(v10 + 197) )
    goto LABEL_79;
  Vdbe = (const char *)sqlite3GetVdbe(a1);
  v27 = Vdbe;
  if ( !Vdbe )
    return (int)Vdbe;
  sqlite3VdbeAddOp3((_DWORD)Vdbe, 122, 0, 0, 0);
  v28 = *((_BYTE *)v9 + 63);
  v29 = "TABLE";
  if ( v28 )
    v29 = "VIEW";
  v30 = "table";
  if ( v28 )
    v30 = "view";
  v57 = v30;
  if ( !a5 )
  {
    v44 = a1 + 36;
    if ( !v63 )
      v44 = v7;
    v45 = *v44 - *((_DWORD *)a1 + 68);
    if ( **(_BYTE **)v44 != 59 )
      v45 += v44[2];
    TableStmt = sqlite3MPrintf(v10, "CREATE %s %.*s", v29, v45, (const char *)a1[34]);
    v33 = v60;
LABEL_72:
    v46 = TableStmt;
    v47 = 32LL * (int)v33;
    sqlite3NestedParse(
      a1,
      "UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d",
      *(_QWORD *)(*(_QWORD *)(v10 + 32) + v47),
      v57,
      *v9,
      *v9,
      *((_DWORD *)a1 + 35),
      TableStmt,
      *((_DWORD *)a1 + 34));
    sqlite3DbFree(v10, v46);
    sqlite3VdbeAddOp3(a1[2], 100, v60, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32LL) + v47 + 24) + 1);
    if ( ((_BYTE)v9[6] & 8) != 0 && !*((_BYTE *)a1 + 308) )
    {
      v48 = *(_QWORD *)(v10 + 32);
      if ( !*(_QWORD *)(*(_QWORD *)(v48 + v47 + 24) + 104LL) )
        sqlite3NestedParse(a1, "CREATE TABLE %Q.sqlite_sequence(name,seq)", *(_QWORD *)(v48 + v47));
    }
    v49 = sqlite3MPrintf(v10, "tbl_name='%q' AND type!='trigger'", *v9);
    LODWORD(Vdbe) = sqlite3VdbeAddParseSchemaOp(v27, v60, v49, 0);
    if ( ((_BYTE)v9[6] & 0x60) != 0 )
    {
      v50 = sqlite3MPrintf(v10, "SELECT*FROM\"%w\".\"%w\"", *(_QWORD *)(*(_QWORD *)(v10 + 32) + v47), *v9);
      LODWORD(Vdbe) = sqlite3VdbeAddOp4((_DWORD)v27, 148, 1, 0, 0, v50, -6);
    }
    v7 = a3;
    if ( !*(_BYTE *)(v10 + 197) )
    {
LABEL_83:
      if ( !a5 && !*((_BYTE *)v9 + 63) )
      {
        if ( *a2 )
          v7 = a2;
        LODWORD(Vdbe) = *v7 - *((_DWORD *)a1 + 68) + 13;
        *((_DWORD *)v9 + 16) = (_DWORD)Vdbe;
      }
      return (int)Vdbe;
    }
LABEL_79:
    if ( sqlite3HashInsert(v9[12] + 8, *v9, v9) )
    {
      LODWORD(Vdbe) = sqlite3OomFault(v10);
      return (int)Vdbe;
    }
    a1[44] = 0;
    *(_DWORD *)(v10 + 44) |= 1u;
    LODWORD(Vdbe) = strcmp_0(*v9, "sqlite_sequence");
    if ( !(_DWORD)Vdbe )
    {
      Vdbe = v9[12];
      *((_QWORD *)Vdbe + 13) = v9;
    }
    goto LABEL_83;
  }
  LODWORD(Vdbe) = 0;
  memset(v58, 0, 37);
  if ( *((_BYTE *)a1 + 308) )
  {
    ++*((_DWORD *)a1 + 12);
    *((_DWORD *)a1 + 6) = 1;
    return (int)Vdbe;
  }
  v31 = a1;
  v32 = *((_DWORD *)a1 + 13);
  v33 = v60;
  v34 = *((_DWORD *)a1 + 14) + 1;
  v53 = v32;
  *((_DWORD *)a1 + 13) = v32 + 1;
  v55 = v34 + 1;
  *((_DWORD *)a1 + 14) = v34 + 2;
  v54 = v34 + 2;
  if ( a1[22] )
    v31 = (_QWORD *)a1[22];
  *((_BYTE *)v31 + 33) = 1;
  sqlite3VdbeAddOp3((_DWORD)v27, 113, v32, *((_DWORD *)a1 + 35), v60);
  sqlite3VdbeChangeP5(v27, 16);
  v56 = *((_DWORD *)v27 + 36);
  LODWORD(Vdbe) = sqlite3VdbeAddOp3(v35, 11, v34, 0, v56 + 1);
  if ( !*((_DWORD *)a1 + 12) )
  {
    LOBYTE(v36) = 65;
    Vdbe = (const char *)sqlite3ResultSetOfSelect(a1, a5, v36);
    if ( Vdbe )
    {
      v37 = *((_WORD *)Vdbe + 27);
      *((_WORD *)v9 + 28) = v37;
      *((_WORD *)v9 + 27) = v37;
      v9[1] = (const char *)*((_QWORD *)Vdbe + 1);
      *((_WORD *)Vdbe + 27) = 0;
      *((_QWORD *)Vdbe + 1) = 0;
      sqlite3DeleteTable(v10, Vdbe);
      LOBYTE(v58[0]) = 13;
      *((_QWORD *)&v58[0] + 1) = 0;
      *((_QWORD *)&v58[1] + 1) = 0;
      LODWORD(v58[1]) = 0;
      DWORD1(v58[0]) = v34;
      LODWORD(Vdbe) = sqlite3Select(a1, a5, v58);
      if ( !*((_DWORD *)a1 + 12) )
      {
        sqlite3VdbeAddOp3((_DWORD)v27, 68, v34, 0, 0);
        *(_BYTE *)(*((_QWORD *)v27 + 3) + 31LL) = 0;
        *(_DWORD *)(*((_QWORD *)v27 + 3) + 40LL) = 0;
        *(_DWORD *)(sqlite3VdbeGetOp(v27, v56, v38, 0) + 8) = *((_DWORD *)v27 + 36);
        v40 = sqlite3VdbeAddOp3((_DWORD)v27, v39 + 12, DWORD1(v58[0]), v39, v39);
        sqlite3VdbeAddOp3((_DWORD)v27, 97, HIDWORD(v58[0]), v58[1], v55);
        sqlite3TableAffinity(v27, v9, 0);
        sqlite3VdbeAddOp3((_DWORD)v27, 127, v53, v54, 0);
        sqlite3VdbeAddOp3((_DWORD)v27, 128, v53, v55, v54);
        sqlite3VdbeAddOp3((_DWORD)v27, 9, 0, v40, 0);
        *(_DWORD *)(sqlite3VdbeGetOp(v27, v40, v41, v42) + 8) = *((_DWORD *)v27 + 36);
        sqlite3VdbeAddOp3((_DWORD)v27, 122, v53, 0, 0);
        TableStmt = createTableStmt(v10, (__int16 *)v9);
        goto LABEL_72;
      }
    }
  }
  return (int)Vdbe;
}

```

## disassembly

```asm
0x1800635fc  mov     rax, rsp
0x1800635ff  mov     [rax+20h], r9d
0x180063603  mov     [rax+18h], r8
0x180063607  mov     [rax+10h], rdx
0x18006360b  push    rbp
0x18006360c  push    rbx
0x18006360d  push    rsi
0x18006360e  push    rdi
0x18006360f  push    r12
0x180063611  push    r13
0x180063613  push    r14
0x180063615  push    r15
0x180063617  lea     rbp, [rax-57h]
0x18006361b  sub     rsp, 98h
0x180063622  mov     r13, [rbp+4Fh+arg_20]
0x180063626  xor     r15d, r15d
0x180063629  mov     r12, r8
0x18006362c  mov     rsi, rcx
0x18006362f  test    r8, r8
0x180063632  jnz     short loc_18006363D
0x180063634  test    r13, r13
0x180063637  jz      loc_180063D40
0x18006363d  mov     rdi, [rcx+160h]
0x180063644  test    rdi, rdi
0x180063647  jz      loc_180063D40
0x18006364d  mov     r14, [rcx]
0x180063650  test    r13, r13
0x180063653  jnz     short loc_18006366D
0x180063655  mov     rdx, [rdi]
0x180063658  mov     rcx, r14
0x18006365b  call    sqlite3ShadowTableName
0x180063660  mov     r9d, [rbp+4Fh+arg_18]
0x180063664  test    eax, eax
0x180063666  jz      short loc_18006366D
0x180063668  bts     dword ptr [rdi+30h], 0Ch
0x18006366d  cmp     [r14+0C5h], r15b
0x180063674  jz      short loc_1800636A0
0x180063676  test    r13, r13
0x180063679  jnz     loc_18006370D
0x18006367f  cmp     [rdi+3Fh], r15b
0x180063683  jz      short loc_18006368E
0x180063685  cmp     [r14+0C0h], r15d
0x18006368c  jnz     short loc_18006370D
0x18006368e  mov     eax, [r14+0C0h]
0x180063695  mov     [rdi+28h], eax
0x180063698  cmp     eax, 1
0x18006369b  jnz     short loc_1800636A0
0x18006369d  or      [rdi+30h], eax
0x1800636a0  mov     ecx, 10000h
0x1800636a5  test    ecx, r9d
0x1800636a8  jz      loc_180063774
0x1800636ae  or      [rdi+30h], ecx
0x1800636b1  mov     edx, r15d
0x1800636b4  movsx   eax, word ptr [rdi+36h]
0x1800636b8  cmp     edx, eax
0x1800636ba  jge     loc_180063770
0x1800636c0  movsxd  rax, edx
0x1800636c3  lea     rcx, [rax+rax*2]
0x1800636c7  mov     rax, [rdi+8]
0x1800636cb  lea     r9, [rax+rcx*8]
0x1800636cf  mov     ecx, [r9+8]
0x1800636d3  mov     eax, ecx
0x1800636d5  and     eax, 0F0h
0x1800636da  jz      short loc_180063721
0x1800636dc  cmp     eax, 10h
0x1800636df  jnz     short loc_1800636E6
0x1800636e1  mov     byte ptr [r9+0Ch], 41h ; 'A'
0x1800636e6  test    byte ptr [r9+12h], 1
0x1800636eb  jz      short loc_180063709
0x1800636ed  movsx   eax, word ptr [rdi+34h]
0x1800636f1  cmp     eax, edx
0x1800636f3  jz      short loc_180063709
0x1800636f5  test    cl, 0Fh
0x1800636f8  jnz     short loc_180063709
0x1800636fa  and     ecx, 0FFFFFFF2h
0x1800636fd  or      ecx, 2
0x180063700  mov     [r9+8], ecx
0x180063704  bts     dword ptr [rdi+30h], 0Bh
0x180063709  inc     edx
0x18006370b  jmp     short loc_1800636B4
0x18006370d  lea     rdx, Src
0x180063714  mov     rcx, rsi
0x180063717  call    sqlite3ErrorMsg
0x18006371c  jmp     loc_180063D40
0x180063721  test    byte ptr [r9+12h], 4
0x180063726  jz      short loc_180063756
0x180063728  lea     rdx, Src
0x18006372f  mov     rcx, r9
0x180063732  call    sqlite3ColumnType
0x180063737  mov     r9, [r9]
0x18006373a  lea     rdx, aUnknownDatatyp; "unknown datatype for %s.%s: \"%s\""
0x180063741  mov     r8, [rdi]
0x180063744  mov     rcx, rsi
0x180063747  mov     [rsp+0D0h+var_B0], rax
0x18006374c  call    sqlite3ErrorMsg
0x180063751  jmp     loc_180063D40
0x180063756  mov     r9, [r9]
0x180063759  lea     rdx, aMissingDatatyp; "missing datatype for %s.%s"
0x180063760  mov     r8, [rdi]
0x180063763  mov     rcx, rsi
0x180063766  call    sqlite3ErrorMsg
0x18006376b  jmp     loc_180063D40
0x180063770  mov     r9d, [rbp+4Fh+arg_18]
0x180063774  test    r9b, r9b
0x180063777  jns     short loc_1800637B4
0x180063779  mov     eax, [rdi+30h]
0x18006377c  test    al, 8
0x18006377e  jz      short loc_180063789
0x180063780  lea     rdx, aAutoincrementN; "AUTOINCREMENT not allowed on WITHOUT RO"...
0x180063787  jmp     short loc_180063714
0x180063789  mov     rcx, rsi
0x18006378c  test    al, 4
0x18006378e  jnz     short loc_1800637A4
0x180063790  mov     r8, [rdi]
0x180063793  lea     rdx, aPrimaryKeyMiss; "PRIMARY KEY missing on table %s"
0x18006379a  call    sqlite3ErrorMsg
0x18006379f  jmp     loc_180063D40
0x1800637a4  or      eax, 280h
0x1800637a9  mov     rdx, rdi
0x1800637ac  mov     [rdi+30h], eax
0x1800637af  call    convertToWithoutRowidTable
0x1800637b4  mov     rdx, [rdi+60h]
0x1800637b8  mov     rcx, r14
0x1800637bb  call    sqlite3SchemaToIndex
0x1800637c0  mov     [rbp+4Fh+arg_0], eax
0x1800637c3  mov     rax, [rdi+20h]
0x1800637c7  test    rax, rax
0x1800637ca  jz      short loc_1800637F9
0x1800637cc  xor     r9d, r9d
0x1800637cf  mov     [rsp+0D0h+var_B0], rax
0x1800637d4  mov     rdx, rdi
0x1800637d7  mov     rcx, rsi
0x1800637da  lea     r8d, [r9+4]
0x1800637de  call    sqlite3ResolveSelfReference
0x1800637e3  cmp     [rsi+30h], r15d
0x1800637e7  jz      short loc_1800637F9
0x1800637e9  mov     rdx, [rdi+20h]
0x1800637ed  mov     rcx, r14
0x1800637f0  call    sqlite3ExprListDeleteGeneric
0x1800637f5  mov     [rdi+20h], r15
0x1800637f9  test    byte ptr [rdi+30h], 60h
0x1800637fd  jz      loc_1800638A3
0x180063803  xor     eax, eax
0x180063805  mov     ecx, r15d
0x180063808  mov     [rbp+4Fh+var_80], ecx
0x18006380b  cmp     ax, [rdi+36h]
0x18006380f  jge     short loc_180063890
0x180063811  movsxd  rax, r15d
0x180063814  lea     rbx, [rax+rax*2]
0x180063818  mov     rax, [rdi+8]
0x18006381c  lea     rdx, [rax+rbx*8]
0x180063820  test    byte ptr [rdx+12h], 60h
0x180063824  jz      short loc_18006389C
0x180063826  mov     rcx, rdi
0x180063829  call    sqlite3ColumnExpr
0x18006382e  mov     r9, rax
0x180063831  mov     [rsp+0D0h+var_B0], 0
0x18006383a  mov     r8d, 8
0x180063840  mov     rcx, rsi
0x180063843  mov     rdx, rdi
0x180063846  call    sqlite3ResolveSelfReference
0x18006384b  test    eax, eax
0x18006384d  jz      short loc_18006387A
0x18006384f  mov     rax, [rdi+8]
0x180063853  xor     r9d, r9d
0x180063856  xor     r8d, r8d
0x180063859  mov     rcx, r14
0x18006385c  lea     edx, [r9+79h]
0x180063860  lea     rbx, [rax+rbx*8]
0x180063864  call    sqlite3ExprAlloc
0x180063869  mov     r9, rax
0x18006386c  mov     r8, rbx
0x18006386f  mov     rdx, rdi
0x180063872  mov     rcx, rsi
0x180063875  call    sqlite3ColumnSetExpr
0x18006387a  mov     ecx, [rbp+4Fh+var_80]
0x18006387d  movsx   eax, word ptr [rdi+36h]
0x180063881  inc     r15d
0x180063884  cmp     r15d, eax
0x180063887  jl      short loc_180063811
0x180063889  xor     r15d, r15d
0x18006388c  test    ecx, ecx
0x18006388e  jnz     short loc_1800638A3
0x180063890  lea     rdx, aMustHaveAtLeas; "must have at least one non-generated co"...
0x180063897  jmp     loc_180063714
0x18006389c  inc     ecx
0x18006389e  mov     [rbp+4Fh+var_80], ecx
0x1800638a1  jmp     short loc_18006387D
0x1800638a3  mov     rcx, rdi
0x1800638a6  call    estimateTableWidth
0x1800638ab  mov     rbx, [rdi+10h]
0x1800638af  jmp     short loc_1800638BD
0x1800638b1  mov     rcx, rbx
0x1800638b4  call    estimateIndexWidth
0x1800638b9  mov     rbx, [rbx+28h]
0x1800638bd  test    rbx, rbx
0x1800638c0  jnz     short loc_1800638B1
0x1800638c2  cmp     [r14+0C5h], r15b
0x1800638c9  jnz     loc_180063CD1
0x1800638cf  mov     rcx, rsi
0x1800638d2  call    sqlite3GetVdbe
0x1800638d7  mov     r15, rax
0x1800638da  test    rax, rax
0x1800638dd  jz      loc_180063D40
0x1800638e3  xor     r9d, r9d
0x1800638e6  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800638ea  xor     r8d, r8d
0x1800638ed  lea     edx, [rbx+7Ah]
0x1800638f0  mov     rcx, rax
0x1800638f3  call    sqlite3VdbeAddOp3
0x1800638f8  mov     cl, [rdi+3Fh]
0x1800638fb  lea     rax, aView; "VIEW"
0x180063902  test    cl, cl
0x180063904  lea     r8, aTable_0; "TABLE"
0x18006390b  lea     rdx, aView_0; "view"
0x180063912  cmovnz  r8, rax
0x180063916  lea     rax, aTable; "table"
0x18006391d  cmovnz  rax, rdx
0x180063921  mov     [rbp+4Fh+var_70], rax
0x180063925  test    r13, r13
0x180063928  jz      loc_180063B5F
0x18006392e  xor     eax, eax
0x180063930  xorps   xmm0, xmm0
0x180063933  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x180063937  mov     qword ptr [rbp+4Fh+var_58+0Dh], rax
0x18006393b  movups  [rbp+4Fh+var_68], xmm0
0x18006393f  cmp     [rsi+134h], bl
0x180063945  jz      short loc_180063956
0x180063947  inc     dword ptr [rsi+30h]
0x18006394a  mov     dword ptr [rsi+18h], 1
0x180063951  jmp     loc_180063D40
0x180063956  mov     edx, [rsi+34h]
0x180063959  mov     rcx, rsi
0x18006395c  mov     ebx, [rsi+38h]
0x18006395f  mov     r8d, edx
0x180063962  mov     r12d, [rbp+4Fh+arg_0]
0x180063966  inc     ebx
0x180063968  mov     [rbp+4Fh+var_80], edx
0x18006396b  lea     eax, [rdx+1]
0x18006396e  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x180063973  mov     [rsi+34h], eax
0x180063976  mov     edx, 71h ; 'q'
0x18006397b  lea     eax, [rbx+1]
0x18006397e  mov     [rbp+4Fh+var_78], eax
0x180063981  inc     eax
0x180063983  mov     [rsi+38h], eax
0x180063986  mov     [rbp+4Fh+var_7C], eax
0x180063989  mov     rax, [rsi+0B0h]
0x180063990  test    rax, rax
0x180063993  cmovnz  rcx, rax
0x180063997  mov     byte ptr [rcx+21h], 1
0x18006399b  mov     rcx, r15
0x18006399e  mov     r9d, [rsi+8Ch]
0x1800639a5  call    sqlite3VdbeAddOp3
0x1800639aa  mov     edx, 10h
0x1800639af  mov     rcx, r15
0x1800639b2  call    sqlite3VdbeChangeP5
0x1800639b7  mov     eax, [r15+90h]
0x1800639be  xor     r9d, r9d
0x1800639c1  mov     [rbp+4Fh+var_74], eax
0x1800639c4  mov     r8d, ebx
0x1800639c7  inc     eax
0x1800639c9  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800639cd  lea     edx, [r9+0Bh]
0x1800639d1  call    sqlite3VdbeAddOp3
0x1800639d6  cmp     dword ptr [rsi+30h], 0
0x1800639da  jnz     loc_180063D40
0x1800639e0  mov     r8b, 41h ; 'A'
0x1800639e3  mov     rdx, r13
0x1800639e6  mov     rcx, rsi
0x1800639e9  call    sqlite3ResultSetOfSelect
0x1800639ee  test    rax, rax
0x1800639f1  jz      loc_180063D40
0x1800639f7  movzx   ecx, word ptr [rax+36h]
0x1800639fb  mov     rdx, rax
0x1800639fe  mov     [rdi+38h], cx
0x180063a02  mov     [rdi+36h], cx
0x180063a06  mov     rcx, [rax+8]
0x180063a0a  mov     [rdi+8], rcx
0x180063a0e  xor     ecx, ecx
0x180063a10  mov     [rax+36h], cx
0x180063a14  mov     [rax+8], rcx
0x180063a18  mov     rcx, r14
0x180063a1b  call    sqlite3DeleteTable
0x180063a20  xor     eax, eax
0x180063a22  mov     byte ptr [rbp+4Fh+var_68], 0Dh
0x180063a26  lea     r8, [rbp+4Fh+var_68]
0x180063a2a  mov     qword ptr [rbp+4Fh+var_68+8], rax
0x180063a2e  mov     rdx, r13
0x180063a31  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x180063a35  mov     rcx, rsi
0x180063a38  mov     dword ptr [rbp+4Fh+var_58], eax
0x180063a3b  mov     dword ptr [rbp+4Fh+var_68+4], ebx
0x180063a3e  call    sqlite3Select
0x180063a43  cmp     dword ptr [rsi+30h], 0
0x180063a47  jnz     loc_180063D40
0x180063a4d  xor     r9d, r9d
0x180063a50  mov     dword ptr [rsp+0D0h+var_B0], 0
0x180063a58  mov     r8d, ebx
0x180063a5b  mov     rcx, r15
  ... truncated ...
```

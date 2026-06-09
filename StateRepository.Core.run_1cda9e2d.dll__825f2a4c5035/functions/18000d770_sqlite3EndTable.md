# sqlite3EndTable

- ea: `0x18000d770`
- end: `0x18000dec8`
- name: `sqlite3EndTable`
- size: `1880`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x18000d480`
- `0x180031b38`

## callees

- `0x180002770`
- `0x180005c54`
- `0x18000a9e0`
- `0x18000c500`
- `0x18000c930`
- `0x18000d770`
- `0x180010810`
- `0x1800110a0`
- `0x1800119e0`
- `0x180011d80`
- `0x180013d60`
- `0x180013db0`
- `0x1800256c4`
- `0x180036688`
- `0x180037194`
- `0x180039490`
- `0x18003f6dc`
- `0x18004660c`
- `0x18005a9d0`
- `0x18005cc60`
- `0x180060ce8`
- `0x18006170c`
- `0x180064c24`
- `0x180064ef0`
- `0x1800655a8`
- `0x18006cdd8`
- `0x18006d26c`
- `0x1800857c4`
- `0x180088234`
- `0x1800997e4`

## string_xrefs

- `0x18000dcff`: `CREATE %s %.*s`
- `0x18000dd1a`: `UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d`
- `0x18000ddbb`: `CREATE TABLE %Q.sqlite_sequence(name,seq)`

## pseudocode

```c
int __fastcall sqlite3EndTable(__int64 *a1, _QWORD *a2, _DWORD *a3, int a4, __int64 a5)
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
  int v19; // ecx
  int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rax
  const char *j; // rbx
  const char *v24; // r15
  char v25; // cl
  const char *v26; // r8
  const char *v27; // rax
  __int64 *v28; // rcx
  int v29; // r8d
  unsigned int v30; // r12d
  int v31; // ebx
  int v32; // ecx
  __int64 v33; // r8
  __int16 v34; // cx
  int v35; // r9d
  unsigned int v36; // ebx
  __int64 TableStmt; // rax
  _DWORD *v38; // rcx
  int v39; // r9d
  __int64 v40; // rbx
  __int64 v41; // r12
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // rax
  int v46; // [rsp+58h] [rbp-31h]
  int v47; // [rsp+58h] [rbp-31h]
  int v48; // [rsp+5Ch] [rbp-2Dh]
  int v49; // [rsp+60h] [rbp-29h]
  unsigned int v50; // [rsp+64h] [rbp-25h]
  const char *v51; // [rsp+68h] [rbp-21h]
  _OWORD v52[6]; // [rsp+70h] [rbp-19h] BYREF
  _UNKNOWN *retaddr; // [rsp+E0h] [rbp+57h] BYREF
  unsigned int v54; // [rsp+E8h] [rbp+5Fh]
  int v57; // [rsp+100h] [rbp+77h]

  Vdbe = (const char *)&retaddr;
  v57 = a4;
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
    a4 = v57;
    if ( v11 )
      *((_DWORD *)v9 + 12) |= 0x1000u;
  }
  if ( *(_BYTE *)(v10 + 197) )
  {
    if ( a5 || *((_BYTE *)v9 + 63) && *(_DWORD *)(v10 + 192) )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, byte_18009EEF0);
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
        LOBYTE(a4) = v57;
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
      v16 = (const char *)sqlite3ColumnType(v14, byte_18009EEF0);
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
  v54 = sqlite3SchemaToIndex(v10, v9[12]);
  if ( v9[4] )
  {
    sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v9, 4, 0, (__int64)v9[4]);
    if ( *((_DWORD *)a1 + 13) )
    {
      sqlite3ExprListDeleteGeneric(v10, v9[4]);
      v9[4] = 0;
    }
  }
  if ( ((_BYTE)v9[6] & 0x60) != 0 )
  {
    v19 = 0;
    v46 = 0;
    if ( *((__int16 *)v9 + 27) <= 0 )
      goto LABEL_47;
    do
    {
      if ( (v9[1][24 * v6 + 18] & 0x60) != 0 )
      {
        v20 = sqlite3ColumnExpr(v9);
        if ( (unsigned int)sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v9, 8, v20, 0) )
        {
          v21 = (__int64)&v9[1][24 * v6];
          v22 = sqlite3ExprAlloc(v10, 122, 0, 0);
          sqlite3ColumnSetExpr(a1, v9, v21, v22);
        }
        v19 = v46;
      }
      else
      {
        v46 = ++v19;
      }
      ++v6;
    }
    while ( v6 < *((__int16 *)v9 + 27) );
    if ( !v19 )
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
  v24 = Vdbe;
  if ( !Vdbe )
    return (int)Vdbe;
  sqlite3VdbeAddOp3((_DWORD)Vdbe, 122, 0, 0, 0);
  v25 = *((_BYTE *)v9 + 63);
  v26 = "TABLE";
  if ( v25 )
    v26 = "VIEW";
  v27 = "table";
  if ( v25 )
    v27 = "view";
  v51 = v27;
  if ( !a5 )
  {
    v38 = a1 + 36;
    if ( !v57 )
      v38 = v7;
    v39 = *v38 - *((_DWORD *)a1 + 68);
    if ( **(_BYTE **)v38 != 59 )
      v39 += v38[2];
    TableStmt = sqlite3MPrintf(v10, "CREATE %s %.*s", v26, v39, (const char *)a1[34]);
    v30 = v54;
LABEL_72:
    v40 = TableStmt;
    v41 = 32LL * (int)v30;
    sqlite3NestedParse(
      a1,
      "UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d",
      *(_QWORD *)(*(_QWORD *)(v10 + 32) + v41),
      v51,
      *v9,
      *v9,
      *((_DWORD *)a1 + 35),
      TableStmt,
      *((_DWORD *)a1 + 34));
    sqlite3DbFree(v10, v40);
    sqlite3VdbeAddOp3(a1[2], 100, v54, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32) + v41 + 24) + 1);
    if ( ((_BYTE)v9[6] & 8) != 0 && !*((_BYTE *)a1 + 308) )
    {
      v42 = *(_QWORD *)(v10 + 32);
      if ( !*(_QWORD *)(*(_QWORD *)(v42 + v41 + 24) + 104LL) )
        sqlite3NestedParse(a1, "CREATE TABLE %Q.sqlite_sequence(name,seq)", *(_QWORD *)(v42 + v41));
    }
    v43 = sqlite3MPrintf(v10, "tbl_name='%q' AND type!='trigger'", *v9);
    LODWORD(Vdbe) = sqlite3VdbeAddParseSchemaOp(v24, v54, v43, 0);
    if ( ((_BYTE)v9[6] & 0x60) != 0 )
    {
      v44 = sqlite3MPrintf(v10, "SELECT*FROM\"%w\".\"%w\"", *(_QWORD *)(*(_QWORD *)(v10 + 32) + v41), *v9);
      LODWORD(Vdbe) = sqlite3VdbeAddOp4((_DWORD)v24, 148, 1, 0, 0, v44, -6);
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
  memset(v52, 0, 37);
  if ( *((_BYTE *)a1 + 308) )
  {
    ++*((_DWORD *)a1 + 13);
    *((_DWORD *)a1 + 6) = 1;
    return (int)Vdbe;
  }
  v28 = a1;
  v29 = *((_DWORD *)a1 + 14);
  v30 = v54;
  v31 = *((_DWORD *)a1 + 15) + 1;
  v47 = v29;
  *((_DWORD *)a1 + 14) = v29 + 1;
  v49 = v31 + 1;
  *((_DWORD *)a1 + 15) = v31 + 2;
  v48 = v31 + 2;
  if ( a1[22] )
    v28 = (__int64 *)a1[22];
  *((_BYTE *)v28 + 33) = 1;
  sqlite3VdbeAddOp3((_DWORD)v24, 113, v29, *((_DWORD *)a1 + 35), v54);
  sqlite3VdbeChangeP5(v24, 16);
  v50 = *((_DWORD *)v24 + 36);
  LODWORD(Vdbe) = sqlite3VdbeAddOp3(v32, 11, v31, 0, v50 + 1);
  if ( !*((_DWORD *)a1 + 13) )
  {
    LOBYTE(v33) = 65;
    Vdbe = (const char *)sqlite3ResultSetOfSelect(a1, a5, v33);
    if ( Vdbe )
    {
      v34 = *((_WORD *)Vdbe + 27);
      *((_WORD *)v9 + 28) = v34;
      *((_WORD *)v9 + 27) = v34;
      v9[1] = (const char *)*((_QWORD *)Vdbe + 1);
      *((_WORD *)Vdbe + 27) = 0;
      *((_QWORD *)Vdbe + 1) = 0;
      sqlite3DeleteTable(v10, Vdbe);
      LOBYTE(v52[0]) = 13;
      *((_QWORD *)&v52[0] + 1) = 0;
      *((_QWORD *)&v52[1] + 1) = 0;
      LODWORD(v52[1]) = 0;
      DWORD1(v52[0]) = v31;
      LODWORD(Vdbe) = sqlite3Select(a1, a5, v52);
      if ( !*((_DWORD *)a1 + 13) )
      {
        sqlite3VdbeAddOp3((_DWORD)v24, 68, v31, 0, 0);
        *(_BYTE *)(*((_QWORD *)v24 + 3) + 31LL) = 0;
        *(_DWORD *)(*((_QWORD *)v24 + 3) + 44LL) = 0;
        *(_DWORD *)(sqlite3VdbeGetOp(v24, v50) + 8) = *((_DWORD *)v24 + 36);
        v36 = sqlite3VdbeAddOp3((_DWORD)v24, v35 + 12, DWORD1(v52[0]), v35, v35);
        sqlite3VdbeAddOp3((_DWORD)v24, 97, HIDWORD(v52[0]), v52[1], v49);
        sqlite3TableAffinity(v24, v9, 0);
        sqlite3VdbeAddOp3((_DWORD)v24, 127, v47, v48, 0);
        sqlite3VdbeAddOp3((_DWORD)v24, 128, v47, v49, v48);
        sqlite3VdbeAddOp3((_DWORD)v24, 9, 0, v36, 0);
        *(_DWORD *)(sqlite3VdbeGetOp(v24, v36) + 8) = *((_DWORD *)v24 + 36);
        sqlite3VdbeAddOp3((_DWORD)v24, 122, v47, 0, 0);
        TableStmt = createTableStmt(v10, v9);
        goto LABEL_72;
      }
    }
  }
  return (int)Vdbe;
}

```

## disassembly

```asm
0x18000d770  mov     rax, rsp
0x18000d773  mov     [rax+20h], r9d
0x18000d777  mov     [rax+18h], r8
0x18000d77b  mov     [rax+10h], rdx
0x18000d77f  push    rbp
0x18000d780  push    rbx
0x18000d781  push    rsi
0x18000d782  push    rdi
0x18000d783  push    r12
0x18000d785  push    r13
0x18000d787  push    r14
0x18000d789  push    r15
0x18000d78b  lea     rbp, [rax-57h]
0x18000d78f  sub     rsp, 98h
0x18000d796  mov     r13, [rbp+4Fh+arg_20]
0x18000d79a  xor     r15d, r15d
0x18000d79d  mov     r12, r8
0x18000d7a0  mov     rsi, rcx
0x18000d7a3  test    r8, r8
0x18000d7a6  jnz     short loc_18000D7B1
0x18000d7a8  test    r13, r13
0x18000d7ab  jz      loc_18000DEB4
0x18000d7b1  mov     rdi, [rcx+160h]
0x18000d7b8  test    rdi, rdi
0x18000d7bb  jz      loc_18000DEB4
0x18000d7c1  mov     r14, [rcx]
0x18000d7c4  test    r13, r13
0x18000d7c7  jnz     short loc_18000D7E1
0x18000d7c9  mov     rdx, [rdi]
0x18000d7cc  mov     rcx, r14
0x18000d7cf  call    sqlite3ShadowTableName
0x18000d7d4  mov     r9d, [rbp+4Fh+arg_18]
0x18000d7d8  test    eax, eax
0x18000d7da  jz      short loc_18000D7E1
0x18000d7dc  bts     dword ptr [rdi+30h], 0Ch
0x18000d7e1  cmp     [r14+0C5h], r15b
0x18000d7e8  jz      short loc_18000D814
0x18000d7ea  test    r13, r13
0x18000d7ed  jnz     loc_18000D881
0x18000d7f3  cmp     [rdi+3Fh], r15b
0x18000d7f7  jz      short loc_18000D802
0x18000d7f9  cmp     [r14+0C0h], r15d
0x18000d800  jnz     short loc_18000D881
0x18000d802  mov     eax, [r14+0C0h]
0x18000d809  mov     [rdi+28h], eax
0x18000d80c  cmp     eax, 1
0x18000d80f  jnz     short loc_18000D814
0x18000d811  or      [rdi+30h], eax
0x18000d814  mov     ecx, 10000h
0x18000d819  test    ecx, r9d
0x18000d81c  jz      loc_18000D8E8
0x18000d822  or      [rdi+30h], ecx
0x18000d825  mov     edx, r15d
0x18000d828  movsx   eax, word ptr [rdi+36h]
0x18000d82c  cmp     edx, eax
0x18000d82e  jge     loc_18000D8E4
0x18000d834  movsxd  rax, edx
0x18000d837  lea     rcx, [rax+rax*2]
0x18000d83b  mov     rax, [rdi+8]
0x18000d83f  lea     r9, [rax+rcx*8]
0x18000d843  mov     ecx, [r9+8]
0x18000d847  mov     eax, ecx
0x18000d849  and     eax, 0F0h
0x18000d84e  jz      short loc_18000D895
0x18000d850  cmp     eax, 10h
0x18000d853  jnz     short loc_18000D85A
0x18000d855  mov     byte ptr [r9+0Ch], 41h ; 'A'
0x18000d85a  test    byte ptr [r9+12h], 1
0x18000d85f  jz      short loc_18000D87D
0x18000d861  movsx   eax, word ptr [rdi+34h]
0x18000d865  cmp     eax, edx
0x18000d867  jz      short loc_18000D87D
0x18000d869  test    cl, 0Fh
0x18000d86c  jnz     short loc_18000D87D
0x18000d86e  and     ecx, 0FFFFFFF2h
0x18000d871  or      ecx, 2
0x18000d874  mov     [r9+8], ecx
0x18000d878  bts     dword ptr [rdi+30h], 0Bh
0x18000d87d  inc     edx
0x18000d87f  jmp     short loc_18000D828
0x18000d881  lea     rdx, byte_18009EEF0
0x18000d888  mov     rcx, rsi
0x18000d88b  call    sqlite3ErrorMsg
0x18000d890  jmp     loc_18000DEB4
0x18000d895  test    byte ptr [r9+12h], 4
0x18000d89a  jz      short loc_18000D8CA
0x18000d89c  lea     rdx, byte_18009EEF0
0x18000d8a3  mov     rcx, r9
0x18000d8a6  call    sqlite3ColumnType
0x18000d8ab  mov     r9, [r9]
0x18000d8ae  lea     rdx, aUnknownDatatyp; "unknown datatype for %s.%s: \"%s\""
0x18000d8b5  mov     r8, [rdi]
0x18000d8b8  mov     rcx, rsi
0x18000d8bb  mov     [rsp+0D0h+var_B0], rax
0x18000d8c0  call    sqlite3ErrorMsg
0x18000d8c5  jmp     loc_18000DEB4
0x18000d8ca  mov     r9, [r9]
0x18000d8cd  lea     rdx, aMissingDatatyp; "missing datatype for %s.%s"
0x18000d8d4  mov     r8, [rdi]
0x18000d8d7  mov     rcx, rsi
0x18000d8da  call    sqlite3ErrorMsg
0x18000d8df  jmp     loc_18000DEB4
0x18000d8e4  mov     r9d, [rbp+4Fh+arg_18]
0x18000d8e8  test    r9b, r9b
0x18000d8eb  jns     short loc_18000D928
0x18000d8ed  mov     eax, [rdi+30h]
0x18000d8f0  test    al, 8
0x18000d8f2  jz      short loc_18000D8FD
0x18000d8f4  lea     rdx, aAutoincrementN; "AUTOINCREMENT not allowed on WITHOUT RO"...
0x18000d8fb  jmp     short loc_18000D888
0x18000d8fd  mov     rcx, rsi
0x18000d900  test    al, 4
0x18000d902  jnz     short loc_18000D918
0x18000d904  mov     r8, [rdi]
0x18000d907  lea     rdx, aPrimaryKeyMiss; "PRIMARY KEY missing on table %s"
0x18000d90e  call    sqlite3ErrorMsg
0x18000d913  jmp     loc_18000DEB4
0x18000d918  or      eax, 280h
0x18000d91d  mov     rdx, rdi
0x18000d920  mov     [rdi+30h], eax
0x18000d923  call    convertToWithoutRowidTable
0x18000d928  mov     rdx, [rdi+60h]
0x18000d92c  mov     rcx, r14
0x18000d92f  call    sqlite3SchemaToIndex
0x18000d934  mov     [rbp+4Fh+arg_0], eax
0x18000d937  mov     rax, [rdi+20h]
0x18000d93b  test    rax, rax
0x18000d93e  jz      short loc_18000D96D
0x18000d940  xor     r9d, r9d
0x18000d943  mov     [rsp+0D0h+var_B0], rax
0x18000d948  mov     rdx, rdi
0x18000d94b  mov     rcx, rsi
0x18000d94e  lea     r8d, [r9+4]
0x18000d952  call    sqlite3ResolveSelfReference
0x18000d957  cmp     [rsi+34h], r15d
0x18000d95b  jz      short loc_18000D96D
0x18000d95d  mov     rdx, [rdi+20h]
0x18000d961  mov     rcx, r14
0x18000d964  call    sqlite3ExprListDeleteGeneric
0x18000d969  mov     [rdi+20h], r15
0x18000d96d  test    byte ptr [rdi+30h], 60h
0x18000d971  jz      loc_18000DA17
0x18000d977  xor     eax, eax
0x18000d979  mov     ecx, r15d
0x18000d97c  mov     [rbp+4Fh+var_80], ecx
0x18000d97f  cmp     ax, [rdi+36h]
0x18000d983  jge     short loc_18000DA04
0x18000d985  movsxd  rax, r15d
0x18000d988  lea     rbx, [rax+rax*2]
0x18000d98c  mov     rax, [rdi+8]
0x18000d990  lea     rdx, [rax+rbx*8]
0x18000d994  test    byte ptr [rdx+12h], 60h
0x18000d998  jz      short loc_18000DA10
0x18000d99a  mov     rcx, rdi
0x18000d99d  call    sqlite3ColumnExpr
0x18000d9a2  mov     r9, rax
0x18000d9a5  mov     [rsp+0D0h+var_B0], 0
0x18000d9ae  mov     rcx, rsi
0x18000d9b1  mov     r8d, 8
0x18000d9b7  mov     rdx, rdi
0x18000d9ba  call    sqlite3ResolveSelfReference
0x18000d9bf  test    eax, eax
0x18000d9c1  jz      short loc_18000D9EE
0x18000d9c3  mov     rax, [rdi+8]
0x18000d9c7  xor     r9d, r9d
0x18000d9ca  xor     r8d, r8d
0x18000d9cd  mov     rcx, r14
0x18000d9d0  lea     edx, [r9+7Ah]
0x18000d9d4  lea     rbx, [rax+rbx*8]
0x18000d9d8  call    sqlite3ExprAlloc
0x18000d9dd  mov     r9, rax
0x18000d9e0  mov     r8, rbx
0x18000d9e3  mov     rdx, rdi
0x18000d9e6  mov     rcx, rsi
0x18000d9e9  call    sqlite3ColumnSetExpr
0x18000d9ee  mov     ecx, [rbp+4Fh+var_80]
0x18000d9f1  movsx   eax, word ptr [rdi+36h]
0x18000d9f5  inc     r15d
0x18000d9f8  cmp     r15d, eax
0x18000d9fb  jl      short loc_18000D985
0x18000d9fd  xor     r15d, r15d
0x18000da00  test    ecx, ecx
0x18000da02  jnz     short loc_18000DA17
0x18000da04  lea     rdx, aMustHaveAtLeas; "must have at least one non-generated co"...
0x18000da0b  jmp     loc_18000D888
0x18000da10  inc     ecx
0x18000da12  mov     [rbp+4Fh+var_80], ecx
0x18000da15  jmp     short loc_18000D9F1
0x18000da17  mov     rcx, rdi
0x18000da1a  call    estimateTableWidth
0x18000da1f  mov     rbx, [rdi+10h]
0x18000da23  jmp     short loc_18000DA31
0x18000da25  mov     rcx, rbx
0x18000da28  call    estimateIndexWidth
0x18000da2d  mov     rbx, [rbx+28h]
0x18000da31  test    rbx, rbx
0x18000da34  jnz     short loc_18000DA25
0x18000da36  cmp     [r14+0C5h], r15b
0x18000da3d  jnz     loc_18000DE45
0x18000da43  mov     rcx, rsi
0x18000da46  call    sqlite3GetVdbe
0x18000da4b  mov     r15, rax
0x18000da4e  test    rax, rax
0x18000da51  jz      loc_18000DEB4
0x18000da57  xor     r9d, r9d
0x18000da5a  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18000da5e  xor     r8d, r8d
0x18000da61  lea     edx, [rbx+7Ah]
0x18000da64  mov     rcx, rax
0x18000da67  call    sqlite3VdbeAddOp3
0x18000da6c  mov     cl, [rdi+3Fh]
0x18000da6f  lea     rax, aView; "VIEW"
0x18000da76  test    cl, cl
0x18000da78  lea     r8, aTable_0; "TABLE"
0x18000da7f  lea     rdx, aView_0; "view"
0x18000da86  cmovnz  r8, rax
0x18000da8a  lea     rax, aTable; "table"
0x18000da91  cmovnz  rax, rdx
0x18000da95  mov     [rbp+4Fh+var_70], rax
0x18000da99  test    r13, r13
0x18000da9c  jz      loc_18000DCD3
0x18000daa2  xor     eax, eax
0x18000daa4  xorps   xmm0, xmm0
0x18000daa7  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x18000daab  mov     qword ptr [rbp+4Fh+var_58+0Dh], rax
0x18000daaf  movups  [rbp+4Fh+var_68], xmm0
0x18000dab3  cmp     [rsi+134h], bl
0x18000dab9  jz      short loc_18000DACA
0x18000dabb  inc     dword ptr [rsi+34h]
0x18000dabe  mov     dword ptr [rsi+18h], 1
0x18000dac5  jmp     loc_18000DEB4
0x18000daca  mov     edx, [rsi+38h]
0x18000dacd  mov     rcx, rsi
0x18000dad0  mov     ebx, [rsi+3Ch]
0x18000dad3  mov     r8d, edx
0x18000dad6  mov     r12d, [rbp+4Fh+arg_0]
0x18000dada  inc     ebx
0x18000dadc  mov     [rbp+4Fh+var_80], edx
0x18000dadf  lea     eax, [rdx+1]
0x18000dae2  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x18000dae7  mov     [rsi+38h], eax
0x18000daea  mov     edx, 71h ; 'q'
0x18000daef  lea     eax, [rbx+1]
0x18000daf2  mov     [rbp+4Fh+var_78], eax
0x18000daf5  inc     eax
0x18000daf7  mov     [rsi+3Ch], eax
0x18000dafa  mov     [rbp+4Fh+var_7C], eax
0x18000dafd  mov     rax, [rsi+0B0h]
0x18000db04  test    rax, rax
0x18000db07  cmovnz  rcx, rax
0x18000db0b  mov     byte ptr [rcx+21h], 1
0x18000db0f  mov     rcx, r15
0x18000db12  mov     r9d, [rsi+8Ch]
0x18000db19  call    sqlite3VdbeAddOp3
0x18000db1e  mov     edx, 10h
0x18000db23  mov     rcx, r15
0x18000db26  call    sqlite3VdbeChangeP5
0x18000db2b  mov     eax, [r15+90h]
0x18000db32  xor     r9d, r9d
0x18000db35  mov     [rbp+4Fh+var_74], eax
0x18000db38  mov     r8d, ebx
0x18000db3b  inc     eax
0x18000db3d  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000db41  lea     edx, [r9+0Bh]
0x18000db45  call    sqlite3VdbeAddOp3
0x18000db4a  cmp     dword ptr [rsi+34h], 0
0x18000db4e  jnz     loc_18000DEB4
0x18000db54  mov     r8b, 41h ; 'A'
0x18000db57  mov     rdx, r13
0x18000db5a  mov     rcx, rsi
0x18000db5d  call    sqlite3ResultSetOfSelect
0x18000db62  test    rax, rax
0x18000db65  jz      loc_18000DEB4
0x18000db6b  movzx   ecx, word ptr [rax+36h]
0x18000db6f  mov     rdx, rax
0x18000db72  mov     [rdi+38h], cx
0x18000db76  mov     [rdi+36h], cx
0x18000db7a  mov     rcx, [rax+8]
0x18000db7e  mov     [rdi+8], rcx
0x18000db82  xor     ecx, ecx
0x18000db84  mov     [rax+36h], cx
0x18000db88  mov     [rax+8], rcx
0x18000db8c  mov     rcx, r14
0x18000db8f  call    sqlite3DeleteTable
0x18000db94  xor     eax, eax
0x18000db96  mov     byte ptr [rbp+4Fh+var_68], 0Dh
0x18000db9a  lea     r8, [rbp+4Fh+var_68]
0x18000db9e  mov     qword ptr [rbp+4Fh+var_68+8], rax
0x18000dba2  mov     rdx, r13
0x18000dba5  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x18000dba9  mov     rcx, rsi
0x18000dbac  mov     dword ptr [rbp+4Fh+var_58], eax
0x18000dbaf  mov     dword ptr [rbp+4Fh+var_68+4], ebx
0x18000dbb2  call    sqlite3Select
0x18000dbb7  cmp     dword ptr [rsi+34h], 0
0x18000dbbb  jnz     loc_18000DEB4
0x18000dbc1  xor     r9d, r9d
0x18000dbc4  mov     dword ptr [rsp+0D0h+var_B0], 0
0x18000dbcc  mov     r8d, ebx
0x18000dbcf  mov     rcx, r15
  ... truncated ...
```

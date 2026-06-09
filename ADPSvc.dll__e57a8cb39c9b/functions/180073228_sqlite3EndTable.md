# sqlite3EndTable

- ea: `0x180073228`
- end: `0x1800739bb`
- name: `sqlite3EndTable`
- size: `1939`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x180071400`
- `0x1800c3bd8`

## callees

- `0x1800404b4`
- `0x1800412d4`
- `0x180042554`
- `0x180043504`
- `0x180045b1c`
- `0x18006db58`
- `0x18006f18c`
- `0x18006f2e0`
- `0x18006f370`
- `0x1800716fc`
- `0x180073228`
- `0x180073aec`
- `0x1800740f0`
- `0x18007d478`
- `0x18007d618`
- `0x180080904`
- `0x180080b64`
- `0x1800817f4`
- `0x180081a3c`
- `0x18008a418`
- `0x18008a508`
- `0x18008b73c`
- `0x18008dd8c`
- `0x18008f1c8`
- `0x1800923d8`
- `0x180092638`
- `0x1800927e0`
- `0x180092e74`
- `0x18009a3b4`
- `0x1800c6e84`

## string_xrefs

- `0x180073804`: `CREATE %s %.*s`
- `0x18007381b`: `UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d`
- `0x1800738a1`: `CREATE TABLE %Q.sqlite_sequence(name,seq)`

## pseudocode

```c
int __fastcall sqlite3EndTable(__int64 *a1, const char *a2, _DWORD *a3, __int64 a4, __int64 a5)
{
  const char *Vdbe; // rax
  __int64 v6; // r12
  int v7; // r15d
  int v8; // r10d
  const char **v10; // rdi
  __int64 v11; // r14
  int v12; // eax
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // eax
  const char *v17; // rax
  const char **v18; // r9
  const char *v19; // rcx
  int v20; // r13d
  __int64 v21; // rdx
  const char *v22; // rdx
  int v23; // ecx
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rbx
  __int64 v27; // rax
  const char *v28; // r8
  int v29; // edx
  int i; // ecx
  int v31; // eax
  int v32; // ecx
  __int16 v33; // ax
  const char *v34; // rbx
  const char *v35; // r15
  char v36; // cl
  const char *v37; // r8
  const char *v38; // rax
  __int64 *v39; // rcx
  int v40; // r8d
  unsigned int v41; // ebx
  __int64 v42; // rax
  __int64 v43; // r8
  __int16 v44; // cx
  bool v45; // zf
  unsigned int v46; // ebx
  __int64 TableStmt; // rax
  _DWORD *v48; // rcx
  int v49; // r9d
  __int64 v50; // rbx
  __int64 v51; // r12
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rbx
  unsigned int v55; // eax
  unsigned int v57; // [rsp+58h] [rbp-31h]
  unsigned int v58; // [rsp+5Ch] [rbp-2Dh]
  int v59; // [rsp+60h] [rbp-29h]
  const char *v60; // [rsp+68h] [rbp-21h]
  _OWORD v61[6]; // [rsp+70h] [rbp-19h] BYREF
  _UNKNOWN *retaddr; // [rsp+E0h] [rbp+57h] BYREF
  int v63; // [rsp+E8h] [rbp+5Fh]
  unsigned int v64; // [rsp+E8h] [rbp+5Fh]
  int v67; // [rsp+100h] [rbp+77h]

  Vdbe = (const char *)&retaddr;
  v67 = a4;
  v6 = a5;
  v7 = 0;
  v8 = a4;
  if ( !a3 && !a5 )
    return (int)Vdbe;
  v10 = (const char **)a1[44];
  if ( !v10 )
    return (int)Vdbe;
  v11 = *a1;
  if ( !a5 )
  {
    v12 = sqlite3ShadowTableName(*a1, *v10);
    v8 = v67;
    if ( v12 )
      *((_DWORD *)v10 + 12) |= 0x1000u;
  }
  if ( *(_BYTE *)(v11 + 197) )
  {
    if ( a5 || *((_BYTE *)v10 + 63) && *(_DWORD *)(v11 + 192) )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, (const char *)&Src);
      return (int)Vdbe;
    }
    v13 = *(_DWORD *)(v11 + 192);
    *((_DWORD *)v10 + 10) = v13;
    if ( v13 == 1 )
      *((_DWORD *)v10 + 12) |= 1u;
  }
  if ( (v8 & 0x10000) != 0 )
  {
    *((_DWORD *)v10 + 12) |= 0x10000u;
    v14 = 0;
    if ( *((__int16 *)v10 + 27) > 0 )
    {
      while ( 1 )
      {
        a4 = (__int64)&v10[1][24 * v14];
        v15 = *(_DWORD *)(a4 + 8);
        if ( (v15 & 0xF0) == 0 )
          break;
        if ( (*(_DWORD *)(a4 + 8) & 0xF0) == 0x10 )
          *(_BYTE *)(a4 + 12) = 65;
        if ( (*(_BYTE *)(a4 + 18) & 1) != 0 && *((__int16 *)v10 + 26) != v14 && (v15 & 0xF) == 0 )
        {
          *(_DWORD *)(a4 + 8) = v15 & 0xFFFFFFF0 | 2;
          *((_DWORD *)v10 + 12) |= 0x800u;
        }
        if ( ++v14 >= *((__int16 *)v10 + 27) )
          goto LABEL_23;
      }
      if ( (*(_BYTE *)(a4 + 18) & 4) != 0 )
      {
        v17 = (const char *)sqlite3ColumnType(a4, &Src);
        LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "unknown datatype for %s.%s: \"%s\"", *v10, *v18, v17);
      }
      else
      {
        LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "missing datatype for %s.%s", *v10, *(const char **)a4);
      }
      return (int)Vdbe;
    }
  }
LABEL_23:
  if ( (v8 & 0x80u) != 0 )
  {
    v16 = *((_DWORD *)v10 + 12);
    if ( (v16 & 8) != 0 )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "AUTOINCREMENT not allowed on WITHOUT ROWID tables");
      return (int)Vdbe;
    }
    if ( (v16 & 4) == 0 )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "PRIMARY KEY missing on table %s", *v10);
      return (int)Vdbe;
    }
    *((_DWORD *)v10 + 12) = v16 | 0x280;
    convertToWithoutRowidTable(a1, v10);
  }
  v19 = v10[12];
  v20 = -32768;
  if ( v19 )
  {
    v21 = *(_QWORD *)(v11 + 32);
    v20 = 0;
    if ( *(const char **)(v21 + 24) != v19 )
    {
      do
        ++v20;
      while ( *(const char **)(32LL * v20 + v21 + 24) != v19 );
    }
  }
  if ( v10[4] )
  {
    sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v10, 4, 0, (__int64)v10[4]);
    if ( *((_DWORD *)a1 + 12) )
    {
      v22 = v10[4];
      if ( v22 )
        exprListDeleteNN(v11, v22);
      v10[4] = 0;
    }
  }
  if ( ((_BYTE)v10[6] & 0x60) != 0 )
  {
    v23 = 0;
    v63 = 0;
    if ( *((__int16 *)v10 + 27) <= 0 )
      goto LABEL_49;
    do
    {
      v24 = (__int64)&v10[1][24 * v7];
      if ( (*(_BYTE *)(v24 + 18) & 0x60) != 0 )
      {
        v25 = sqlite3ColumnExpr(v10, v24, a3, a4);
        if ( (unsigned int)sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v10, 8, v25, 0) )
        {
          v26 = (__int64)&v10[1][24 * v7];
          v27 = sqlite3ExprAlloc(v11, 121, 0);
          sqlite3ColumnSetExpr(a1, v10, v26, v27);
        }
        v23 = v63;
      }
      else
      {
        v63 = ++v23;
      }
      ++v7;
    }
    while ( v7 < *((__int16 *)v10 + 27) );
    v6 = a5;
    if ( !v23 )
    {
LABEL_49:
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "must have at least one non-generated column");
      return (int)Vdbe;
    }
  }
  v28 = v10[1];
  v29 = 0;
  for ( i = *((__int16 *)v10 + 27); i > 0; --i )
  {
    v31 = *((unsigned __int8 *)v28 + 13);
    v28 += 24;
    v29 += v31;
  }
  v32 = v29 + 1;
  if ( *((__int16 *)v10 + 26) >= 0 )
    v32 = v29;
  v33 = sqlite3LogEst((unsigned int)(4 * v32));
  v34 = v10[2];
  *((_WORD *)v10 + 30) = v33;
  while ( v34 )
  {
    estimateIndexWidth(v34);
    v34 = (const char *)*((_QWORD *)v34 + 5);
  }
  if ( *(_BYTE *)(v11 + 197) )
    goto LABEL_93;
  Vdbe = (const char *)sqlite3GetVdbe(a1);
  v35 = Vdbe;
  if ( !Vdbe )
    return (int)Vdbe;
  sqlite3VdbeAddOp3((_DWORD)Vdbe, 122, 0, 0, 0);
  v36 = *((_BYTE *)v10 + 63);
  v37 = "TABLE";
  if ( v36 )
    v37 = "VIEW";
  v38 = "table";
  if ( v36 )
    v38 = "view";
  v60 = v38;
  if ( !v6 )
  {
    v48 = a1 + 36;
    if ( !v67 )
      v48 = a3;
    v49 = *v48 - *((_DWORD *)a1 + 68);
    if ( **(_BYTE **)v48 != 59 )
      v49 += v48[2];
    TableStmt = sqlite3MPrintf(v11, "CREATE %s %.*s", v37, v49, (const char *)a1[34]);
LABEL_84:
    v50 = TableStmt;
    v51 = 32LL * v20;
    sqlite3NestedParse(
      a1,
      "UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d",
      *(_QWORD *)(v51 + *(_QWORD *)(v11 + 32)),
      v60,
      *v10,
      *v10,
      *((_DWORD *)a1 + 35),
      TableStmt,
      *((_DWORD *)a1 + 34));
    if ( v50 )
      sqlite3DbFreeNN(v11);
    sqlite3ChangeCookie(a1, (unsigned int)v20);
    if ( ((_BYTE)v10[6] & 8) != 0 && !*((_BYTE *)a1 + 308) )
    {
      v52 = *(_QWORD *)(v11 + 32);
      if ( !*(_QWORD *)(*(_QWORD *)(v51 + v52 + 24) + 104LL) )
        sqlite3NestedParse(a1, "CREATE TABLE %Q.sqlite_sequence(name,seq)", *(_QWORD *)(v51 + v52));
    }
    v53 = sqlite3MPrintf(v11, "tbl_name='%q' AND type!='trigger'", *v10);
    LODWORD(Vdbe) = sqlite3VdbeAddParseSchemaOp(v35, (unsigned int)v20, v53, 0);
    if ( ((_BYTE)v10[6] & 0x60) != 0 )
    {
      v54 = sqlite3MPrintf(v11, "SELECT*FROM\"%w\".\"%w\"", *(_QWORD *)(v51 + *(_QWORD *)(v11 + 32)), *v10);
      v55 = sqlite3VdbeAddOp3((_DWORD)v35, 148, 1, 0, 0);
      LODWORD(Vdbe) = sqlite3VdbeChangeP4(v35, v55, v54, 4294967290LL);
    }
    v6 = a5;
    if ( !*(_BYTE *)(v11 + 197) )
    {
LABEL_97:
      if ( !v6 && !*((_BYTE *)v10 + 63) )
      {
        Vdbe = (const char *)a3;
        if ( *(_QWORD *)a2 )
          Vdbe = a2;
        LODWORD(Vdbe) = *(_DWORD *)Vdbe - *((_DWORD *)a1 + 68) + 13;
        *((_DWORD *)v10 + 16) = (_DWORD)Vdbe;
      }
      return (int)Vdbe;
    }
LABEL_93:
    if ( sqlite3HashInsert(v10[12] + 8, *v10, v10) )
    {
      LODWORD(Vdbe) = sqlite3OomFault(v11);
      return (int)Vdbe;
    }
    a1[44] = 0;
    *(_DWORD *)(v11 + 44) |= 1u;
    LODWORD(Vdbe) = strcmp_0(*v10, "sqlite_sequence");
    if ( !(_DWORD)Vdbe )
    {
      Vdbe = v10[12];
      *((_QWORD *)Vdbe + 13) = v10;
    }
    goto LABEL_97;
  }
  LODWORD(Vdbe) = 0;
  memset(v61, 0, 37);
  if ( *((_BYTE *)a1 + 308) )
  {
    ++*((_DWORD *)a1 + 12);
    *((_DWORD *)a1 + 6) = 1;
    return (int)Vdbe;
  }
  v39 = a1;
  v40 = *((_DWORD *)a1 + 13);
  v41 = *((_DWORD *)a1 + 14) + 1;
  v59 = v40;
  *((_DWORD *)a1 + 13) = v40 + 1;
  v57 = v41 + 1;
  *((_DWORD *)a1 + 14) = v41 + 2;
  v64 = v41 + 2;
  if ( a1[22] )
    v39 = (__int64 *)a1[22];
  *((_BYTE *)v39 + 33) = 1;
  sqlite3VdbeAddOp3((_DWORD)v35, 113, v40, *((_DWORD *)a1 + 35), v20);
  v42 = *((int *)v35 + 36);
  if ( (int)v42 > 0 )
    *(_WORD *)(*((_QWORD *)v35 + 17) + 24 * v42 - 22) = 16;
  v58 = *((_DWORD *)v35 + 36);
  LODWORD(Vdbe) = sqlite3VdbeAddOp3((_DWORD)v35, 11, v41, 0, v58 + 1);
  if ( !*((_DWORD *)a1 + 12) )
  {
    LOBYTE(v43) = 65;
    Vdbe = (const char *)sqlite3ResultSetOfSelect(a1, v6, v43);
    if ( Vdbe )
    {
      v44 = *((_WORD *)Vdbe + 27);
      *((_WORD *)v10 + 28) = v44;
      *((_WORD *)v10 + 27) = v44;
      v10[1] = (const char *)*((_QWORD *)Vdbe + 1);
      *((_WORD *)Vdbe + 27) = 0;
      *((_QWORD *)Vdbe + 1) = 0;
      if ( *(_QWORD *)(v11 + 776) || (v45 = *((_DWORD *)Vdbe + 11) == 1, --*((_DWORD *)Vdbe + 11), v45) )
        deleteTable(v11, Vdbe, 0);
      *((_QWORD *)&v61[1] + 1) = 0;
      LODWORD(v61[1]) = 0;
      LOBYTE(v61[0]) = 13;
      DWORD1(v61[0]) = v41;
      *((_QWORD *)&v61[0] + 1) = 0;
      LODWORD(Vdbe) = sqlite3Select(a1, v6, v61);
      if ( !*((_DWORD *)a1 + 12) )
      {
        sqlite3VdbeEndCoroutine(v35, v41);
        sqlite3VdbeJumpHere(v35, v58);
        v46 = sqlite3VdbeAddOp3((_DWORD)v35, 12, DWORD1(v61[0]), 0, 0);
        sqlite3VdbeAddOp3((_DWORD)v35, 97, HIDWORD(v61[0]), v61[1], v57);
        sqlite3TableAffinity(v35, v10, 0);
        sqlite3VdbeAddOp3((_DWORD)v35, 127, v59, v64, 0);
        sqlite3VdbeAddOp3((_DWORD)v35, 128, v59, v57, v64);
        sqlite3VdbeAddOp3((_DWORD)v35, 9, 0, v46, 0);
        sqlite3VdbeJumpHere(v35, v46);
        sqlite3VdbeAddOp3((_DWORD)v35, 122, v59, 0, 0);
        TableStmt = createTableStmt(v11, v10);
        goto LABEL_84;
      }
    }
  }
  return (int)Vdbe;
}

```

## disassembly

```asm
0x180073228  mov     rax, rsp
0x18007322b  mov     [rax+20h], r9d
0x18007322f  mov     [rax+18h], r8
0x180073233  mov     [rax+10h], rdx
0x180073237  push    rbp
0x180073238  push    rbx
0x180073239  push    rsi
0x18007323a  push    rdi
0x18007323b  push    r12
0x18007323d  push    r13
0x18007323f  push    r14
0x180073241  push    r15
0x180073243  lea     rbp, [rax-57h]
0x180073247  sub     rsp, 98h
0x18007324e  mov     r12, [rbp+4Fh+arg_20]
0x180073252  xor     r15d, r15d
0x180073255  mov     r10d, r9d
0x180073258  mov     rsi, rcx
0x18007325b  test    r8, r8
0x18007325e  jnz     short loc_180073269
0x180073260  test    r12, r12
0x180073263  jz      loc_1800739A7
0x180073269  mov     rdi, [rcx+160h]
0x180073270  test    rdi, rdi
0x180073273  jz      loc_1800739A7
0x180073279  mov     r14, [rcx]
0x18007327c  test    r12, r12
0x18007327f  jnz     short loc_180073299
0x180073281  mov     rdx, [rdi]
0x180073284  mov     rcx, r14
0x180073287  call    sqlite3ShadowTableName
0x18007328c  mov     r10d, [rbp+4Fh+arg_18]
0x180073290  test    eax, eax
0x180073292  jz      short loc_180073299
0x180073294  bts     dword ptr [rdi+30h], 0Ch
0x180073299  cmp     [r14+0C5h], r15b
0x1800732a0  jz      short loc_1800732D0
0x1800732a2  test    r12, r12
0x1800732a5  jnz     loc_180073353
0x1800732ab  cmp     [rdi+3Fh], r15b
0x1800732af  jz      short loc_1800732BE
0x1800732b1  cmp     [r14+0C0h], r15d
0x1800732b8  jnz     loc_180073353
0x1800732be  mov     eax, [r14+0C0h]
0x1800732c5  mov     [rdi+28h], eax
0x1800732c8  cmp     eax, 1
0x1800732cb  jnz     short loc_1800732D0
0x1800732cd  or      [rdi+30h], eax
0x1800732d0  mov     ecx, 10000h
0x1800732d5  test    ecx, r10d
0x1800732d8  jz      short loc_18007333A
0x1800732da  or      [rdi+30h], ecx
0x1800732dd  mov     edx, r15d
0x1800732e0  cmp     r15w, [rdi+36h]
0x1800732e5  jge     short loc_18007333A
0x1800732e7  movsxd  rax, edx
0x1800732ea  lea     rcx, [rax+rax*2]
0x1800732ee  mov     rax, [rdi+8]
0x1800732f2  lea     r9, [rax+rcx*8]
0x1800732f6  mov     ecx, [r9+8]
0x1800732fa  mov     eax, ecx
0x1800732fc  and     eax, 0F0h
0x180073301  jz      short loc_180073367
0x180073303  cmp     eax, 10h
0x180073306  jnz     short loc_18007330D
0x180073308  mov     byte ptr [r9+0Ch], 41h ; 'A'
0x18007330d  test    byte ptr [r9+12h], 1
0x180073312  jz      short loc_180073330
0x180073314  movsx   eax, word ptr [rdi+34h]
0x180073318  cmp     eax, edx
0x18007331a  jz      short loc_180073330
0x18007331c  test    cl, 0Fh
0x18007331f  jnz     short loc_180073330
0x180073321  and     ecx, 0FFFFFFF2h
0x180073324  or      ecx, 2
0x180073327  mov     [r9+8], ecx
0x18007332b  bts     dword ptr [rdi+30h], 0Bh
0x180073330  movsx   eax, word ptr [rdi+36h]
0x180073334  inc     edx
0x180073336  cmp     edx, eax
0x180073338  jl      short loc_1800732E7
0x18007333a  test    r10b, r10b
0x18007333d  jns     loc_1800733E1
0x180073343  mov     eax, [rdi+30h]
0x180073346  test    al, 8
0x180073348  jz      short loc_1800733B6
0x18007334a  lea     rdx, aAutoincrementN; "AUTOINCREMENT not allowed on WITHOUT RO"...
0x180073351  jmp     short loc_18007335A
0x180073353  lea     rdx, Src
0x18007335a  mov     rcx, rsi
0x18007335d  call    sqlite3ErrorMsg
0x180073362  jmp     loc_1800739A7
0x180073367  test    byte ptr [r9+12h], 4
0x18007336c  jz      short loc_18007339C
0x18007336e  lea     rdx, Src
0x180073375  mov     rcx, r9
0x180073378  call    sqlite3ColumnType
0x18007337d  mov     r9, [r9]
0x180073380  lea     rdx, aUnknownDatatyp; "unknown datatype for %s.%s: \"%s\""
0x180073387  mov     r8, [rdi]
0x18007338a  mov     rcx, rsi
0x18007338d  mov     [rsp+0D0h+var_B0], rax
0x180073392  call    sqlite3ErrorMsg
0x180073397  jmp     loc_1800739A7
0x18007339c  mov     r9, [r9]
0x18007339f  lea     rdx, aMissingDatatyp; "missing datatype for %s.%s"
0x1800733a6  mov     r8, [rdi]
0x1800733a9  mov     rcx, rsi
0x1800733ac  call    sqlite3ErrorMsg
0x1800733b1  jmp     loc_1800739A7
0x1800733b6  mov     rcx, rsi
0x1800733b9  test    al, 4
0x1800733bb  jnz     short loc_1800733D1
0x1800733bd  mov     r8, [rdi]
0x1800733c0  lea     rdx, aPrimaryKeyMiss; "PRIMARY KEY missing on table %s"
0x1800733c7  call    sqlite3ErrorMsg
0x1800733cc  jmp     loc_1800739A7
0x1800733d1  or      eax, 280h
0x1800733d6  mov     rdx, rdi
0x1800733d9  mov     [rdi+30h], eax
0x1800733dc  call    convertToWithoutRowidTable
0x1800733e1  mov     rcx, [rdi+60h]
0x1800733e5  mov     r13d, 0FFFF8000h
0x1800733eb  test    rcx, rcx
0x1800733ee  jz      short loc_18007340E
0x1800733f0  mov     rdx, [r14+20h]
0x1800733f4  mov     r13d, r15d
0x1800733f7  cmp     [rdx+18h], rcx
0x1800733fb  jz      short loc_18007340E
0x1800733fd  inc     r13d
0x180073400  movsxd  rax, r13d
0x180073403  shl     rax, 5
0x180073407  cmp     [rax+rdx+18h], rcx
0x18007340c  jnz     short loc_1800733FD
0x18007340e  mov     rax, [rdi+20h]
0x180073412  test    rax, rax
0x180073415  jz      short loc_180073449
0x180073417  xor     r9d, r9d
0x18007341a  mov     [rsp+0D0h+var_B0], rax
0x18007341f  mov     rdx, rdi
0x180073422  mov     rcx, rsi
0x180073425  lea     r8d, [r9+4]
0x180073429  call    sqlite3ResolveSelfReference
0x18007342e  cmp     [rsi+30h], r15d
0x180073432  jz      short loc_180073449
0x180073434  mov     rdx, [rdi+20h]
0x180073438  test    rdx, rdx
0x18007343b  jz      short loc_180073445
0x18007343d  mov     rcx, r14
0x180073440  call    exprListDeleteNN
0x180073445  mov     [rdi+20h], r15
0x180073449  test    byte ptr [rdi+30h], 60h
0x18007344d  jz      loc_1800734FA
0x180073453  xor     eax, eax
0x180073455  mov     ecx, r15d
0x180073458  mov     [rbp+4Fh+arg_0], ecx
0x18007345b  cmp     ax, [rdi+36h]
0x18007345f  jge     loc_1800734E7
0x180073465  xor     r12d, r12d
0x180073468  movsxd  rax, r15d
0x18007346b  lea     rbx, [rax+rax*2]
0x18007346f  mov     rax, [rdi+8]
0x180073473  lea     rdx, [rax+rbx*8]
0x180073477  test    byte ptr [rdx+12h], 60h
0x18007347b  jz      short loc_1800734F3
0x18007347d  mov     rcx, rdi
0x180073480  call    sqlite3ColumnExpr
0x180073485  mov     r9, rax
0x180073488  mov     [rsp+0D0h+var_B0], r12
0x18007348d  mov     rcx, rsi
0x180073490  mov     r8d, 8
0x180073496  mov     rdx, rdi
0x180073499  call    sqlite3ResolveSelfReference
0x18007349e  test    eax, eax
0x1800734a0  jz      short loc_1800734CD
0x1800734a2  mov     rax, [rdi+8]
0x1800734a6  xor     r9d, r9d
0x1800734a9  xor     r8d, r8d
0x1800734ac  mov     rcx, r14
0x1800734af  lea     edx, [r9+79h]
0x1800734b3  lea     rbx, [rax+rbx*8]
0x1800734b7  call    sqlite3ExprAlloc
0x1800734bc  mov     r9, rax
0x1800734bf  mov     r8, rbx
0x1800734c2  mov     rdx, rdi
0x1800734c5  mov     rcx, rsi
0x1800734c8  call    sqlite3ColumnSetExpr
0x1800734cd  mov     ecx, [rbp+4Fh+arg_0]
0x1800734d0  movsx   eax, word ptr [rdi+36h]
0x1800734d4  inc     r15d
0x1800734d7  cmp     r15d, eax
0x1800734da  jl      short loc_180073468
0x1800734dc  mov     r12, [rbp+4Fh+arg_20]
0x1800734e0  xor     r15d, r15d
0x1800734e3  test    ecx, ecx
0x1800734e5  jnz     short loc_1800734FA
0x1800734e7  lea     rdx, aMustHaveAtLeas; "must have at least one non-generated co"...
0x1800734ee  jmp     loc_18007335A
0x1800734f3  inc     ecx
0x1800734f5  mov     [rbp+4Fh+arg_0], ecx
0x1800734f8  jmp     short loc_1800734D0
0x1800734fa  mov     r8, [rdi+8]
0x1800734fe  mov     edx, r15d
0x180073501  movsx   ecx, word ptr [rdi+36h]
0x180073505  jmp     short loc_180073514
0x180073507  movzx   eax, byte ptr [r8+0Dh]
0x18007350c  lea     r8, [r8+18h]
0x180073510  add     edx, eax
0x180073512  dec     ecx
0x180073514  test    ecx, ecx
0x180073516  jg      short loc_180073507
0x180073518  cmp     [rdi+34h], r15w
0x18007351d  lea     ecx, [rdx+1]
0x180073520  cmovge  ecx, edx
0x180073523  shl     ecx, 2
0x180073526  call    sqlite3LogEst
0x18007352b  mov     rbx, [rdi+10h]
0x18007352f  mov     [rdi+3Ch], ax
0x180073533  jmp     short loc_180073541
0x180073535  mov     rcx, rbx
0x180073538  call    estimateIndexWidth
0x18007353d  mov     rbx, [rbx+28h]
0x180073541  test    rbx, rbx
0x180073544  jnz     short loc_180073535
0x180073546  cmp     [r14+0C5h], r15b
0x18007354d  jnz     loc_180073936
0x180073553  mov     rcx, rsi
0x180073556  call    sqlite3GetVdbe
0x18007355b  mov     r15, rax
0x18007355e  test    rax, rax
0x180073561  jz      loc_1800739A7
0x180073567  xor     r9d, r9d
0x18007356a  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18007356e  xor     r8d, r8d
0x180073571  lea     edx, [rbx+7Ah]
0x180073574  mov     rcx, rax
0x180073577  call    sqlite3VdbeAddOp3
0x18007357c  mov     cl, [rdi+3Fh]
0x18007357f  lea     rax, aView; "VIEW"
0x180073586  test    cl, cl
0x180073588  lea     r8, aTable_0; "TABLE"
0x18007358f  lea     rdx, aView_0; "view"
0x180073596  cmovnz  r8, rax
0x18007359a  lea     rax, aTable; "table"
0x1800735a1  cmovnz  rax, rdx
0x1800735a5  mov     [rbp+4Fh+var_70], rax
0x1800735a9  test    r12, r12
0x1800735ac  jz      loc_1800737D7
0x1800735b2  xor     eax, eax
0x1800735b4  xorps   xmm0, xmm0
0x1800735b7  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x1800735bb  mov     qword ptr [rbp+4Fh+var_58+0Dh], rax
0x1800735bf  movups  [rbp+4Fh+var_68], xmm0
0x1800735c3  cmp     [rsi+134h], bl
0x1800735c9  jz      short loc_1800735DA
0x1800735cb  inc     dword ptr [rsi+30h]
0x1800735ce  mov     dword ptr [rsi+18h], 1
0x1800735d5  jmp     loc_1800739A7
0x1800735da  mov     edx, [rsi+34h]
0x1800735dd  mov     rcx, rsi
0x1800735e0  mov     ebx, [rsi+38h]
0x1800735e3  mov     r8d, edx
0x1800735e6  inc     ebx
0x1800735e8  mov     [rbp+4Fh+var_78], edx
0x1800735eb  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x1800735f0  lea     eax, [rdx+1]
0x1800735f3  mov     edx, 71h ; 'q'
0x1800735f8  mov     [rsi+34h], eax
0x1800735fb  lea     eax, [rbx+1]
0x1800735fe  mov     [rbp+4Fh+var_80], eax
0x180073601  inc     eax
0x180073603  mov     [rsi+38h], eax
0x180073606  mov     [rbp+4Fh+arg_0], eax
0x180073609  mov     rax, [rsi+0B0h]
0x180073610  test    rax, rax
0x180073613  cmovnz  rcx, rax
0x180073617  mov     byte ptr [rcx+21h], 1
0x18007361b  mov     rcx, r15
0x18007361e  mov     r9d, [rsi+8Ch]
0x180073625  call    sqlite3VdbeAddOp3
0x18007362a  movsxd  rax, dword ptr [r15+90h]
0x180073631  test    eax, eax
0x180073633  jle     short loc_180073647
0x180073635  lea     rcx, [rax+rax*2]
0x180073639  mov     rax, [r15+88h]
0x180073640  mov     word ptr [rax+rcx*8-16h], 10h
0x180073647  mov     eax, [r15+90h]
0x18007364e  xor     r9d, r9d
0x180073651  mov     [rbp+4Fh+var_7C], eax
0x180073654  mov     r8d, ebx
0x180073657  inc     eax
0x180073659  mov     rcx, r15
0x18007365c  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180073660  lea     edx, [r9+0Bh]
0x180073664  call    sqlite3VdbeAddOp3
0x180073669  cmp     dword ptr [rsi+30h], 0
0x18007366d  jnz     loc_1800739A7
0x180073673  mov     r8b, 41h ; 'A'
0x180073676  mov     rdx, r12
0x180073679  mov     rcx, rsi
  ... truncated ...
```

# sqlite3EndTable

- ea: `0x140055854`
- end: `0x140055f95`
- name: `sqlite3EndTable`
- size: `1857`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `installer_update`

## callers

- `0x140053b3c`
- `0x1400a40bc`

## callees

- `0x140025c04`
- `0x1400269b4`
- `0x140027ba8`
- `0x140028b74`
- `0x14002b178`
- `0x140050530`
- `0x1400518c4`
- `0x140051a18`
- `0x140051aa8`
- `0x140053e3c`
- `0x140055854`
- `0x1400560c4`
- `0x1400563f0`
- `0x14005f5fc`
- `0x14005f79c`
- `0x14006299c`
- `0x140062bfc`
- `0x14006348c`
- `0x1400636dc`
- `0x14006bae0`
- `0x14006bbd0`
- `0x14006cd0c`
- `0x14006f318`
- `0x140070708`
- `0x1400738a0`
- `0x140073b00`
- `0x14007433c`
- `0x14007b574`
- `0x1400a72e4`

## string_xrefs

- `0x140055e68`: `UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d`
- `0x140055e2d`: `CREATE %s %.*s`
- `0x140055ecf`: `CREATE TABLE %Q.sqlite_sequence(name,seq)`

## pseudocode

```c
int __fastcall sqlite3EndTable(_QWORD *a1, const char *a2, _DWORD *a3, int a4, __int64 a5)
{
  const char *Vdbe; // rax
  __int64 v6; // r13
  int v7; // r15d
  int v8; // r10d
  const char **v10; // rdi
  __int64 v11; // r14
  int v12; // eax
  int v13; // eax
  int v14; // edx
  __int64 v15; // r9
  int v16; // ecx
  int v17; // eax
  const char *v18; // rax
  const char **v19; // r9
  const char *v20; // rcx
  int v21; // r12d
  __int64 v22; // rdx
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
  unsigned int v39; // ebx
  _QWORD *v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r8
  __int16 v43; // cx
  bool v44; // zf
  unsigned int v45; // ebx
  __int64 TableStmt; // rax
  _DWORD *v47; // rcx
  int v48; // r9d
  __int64 v49; // rbx
  __int64 v50; // r8
  __int64 v51; // rax
  int v53; // [rsp+58h] [rbp-31h]
  unsigned int v54; // [rsp+5Ch] [rbp-2Dh]
  const char *v55; // [rsp+68h] [rbp-21h]
  _OWORD v56[6]; // [rsp+70h] [rbp-19h] BYREF
  _UNKNOWN *retaddr; // [rsp+E0h] [rbp+57h] BYREF
  int v58; // [rsp+E8h] [rbp+5Fh]
  unsigned int v59; // [rsp+E8h] [rbp+5Fh]
  __int64 v60; // [rsp+E8h] [rbp+5Fh]

  Vdbe = (const char *)&retaddr;
  v6 = a5;
  v7 = 0;
  v8 = a4;
  if ( !a3 && !a5 )
    return (int)Vdbe;
  v10 = (const char **)a1[43];
  if ( !v10 )
    return (int)Vdbe;
  v11 = *a1;
  if ( !a5 )
  {
    v12 = sqlite3ShadowTableName(*a1, *v10);
    v8 = a4;
    if ( v12 )
      *((_DWORD *)v10 + 12) |= 0x1000u;
  }
  if ( *(_BYTE *)(v11 + 197) )
  {
    if ( a5 || *((_BYTE *)v10 + 63) && *(_DWORD *)(v11 + 192) )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, (const char *)&dword_1400ACDEC);
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
        v15 = (__int64)&v10[1][24 * v14];
        v16 = *(_DWORD *)(v15 + 8);
        if ( (v16 & 0xF0) == 0 )
          break;
        if ( (*(_DWORD *)(v15 + 8) & 0xF0) == 0x10 )
          *(_BYTE *)(v15 + 12) = 65;
        if ( (*(_BYTE *)(v15 + 18) & 1) != 0 && *((__int16 *)v10 + 26) != v14 && (v16 & 0xF) == 0 )
        {
          *(_DWORD *)(v15 + 8) = v16 & 0xFFFFFFF0 | 2;
          *((_DWORD *)v10 + 12) |= 0x800u;
        }
        if ( ++v14 >= *((__int16 *)v10 + 27) )
          goto LABEL_23;
      }
      if ( (*(_BYTE *)(v15 + 18) & 4) != 0 )
      {
        v18 = (const char *)sqlite3ColumnType(v15, &dword_1400ACDEC);
        LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "unknown datatype for %s.%s: \"%s\"", *v10, *v19, v18);
      }
      else
      {
        LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "missing datatype for %s.%s", *v10, *(const char **)v15);
      }
      return (int)Vdbe;
    }
  }
LABEL_23:
  if ( (v8 & 0x80u) != 0 )
  {
    v17 = *((_DWORD *)v10 + 12);
    if ( (v17 & 8) != 0 )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "AUTOINCREMENT not allowed on WITHOUT ROWID tables");
      return (int)Vdbe;
    }
    if ( (v17 & 4) == 0 )
    {
      LODWORD(Vdbe) = sqlite3ErrorMsg(a1, "PRIMARY KEY missing on table %s", *v10);
      return (int)Vdbe;
    }
    *((_DWORD *)v10 + 12) = v17 | 0x280;
    convertToWithoutRowidTable(a1, v10);
  }
  v20 = v10[12];
  v21 = -32768;
  if ( v20 )
  {
    v22 = *(_QWORD *)(v11 + 32);
    v21 = 0;
    if ( *(const char **)(v22 + 24) != v20 )
    {
      do
        ++v21;
      while ( *(const char **)(32LL * v21 + v22 + 24) != v20 );
    }
  }
  if ( v10[4] )
  {
    sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v10, 4, 0, (__int64)v10[4]);
    if ( *((_DWORD *)a1 + 12) )
    {
      if ( v10[4] )
        exprListDeleteNN(v11);
      v10[4] = 0;
    }
  }
  if ( ((_BYTE)v10[6] & 0x60) != 0 )
  {
    v23 = 0;
    v58 = 0;
    if ( *((__int16 *)v10 + 27) <= 0 )
      goto LABEL_49;
    do
    {
      v24 = (__int64)&v10[1][24 * v7];
      if ( (*(_BYTE *)(v24 + 18) & 0x60) != 0 )
      {
        v25 = sqlite3ColumnExpr(v10, v24);
        if ( (unsigned int)sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v10, 8, v25, 0) )
        {
          v26 = (__int64)&v10[1][24 * v7];
          v27 = sqlite3ExprAlloc(v11, 121, 0);
          sqlite3ColumnSetExpr(a1, v10, v26, v27);
        }
        v23 = v58;
      }
      else
      {
        v58 = ++v23;
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
    goto LABEL_91;
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
  v55 = v38;
  if ( !v6 )
  {
    v47 = a1 + 35;
    if ( !a4 )
      v47 = a3;
    v48 = *v47 - *((_DWORD *)a1 + 66);
    if ( **(_BYTE **)v47 != 59 )
      v48 += v47[2];
    TableStmt = sqlite3MPrintf(v11, "CREATE %s %.*s", v37, v48, (const char *)a1[33]);
LABEL_84:
    v60 = TableStmt;
    v49 = 32LL * v21;
    sqlite3NestedParse(
      a1,
      "UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d",
      *(_QWORD *)(v49 + *(_QWORD *)(v11 + 32)),
      v55,
      *v10,
      *v10,
      *((_DWORD *)a1 + 33),
      TableStmt,
      *((_DWORD *)a1 + 32));
    if ( v60 )
      sqlite3DbFreeNN(v11);
    sqlite3ChangeCookie(a1, (unsigned int)v21);
    if ( ((_BYTE)v10[6] & 8) != 0 && !*((_BYTE *)a1 + 300) )
    {
      v50 = *(_QWORD *)(v11 + 32);
      if ( !*(_QWORD *)(*(_QWORD *)(v49 + v50 + 24) + 104LL) )
        sqlite3NestedParse(a1, "CREATE TABLE %Q.sqlite_sequence(name,seq)", *(_QWORD *)(v49 + v50));
    }
    v51 = sqlite3MPrintf(v11, "tbl_name='%q' AND type!='trigger'", *v10);
    LODWORD(Vdbe) = sqlite3VdbeAddParseSchemaOp(v35, (unsigned int)v21, v51, 0);
    if ( !*(_BYTE *)(v11 + 197) )
    {
LABEL_95:
      if ( !v6 && !*((_BYTE *)v10 + 63) )
      {
        Vdbe = (const char *)a3;
        if ( *(_QWORD *)a2 )
          Vdbe = a2;
        LODWORD(Vdbe) = *(_DWORD *)Vdbe - *((_DWORD *)a1 + 66) + 13;
        *((_DWORD *)v10 + 16) = (_DWORD)Vdbe;
      }
      return (int)Vdbe;
    }
LABEL_91:
    if ( sqlite3HashInsert(v10[12] + 8, *v10, v10) )
    {
      LODWORD(Vdbe) = sqlite3OomFault(v11);
      return (int)Vdbe;
    }
    a1[43] = 0;
    *(_DWORD *)(v11 + 44) |= 1u;
    LODWORD(Vdbe) = strcmp_0(*v10, "sqlite_sequence");
    if ( !(_DWORD)Vdbe )
    {
      Vdbe = v10[12];
      *((_QWORD *)Vdbe + 13) = v10;
    }
    goto LABEL_95;
  }
  LODWORD(Vdbe) = 0;
  memset(v56, 0, 37);
  if ( *((_BYTE *)a1 + 300) )
  {
    ++*((_DWORD *)a1 + 12);
    *((_DWORD *)a1 + 6) = 1;
    return (int)Vdbe;
  }
  v39 = *((_DWORD *)a1 + 14) + 1;
  v40 = a1;
  v53 = *((_DWORD *)a1 + 14) + 2;
  *((_DWORD *)a1 + 14) += 3;
  v59 = v39 + 2;
  if ( a1[21] )
    v40 = (_QWORD *)a1[21];
  *((_BYTE *)v40 + 33) = 1;
  sqlite3VdbeAddOp3((_DWORD)v35, 113, 1, *((_DWORD *)a1 + 33), v21);
  v41 = *((int *)v35 + 36);
  if ( (int)v41 > 0 )
    *(_WORD *)(*((_QWORD *)v35 + 17) + 24 * v41 - 22) = 16;
  *((_DWORD *)a1 + 13) = 2;
  v54 = *((_DWORD *)v35 + 36);
  LODWORD(Vdbe) = sqlite3VdbeAddOp3((_DWORD)v35, 11, v39, 0, v54 + 1);
  if ( !*((_DWORD *)a1 + 12) )
  {
    LOBYTE(v42) = 65;
    Vdbe = (const char *)sqlite3ResultSetOfSelect(a1, v6, v42);
    if ( Vdbe )
    {
      v43 = *((_WORD *)Vdbe + 27);
      *((_WORD *)v10 + 28) = v43;
      *((_WORD *)v10 + 27) = v43;
      v10[1] = (const char *)*((_QWORD *)Vdbe + 1);
      *((_WORD *)Vdbe + 27) = 0;
      *((_QWORD *)Vdbe + 1) = 0;
      if ( *(_QWORD *)(v11 + 776) || (v44 = *((_DWORD *)Vdbe + 11) == 1, --*((_DWORD *)Vdbe + 11), v44) )
        deleteTable(v11, (__int64)Vdbe);
      *((_QWORD *)&v56[1] + 1) = 0;
      LODWORD(v56[1]) = 0;
      LOBYTE(v56[0]) = 13;
      DWORD1(v56[0]) = v39;
      *((_QWORD *)&v56[0] + 1) = 0;
      LODWORD(Vdbe) = sqlite3Select(a1, v6, v56);
      if ( !*((_DWORD *)a1 + 12) )
      {
        sqlite3VdbeEndCoroutine(v35, v39);
        sqlite3VdbeJumpHere(v35, v54);
        v45 = sqlite3VdbeAddOp3((_DWORD)v35, 12, DWORD1(v56[0]), 0, 0);
        sqlite3VdbeAddOp3((_DWORD)v35, 97, HIDWORD(v56[0]), v56[1], v53);
        sqlite3TableAffinity(v35, v10, 0);
        sqlite3VdbeAddOp3((_DWORD)v35, 127, 1, v59, 0);
        sqlite3VdbeAddOp3((_DWORD)v35, 128, 1, v53, v59);
        sqlite3VdbeAddOp3((_DWORD)v35, 9, 0, v45, 0);
        sqlite3VdbeJumpHere(v35, v45);
        sqlite3VdbeAddOp3((_DWORD)v35, 122, 1, 0, 0);
        TableStmt = createTableStmt(v11, (__int64)v10);
        goto LABEL_84;
      }
    }
  }
  return (int)Vdbe;
}

```

## disassembly

```asm
0x140055854  mov     rax, rsp
0x140055857  mov     [rax+20h], r9d
0x14005585b  mov     [rax+18h], r8
0x14005585f  mov     [rax+10h], rdx
0x140055863  push    rbp
0x140055864  push    rbx
0x140055865  push    rsi
0x140055866  push    rdi
0x140055867  push    r12
0x140055869  push    r13
0x14005586b  push    r14
0x14005586d  push    r15
0x14005586f  lea     rbp, [rax-57h]
0x140055873  sub     rsp, 98h
0x14005587a  mov     r13, [rbp+4Fh+arg_20]
0x14005587e  xor     r15d, r15d
0x140055881  mov     r10d, r9d
0x140055884  mov     rsi, rcx
0x140055887  test    r8, r8
0x14005588a  jnz     short loc_140055895
0x14005588c  test    r13, r13
0x14005588f  jz      loc_140055F81
0x140055895  mov     rdi, [rcx+158h]
0x14005589c  test    rdi, rdi
0x14005589f  jz      loc_140055F81
0x1400558a5  mov     r14, [rcx]
0x1400558a8  test    r13, r13
0x1400558ab  jnz     short loc_1400558C5
0x1400558ad  mov     rdx, [rdi]
0x1400558b0  mov     rcx, r14
0x1400558b3  call    sqlite3ShadowTableName
0x1400558b8  mov     r10d, [rbp+4Fh+arg_18]
0x1400558bc  test    eax, eax
0x1400558be  jz      short loc_1400558C5
0x1400558c0  bts     dword ptr [rdi+30h], 0Ch
0x1400558c5  cmp     [r14+0C5h], r15b
0x1400558cc  jz      short loc_1400558FC
0x1400558ce  test    r13, r13
0x1400558d1  jnz     loc_14005597F
0x1400558d7  cmp     [rdi+3Fh], r15b
0x1400558db  jz      short loc_1400558EA
0x1400558dd  cmp     [r14+0C0h], r15d
0x1400558e4  jnz     loc_14005597F
0x1400558ea  mov     eax, [r14+0C0h]
0x1400558f1  mov     [rdi+28h], eax
0x1400558f4  cmp     eax, 1
0x1400558f7  jnz     short loc_1400558FC
0x1400558f9  or      [rdi+30h], eax
0x1400558fc  mov     ecx, 10000h
0x140055901  test    ecx, r10d
0x140055904  jz      short loc_140055966
0x140055906  or      [rdi+30h], ecx
0x140055909  mov     edx, r15d
0x14005590c  cmp     r15w, [rdi+36h]
0x140055911  jge     short loc_140055966
0x140055913  movsxd  rax, edx
0x140055916  lea     rcx, [rax+rax*2]
0x14005591a  mov     rax, [rdi+8]
0x14005591e  lea     r9, [rax+rcx*8]
0x140055922  mov     ecx, [r9+8]
0x140055926  mov     eax, ecx
0x140055928  and     eax, 0F0h
0x14005592d  jz      short loc_140055993
0x14005592f  cmp     eax, 10h
0x140055932  jnz     short loc_140055939
0x140055934  mov     byte ptr [r9+0Ch], 41h ; 'A'
0x140055939  test    byte ptr [r9+12h], 1
0x14005593e  jz      short loc_14005595C
0x140055940  movsx   eax, word ptr [rdi+34h]
0x140055944  cmp     eax, edx
0x140055946  jz      short loc_14005595C
0x140055948  test    cl, 0Fh
0x14005594b  jnz     short loc_14005595C
0x14005594d  and     ecx, 0FFFFFFF2h
0x140055950  or      ecx, 2
0x140055953  mov     [r9+8], ecx
0x140055957  bts     dword ptr [rdi+30h], 0Bh
0x14005595c  movsx   eax, word ptr [rdi+36h]
0x140055960  inc     edx
0x140055962  cmp     edx, eax
0x140055964  jl      short loc_140055913
0x140055966  test    r10b, r10b
0x140055969  jns     loc_140055A0D
0x14005596f  mov     eax, [rdi+30h]
0x140055972  test    al, 8
0x140055974  jz      short loc_1400559E2
0x140055976  lea     rdx, aAutoincrementN; "AUTOINCREMENT not allowed on WITHOUT RO"...
0x14005597d  jmp     short loc_140055986
0x14005597f  lea     rdx, dword_1400ACDEC
0x140055986  mov     rcx, rsi
0x140055989  call    sqlite3ErrorMsg
0x14005598e  jmp     loc_140055F81
0x140055993  test    byte ptr [r9+12h], 4
0x140055998  jz      short loc_1400559C8
0x14005599a  lea     rdx, dword_1400ACDEC
0x1400559a1  mov     rcx, r9
0x1400559a4  call    sqlite3ColumnType
0x1400559a9  mov     r9, [r9]
0x1400559ac  lea     rdx, aUnknownDatatyp; "unknown datatype for %s.%s: \"%s\""
0x1400559b3  mov     r8, [rdi]
0x1400559b6  mov     rcx, rsi
0x1400559b9  mov     [rsp+0D0h+var_B0], rax
0x1400559be  call    sqlite3ErrorMsg
0x1400559c3  jmp     loc_140055F81
0x1400559c8  mov     r9, [r9]
0x1400559cb  lea     rdx, aMissingDatatyp; "missing datatype for %s.%s"
0x1400559d2  mov     r8, [rdi]
0x1400559d5  mov     rcx, rsi
0x1400559d8  call    sqlite3ErrorMsg
0x1400559dd  jmp     loc_140055F81
0x1400559e2  mov     rcx, rsi
0x1400559e5  test    al, 4
0x1400559e7  jnz     short loc_1400559FD
0x1400559e9  mov     r8, [rdi]
0x1400559ec  lea     rdx, aPrimaryKeyMiss; "PRIMARY KEY missing on table %s"
0x1400559f3  call    sqlite3ErrorMsg
0x1400559f8  jmp     loc_140055F81
0x1400559fd  or      eax, 280h
0x140055a02  mov     rdx, rdi
0x140055a05  mov     [rdi+30h], eax
0x140055a08  call    convertToWithoutRowidTable
0x140055a0d  mov     rcx, [rdi+60h]
0x140055a11  mov     r12d, 0FFFF8000h
0x140055a17  test    rcx, rcx
0x140055a1a  jz      short loc_140055A3A
0x140055a1c  mov     rdx, [r14+20h]
0x140055a20  mov     r12d, r15d
0x140055a23  cmp     [rdx+18h], rcx
0x140055a27  jz      short loc_140055A3A
0x140055a29  inc     r12d
0x140055a2c  movsxd  rax, r12d
0x140055a2f  shl     rax, 5
0x140055a33  cmp     [rax+rdx+18h], rcx
0x140055a38  jnz     short loc_140055A29
0x140055a3a  mov     rax, [rdi+20h]
0x140055a3e  test    rax, rax
0x140055a41  jz      short loc_140055A75
0x140055a43  xor     r9d, r9d
0x140055a46  mov     [rsp+0D0h+var_B0], rax
0x140055a4b  mov     rdx, rdi
0x140055a4e  mov     rcx, rsi
0x140055a51  lea     r8d, [r9+4]
0x140055a55  call    sqlite3ResolveSelfReference
0x140055a5a  cmp     [rsi+30h], r15d
0x140055a5e  jz      short loc_140055A75
0x140055a60  mov     rdx, [rdi+20h]
0x140055a64  test    rdx, rdx
0x140055a67  jz      short loc_140055A71
0x140055a69  mov     rcx, r14
0x140055a6c  call    exprListDeleteNN
0x140055a71  mov     [rdi+20h], r15
0x140055a75  test    byte ptr [rdi+30h], 60h
0x140055a79  jz      loc_140055B26
0x140055a7f  xor     eax, eax
0x140055a81  mov     ecx, r15d
0x140055a84  mov     dword ptr [rbp+4Fh+arg_0], ecx
0x140055a87  cmp     ax, [rdi+36h]
0x140055a8b  jge     loc_140055B13
0x140055a91  xor     r13d, r13d
0x140055a94  movsxd  rax, r15d
0x140055a97  lea     rbx, [rax+rax*2]
0x140055a9b  mov     rax, [rdi+8]
0x140055a9f  lea     rdx, [rax+rbx*8]
0x140055aa3  test    byte ptr [rdx+12h], 60h
0x140055aa7  jz      short loc_140055B1F
0x140055aa9  mov     rcx, rdi
0x140055aac  call    sqlite3ColumnExpr
0x140055ab1  mov     r9, rax
0x140055ab4  mov     [rsp+0D0h+var_B0], r13
0x140055ab9  mov     rcx, rsi
0x140055abc  mov     r8d, 8
0x140055ac2  mov     rdx, rdi
0x140055ac5  call    sqlite3ResolveSelfReference
0x140055aca  test    eax, eax
0x140055acc  jz      short loc_140055AF9
0x140055ace  mov     rax, [rdi+8]
0x140055ad2  xor     r9d, r9d
0x140055ad5  xor     r8d, r8d
0x140055ad8  mov     rcx, r14
0x140055adb  lea     edx, [r9+79h]
0x140055adf  lea     rbx, [rax+rbx*8]
0x140055ae3  call    sqlite3ExprAlloc
0x140055ae8  mov     r9, rax
0x140055aeb  mov     r8, rbx
0x140055aee  mov     rdx, rdi
0x140055af1  mov     rcx, rsi
0x140055af4  call    sqlite3ColumnSetExpr
0x140055af9  mov     ecx, dword ptr [rbp+4Fh+arg_0]
0x140055afc  movsx   eax, word ptr [rdi+36h]
0x140055b00  inc     r15d
0x140055b03  cmp     r15d, eax
0x140055b06  jl      short loc_140055A94
0x140055b08  mov     r13, [rbp+4Fh+arg_20]
0x140055b0c  xor     r15d, r15d
0x140055b0f  test    ecx, ecx
0x140055b11  jnz     short loc_140055B26
0x140055b13  lea     rdx, aMustHaveAtLeas; "must have at least one non-generated co"...
0x140055b1a  jmp     loc_140055986
0x140055b1f  inc     ecx
0x140055b21  mov     dword ptr [rbp+4Fh+arg_0], ecx
0x140055b24  jmp     short loc_140055AFC
0x140055b26  mov     r8, [rdi+8]
0x140055b2a  mov     edx, r15d
0x140055b2d  movsx   ecx, word ptr [rdi+36h]
0x140055b31  jmp     short loc_140055B40
0x140055b33  movzx   eax, byte ptr [r8+0Dh]
0x140055b38  lea     r8, [r8+18h]
0x140055b3c  add     edx, eax
0x140055b3e  dec     ecx
0x140055b40  test    ecx, ecx
0x140055b42  jg      short loc_140055B33
0x140055b44  cmp     [rdi+34h], r15w
0x140055b49  lea     ecx, [rdx+1]
0x140055b4c  cmovge  ecx, edx
0x140055b4f  shl     ecx, 2
0x140055b52  call    sqlite3LogEst
0x140055b57  mov     rbx, [rdi+10h]
0x140055b5b  mov     [rdi+3Ch], ax
0x140055b5f  jmp     short loc_140055B6D
0x140055b61  mov     rcx, rbx
0x140055b64  call    estimateIndexWidth
0x140055b69  mov     rbx, [rbx+28h]
0x140055b6d  test    rbx, rbx
0x140055b70  jnz     short loc_140055B61
0x140055b72  cmp     [r14+0C5h], r15b
0x140055b79  jnz     loc_140055F10
0x140055b7f  mov     rcx, rsi
0x140055b82  call    sqlite3GetVdbe
0x140055b87  mov     r15, rax
0x140055b8a  test    rax, rax
0x140055b8d  jz      loc_140055F81
0x140055b93  xor     r9d, r9d
0x140055b96  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x140055b9a  xor     r8d, r8d
0x140055b9d  lea     edx, [rbx+7Ah]
0x140055ba0  mov     rcx, rax
0x140055ba3  call    sqlite3VdbeAddOp3
0x140055ba8  mov     cl, [rdi+3Fh]
0x140055bab  lea     rax, aView; "VIEW"
0x140055bb2  test    cl, cl
0x140055bb4  lea     r8, aTable_0; "TABLE"
0x140055bbb  lea     rdx, aView_0; "view"
0x140055bc2  cmovnz  r8, rax
0x140055bc6  lea     rax, aTable; "table"
0x140055bcd  cmovnz  rax, rdx
0x140055bd1  mov     [rbp+4Fh+var_70], rax
0x140055bd5  test    r13, r13
0x140055bd8  jz      loc_140055E00
0x140055bde  xor     eax, eax
0x140055be0  xorps   xmm0, xmm0
0x140055be3  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x140055be7  mov     qword ptr [rbp+4Fh+var_58+0Dh], rax
0x140055beb  movups  [rbp+4Fh+var_68], xmm0
0x140055bef  cmp     [rsi+12Ch], bl
0x140055bf5  jz      short loc_140055C06
0x140055bf7  inc     dword ptr [rsi+30h]
0x140055bfa  mov     dword ptr [rsi+18h], 1
0x140055c01  jmp     loc_140055F81
0x140055c06  mov     ebx, [rsi+38h]
0x140055c09  mov     edx, 71h ; 'q'
0x140055c0e  inc     ebx
0x140055c10  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x140055c15  mov     rcx, rsi
0x140055c18  lea     r8d, [rdx-70h]
0x140055c1c  lea     eax, [rbx+1]
0x140055c1f  mov     [rbp+4Fh+var_80], eax
0x140055c22  inc     eax
0x140055c24  mov     [rsi+38h], eax
0x140055c27  mov     dword ptr [rbp+4Fh+arg_0], eax
0x140055c2a  mov     rax, [rsi+0A8h]
0x140055c31  test    rax, rax
0x140055c34  cmovnz  rcx, rax
0x140055c38  mov     byte ptr [rcx+21h], 1
0x140055c3c  mov     rcx, r15
0x140055c3f  mov     r9d, [rsi+84h]
0x140055c46  call    sqlite3VdbeAddOp3
0x140055c4b  movsxd  rax, dword ptr [r15+90h]
0x140055c52  test    eax, eax
0x140055c54  jle     short loc_140055C68
0x140055c56  lea     rcx, [rax+rax*2]
0x140055c5a  mov     rax, [r15+88h]
0x140055c61  mov     word ptr [rax+rcx*8-16h], 10h
0x140055c68  xor     r9d, r9d
0x140055c6b  mov     dword ptr [rsi+34h], 2
0x140055c72  mov     eax, [r15+90h]
0x140055c79  mov     r8d, ebx
0x140055c7c  mov     [rbp+4Fh+var_7C], eax
0x140055c7f  mov     rcx, r15
0x140055c82  inc     eax
0x140055c84  lea     edx, [r9+0Bh]
0x140055c88  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140055c8c  call    sqlite3VdbeAddOp3
0x140055c91  cmp     dword ptr [rsi+30h], 0
0x140055c95  jnz     loc_140055F81
0x140055c9b  mov     r8b, 41h ; 'A'
0x140055c9e  mov     rdx, r13
0x140055ca1  mov     rcx, rsi
0x140055ca4  call    sqlite3ResultSetOfSelect
0x140055ca9  xor     r8d, r8d
0x140055cac  mov     rdx, rax
  ... truncated ...
```

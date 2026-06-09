# sqlite3EndTable

- ea: `0x18010a820`
- end: `0x18010b1ea`
- name: `sqlite3EndTable`
- size: `2506`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `installer_update`

## callers

- `0x180108540`
- `0x180174050`

## callees

- `0x1800c8ad0`
- `0x1800c9bf0`
- `0x1800ca830`
- `0x1800cb160`
- `0x1800cf1f0`
- `0x1800d8770`
- `0x180102ee0`
- `0x1801057d0`
- `0x180108840`
- `0x1801089d0`
- `0x180108a90`
- `0x18010a820`
- `0x18010b290`
- `0x180119dd0`
- `0x18011dbb0`
- `0x18011ddf0`
- `0x18011ec20`
- `0x18011ef50`
- `0x18012a4e0`
- `0x18012a5e0`
- `0x18012c390`
- `0x180130a60`
- `0x180132d10`
- `0x180137a10`
- `0x180137a80`
- `0x180137af0`
- `0x180137d70`
- `0x180138140`
- `0x1801387b0`
- `0x180141d60`
- `0x180142480`
- `0x18015dbf0`
- `0x180242d80`
- `0x180242e40`

## string_xrefs

- `0x18010af74`: `CREATE %s %.*s`
- `0x18010af8b`: `UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d`
- `0x18010b010`: `CREATE TABLE %Q.sqlite_sequence(name,seq)`

## pseudocode

```c
void __fastcall sqlite3EndTable(__int64 *a1, __int64 *a2, unsigned __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rbp
  int v6; // r10d
  __int64 v7; // r12
  _DWORD *v8; // r13
  const char **v10; // rbx
  int v11; // eax
  __int64 v12; // r14
  const char *v13; // rdx
  int v14; // ecx
  int v15; // eax
  int v16; // eax
  const char *v17; // rdi
  size_t v18; // rax
  const char *v19; // rcx
  int v20; // r15d
  const char **v21; // rax
  int v22; // r12d
  int v23; // edi
  const char *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r9
  const char *v27; // r9
  __int64 v28; // r9
  int v29; // r10d
  int v30; // r8d
  const char *v31; // rcx
  int v32; // r9d
  int v33; // r11d
  __int64 v34; // rdx
  int v35; // eax
  __int16 v36; // ax
  const char *v37; // rdi
  __int64 v38; // r14
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  const char *v42; // r8
  const char *v43; // r13
  unsigned int v44; // r12d
  __int64 *v45; // rcx
  unsigned int v46; // edi
  __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // rax
  __int16 v50; // cx
  bool v51; // zf
  unsigned int v52; // edi
  __int64 TableStmt; // rax
  _DWORD *v54; // rcx
  int v55; // r9d
  __int64 v56; // r12
  __int64 v57; // rdi
  __int64 v58; // r8
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rdi
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  unsigned int v69; // [rsp+50h] [rbp-88h]
  unsigned int v70; // [rsp+54h] [rbp-84h]
  char v71[4]; // [rsp+60h] [rbp-78h] BYREF
  unsigned int v72; // [rsp+64h] [rbp-74h]
  __int64 v73; // [rsp+68h] [rbp-70h]
  int v74; // [rsp+70h] [rbp-68h]
  __int64 v75; // [rsp+78h] [rbp-60h]
  int v76; // [rsp+E0h] [rbp+8h]
  unsigned int v77; // [rsp+E0h] [rbp+8h]
  _DWORD *v79; // [rsp+F0h] [rbp+18h]
  int v80; // [rsp+F8h] [rbp+20h]

  v80 = a4;
  v79 = (_DWORD *)a3;
  v5 = *a1;
  v6 = a4;
  v7 = a5;
  v8 = (_DWORD *)a3;
  if ( !a3 && !a5 )
    return;
  v10 = (const char **)a1[43];
  if ( !v10 )
    return;
  if ( !a5 )
  {
    v11 = sqlite3ShadowTableName(v5, *v10);
    v6 = v80;
    if ( v11 )
      *((_DWORD *)v10 + 12) |= 0x1000u;
  }
  if ( *(_BYTE *)(v5 + 197) )
  {
    if ( a5 )
      goto LABEL_28;
    if ( *((_BYTE *)v10 + 63) )
    {
      if ( !*(_DWORD *)(v5 + 192) )
      {
        *((_DWORD *)v10 + 10) = *(_DWORD *)(v5 + 192);
        goto LABEL_12;
      }
LABEL_28:
      sqlite3ErrorMsg(a1, (const char *)&byte_1802990D8);
      return;
    }
    v16 = *(_DWORD *)(v5 + 192);
    *((_DWORD *)v10 + 10) = v16;
    if ( v16 == 1 )
      *((_DWORD *)v10 + 12) |= 1u;
  }
LABEL_12:
  v12 = 0;
  if ( (v6 & 0x10000) != 0 )
  {
    *((_DWORD *)v10 + 12) |= 0x10000u;
    a3 = 0;
    if ( *((__int16 *)v10 + 27) > 0 )
    {
      a4 = 0;
      while ( 1 )
      {
        v13 = &v10[1][a4];
        v14 = *((_DWORD *)v13 + 2);
        if ( (v14 & 0xF0) == 0 )
          break;
        if ( (*((_DWORD *)v13 + 2) & 0xF0) == 0x10 )
          *((_BYTE *)v13 + 12) = 65;
        if ( (v13[18] & 1) != 0 && *((__int16 *)v10 + 26) != (_DWORD)a3 && (v14 & 0xF) == 0 )
        {
          *((_DWORD *)v13 + 2) = v14 & 0xFFFFFFF0 | 2;
          *((_DWORD *)v10 + 12) |= 0x800u;
        }
        a3 = (unsigned int)(a3 + 1);
        a4 += 24;
        if ( (int)a3 >= *((__int16 *)v10 + 27) )
          goto LABEL_23;
      }
      v17 = *(const char **)v13;
      if ( (v13[18] & 4) != 0 )
      {
        v18 = strlen(*(const char **)v13);
        sqlite3ErrorMsg(a1, "unknown datatype for %s.%s: \"%s\"", *v10, v17, &v17[v18 + 1]);
      }
      else
      {
        sqlite3ErrorMsg(a1, "missing datatype for %s.%s", *v10, v17);
      }
      return;
    }
  }
LABEL_23:
  if ( (v6 & 0x80u) != 0 )
  {
    v15 = *((_DWORD *)v10 + 12);
    if ( (v15 & 8) != 0 )
    {
      sqlite3ErrorMsg(a1, "AUTOINCREMENT not allowed on WITHOUT ROWID tables", a3, a4);
      return;
    }
    if ( (v15 & 4) == 0 )
    {
      sqlite3ErrorMsg(a1, "PRIMARY KEY missing on table %s", *v10);
      return;
    }
    *((_DWORD *)v10 + 12) = v15 | 0x280;
    convertToWithoutRowidTable(a1, v10, a3, a4);
  }
  v19 = v10[12];
  v20 = -32768;
  v76 = -32768;
  if ( v19 )
  {
    v20 = 0;
    v21 = (const char **)(*(_QWORD *)(v5 + 32) + 24LL);
    v76 = 0;
    if ( *v21 != v19 )
    {
      do
      {
        ++v20;
        v21 += 4;
      }
      while ( *v21 != v19 );
      v76 = v20;
    }
  }
  if ( v10[4] )
  {
    sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v10, 4, 0, (__int64)v10[4]);
    if ( *((_DWORD *)a1 + 12) )
    {
      if ( v10[4] )
        exprListDeleteNN(v5);
      v10[4] = 0;
    }
  }
  if ( ((_BYTE)v10[6] & 0x60) != 0 )
  {
    v22 = 0;
    v23 = 0;
    if ( *((__int16 *)v10 + 27) <= 0 )
      goto LABEL_63;
    do
    {
      v24 = v10[1];
      if ( (v24[v12 + 18] & 0x60) != 0 )
      {
        v25 = *(unsigned __int16 *)&v24[v12 + 16];
        if ( (_WORD)v25 )
        {
          if ( *((_BYTE *)v10 + 63) )
          {
            LODWORD(v26) = 0;
          }
          else
          {
            v27 = v10[10];
            if ( v27 )
            {
              if ( *(_DWORD *)v27 >= (int)v25 )
                v26 = *(_QWORD *)&v27[32 * v25 - 24];
              else
                LODWORD(v26) = 0;
            }
            else
            {
              LODWORD(v26) = 0;
            }
          }
        }
        else
        {
          LODWORD(v26) = 0;
        }
        if ( (unsigned int)sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v10, 8, v26, 0) )
        {
          v28 = sqlite3DbMallocRawNN(v5, 72);
          if ( v28 )
          {
            *(_OWORD *)v28 = 0;
            *(_OWORD *)(v28 + 16) = 0;
            *(_OWORD *)(v28 + 32) = 0;
            *(_OWORD *)(v28 + 48) = 0;
            *(_QWORD *)(v28 + 64) = 0;
            *(_BYTE *)v28 = 121;
            *(_WORD *)(v28 + 50) = -1;
            *(_DWORD *)(v28 + 40) = 1;
          }
          sqlite3ColumnSetExpr(a1, v10, &v10[1][24 * v23], v28);
        }
      }
      else
      {
        ++v22;
      }
      ++v23;
      v12 += 24;
    }
    while ( v23 < *((__int16 *)v10 + 27) );
    v20 = v76;
    v8 = v79;
    if ( !v22 )
    {
LABEL_63:
      sqlite3ErrorMsg(a1, "must have at least one non-generated column", a3, a4);
      return;
    }
    v7 = a5;
  }
  v29 = *((__int16 *)v10 + 27);
  v30 = 0;
  v31 = v10[1];
  v32 = 0;
  v33 = 0;
  if ( v29 >= 2 )
  {
    v34 = ((unsigned int)(v29 - 2) >> 1) + 1;
    v29 -= 2 * v34;
    do
    {
      v30 += *((unsigned __int8 *)v31 + 13);
      v32 += *((unsigned __int8 *)v31 + 37);
      v31 += 48;
      --v34;
    }
    while ( v34 );
  }
  if ( v29 > 0 )
    v33 = *((unsigned __int8 *)v31 + 13);
  v35 = v33 + v32 + v30 + 1;
  if ( *((__int16 *)v10 + 26) >= 0 )
    v35 = v33 + v32 + v30;
  v36 = sqlite3LogEst((unsigned int)(4 * v35));
  v37 = v10[2];
  for ( *((_WORD *)v10 + 30) = v36; v37; v37 = (const char *)*((_QWORD *)v37 + 5) )
    estimateIndexWidth(v37);
  if ( *(_BYTE *)(v5 + 197) )
    goto LABEL_124;
  v38 = a1[2];
  if ( !v38 )
  {
    if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v38 = sqlite3VdbeCreate(a1);
    if ( !v38 )
      return;
  }
  v39 = *(int *)(v38 + 144);
  if ( *(_DWORD *)(v38 + 148) > (int)v39 )
  {
    *(_DWORD *)(v38 + 144) = v39 + 1;
    v40 = 3 * v39;
    v41 = *(_QWORD *)(v38 + 136);
    *(_QWORD *)(v41 + 8 * v40) = 122;
    *(_QWORD *)(v41 + 8 * v40 + 8) = 0;
    *(_QWORD *)(v41 + 8 * v40 + 16) = 0;
  }
  else
  {
    growOp3(v38, 122, 0, 0, 0);
  }
  v42 = "TABLE";
  v43 = "table";
  if ( *((_BYTE *)v10 + 63) )
  {
    v42 = "VIEW";
    v43 = "view";
  }
  if ( !v7 )
  {
    v54 = a1 + 35;
    if ( !v80 )
      v54 = v79;
    v55 = *v54 - *((_DWORD *)a1 + 66);
    if ( **(_BYTE **)v54 != 59 )
      v55 += v54[2];
    TableStmt = sqlite3MPrintf(v5, "CREATE %s %.*s", v42, v55, (const char *)a1[33]);
LABEL_104:
    v56 = TableStmt;
    v57 = 32LL * v20;
    sqlite3NestedParse(
      a1,
      "UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d",
      *(_QWORD *)(*(_QWORD *)(v5 + 32) + v57),
      v43,
      *v10,
      *v10,
      *((_DWORD *)a1 + 35),
      TableStmt,
      *((_DWORD *)a1 + 34));
    if ( v56 )
      sqlite3DbFreeNN(v5);
    sqlite3ChangeCookie(a1, (unsigned int)v20);
    if ( ((_BYTE)v10[6] & 8) != 0 && !*((_BYTE *)a1 + 300) )
    {
      v58 = *(_QWORD *)(v5 + 32);
      if ( !*(_QWORD *)(*(_QWORD *)(v58 + v57 + 24) + 104LL) )
        sqlite3NestedParse(a1, "CREATE TABLE %Q.sqlite_sequence(name,seq)", *(_QWORD *)(v58 + 32LL * v20));
    }
    v59 = sqlite3MPrintf(v5, "tbl_name='%q' AND type!='trigger'", *v10);
    sqlite3VdbeAddParseSchemaOp(v38, (unsigned int)v20, v59, 0);
    if ( ((_BYTE)v10[6] & 0x60) != 0 )
    {
      v60 = sqlite3MPrintf(v5, "SELECT*FROM\"%w\".\"%w\"", *(_QWORD *)(*(_QWORD *)(v5 + 32) + 32LL * v20), *v10);
      v61 = *(int *)(v38 + 144);
      v62 = v60;
      if ( *(_DWORD *)(v38 + 148) > (int)v61 )
      {
        v63 = 3 * v61;
        *(_DWORD *)(v38 + 144) = v61 + 1;
        v64 = *(_QWORD *)(v38 + 136);
        *(_DWORD *)(v64 + 8 * v63) = 148;
        *(_QWORD *)(v64 + 8 * v63 + 4) = 1;
        *(_DWORD *)(v64 + 8 * v63 + 12) = 0;
        *(_QWORD *)(v64 + 8 * v63 + 16) = 0;
      }
      else
      {
        LODWORD(v61) = growOp3(v38, 148, 1, 0, 0);
      }
      if ( *(_BYTE *)(*(_QWORD *)v38 + 103LL) )
      {
        if ( v62 )
          sqlite3DbNNFreeNN(*(_QWORD *)v38, v62);
      }
      else
      {
        if ( (int)v61 < 0 )
        {
          _mm_lfence();
          LODWORD(v61) = *(_DWORD *)(v38 + 144) - 1;
        }
        v65 = 3LL * (int)v61;
        v66 = *(_QWORD *)(v38 + 136);
        v67 = v66 + 8 * v65;
        if ( *(_BYTE *)(v67 + 1) )
        {
          vdbeChangeP4Full(v38, v66 + 8 * v65, v62, 4294967290LL);
        }
        else if ( v62 )
        {
          *(_QWORD *)(v67 + 16) = v62;
          *(_BYTE *)(v67 + 1) = -6;
        }
      }
    }
    v8 = v79;
    if ( !*(_BYTE *)(v5 + 197) )
    {
LABEL_128:
      if ( !a5 && !*((_BYTE *)v10 + 63) )
      {
        v68 = *a2;
        if ( !*a2 )
          LODWORD(v68) = *v8;
        *((_DWORD *)v10 + 16) = v68 - *((_DWORD *)a1 + 66) + 13;
      }
      return;
    }
LABEL_124:
    if ( sqlite3HashInsert(v10[12] + 8, *v10, v10) )
    {
      sqlite3OomFault(v5);
      return;
    }
    a1[43] = 0;
    *(_DWORD *)(v5 + 44) |= 1u;
    if ( !strcmp(*v10, "sqlite_sequence") )
      *((_QWORD *)v10[12] + 13) = v10;
    goto LABEL_128;
  }
  if ( *((_BYTE *)a1 + 300) )
  {
    ++*((_DWORD *)a1 + 12);
    *((_DWORD *)a1 + 6) = 1;
    return;
  }
  v44 = *((_DWORD *)a1 + 13);
  v45 = a1;
  v46 = *((_DWORD *)a1 + 14) + 1;
  *((_DWORD *)a1 + 13) = v44 + 1;
  v69 = v46 + 1;
  *((_DWORD *)a1 + 14) = v46 + 2;
  v77 = v46 + 2;
  if ( a1[21] )
    v45 = (__int64 *)a1[21];
  *((_BYTE *)v45 + 33) = 1;
  sqlite3VdbeAddOp3(v38, 113, v44, *((_DWORD *)a1 + 35), v20);
  v47 = *(int *)(v38 + 144);
  if ( (int)v47 > 0 )
    *(_WORD *)(*(_QWORD *)(v38 + 136) + 24 * v47 - 22) = 16;
  v70 = *(_DWORD *)(v38 + 144);
  sqlite3VdbeAddOp3(v38, 11, v46, 0, v70 + 1);
  if ( !*((_DWORD *)a1 + 12) )
  {
    LOBYTE(v48) = 65;
    v49 = sqlite3ResultSetOfSelect(a1, a5, v48);
    if ( v49 )
    {
      v50 = *(_WORD *)(v49 + 54);
      *((_WORD *)v10 + 28) = v50;
      *((_WORD *)v10 + 27) = v50;
      v10[1] = *(const char **)(v49 + 8);
      *(_WORD *)(v49 + 54) = 0;
      *(_QWORD *)(v49 + 8) = 0;
      if ( *(_QWORD *)(v5 + 760) || (v51 = *(_DWORD *)(v49 + 44) == 1, --*(_DWORD *)(v49 + 44), v51) )
        deleteTable(v5, v49);
      v75 = 0;
      v74 = 0;
      v71[0] = 13;
      v72 = v46;
      v73 = 0;
      sqlite3Select(a1, a5, v71);
      if ( !*((_DWORD *)a1 + 12) )
      {
        sqlite3VdbeEndCoroutine(v38, v46);
        sqlite3VdbeJumpHere(v38, v70);
        v52 = sqlite3VdbeAddOp1(v38, 12, v72);
        sqlite3VdbeAddOp3(v38, 97, HIDWORD(v73), v74, v69);
        sqlite3TableAffinity(v38, v10, 0);
        sqlite3VdbeAddOp2(v38, 127, v44, v77);
        sqlite3VdbeAddOp3(v38, 128, v44, v69, v77);
        sqlite3VdbeGoto(v38, v52);
        sqlite3VdbeJumpHere(v38, v52);
        sqlite3VdbeAddOp1(v38, 122, v44);
        TableStmt = createTableStmt(v5, v10);
        goto LABEL_104;
      }
    }
  }
}

```

## disassembly

```asm
0x18010a820  mov     [rsp+arg_18], r9d
0x18010a825  mov     [rsp+arg_10], r8
0x18010a82a  mov     [rsp+arg_8], rdx
0x18010a82f  push    rbp
0x18010a830  push    rsi
0x18010a831  push    r12
0x18010a833  push    r13
0x18010a835  sub     rsp, 0B8h
0x18010a83c  mov     rbp, [rcx]
0x18010a83f  mov     r10d, r9d
0x18010a842  mov     r12, [rsp+0D8h+arg_20]
0x18010a84a  mov     r13, r8
0x18010a84d  mov     rsi, rcx
0x18010a850  test    r8, r8
0x18010a853  jnz     short loc_18010A85E
0x18010a855  test    r12, r12
0x18010a858  jz      loc_18010B1DC
0x18010a85e  mov     [rsp+0D8h+var_28], rbx
0x18010a866  mov     rbx, [rcx+158h]
0x18010a86d  test    rbx, rbx
0x18010a870  jz      loc_18010B1D4
0x18010a876  test    r12, r12
0x18010a879  jnz     short loc_18010A899
0x18010a87b  mov     rdx, [rbx]
0x18010a87e  mov     rcx, rbp
0x18010a881  call    sqlite3ShadowTableName
0x18010a886  mov     r10d, [rsp+0D8h+arg_18]
0x18010a88e  test    eax, eax
0x18010a890  jz      short loc_18010A899
0x18010a892  or      dword ptr [rbx+30h], 1000h
0x18010a899  cmp     byte ptr [rbp+0C5h], 0
0x18010a8a0  jz      short loc_18010A8CB
0x18010a8a2  test    r12, r12
0x18010a8a5  jnz     loc_18010A996
0x18010a8ab  cmp     [rbx+3Fh], r12b
0x18010a8af  jz      loc_18010A97C
0x18010a8b5  cmp     [rbp+0C0h], r12d
0x18010a8bc  jnz     loc_18010A996
0x18010a8c2  mov     eax, [rbp+0C0h]
0x18010a8c8  mov     [rbx+28h], eax
0x18010a8cb  mov     [rsp+0D8h+var_30], rdi
0x18010a8d3  mov     [rsp+0D8h+var_38], r14
0x18010a8db  xor     r14d, r14d
0x18010a8de  bt      r10d, 10h
0x18010a8e3  jnb     short loc_18010A954
0x18010a8e5  or      dword ptr [rbx+30h], 10000h
0x18010a8ec  mov     r8d, r14d
0x18010a8ef  cmp     r14w, [rbx+36h]
0x18010a8f4  jge     short loc_18010A954
0x18010a8f6  mov     r9d, r14d
0x18010a8f9  nop     dword ptr [rax+00000000h]
0x18010a900  mov     rdx, [rbx+8]
0x18010a904  add     rdx, r9
0x18010a907  mov     ecx, [rdx+8]
0x18010a90a  mov     eax, ecx
0x18010a90c  and     eax, 0F0h
0x18010a911  jz      loc_18010A9AA
0x18010a917  cmp     eax, 10h
0x18010a91a  jnz     short loc_18010A920
0x18010a91c  mov     byte ptr [rdx+0Ch], 41h ; 'A'
0x18010a920  test    byte ptr [rdx+12h], 1
0x18010a924  jz      short loc_18010A944
0x18010a926  movsx   eax, word ptr [rbx+34h]
0x18010a92a  cmp     eax, r8d
0x18010a92d  jz      short loc_18010A944
0x18010a92f  test    cl, 0Fh
0x18010a932  jnz     short loc_18010A944
0x18010a934  and     ecx, 0FFFFFFF2h
0x18010a937  or      ecx, 2
0x18010a93a  mov     [rdx+8], ecx
0x18010a93d  or      dword ptr [rbx+30h], 800h
0x18010a944  movsx   eax, word ptr [rbx+36h]
0x18010a948  inc     r8d
0x18010a94b  add     r9, 18h
0x18010a94f  cmp     r8d, eax
0x18010a952  jl      short loc_18010A900
0x18010a954  test    r10b, r10b
0x18010a957  jns     loc_18010AA23
0x18010a95d  mov     eax, [rbx+30h]
0x18010a960  mov     rcx, rsi
0x18010a963  test    al, 8
0x18010a965  jz      loc_18010A9FB
0x18010a96b  lea     rdx, aAutoincrementN; "AUTOINCREMENT not allowed on WITHOUT RO"...
0x18010a972  call    sqlite3ErrorMsg
0x18010a977  jmp     loc_18010B1C4
0x18010a97c  mov     eax, [rbp+0C0h]
0x18010a982  mov     [rbx+28h], eax
0x18010a985  cmp     eax, 1
0x18010a988  jnz     loc_18010A8CB
0x18010a98e  or      [rbx+30h], eax
0x18010a991  jmp     loc_18010A8CB
0x18010a996  lea     rdx, byte_1802990D8
0x18010a99d  mov     rcx, rsi
0x18010a9a0  call    sqlite3ErrorMsg
0x18010a9a5  jmp     loc_18010B1D4
0x18010a9aa  test    byte ptr [rdx+12h], 4
0x18010a9ae  mov     rdi, [rdx]
0x18010a9b1  jz      short loc_18010A9E1
0x18010a9b3  mov     rcx, rdi; Str
0x18010a9b6  call    strlen
0x18010a9bb  mov     r8, [rbx]
0x18010a9be  lea     rdx, aUnknownDatatyp; "unknown datatype for %s.%s: \"%s\""
0x18010a9c5  mov     r9, rdi
0x18010a9c8  lea     rcx, [rax+1]
0x18010a9cc  add     rcx, rdi
0x18010a9cf  mov     [rsp+0D8h+var_B8], rcx
0x18010a9d4  mov     rcx, rsi
0x18010a9d7  call    sqlite3ErrorMsg
0x18010a9dc  jmp     loc_18010B1C4
0x18010a9e1  mov     r8, [rbx]
0x18010a9e4  lea     rdx, aMissingDatatyp; "missing datatype for %s.%s"
0x18010a9eb  mov     r9, rdi
0x18010a9ee  mov     rcx, rsi
0x18010a9f1  call    sqlite3ErrorMsg
0x18010a9f6  jmp     loc_18010B1C4
0x18010a9fb  test    al, 4
0x18010a9fd  jnz     short loc_18010AA13
0x18010a9ff  mov     r8, [rbx]
0x18010aa02  lea     rdx, aPrimaryKeyMiss; "PRIMARY KEY missing on table %s"
0x18010aa09  call    sqlite3ErrorMsg
0x18010aa0e  jmp     loc_18010B1C4
0x18010aa13  or      eax, 280h
0x18010aa18  mov     rdx, rbx
0x18010aa1b  mov     [rbx+30h], eax
0x18010aa1e  call    convertToWithoutRowidTable
0x18010aa23  mov     rcx, [rbx+60h]
0x18010aa27  mov     [rsp+0D8h+var_40], r15
0x18010aa2f  mov     r15d, 0FFFF8000h
0x18010aa35  mov     [rsp+0D8h+arg_0], r15d
0x18010aa3d  test    rcx, rcx
0x18010aa40  jz      short loc_18010AA74
0x18010aa42  mov     rax, [rbp+20h]
0x18010aa46  mov     r15d, r14d
0x18010aa49  add     rax, 18h
0x18010aa4d  mov     [rsp+0D8h+arg_0], r14d
0x18010aa55  cmp     [rax], rcx
0x18010aa58  jz      short loc_18010AA74
0x18010aa5a  nop     word ptr [rax+rax+00h]
0x18010aa60  inc     r15d
0x18010aa63  lea     rax, [rax+20h]
0x18010aa67  cmp     [rax], rcx
0x18010aa6a  jnz     short loc_18010AA60
0x18010aa6c  mov     [rsp+0D8h+arg_0], r15d
0x18010aa74  mov     rax, [rbx+20h]
0x18010aa78  test    rax, rax
0x18010aa7b  jz      short loc_18010AAB1
0x18010aa7d  xor     r9d, r9d
0x18010aa80  mov     [rsp+0D8h+var_B8], rax
0x18010aa85  mov     r8d, 4
0x18010aa8b  mov     rdx, rbx
0x18010aa8e  mov     rcx, rsi
0x18010aa91  call    sqlite3ResolveSelfReference
0x18010aa96  cmp     [rsi+30h], r14d
0x18010aa9a  jz      short loc_18010AAB1
0x18010aa9c  mov     rdx, [rbx+20h]
0x18010aaa0  test    rdx, rdx
0x18010aaa3  jz      short loc_18010AAAD
0x18010aaa5  mov     rcx, rbp
0x18010aaa8  call    exprListDeleteNN
0x18010aaad  mov     [rbx+20h], r14
0x18010aab1  test    byte ptr [rbx+30h], 60h
0x18010aab5  jz      loc_18010ABE2
0x18010aabb  mov     r12d, r14d
0x18010aabe  mov     edi, r14d
0x18010aac1  cmp     r14w, [rbx+36h]
0x18010aac6  jge     loc_18010ABC3
0x18010aacc  xor     r13d, r13d
0x18010aacf  nop
0x18010aad0  mov     rax, [rbx+8]
0x18010aad4  test    byte ptr [rax+r14+12h], 60h
0x18010aada  jz      loc_18010AB99
0x18010aae0  movzx   ecx, word ptr [rax+r14+10h]
0x18010aae6  test    cx, cx
0x18010aae9  jnz     short loc_18010AAF0
0x18010aaeb  mov     r9, r13
0x18010aaee  jmp     short loc_18010AB1F
0x18010aaf0  cmp     [rbx+3Fh], r13b
0x18010aaf4  jz      short loc_18010AAFB
0x18010aaf6  mov     r9, r13
0x18010aaf9  jmp     short loc_18010AB1F
0x18010aafb  mov     r9, [rbx+50h]
0x18010aaff  test    r9, r9
0x18010ab02  jnz     short loc_18010AB09
0x18010ab04  mov     r9, r13
0x18010ab07  jmp     short loc_18010AB1F
0x18010ab09  mov     rax, rcx
0x18010ab0c  cmp     [r9], ecx
0x18010ab0f  jge     short loc_18010AB16
0x18010ab11  mov     r9, r13
0x18010ab14  jmp     short loc_18010AB1F
0x18010ab16  shl     rax, 5
0x18010ab1a  mov     r9, [rax+r9-18h]
0x18010ab1f  mov     r8d, 8
0x18010ab25  mov     [rsp+0D8h+var_B8], r13
0x18010ab2a  mov     rdx, rbx
0x18010ab2d  mov     rcx, rsi
0x18010ab30  call    sqlite3ResolveSelfReference
0x18010ab35  test    eax, eax
0x18010ab37  jz      short loc_18010AB9C
0x18010ab39  mov     edx, 48h ; 'H'
0x18010ab3e  mov     rcx, rbp
0x18010ab41  call    sqlite3DbMallocRawNN
0x18010ab46  mov     r9, rax
0x18010ab49  test    rax, rax
0x18010ab4c  jz      short loc_18010AB7D
0x18010ab4e  xorps   xmm0, xmm0
0x18010ab51  xor     eax, eax
0x18010ab53  movups  xmmword ptr [r9], xmm0
0x18010ab57  movups  xmmword ptr [r9+10h], xmm0
0x18010ab5c  movups  xmmword ptr [r9+20h], xmm0
0x18010ab61  movups  xmmword ptr [r9+30h], xmm0
0x18010ab66  mov     [r9+40h], rax
0x18010ab6a  mov     byte ptr [r9], 79h ; 'y'
0x18010ab6e  mov     word ptr [r9+32h], 0FFFFh
0x18010ab75  mov     dword ptr [r9+28h], 1
0x18010ab7d  movsxd  rax, edi
0x18010ab80  mov     rdx, rbx
0x18010ab83  lea     rcx, [rax+rax*2]
0x18010ab87  mov     rax, [rbx+8]
0x18010ab8b  lea     r8, [rax+rcx*8]
0x18010ab8f  mov     rcx, rsi
0x18010ab92  call    sqlite3ColumnSetExpr
0x18010ab97  jmp     short loc_18010AB9C
0x18010ab99  inc     r12d
0x18010ab9c  movsx   eax, word ptr [rbx+36h]
0x18010aba0  inc     edi
0x18010aba2  add     r14, 18h
0x18010aba6  cmp     edi, eax
0x18010aba8  jl      loc_18010AAD0
0x18010abae  mov     r15d, [rsp+0D8h+arg_0]
0x18010abb6  mov     r13, [rsp+0D8h+arg_10]
0x18010abbe  test    r12d, r12d
0x18010abc1  jnz     short loc_18010ABD7
0x18010abc3  lea     rdx, aMustHaveAtLeas; "must have at least one non-generated co"...
0x18010abca  mov     rcx, rsi
0x18010abcd  call    sqlite3ErrorMsg
0x18010abd2  jmp     loc_18010B1BC
0x18010abd7  mov     r12, [rsp+0D8h+arg_20]
0x18010abdf  xor     r14d, r14d
0x18010abe2  movsx   r10d, word ptr [rbx+36h]
0x18010abe7  mov     r8d, r14d
0x18010abea  mov     rcx, [rbx+8]
0x18010abee  mov     r9d, r14d
0x18010abf1  mov     r11d, r14d
0x18010abf4  cmp     r10d, 2
0x18010abf8  jl      short loc_18010AC28
0x18010abfa  lea     eax, [r10-2]
0x18010abfe  shr     eax, 1
0x18010ac00  inc     eax
0x18010ac02  mov     edx, eax
0x18010ac04  neg     eax
0x18010ac06  lea     r10d, [r10+rax*2]
0x18010ac0a  nop     word ptr [rax+rax+00h]
0x18010ac10  movzx   eax, byte ptr [rcx+0Dh]
0x18010ac14  add     r8d, eax
0x18010ac17  movzx   eax, byte ptr [rcx+25h]
0x18010ac1b  add     r9d, eax
0x18010ac1e  add     rcx, 30h ; '0'
0x18010ac22  sub     rdx, 1
0x18010ac26  jnz     short loc_18010AC10
0x18010ac28  test    r10d, r10d
0x18010ac2b  jle     short loc_18010AC32
0x18010ac2d  movzx   r11d, byte ptr [rcx+0Dh]
0x18010ac32  lea     ecx, [r9+r8]
0x18010ac36  add     ecx, r11d
0x18010ac39  cmp     word ptr [rbx+34h], 0
0x18010ac3e  lea     eax, [rcx+1]
0x18010ac41  cmovge  eax, ecx
0x18010ac44  shl     eax, 2
0x18010ac47  mov     ecx, eax
0x18010ac49  call    sqlite3LogEst
0x18010ac4e  mov     rdi, [rbx+10h]
0x18010ac52  mov     [rbx+3Ch], ax
0x18010ac56  test    rdi, rdi
0x18010ac59  jz      short loc_18010AC71
0x18010ac5b  nop     dword ptr [rax+rax+00h]
0x18010ac60  mov     rcx, rdi
0x18010ac63  call    estimateIndexWidth
0x18010ac68  mov     rdi, [rdi+28h]
0x18010ac6c  test    rdi, rdi
0x18010ac6f  jnz     short loc_18010AC60
0x18010ac71  cmp     byte ptr [rbp+0C5h], 0
0x18010ac78  jnz     loc_18010B143
0x18010ac7e  mov     r14, [rsi+10h]
0x18010ac82  test    r14, r14
0x18010ac85  jnz     short loc_18010ACB1
0x18010ac87  cmp     [rsi+0A8h], r14
0x18010ac8e  jnz     short loc_18010AC9D
0x18010ac90  mov     rax, [rsi]
0x18010ac93  test    byte ptr [rax+60h], 8
0x18010ac97  jnz     short loc_18010AC9D
0x18010ac99  mov     byte ptr [rsi+23h], 1
0x18010ac9d  mov     rcx, rsi
0x18010aca0  call    sqlite3VdbeCreate
0x18010aca5  mov     r14, rax
0x18010aca8  test    rax, rax
0x18010acab  jz      loc_18010B1BC
0x18010acb1  movsxd  rcx, dword ptr [r14+90h]
0x18010acb8  xor     edx, edx
0x18010acba  cmp     [r14+94h], ecx
  ... truncated ...
```

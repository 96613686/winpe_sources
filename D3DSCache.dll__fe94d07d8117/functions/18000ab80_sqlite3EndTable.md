# sqlite3EndTable

- ea: `0x18000ab80`
- end: `0x18000b4b5`
- name: `sqlite3EndTable`
- size: `2357`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x18001bc30`
- `0x18007d68c`

## callees

- `0x180008860`
- `0x18000ab80`
- `0x18000b4bc`
- `0x18000b544`
- `0x18000b5a8`
- `0x180014464`
- `0x180016b18`
- `0x180036970`
- `0x180036d74`
- `0x180037880`
- `0x180039494`
- `0x1800399d0`
- `0x18003b5b4`
- `0x18003b8bc`
- `0x18003b9c8`
- `0x18003be78`
- `0x18003bf64`
- `0x18003c8d4`
- `0x18003cc7c`
- `0x180041574`
- `0x180042488`
- `0x180042cd4`
- `0x18005aed4`
- `0x18005bb30`
- `0x18007c408`
- `0x18007c52c`
- `0x18007c5b8`
- `0x180089bdc`
- `0x180089ccc`
- `0x1800a6cb4`

## string_xrefs

- `0x18000b285`: `UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d`
- `0x18000b23d`: `CREATE %s %.*s`
- `0x18000b318`: `CREATE TABLE %Q.sqlite_sequence(name,seq)`

## pseudocode

```c
void __fastcall sqlite3EndTable(__int64 *a1, __int64 *a2, _DWORD *a3, int a4, __int64 a5)
{
  __int64 *v7; // r14
  const char **v9; // rbx
  __int64 v10; // rbp
  int i; // edx
  __int64 v12; // r9
  int v13; // ecx
  int v14; // eax
  const char *v15; // rax
  const char **v16; // r9
  int v17; // eax
  const char *v18; // rcx
  __int64 v19; // r8
  int v20; // edx
  const char *v21; // rdx
  int v22; // edx
  int v23; // r14d
  __int64 v24; // rdi
  int v25; // eax
  const char *v26; // rdi
  __int64 v27; // rax
  int v28; // edx
  int v29; // ecx
  const char *j; // r8
  int v31; // eax
  int v32; // eax
  __int16 v33; // ax
  const char *v34; // rdi
  __int64 v35; // r14
  char v36; // al
  const char *v37; // r8
  const char *v38; // rcx
  __int64 *v39; // rcx
  int v40; // r8d
  int v41; // r15d
  int v42; // edi
  int v43; // ecx
  __int64 v44; // r8
  __int64 v45; // rax
  __int16 v46; // cx
  unsigned int v47; // edi
  __int64 TableStmt; // rax
  _DWORD *v49; // rcx
  int v50; // r9d
  __int64 v51; // rdi
  __int64 v52; // r8
  __int64 v53; // rdi
  unsigned int v54; // eax
  __int64 v55; // rax
  __int64 k; // rdx
  int v57; // edx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  int v61; // [rsp+50h] [rbp-78h]
  int v62; // [rsp+54h] [rbp-74h]
  const char *v63; // [rsp+58h] [rbp-70h]
  _OWORD v64[3]; // [rsp+60h] [rbp-68h] BYREF
  int v65; // [rsp+D0h] [rbp+8h]
  unsigned int v66; // [rsp+D0h] [rbp+8h]
  __int64 v67; // [rsp+D0h] [rbp+8h]
  int v69; // [rsp+E0h] [rbp+18h]
  int v70; // [rsp+E0h] [rbp+18h]
  __int64 v71; // [rsp+E0h] [rbp+18h]

  v7 = a2;
  if ( !a3 && !a5 )
    return;
  v9 = (const char **)a1[44];
  if ( !v9 )
    return;
  v10 = *a1;
  if ( !a5 && (unsigned int)sqlite3ShadowTableName(*a1, *v9) )
    *((_DWORD *)v9 + 12) |= 0x1000u;
  if ( *(_BYTE *)(v10 + 197) )
  {
    if ( a5 )
      goto LABEL_25;
    if ( *((_BYTE *)v9 + 63) )
    {
      if ( !*(_DWORD *)(v10 + 192) )
      {
        *((_DWORD *)v9 + 10) = *(_DWORD *)(v10 + 192);
        goto LABEL_12;
      }
LABEL_25:
      sqlite3ErrorMsg(a1, (const char *)&Src);
      return;
    }
    v14 = *(_DWORD *)(v10 + 192);
    *((_DWORD *)v9 + 10) = v14;
    if ( v14 == 1 )
      *((_DWORD *)v9 + 12) |= 1u;
  }
LABEL_12:
  if ( (a4 & 0x10000) != 0 )
  {
    *((_DWORD *)v9 + 12) |= 0x10000u;
    for ( i = 0; i < *((__int16 *)v9 + 27); ++i )
    {
      v12 = (__int64)&v9[1][24 * i];
      v13 = *(_DWORD *)(v12 + 8);
      if ( (v13 & 0xF0) == 0 )
      {
        if ( (*(_BYTE *)(v12 + 18) & 4) != 0 )
        {
          v15 = (const char *)sqlite3ColumnType(v12, &Src);
          sqlite3ErrorMsg(a1, "unknown datatype for %s.%s: \"%s\"", *v9, *v16, v15);
        }
        else
        {
          sqlite3ErrorMsg(a1, "missing datatype for %s.%s", *v9, *(const char **)v12);
        }
        return;
      }
      if ( (*(_DWORD *)(v12 + 8) & 0xF0) == 0x10 )
        *(_BYTE *)(v12 + 12) = 65;
      if ( (*(_BYTE *)(v12 + 18) & 1) != 0 && *((__int16 *)v9 + 26) != i && (v13 & 0xF) == 0 )
      {
        *(_DWORD *)(v12 + 8) = v13 & 0xFFFFFFF0 | 2;
        *((_DWORD *)v9 + 12) |= 0x800u;
      }
    }
  }
  if ( (a4 & 0x80u) != 0 )
  {
    v17 = *((_DWORD *)v9 + 12);
    if ( (v17 & 8) != 0 )
    {
      sqlite3ErrorMsg(a1, "AUTOINCREMENT not allowed on WITHOUT ROWID tables");
      return;
    }
    if ( (v17 & 4) == 0 )
    {
      sqlite3ErrorMsg(a1, "PRIMARY KEY missing on table %s", *v9);
      return;
    }
    *((_DWORD *)v9 + 12) = v17 | 0x280;
    convertToWithoutRowidTable(a1, v9);
  }
  v18 = v9[12];
  v65 = -32768;
  if ( v18 )
  {
    v19 = *(_QWORD *)(v10 + 32);
    v20 = 0;
    v65 = 0;
    if ( *(const char **)(v19 + 24) != v18 )
    {
      do
        ++v20;
      while ( *(const char **)(32LL * v20 + v19 + 24) != v18 );
      v65 = v20;
    }
  }
  if ( v9[4] )
  {
    sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v9, 4, 0, (__int64)v9[4]);
    if ( *((_DWORD *)a1 + 12) )
    {
      v21 = v9[4];
      if ( v21 )
        exprListDeleteNN(v10, v21);
      v9[4] = 0;
    }
  }
  if ( ((_BYTE)v9[6] & 0x60) != 0 )
  {
    v22 = 0;
    v69 = 0;
    if ( *((__int16 *)v9 + 27) <= 0 )
      goto LABEL_53;
    v23 = 0;
    do
    {
      v24 = 24LL * v23;
      if ( (v9[1][v24 + 18] & 0x60) != 0 )
      {
        v25 = sqlite3ColumnExpr(v9, &v9[1][v24]);
        if ( (unsigned int)sqlite3ResolveSelfReference((_DWORD)a1, (_DWORD)v9, 8, v25, 0) )
        {
          v26 = &v9[1][v24];
          v27 = sqlite3ExprAlloc(v10, 121, 0, 0);
          sqlite3ColumnSetExpr(a1, v9, v26, v27);
        }
        v22 = v69;
      }
      else
      {
        v69 = ++v22;
      }
      ++v23;
    }
    while ( v23 < *((__int16 *)v9 + 27) );
    v7 = a2;
    if ( !v22 )
    {
LABEL_53:
      sqlite3ErrorMsg(a1, "must have at least one non-generated column");
      return;
    }
  }
  v28 = *((__int16 *)v9 + 27);
  v29 = 0;
  for ( j = v9[1]; v28 > 0; --v28 )
  {
    v31 = *((unsigned __int8 *)j + 13);
    j += 24;
    v29 += v31;
  }
  v32 = v29 + 1;
  if ( *((__int16 *)v9 + 26) >= 0 )
    v32 = v29;
  v33 = sqlite3LogEst((unsigned int)(4 * v32));
  v34 = v9[2];
  for ( *((_WORD *)v9 + 30) = v33; v34; v34 = (const char *)*((_QWORD *)v34 + 5) )
    estimateIndexWidth(v34);
  if ( *(_BYTE *)(v10 + 197) )
    goto LABEL_101;
  v35 = a1[2];
  if ( v35 )
    goto LABEL_67;
  if ( !a1[22] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
    *((_BYTE *)a1 + 35) = 1;
  v35 = sqlite3VdbeCreate(a1);
  if ( v35 )
  {
LABEL_67:
    sqlite3VdbeAddOp3(v35, 122, 0, 0, 0);
    v36 = *((_BYTE *)v9 + 63);
    v37 = "TABLE";
    if ( v36 )
      v37 = "VIEW";
    v38 = "table";
    if ( v36 )
      v38 = "view";
    v63 = v38;
    if ( !a5 )
    {
      if ( a4 )
        v49 = a1 + 36;
      else
        v49 = a3;
      v50 = *v49 - *((_DWORD *)a1 + 68);
      if ( **(_BYTE **)v49 != 59 )
        v50 += v49[2];
      TableStmt = sqlite3MPrintf(v10, "CREATE %s %.*s", v37, v50, (const char *)a1[34]);
      v41 = v65;
LABEL_86:
      v71 = TableStmt;
      v51 = 32LL * v41;
      v67 = v51;
      sqlite3NestedParse(
        a1,
        "UPDATE %Q.sqlite_master SET type='%s', name=%Q, tbl_name=%Q, rootpage=#%d, sql=%Q WHERE rowid=#%d",
        *(_QWORD *)(*(_QWORD *)(v10 + 32) + v51),
        v63,
        *v9,
        *v9,
        *((_DWORD *)a1 + 35),
        TableStmt,
        *((_DWORD *)a1 + 34));
      if ( v71 )
        sqlite3DbFreeNN(v10, v71);
      sqlite3VdbeAddOp3(a1[2], 100, v41, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32) + v51 + 24) + 1);
      if ( ((_BYTE)v9[6] & 8) != 0 && !*((_BYTE *)a1 + 308) )
      {
        v52 = *(_QWORD *)(v10 + 32);
        if ( !*(_QWORD *)(*(_QWORD *)(v52 + v51 + 24) + 104LL) )
          sqlite3NestedParse(a1, "CREATE TABLE %Q.sqlite_sequence(name,seq)", *(_QWORD *)(v52 + 32LL * v41));
      }
      v53 = sqlite3MPrintf(v10, "tbl_name='%q' AND type!='trigger'", *v9);
      v54 = sqlite3VdbeAddOp3(v35, 149, v41, 0, 0);
      sqlite3VdbeChangeP4(v35, v54, v53);
      v55 = *(int *)(v35 + 144);
      if ( (int)v55 > 0 )
        *(_WORD *)(*(_QWORD *)(v35 + 136) + 24 * v55 - 22) = 0;
      for ( k = 0; (int)k < *(_DWORD *)(*(_QWORD *)v35 + 40LL); k = (unsigned int)(v57 + 1) )
        sqlite3VdbeUsesBtree(v35, k);
      v58 = *(_QWORD *)(v35 + 24);
      if ( *(_QWORD *)(v58 + 176) )
        v58 = *(_QWORD *)(v58 + 176);
      *(_BYTE *)(v58 + 33) = 1;
      if ( ((_BYTE)v9[6] & 0x60) != 0 )
      {
        v59 = sqlite3MPrintf(v10, "SELECT*FROM\"%w\".\"%w\"", *(_QWORD *)(*(_QWORD *)(v10 + 32) + v67), *v9);
        sqlite3VdbeAddOp4(v35, 148, 1, 0, 0, v59, -6);
      }
      v7 = a2;
      if ( !*(_BYTE *)(v10 + 197) )
      {
LABEL_105:
        if ( !a5 && !*((_BYTE *)v9 + 63) )
        {
          v60 = *v7;
          if ( !*v7 )
            LODWORD(v60) = *a3;
          *((_DWORD *)v9 + 16) = v60 - *((_DWORD *)a1 + 68) + 13;
        }
        return;
      }
LABEL_101:
      if ( sqlite3HashInsert(v9[12] + 8, *v9, v9) )
      {
        sqlite3OomFault(v10);
        return;
      }
      a1[44] = 0;
      *(_DWORD *)(v10 + 44) |= 1u;
      if ( !strcmp_0(*v9, "sqlite_sequence") )
        *((_QWORD *)v9[12] + 13) = v9;
      goto LABEL_105;
    }
    memset(v64, 0, 37);
    if ( *((_BYTE *)a1 + 308) )
    {
      ++*((_DWORD *)a1 + 12);
      *((_DWORD *)a1 + 6) = 1;
      return;
    }
    v39 = a1;
    v40 = *((_DWORD *)a1 + 13);
    v41 = v65;
    v42 = *((_DWORD *)a1 + 14) + 1;
    v70 = v40;
    *((_DWORD *)a1 + 13) = v40 + 1;
    v62 = v42 + 1;
    *((_DWORD *)a1 + 14) = v42 + 2;
    v61 = v42 + 2;
    if ( a1[22] )
      v39 = (__int64 *)a1[22];
    *((_BYTE *)v39 + 33) = 1;
    sqlite3VdbeAddOp3(v35, 113, v40, *((_DWORD *)a1 + 35), v65);
    sqlite3VdbeChangeP5(v35, 16);
    v66 = *(_DWORD *)(v35 + 144);
    sqlite3VdbeAddOp3(v43, 11, v42, 0, v66 + 1);
    if ( !*((_DWORD *)a1 + 12) )
    {
      LOBYTE(v44) = 65;
      v45 = sqlite3ResultSetOfSelect(a1, a5, v44);
      if ( v45 )
      {
        v46 = *(_WORD *)(v45 + 54);
        *((_WORD *)v9 + 28) = v46;
        *((_WORD *)v9 + 27) = v46;
        v9[1] = *(const char **)(v45 + 8);
        *(_WORD *)(v45 + 54) = 0;
        *(_QWORD *)(v45 + 8) = 0;
        sqlite3DeleteTable(v10, v45);
        LOBYTE(v64[0]) = 13;
        DWORD1(v64[0]) = v42;
        *((_QWORD *)&v64[0] + 1) = 0;
        *((_QWORD *)&v64[1] + 1) = 0;
        LODWORD(v64[1]) = 0;
        sqlite3Select(a1, a5, v64);
        if ( !*((_DWORD *)a1 + 12) )
        {
          sqlite3VdbeAddOp3(v35, 68, v42, 0, 0);
          *(_BYTE *)(*(_QWORD *)(v35 + 24) + 31LL) = 0;
          *(_DWORD *)(*(_QWORD *)(v35 + 24) + 40LL) = 0;
          *(_DWORD *)(sqlite3VdbeGetOp(v35, v66) + 8) = *(_DWORD *)(v35 + 144);
          v47 = sqlite3VdbeAddOp3(v35, 12, DWORD1(v64[0]), 0, 0);
          sqlite3VdbeAddOp3(v35, 97, HIDWORD(v64[0]), v64[1], v62);
          sqlite3TableAffinity(v35, v9, 0);
          sqlite3VdbeAddOp3(v35, 127, v70, v61, 0);
          sqlite3VdbeAddOp3(v35, 128, v70, v62, v61);
          sqlite3VdbeAddOp3(v35, 9, 0, v47, 0);
          *(_DWORD *)(sqlite3VdbeGetOp(v35, v47) + 8) = *(_DWORD *)(v35 + 144);
          sqlite3VdbeAddOp3(v35, 122, v70, 0, 0);
          TableStmt = createTableStmt(v10, v9);
          goto LABEL_86;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000ab80  mov     [rsp+arg_8], rdx
0x18000ab85  push    rsi
0x18000ab86  push    r12
0x18000ab88  push    r13
0x18000ab8a  push    r14
0x18000ab8c  push    r15
0x18000ab8e  sub     rsp, 0A0h
0x18000ab95  mov     r12, [rsp+0C8h+arg_20]
0x18000ab9d  mov     r15d, r9d
0x18000aba0  mov     r13, r8
0x18000aba3  mov     r14, rdx
0x18000aba6  mov     rsi, rcx
0x18000aba9  test    r8, r8
0x18000abac  jnz     short loc_18000ABB7
0x18000abae  test    r12, r12
0x18000abb1  jz      loc_18000B4A4
0x18000abb7  mov     [rsp+0C8h+arg_18], rbx
0x18000abbf  mov     rbx, [rcx+160h]
0x18000abc6  test    rbx, rbx
0x18000abc9  jz      loc_18000B49C
0x18000abcf  mov     [rsp+0C8h+var_30], rbp
0x18000abd7  mov     rbp, [rcx]
0x18000abda  test    r12, r12
0x18000abdd  jnz     short loc_18000ABF5
0x18000abdf  mov     rdx, [rbx]
0x18000abe2  mov     rcx, rbp
0x18000abe5  call    sqlite3ShadowTableName
0x18000abea  test    eax, eax
0x18000abec  jz      short loc_18000ABF5
0x18000abee  or      dword ptr [rbx+30h], 1000h
0x18000abf5  cmp     byte ptr [rbp+0C5h], 0
0x18000abfc  jz      short loc_18000AC27
0x18000abfe  test    r12, r12
0x18000ac01  jnz     loc_18000ACAC
0x18000ac07  cmp     [rbx+3Fh], r12b
0x18000ac0b  jz      loc_18000AC96
0x18000ac11  cmp     [rbp+0C0h], r12d
0x18000ac18  jnz     loc_18000ACAC
0x18000ac1e  mov     eax, [rbp+0C0h]
0x18000ac24  mov     [rbx+28h], eax
0x18000ac27  bt      r15d, 10h
0x18000ac2c  jnb     loc_18000AD0F
0x18000ac32  or      dword ptr [rbx+30h], 10000h
0x18000ac39  xor     edx, edx
0x18000ac3b  movsx   eax, word ptr [rbx+36h]
0x18000ac3f  cmp     edx, eax
0x18000ac41  jge     loc_18000AD0F
0x18000ac47  movsxd  rax, edx
0x18000ac4a  lea     rcx, [rax+rax*2]
0x18000ac4e  mov     rax, [rbx+8]
0x18000ac52  lea     r9, [rax+rcx*8]
0x18000ac56  mov     ecx, [rax+rcx*8+8]
0x18000ac5a  mov     eax, ecx
0x18000ac5c  and     eax, 0F0h
0x18000ac61  jz      short loc_18000ACC0
0x18000ac63  cmp     eax, 10h
0x18000ac66  jnz     short loc_18000AC6D
0x18000ac68  mov     byte ptr [r9+0Ch], 41h ; 'A'
0x18000ac6d  test    byte ptr [r9+12h], 1
0x18000ac72  jz      short loc_18000AC92
0x18000ac74  movsx   eax, word ptr [rbx+34h]
0x18000ac78  cmp     eax, edx
0x18000ac7a  jz      short loc_18000AC92
0x18000ac7c  test    cl, 0Fh
0x18000ac7f  jnz     short loc_18000AC92
0x18000ac81  and     ecx, 0FFFFFFF2h
0x18000ac84  or      ecx, 2
0x18000ac87  mov     [r9+8], ecx
0x18000ac8b  or      dword ptr [rbx+30h], 800h
0x18000ac92  inc     edx
0x18000ac94  jmp     short loc_18000AC3B
0x18000ac96  mov     eax, [rbp+0C0h]
0x18000ac9c  mov     [rbx+28h], eax
0x18000ac9f  cmp     eax, 1
0x18000aca2  jnz     short loc_18000AC27
0x18000aca4  or      [rbx+30h], eax
0x18000aca7  jmp     loc_18000AC27
0x18000acac  lea     rdx, Src
0x18000acb3  mov     rcx, rsi
0x18000acb6  call    sqlite3ErrorMsg
0x18000acbb  jmp     loc_18000B494
0x18000acc0  test    byte ptr [r9+12h], 4
0x18000acc5  jz      short loc_18000ACF5
0x18000acc7  lea     rdx, Src
0x18000acce  mov     rcx, r9
0x18000acd1  call    sqlite3ColumnType
0x18000acd6  mov     r9, [r9]
0x18000acd9  lea     rdx, aUnknownDatatyp; "unknown datatype for %s.%s: \"%s\""
0x18000ace0  mov     r8, [rbx]
0x18000ace3  mov     rcx, rsi
0x18000ace6  mov     [rsp+0C8h+var_A8], rax
0x18000aceb  call    sqlite3ErrorMsg
0x18000acf0  jmp     loc_18000B494
0x18000acf5  mov     r9, [r9]
0x18000acf8  lea     rdx, aMissingDatatyp; "missing datatype for %s.%s"
0x18000acff  mov     r8, [rbx]
0x18000ad02  mov     rcx, rsi
0x18000ad05  call    sqlite3ErrorMsg
0x18000ad0a  jmp     loc_18000B494
0x18000ad0f  test    r15b, r15b
0x18000ad12  jns     short loc_18000AD57
0x18000ad14  mov     eax, [rbx+30h]
0x18000ad17  mov     rcx, rsi
0x18000ad1a  test    al, 8
0x18000ad1c  jz      short loc_18000AD2F
0x18000ad1e  lea     rdx, aAutoincrementN; "AUTOINCREMENT not allowed on WITHOUT RO"...
0x18000ad25  call    sqlite3ErrorMsg
0x18000ad2a  jmp     loc_18000B494
0x18000ad2f  test    al, 4
0x18000ad31  jnz     short loc_18000AD47
0x18000ad33  mov     r8, [rbx]
0x18000ad36  lea     rdx, aPrimaryKeyMiss; "PRIMARY KEY missing on table %s"
0x18000ad3d  call    sqlite3ErrorMsg
0x18000ad42  jmp     loc_18000B494
0x18000ad47  or      eax, 280h
0x18000ad4c  mov     rdx, rbx
0x18000ad4f  mov     [rbx+30h], eax
0x18000ad52  call    convertToWithoutRowidTable
0x18000ad57  mov     rcx, [rbx+60h]
0x18000ad5b  mov     dword ptr [rsp+0C8h+arg_0], 0FFFF8000h
0x18000ad66  test    rcx, rcx
0x18000ad69  jz      short loc_18000AD95
0x18000ad6b  mov     r8, [rbp+20h]
0x18000ad6f  xor     edx, edx
0x18000ad71  mov     dword ptr [rsp+0C8h+arg_0], edx
0x18000ad78  cmp     [r8+18h], rcx
0x18000ad7c  jz      short loc_18000AD95
0x18000ad7e  inc     edx
0x18000ad80  movsxd  rax, edx
0x18000ad83  shl     rax, 5
0x18000ad87  cmp     [rax+r8+18h], rcx
0x18000ad8c  jnz     short loc_18000AD7E
0x18000ad8e  mov     dword ptr [rsp+0C8h+arg_0], edx
0x18000ad95  mov     rax, [rbx+20h]
0x18000ad99  test    rax, rax
0x18000ad9c  jz      short loc_18000ADD6
0x18000ad9e  xor     r9d, r9d
0x18000ada1  mov     [rsp+0C8h+var_A8], rax
0x18000ada6  mov     r8d, 4
0x18000adac  mov     rdx, rbx
0x18000adaf  mov     rcx, rsi
0x18000adb2  call    sqlite3ResolveSelfReference
0x18000adb7  cmp     dword ptr [rsi+30h], 0
0x18000adbb  jz      short loc_18000ADD6
0x18000adbd  mov     rdx, [rbx+20h]
0x18000adc1  test    rdx, rdx
0x18000adc4  jz      short loc_18000ADCE
0x18000adc6  mov     rcx, rbp
0x18000adc9  call    exprListDeleteNN
0x18000adce  mov     qword ptr [rbx+20h], 0
0x18000add6  test    byte ptr [rbx+30h], 60h
0x18000adda  mov     [rsp+0C8h+var_38], rdi
0x18000ade2  jz      loc_18000AEB6
0x18000ade8  xor     edx, edx
0x18000adea  xor     eax, eax
0x18000adec  mov     dword ptr [rsp+0C8h+arg_10], edx
0x18000adf3  cmp     ax, [rbx+36h]
0x18000adf7  jge     loc_18000AE97
0x18000adfd  mov     r14d, eax
0x18000ae00  movsxd  rax, r14d
0x18000ae03  lea     rcx, [rax+rax*2]
0x18000ae07  lea     rdi, ds:0[rcx*8]
0x18000ae0f  mov     rcx, [rbx+8]
0x18000ae13  add     rcx, rdi
0x18000ae16  test    byte ptr [rcx+12h], 60h
0x18000ae1a  jz      loc_18000AEAB
0x18000ae20  mov     rdx, rcx
0x18000ae23  mov     rcx, rbx
0x18000ae26  call    sqlite3ColumnExpr
0x18000ae2b  mov     r9, rax
0x18000ae2e  mov     [rsp+0C8h+var_A8], 0
0x18000ae37  mov     rcx, rsi
0x18000ae3a  mov     r8d, 8
0x18000ae40  mov     rdx, rbx
0x18000ae43  call    sqlite3ResolveSelfReference
0x18000ae48  test    eax, eax
0x18000ae4a  jz      short loc_18000AE74
0x18000ae4c  add     rdi, [rbx+8]
0x18000ae50  xor     r9d, r9d
0x18000ae53  xor     r8d, r8d
0x18000ae56  mov     edx, 79h ; 'y'
0x18000ae5b  mov     rcx, rbp
0x18000ae5e  call    sqlite3ExprAlloc
0x18000ae63  mov     r9, rax
0x18000ae66  mov     r8, rdi
0x18000ae69  mov     rdx, rbx
0x18000ae6c  mov     rcx, rsi
0x18000ae6f  call    sqlite3ColumnSetExpr
0x18000ae74  mov     edx, dword ptr [rsp+0C8h+arg_10]
0x18000ae7b  movsx   eax, word ptr [rbx+36h]
0x18000ae7f  inc     r14d
0x18000ae82  cmp     r14d, eax
0x18000ae85  jl      loc_18000AE00
0x18000ae8b  mov     r14, [rsp+0C8h+arg_8]
0x18000ae93  test    edx, edx
0x18000ae95  jnz     short loc_18000AEB6
0x18000ae97  lea     rdx, aMustHaveAtLeas; "must have at least one non-generated co"...
0x18000ae9e  mov     rcx, rsi
0x18000aea1  call    sqlite3ErrorMsg
0x18000aea6  jmp     loc_18000B48C
0x18000aeab  inc     edx
0x18000aead  mov     dword ptr [rsp+0C8h+arg_10], edx
0x18000aeb4  jmp     short loc_18000AE7B
0x18000aeb6  movsx   edx, word ptr [rbx+36h]
0x18000aeba  xor     ecx, ecx
0x18000aebc  mov     r8, [rbx+8]
0x18000aec0  test    edx, edx
0x18000aec2  jle     short loc_18000AED5
0x18000aec4  movzx   eax, byte ptr [r8+0Dh]
0x18000aec9  lea     r8, [r8+18h]
0x18000aecd  add     ecx, eax
0x18000aecf  dec     edx
0x18000aed1  test    edx, edx
0x18000aed3  jg      short loc_18000AEC4
0x18000aed5  cmp     word ptr [rbx+34h], 0
0x18000aeda  lea     eax, [rcx+1]
0x18000aedd  cmovge  eax, ecx
0x18000aee0  shl     eax, 2
0x18000aee3  mov     ecx, eax
0x18000aee5  call    sqlite3LogEst
0x18000aeea  mov     rdi, [rbx+10h]
0x18000aeee  mov     [rbx+3Ch], ax
0x18000aef2  test    rdi, rdi
0x18000aef5  jz      short loc_18000AF08
0x18000aef7  mov     rcx, rdi
0x18000aefa  call    estimateIndexWidth
0x18000aeff  mov     rdi, [rdi+28h]
0x18000af03  test    rdi, rdi
0x18000af06  jnz     short loc_18000AEF7
0x18000af08  cmp     byte ptr [rbp+0C5h], 0
0x18000af0f  jnz     loc_18000B41D
0x18000af15  mov     r14, [rsi+10h]
0x18000af19  test    r14, r14
0x18000af1c  jnz     short loc_18000AF48
0x18000af1e  cmp     [rsi+0B0h], r14
0x18000af25  jnz     short loc_18000AF34
0x18000af27  mov     rax, [rsi]
0x18000af2a  test    byte ptr [rax+60h], 8
0x18000af2e  jnz     short loc_18000AF34
0x18000af30  mov     byte ptr [rsi+23h], 1
0x18000af34  mov     rcx, rsi
0x18000af37  call    sqlite3VdbeCreate
0x18000af3c  mov     r14, rax
0x18000af3f  test    rax, rax
0x18000af42  jz      loc_18000B48C
0x18000af48  xor     r9d, r9d
0x18000af4b  mov     dword ptr [rsp+0C8h+var_A8], 0
0x18000af53  xor     r8d, r8d
0x18000af56  mov     edx, 7Ah ; 'z'
0x18000af5b  mov     rcx, r14
0x18000af5e  call    sqlite3VdbeAddOp3
0x18000af63  movzx   eax, byte ptr [rbx+3Fh]
0x18000af67  lea     rcx, aView; "VIEW"
0x18000af6e  test    al, al
0x18000af70  lea     r8, aTable_0; "TABLE"
0x18000af77  lea     rdx, aView_0; "view"
0x18000af7e  cmovnz  r8, rcx
0x18000af82  lea     rcx, aTable; "table"
0x18000af89  cmovnz  rcx, rdx
0x18000af8d  mov     [rsp+0C8h+var_70], rcx
0x18000af92  test    r12, r12
0x18000af95  jz      loc_18000B20F
0x18000af9b  xor     eax, eax
0x18000af9d  xorps   xmm0, xmm0
0x18000afa0  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x18000afa5  mov     qword ptr [rsp+0C8h+var_58+0Dh], rax
0x18000afaa  movups  [rsp+0C8h+var_68], xmm0
0x18000afaf  cmp     [rsi+134h], al
0x18000afb5  jz      short loc_18000AFC6
0x18000afb7  inc     dword ptr [rsi+30h]
0x18000afba  mov     dword ptr [rsi+18h], 1
0x18000afc1  jmp     loc_18000B48C
0x18000afc6  mov     edx, [rsi+34h]
0x18000afc9  mov     rcx, rsi
0x18000afcc  mov     edi, [rsi+38h]
0x18000afcf  mov     r8d, edx
0x18000afd2  mov     r15d, dword ptr [rsp+0C8h+arg_0]
0x18000afda  inc     edi
0x18000afdc  mov     dword ptr [rsp+0C8h+arg_10], edx
0x18000afe3  lea     eax, [rdx+1]
0x18000afe6  mov     dword ptr [rsp+0C8h+var_A8], r15d
0x18000afeb  mov     [rsi+34h], eax
0x18000afee  mov     edx, 71h ; 'q'
0x18000aff3  lea     eax, [rdi+1]
0x18000aff6  mov     [rsp+0C8h+var_74], eax
0x18000affa  inc     eax
0x18000affc  mov     [rsi+38h], eax
0x18000afff  mov     [rsp+0C8h+var_78], eax
0x18000b003  mov     rax, [rsi+0B0h]
0x18000b00a  test    rax, rax
0x18000b00d  cmovnz  rcx, rax
0x18000b011  mov     byte ptr [rcx+21h], 1
0x18000b015  mov     rcx, r14
0x18000b018  mov     r9d, [rsi+8Ch]
0x18000b01f  call    sqlite3VdbeAddOp3
0x18000b024  mov     edx, 10h
0x18000b029  mov     rcx, r14
0x18000b02c  call    sqlite3VdbeChangeP5
0x18000b031  mov     eax, [r14+90h]
0x18000b038  xor     r9d, r9d
  ... truncated ...
```

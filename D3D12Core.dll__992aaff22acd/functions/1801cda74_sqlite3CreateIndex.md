# sqlite3CreateIndex

- ea: `0x1801cda74`
- end: `0x1801ce6ef`
- name: `sqlite3CreateIndex`
- size: `3195`
- prototype: ``
- caller_count: `3`
- callee_count: `55`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1801a08a4`
- `0x1801c51b4`
- `0x18021d7f0`

## callees

- `0x1800bc07c`
- `0x1800bc094`
- `0x1801a353c`
- `0x1801ac5ec`
- `0x1801bdd58`
- `0x1801c5610`
- `0x1801c716c`
- `0x1801c7bf0`
- `0x1801cb4d4`
- `0x1801cc4f8`
- `0x1801cc610`
- `0x1801cda74`
- `0x1801ce9a0`
- `0x1801ceee4`
- `0x1801d0c94`
- `0x1801d125c`
- `0x1801d3c20`
- `0x1801d4890`
- `0x1801d4b08`
- `0x1801d4bb0`
- `0x1801d4d80`
- `0x1801d5114`
- `0x1801d5a40`
- `0x1801d5ac8`
- `0x1801d6340`
- `0x1801d63c4`
- `0x1801d71ec`
- `0x1801d770c`
- `0x1801da0fc`
- `0x1801da1b4`
- `0x1801da284`
- `0x1801da6d8`
- `0x1801dcfec`
- `0x1801dd19c`
- `0x1801dd55c`
- `0x1801de0f4`
- `0x1801de124`
- `0x1801de36c`
- `0x1801e4bb8`
- `0x1801e5344`
- `0x1801e5688`
- `0x1801e5eb8`
- `0x1801e63bc`
- `0x1801e7704`
- `0x1801e9ec8`
- `0x1801ea2e4`
- `0x1801eac38`
- `0x1801eaca4`
- `0x1801eacc8`
- `0x1801eb23c`

## string_xrefs

- `0x1801cdddb`: `sqlite_temp_master`
- `0x1801ce547`: `CREATE%s INDEX %.*s`
- `0x1801cdd28`: `there is already a table named %s`
- `0x1801cdd57`: `index %s already exists`
- `0x1801cdbe6`: `cannot create a TEMP index on non-TEMP table "%s"`

## pseudocode

```c
__int64 __fastcall sqlite3CreateIndex(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _WORD *a5,
        int a6,
        __int64 a7,
        void *a8,
        unsigned int a9,
        int a10,
        unsigned __int8 a11)
{
  __int64 *v13; // rdi
  _BYTE *v15; // r13
  __int64 v16; // r15
  int v17; // r12d
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 TableItem; // rax
  const char **v21; // r14
  const char *v22; // r8
  const char *v23; // rdx
  char v24; // al
  __int64 v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // rax
  const char *v28; // rax
  int v29; // r9d
  __int64 v30; // rsi
  const char *v31; // r8
  int v32; // edx
  _DWORD *v33; // rsi
  const char *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 i; // rdx
  __int64 v40; // rcx
  int v41; // eax
  int v42; // r8d
  int v43; // eax
  int v44; // r8d
  __int64 v45; // rdx
  void **v46; // rax
  void **v47; // rsi
  char *v48; // rcx
  size_t v49; // r8
  int v50; // eax
  unsigned int v51; // ecx
  const char *v52; // rdx
  bool v53; // cf
  _QWORD *v54; // r8
  int v55; // ebx
  int v56; // r13d
  _QWORD *v57; // r8
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rcx
  int v63; // eax
  const char *v64; // r13
  size_t v65; // rbx
  const void *v66; // rcx
  const char *v67; // rax
  char *v68; // r8
  __int64 v69; // rdx
  char v70; // cl
  _BYTE *v71; // rax
  __int64 *k; // r14
  __int64 v73; // rcx
  int v74; // r15d
  int v75; // ebx
  __int64 v76; // rdi
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // rax
  int v80; // ebx
  int v81; // r13d
  int v82; // r11d
  const char *j; // rbx
  int v84; // r13d
  unsigned int v85; // r11d
  _WORD *v86; // rax
  __int64 v87; // rcx
  int v88; // r11d
  char v89; // al
  __int64 v90; // r12
  unsigned int v91; // ebx
  __int64 Vdbe; // r13
  const char *v93; // r8
  unsigned int v94; // edx
  __int64 v95; // r9
  __int64 v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rax
  unsigned __int8 v100; // [rsp+48h] [rbp-B9h]
  _BYTE *v101; // [rsp+50h] [rbp-B1h]
  int v102; // [rsp+58h] [rbp-A9h]
  int v103; // [rsp+58h] [rbp-A9h]
  _WORD *v104; // [rsp+60h] [rbp-A1h]
  void *v105; // [rsp+68h] [rbp-99h] BYREF
  __int64 v106; // [rsp+70h] [rbp-91h]
  _QWORD *v107; // [rsp+78h] [rbp-89h] BYREF
  char *v108; // [rsp+80h] [rbp-81h] BYREF
  int v109; // [rsp+88h] [rbp-79h]
  int v110; // [rsp+8Ch] [rbp-75h]
  const char **v111; // [rsp+90h] [rbp-71h]
  __int64 v112; // [rsp+98h] [rbp-69h]
  __int64 v113; // [rsp+A0h] [rbp-61h]
  _BYTE v114[144]; // [rsp+A8h] [rbp-59h] BYREF
  unsigned int v116; // [rsp+148h] [rbp+47h]

  v13 = a1;
  v15 = 0;
  memset_0(v114, 0, 0x60u);
  v16 = *v13;
  v113 = *v13;
  v107 = 0;
  v105 = 0;
  if ( *((_DWORD *)v13 + 12) || *((_BYTE *)v13 + 308) == 1 && a11 != 2 || (unsigned int)sqlite3ReadSchema(v13) )
  {
    v104 = a5;
    goto LABEL_180;
  }
  v104 = a5;
  if ( !(unsigned int)sqlite3HasExplicitNulls(v13, a5) )
  {
    v106 = 0;
    if ( a4 )
    {
      v17 = sqlite3TwoPartName(v13, a2, a3, &v107);
      if ( v17 < 0 )
        goto LABEL_180;
      if ( !*(_BYTE *)(v16 + 197) )
      {
        v18 = sqlite3SrcListLookup(v13, a4);
        if ( !*(_DWORD *)(a3 + 8) && v18 && *(_QWORD *)(v18 + 96) == *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) )
          v17 = 1;
      }
      sqlite3FixInit((unsigned int)v114, (_DWORD)v13, v17, (unsigned int)"index", (__int64)v107);
      v19 = a4;
      sqlite3FixSrcList(v114, a4);
      TableItem = sqlite3LocateTableItem(v13, 0, a4 + 8);
      v111 = (const char **)TableItem;
      v21 = (const char **)TableItem;
      if ( !TableItem )
        goto LABEL_100;
      if ( v17 == 1 && *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) != *(_QWORD *)(TableItem + 96) )
      {
        sqlite3ErrorMsg(v13, "cannot create a TEMP index on non-TEMP table \"%s\"", *(const char **)TableItem);
        goto LABEL_101;
      }
      if ( *(char *)(TableItem + 48) < 0 )
        v106 = sqlite3PrimaryKeyIndex(TableItem);
    }
    else
    {
      v21 = (const char **)v13[44];
      v111 = v21;
      if ( !v21 )
        goto LABEL_180;
      v19 = a4;
      v17 = sqlite3SchemaToIndex(v16, v21[12]);
    }
    if ( !(unsigned int)sqlite3_strnicmp(*v21, "sqlite_", 7) && !*(_BYTE *)(v16 + 197) && v19 )
    {
      v22 = *v21;
      v23 = "table %s may not be indexed";
LABEL_25:
      sqlite3ErrorMsg(v13, v23, v22);
      goto LABEL_100;
    }
    v24 = *((_BYTE *)v21 + 63);
    if ( v24 == 2 )
    {
      sqlite3ErrorMsg(v13, "views may not be indexed");
      goto LABEL_100;
    }
    if ( v24 == 1 )
    {
      sqlite3ErrorMsg(v13, "virtual tables may not be indexed");
      goto LABEL_100;
    }
    v25 = *(_QWORD *)(v16 + 32);
    v26 = 32LL * v17;
    v112 = v25;
    if ( v107 )
    {
      v27 = sqlite3NameFromToken(v16, v107);
      v101 = (_BYTE *)v27;
      v15 = (_BYTE *)v27;
      if ( !v27 || (unsigned int)sqlite3CheckObjectName(v13, v27, "index", *v21) )
        goto LABEL_100;
      if ( *((_BYTE *)v13 + 308) >= 2u )
      {
LABEL_54:
        v33 = a5;
        if ( a5 )
        {
          sqlite3ExprListCheckLength(v13, a5, "index");
          if ( *((_DWORD *)v13 + 12) )
            goto LABEL_100;
        }
        else
        {
          v34 = v21[1];
          v110 = 0;
          v35 = *((__int16 *)v21 + 27);
          *(_WORD *)&v34[24 * v35 - 6] |= 8u;
          v108 = *(char **)&v34[24 * v35 - 24];
          v109 = ((__int64 (*)(void))sqlite3Strlen30)();
          v36 = sqlite3ExprAlloc(v16, 59, &v108, 0);
          v37 = sqlite3ExprListAppend(v13, 0, v36);
          v104 = (_WORD *)v37;
          v33 = (_DWORD *)v37;
          if ( !v37 )
            goto LABEL_100;
          sqlite3ExprListSetSortOrder(v37, a9, 0xFFFFFFFFLL);
        }
        v38 = 0;
        for ( i = 0; (int)i < *v33; i = (unsigned int)(i + 1) )
        {
          v40 = *(_QWORD *)&v33[8 * (unsigned int)i + 2];
          if ( *(_BYTE *)v40 == 113 )
          {
            v41 = sqlite3Strlen30(*(_QWORD *)(v40 + 8), i, v38);
            v38 = (unsigned int)(v41 + v42 + 1);
          }
        }
        v43 = sqlite3Strlen30(v15, i, v38);
        v102 = v43;
        if ( v106 )
          v45 = *(unsigned __int16 *)(v106 + 94);
        else
          v45 = 1;
        LOWORD(v45) = *(_WORD *)v33 + v45;
        v46 = (void **)sqlite3AllocateIndexObject(v16, v45, (unsigned int)(v43 + 1 + v44), &v105);
        v47 = v46;
        if ( *(_BYTE *)(v16 + 103) )
        {
LABEL_98:
          if ( v47 )
            sqlite3FreeIndex(v16, v47);
          goto LABEL_100;
        }
        v48 = (char *)v105;
        *v46 = v105;
        v49 = v102 + 1;
        v108 = &v48[v49];
        memcpy_0(v48, v15, v49);
        *((_BYTE *)v47 + 98) = a6;
        v50 = *((_DWORD *)v47 + 25);
        v47[3] = v21;
        v51 = v50 & 0xFFFFFFF7 | (a6 != 0 ? 8 : 0);
        v52 = 0;
        *((_DWORD *)v47 + 25) = v51 ^ ((unsigned __int8)v51 ^ a11) & 3;
        v47[6] = *(void **)(v26 + *(_QWORD *)(v16 + 32) + 24);
        *((_WORD *)v47 + 47) = *v104;
        if ( a8 )
        {
          sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v21, 2, (_DWORD)a8, 0);
          v52 = 0;
          v47[9] = a8;
          a8 = 0;
        }
        v53 = *((_BYTE *)v13 + 308) < 2u;
        v54 = v104 + 4;
        v105 = v104 + 4;
        v100 = *(_BYTE *)(*(_QWORD *)(v26 + v112 + 24) + 112LL);
        if ( !v53 )
        {
          v47[10] = v104;
          v104 = 0;
        }
        v55 = 0;
        while ( 1 )
        {
          v56 = *((unsigned __int16 *)v47 + 47);
          v103 = v55;
          if ( v55 >= v56 )
          {
            if ( v106 )
            {
              if ( *(_WORD *)(v106 + 94) )
              {
                v74 = v55;
                v75 = 0;
                v76 = v106;
                do
                {
                  if ( (unsigned int)isDupColumn(v47, (unsigned __int16)v56, v76, (unsigned int)v75) )
                  {
                    --*((_WORD *)v47 + 48);
                  }
                  else
                  {
                    v77 = v74++;
                    v52 = (const char *)v75;
                    *((_WORD *)v47[1] + v77) = *(_WORD *)(*(_QWORD *)(v76 + 8) + 2LL * v75);
                    *((_QWORD *)v47[8] + v77) = *(_QWORD *)(*(_QWORD *)(v76 + 64) + 8LL * v75);
                    *((_BYTE *)v47[7] + v77) = *(_BYTE *)(v75 + *(_QWORD *)(v76 + 56));
                    LOWORD(v56) = *((_WORD *)v47 + 47);
                  }
                  ++v75;
                }
                while ( v75 < *(unsigned __int16 *)(v76 + 94) );
                v13 = a1;
                v21 = v111;
                v16 = v113;
              }
            }
            else
            {
              v52 = "BINARY";
              *((_WORD *)v47[1] + v55) = -1;
              *((_QWORD *)v47[8] + v55) = "BINARY";
            }
            sqlite3DefaultRowEst(v47, v52);
            if ( !v13[44] )
              estimateIndexWidth(v47);
            recomputeColumnsNotIndexed(v47);
            v79 = a4;
            if ( a4 )
            {
              if ( *((unsigned __int16 *)v47 + 48) >= *((__int16 *)v21 + 27) )
              {
                v80 = 0;
                *((_DWORD *)v47 + 25) |= 0x20u;
                v81 = *((__int16 *)v21 + 27);
                while ( v80 < v81 )
                {
                  if ( v80 != *((__int16 *)v21 + 26)
                    && (sqlite3TableColumnToIndex(v47, (unsigned __int16)v80, 0) & 0x8000u) != 0LL )
                  {
                    *((_DWORD *)v47 + 25) = v82 & 0xFFFFFFDF;
                    break;
                  }
                  ++v80;
                }
              }
              v79 = a4;
            }
            if ( v21 == (const char **)v13[44] )
            {
              for ( j = v21[2]; ; j = (const char *)*((_QWORD *)j + 5) )
              {
                if ( !j )
                {
                  v79 = a4;
                  break;
                }
                v84 = *((unsigned __int16 *)j + 47);
                if ( (_WORD)v84 == *((_WORD *)v47 + 47) )
                {
                  v85 = 0;
                  if ( (_WORD)v84 )
                  {
                    v86 = v47[1];
                    v87 = *((_QWORD *)j + 1);
                    while ( *(_WORD *)(v87 + 2LL * v85) == v86[v85]
                         && !(unsigned int)sqlite3StrICmp(
                                             *(_QWORD *)(*((_QWORD *)j + 8) + 8LL * v85),
                                             *((_QWORD *)v47[8] + v85)) )
                    {
                      v86 = v47[1];
                      v85 = v88 + 1;
                      v87 = *((_QWORD *)j + 1);
                      if ( (int)v85 >= v84 )
                        goto LABEL_134;
                    }
                  }
                  else
                  {
LABEL_134:
                    if ( v85 == v84 )
                    {
                      v89 = *((_BYTE *)v47 + 98);
                      if ( j[98] != v89 )
                      {
                        if ( j[98] == 11 )
                          goto LABEL_141;
                        if ( v89 != 11 )
                          sqlite3ErrorMsg(v13, "conflicting ON CONFLICT clauses specified", 0);
                        if ( j[98] == 11 )
LABEL_141:
                          *((_BYTE *)j + 98) = *((_BYTE *)v47 + 98);
                      }
                      if ( a11 == 2 )
                        *((_DWORD *)j + 25) ^= ((unsigned __int8)*((_DWORD *)j + 25) ^ 2) & 3;
                      v15 = v101;
                      if ( *((_BYTE *)v13 + 308) >= 2u )
                      {
                        v47[5] = (void *)v13[45];
                        v13[45] = (__int64)v47;
                        v47 = 0;
                      }
                      goto LABEL_98;
                    }
                  }
                }
              }
            }
            if ( *((_BYTE *)v13 + 308) < 2u )
            {
              if ( *(_BYTE *)(v16 + 197) )
              {
                v90 = a4;
                if ( a4 )
                {
                  *((_DWORD *)v47 + 22) = *(_DWORD *)(v16 + 192);
                  if ( (unsigned int)sqlite3IndexHasDuplicateRootPage(v47, v78, 0) )
                  {
                    sqlite3ErrorMsg(v13, "invalid rootpage");
                    *((_DWORD *)v13 + 6) = sqlite3ReportError(11, 125740, "database corruption");
                    goto LABEL_97;
                  }
                }
                if ( sqlite3HashInsert((char *)v47[6] + 32, *v47, v47) )
                {
                  sqlite3OomFault(v16);
                  goto LABEL_97;
                }
                *(_DWORD *)(v16 + 44) |= 1u;
LABEL_169:
                if ( *(_BYTE *)(v16 + 197) || !v90 )
                {
                  v47[5] = (void *)v21[2];
                  v21[2] = (const char *)v47;
                }
                else
                {
                  if ( *((_BYTE *)v13 + 308) < 2u )
                    goto LABEL_97;
                  v13[45] = (__int64)v47;
                }
                v15 = v101;
LABEL_100:
                if ( v21 )
                {
LABEL_101:
                  for ( k = (__int64 *)(v21 + 2); ; k = (__int64 *)(v73 + 40) )
                  {
                    v73 = *k;
                    if ( !*k )
                      break;
                    if ( *(_BYTE *)(v73 + 98) == 5 )
                    {
                      while ( 1 )
                      {
                        v98 = *(_QWORD *)(v73 + 40);
                        if ( !v98 || *(_BYTE *)(v98 + 98) == 5 )
                          break;
                        *k = v98;
                        k = (__int64 *)(v98 + 40);
                        *(_QWORD *)(v73 + 40) = *(_QWORD *)(v98 + 40);
                        *(_QWORD *)(v98 + 40) = v73;
                      }
                      goto LABEL_180;
                    }
                  }
                }
                goto LABEL_180;
              }
              if ( *((char *)v21 + 48) >= 0 || v79 )
              {
                v91 = ++*((_DWORD *)v13 + 14);
                v116 = v91;
                Vdbe = sqlite3GetVdbe(v13);
                if ( !Vdbe )
                  goto LABEL_97;
                sqlite3BeginWriteOperation(v13, 1, (unsigned int)v17);
                *((_DWORD *)v47 + 22) = sqlite3VdbeAddOp3(Vdbe, 187, 0, 0, 0);
                sqlite3VdbeAddOp3(Vdbe, 147, v17, v91, 2);
                if ( a7 )
                {
                  v93 = Src;
                  v94 = *((_DWORD *)v13 + 72) + *((_DWORD *)v13 + 74) - *(_DWORD *)v107;
                  v95 = v94 - 1;
                  if ( *(_BYTE *)((int)v95 + *v107) != 59 )
                    v95 = v94;
                  if ( a6 )
                    v93 = " UNIQUE";
                  v96 = sqlite3MPrintf(v16, "CREATE%s INDEX %.*s", v93, v95, *v107);
                }
                else
                {
                  v96 = 0;
                }
                sqlite3NestedParse(
                  v13,
                  "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
                  *(_QWORD *)(32LL * v17 + *(_QWORD *)(v16 + 32)),
                  *v47,
                  *v21,
                  v116,
                  v96);
                sqlite3DbFree(v16, v96);
                if ( a4 )
                {
                  sqlite3RefillIndex(v13, v47, v116);
                  sqlite3VdbeAddOp3(v13[2], 100, v17, 1, **(_DWORD **)(32LL * v17 + *(_QWORD *)(*v13 + 32) + 24) + 1);
                  v97 = sqlite3MPrintf(v16, "name='%q' AND type='index'", *v47);
                  sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v17, v97, 0);
                  sqlite3VdbeAddOp3(Vdbe, 166, 0, 1, 0);
                }
                *(_DWORD *)(sqlite3VdbeGetOp(Vdbe, *((unsigned int *)v47 + 22)) + 8) = *(_DWORD *)(Vdbe + 144);
              }
            }
            v90 = a4;
            goto LABEL_169;
          }
          sqlite3StringToId(*v54, 0);
          sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v21, 32, *v57, v58);
          if ( *((_DWORD *)v13 + 12) )
            goto LABEL_97;
          v59 = sqlite3ExprSkipCollate(*(_QWORD *)v105);
          if ( *(_BYTE *)v59 == 0xA7 )
          {
            v62 = *(__int16 *)(v59 + 48);
            if ( (int)v62 >= 0 )
            {
              if ( (v21[1][24 * v62 + 8] & 0xF) == 0 )
                *((_DWORD *)v47 + 25) &= ~8u;
              if ( (v21[1][24 * v62 + 18] & 0x20) != 0 )
                *((_DWORD *)v47 + 25) |= 0x1800u;
            }
            else
            {
              LODWORD(v62) = *((__int16 *)v21 + 26);
            }
            v61 = v55;
            *((_WORD *)v47[1] + v55) = v62;
          }
          else
          {
            if ( v21 == (const char **)v13[44] )
            {
              sqlite3ErrorMsg(v13, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
LABEL_97:
              v15 = v101;
              goto LABEL_98;
            }
            if ( !v47[10] )
            {
              v47[10] = v104;
              v104 = 0;
            }
            v61 = v55;
            LODWORD(v62) = -2;
            *((_WORD *)v47[1] + v55) = -2;
            *((_DWORD *)v47 + 25) = *((_DWORD *)v47 + 25) & 0xFFFFEFF7 | 0x1000;
          }
          if ( **(_BYTE **)v60 == 113 )
          {
            v63 = sqlite3Strlen30(*(_QWORD *)(*(_QWORD *)v60 + 8LL), v61, v60);
            v64 = v108;
            v65 = v63 + 1;
            memcpy_0(v108, v66, v65);
            v67 = &v64[v65];
            v55 = v103;
            v108 = (char *)v67;
          }
          else
          {
            if ( (int)v62 < 0 )
              goto LABEL_90;
            v64 = (const char *)sqlite3ColumnColl(&v21[1][24 * (int)v62]);
          }
          if ( !v64 )
LABEL_90:
            v64 = "BINARY";
          if ( !*(_BYTE *)(v16 + 197) && !sqlite3LocateCollSeq(v13, v64) )
            goto LABEL_97;
          v68 = (char *)v105;
          v69 = v55;
          *((_QWORD *)v47[8] + v55) = v64;
          v70 = v68[16];
          if ( v100 < 4u )
            v70 = 0;
          v71 = v47[7];
          v54 = v68 + 32;
          ++v55;
          v105 = v54;
          v71[v69] = v70;
          v52 = 0;
        }
      }
      if ( !*(_BYTE *)(v16 + 197) && sqlite3FindTable(v16, v15, *(_QWORD *)(v26 + v25)) )
      {
        v22 = v15;
        v23 = "there is already a table named %s";
        goto LABEL_25;
      }
      if ( sqlite3FindIndex(v16, v15, *(_QWORD *)(v26 + v25)) )
      {
        if ( a10 )
        {
          sqlite3CodeVerifySchema(v13, (unsigned int)v17);
          sqlite3ForceNotReadOnly(v13);
        }
        else
        {
          sqlite3ErrorMsg(v13, "index %s already exists", v15);
        }
        goto LABEL_100;
      }
    }
    else
    {
      v28 = v21[2];
      v29 = 1;
      while ( v28 )
      {
        v28 = (const char *)*((_QWORD *)v28 + 5);
        ++v29;
      }
      v15 = (_BYTE *)sqlite3MPrintf(v16, "sqlite_autoindex_%s_%d", *v21, v29);
      v101 = v15;
      if ( !v15 )
        goto LABEL_100;
      if ( *((_BYTE *)v13 + 308) )
        ++v15[7];
    }
    if ( *((_BYTE *)v13 + 308) < 2u )
    {
      v30 = *(_QWORD *)(v26 + v25);
      v31 = "sqlite_temp_master";
      if ( v17 != 1 )
        v31 = "sqlite_master";
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, 18, (_DWORD)v31, 0, v30) )
        goto LABEL_100;
      v32 = 3;
      if ( v17 != 1 )
        v32 = 1;
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, v32, (_DWORD)v15, (unsigned int)*v21, v30) )
        goto LABEL_100;
    }
    goto LABEL_54;
  }
LABEL_180:
  sqlite3ExprDeleteGeneric(v16, a8);
  sqlite3ExprListDeleteGeneric(v16, v104);
  sqlite3SrcListDelete(v16, a4);
  return sqlite3DbFree(v16, v15);
}

```

## disassembly

```asm
0x1801cda74  mov     rax, rsp
0x1801cda77  mov     [rax+10h], rbx
0x1801cda7b  mov     [rax+20h], r9
0x1801cda7f  mov     [rax+8], rcx
0x1801cda83  push    rbp
0x1801cda84  push    rsi
0x1801cda85  push    rdi
0x1801cda86  push    r12
0x1801cda88  push    r13
0x1801cda8a  push    r14
0x1801cda8c  push    r15
0x1801cda8e  lea     rbp, [rax-3Fh]
0x1801cda92  sub     rsp, 100h
0x1801cda99  xor     r14d, r14d
0x1801cda9c  mov     rbx, r8
0x1801cda9f  mov     rsi, rdx
0x1801cdaa2  mov     rdi, rcx
0x1801cdaa5  xor     edx, edx; Val
0x1801cdaa7  lea     rcx, [rbp+37h+var_90]; void *
0x1801cdaab  mov     r12, r9
0x1801cdaae  mov     r13d, r14d
0x1801cdab1  lea     r8d, [r14+60h]; Size
0x1801cdab5  call    memset_0
0x1801cdaba  mov     r15, [rdi]
0x1801cdabd  mov     [rbp+37h+var_98], r15
0x1801cdac1  mov     [rsp+130h+var_C0], r14
0x1801cdac6  mov     [rsp+130h+var_D0], r14
0x1801cdacb  cmp     [rdi+30h], r14d
0x1801cdacf  jnz     loc_1801CE69B
0x1801cdad5  cmp     byte ptr [rdi+134h], 1
0x1801cdadc  jnz     short loc_1801CDAEB
0x1801cdade  cmp     [rbp+37h+arg_50], 2
0x1801cdae5  jnz     loc_1801CE69B
0x1801cdaeb  mov     rcx, rdi
0x1801cdaee  call    sqlite3ReadSchema
0x1801cdaf3  test    eax, eax
0x1801cdaf5  jnz     loc_1801CE69B
0x1801cdafb  mov     rax, [rbp+37h+arg_20]
0x1801cdaff  mov     rcx, rdi
0x1801cdb02  mov     rdx, rax
0x1801cdb05  mov     [rsp+130h+var_D8], rax
0x1801cdb0a  call    sqlite3HasExplicitNulls
0x1801cdb0f  test    eax, eax
0x1801cdb11  jnz     loc_1801CE6A4
0x1801cdb17  mov     [rsp+130h+var_C8], r14
0x1801cdb1c  test    r12, r12
0x1801cdb1f  jz      loc_1801CDC10
0x1801cdb25  lea     r9, [rsp+130h+var_C0]
0x1801cdb2a  mov     r8, rbx
0x1801cdb2d  mov     rdx, rsi
0x1801cdb30  mov     rcx, rdi
0x1801cdb33  call    sqlite3TwoPartName
0x1801cdb38  mov     r12d, eax
0x1801cdb3b  test    eax, eax
0x1801cdb3d  js      loc_1801CE6A4
0x1801cdb43  cmp     [r15+0C5h], r14b
0x1801cdb4a  jnz     short loc_1801CDB7D
0x1801cdb4c  mov     rdx, [rbp+37h+arg_18]
0x1801cdb50  mov     rcx, rdi
0x1801cdb53  call    sqlite3SrcListLookup
0x1801cdb58  mov     rcx, rax
0x1801cdb5b  cmp     [rbx+8], r14d
0x1801cdb5f  jnz     short loc_1801CDB7D
0x1801cdb61  mov     esi, 1
0x1801cdb66  test    rax, rax
0x1801cdb69  jz      short loc_1801CDB82
0x1801cdb6b  mov     rax, [r15+20h]
0x1801cdb6f  mov     rax, [rax+38h]
0x1801cdb73  cmp     [rcx+60h], rax
0x1801cdb77  cmovz   r12d, esi
0x1801cdb7b  jmp     short loc_1801CDB82
0x1801cdb7d  mov     esi, 1
0x1801cdb82  mov     rax, [rsp+130h+var_C0]
0x1801cdb87  lea     r9, aIndex_0; "index"
0x1801cdb8e  mov     r8d, r12d
0x1801cdb91  mov     qword ptr [rsp+130h+var_110], rax
0x1801cdb96  mov     rdx, rdi
0x1801cdb99  lea     rcx, [rbp+37h+var_90]
0x1801cdb9d  call    sqlite3FixInit
0x1801cdba2  mov     rbx, [rbp+37h+arg_18]
0x1801cdba6  lea     rcx, [rbp+37h+var_90]
0x1801cdbaa  mov     rdx, rbx
0x1801cdbad  call    sqlite3FixSrcList
0x1801cdbb2  lea     r8, [rbx+8]
0x1801cdbb6  xor     edx, edx
0x1801cdbb8  mov     rcx, rdi
0x1801cdbbb  call    sqlite3LocateTableItem
0x1801cdbc0  mov     [rbp+37h+var_A8], rax
0x1801cdbc4  mov     r14, rax
0x1801cdbc7  test    rax, rax
0x1801cdbca  jz      loc_1801CE1A3
0x1801cdbd0  cmp     r12d, esi
0x1801cdbd3  jnz     short loc_1801CDBFA
0x1801cdbd5  mov     rcx, [r15+20h]
0x1801cdbd9  mov     rax, [rax+60h]
0x1801cdbdd  cmp     [rcx+38h], rax
0x1801cdbe1  jz      short loc_1801CDBFA
0x1801cdbe3  mov     r8, [r14]
0x1801cdbe6  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x1801cdbed  mov     rcx, rdi
0x1801cdbf0  call    sqlite3ErrorMsg
0x1801cdbf5  jmp     loc_1801CE1AC
0x1801cdbfa  test    byte ptr [r14+30h], 80h
0x1801cdbff  jz      short loc_1801CDC37
0x1801cdc01  mov     rcx, r14
0x1801cdc04  call    sqlite3PrimaryKeyIndex
0x1801cdc09  mov     [rsp+130h+var_C8], rax
0x1801cdc0e  jmp     short loc_1801CDC37
0x1801cdc10  mov     r14, [rdi+160h]
0x1801cdc17  mov     [rbp+37h+var_A8], r14
0x1801cdc1b  test    r14, r14
0x1801cdc1e  jz      loc_1801CE6A4
0x1801cdc24  mov     rdx, [r14+60h]
0x1801cdc28  mov     rcx, r15
0x1801cdc2b  call    sqlite3SchemaToIndex
0x1801cdc30  mov     rbx, [rbp+37h+arg_18]
0x1801cdc34  mov     r12d, eax
0x1801cdc37  mov     rcx, [r14]
0x1801cdc3a  lea     rdx, aSqlite_0; "sqlite_"
0x1801cdc41  mov     r8d, 7
0x1801cdc47  call    sqlite3_strnicmp
0x1801cdc4c  xor     ecx, ecx
0x1801cdc4e  test    eax, eax
0x1801cdc50  jnz     short loc_1801CDC77
0x1801cdc52  cmp     [r15+0C5h], cl
0x1801cdc59  jnz     short loc_1801CDC77
0x1801cdc5b  test    rbx, rbx
0x1801cdc5e  jz      short loc_1801CDC77
0x1801cdc60  mov     r8, [r14]
0x1801cdc63  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x1801cdc6a  mov     rcx, rdi
0x1801cdc6d  call    sqlite3ErrorMsg
0x1801cdc72  jmp     loc_1801CE1A3
0x1801cdc77  mov     al, [r14+3Fh]
0x1801cdc7b  cmp     al, 2
0x1801cdc7d  jnz     short loc_1801CDC93
0x1801cdc7f  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x1801cdc86  mov     rcx, rdi
0x1801cdc89  call    sqlite3ErrorMsg
0x1801cdc8e  jmp     loc_1801CE1A3
0x1801cdc93  mov     edx, 1
0x1801cdc98  cmp     al, dl
0x1801cdc9a  jnz     short loc_1801CDCA5
0x1801cdc9c  lea     rdx, aVirtualTablesM; "virtual tables may not be indexed"
0x1801cdca3  jmp     short loc_1801CDC86
0x1801cdca5  mov     rax, [rsp+130h+var_C0]
0x1801cdcaa  mov     rsi, [r15+20h]
0x1801cdcae  movsxd  rbx, r12d
0x1801cdcb1  shl     rbx, 5
0x1801cdcb5  mov     [rbp+37h+var_A0], rsi
0x1801cdcb9  test    rax, rax
0x1801cdcbc  jz      loc_1801CDD78
0x1801cdcc2  mov     rdx, rax
0x1801cdcc5  mov     rcx, r15
0x1801cdcc8  call    sqlite3NameFromToken
0x1801cdccd  mov     [rsp+130h+var_E8], rax
0x1801cdcd2  mov     r13, rax
0x1801cdcd5  test    rax, rax
0x1801cdcd8  jz      loc_1801CE1A3
0x1801cdcde  mov     r9, [r14]
0x1801cdce1  lea     r8, aIndex_0; "index"
0x1801cdce8  mov     rdx, rax
0x1801cdceb  mov     rcx, rdi
0x1801cdcee  call    sqlite3CheckObjectName
0x1801cdcf3  test    eax, eax
0x1801cdcf5  jnz     loc_1801CE1A3
0x1801cdcfb  cmp     byte ptr [rdi+134h], 2
0x1801cdd02  jnb     loc_1801CDE24
0x1801cdd08  cmp     [r15+0C5h], al
0x1801cdd0f  jnz     short loc_1801CDD34
0x1801cdd11  mov     r8, [rbx+rsi]
0x1801cdd15  mov     rdx, r13
0x1801cdd18  mov     rcx, r15
0x1801cdd1b  call    sqlite3FindTable
0x1801cdd20  test    rax, rax
0x1801cdd23  jz      short loc_1801CDD34
0x1801cdd25  mov     r8, r13
0x1801cdd28  lea     rdx, aThereIsAlready; "there is already a table named %s"
0x1801cdd2f  jmp     loc_1801CDC6A
0x1801cdd34  mov     r8, [rbx+rsi]
0x1801cdd38  mov     rdx, r13
0x1801cdd3b  mov     rcx, r15
0x1801cdd3e  call    sqlite3FindIndex
0x1801cdd43  test    rax, rax
0x1801cdd46  jz      short loc_1801CDDBE
0x1801cdd48  cmp     [rbp+37h+arg_48], 0
0x1801cdd4f  mov     rcx, rdi
0x1801cdd52  jnz     short loc_1801CDD63
0x1801cdd54  mov     r8, r13
0x1801cdd57  lea     rdx, aIndexSAlreadyE; "index %s already exists"
0x1801cdd5e  jmp     loc_1801CDC6D
0x1801cdd63  mov     edx, r12d
0x1801cdd66  call    sqlite3CodeVerifySchema
0x1801cdd6b  mov     rcx, rdi
0x1801cdd6e  call    sqlite3ForceNotReadOnly
0x1801cdd73  jmp     loc_1801CE1A3
0x1801cdd78  mov     rax, [r14+10h]
0x1801cdd7c  mov     r9d, edx
0x1801cdd7f  jmp     short loc_1801CDD88
0x1801cdd81  mov     rax, [rax+28h]
0x1801cdd85  add     r9d, edx
0x1801cdd88  test    rax, rax
0x1801cdd8b  jnz     short loc_1801CDD81
0x1801cdd8d  mov     r8, [r14]
0x1801cdd90  lea     rdx, aSqliteAutoinde; "sqlite_autoindex_%s_%d"
0x1801cdd97  mov     rcx, r15
0x1801cdd9a  call    sqlite3MPrintf
0x1801cdd9f  mov     r13, rax
0x1801cdda2  mov     [rsp+130h+var_E8], rax
0x1801cdda7  xor     eax, eax
0x1801cdda9  test    r13, r13
0x1801cddac  jz      loc_1801CE1A3
0x1801cddb2  cmp     [rdi+134h], al
0x1801cddb8  jz      short loc_1801CDDBE
0x1801cddba  inc     byte ptr [r13+7]
0x1801cddbe  cmp     byte ptr [rdi+134h], 2
0x1801cddc5  jnb     short loc_1801CDE24
0x1801cddc7  mov     rsi, [rbx+rsi]
0x1801cddcb  lea     rax, aSqliteMaster; "sqlite_master"
0x1801cddd2  cmp     r12d, 1
0x1801cddd6  mov     qword ptr [rsp+130h+var_110], rsi
0x1801cdddb  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x1801cdde2  mov     rcx, rdi
0x1801cdde5  cmovnz  r8, rax
0x1801cdde9  xor     r9d, r9d
0x1801cddec  lea     edx, [r9+12h]
0x1801cddf0  call    sqlite3AuthCheck
0x1801cddf5  test    eax, eax
0x1801cddf7  jnz     loc_1801CE1A3
0x1801cddfd  mov     r9, [r14]
0x1801cde00  lea     edx, [rax+3]
0x1801cde03  lea     eax, [rdx-2]
0x1801cde06  mov     qword ptr [rsp+130h+var_110], rsi
0x1801cde0b  cmp     r12d, eax
0x1801cde0e  mov     r8, r13
0x1801cde11  mov     rcx, rdi
0x1801cde14  cmovnz  edx, eax
0x1801cde17  call    sqlite3AuthCheck
0x1801cde1c  test    eax, eax
0x1801cde1e  jnz     loc_1801CE1A3
0x1801cde24  mov     rsi, [rbp+37h+arg_20]
0x1801cde28  xor     eax, eax
0x1801cde2a  mov     r8d, 8
0x1801cde30  test    rsi, rsi
0x1801cde33  jnz     short loc_1801CDEA4
0x1801cde35  mov     rcx, [r14+8]
0x1801cde39  mov     [rbp+37h+var_AC], eax
0x1801cde3c  movsx   rax, word ptr [r14+36h]
0x1801cde41  lea     rdx, [rax+rax*2]
0x1801cde45  or      [rcx+rdx*8-6], r8w
0x1801cde4b  mov     rcx, [rcx+rdx*8-18h]
0x1801cde50  mov     [rsp+130h+var_B8], rcx
0x1801cde55  call    sqlite3Strlen30
0x1801cde5a  xor     r9d, r9d
0x1801cde5d  mov     [rbp+37h+var_B0], eax
0x1801cde60  lea     r8, [rsp+130h+var_B8]
0x1801cde65  mov     rcx, r15
0x1801cde68  lea     edx, [rsi+3Bh]
0x1801cde6b  call    sqlite3ExprAlloc
0x1801cde70  mov     r8, rax
0x1801cde73  xor     edx, edx
0x1801cde75  mov     rcx, rdi
0x1801cde78  call    sqlite3ExprListAppend
0x1801cde7d  mov     [rsp+130h+var_D8], rax
0x1801cde82  mov     rsi, rax
0x1801cde85  test    rax, rax
0x1801cde88  jz      loc_1801CE1A3
0x1801cde8e  mov     edx, [rbp+37h+arg_40]
0x1801cde94  or      r8d, 0FFFFFFFFh
0x1801cde98  mov     rcx, rax
0x1801cde9b  call    sqlite3ExprListSetSortOrder
0x1801cdea0  xor     eax, eax
0x1801cdea2  jmp     short loc_1801CDEC1
0x1801cdea4  lea     r8, aIndex_0; "index"
0x1801cdeab  mov     rdx, rsi
0x1801cdeae  mov     rcx, rdi
0x1801cdeb1  call    sqlite3ExprListCheckLength
0x1801cdeb6  xor     eax, eax
0x1801cdeb8  cmp     [rdi+30h], eax
0x1801cdebb  jnz     loc_1801CE1A3
0x1801cdec1  mov     r8d, eax
0x1801cdec4  mov     edx, eax
0x1801cdec6  cmp     [rsi], eax
0x1801cdec8  jle     short loc_1801CDEEF
0x1801cdeca  mov     eax, edx
0x1801cdecc  shl     rax, 5
0x1801cded0  mov     rcx, [rax+rsi+8]
0x1801cded5  cmp     byte ptr [rcx], 71h ; 'q'
0x1801cded8  jnz     short loc_1801CDEE9
0x1801cdeda  mov     rcx, [rcx+8]
0x1801cdede  call    sqlite3Strlen30
0x1801cdee3  inc     r8d
0x1801cdee6  add     r8d, eax
0x1801cdee9  inc     edx
0x1801cdeeb  cmp     edx, [rsi]
0x1801cdeed  jl      short loc_1801CDECA
0x1801cdeef  mov     rcx, r13
0x1801cdef2  call    sqlite3Strlen30
0x1801cdef7  mov     rdx, [rsp+130h+var_C8]
0x1801cdefc  mov     dword ptr [rsp+130h+var_E0], eax
  ... truncated ...
```

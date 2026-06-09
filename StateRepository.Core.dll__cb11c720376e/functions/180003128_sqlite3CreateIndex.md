# sqlite3CreateIndex

- ea: `0x180003128`
- end: `0x180003e3f`
- name: `sqlite3CreateIndex`
- size: `3351`
- prototype: ``
- caller_count: `3`
- callee_count: `53`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180031b38`
- `0x18005eea8`
- `0x18006cdd8`

## callees

- `0x180002580`
- `0x1800025b0`
- `0x18000266c`
- `0x1800026f8`
- `0x180002770`
- `0x180003104`
- `0x180003128`
- `0x1800053d4`
- `0x180005810`
- `0x18000a9e0`
- `0x18000c500`
- `0x18000c718`
- `0x18000c930`
- `0x18000c960`
- `0x18000ca30`
- `0x18000fd7c`
- `0x180010810`
- `0x1800110a0`
- `0x1800119e0`
- `0x1800139a4`
- `0x180013a00`
- `0x180013bc0`
- `0x180013db0`
- `0x1800143f0`
- `0x180014434`
- `0x1800150f4`
- `0x1800157d4`
- `0x180016574`
- `0x1800184cc`
- `0x180019d20`
- `0x180019da4`
- `0x1800256c4`
- `0x1800275f0`
- `0x18003465c`
- `0x180036688`
- `0x1800398f0`
- `0x18003de20`
- `0x18003f6dc`
- `0x180053eb0`
- `0x18005d4f8`
- `0x180060ce8`
- `0x180062484`
- `0x1800624b4`
- `0x180064d24`
- `0x180064ef0`
- `0x180067de4`
- `0x18006910e`
- `0x1800723d0`
- `0x1800842a4`
- `0x1800857c4`

## string_xrefs

- `0x1800034e2`: `sqlite_temp_master`
- `0x18000329d`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x180003425`: `there is already a table named %s`
- `0x180003463`: `index %s already exists`
- `0x180003c8e`: `CREATE%s INDEX %.*s`

## pseudocode

```c
__int64 __fastcall sqlite3CreateIndex(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        int a6,
        __int64 a7,
        void *a8,
        unsigned int a9,
        int a10,
        unsigned __int8 a11)
{
  __int64 *v13; // rdi
  void *v14; // rsi
  __int64 v16; // r15
  _DWORD *v17; // r13
  int v18; // r12d
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 TableItem; // rax
  const char *v22; // r11
  const char **v23; // r14
  __int64 v24; // r10
  const char *v25; // r9
  const char *v26; // r8
  int v27; // edx
  char v28; // al
  __int64 v29; // rbx
  __int64 v30; // r13
  __int64 v31; // rax
  int v32; // eax
  int v33; // r11d
  __int64 Index; // rax
  const char *v35; // rax
  int v36; // r9d
  __int64 v37; // rax
  __int64 v38; // rbx
  const char *v39; // r8
  int v40; // edx
  int v41; // eax
  _DWORD *v42; // r10
  __int64 v43; // rax
  const char *v44; // rcx
  int v45; // r10d
  __int64 v46; // rax
  __int64 v47; // rax
  int i; // edx
  __int64 v49; // rcx
  int v50; // ebx
  int v51; // r8d
  _WORD *v52; // r10
  __int64 v53; // rdx
  void **v54; // rax
  void **v55; // rsi
  char *v56; // rcx
  size_t v57; // r8
  int v58; // eax
  unsigned int v59; // ecx
  _WORD *v60; // r11
  bool v61; // cf
  _QWORD *v62; // r8
  int v63; // ebx
  int v64; // r13d
  _QWORD *v65; // r8
  __int64 v66; // r11
  __int64 v67; // rax
  __int64 v68; // r8
  __int64 v69; // rcx
  int v70; // eax
  const char *v71; // r13
  size_t v72; // rbx
  const void *v73; // rcx
  const char *v74; // rax
  __int64 CollSeq; // rax
  char *v76; // r8
  __int64 v77; // rdx
  char v78; // cl
  _BYTE *v79; // rax
  __int64 *k; // r14
  __int64 v81; // rcx
  int v82; // r15d
  int v83; // ebx
  __int64 v84; // rdi
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // rax
  int v88; // ebx
  int v89; // r13d
  int v90; // r11d
  const char *j; // rbx
  int v92; // r13d
  unsigned int v93; // r11d
  _WORD *v94; // rax
  __int64 v95; // rcx
  int v96; // r11d
  char v97; // al
  __int64 v98; // rax
  __int64 v99; // r11
  unsigned int v100; // ebx
  __int64 Vdbe; // r13
  __int64 *v102; // r8
  unsigned int v103; // edx
  __int64 v104; // r9
  __int64 v105; // rbx
  __int64 v106; // rax
  __int64 v107; // rax
  unsigned __int8 v109; // [rsp+48h] [rbp-B9h]
  _WORD *v110; // [rsp+50h] [rbp-B1h]
  void *Src; // [rsp+58h] [rbp-A9h]
  void *v112; // [rsp+60h] [rbp-A1h] BYREF
  __int64 v113; // [rsp+68h] [rbp-99h]
  __int64 v114; // [rsp+70h] [rbp-91h]
  _QWORD *v115; // [rsp+78h] [rbp-89h] BYREF
  char *v116; // [rsp+80h] [rbp-81h] BYREF
  int v117; // [rsp+88h] [rbp-79h]
  int v118; // [rsp+8Ch] [rbp-75h]
  const char **v119; // [rsp+90h] [rbp-71h]
  __int64 v120; // [rsp+98h] [rbp-69h]
  _BYTE v121[144]; // [rsp+A8h] [rbp-59h] BYREF
  unsigned int v123; // [rsp+148h] [rbp+47h]

  v13 = a1;
  v14 = 0;
  memset_0(v121, 0, 0x60u);
  v16 = *v13;
  v120 = *v13;
  v115 = 0;
  v112 = 0;
  if ( *((_DWORD *)v13 + 13) || *((_BYTE *)v13 + 308) == 1 && a11 != 2 || (unsigned int)sqlite3ReadSchema(v13) )
  {
    v17 = a5;
    goto LABEL_188;
  }
  v17 = a5;
  v110 = a5;
  if ( (unsigned int)sqlite3HasExplicitNulls(v13, a5) )
    goto LABEL_188;
  v114 = 0;
  if ( a4 )
  {
    v18 = sqlite3TwoPartName(v13, a2, a3, &v115);
    if ( v18 < 0 )
      goto LABEL_188;
    if ( !*(_BYTE *)(v16 + 197) )
    {
      v19 = sqlite3SrcListLookup(v13, a4);
      if ( !*(_DWORD *)(a3 + 8) && v19 && *(_QWORD *)(v19 + 96) == *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) )
        v18 = 1;
    }
    sqlite3FixInit((unsigned int)v121, (_DWORD)v13, v18, (unsigned int)"index", (__int64)v115);
    v20 = a4;
    sqlite3FixSrcList(v121, a4);
    TableItem = sqlite3LocateTableItem(v13, 0, a4 + 8);
    v22 = 0;
    v119 = (const char **)TableItem;
    v23 = (const char **)TableItem;
    if ( !TableItem )
      goto LABEL_188;
    v24 = 1;
    if ( v18 == 1 && *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) != *(_QWORD *)(TableItem + 96) )
    {
      sqlite3ErrorMsg(v13, "cannot create a TEMP index on non-TEMP table \"%s\"", *(_QWORD *)TableItem);
      goto LABEL_110;
    }
    if ( *(char *)(TableItem + 48) < 0 )
      v114 = sqlite3PrimaryKeyIndex(TableItem);
  }
  else
  {
    v23 = (const char **)v13[44];
    v119 = v23;
    if ( !v23 )
      goto LABEL_188;
    v20 = a4;
    v18 = sqlite3SchemaToIndex(v16, v23[12]);
    v24 = 1;
  }
  if ( *v23 != v22 )
  {
    v25 = *v23;
    v26 = "sqlite_";
    v27 = 7;
    while ( 1 )
    {
      v27 -= v24;
      if ( *v25 == (_BYTE)v22 )
        break;
      v17 = a5;
      if ( *((_BYTE *)qword_18009E760 + *(unsigned __int8 *)v25) != *((_BYTE *)qword_18009E760 + *(unsigned __int8 *)v26) )
        break;
      v25 += v24;
      v26 += v24;
      if ( v27 <= 0 )
      {
        v27 -= v24;
        break;
      }
    }
    if ( (v27 < 0
       || *((unsigned __int8 *)qword_18009E760 + *(unsigned __int8 *)v25) == *((unsigned __int8 *)qword_18009E760
                                                                             + *(unsigned __int8 *)v26))
      && *(_BYTE *)(v16 + 197) == (_BYTE)v22
      && v20 )
    {
      sqlite3ErrorMsg(v13, "table %s may not be indexed", *v23);
      goto LABEL_110;
    }
  }
  v28 = *((_BYTE *)v23 + 63);
  if ( v28 == 2 )
  {
    sqlite3ErrorMsg(v13, "views may not be indexed");
    goto LABEL_110;
  }
  if ( v28 == (_BYTE)v24 )
  {
    sqlite3ErrorMsg(v13, "virtual tables may not be indexed");
    goto LABEL_110;
  }
  v29 = *(_QWORD *)(v16 + 32);
  v30 = 32LL * v18;
  v113 = v29;
  if ( !v115 )
  {
    v35 = v23[2];
    v36 = v24;
    while ( v35 )
    {
      v35 = (const char *)*((_QWORD *)v35 + 5);
      v36 += v24;
    }
    v37 = sqlite3MPrintf(v16, "sqlite_autoindex_%s_%d", *v23, v36);
    v33 = 0;
    Src = (void *)v37;
    v14 = (void *)v37;
    if ( !v37 )
      goto LABEL_109;
    if ( *((_BYTE *)v13 + 308) )
      ++*(_BYTE *)(v37 + 7);
LABEL_54:
    if ( *((_BYTE *)v13 + 308) < 2u )
    {
      v38 = *(_QWORD *)(v29 + 32LL * v18);
      v39 = "sqlite_temp_master";
      if ( v18 != 1 )
        v39 = "sqlite_master";
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, 18, (_DWORD)v39, 0, v38) )
        goto LABEL_109;
      v40 = 3;
      if ( v18 != 1 )
        v40 = 1;
      v41 = sqlite3AuthCheck((_DWORD)v13, v40, (_DWORD)v14, (unsigned int)*v23, v38);
      v33 = 0;
      if ( v41 )
        goto LABEL_109;
    }
    goto LABEL_61;
  }
  v31 = sqlite3NameFromToken(v16, v115);
  Src = (void *)v31;
  v14 = (void *)v31;
  if ( !v31 )
    goto LABEL_109;
  v32 = sqlite3CheckObjectName(v13, v31, "index", *v23);
  v33 = 0;
  if ( v32 )
    goto LABEL_109;
  if ( *((_BYTE *)v13 + 308) < 2u )
  {
    if ( !*(_BYTE *)(v16 + 197) && sqlite3FindTable(v16, v14, *(_QWORD *)(v29 + 32LL * v18)) )
    {
      sqlite3ErrorMsg(v13, "there is already a table named %s", v14);
LABEL_43:
      v17 = a5;
      goto LABEL_110;
    }
    Index = sqlite3FindIndex(v16, v14, *(_QWORD *)(v29 + 32LL * v18));
    v33 = 0;
    if ( Index )
    {
      if ( a10 )
      {
        sqlite3CodeVerifySchema(v13, (unsigned int)v18);
        sqlite3ForceNotReadOnly(v13);
      }
      else
      {
        sqlite3ErrorMsg(v13, "index %s already exists", v14);
      }
      goto LABEL_43;
    }
    goto LABEL_54;
  }
LABEL_61:
  v42 = a5;
  if ( a5 )
  {
    if ( *a5 > *(_DWORD *)(*v13 + 144) )
    {
      sqlite3ErrorMsg(v13, "too many columns in %s", "index");
      v42 = a5;
      v33 = 0;
    }
    if ( *((_DWORD *)v13 + 13) )
      goto LABEL_109;
  }
  else
  {
    v43 = *((__int16 *)v23 + 27);
    v44 = v23[1];
    v118 = 0;
    *(_WORD *)&v44[24 * v43 - 6] |= 8u;
    v116 = *(char **)&v44[24 * v43 - 24];
    v117 = sqlite3Strlen30(v116);
    v46 = sqlite3ExprAlloc(v16, (unsigned int)(v45 + 60), &v116, 0);
    v47 = sqlite3ExprListAppend(v13, 0, v46);
    v110 = (_WORD *)v47;
    if ( !v47 )
      goto LABEL_109;
    sqlite3ExprListSetSortOrder(v47, a9, 0xFFFFFFFFLL);
  }
  for ( i = v33; i < *v42; ++i )
  {
    v49 = *(_QWORD *)&v42[8 * i + 2];
    if ( *(_BYTE *)v49 == 114 )
      sqlite3Strlen30(*(_QWORD *)(v49 + 8));
  }
  v50 = sqlite3Strlen30(v14);
  if ( v114 )
    v53 = *(unsigned __int16 *)(v114 + 94);
  else
    v53 = 1;
  LOWORD(v53) = *v52 + v53;
  v54 = (void **)sqlite3AllocateIndexObject(v16, v53, (unsigned int)(v50 + v51 + 1), &v112);
  v55 = v54;
  if ( *(_BYTE *)(v16 + 103) )
  {
LABEL_106:
    if ( v55 )
      sqlite3FreeIndex(v16, v55);
    goto LABEL_108;
  }
  v56 = (char *)v112;
  *v54 = v112;
  v57 = v50 + 1;
  v116 = &v56[v57];
  memcpy_0(v56, Src, v57);
  *((_BYTE *)v55 + 98) = a6;
  v58 = *((_DWORD *)v55 + 25);
  v55[3] = v23;
  v59 = v58 & 0xFFFFFFF7 | (a6 != 0 ? 8 : 0);
  LODWORD(v60) = 0;
  *((_DWORD *)v55 + 25) = v59 ^ ((unsigned __int8)v59 ^ a11) & 3;
  v55[6] = *(void **)(*(_QWORD *)(v16 + 32) + v30 + 24);
  *((_WORD *)v55 + 47) = *v110;
  if ( a8 )
  {
    sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v23, 2, (_DWORD)a8, 0);
    LODWORD(v60) = 0;
    v55[9] = a8;
    a8 = 0;
  }
  v61 = *((_BYTE *)v13 + 308) < 2u;
  v109 = *(_BYTE *)(*(_QWORD *)(v113 + v30 + 24) + 112LL);
  v62 = v110 + 4;
  v112 = v110 + 4;
  if ( !v61 )
  {
    v55[10] = v110;
    v110 = 0;
  }
  v63 = 0;
  while ( 1 )
  {
    v64 = *((unsigned __int16 *)v55 + 47);
    LODWORD(v113) = v63;
    if ( v63 >= v64 )
      break;
    sqlite3StringToId(*v62);
    sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v23, 32, *v65, v66);
    if ( *((_DWORD *)v13 + 13) )
      goto LABEL_106;
    v67 = sqlite3ExprSkipCollate(*(_QWORD *)v112);
    if ( *(_BYTE *)v67 == 0xA8 )
    {
      v69 = *(__int16 *)(v67 + 48);
      if ( (int)v69 >= 0 )
      {
        if ( (v23[1][24 * v69 + 8] & 0xF) == 0 )
          *((_DWORD *)v55 + 25) &= ~8u;
        if ( (v23[1][24 * v69 + 18] & 0x20) != 0 )
          *((_DWORD *)v55 + 25) |= 0x1800u;
      }
      else
      {
        LODWORD(v69) = *((__int16 *)v23 + 26);
      }
      *((_WORD *)v55[1] + v63) = v69;
    }
    else
    {
      if ( v23 == (const char **)v13[44] )
      {
        sqlite3ErrorMsg(v13, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
        goto LABEL_106;
      }
      if ( v55[10] == v60 )
      {
        v55[10] = v110;
        v110 = v60;
      }
      LODWORD(v69) = -2;
      *((_WORD *)v55[1] + v63) = -2;
      *((_DWORD *)v55 + 25) &= ~8u;
      *((_DWORD *)v55 + 25) |= 0x1000u;
    }
    if ( **(_BYTE **)v68 == 114 )
    {
      v70 = sqlite3Strlen30(*(_QWORD *)(*(_QWORD *)v68 + 8LL));
      v71 = v116;
      v72 = v70 + 1;
      memcpy_0(v116, v73, v72);
      v74 = &v71[v72];
      LODWORD(v60) = 0;
      v63 = v113;
      v116 = (char *)v74;
    }
    else
    {
      if ( (int)v69 < 0 )
        goto LABEL_99;
      v71 = (const char *)sqlite3ColumnColl(&v23[1][24 * (int)v69]);
    }
    if ( !v71 )
LABEL_99:
      v71 = "BINARY";
    if ( *(_BYTE *)(v16 + 197) == (_BYTE)v60 )
    {
      CollSeq = sqlite3LocateCollSeq(v13, v71);
      LODWORD(v60) = 0;
      if ( !CollSeq )
        goto LABEL_106;
    }
    v76 = (char *)v112;
    v77 = v63;
    *((_QWORD *)v55[8] + v63) = v71;
    v78 = v76[16];
    v79 = v55[7];
    if ( v109 < 4u )
      v78 = (char)v60;
    ++v63;
    v62 = v76 + 32;
    v112 = v62;
    v79[v77] = v78;
  }
  if ( v114 )
  {
    if ( (unsigned __int16)v60 < *(_WORD *)(v114 + 94) )
    {
      v82 = v113;
      v83 = (int)v60;
      v84 = v114;
      do
      {
        if ( (unsigned int)isDupColumn(v55, (unsigned __int16)v64, v84, (unsigned int)v83) )
        {
          --*((_WORD *)v55 + 48);
        }
        else
        {
          v85 = v82++;
          *((_WORD *)v55[1] + v85) = *(_WORD *)(*(_QWORD *)(v84 + 8) + 2LL * v83);
          *((_QWORD *)v55[8] + v85) = *(_QWORD *)(*(_QWORD *)(v84 + 64) + 8LL * v83);
          *((_BYTE *)v55[7] + v85) = *(_BYTE *)(v83 + *(_QWORD *)(v84 + 56));
          LOWORD(v64) = *((_WORD *)v55 + 47);
        }
        ++v83;
      }
      while ( v83 < *(unsigned __int16 *)(v84 + 94) );
      v13 = a1;
      v23 = v119;
      v16 = v120;
    }
  }
  else
  {
    *((_WORD *)v55[1] + v63) = -1;
    *((_QWORD *)v55[8] + v63) = "BINARY";
  }
  sqlite3DefaultRowEst(v55);
  if ( !v13[44] )
    estimateIndexWidth(v55);
  recomputeColumnsNotIndexed(v55);
  v87 = a4;
  if ( a4 )
  {
    if ( *((unsigned __int16 *)v55 + 48) >= *((__int16 *)v23 + 27) )
    {
      v88 = 0;
      *((_DWORD *)v55 + 25) |= 0x20u;
      v89 = *((__int16 *)v23 + 27);
      while ( v88 < v89 )
      {
        if ( v88 != *((__int16 *)v23 + 26)
          && (sqlite3TableColumnToIndex(v55, (unsigned __int16)v88, 0) & 0x8000u) != 0LL )
        {
          *((_DWORD *)v55 + 25) = v90 & 0xFFFFFFDF;
          break;
        }
        ++v88;
      }
    }
    v87 = a4;
  }
  if ( v23 == (const char **)v13[44] )
  {
    for ( j = v23[2]; ; j = (const char *)*((_QWORD *)j + 5) )
    {
      if ( !j )
      {
        v87 = a4;
        break;
      }
      v92 = *((unsigned __int16 *)j + 47);
      if ( (_WORD)v92 == *((_WORD *)v55 + 47) )
      {
        v93 = 0;
        if ( (_WORD)v92 )
        {
          v94 = v55[1];
          v95 = *((_QWORD *)j + 1);
          while ( *(_WORD *)(v95 + 2LL * v93) == v94[v93]
               && !(unsigned int)sqlite3StrICmp(*(_QWORD *)(*((_QWORD *)j + 8) + 8LL * v93), *((_QWORD *)v55[8] + v93)) )
          {
            v94 = v55[1];
            v93 = v96 + 1;
            v95 = *((_QWORD *)j + 1);
            if ( (int)v93 >= v92 )
              goto LABEL_143;
          }
        }
        else
        {
LABEL_143:
          if ( v93 == v92 )
          {
            v97 = *((_BYTE *)v55 + 98);
            if ( j[98] != v97 )
            {
              if ( j[98] == 11 )
                goto LABEL_150;
              if ( v97 != 11 )
                sqlite3ErrorMsg(v13, "conflicting ON CONFLICT clauses specified", 0);
              if ( j[98] == 11 )
LABEL_150:
                *((_BYTE *)j + 98) = *((_BYTE *)v55 + 98);
            }
            if ( a11 == 2 )
              *((_DWORD *)j + 25) ^= ((unsigned __int8)*((_DWORD *)j + 25) ^ 2) & 3;
            if ( *((_BYTE *)v13 + 308) >= 2u )
            {
              v55[5] = (void *)v13[45];
              v13[45] = (__int64)v55;
              v55 = 0;
            }
            goto LABEL_106;
          }
        }
      }
    }
  }
  if ( *((_BYTE *)v13 + 308) >= 2u )
  {
LABEL_177:
    v99 = 0;
    goto LABEL_178;
  }
  if ( !*(_BYTE *)(v16 + 197) )
  {
    if ( *((char *)v23 + 48) >= 0 || v87 )
    {
      v100 = ++*((_DWORD *)v13 + 15);
      v123 = v100;
      Vdbe = sqlite3GetVdbe(v13);
      if ( !Vdbe )
        goto LABEL_106;
      sqlite3BeginWriteOperation(v13, 1, (unsigned int)v18);
      *((_DWORD *)v55 + 22) = sqlite3VdbeAddOp3(Vdbe, 187, 0, 0, 0);
      sqlite3VdbeAddOp3(Vdbe, 147, v18, v100, 2);
      if ( a7 )
      {
        v102 = qword_18009EEF0;
        v103 = *((_DWORD *)v13 + 72) + *((_DWORD *)v13 + 74) - *(_DWORD *)v115;
        v104 = v103 - 1;
        if ( *(_BYTE *)((int)v104 + *v115) != 59 )
          v104 = v103;
        if ( a6 )
          v102 = (__int64 *)" UNIQUE";
        v105 = sqlite3MPrintf(v16, "CREATE%s INDEX %.*s", v102, v104, *v115);
      }
      else
      {
        v105 = 0;
      }
      sqlite3NestedParse(
        v13,
        "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
        *(_QWORD *)(32LL * v18 + *(_QWORD *)(v16 + 32)),
        *v55,
        *v23,
        v123,
        v105);
      sqlite3DbFree(v16, v105);
      if ( a4 )
      {
        sqlite3RefillIndex(v13, v55, v123);
        sqlite3VdbeAddOp3(v13[2], 100, v18, 1, **(_DWORD **)(32LL * v18 + *(_QWORD *)(*v13 + 32) + 24) + 1);
        v106 = sqlite3MPrintf(v16, "name='%q' AND type='index'", *v55);
        sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v18, v106, 0);
        sqlite3VdbeAddOp3(Vdbe, 166, 0, 1, 0);
      }
      *(_DWORD *)(sqlite3VdbeGetOp(Vdbe, *((unsigned int *)v55 + 22)) + 8) = *(_DWORD *)(Vdbe + 144);
      goto LABEL_178;
    }
    goto LABEL_177;
  }
  if ( v87 )
  {
    *((_DWORD *)v55 + 22) = *(_DWORD *)(v16 + 192);
    if ( (unsigned int)sqlite3IndexHasDuplicateRootPage(v55, v86, 0) )
    {
      sqlite3ErrorMsg(v13, "invalid rootpage");
      sqlite3_log(
        11,
        "%s at line %d of [%.10s]",
        "database corruption",
        126337,
        "2aabe05e2e8cae4847a802ee2daddc1d7413d8fc560254d93ee3e72c14685b6c");
      *((_DWORD *)v13 + 6) = 11;
      goto LABEL_106;
    }
  }
  v98 = sqlite3HashInsert((char *)v55[6] + 32, *v55, v55);
  v99 = 0;
  if ( v98 )
  {
    sqlite3OomFault(v16);
    goto LABEL_106;
  }
  *(_DWORD *)(v16 + 44) |= 1u;
LABEL_178:
  if ( *(_BYTE *)(v16 + 197) != (_BYTE)v99 || a4 == v99 )
  {
    v55[5] = (void *)v23[2];
    v23[2] = (const char *)v55;
  }
  else
  {
    if ( *((_BYTE *)v13 + 308) < 2u )
      goto LABEL_106;
    v13[45] = (__int64)v55;
  }
LABEL_108:
  v14 = Src;
LABEL_109:
  v17 = v110;
LABEL_110:
  for ( k = (__int64 *)(v23 + 2); ; k = (__int64 *)(v81 + 40) )
  {
    v81 = *k;
    if ( !*k )
      break;
    if ( *(_BYTE *)(v81 + 98) == 5 )
    {
      while ( 1 )
      {
        v107 = *(_QWORD *)(v81 + 40);
        if ( !v107 || *(_BYTE *)(v107 + 98) == 5 )
          break;
        *k = v107;
        k = (__int64 *)(v107 + 40);
        *(_QWORD *)(v81 + 40) = *(_QWORD *)(v107 + 40);
        *(_QWORD *)(v107 + 40) = v81;
      }
      break;
    }
  }
LABEL_188:
  if ( a8 )
    sqlite3ExprDeleteNN(v16);
  sqlite3ExprListDeleteGeneric(v16, v17);
  sqlite3SrcListDelete(v16, a4);
  return sqlite3DbFree(v16, v14);
}

```

## disassembly

```asm
0x180003128  mov     rax, rsp
0x18000312b  mov     [rax+10h], rbx
0x18000312f  mov     [rax+20h], r9
0x180003133  mov     [rax+8], rcx
0x180003137  push    rbp
0x180003138  push    rsi
0x180003139  push    rdi
0x18000313a  push    r12
0x18000313c  push    r13
0x18000313e  push    r14
0x180003140  push    r15
0x180003142  lea     rbp, [rax-3Fh]
0x180003146  sub     rsp, 100h
0x18000314d  mov     rbx, r8
0x180003150  mov     r14, rdx
0x180003153  mov     rdi, rcx
0x180003156  xor     esi, esi
0x180003158  xor     edx, edx; Val
0x18000315a  lea     rcx, [rbp+37h+var_90]; void *
0x18000315e  mov     r12, r9
0x180003161  lea     r8d, [rsi+60h]; Size
0x180003165  call    memset_0
0x18000316a  mov     r15, [rdi]
0x18000316d  xor     r11d, r11d
0x180003170  mov     [rbp+37h+var_A0], r15
0x180003174  mov     [rsp+130h+var_C0], r11
0x180003179  mov     [rsp+130h+var_D8], r11
0x18000317e  cmp     [rdi+34h], r11d
0x180003182  jnz     loc_180003DEA
0x180003188  cmp     byte ptr [rdi+134h], 1
0x18000318f  jnz     short loc_18000319E
0x180003191  cmp     [rbp+37h+arg_50], 2
0x180003198  jnz     loc_180003DEA
0x18000319e  mov     rcx, rdi
0x1800031a1  call    sqlite3ReadSchema
0x1800031a6  test    eax, eax
0x1800031a8  jnz     loc_180003DEA
0x1800031ae  mov     r13, [rbp+37h+arg_20]
0x1800031b2  mov     rcx, rdi
0x1800031b5  mov     rdx, r13
0x1800031b8  mov     [rsp+130h+var_E8], r13
0x1800031bd  call    sqlite3HasExplicitNulls
0x1800031c2  xor     r11d, r11d
0x1800031c5  test    eax, eax
0x1800031c7  jnz     loc_180003DEE
0x1800031cd  mov     [rsp+130h+var_C8], r11
0x1800031d2  test    r12, r12
0x1800031d5  jz      loc_1800032CA
0x1800031db  lea     r9, [rsp+130h+var_C0]
0x1800031e0  mov     r8, rbx
0x1800031e3  mov     rdx, r14
0x1800031e6  mov     rcx, rdi
0x1800031e9  call    sqlite3TwoPartName
0x1800031ee  xor     r11d, r11d
0x1800031f1  mov     r12d, eax
0x1800031f4  test    eax, eax
0x1800031f6  js      loc_180003DEE
0x1800031fc  cmp     [r15+0C5h], r11b
0x180003203  jnz     short loc_180003235
0x180003205  mov     rdx, [rbp+37h+arg_18]
0x180003209  mov     rcx, rdi
0x18000320c  call    sqlite3SrcListLookup
0x180003211  mov     rcx, rax
0x180003214  xor     eax, eax
0x180003216  cmp     [rbx+8], eax
0x180003219  jnz     short loc_180003235
0x18000321b  test    rcx, rcx
0x18000321e  jz      short loc_180003235
0x180003220  mov     rax, [r15+20h]
0x180003224  mov     edx, 1
0x180003229  mov     rax, [rax+38h]
0x18000322d  cmp     [rcx+60h], rax
0x180003231  cmovz   r12d, edx
0x180003235  mov     rax, [rsp+130h+var_C0]
0x18000323a  lea     r9, aIndex; "index"
0x180003241  mov     r8d, r12d
0x180003244  mov     qword ptr [rsp+130h+var_110], rax
0x180003249  mov     rdx, rdi
0x18000324c  lea     rcx, [rbp+37h+var_90]
0x180003250  call    sqlite3FixInit
0x180003255  mov     rbx, [rbp+37h+arg_18]
0x180003259  lea     rcx, [rbp+37h+var_90]
0x18000325d  mov     rdx, rbx
0x180003260  call    sqlite3FixSrcList
0x180003265  lea     r8, [rbx+8]
0x180003269  xor     edx, edx
0x18000326b  mov     rcx, rdi
0x18000326e  call    sqlite3LocateTableItem
0x180003273  xor     r11d, r11d
0x180003276  mov     [rbp+37h+var_A8], rax
0x18000327a  mov     r14, rax
0x18000327d  test    rax, rax
0x180003280  jz      loc_180003DEE
0x180003286  lea     r10d, [r11+1]
0x18000328a  cmp     r12d, r10d
0x18000328d  jnz     short loc_1800032B4
0x18000328f  mov     rcx, [r15+20h]
0x180003293  mov     rax, [rax+60h]
0x180003297  cmp     [rcx+38h], rax
0x18000329b  jz      short loc_1800032B4
0x18000329d  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x1800032a4  mov     r8, [r14]
0x1800032a7  mov     rcx, rdi
0x1800032aa  call    sqlite3ErrorMsg
0x1800032af  jmp     loc_1800038D0
0x1800032b4  test    byte ptr [r14+30h], 80h
0x1800032b9  jz      short loc_1800032F7
0x1800032bb  mov     rcx, r14
0x1800032be  call    sqlite3PrimaryKeyIndex
0x1800032c3  mov     [rsp+130h+var_C8], rax
0x1800032c8  jmp     short loc_1800032F7
0x1800032ca  mov     r14, [rdi+160h]
0x1800032d1  mov     [rbp+37h+var_A8], r14
0x1800032d5  test    r14, r14
0x1800032d8  jz      loc_180003DEE
0x1800032de  mov     rdx, [r14+60h]
0x1800032e2  mov     rcx, r15
0x1800032e5  call    sqlite3SchemaToIndex
0x1800032ea  mov     rbx, [rbp+37h+arg_18]
0x1800032ee  mov     r12d, eax
0x1800032f1  mov     r10d, 1
0x1800032f7  cmp     [r14], r11
0x1800032fa  jz      short loc_180003377
0x1800032fc  mov     r9, [r14]
0x1800032ff  lea     r8, aSqlite_0; "sqlite_"
0x180003306  mov     edx, 7
0x18000330b  sub     edx, r10d
0x18000330e  cmp     [r9], r11b
0x180003311  jz      short loc_18000333E
0x180003313  movzx   eax, byte ptr [r8]
0x180003317  lea     r13, qword_18009E760
0x18000331e  movzx   ecx, byte ptr [r9]
0x180003322  mov     al, [rax+r13]
0x180003326  cmp     [rcx+r13], al
0x18000332a  mov     r13, [rsp+130h+var_E8]
0x18000332f  jnz     short loc_18000333E
0x180003331  add     r9, r10
0x180003334  add     r8, r10
0x180003337  test    edx, edx
0x180003339  jg      short loc_18000330B
0x18000333b  sub     edx, r10d
0x18000333e  test    edx, edx
0x180003340  js      short loc_18000335D
0x180003342  movzx   eax, byte ptr [r8]
0x180003346  lea     rdx, qword_18009E760
0x18000334d  movzx   ecx, byte ptr [rax+rdx]
0x180003351  movzx   eax, byte ptr [r9]
0x180003355  movzx   eax, byte ptr [rax+rdx]
0x180003359  cmp     eax, ecx
0x18000335b  jnz     short loc_180003377
0x18000335d  cmp     [r15+0C5h], r11b
0x180003364  jnz     short loc_180003377
0x180003366  test    rbx, rbx
0x180003369  jz      short loc_180003377
0x18000336b  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x180003372  jmp     loc_1800032A4
0x180003377  mov     al, [r14+3Fh]
0x18000337b  cmp     al, 2
0x18000337d  jnz     short loc_180003393
0x18000337f  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x180003386  mov     rcx, rdi
0x180003389  call    sqlite3ErrorMsg
0x18000338e  jmp     loc_1800038D0
0x180003393  cmp     al, r10b
0x180003396  jnz     short loc_1800033A1
0x180003398  lea     rdx, aVirtualTablesM; "virtual tables may not be indexed"
0x18000339f  jmp     short loc_180003386
0x1800033a1  mov     rax, [rsp+130h+var_C0]
0x1800033a6  mov     rbx, [r15+20h]
0x1800033aa  movsxd  r13, r12d
0x1800033ad  shl     r13, 5
0x1800033b1  mov     [rsp+130h+var_D0], rbx
0x1800033b6  test    rax, rax
0x1800033b9  jz      loc_18000347E
0x1800033bf  mov     rdx, rax
0x1800033c2  mov     rcx, r15
0x1800033c5  call    sqlite3NameFromToken
0x1800033ca  mov     [rsp+130h+Src], rax
0x1800033cf  mov     rsi, rax
0x1800033d2  test    rax, rax
0x1800033d5  jz      loc_1800038CB
0x1800033db  mov     r9, [r14]
0x1800033de  lea     r8, aIndex; "index"
0x1800033e5  mov     rdx, rax
0x1800033e8  mov     rcx, rdi
0x1800033eb  call    sqlite3CheckObjectName
0x1800033f0  xor     r11d, r11d
0x1800033f3  test    eax, eax
0x1800033f5  jnz     loc_1800038CB
0x1800033fb  cmp     byte ptr [rdi+134h], 2
0x180003402  jnb     loc_18000352E
0x180003408  cmp     [r15+0C5h], r11b
0x18000340f  jnz     short loc_180003440
0x180003411  mov     r8, [rbx+r13]
0x180003415  mov     rdx, rsi
0x180003418  mov     rcx, r15
0x18000341b  call    sqlite3FindTable
0x180003420  test    rax, rax
0x180003423  jz      short loc_180003440
0x180003425  lea     rdx, aThereIsAlready; "there is already a table named %s"
0x18000342c  mov     rcx, rdi
0x18000342f  mov     r8, rsi
0x180003432  call    sqlite3ErrorMsg
0x180003437  mov     r13, [rbp+37h+arg_20]
0x18000343b  jmp     loc_1800038D0
0x180003440  mov     r8, [rbx+r13]
0x180003444  mov     rdx, rsi
0x180003447  mov     rcx, r15
0x18000344a  call    sqlite3FindIndex
0x18000344f  xor     r11d, r11d
0x180003452  test    rax, rax
0x180003455  jz      short loc_1800034C5
0x180003457  mov     rcx, rdi
0x18000345a  cmp     [rbp+37h+arg_48], r11d
0x180003461  jnz     short loc_18000346C
0x180003463  lea     rdx, aIndexSAlreadyE; "index %s already exists"
0x18000346a  jmp     short loc_18000342F
0x18000346c  mov     edx, r12d
0x18000346f  call    sqlite3CodeVerifySchema
0x180003474  mov     rcx, rdi
0x180003477  call    sqlite3ForceNotReadOnly
0x18000347c  jmp     short loc_180003437
0x18000347e  mov     rax, [r14+10h]
0x180003482  mov     r9d, r10d
0x180003485  jmp     short loc_18000348E
0x180003487  mov     rax, [rax+28h]
0x18000348b  add     r9d, r10d
0x18000348e  test    rax, rax
0x180003491  jnz     short loc_180003487
0x180003493  mov     r8, [r14]
0x180003496  lea     rdx, aSqliteAutoinde; "sqlite_autoindex_%s_%d"
0x18000349d  mov     rcx, r15
0x1800034a0  call    sqlite3MPrintf
0x1800034a5  xor     r11d, r11d
0x1800034a8  mov     [rsp+130h+Src], rax
0x1800034ad  mov     rsi, rax
0x1800034b0  test    rax, rax
0x1800034b3  jz      loc_1800038CB
0x1800034b9  cmp     [rdi+134h], r11b
0x1800034c0  jz      short loc_1800034C5
0x1800034c2  inc     byte ptr [rax+7]
0x1800034c5  cmp     byte ptr [rdi+134h], 2
0x1800034cc  jnb     short loc_18000352E
0x1800034ce  mov     rbx, [rbx+r13]
0x1800034d2  lea     rax, aSqliteMaster; "sqlite_master"
0x1800034d9  cmp     r12d, 1
0x1800034dd  mov     qword ptr [rsp+130h+var_110], rbx
0x1800034e2  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x1800034e9  mov     rcx, rdi
0x1800034ec  cmovnz  r8, rax
0x1800034f0  xor     r9d, r9d
0x1800034f3  lea     edx, [r9+12h]
0x1800034f7  call    sqlite3AuthCheck
0x1800034fc  test    eax, eax
0x1800034fe  jnz     loc_1800038CB
0x180003504  mov     r9, [r14]
0x180003507  lea     edx, [rax+3]
0x18000350a  lea     eax, [rdx-2]
0x18000350d  mov     qword ptr [rsp+130h+var_110], rbx
0x180003512  cmp     r12d, eax
0x180003515  mov     r8, rsi
0x180003518  mov     rcx, rdi
0x18000351b  cmovnz  edx, eax
0x18000351e  call    sqlite3AuthCheck
0x180003523  xor     r11d, r11d
0x180003526  test    eax, eax
0x180003528  jnz     loc_1800038CB
0x18000352e  mov     r10, [rbp+37h+arg_20]
0x180003532  mov     r8d, 8
0x180003538  test    r10, r10
0x18000353b  jnz     short loc_1800035AF
0x18000353d  movsx   rax, word ptr [r14+36h]
0x180003542  mov     rcx, [r14+8]
0x180003546  mov     [rbp+37h+var_AC], r11d
0x18000354a  lea     rdx, [rax+rax*2]
0x18000354e  or      [rcx+rdx*8-6], r8w
0x180003554  mov     rcx, [rcx+rdx*8-18h]
0x180003559  mov     [rsp+130h+var_B8], rcx
0x18000355e  call    sqlite3Strlen30
0x180003563  xor     r9d, r9d
0x180003566  mov     [rbp+37h+var_B0], eax
0x180003569  lea     r8, [rsp+130h+var_B8]
0x18000356e  mov     rcx, r15
0x180003571  lea     edx, [r10+3Ch]
0x180003575  call    sqlite3ExprAlloc
0x18000357a  mov     r8, rax
0x18000357d  xor     edx, edx
0x18000357f  mov     rcx, rdi
0x180003582  call    sqlite3ExprListAppend
0x180003587  xor     r11d, r11d
0x18000358a  mov     [rsp+130h+var_E8], rax
0x18000358f  mov     r10, rax
0x180003592  test    rax, rax
0x180003595  jz      loc_1800038CB
0x18000359b  mov     edx, [rbp+37h+arg_40]
0x1800035a1  or      r8d, 0FFFFFFFFh
0x1800035a5  mov     rcx, rax
0x1800035a8  call    sqlite3ExprListSetSortOrder
0x1800035ad  jmp     short loc_1800035E4
0x1800035af  mov     rax, [rdi]
  ... truncated ...
```

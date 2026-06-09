# sqlite3CreateIndex

- ea: `0x180014750`
- end: `0x1800156ee`
- name: `sqlite3CreateIndex`
- size: `3998`
- prototype: ``
- caller_count: `3`
- callee_count: `54`
- tags: `broker_com_uri`

## callers

- `0x18001450c`
- `0x18001bc30`
- `0x18005aed4`

## callees

- `0x180007a00`
- `0x18000b4bc`
- `0x180014464`
- `0x180014750`
- `0x1800156f4`
- `0x180015e80`
- `0x180015e9c`
- `0x180016b18`
- `0x18001ece0`
- `0x180027e60`
- `0x18002817c`
- `0x18002b81c`
- `0x18002e290`
- `0x1800367a0`
- `0x180036970`
- `0x180037954`
- `0x180039494`
- `0x1800399d0`
- `0x18003a860`
- `0x18003b5b4`
- `0x18003b8bc`
- `0x18003b9c8`
- `0x18003bebc`
- `0x18003c8d4`
- `0x18003cc7c`
- `0x18003ceec`
- `0x18003d480`
- `0x18003f5a8`
- `0x18003f8d0`
- `0x18003f960`
- `0x18003ff28`
- `0x18004002c`
- `0x180041894`
- `0x180042260`
- `0x180042374`
- `0x180042d74`
- `0x180045374`
- `0x1800645e4`
- `0x18007c31c`
- `0x1800817c0`
- `0x180081b28`
- `0x180081bac`
- `0x1800829d8`
- `0x180082ef8`
- `0x180083f24`
- `0x180085c74`
- `0x180086a20`
- `0x180088ee0`
- `0x180089130`
- `0x180089bdc`

## string_xrefs

- `0x180014c28`: `sqlite_temp_master`
- `0x18001490a`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x180014b75`: `there is already a table named %s`
- `0x180014ba2`: `index %s already exists`
- `0x1800154ed`: `CREATE%s INDEX %.*s`

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
        __int64 a8,
        unsigned int a9,
        int a10,
        unsigned __int8 a11)
{
  __int64 *v13; // rdi
  __int64 v14; // r12
  _BYTE *v15; // r13
  __int64 v16; // rbp
  int Schema; // eax
  __int64 v18; // r10
  _DWORD *v19; // rsi
  int i; // ecx
  __int64 v21; // rax
  char v22; // cl
  const char *v23; // r8
  signed int v24; // r15d
  __int64 v25; // rcx
  __int64 TableItem; // rax
  _QWORD *v27; // r14
  __int64 v28; // r11
  __int64 v29; // rcx
  __int64 v30; // rdx
  _BYTE *v31; // r9
  const char *v32; // r8
  int v33; // edx
  char v34; // al
  __int64 v35; // rbx
  __int64 v36; // r12
  __int64 v37; // rcx
  char *v38; // r10
  __int64 v39; // rbx
  _QWORD *v40; // rbx
  int v41; // eax
  __int64 v42; // rcx
  int v43; // eax
  const char *v44; // rdx
  __int64 Index; // rax
  __int64 v46; // rax
  int v47; // r9d
  __int64 v48; // rax
  __int64 v49; // rbx
  __int16 v50; // r12
  const char *v51; // r8
  int v52; // edx
  int v53; // eax
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // r8
  __int64 v60; // rdx
  __int64 v61; // rcx
  int v62; // eax
  int v63; // r8d
  int v64; // ebx
  __int16 v65; // r12
  _QWORD *v66; // rax
  _QWORD *v67; // rsi
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rax
  char *v72; // rdx
  size_t v73; // r8
  int v74; // eax
  _WORD *v75; // r10
  __int64 v76; // rcx
  _QWORD *v77; // r8
  __int64 v78; // rcx
  int v79; // ebx
  int v80; // r12d
  _QWORD *v81; // r8
  __int64 v82; // r10
  __int64 v83; // rax
  __int64 v84; // r8
  __int64 v85; // rdx
  __int64 v86; // rcx
  size_t v87; // rbx
  const void *v88; // rcx
  const char *v89; // r12
  char *v90; // rax
  __int64 CollSeq; // rax
  __int64 v92; // rdx
  char v93; // cl
  __int64 *j; // r14
  __int64 v95; // rcx
  int v96; // ebp
  int v97; // ebx
  __int64 v98; // r8
  __int64 v99; // rdx
  int v100; // r11d
  int v101; // ebx
  __int64 v102; // rbx
  unsigned __int16 v103; // ax
  unsigned int v104; // r12d
  __int64 v105; // rax
  __int64 v106; // rcx
  char v107; // al
  __int64 Vdbe; // r12
  __int64 *v109; // rbx
  int v110; // eax
  int v111; // eax
  const char *v112; // r8
  unsigned int v113; // ecx
  __int64 v114; // r9
  __int64 v115; // rbx
  __int64 v116; // rax
  int v117; // edx
  __int64 *v118; // rax
  __int64 v119; // rax
  __int64 result; // rax
  signed int v121; // [rsp+40h] [rbp-F8h]
  int v122; // [rsp+40h] [rbp-F8h]
  _WORD *v123; // [rsp+48h] [rbp-F0h]
  __int64 v124; // [rsp+50h] [rbp-E8h]
  _WORD *v125; // [rsp+50h] [rbp-E8h]
  char *v126; // [rsp+58h] [rbp-E0h]
  char *v127; // [rsp+58h] [rbp-E0h]
  __int64 v128; // [rsp+60h] [rbp-D8h]
  _QWORD *v129; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v130; // [rsp+70h] [rbp-C8h]
  _QWORD *v131; // [rsp+78h] [rbp-C0h]
  __int64 v132; // [rsp+80h] [rbp-B8h] BYREF
  int v133; // [rsp+88h] [rbp-B0h]
  int v134; // [rsp+8Ch] [rbp-ACh]
  size_t Size; // [rsp+90h] [rbp-A8h]
  __int64 v136; // [rsp+98h] [rbp-A0h]
  _BYTE v137[152]; // [rsp+A0h] [rbp-98h] BYREF
  int v139; // [rsp+140h] [rbp+8h]
  unsigned int v140; // [rsp+140h] [rbp+8h]
  int v142; // [rsp+160h] [rbp+28h]
  unsigned __int8 v143; // [rsp+160h] [rbp+28h]

  v13 = a1;
  v14 = a4;
  v15 = 0;
  memset_0(v137, 0, 0x60u);
  v16 = *v13;
  v136 = *v13;
  v129 = 0;
  if ( *((_DWORD *)v13 + 12)
    || *((_BYTE *)v13 + 308) == 1 && a11 != 2
    || (Schema = sqlite3ReadSchema(v13), v18 = 0, Schema) )
  {
    v19 = a5;
    goto LABEL_228;
  }
  v19 = a5;
  v123 = a5;
  if ( a5 )
  {
    for ( i = 0; i < *a5; ++i )
    {
      v21 = 8LL * i;
      if ( (a5[v21 + 7] & 0x20) != 0 )
      {
        v22 = a5[v21 + 6];
        if ( !v22 || (v23 = "LAST", v22 == 3) )
          v23 = "FIRST";
        sqlite3ErrorMsg(v13, "unsupported use of NULLS %s", v23);
        goto LABEL_228;
      }
    }
  }
  v128 = 0;
  if ( v14 )
  {
    v24 = sqlite3TwoPartName(v13, a2, a3, &v129);
    if ( v24 < 0 )
      goto LABEL_228;
    if ( !*(_BYTE *)(v16 + 197) )
    {
      v25 = sqlite3SrcListLookup(v13, v14);
      if ( !*(_DWORD *)(a3 + 8) && v25 && *(_QWORD *)(v25 + 96) == *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) )
        v24 = 1;
    }
    sqlite3FixInit((unsigned int)v137, (_DWORD)v13, v24, (unsigned int)"index", (__int64)v129);
    sqlite3FixSrcList(v137, v14);
    TableItem = sqlite3LocateTableItem(v13, 0, v14 + 8);
    v18 = 0;
    v131 = (_QWORD *)TableItem;
    v27 = (_QWORD *)TableItem;
    if ( !TableItem )
      goto LABEL_228;
    v28 = 1;
    if ( v24 == 1 && *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) != *(_QWORD *)(TableItem + 96) )
    {
      sqlite3ErrorMsg(v13, "cannot create a TEMP index on non-TEMP table \"%s\"", *(_QWORD *)TableItem);
      goto LABEL_141;
    }
    if ( *(char *)(TableItem + 48) < 0 )
      v128 = sqlite3PrimaryKeyIndex(TableItem);
  }
  else
  {
    v27 = (_QWORD *)v13[44];
    v131 = v27;
    if ( !v27 )
      goto LABEL_228;
    v29 = v27[12];
    v24 = -32768;
    v28 = 1;
    if ( v29 )
    {
      v30 = *(_QWORD *)(v16 + 32);
      v24 = 0;
      if ( *(_QWORD *)(v30 + 24) != v29 )
      {
        do
          ++v24;
        while ( *(_QWORD *)(32LL * v24 + v30 + 24) != v29 );
      }
    }
  }
  if ( *v27 != v18 )
  {
    v31 = (_BYTE *)*v27;
    v32 = "sqlite_";
    v33 = 7;
    while ( 1 )
    {
      v33 -= v28;
      if ( *v31 == (_BYTE)v18
        || *((_BYTE *)qword_1800ADCF0 + (unsigned __int8)*v31) != *((_BYTE *)qword_1800ADCF0 + *(unsigned __int8 *)v32) )
      {
        break;
      }
      v31 += v28;
      v32 += v28;
      if ( v33 <= 0 )
      {
        v33 -= v28;
        break;
      }
    }
    if ( (v33 < 0
       || *((unsigned __int8 *)qword_1800ADCF0 + (unsigned __int8)*v31) == *((unsigned __int8 *)qword_1800ADCF0
                                                                           + *(unsigned __int8 *)v32))
      && *(_BYTE *)(v16 + 197) == (_BYTE)v18
      && v14 )
    {
      sqlite3ErrorMsg(v13, "table %s may not be indexed", *v27);
      goto LABEL_141;
    }
  }
  v34 = *((_BYTE *)v27 + 63);
  if ( v34 == 2 )
  {
    sqlite3ErrorMsg(v13, "views may not be indexed");
    goto LABEL_141;
  }
  if ( v34 == (_BYTE)v28 )
  {
    sqlite3ErrorMsg(v13, "virtual tables may not be indexed");
    goto LABEL_141;
  }
  v35 = *(_QWORD *)(v16 + 32);
  v36 = 32LL * v24;
  v130 = v36;
  v124 = v35;
  if ( v129 )
  {
    v15 = (_BYTE *)sqlite3DbStrNDup(v16, *v129, *((unsigned int *)v129 + 2));
    sqlite3Dequote(v15);
    v38 = 0;
    if ( !v37 )
    {
LABEL_56:
      v14 = a4;
      goto LABEL_141;
    }
    v39 = *v13;
    if ( (*(_DWORD *)(*v13 + 48) & 0x10000001) != 1 && (*(_BYTE *)(v39 + 200) & 2) == 0 && byte_1800C6979 )
    {
      if ( *(_BYTE *)(v39 + 197) )
      {
        v40 = *(_QWORD **)(v39 + 208);
        if ( (unsigned int)sqlite3_stricmp("index", *v40)
          || (unsigned int)sqlite3_stricmp(v15, v40[1])
          || (v41 = sqlite3_stricmp(*v27, v40[2]), v38 = 0, v41) )
        {
          sqlite3ErrorMsg(v13, (const char *)&Src);
          goto LABEL_56;
        }
      }
      else if ( !*((_BYTE *)v13 + 30) && !(unsigned int)sqlite3_strnicmp(v37, "sqlite_", 7)
             || (unsigned int)sqlite3ReadOnlyShadowTables(v39) && (v43 = sqlite3ShadowTableName(v42, v15), v38 = 0, v43) )
      {
        v44 = "object name reserved for internal use: %s";
LABEL_62:
        sqlite3ErrorMsg(v13, v44, v15);
        goto LABEL_56;
      }
    }
    v35 = v124;
    if ( *((_BYTE *)v13 + 308) >= 2u )
      goto LABEL_85;
    if ( *(_BYTE *)(v16 + 197) == (_BYTE)v38 && sqlite3FindTable(v16, v15, *(_QWORD *)(v36 + v124)) )
    {
      v44 = "there is already a table named %s";
      goto LABEL_62;
    }
    Index = sqlite3FindIndex(v16, v15, *(_QWORD *)(v36 + v124));
    v38 = 0;
    if ( Index )
    {
      if ( a10 )
      {
        sqlite3CodeVerifySchema(v13, (unsigned int)v24);
        sqlite3ForceNotReadOnly(v13);
      }
      else
      {
        sqlite3ErrorMsg(v13, "index %s already exists", v15);
      }
      goto LABEL_56;
    }
  }
  else
  {
    v46 = v27[2];
    v47 = v28;
    while ( v46 )
    {
      v46 = *(_QWORD *)(v46 + 40);
      v47 += v28;
    }
    v48 = sqlite3MPrintf(v16, "sqlite_autoindex_%s_%d", (const char *)*v27, v47);
    v38 = 0;
    v15 = (_BYTE *)v48;
    if ( !v48 )
      goto LABEL_56;
    if ( *((_BYTE *)v13 + 308) )
      ++*(_BYTE *)(v48 + 7);
  }
  if ( *((_BYTE *)v13 + 308) < 2u )
  {
    v49 = *(_QWORD *)(v36 + v35);
    v50 = 1;
    v51 = "sqlite_temp_master";
    if ( v24 != 1 )
      v51 = "sqlite_master";
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, 18, (_DWORD)v51, 0, v49) )
      goto LABEL_56;
    v52 = 3;
    if ( v24 != 1 )
      v52 = 1;
    v53 = sqlite3AuthCheck((_DWORD)v13, v52, (_DWORD)v15, *v27, v49);
    v38 = 0;
    if ( v53 )
      goto LABEL_56;
    goto LABEL_86;
  }
LABEL_85:
  v50 = 1;
LABEL_86:
  v54 = -1;
  if ( a5 )
  {
    if ( *a5 > *(_DWORD *)(*v13 + 144) )
    {
      sqlite3ErrorMsg(v13, "too many columns in %s", "index");
      v38 = 0;
    }
    if ( *((_DWORD *)v13 + 12) != (_DWORD)v38 )
      goto LABEL_56;
  }
  else
  {
    v55 = *((__int16 *)v27 + 27);
    v56 = v27[1];
    v134 = (int)v38;
    *(_WORD *)(v56 + 24 * v55 - 6) |= 8u;
    v132 = *(_QWORD *)(v56 + 24 * v55 - 24);
    v133 = ((__int64 (*)(void))sqlite3Strlen30)();
    v57 = sqlite3ExprAlloc(v16, 59, &v132, 0);
    v58 = sqlite3ExprListAppend(v13, 0, v57);
    v123 = (_WORD *)v58;
    v19 = (_DWORD *)v58;
    if ( !v58 )
      goto LABEL_56;
    sqlite3ExprListSetSortOrder(v58, a9, 0xFFFFFFFFLL);
  }
  v59 = (unsigned int)v38;
  v126 = v38;
  v60 = (unsigned int)v38;
  if ( *v19 > (int)v38 )
  {
    do
    {
      v61 = *(_QWORD *)&v19[8 * (unsigned int)v60 + 2];
      if ( *(_BYTE *)v61 == 113 )
      {
        v62 = sqlite3Strlen30(*(_QWORD *)(v61 + 8), v60, v59);
        v59 = (unsigned int)(v62 + v63 + 1);
      }
      v60 = (unsigned int)(v60 + 1);
    }
    while ( (int)v60 < *v19 );
  }
  if ( v15 )
  {
    do
      ++v54;
    while ( v15[v54] != (_BYTE)v38 );
    v64 = v54 & 0x3FFFFFFF;
  }
  else
  {
    v64 = (int)v38;
  }
  if ( v128 )
    v50 = *(_WORD *)(v128 + 94);
  v65 = *(_WORD *)v19 + v50;
  v132 = v65;
  v142 = v65 + 1;
  v121 = ((v65 + 2 * (v65 + v142) + 7) & 0xFFFFFFF8) + 8 * (v65 + 14);
  Size = (int)v59 + v64 + v121 + 1LL;
  v66 = (_QWORD *)sqlite3DbMallocRawNN(v16, Size);
  v67 = v66;
  if ( v66 )
  {
    memset_0(v66, 0, Size);
    v68 = v132;
    v67[8] = v67 + 14;
    *((_WORD *)v67 + 48) = v65;
    *((_WORD *)v67 + 47) = v65 - 1;
    v69 = (__int64)&v67[v68 + 14];
    v67[2] = v69;
    v70 = v69 + 2LL * v142;
    v71 = v70 + 2 * v68;
    v67[1] = v70;
    v72 = (char *)v67 + v121;
    v67[7] = v71;
  }
  else
  {
    v72 = v126;
  }
  if ( *(_BYTE *)(v16 + 103) )
    goto LABEL_137;
  *v67 = v72;
  v73 = (unsigned int)(v64 + 1);
  v127 = &v72[v73];
  memcpy_0(v72, v15, v73);
  *((_BYTE *)v67 + 98) = a6;
  v74 = *((_DWORD *)v67 + 25);
  v67[3] = v27;
  LODWORD(v75) = 0;
  v76 = v130;
  *((_DWORD *)v67 + 25) = (v74 & 0xFFFFFFF7 | (a6 != 0 ? 8 : 0)) ^ (a11 ^ (v74 & 0xF7 | (a6 != 0 ? 8 : 0))) & 3;
  v67[6] = *(_QWORD *)(v76 + *(_QWORD *)(v16 + 32) + 24);
  *((_WORD *)v67 + 47) = *v123;
  if ( a8 )
  {
    sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v27, 2, a8, 0);
    LODWORD(v75) = 0;
    v67[9] = a8;
    a8 = 0;
  }
  v77 = v123 + 4;
  v78 = v124;
  v125 = v123 + 4;
  v143 = *(_BYTE *)(*(_QWORD *)(v130 + v78 + 24) + 112LL);
  if ( *((_BYTE *)v13 + 308) >= 2u )
  {
    v67[10] = v123;
    v123 = 0;
  }
  v79 = 0;
  while ( 1 )
  {
    v80 = *((unsigned __int16 *)v67 + 47);
    v122 = v79;
    if ( v79 >= v80 )
      break;
    sqlite3StringToId(*v77);
    sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v27, 32, *v81, v82);
    if ( *((_DWORD *)v13 + 12) )
      goto LABEL_137;
    v83 = sqlite3ExprSkipCollate(*(_QWORD *)v125);
    if ( *(_BYTE *)v83 == 0xA7 )
    {
      v86 = *(__int16 *)(v83 + 48);
      if ( (int)v86 >= 0 )
      {
        if ( (*(_BYTE *)(v27[1] + 24 * v86 + 8) & 0xF) == 0 )
          *((_DWORD *)v67 + 25) &= ~8u;
        if ( (*(_BYTE *)(v27[1] + 24 * v86 + 18) & 0x20) != 0 )
          *((_DWORD *)v67 + 25) |= 0x1800u;
      }
      else
      {
        LODWORD(v86) = *((__int16 *)v27 + 26);
      }
      v85 = v79;
      *(_WORD *)(v67[1] + 2LL * v79) = v86;
    }
    else
    {
      if ( v27 == (_QWORD *)v13[44] )
      {
        sqlite3ErrorMsg(v13, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
LABEL_137:
        v14 = a4;
        goto LABEL_138;
      }
      if ( (_WORD *)v67[10] == v75 )
      {
        v67[10] = v123;
        v123 = v75;
      }
      v85 = v79;
      LODWORD(v86) = -2;
      *(_WORD *)(v67[1] + 2LL * v79) = -2;
      *((_DWORD *)v67 + 25) = *((_DWORD *)v67 + 25) & 0xFFFFEFF7 | 0x1000;
    }
    if ( **(_BYTE **)v84 == 113 )
    {
      v87 = (int)(sqlite3Strlen30(*(_QWORD *)(*(_QWORD *)v84 + 8LL), v85, v84) + 1);
      memcpy_0(v127, v88, v87);
      v89 = v127;
      v90 = &v127[v87];
      v79 = v122;
      LODWORD(v75) = 0;
      v127 = v90;
    }
    else
    {
      if ( (int)v86 < 0 )
        goto LABEL_130;
      v89 = (const char *)sqlite3ColumnColl(v27[1] + 24LL * (int)v86);
    }
    if ( !v89 )
LABEL_130:
      v89 = "BINARY";
    if ( *(_BYTE *)(v16 + 197) == (_BYTE)v75 )
    {
      CollSeq = sqlite3LocateCollSeq(v13, v89);
      LODWORD(v75) = 0;
      if ( !CollSeq )
        goto LABEL_137;
    }
    v92 = v79;
    *(_QWORD *)(v67[8] + 8LL * v79) = v89;
    v93 = *((_BYTE *)v125 + 16);
    if ( v143 < 4u )
      v93 = (char)v75;
    ++v79;
    v77 = v125 + 16;
    v125 += 16;
    *(_BYTE *)(v92 + v67[7]) = v93;
  }
  if ( v128 )
  {
    if ( (unsigned __int16)v75 < *(_WORD *)(v128 + 94) )
    {
      v96 = v79;
      v97 = (int)v75;
      do
      {
        if ( (unsigned int)isDupColumn(v67, (unsigned __int16)v80, v128, (unsigned int)v97) )
        {
          --*((_WORD *)v67 + 48);
        }
        else
        {
          v98 = v96++;
          *(_WORD *)(v67[1] + 2 * v98) = *(_WORD *)(*(_QWORD *)(v128 + 8) + 2LL * v97);
          *(_QWORD *)(v67[8] + 8 * v98) = *(_QWORD *)(*(_QWORD *)(v128 + 64) + 8LL * v97);
          *(_BYTE *)(v98 + v67[7]) = *(_BYTE *)(v97 + *(_QWORD *)(v128 + 56));
          LOWORD(v80) = *((_WORD *)v67 + 47);
        }
        ++v97;
      }
      while ( v97 < *(unsigned __int16 *)(v128 + 94) );
      v13 = a1;
      v27 = v131;
      v16 = v136;
    }
  }
  else
  {
    *(_WORD *)(v67[1] + 2LL * v79) = -1;
    *(_QWORD *)(v67[8] + 8LL * v79) = "BINARY";
  }
  sqlite3DefaultRowEst(v67);
  if ( !v13[44] )
    estimateIndexWidth(v67);
  recomputeColumnsNotIndexed(v67);
  v14 = a4;
  if ( a4 && *((unsigned __int16 *)v67 + 48) >= *((__int16 *)v27 + 27) )
  {
    *((_DWORD *)v67 + 25) |= 0x20u;
    v100 = 0;
    v101 = *((__int16 *)v27 + 27);
    while ( v100 < v101 )
    {
      if ( v100 != *((__int16 *)v27 + 26)
        && (sqlite3TableColumnToIndex(v67, (unsigned __int16)v100, 0) & 0x8000u) != 0LL )
      {
        *((_DWORD *)v67 + 25) &= ~0x20u;
        break;
      }
      ++v100;
    }
  }
  if ( v27 != (_QWORD *)v13[44] )
  {
LABEL_187:
    if ( *((_BYTE *)v13 + 308) < 2u )
    {
      if ( *(_BYTE *)(v16 + 197) )
      {
        if ( v14 )
        {
          *((_DWORD *)v67 + 22) = *(_DWORD *)(v16 + 192);
          if ( (unsigned int)sqlite3IndexHasDuplicateRootPage(v67, v99, 0) )
          {
            sqlite3ErrorMsg(v13, "invalid rootpage");
            *((_DWORD *)v13 + 6) = sqlite3ReportError(11, 125740, "database corruption");
            goto LABEL_138;
          }
        }
        if ( sqlite3HashInsert(v67[6] + 32LL, *v67, v67) )
        {
          sqlite3OomFault(v16);
          goto LABEL_138;
        }
        *(_DWORD *)(v16 + 44) |= 1u;
      }
      else if ( *((char *)v27 + 48) >= 0 || v14 )
      {
        v140 = ++*((_DWORD *)v13 + 14);
        Vdbe = sqlite3GetVdbe(v13);
        if ( !Vdbe )
          goto LABEL_137;
        v109 = v13;
        if ( v13[22] )
          v109 = (__int64 *)v13[22];
        v110 = *((_DWORD *)v109 + 33);
        if ( !_bittest(&v110, v24) )
        {
          *((_DWORD *)v109 + 33) = v110 | (1 << v24);
          if ( v24 == 1 )
            sqlite3OpenTempDatabase(v109);
        }
        v111 = *((_DWORD *)v109 + 32);
        *((_BYTE *)v109 + 32) |= 1u;
        *((_DWORD *)v109 + 32) = v111 | (1 << v24);
        *((_DWORD *)v67 + 22) = sqlite3VdbeAddOp3(Vdbe, 187, 0, 0, 0);
        sqlite3VdbeAddOp3(Vdbe, 147, v24, v140, 2);
        if ( a7 )
        {
          v112 = (const char *)&Src;
          v113 = *((_DWORD *)v13 + 72) + *((_DWORD *)v13 + 74) - *(_DWORD *)v129;
          v114 = v113 - 1;
          if ( *(_BYTE *)((int)v114 + *v129) != 59 )
            v114 = v113;
          if ( a6 )
            v112 = " UNIQUE";
          v115 = sqlite3MPrintf(v16, "CREATE%s INDEX %.*s", v112, v114, *v129);
        }
        else
        {
          v115 = 0;
        }
        sqlite3NestedParse(
          v13,
          "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
          *(_QWORD *)(32LL * v24 + *(_QWORD *)(v16 + 32)),
          *v67,
          *v27,
          v140,
          v115);
        if ( v115 )
          sqlite3DbFreeNN(v16, v115);
        if ( a4 )
        {
          sqlite3RefillIndex(v13, v67, v140);
          sqlite3VdbeAddOp3(v13[2], 100, v24, 1, **(_DWORD **)(32LL * v24 + *(_QWORD *)(*v13 + 32) + 24) + 1);
          v116 = sqlite3MPrintf(v16, "name='%q' AND type='index'", *v67);
          sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v24, v116, 0);
          sqlite3VdbeAddOp3(Vdbe, 166, 0, 1, 0);
        }
        v117 = *(_DWORD *)(Vdbe + 144);
        if ( *(_BYTE *)(*(_QWORD *)Vdbe + 103LL) )
          v118 = qword_1800C7590;
        else
          v118 = (__int64 *)(*(_QWORD *)(Vdbe + 136) + 24LL * *((int *)v67 + 22));
        v14 = a4;
        *((_DWORD *)v118 + 2) = v117;
      }
    }
    if ( *(_BYTE *)(v16 + 197) || !v14 )
    {
      v67[5] = v27[2];
      v27[2] = v67;
    }
    else
    {
      if ( *((_BYTE *)v13 + 308) < 2u )
        goto LABEL_138;
      v13[45] = (__int64)v67;
    }
    goto LABEL_140;
  }
  v102 = v27[2];
  while ( 2 )
  {
    if ( !v102 )
    {
      v14 = a4;
      goto LABEL_187;
    }
    v103 = *(_WORD *)(v102 + 94);
    if ( v103 != *((_WORD *)v67 + 47) )
      goto LABEL_175;
    v139 = *(unsigned __int16 *)(v102 + 94);
    v104 = 0;
    if ( *(_WORD *)(v102 + 94) )
    {
      v105 = v67[1];
      v106 = *(_QWORD *)(v102 + 8);
      while ( *(_WORD *)(v106 + 2LL * v104) == *(_WORD *)(v105 + 2LL * v104)
           && !(unsigned int)sqlite3StrICmp(
                               *(_QWORD *)(*(_QWORD *)(v102 + 64) + 8LL * v104),
                               *(_QWORD *)(v67[8] + 8LL * v104)) )
      {
        v105 = v67[1];
        ++v104;
        v106 = *(_QWORD *)(v102 + 8);
        if ( (int)v104 >= v139 )
        {
          v103 = *(_WORD *)(v102 + 94);
          goto LABEL_174;
        }
      }
      goto LABEL_175;
    }
LABEL_174:
    if ( v104 != v103 )
    {
LABEL_175:
      v102 = *(_QWORD *)(v102 + 40);
      continue;
    }
    break;
  }
  v107 = *((_BYTE *)v67 + 98);
  if ( *(_BYTE *)(v102 + 98) != v107 )
  {
    if ( *(_BYTE *)(v102 + 98) == 11 )
      goto LABEL_181;
    if ( v107 != 11 )
      sqlite3ErrorMsg(v13, "conflicting ON CONFLICT clauses specified", 0);
    if ( *(_BYTE *)(v102 + 98) == 11 )
LABEL_181:
      *(_BYTE *)(v102 + 98) = *((_BYTE *)v67 + 98);
  }
  if ( a11 == 2 )
    *(_DWORD *)(v102 + 100) ^= ((unsigned __int8)*(_DWORD *)(v102 + 100) ^ 2) & 3;
  v14 = a4;
  if ( *((_BYTE *)v13 + 308) >= 2u )
  {
    v67[5] = v13[45];
    v13[45] = (__int64)v67;
    v67 = 0;
  }
LABEL_138:
  if ( v67 )
    sqlite3FreeIndex(v16, v67);
LABEL_140:
  v19 = v123;
LABEL_141:
  for ( j = v27 + 2; ; j = (__int64 *)(v95 + 40) )
  {
    v95 = *j;
    if ( !*j )
      break;
    if ( *(_BYTE *)(v95 + 98) == 5 )
    {
      while ( 1 )
      {
        v119 = *(_QWORD *)(v95 + 40);
        if ( !v119 || *(_BYTE *)(v119 + 98) == 5 )
          break;
        *j = v119;
        j = (__int64 *)(v119 + 40);
        *(_QWORD *)(v95 + 40) = *(_QWORD *)(v119 + 40);
        *(_QWORD *)(v119 + 40) = v95;
      }
      break;
    }
  }
LABEL_228:
  sqlite3ExprDeleteGeneric(v16, a8);
  if ( v19 )
    exprListDeleteNN(v16, v19);
  result = sqlite3SrcListDelete(v16, v14);
  if ( v15 )
    return sqlite3DbFreeNN(v16, v15);
  return result;
}

```

## disassembly

```asm
0x180014750  mov     rax, rsp
0x180014753  mov     [rax+10h], rbx
0x180014757  mov     [rax+20h], r9
0x18001475b  mov     [rax+8], rcx
0x18001475f  push    rbp
0x180014760  push    rsi
0x180014761  push    rdi
0x180014762  push    r12
0x180014764  push    r13
0x180014766  push    r14
0x180014768  push    r15
0x18001476a  sub     rsp, 100h
0x180014771  xor     esi, esi
0x180014773  mov     rbx, r8
0x180014776  mov     r14, rdx
0x180014779  mov     rdi, rcx
0x18001477c  xor     edx, edx; Val
0x18001477e  lea     rcx, [rax-98h]; void *
0x180014785  mov     r12, r9
0x180014788  mov     r13d, esi
0x18001478b  lea     r8d, [rsi+60h]; Size
0x18001478f  call    memset_0
0x180014794  mov     rbp, [rdi]
0x180014797  mov     [rsp+138h+var_A0], rbp
0x18001479f  mov     [rsp+138h+var_D0], rsi
0x1800147a4  cmp     [rdi+30h], esi
0x1800147a7  jnz     loc_180015690
0x1800147ad  lea     r15d, [rsi+1]
0x1800147b1  cmp     [rdi+134h], r15b
0x1800147b8  jnz     short loc_1800147C8
0x1800147ba  cmp     [rsp+138h+arg_50], 2
0x1800147c2  jnz     loc_180015690
0x1800147c8  mov     rcx, rdi
0x1800147cb  call    sqlite3ReadSchema
0x1800147d0  xor     r10d, r10d
0x1800147d3  test    eax, eax
0x1800147d5  jnz     loc_180015690
0x1800147db  mov     rsi, [rsp+138h+arg_20]
0x1800147e3  mov     [rsp+138h+var_F0], rsi
0x1800147e8  test    rsi, rsi
0x1800147eb  jz      short loc_180014836
0x1800147ed  mov     ecx, r10d
0x1800147f0  cmp     ecx, [rsi]
0x1800147f2  jge     short loc_180014836
0x1800147f4  movsxd  rax, ecx
0x1800147f7  shl     rax, 5
0x1800147fb  test    byte ptr [rax+rsi+1Ch], 20h
0x180014800  jnz     short loc_180014807
0x180014802  add     ecx, r15d
0x180014805  jmp     short loc_1800147F0
0x180014807  mov     cl, [rax+rsi+18h]
0x18001480b  test    cl, cl
0x18001480d  jz      short loc_18001481B
0x18001480f  lea     r8, aLast_0; "LAST"
0x180014816  cmp     cl, 3
0x180014819  jnz     short loc_180014822
0x18001481b  lea     r8, aFirst; "FIRST"
0x180014822  lea     rdx, aUnsupportedUse; "unsupported use of NULLS %s"
0x180014829  mov     rcx, rdi
0x18001482c  call    sqlite3ErrorMsg
0x180014831  jmp     loc_180015698
0x180014836  mov     [rsp+138h+var_D8], r10
0x18001483b  test    r12, r12
0x18001483e  jz      loc_180014937
0x180014844  lea     r9, [rsp+138h+var_D0]
0x180014849  mov     r8, rbx
0x18001484c  mov     rdx, r14
0x18001484f  mov     rcx, rdi
0x180014852  call    sqlite3TwoPartName
0x180014857  mov     r15d, eax
0x18001485a  xor     eax, eax
0x18001485c  test    r15d, r15d
0x18001485f  js      loc_180015698
0x180014865  cmp     [rbp+0C5h], al
0x18001486b  jnz     short loc_18001489C
0x18001486d  mov     rdx, r12
0x180014870  mov     rcx, rdi
0x180014873  call    sqlite3SrcListLookup
0x180014878  mov     rcx, rax
0x18001487b  xor     eax, eax
0x18001487d  cmp     [rbx+8], eax
0x180014880  jnz     short loc_18001489C
0x180014882  test    rcx, rcx
0x180014885  jz      short loc_18001489C
0x180014887  mov     rax, [rbp+20h]
0x18001488b  mov     edx, 1
0x180014890  mov     rax, [rax+38h]
0x180014894  cmp     [rcx+60h], rax
0x180014898  cmovz   r15d, edx
0x18001489c  mov     rdx, [rsp+138h+var_D0]
0x1800148a1  lea     r9, aIndex; "index"
0x1800148a8  mov     [rsp+138h+var_118], rdx
0x1800148ad  lea     rcx, [rsp+138h+var_98]
0x1800148b5  mov     rdx, rdi
0x1800148b8  mov     r8d, r15d
0x1800148bb  call    sqlite3FixInit
0x1800148c0  mov     rdx, r12
0x1800148c3  lea     rcx, [rsp+138h+var_98]
0x1800148cb  call    sqlite3FixSrcList
0x1800148d0  lea     r8, [r12+8]
0x1800148d5  xor     edx, edx
0x1800148d7  mov     rcx, rdi
0x1800148da  call    sqlite3LocateTableItem
0x1800148df  xor     r10d, r10d
0x1800148e2  mov     [rsp+138h+var_C0], rax
0x1800148e7  mov     r14, rax
0x1800148ea  test    rax, rax
0x1800148ed  jz      loc_180015698
0x1800148f3  lea     r11d, [r10+1]
0x1800148f7  cmp     r15d, r11d
0x1800148fa  jnz     short loc_180014921
0x1800148fc  mov     rcx, [rbp+20h]
0x180014900  mov     rax, [rax+60h]
0x180014904  cmp     [rcx+38h], rax
0x180014908  jz      short loc_180014921
0x18001490a  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x180014911  mov     r8, [r14]
0x180014914  mov     rcx, rdi
0x180014917  call    sqlite3ErrorMsg
0x18001491c  jmp     loc_1800150F3
0x180014921  test    byte ptr [r14+30h], 80h
0x180014926  jz      short loc_18001497F
0x180014928  mov     rcx, r14
0x18001492b  call    sqlite3PrimaryKeyIndex
0x180014930  mov     [rsp+138h+var_D8], rax
0x180014935  jmp     short loc_18001497F
0x180014937  mov     r14, [rdi+160h]
0x18001493e  mov     [rsp+138h+var_C0], r14
0x180014943  test    r14, r14
0x180014946  jz      loc_180015698
0x18001494c  mov     rcx, [r14+60h]
0x180014950  mov     r15d, 0FFFF8000h
0x180014956  mov     r11d, 1
0x18001495c  test    rcx, rcx
0x18001495f  jz      short loc_18001497F
0x180014961  mov     rdx, [rbp+20h]
0x180014965  mov     r15d, r10d
0x180014968  cmp     [rdx+18h], rcx
0x18001496c  jz      short loc_18001497F
0x18001496e  add     r15d, r11d
0x180014971  movsxd  rax, r15d
0x180014974  shl     rax, 5
0x180014978  cmp     [rax+rdx+18h], rcx
0x18001497d  jnz     short loc_18001496E
0x18001497f  cmp     [r14], r10
0x180014982  jz      short loc_1800149F1
0x180014984  mov     r9, [r14]
0x180014987  lea     r8, aSqlite_0; "sqlite_"
0x18001498e  mov     edx, 7
0x180014993  lea     rbx, qword_1800ADCF0
0x18001499a  sub     edx, r11d
0x18001499d  cmp     [r9], r10b
0x1800149a0  jz      short loc_1800149BF
0x1800149a2  movzx   eax, byte ptr [r8]
0x1800149a6  movzx   ecx, byte ptr [r9]
0x1800149aa  mov     al, [rax+rbx]
0x1800149ad  cmp     [rcx+rbx], al
0x1800149b0  jnz     short loc_1800149BF
0x1800149b2  add     r9, r11
0x1800149b5  add     r8, r11
0x1800149b8  test    edx, edx
0x1800149ba  jg      short loc_18001499A
0x1800149bc  sub     edx, r11d
0x1800149bf  test    edx, edx
0x1800149c1  js      short loc_1800149D7
0x1800149c3  movzx   eax, byte ptr [r8]
0x1800149c7  movzx   ecx, byte ptr [rax+rbx]
0x1800149cb  movzx   eax, byte ptr [r9]
0x1800149cf  movzx   eax, byte ptr [rax+rbx]
0x1800149d3  cmp     eax, ecx
0x1800149d5  jnz     short loc_1800149F1
0x1800149d7  cmp     [rbp+0C5h], r10b
0x1800149de  jnz     short loc_1800149F1
0x1800149e0  test    r12, r12
0x1800149e3  jz      short loc_1800149F1
0x1800149e5  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x1800149ec  jmp     loc_180014911
0x1800149f1  mov     al, [r14+3Fh]
0x1800149f5  cmp     al, 2
0x1800149f7  jnz     short loc_180014A0D
0x1800149f9  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x180014a00  mov     rcx, rdi
0x180014a03  call    sqlite3ErrorMsg
0x180014a08  jmp     loc_1800150F3
0x180014a0d  cmp     al, r11b
0x180014a10  jnz     short loc_180014A1B
0x180014a12  lea     rdx, aVirtualTablesM; "virtual tables may not be indexed"
0x180014a19  jmp     short loc_180014A00
0x180014a1b  mov     rax, [rsp+138h+var_D0]
0x180014a20  mov     rbx, [rbp+20h]
0x180014a24  movsxd  r12, r15d
0x180014a27  shl     r12, 5
0x180014a2b  mov     [rsp+138h+var_C8], r12
0x180014a30  mov     [rsp+138h+var_E8], rbx
0x180014a35  test    rax, rax
0x180014a38  jz      loc_180014BC0
0x180014a3e  mov     r8d, [rax+8]
0x180014a42  mov     rcx, rbp
0x180014a45  mov     rdx, [rax]
0x180014a48  call    sqlite3DbStrNDup
0x180014a4d  mov     rcx, rax
0x180014a50  mov     r13, rax
0x180014a53  call    sqlite3Dequote
0x180014a58  xor     r10d, r10d
0x180014a5b  test    rcx, rcx
0x180014a5e  jz      loc_180014AEB
0x180014a64  mov     rbx, [rdi]
0x180014a67  lea     edx, [r10+1]
0x180014a6b  mov     eax, [rbx+30h]
0x180014a6e  and     eax, 10000001h
0x180014a73  cmp     rax, rdx
0x180014a76  jz      loc_180014B46
0x180014a7c  test    byte ptr [rbx+0C8h], 2
0x180014a83  jnz     loc_180014B46
0x180014a89  cmp     cs:byte_1800C6979, r10b
0x180014a90  jz      loc_180014B46
0x180014a96  cmp     [rbx+0C5h], r10b
0x180014a9d  jz      short loc_180014AF8
0x180014a9f  mov     rbx, [rbx+0D0h]
0x180014aa6  lea     rcx, aIndex; "index"
0x180014aad  mov     rdx, [rbx]
0x180014ab0  call    sqlite3_stricmp
0x180014ab5  test    eax, eax
0x180014ab7  jnz     short loc_180014ADC
0x180014ab9  mov     rdx, [rbx+8]
0x180014abd  mov     rcx, r13
0x180014ac0  call    sqlite3_stricmp
0x180014ac5  test    eax, eax
0x180014ac7  jnz     short loc_180014ADC
0x180014ac9  mov     rdx, [rbx+10h]
0x180014acd  mov     rcx, [r14]
0x180014ad0  call    sqlite3_stricmp
0x180014ad5  xor     r10d, r10d
0x180014ad8  test    eax, eax
0x180014ada  jz      short loc_180014B46
0x180014adc  lea     rdx, Src
0x180014ae3  mov     rcx, rdi
0x180014ae6  call    sqlite3ErrorMsg
0x180014aeb  mov     r12, [rsp+138h+arg_18]
0x180014af3  jmp     loc_1800150F3
0x180014af8  cmp     [rdi+1Eh], r10b
0x180014afc  jnz     short loc_180014B17
0x180014afe  mov     r8d, 7
0x180014b04  lea     rdx, aSqlite_0; "sqlite_"
0x180014b0b  call    sqlite3_strnicmp
0x180014b10  xor     r10d, r10d
0x180014b13  test    eax, eax
0x180014b15  jz      short loc_180014B32
0x180014b17  mov     rcx, rbx
0x180014b1a  call    sqlite3ReadOnlyShadowTables
0x180014b1f  test    eax, eax
0x180014b21  jz      short loc_180014B46
0x180014b23  mov     rdx, r13
0x180014b26  call    sqlite3ShadowTableName
0x180014b2b  xor     r10d, r10d
0x180014b2e  test    eax, eax
0x180014b30  jz      short loc_180014B46
0x180014b32  lea     rdx, aObjectNameRese; "object name reserved for internal use: "...
0x180014b39  mov     rcx, rdi
0x180014b3c  mov     r8, r13
0x180014b3f  call    sqlite3ErrorMsg
0x180014b44  jmp     short loc_180014AEB
0x180014b46  cmp     byte ptr [rdi+134h], 2
0x180014b4d  mov     rbx, [rsp+138h+var_E8]
0x180014b52  jnb     loc_180014C75
0x180014b58  cmp     [rbp+0C5h], r10b
0x180014b5f  jnz     short loc_180014B7E
0x180014b61  mov     r8, [r12+rbx]
0x180014b65  mov     rdx, r13
0x180014b68  mov     rcx, rbp
0x180014b6b  call    sqlite3FindTable
0x180014b70  test    rax, rax
0x180014b73  jz      short loc_180014B7E
0x180014b75  lea     rdx, aThereIsAlready; "there is already a table named %s"
0x180014b7c  jmp     short loc_180014B39
0x180014b7e  mov     r8, [r12+rbx]
0x180014b82  mov     rdx, r13
0x180014b85  mov     rcx, rbp
0x180014b88  call    sqlite3FindIndex
0x180014b8d  xor     r10d, r10d
0x180014b90  test    rax, rax
0x180014b93  jz      short loc_180014C06
0x180014b95  mov     rcx, rdi
0x180014b98  cmp     [rsp+138h+arg_48], r10d
0x180014ba0  jnz     short loc_180014BAB
0x180014ba2  lea     rdx, aIndexSAlreadyE; "index %s already exists"
0x180014ba9  jmp     short loc_180014B3C
0x180014bab  mov     edx, r15d
0x180014bae  call    sqlite3CodeVerifySchema
0x180014bb3  mov     rcx, rdi
0x180014bb6  call    sqlite3ForceNotReadOnly
0x180014bbb  jmp     loc_180014AEB
0x180014bc0  mov     rax, [r14+10h]
0x180014bc4  mov     r9d, r11d
0x180014bc7  jmp     short loc_180014BD0
0x180014bc9  mov     rax, [rax+28h]
0x180014bcd  add     r9d, r11d
0x180014bd0  test    rax, rax
0x180014bd3  jnz     short loc_180014BC9
0x180014bd5  mov     r8, [r14]
  ... truncated ...
```

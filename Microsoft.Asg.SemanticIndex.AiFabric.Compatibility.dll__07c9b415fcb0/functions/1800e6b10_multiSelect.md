# multiSelect

- ea: `0x1800e6b10`
- end: `0x1800e75ba`
- name: `multiSelect`
- size: `2730`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x18012c390`

## callees

- `0x1800c6fc0`
- `0x1800d7100`
- `0x1800d8770`
- `0x1800e6b10`
- `0x1800e75c0`
- `0x1800e7650`
- `0x1800f8d00`
- `0x180108a90`
- `0x18010f570`
- `0x18010fd20`
- `0x180110b50`
- `0x18011d0a0`
- `0x18011dc40`
- `0x180121fc0`
- `0x18012c390`
- `0x180130600`
- `0x180137a10`
- `0x180137a80`
- `0x180137af0`
- `0x180137bf0`
- `0x180138140`
- `0x1801418f0`
- `0x180141a50`
- `0x180142480`
- `0x180145480`
- `0x18015dbf0`
- `0x1801f7110`

## string_xrefs

- `0x1800e6d50`: `COMPOUND QUERY`
- `0x1800e6e4a`: `%s USING TEMP B-TREE`
- `0x1800e7288`: `%s USING TEMP B-TREE`

## pseudocode

```c
__int64 __fastcall multiSelect(__int64 *a1, unsigned __int8 *a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __int64 v4; // r14
  __int64 v5; // rdi
  __int128 *v6; // rbx
  __int64 v7; // rsi
  unsigned __int8 *v8; // r15
  __int128 v10; // xmm1
  char v11; // dl
  int v12; // r8d
  int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r13
  unsigned __int8 *v18; // rbx
  int v19; // edi
  __int64 v20; // rax
  unsigned __int8 *v21; // rax
  const char *v23; // rax
  __int128 *v24; // rdx
  unsigned int v25; // ecx
  unsigned int v26; // edi
  unsigned __int8 *v27; // rcx
  unsigned __int8 *i; // rax
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rbx
  const char *v32; // rax
  unsigned int v33; // r13d
  __int16 v34; // ax
  __int64 v35; // rdx
  unsigned int v36; // esi
  unsigned int v37; // r13d
  char v38; // al
  unsigned int v39; // ebx
  unsigned __int8 v40; // al
  __int64 v41; // rcx
  __int64 v42; // r8
  unsigned int v43; // ebx
  __int64 v44; // r8
  unsigned int v45; // eax
  int v46; // ecx
  unsigned int v47; // eax
  __int64 v48; // r10
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int16 v51; // ax
  __int64 v52; // rcx
  __int16 v53; // cx
  __int16 v54; // dx
  unsigned __int64 v55; // rax
  __int16 v56; // dx
  unsigned __int64 v57; // rax
  __int16 v58; // cx
  unsigned int v59; // r13d
  unsigned __int8 *v60; // rcx
  unsigned __int8 *j; // rax
  char v62; // cl
  __int64 v63; // rbx
  const char *v64; // rax
  bool v65; // zf
  __int64 v66; // rdx
  unsigned int v67; // esi
  unsigned int v68; // edi
  unsigned int v69; // ebx
  __int64 v70; // r13
  __int64 v71; // rax
  __int64 v72; // rbx
  __int64 *v73; // rdi
  unsigned int v74; // esi
  __int64 v75; // rbx
  __int64 v76; // r13
  __int64 v77; // rdx
  __int64 v78; // rax
  _DWORD *v79; // rdx
  __int64 v80; // rsi
  int *v81; // rdi
  __int64 v82; // rdx
  __int64 *v83; // rax
  int v84; // ecx
  __int64 v85; // rax
  __int64 v86; // rdx
  __int128 *v87; // rdx
  unsigned int v88; // [rsp+40h] [rbp-99h]
  int v89; // [rsp+44h] [rbp-95h] BYREF
  __int64 v90; // [rsp+48h] [rbp-91h]
  __int128 *v91; // [rsp+50h] [rbp-89h]
  __int64 v92; // [rsp+58h] [rbp-81h]
  unsigned int v93; // [rsp+60h] [rbp-79h]
  __int64 v94; // [rsp+68h] [rbp-71h]
  __int64 v95; // [rsp+70h] [rbp-69h]
  __int64 v96; // [rsp+78h] [rbp-61h]
  __int128 v97; // [rsp+80h] [rbp-59h] BYREF
  __int128 v98; // [rsp+90h] [rbp-49h]
  __int64 v99; // [rsp+A0h] [rbp-39h]
  _BYTE v100[4]; // [rsp+A8h] [rbp-31h] BYREF
  unsigned int v101; // [rsp+ACh] [rbp-2Dh]
  __int64 v102; // [rsp+B0h] [rbp-29h]
  int v103; // [rsp+B8h] [rbp-21h]
  __int64 v104; // [rsp+C0h] [rbp-19h]
  _BYTE v105[4]; // [rsp+D0h] [rbp-9h] BYREF
  unsigned int v106; // [rsp+D4h] [rbp-5h]
  __int64 v107; // [rsp+D8h] [rbp-1h]
  int v108; // [rsp+E0h] [rbp+7h]
  __int64 v109; // [rsp+E8h] [rbp+Fh]

  v3 = *a3;
  v4 = a1[2];
  v5 = *a1;
  v6 = a3;
  v7 = *((_QWORD *)a2 + 10);
  v8 = a2;
  v91 = a3;
  v92 = 0;
  v90 = v5;
  v95 = v4;
  v10 = a3[1];
  v97 = v3;
  v99 = *((_QWORD *)a3 + 4);
  v98 = v10;
  if ( !v4 )
  {
    if ( !a1[21] && (*(_BYTE *)(v5 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v4 = sqlite3VdbeCreate(a1);
    v95 = v4;
  }
  v11 = v97;
  if ( (_BYTE)v97 == 12 )
  {
    v12 = DWORD1(v97);
    v13 = **((_DWORD **)v8 + 4);
    v14 = *(int *)(v4 + 144);
    if ( *(_DWORD *)(v4 + 148) > (int)v14 )
    {
      *(_DWORD *)(v4 + 144) = v14 + 1;
      v15 = 3 * v14;
      v16 = *(_QWORD *)(v4 + 136);
      *(_DWORD *)(v16 + 8 * v15) = 118;
      *(_DWORD *)(v16 + 8 * v15 + 4) = v12;
      *(_DWORD *)(v16 + 8 * v15 + 8) = v13;
      *(_DWORD *)(v16 + 8 * v15 + 12) = 0;
      *(_QWORD *)(v16 + 8 * v15 + 16) = 0;
    }
    else
    {
      growOp3(v4, 118, DWORD1(v97), v13, 0);
    }
    v11 = 14;
    LOBYTE(v97) = 14;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x400) != 0 )
  {
    v17 = *((_QWORD *)v8 + 12);
    v18 = v8;
    v19 = 1;
    if ( !*((_QWORD *)v8 + 14) )
    {
      while ( 1 )
      {
        v20 = *((_QWORD *)v18 + 10);
        if ( !v20 )
          break;
        v19 += v17 == 0;
        v18 = (unsigned __int8 *)*((_QWORD *)v18 + 10);
        if ( *(_QWORD *)(v20 + 112) )
          goto LABEL_15;
      }
      v23 = "S";
      if ( v19 == 1 )
        v23 = (const char *)&byte_1802990D8;
      sqlite3VdbeExplain(a1, 0, "SCAN %d CONSTANT ROW%s", v19, v23);
      do
      {
        selectInnerLoop((_DWORD)a1, (_DWORD)v18, -1, 0, 0, (__int64)&v97, 1, 1);
        if ( v17 )
          break;
        *((_WORD *)v18 + 1) = v19;
        v18 = (unsigned __int8 *)*((_QWORD *)v18 + 11);
      }
      while ( v18 );
      v24 = v91;
      v25 = 0;
      *((_DWORD *)v91 + 3) = HIDWORD(v97);
      *((_DWORD *)v24 + 4) = v98;
      return v25;
    }
LABEL_15:
    v6 = v91;
    v5 = v90;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x2000) == 0 )
  {
LABEL_20:
    if ( *((_QWORD *)v8 + 9) )
      return multiSelectOrderBy(a1, v8, v6);
    if ( !*(_QWORD *)(v7 + 80) )
    {
      sqlite3VdbeExplain(a1, 1, "COMPOUND QUERY");
      sqlite3VdbeExplain(a1, 1, "LEFT-MOST SUBQUERY");
      v11 = v97;
    }
    if ( *v8 == 134 )
      goto LABEL_80;
    if ( *v8 != 135 )
    {
      if ( *v8 != 136 )
      {
        v26 = *((_DWORD *)a1 + 13);
        *((_DWORD *)a1 + 13) = v26 + 2;
        *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp2(v4, 118, v26, 0);
        v27 = v8;
        for ( i = (unsigned __int8 *)*((_QWORD *)v8 + 11); i; i = (unsigned __int8 *)*((_QWORD *)i + 11) )
          v27 = i;
        *((_DWORD *)v27 + 1) |= 0x20u;
        v100[0] = 1;
        v102 = 0;
        v104 = 0;
        v103 = 0;
        v101 = v26;
        v88 = sqlite3Select(a1, v7, v100);
        v25 = v88;
        if ( v88 )
          goto LABEL_129;
        v29 = sqlite3VdbeAddOp2(v4, 118, v26 + 1, 0);
        v30 = *v8;
        *((_DWORD *)v8 + 6) = v29;
        *((_QWORD *)v8 + 10) = 0;
        v31 = *((_QWORD *)v8 + 12);
        *((_QWORD *)v8 + 12) = 0;
        v101 = v26 + 1;
        v32 = (const char *)sqlite3SelectOpName(v30);
        sqlite3VdbeExplain(a1, 1, "%s USING TEMP B-TREE", v32);
        v33 = sqlite3Select(a1, v8, v100);
        v88 = v33;
        v92 = *((_QWORD *)v8 + 10);
        *((_QWORD *)v8 + 10) = v7;
        v34 = *(_WORD *)(v7 + 2);
        if ( *((__int16 *)v8 + 1) > v34 )
          *((_WORD *)v8 + 1) = v34;
        v35 = *((_QWORD *)v8 + 12);
        if ( v35 )
          sqlite3ExprDeleteNN(v90, v35);
        *((_QWORD *)v8 + 12) = v31;
        if ( v33 )
          goto LABEL_94;
        v36 = *((_DWORD *)a1 + 17) - 1;
        v37 = *((_DWORD *)a1 + 17) - 2;
        *((_DWORD *)a1 + 17) = v37;
        computeLimitRegisters(a1, v8, v36);
        sqlite3VdbeAddOp2(v4, 36, v26, v36);
        v38 = *((_BYTE *)a1 + 31);
        if ( v38 )
        {
          v40 = v38 - 1;
          *((_BYTE *)a1 + 31) = v40;
          v39 = *((_DWORD *)a1 + v40 + 56);
        }
        else
        {
          v39 = ++*((_DWORD *)a1 + 14);
        }
        v89 = sqlite3VdbeAddOp2(v4, 134, v26, v39);
        sqlite3VdbeAddOp4Int(v4, 28, v26 + 1, v37, v39, 0);
        if ( v39 )
        {
          v41 = *((unsigned __int8 *)a1 + 31);
          if ( (unsigned __int8)v41 < 8u )
          {
            *((_DWORD *)a1 + v41 + 56) = v39;
            ++*((_BYTE *)a1 + 31);
          }
        }
        selectInnerLoop((_DWORD)a1, (_DWORD)v8, v26, 0, 0, (__int64)&v97, v36 - 1, v36);
        sqlite3VdbeResolveLabel(v4, v37);
        sqlite3VdbeAddOp2(v4, 39, v26, (unsigned int)v89);
        sqlite3VdbeResolveLabel(v4, v36);
        sqlite3VdbeAddOp2(v4, 122, v26 + 1, 0);
        v42 = v26;
LABEL_93:
        sqlite3VdbeAddOp2(v4, 122, v42, 0);
LABEL_94:
        if ( !*((_QWORD *)v8 + 11) )
          sqlite3VdbeExplainPop(a1);
        goto LABEL_96;
      }
LABEL_80:
      if ( v11 == 1 )
      {
        v59 = DWORD1(v97);
      }
      else
      {
        v59 = *((_DWORD *)a1 + 13);
        *((_DWORD *)a1 + 13) = v59 + 1;
        *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp2(v4, 118, v59, 0);
        v60 = v8;
        for ( j = (unsigned __int8 *)*((_QWORD *)v8 + 11); j; j = (unsigned __int8 *)*((_QWORD *)j + 11) )
          v60 = j;
        *((_DWORD *)v60 + 1) |= 0x20u;
      }
      v105[0] = 1;
      v107 = 0;
      v109 = 0;
      v108 = 0;
      v106 = v59;
      v88 = sqlite3Select(a1, v7, v105);
      v25 = v88;
      if ( v88 )
        goto LABEL_129;
      v62 = *v8;
      *((_QWORD *)v8 + 10) = 0;
      v63 = *((_QWORD *)v8 + 12);
      *((_QWORD *)v8 + 12) = 0;
      v105[0] = (v62 == -120) + 1;
      v64 = (const char *)((__int64 (*)(void))sqlite3SelectOpName)();
      sqlite3VdbeExplain(a1, 1, "%s USING TEMP B-TREE", v64);
      v88 = sqlite3Select(a1, v8, v105);
      v92 = *((_QWORD *)v8 + 10);
      v65 = *v8 == 0x86;
      *((_QWORD *)v8 + 10) = v7;
      *((_QWORD *)v8 + 9) = 0;
      if ( v65 )
        *((_WORD *)v8 + 1) = sqlite3LogEstAdd(*((unsigned __int16 *)v8 + 1), *(unsigned __int16 *)(v7 + 2));
      v66 = *((_QWORD *)v8 + 12);
      if ( v66 )
        sqlite3ExprDeleteNN(v5, v66);
      *((_QWORD *)v8 + 12) = v63;
      v65 = (_BYTE)v97 == 1;
      *((_QWORD *)v8 + 1) = 0;
      if ( v65 || *(_BYTE *)(v5 + 103) )
        goto LABEL_94;
      v67 = *((_DWORD *)a1 + 17) - 1;
      v68 = *((_DWORD *)a1 + 17) - 2;
      *((_DWORD *)a1 + 17) = v68;
      computeLimitRegisters(a1, v8, v67);
      sqlite3VdbeAddOp2(v4, 36, v59, v67);
      v69 = *(_DWORD *)(v4 + 144);
      selectInnerLoop((_DWORD)a1, (_DWORD)v8, v59, 0, 0, (__int64)&v97, v67 - 1, v67);
      sqlite3VdbeResolveLabel(v4, v68);
      sqlite3VdbeAddOp2(v4, 39, v59, v69);
      sqlite3VdbeResolveLabel(v4, v67);
      v42 = v59;
      goto LABEL_93;
    }
    *(_DWORD *)(v7 + 8) = *((_DWORD *)v8 + 2);
    *(_DWORD *)(v7 + 12) = *((_DWORD *)v8 + 3);
    v43 = 0;
    *(_QWORD *)(v7 + 96) = *((_QWORD *)v8 + 12);
    v89 = 0;
    v88 = sqlite3Select(a1, v7, &v97);
    v25 = v88;
    *(_QWORD *)(v7 + 96) = 0;
    if ( v88 )
      goto LABEL_129;
    *((_QWORD *)v8 + 10) = 0;
    v44 = *(unsigned int *)(v7 + 8);
    *((_DWORD *)v8 + 2) = v44;
    *((_DWORD *)v8 + 3) = *(_DWORD *)(v7 + 12);
    if ( (_DWORD)v44 )
    {
      v45 = sqlite3VdbeAddOp1(v4, 17, v44);
      v46 = *((_DWORD *)v8 + 3);
      v43 = v45;
      if ( v46 )
        sqlite3VdbeAddOp3(v4, 160, *((_DWORD *)v8 + 2), v46 + 1, v46);
    }
    sqlite3VdbeExplain(a1, 1, "UNION ALL");
    v47 = sqlite3Select(a1, v8, &v97);
    v48 = *((_QWORD *)v8 + 10);
    v49 = *((unsigned __int16 *)v8 + 1);
    *((_QWORD *)v8 + 10) = v7;
    v50 = *(unsigned __int16 *)(v7 + 2);
    v88 = v47;
    v92 = v48;
    v51 = sqlite3LogEstAdd(v49, v50);
    v52 = *((_QWORD *)v8 + 12);
    *((_WORD *)v8 + 1) = v51;
    if ( !v52 || !(unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v52 + 16), &v89) || v89 <= 0 )
    {
LABEL_78:
      if ( v43 )
        sqlite3VdbeJumpHere(v4, v43);
      goto LABEL_94;
    }
    v53 = 40;
    v54 = 40;
    v55 = v89;
    if ( (unsigned __int64)v89 >= 8 )
    {
      if ( (unsigned __int64)v89 > 0xFF )
      {
        do
        {
          v54 += 40;
          v55 >>= 4;
        }
        while ( v55 > 0xFF );
      }
      for ( ; v55 > 0xF; v55 >>= 1 )
        v54 += 10;
    }
    else
    {
      if ( (unsigned __int64)v89 < 2 )
      {
        v56 = 0;
        goto LABEL_66;
      }
      do
      {
        v54 -= 10;
        v55 *= 2LL;
      }
      while ( v55 < 8 );
    }
    v56 = *((_WORD *)qword_1803380F8 + (v55 & 7)) + v54 - 10;
LABEL_66:
    if ( *((__int16 *)v8 + 1) <= v56 )
      goto LABEL_78;
    v57 = v89;
    if ( (unsigned __int64)v89 >= 8 )
    {
      if ( (unsigned __int64)v89 > 0xFF )
      {
        do
        {
          v53 += 40;
          v57 >>= 4;
        }
        while ( v57 > 0xFF );
      }
      for ( ; v57 > 0xF; v57 >>= 1 )
        v53 += 10;
    }
    else
    {
      if ( (unsigned __int64)v89 < 2 )
      {
        v58 = 0;
LABEL_77:
        *((_WORD *)v8 + 1) = v58;
        goto LABEL_78;
      }
      do
      {
        v53 -= 10;
        v57 *= 2LL;
      }
      while ( v57 < 8 );
    }
    v58 = *((_WORD *)qword_1803380F8 + (v57 & 7)) + v53 - 10;
    goto LABEL_77;
  }
  v21 = v8;
  while ( (*((_DWORD *)v21 + 1) & 0x2000) != 0 )
  {
    v21 = (unsigned __int8 *)*((_QWORD *)v21 + 10);
    if ( !v21 )
      goto LABEL_20;
  }
  generateWithRecursiveQuery(a1, v8, &v97);
  v88 = 0;
LABEL_96:
  if ( !*((_DWORD *)a1 + 12) && (v8[4] & 0x20) != 0 )
  {
    v93 = **((_DWORD **)v8 + 4);
    v70 = (int)v93;
    v71 = sqlite3KeyInfoAlloc(v90, v93, 1);
    v96 = v71;
    v72 = v71;
    if ( !v71 )
    {
      v25 = 7;
      v88 = 7;
      goto LABEL_129;
    }
    v94 = v70;
    v73 = (__int64 *)(v71 + 32);
    v74 = 0;
    if ( (int)v70 > 0 )
    {
      v75 = v90;
      v76 = 0;
      while ( 1 )
      {
        v77 = *((_QWORD *)v8 + 10);
        if ( !v77 )
          break;
        v78 = multiSelectCollSeq(a1, v77, v74);
        if ( !v78 )
          goto LABEL_106;
LABEL_108:
        *v73 = v78;
        if ( !v78 )
          *v73 = *(_QWORD *)(v75 + 16);
        ++v74;
        v76 += 8;
        ++v73;
        if ( !--v94 )
        {
          v72 = v96;
          v4 = v95;
          LODWORD(v70) = v93;
          goto LABEL_112;
        }
      }
      v78 = 0;
LABEL_106:
      v79 = (_DWORD *)*((_QWORD *)v8 + 4);
      if ( (signed int)v74 < *v79 )
        v78 = sqlite3ExprCollSeq(a1, *(_QWORD *)&v79[v76 + 2]);
      goto LABEL_108;
    }
    do
    {
LABEL_112:
      v80 = 0;
      v81 = (int *)(v8 + 20);
      do
      {
        v82 = *v81;
        if ( (int)v82 < 0 )
          break;
        v83 = *(_BYTE *)(*(_QWORD *)v4 + 103LL) ? &qword_1803DCAC0 : (__int64 *)(*(_QWORD *)(v4 + 136) + 24 * v82);
        *((_DWORD *)v83 + 2) = v70;
        v84 = (*(_DWORD *)v72)++;
        if ( *(_BYTE *)(*(_QWORD *)v4 + 103LL) )
        {
          if ( !*(_QWORD *)(*(_QWORD *)v4 + 760LL) )
          {
            *(_DWORD *)v72 = v84;
            if ( !v84 )
              sqlite3DbNNFreeNN(*(_QWORD *)(v72 + 16), v72);
          }
        }
        else
        {
          v85 = *(_QWORD *)(v4 + 136);
          v65 = *(_BYTE *)(v85 + 24 * v82 + 1) == 0;
          v86 = v85 + 24 * v82;
          if ( v65 )
          {
            *(_QWORD *)(v86 + 16) = v72;
            *(_BYTE *)(v86 + 1) = -8;
          }
          else
          {
            _mm_lfence();
            vdbeChangeP4Full(v4, v86, v72, 4294967288LL);
          }
        }
        *v81 = -1;
        ++v80;
        ++v81;
      }
      while ( v80 < 2 );
      v8 = (unsigned __int8 *)*((_QWORD *)v8 + 10);
    }
    while ( v8 );
    v65 = (*(_DWORD *)v72)-- == 1;
    if ( v65 )
      sqlite3DbNNFreeNN(*(_QWORD *)(v72 + 16), v72);
  }
  v25 = v88;
LABEL_129:
  v87 = v91;
  *((_DWORD *)v91 + 3) = HIDWORD(v97);
  *((_DWORD *)v87 + 4) = v98;
  if ( v92 )
  {
    sqlite3ParserAddCleanup(a1, sqlite3SelectDeleteGeneric);
    return v88;
  }
  return v25;
}

```

## disassembly

```asm
0x1800e6b10  mov     [rsp-8+arg_18], rbx
0x1800e6b15  push    rbp
0x1800e6b16  push    rsi
0x1800e6b17  push    rdi
0x1800e6b18  push    r12
0x1800e6b1a  push    r13
0x1800e6b1c  push    r14
0x1800e6b1e  push    r15
0x1800e6b20  lea     rbp, [rsp-27h]
0x1800e6b25  sub     rsp, 100h
0x1800e6b2c  mov     rax, cs:__security_cookie
0x1800e6b33  xor     rax, rsp
0x1800e6b36  mov     [rbp+57h+var_38], rax
0x1800e6b3a  movups  xmm0, xmmword ptr [r8]
0x1800e6b3e  mov     r14, [rcx+10h]
0x1800e6b42  xor     r13d, r13d
0x1800e6b45  mov     rdi, [rcx]
0x1800e6b48  mov     rbx, r8
0x1800e6b4b  mov     rsi, [rdx+50h]
0x1800e6b4f  mov     r15, rdx
0x1800e6b52  mov     [rsp+130h+var_E0], rbx
0x1800e6b57  mov     r12, rcx
0x1800e6b5a  mov     [rsp+130h+var_D8], r13
0x1800e6b5f  mov     [rsp+130h+var_E8], rdi
0x1800e6b64  mov     [rbp+57h+var_C0], r14
0x1800e6b68  movups  xmm1, xmmword ptr [r8+10h]
0x1800e6b6d  movups  [rbp+57h+var_B0], xmm0
0x1800e6b71  movsd   xmm0, qword ptr [r8+20h]
0x1800e6b77  movsd   [rbp+57h+var_90], xmm0
0x1800e6b7c  movups  [rbp+57h+var_A0], xmm1
0x1800e6b80  test    r14, r14
0x1800e6b83  jnz     short loc_1800E6BA4
0x1800e6b85  cmp     [rcx+0A8h], r13
0x1800e6b8c  jnz     short loc_1800E6B98
0x1800e6b8e  test    byte ptr [rdi+60h], 8
0x1800e6b92  jnz     short loc_1800E6B98
0x1800e6b94  mov     byte ptr [rcx+23h], 1
0x1800e6b98  call    sqlite3VdbeCreate
0x1800e6b9d  mov     r14, rax
0x1800e6ba0  mov     [rbp+57h+var_C0], rax
0x1800e6ba4  movzx   edx, byte ptr [rbp+57h+var_B0]
0x1800e6ba8  cmp     dl, 0Ch
0x1800e6bab  jnz     short loc_1800E6C12
0x1800e6bad  mov     rcx, [r15+20h]
0x1800e6bb1  mov     r8d, dword ptr [rbp+57h+var_B0+4]
0x1800e6bb5  mov     edx, [rcx]
0x1800e6bb7  movsxd  rcx, dword ptr [r14+90h]
0x1800e6bbe  cmp     [r14+94h], ecx
0x1800e6bc5  jg      short loc_1800E6BDE
0x1800e6bc7  mov     r9d, edx
0x1800e6bca  mov     dword ptr [rsp+130h+var_110], r13d
0x1800e6bcf  mov     edx, 76h ; 'v'
0x1800e6bd4  mov     rcx, r14
0x1800e6bd7  call    growOp3
0x1800e6bdc  jmp     short loc_1800E6C0D
0x1800e6bde  lea     eax, [rcx+1]
0x1800e6be1  mov     [r14+90h], eax
0x1800e6be8  lea     rcx, [rcx+rcx*2]
0x1800e6bec  mov     rax, [r14+88h]
0x1800e6bf3  mov     dword ptr [rax+rcx*8], 76h ; 'v'
0x1800e6bfa  mov     [rax+rcx*8+4], r8d
0x1800e6bff  mov     [rax+rcx*8+8], edx
0x1800e6c03  mov     [rax+rcx*8+0Ch], r13d
0x1800e6c08  mov     [rax+rcx*8+10h], r13
0x1800e6c0d  mov     dl, 0Eh
0x1800e6c0f  mov     byte ptr [rbp+57h+var_B0], dl
0x1800e6c12  test    dword ptr [r15+4], 400h
0x1800e6c1a  jz      short loc_1800E6C59
0x1800e6c1c  mov     r13, [r15+60h]
0x1800e6c20  xor     ecx, ecx
0x1800e6c22  test    r13, r13
0x1800e6c25  mov     rbx, r15
0x1800e6c28  mov     edi, 1
0x1800e6c2d  setz    cl
0x1800e6c30  cmp     qword ptr [r15+70h], 0
0x1800e6c35  jnz     short loc_1800E6C4C
0x1800e6c37  mov     rax, [rbx+50h]
0x1800e6c3b  test    rax, rax
0x1800e6c3e  jz      short loc_1800E6CA4
0x1800e6c40  add     edi, ecx
0x1800e6c42  mov     rbx, rax
0x1800e6c45  cmp     qword ptr [rax+70h], 0
0x1800e6c4a  jz      short loc_1800E6C37
0x1800e6c4c  mov     rbx, [rsp+130h+var_E0]
0x1800e6c51  xor     r13d, r13d
0x1800e6c54  mov     rdi, [rsp+130h+var_E8]
0x1800e6c59  test    dword ptr [r15+4], 2000h
0x1800e6c61  jz      short loc_1800E6C86
0x1800e6c63  mov     rax, r15
0x1800e6c66  nop     word ptr [rax+rax+00000000h]
0x1800e6c70  test    dword ptr [rax+4], 2000h
0x1800e6c77  jz      loc_1800E6D30
0x1800e6c7d  mov     rax, [rax+50h]
0x1800e6c81  test    rax, rax
0x1800e6c84  jnz     short loc_1800E6C70
0x1800e6c86  cmp     qword ptr [r15+48h], 0
0x1800e6c8b  jz      loc_1800E6D49
0x1800e6c91  mov     r8, rbx
0x1800e6c94  mov     rdx, r15
0x1800e6c97  mov     rcx, r12
0x1800e6c9a  call    multiSelectOrderBy
0x1800e6c9f  jmp     loc_1800E7593
0x1800e6ca4  lea     rcx, byte_1802990D8
0x1800e6cab  cmp     edi, 1
0x1800e6cae  lea     rax, aS_0; "S"
0x1800e6cb5  mov     r9d, edi
0x1800e6cb8  cmovz   rax, rcx
0x1800e6cbc  lea     r8, aScanDConstantR; "SCAN %d CONSTANT ROW%s"
0x1800e6cc3  xor     edx, edx
0x1800e6cc5  mov     [rsp+130h+var_110], rax
0x1800e6cca  mov     rcx, r12
0x1800e6ccd  call    sqlite3VdbeExplain
0x1800e6cd2  xor     esi, esi
0x1800e6cd4  mov     [rsp+130h+var_F8], 1
0x1800e6cdc  lea     rax, [rbp+57h+var_B0]
0x1800e6ce0  mov     [rsp+130h+var_100], 1
0x1800e6ce8  xor     r9d, r9d
0x1800e6ceb  mov     [rsp+130h+var_108], rax
0x1800e6cf0  mov     r8d, 0FFFFFFFFh
0x1800e6cf6  mov     rdx, rbx
0x1800e6cf9  mov     [rsp+130h+var_110], rsi
0x1800e6cfe  mov     rcx, r12
0x1800e6d01  call    selectInnerLoop
0x1800e6d06  test    r13, r13
0x1800e6d09  jnz     short loc_1800E6D18
0x1800e6d0b  mov     [rbx+2], di
0x1800e6d0f  mov     rbx, [rbx+58h]
0x1800e6d13  test    rbx, rbx
0x1800e6d16  jnz     short loc_1800E6CD4
0x1800e6d18  mov     rdx, [rsp+130h+var_E0]
0x1800e6d1d  mov     ecx, esi
0x1800e6d1f  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x1800e6d22  mov     [rdx+0Ch], eax
0x1800e6d25  mov     eax, dword ptr [rbp+57h+var_A0]
0x1800e6d28  mov     [rdx+10h], eax
0x1800e6d2b  jmp     loc_1800E7591
0x1800e6d30  lea     r8, [rbp+57h+var_B0]
0x1800e6d34  mov     rdx, r15
0x1800e6d37  mov     rcx, r12
0x1800e6d3a  call    generateWithRecursiveQuery
0x1800e6d3f  mov     [rsp+130h+var_F0], r13d
0x1800e6d44  jmp     loc_1800E73B2
0x1800e6d49  cmp     qword ptr [rsi+50h], 0
0x1800e6d4e  jnz     short loc_1800E6D7C
0x1800e6d50  lea     r8, aCompoundQuery; "COMPOUND QUERY"
0x1800e6d57  mov     edx, 1
0x1800e6d5c  mov     rcx, r12
0x1800e6d5f  call    sqlite3VdbeExplain
0x1800e6d64  lea     r8, aLeftMostSubque; "LEFT-MOST SUBQUERY"
0x1800e6d6b  mov     edx, 1
0x1800e6d70  mov     rcx, r12
0x1800e6d73  call    sqlite3VdbeExplain
0x1800e6d78  movzx   edx, byte ptr [rbp+57h+var_B0]
0x1800e6d7c  movzx   ecx, byte ptr [r15]
0x1800e6d80  sub     ecx, 86h
0x1800e6d86  jz      loc_1800E71E5
0x1800e6d8c  sub     ecx, 1
0x1800e6d8f  jz      loc_1800E6FCF
0x1800e6d95  cmp     ecx, 1
0x1800e6d98  jz      loc_1800E71E5
0x1800e6d9e  mov     edi, [r12+34h]
0x1800e6da3  xor     r9d, r9d
0x1800e6da6  mov     r8d, edi
0x1800e6da9  mov     edx, 76h ; 'v'
0x1800e6dae  mov     rcx, r14
0x1800e6db1  lea     eax, [rdi+2]
0x1800e6db4  mov     [r12+34h], eax
0x1800e6db9  lea     r13d, [rdi+1]
0x1800e6dbd  call    sqlite3VdbeAddOp2
0x1800e6dc2  mov     [r15+14h], eax
0x1800e6dc6  mov     rcx, r15
0x1800e6dc9  mov     rax, [r15+58h]
0x1800e6dcd  test    rax, rax
0x1800e6dd0  jz      short loc_1800E6DDE
0x1800e6dd2  mov     rcx, rax
0x1800e6dd5  mov     rax, [rax+58h]
0x1800e6dd9  test    rax, rax
0x1800e6ddc  jnz     short loc_1800E6DD2
0x1800e6dde  or      dword ptr [rcx+4], 20h
0x1800e6de2  lea     r8, [rbp+57h+var_88]
0x1800e6de6  xor     ebx, ebx
0x1800e6de8  mov     [rbp+57h+var_88], 1
0x1800e6dec  mov     rcx, r12
0x1800e6def  mov     [rbp+57h+var_80], rbx
0x1800e6df3  mov     rdx, rsi
0x1800e6df6  mov     [rbp+57h+var_70], rbx
0x1800e6dfa  mov     [rbp+57h+var_78], ebx
0x1800e6dfd  mov     [rbp+57h+var_84], edi
0x1800e6e00  call    sqlite3Select
0x1800e6e05  mov     [rsp+130h+var_F0], eax
0x1800e6e09  mov     ecx, eax
0x1800e6e0b  test    eax, eax
0x1800e6e0d  jnz     loc_1800E7560
0x1800e6e13  xor     r9d, r9d
0x1800e6e16  mov     r8d, r13d
0x1800e6e19  mov     edx, 76h ; 'v'
0x1800e6e1e  mov     rcx, r14
0x1800e6e21  call    sqlite3VdbeAddOp2
0x1800e6e26  movzx   ecx, byte ptr [r15]
0x1800e6e2a  mov     [r15+18h], eax
0x1800e6e2e  mov     [r15+50h], rbx
0x1800e6e32  mov     rbx, [r15+60h]
0x1800e6e36  mov     qword ptr [r15+60h], 0
0x1800e6e3e  mov     [rbp+57h+var_84], r13d
0x1800e6e42  call    sqlite3SelectOpName
0x1800e6e47  mov     r9, rax
0x1800e6e4a  lea     r8, aSUsingTempBTre; "%s USING TEMP B-TREE"
0x1800e6e51  mov     rcx, r12
0x1800e6e54  mov     edx, 1
0x1800e6e59  call    sqlite3VdbeExplain
0x1800e6e5e  lea     r8, [rbp+57h+var_88]
0x1800e6e62  mov     rdx, r15
0x1800e6e65  mov     rcx, r12
0x1800e6e68  call    sqlite3Select
0x1800e6e6d  mov     r13d, eax
0x1800e6e70  mov     [rsp+130h+var_F0], eax
0x1800e6e74  mov     rax, [r15+50h]
0x1800e6e78  mov     [rsp+130h+var_D8], rax
0x1800e6e7d  mov     [r15+50h], rsi
0x1800e6e81  movzx   eax, word ptr [rsi+2]
0x1800e6e85  cmp     [r15+2], ax
0x1800e6e8a  jle     short loc_1800E6E91
0x1800e6e8c  mov     [r15+2], ax
0x1800e6e91  mov     rdx, [r15+60h]
0x1800e6e95  test    rdx, rdx
0x1800e6e98  jz      short loc_1800E6EA4
0x1800e6e9a  mov     rcx, [rsp+130h+var_E8]
0x1800e6e9f  call    sqlite3ExprDeleteNN
0x1800e6ea4  mov     [r15+60h], rbx
0x1800e6ea8  test    r13d, r13d
0x1800e6eab  jnz     loc_1800E73A3
0x1800e6eb1  mov     esi, [r12+44h]
0x1800e6eb6  mov     rdx, r15
0x1800e6eb9  dec     esi
0x1800e6ebb  mov     rcx, r12
0x1800e6ebe  mov     r8d, esi
0x1800e6ec1  lea     r13d, [rsi-1]
0x1800e6ec5  mov     [r12+44h], r13d
0x1800e6eca  call    computeLimitRegisters
0x1800e6ecf  mov     r9d, esi
0x1800e6ed2  mov     r8d, edi
0x1800e6ed5  mov     edx, 24h ; '$'
0x1800e6eda  mov     rcx, r14
0x1800e6edd  call    sqlite3VdbeAddOp2
0x1800e6ee2  movzx   eax, byte ptr [r12+1Fh]
0x1800e6ee8  test    al, al
0x1800e6eea  jnz     short loc_1800E6EF8
0x1800e6eec  inc     dword ptr [r12+38h]
0x1800e6ef1  mov     ebx, [r12+38h]
0x1800e6ef6  jmp     short loc_1800E6F0A
0x1800e6ef8  dec     al
0x1800e6efa  movzx   eax, al
0x1800e6efd  mov     [r12+1Fh], al
0x1800e6f02  mov     ebx, [r12+rax*4+0E0h]
0x1800e6f0a  mov     r9d, ebx
0x1800e6f0d  mov     r8d, edi
0x1800e6f10  mov     edx, 86h
0x1800e6f15  mov     rcx, r14
0x1800e6f18  call    sqlite3VdbeAddOp2
0x1800e6f1d  mov     r9d, r13d
0x1800e6f20  mov     dword ptr [rsp+130h+var_108], 0
0x1800e6f28  lea     r8d, [rdi+1]
0x1800e6f2c  mov     [rsp+130h+var_EC], eax
0x1800e6f30  mov     edx, 1Ch
0x1800e6f35  mov     dword ptr [rsp+130h+var_110], ebx
0x1800e6f39  mov     rcx, r14
0x1800e6f3c  call    sqlite3VdbeAddOp4Int
0x1800e6f41  test    ebx, ebx
0x1800e6f43  jz      short loc_1800E6F5D
0x1800e6f45  movzx   ecx, byte ptr [r12+1Fh]
0x1800e6f4b  cmp     cl, 8
0x1800e6f4e  jnb     short loc_1800E6F5D
0x1800e6f50  mov     [r12+rcx*4+0E0h], ebx
0x1800e6f58  inc     byte ptr [r12+1Fh]
0x1800e6f5d  mov     [rsp+130h+var_F8], esi
0x1800e6f61  lea     rax, [rbp+57h+var_B0]
0x1800e6f65  mov     [rsp+130h+var_100], r13d
0x1800e6f6a  xor     r9d, r9d
0x1800e6f6d  mov     [rsp+130h+var_108], rax
0x1800e6f72  mov     r8d, edi
0x1800e6f75  mov     rdx, r15
0x1800e6f78  mov     [rsp+130h+var_110], 0
0x1800e6f81  mov     rcx, r12
0x1800e6f84  call    selectInnerLoop
0x1800e6f89  mov     edx, r13d
0x1800e6f8c  mov     rcx, r14
0x1800e6f8f  call    sqlite3VdbeResolveLabel
0x1800e6f94  mov     r9d, [rsp+130h+var_EC]
0x1800e6f99  mov     r8d, edi
0x1800e6f9c  mov     edx, 27h ; '''
0x1800e6fa1  mov     rcx, r14
0x1800e6fa4  call    sqlite3VdbeAddOp2
0x1800e6fa9  mov     edx, esi
0x1800e6fab  mov     rcx, r14
0x1800e6fae  call    sqlite3VdbeResolveLabel
0x1800e6fb3  xor     r9d, r9d
0x1800e6fb6  lea     r8d, [rdi+1]
0x1800e6fba  mov     edx, 7Ah ; 'z'
0x1800e6fbf  mov     rcx, r14
0x1800e6fc2  call    sqlite3VdbeAddOp2
  ... truncated ...
```

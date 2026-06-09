# selectExpander

- ea: `0x180064960`
- end: `0x180065545`
- name: `selectExpander`
- size: `3045`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x180045b1c`
- `0x180063308`
- `0x180064960`
- `0x1800718ac`
- `0x180071a38`
- `0x180073aec`
- `0x180073dd4`
- `0x180073eb8`
- `0x180077a60`
- `0x18007d9a4`
- `0x18007da74`
- `0x180080774`
- `0x180080b64`
- `0x180080de8`
- `0x1800820a8`
- `0x180088b40`
- `0x18008d680`
- `0x18008e0c8`
- `0x18008ed60`
- `0x18009eef8`
- `0x1800b6a40`

## string_xrefs

- `0x180064b65`: `access to view "%s" prohibited`

## pseudocode

```c
__int64 __fastcall selectExpander(__int64 **a1, __int64 a2)
{
  __int64 *v2; // r14
  __int16 v3; // ax
  __int64 v4; // rsi
  __int64 v6; // rbx
  _DWORD *v8; // r12
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // ebp
  _DWORD *v13; // rdi
  int v14; // eax
  int v15; // eax
  __int64 TableItem; // rax
  const char **v17; // rsi
  unsigned int v18; // eax
  char v19; // al
  __int16 v20; // r12
  const char *v21; // rax
  __int16 v22; // bx
  int v23; // eax
  _DWORD *v24; // rbp
  __int64 v25; // r8
  int v26; // ecx
  __int64 v27; // rdx
  const char *v28; // rdx
  int *v29; // r12
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // r8
  const char *v34; // rdi
  __int64 v35; // rax
  int *v36; // rax
  _DWORD *v37; // r10
  __int64 v38; // r9
  _DWORD *v39; // rbx
  const char *v40; // rax
  __int64 v41; // r11
  __int64 v42; // r15
  int v43; // eax
  int v44; // ecx
  __int16 v45; // cx
  const char *v46; // rbp
  int v47; // edi
  const char *v48; // rsi
  __int64 v49; // rax
  int *v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rax
  int v53; // eax
  unsigned int v54; // eax
  int v55; // edi
  int v56; // ebx
  unsigned int v57; // r11d
  __int64 v58; // r15
  __int64 v59; // rsi
  int v60; // eax
  const char *v61; // rbp
  const char *v62; // rdi
  __int16 v63; // cx
  int v64; // eax
  __int64 v65; // rsi
  _DWORD *v66; // rdi
  int i; // ebx
  __int64 v68; // rcx
  __int64 v69; // rbx
  int matched; // eax
  __int64 v71; // rcx
  __int64 v72; // rbx
  __int64 v73; // rdx
  __int64 *j; // rcx
  const char *v75; // rdi
  __int64 v76; // rax
  int *v77; // rax
  __int64 v78; // rbx
  unsigned int v79; // esi
  __int64 v80; // rax
  unsigned int v81; // edi
  int v82; // eax
  int v83; // eax
  __int64 v84; // rax
  _DWORD *v85; // rcx
  __int64 v86; // [rsp+30h] [rbp-E8h]
  unsigned int v87; // [rsp+38h] [rbp-E0h]
  unsigned int v88; // [rsp+3Ch] [rbp-DCh]
  _DWORD *v89; // [rsp+40h] [rbp-D8h]
  int v90; // [rsp+48h] [rbp-D0h]
  _DWORD *v91; // [rsp+50h] [rbp-C8h]
  int v92; // [rsp+58h] [rbp-C0h]
  int v93; // [rsp+5Ch] [rbp-BCh]
  int v94; // [rsp+60h] [rbp-B8h]
  const char *v95; // [rsp+68h] [rbp-B0h]
  __int64 v96; // [rsp+70h] [rbp-A8h]
  const char *v97; // [rsp+78h] [rbp-A0h]
  const char *v98; // [rsp+80h] [rbp-98h]
  int v99; // [rsp+88h] [rbp-90h]
  __int64 v100; // [rsp+90h] [rbp-88h]
  _DWORD *v101; // [rsp+98h] [rbp-80h]
  const char *v102; // [rsp+A0h] [rbp-78h]
  _DWORD *v103; // [rsp+A8h] [rbp-70h]
  __int64 v104; // [rsp+B0h] [rbp-68h]
  _QWORD v105[12]; // [rsp+B8h] [rbp-60h]
  __int16 v106; // [rsp+120h] [rbp+8h]
  __int16 v108; // [rsp+130h] [rbp+18h]
  int v109; // [rsp+138h] [rbp+20h]

  v2 = *a1;
  v3 = *(_WORD *)(a2 + 4);
  v4 = a2;
  v108 = v3;
  v6 = **a1;
  *(_DWORD *)(a2 + 4) |= 0x40u;
  v96 = v6;
  if ( *(_BYTE *)(v6 + 103) )
    return 2;
  if ( (v3 & 0x40) != 0 )
    return 1;
  if ( *((_WORD *)a1 + 18) )
    *(_DWORD *)(a2 + 16) = ++*((_DWORD *)v2 + 37);
  v8 = *(_DWORD **)(a2 + 40);
  v91 = v8;
  v101 = *(_DWORD **)(a2 + 32);
  if ( v2[51] && (*(_DWORD *)(a2 + 4) & 0x200000) != 0 )
  {
    v9 = *(_QWORD *)(a2 + 104);
    if ( v9 || (v9 = sqlite3DbMallocZero(v6, 64), (*(_QWORD *)(v4 + 104) = v9) != 0) )
    {
      *(_DWORD *)(v9 + 4) = 1;
      goto LABEL_11;
    }
    return 2;
  }
LABEL_11:
  v10 = *(_QWORD *)(v4 + 104);
  if ( v10 && !*((_DWORD *)v2 + 12) )
  {
    *(_QWORD *)(v10 + 8) = v2[51];
    v2[51] = v10;
  }
  sqlite3SrcListAssignCursors(v2, v8);
  v12 = v11;
  v13 = v8 + 2;
  v103 = v8 + 2;
  if ( *v8 > (int)v11 )
  {
    while ( 1 )
    {
      if ( *((_QWORD *)v13 + 4) == v11 )
      {
        if ( *((_QWORD *)v13 + 2) == v11 )
        {
          if ( (unsigned int)sqlite3WalkSelect(a1, *((_QWORD *)v13 + 5)) )
            return 2;
          v14 = sqlite3ExpandSubquery(v2, v13);
          v11 = 0;
          if ( v14 )
            return 2;
        }
        else
        {
          v15 = resolveFromTermToCte(v2, a1, v13);
          v11 = 0;
          if ( v15 )
          {
            if ( v15 > 1 )
              return 2;
          }
          else
          {
            TableItem = sqlite3LocateTableItem(v2, 0, v13);
            v11 = 0;
            *((_QWORD *)v13 + 4) = TableItem;
            v17 = (const char **)TableItem;
            if ( !TableItem )
              return 2;
            v18 = *(_DWORD *)(TableItem + 44);
            if ( v18 >= 0xFFFF )
            {
              sqlite3ErrorMsg(v2, "too many references to \"%s\": max 65535", *v17);
              *((_QWORD *)v13 + 4) = 0;
              return 2;
            }
            *((_DWORD *)v17 + 11) = v18 + 1;
            v19 = *((_BYTE *)v17 + 63);
            if ( v19 != 1 && (v13[16] & 4) != 0 )
            {
              sqlite3ErrorMsg(v2, "'%s' is not a function", *((const char **)v13 + 2));
              return 2;
            }
            if ( v19 )
            {
              v20 = *((unsigned __int8 *)a1 + 36);
              if ( (v19 == 1 || *((__int16 *)v17 + 27) <= 0) && (unsigned int)viewGetColumnNames(v2, v17) )
                return 2;
              if ( *((_BYTE *)v17 + 63) == 2 )
              {
                if ( (*(_DWORD *)(v6 + 48) & 0x80000000) == 0
                  && v17[12] != *(const char **)(*(_QWORD *)(v6 + 32) + 56LL) )
                {
                  sqlite3ErrorMsg(v2, "access to view \"%s\" prohibited", *v17);
                }
                *((_QWORD *)v13 + 5) = sqlite3SelectDup(v6, v17[8], 0);
              }
              else if ( *((_BYTE *)v17 + 63) == 1 && *((char *)v13 + 64) < 0 )
              {
                v21 = v17[10];
                if ( v21 )
                {
                  if ( *((unsigned __int8 *)v21 + 30) > ((*(_DWORD *)(v6 + 48) >> 7) & 1u) )
                    sqlite3ErrorMsg(v2, "unsafe use of virtual table \"%s\"", *v17);
                }
              }
              v22 = *((_WORD *)v17 + 27);
              *((_WORD *)v17 + 27) = -1;
              *((_WORD *)a1 + 18) = 1;
              sqlite3WalkSelect(a1, *((_QWORD *)v13 + 5));
              *((_WORD *)a1 + 18) = v20;
              v11 = 0;
              v8 = v91;
              *((_WORD *)v17 + 27) = v22;
              v6 = v96;
            }
          }
        }
        if ( (v13[16] & 2) != 0 )
        {
          v23 = sqlite3IndexedByLookup(v2, v13, 0);
          v11 = 0;
          if ( v23 )
            return 2;
        }
      }
      if ( ++v12 >= *v8 )
        break;
      v13 += 26;
    }
    v4 = a2;
  }
  if ( *((_DWORD *)v2 + 12) != (_DWORD)v11 || (unsigned int)sqlite3ProcessJoin(v2, v4) )
    return 2;
  v24 = v101;
  v25 = 0;
  v88 = 0;
  v26 = 0;
  if ( (int)*v101 <= 0 )
  {
LABEL_56:
    if ( v26 >= *v101 )
      goto LABEL_190;
  }
  else
  {
    while ( 1 )
    {
      v27 = *(_QWORD *)&v101[8 * v26 + 2];
      if ( *(_BYTE *)v27 == 0xB4 || *(_BYTE *)v27 == 0x8D && **(_BYTE **)(v27 + 24) == 0xB4 )
        break;
      v25 = *(_DWORD *)(v27 + 4) | (unsigned int)v25;
      ++v26;
      v88 = v25;
      if ( v26 >= *v101 )
        goto LABEL_56;
    }
  }
  v28 = 0;
  v29 = 0;
  v94 = 0;
  v99 = *(_DWORD *)(*v2 + 48) & 0x44;
  v30 = 0;
  if ( (int)*v101 <= 0 )
    goto LABEL_189;
  do
  {
    v31 = 8LL * v30;
    v32 = *(_QWORD *)&v24[v31 + 2];
    v104 = v32;
    v33 = *(_DWORD *)(v32 + 4) | (unsigned int)v25;
    v88 = v33;
    if ( *(_BYTE *)v32 == 0xB4 )
    {
      v34 = v28;
      v35 = *(_QWORD *)&v24[v31 + 2];
    }
    else
    {
      if ( *(_BYTE *)v32 != 0x8D || **(_BYTE **)(v32 + 24) != 0xB4 )
      {
        v36 = (int *)sqlite3ExprListAppend(v2, v29, v32);
        v28 = 0;
        v29 = v36;
        if ( v36 )
        {
          *(_QWORD *)&v36[8 * *v36 - 4] = *(_QWORD *)&v24[v31 + 4];
          v36[8 * *v36 - 1] ^= (v24[v31 + 7] ^ v36[8 * *v36 - 1]) & 3;
          *(_QWORD *)&v24[v31 + 4] = 0;
        }
        *(_QWORD *)&v24[v31 + 2] = 0;
        goto LABEL_187;
      }
      v34 = *(const char **)(*(_QWORD *)(v32 + 16) + 8LL);
      v35 = *(_QWORD *)(v32 + 24);
    }
    v37 = v91;
    v38 = (unsigned int)v28;
    v39 = v103;
    v95 = v34;
    v90 = (int)v28;
    v92 = *(_DWORD *)(v35 + 52);
    v109 = (int)v28;
    v89 = v103;
    if ( *v91 <= (int)v28 )
      goto LABEL_181;
    do
    {
      v40 = (const char *)*((_QWORD *)v39 + 3);
      v41 = *((_QWORD *)v39 + 4);
      v86 = v41;
      v98 = v40;
      if ( !v40 )
      {
        v40 = *(const char **)v41;
        v98 = *(const char **)v41;
      }
      v42 = v96;
      if ( *(_BYTE *)(v96 + 103) != (_BYTE)v28 )
        break;
      if ( (v39[16] & 0x2000) != 0 )
      {
        v97 = v28;
        v100 = *(_QWORD *)(*((_QWORD *)v39 + 5) + 32LL);
        goto LABEL_82;
      }
      if ( v34 )
      {
        v43 = sqlite3StrICmp(v34, v40);
        LODWORD(v38) = v109;
        v28 = 0;
        v37 = v91;
        if ( v43 )
          goto LABEL_179;
      }
      v100 = (__int64)v28;
      v28 = *(const char **)(v41 + 96);
      if ( v28 )
      {
        v33 = *(_QWORD *)(v96 + 32);
        v44 = 0;
        if ( *(const char **)(v33 + 24) == v28 )
        {
          v28 = 0;
LABEL_80:
          _mm_lfence();
          v97 = *(const char **)(32LL * v44 + *(_QWORD *)(v96 + 32));
          goto LABEL_82;
        }
        do
          ++v44;
        while ( *(const char **)(32LL * v44 + v33 + 24) != v28 );
        v28 = 0;
        if ( v44 >= 0 )
          goto LABEL_80;
      }
      v97 = "*";
LABEL_82:
      if ( (int)v38 + 1 < *v37
        && (v33 = 1024, (v39[42] & 0x400) != 0)
        && (v45 = v108 & 0x800, v106 = v108 & 0x800, (v108 & 0x800) != 0) )
      {
        v46 = (const char *)*((_QWORD *)v39 + 22);
        v47 = (int)v28;
        v102 = v46;
        if ( *(_DWORD *)v46 > (int)v28 )
        {
          do
          {
            v48 = *(const char **)&v46[16 * v47 + 8];
            v49 = sqlite3Expr(v96, 59, v48);
            if ( v49 && (*(_BYTE *)(v49 + 4) & 3) == 0 )
              *(_DWORD *)(v49 + 52) = v92;
            v50 = (int *)sqlite3ExprListAppend(v2, v29, v49);
            v28 = 0;
            v29 = v50;
            if ( v50 )
            {
              v51 = 8 * (*v50 - 1LL);
              v52 = sqlite3MPrintf(v96, "..%s", v48);
              v29[v51 + 7] &= ~1u;
              v29[v51 + 7] |= 0x82u;
              v28 = 0;
              *(_QWORD *)&v29[v51 + 4] = v52;
            }
            ++v47;
          }
          while ( v47 < *(_DWORD *)v46 );
          v4 = a2;
          v39 = v89;
          v45 = v108 & 0x800;
          v41 = v86;
          LODWORD(v38) = v109;
          v37 = v91;
        }
      }
      else
      {
        v45 = v108 & 0x800;
        v102 = v28;
        v106 = v108 & 0x800;
      }
      v53 = *(__int16 *)(v41 + 54);
      v93 = v53;
      if ( (*(_DWORD *)(v41 + 48) & 0x200) == 0 && v45 )
        v93 = ++v53;
      if ( v53 > 0 )
      {
        v54 = (unsigned int)v28;
        v87 = (unsigned int)v28;
        while ( 1 )
        {
          v55 = *(__int16 *)(v41 + 54);
          if ( v54 != v55 )
            break;
          v105[0] = "_ROWID_";
          v56 = (int)v28;
          v105[1] = "ROWID";
          v105[2] = "OID";
          while ( 1 )
          {
            v57 = (unsigned int)v28;
            if ( v55 > 0 )
            {
              v58 = *(_QWORD *)(v86 + 8);
              v59 = v105[v56];
              while ( 1 )
              {
                v28 = *(const char **)(v58 + 24LL * v57);
                if ( !v59 )
                  break;
                if ( v28 )
                {
                  v60 = sqlite3StrICmp(v59, v28);
LABEL_107:
                  v28 = 0;
                  if ( !v60 )
                    goto LABEL_110;
                }
                if ( (int)++v57 >= v55 )
                  goto LABEL_109;
              }
              v60 = -(v28 != 0);
              goto LABEL_107;
            }
LABEL_109:
            if ( v57 == v55 )
              break;
LABEL_110:
            if ( ++v56 >= 3 )
            {
              v41 = v86;
              goto LABEL_176;
            }
          }
          v61 = (const char *)v105[v56];
          if ( v61 )
          {
            v42 = v96;
            v62 = v95;
            goto LABEL_114;
          }
LABEL_184:
          v41 = v86;
LABEL_176:
          v4 = a2;
          v54 = v87 + 1;
          v42 = v96;
          v87 = v54;
          if ( (int)v54 >= v93 )
          {
LABEL_177:
            v39 = v89;
            LODWORD(v38) = v109;
            v37 = v91;
            goto LABEL_178;
          }
        }
        v33 = v100;
        v68 = 32LL * v54;
        if ( !v100 || (*(_BYTE *)(v100 + v68 + 28) & 3) != 3 )
        {
          v69 = 3LL * v54;
          v62 = v95;
          v28 = 0;
          v61 = *(const char **)(*(_QWORD *)(v41 + 8) + 24LL * v54);
          if ( v95 )
          {
            if ( v100 )
            {
              matched = sqlite3MatchEName((int)v100 + 8 + (int)v68, 0, (_DWORD)v95, 0, 0);
              v41 = v86;
              v28 = 0;
              if ( !matched )
                goto LABEL_176;
            }
          }
          if ( (*(_DWORD *)(v4 + 4) & 0x20000) == 0 && (*(_BYTE *)(*(_QWORD *)(v41 + 8) + 8 * v69 + 18) & 2) != 0 )
            goto LABEL_176;
          v33 = 1024;
          if ( (*(_WORD *)(*(_QWORD *)(v41 + 8) + 8 * v69 + 18) & 0x400) != 0 )
          {
            v63 = v106;
            if ( !v95 && !v106 )
              goto LABEL_176;
          }
          else
          {
LABEL_114:
            v63 = v106;
          }
          v90 = 1;
          if ( v109 > (int)v28 && !v62 && !v63 && (v89[16] & 0x400) != 0 )
          {
            v64 = sqlite3IdListIndex(*((_QWORD *)v89 + 9), v61);
            v28 = 0;
            if ( v64 >= 0 )
              goto LABEL_184;
          }
          v65 = sqlite3Expr(v42, 59, v61);
          if ( (int)*v91 <= 1 )
          {
LABEL_141:
            if ( *((_BYTE *)v2 + 308) >= 2u )
              goto LABEL_142;
            v75 = v97;
          }
          else
          {
            if ( (v89[15] & 0x40) != 0 && !v106 )
            {
              v66 = v89;
              for ( i = *v91 + ~v109; i > 0; --i )
              {
                v66 += 26;
                if ( (v66[16] & 0x400) != 0 )
                {
                  v71 = *((_QWORD *)v66 + 9);
                  if ( v71 )
                  {
                    if ( (int)sqlite3IdListIndex(v71, v61) >= 0 )
                      goto LABEL_141;
                  }
                }
              }
            }
LABEL_142:
            v72 = sqlite3Expr(v42, 59, v98);
            v65 = sqlite3PExpr(v2, 141, v72);
            if ( *((_BYTE *)v2 + 308) >= 2u )
            {
              v73 = *(_QWORD *)(v104 + 16);
              if ( v73 )
              {
                for ( j = (__int64 *)v2[52]; j; j = (__int64 *)j[3] )
                {
                  if ( *j == v73 )
                  {
                    *j = v72;
                    break;
                  }
                }
              }
            }
            v75 = v97;
            if ( v97 )
            {
              v76 = sqlite3Expr(v42, 59, v97);
              v65 = sqlite3PExpr(v2, 141, v76);
            }
          }
          if ( v65 && (*(_BYTE *)(v65 + 4) & 3) == 0 )
            *(_DWORD *)(v65 + 52) = v92;
          v77 = (int *)sqlite3ExprListAppend(v2, v29, v65);
          v28 = 0;
          v29 = v77;
          if ( !v77 )
            goto LABEL_177;
          v78 = 8LL * *v77;
          if ( v106 && *((_BYTE *)v2 + 308) < 2u )
          {
            if ( v100 )
            {
              v79 = v87;
              v80 = sqlite3DbStrDup(v42, *(_QWORD *)(32LL * v87 + v100 + 16));
            }
            else
            {
              v80 = sqlite3MPrintf(v42, "%s.%s.%s", v75, v98, v61);
              v79 = v87;
            }
            *(_QWORD *)&v29[v78 - 4] = v80;
            v81 = v29[v78 - 1] & 0xFFFFFFFC | (3 - (*(__int16 *)(v86 + 54) != v79));
            v29[v78 - 1] = v81;
            if ( (v89[16] & 0x400) != 0 )
            {
              v82 = sqlite3IdListIndex(*((_QWORD *)v89 + 9), v61);
              v28 = 0;
              if ( v82 >= 0 )
                goto LABEL_164;
            }
            else
            {
              v28 = 0;
            }
            if ( v102 && (v83 = sqlite3IdListIndex(v102, v61), v28 = 0, v83 >= 0) )
            {
LABEL_164:
              v41 = v86;
            }
            else
            {
              v41 = v86;
              if ( (int)v79 >= *(__int16 *)(v86 + 54)
                || (*(_WORD *)(*(_QWORD *)(v86 + 8) + 24LL * v79 + 18) & 0x400) == 0 )
              {
                goto LABEL_176;
              }
            }
            v29[v78 - 1] = v81 | 0x100;
            goto LABEL_176;
          }
          if ( v99 == 4 )
            v84 = sqlite3MPrintf(v42, "%s.%s", v98, v61);
          else
            v84 = sqlite3DbStrDup(v42, v61);
          v29[v78 - 1] &= 0xFFFFFFFC;
          v41 = v86;
          *(_QWORD *)&v29[v78 - 4] = v84;
        }
        v28 = 0;
        goto LABEL_176;
      }
LABEL_178:
      v34 = v95;
LABEL_179:
      v4 = a2;
      v38 = (unsigned int)(v38 + 1);
      v39 += 26;
      v109 = v38;
      v89 = v39;
    }
    while ( (int)v38 < *v37 );
    v24 = v101;
    if ( !v90 )
    {
LABEL_181:
      if ( v34 )
        sqlite3ErrorMsg(v2, "no such table: %s", v34);
      else
        sqlite3ErrorMsg(v2, "no tables specified", v33, v38);
      v28 = 0;
    }
LABEL_187:
    LODWORD(v25) = v88;
    v30 = v94 + 1;
    v94 = v30;
  }
  while ( v30 < *v24 );
  v6 = v96;
LABEL_189:
  exprListDeleteNN(v6, v24);
  v25 = v88;
  *(_QWORD *)(v4 + 32) = v29;
LABEL_190:
  v85 = *(_DWORD **)(v4 + 32);
  if ( v85 )
  {
    if ( *v85 > *(_DWORD *)(v6 + 144) )
    {
      sqlite3ErrorMsg(v2, "too many columns in result set", v25);
      return 2;
    }
    if ( (v25 & 0x400008) != 0 )
      *(_DWORD *)(v4 + 4) |= 0x40000u;
  }
  return 0;
}

```

## disassembly

```asm
0x180064960  mov     [rsp+arg_8], rdx
0x180064965  push    rbx
0x180064966  push    rbp
0x180064967  push    rsi
0x180064968  push    rdi
0x180064969  push    r12
0x18006496b  push    r13
0x18006496d  push    r14
0x18006496f  push    r15
0x180064971  sub     rsp, 0D8h
0x180064978  mov     r14, [rcx]
0x18006497b  xor     r8d, r8d
0x18006497e  movzx   eax, word ptr [rdx+4]
0x180064982  mov     rsi, rdx
0x180064985  mov     r15, rcx
0x180064988  mov     [rsp+118h+arg_10], ax
0x180064990  mov     rbx, [r14]
0x180064993  or      dword ptr [rdx+4], 40h
0x180064997  mov     [rsp+118h+var_A8], rbx
0x18006499c  cmp     [rbx+67h], r8b
0x1800649a0  jnz     loc_180064A9F
0x1800649a6  test    al, 40h
0x1800649a8  jz      short loc_1800649B3
0x1800649aa  lea     eax, [r8+1]
0x1800649ae  jmp     loc_180064AA4
0x1800649b3  mov     r13d, 1
0x1800649b9  cmp     [rcx+24h], r8w
0x1800649be  jz      short loc_1800649D1
0x1800649c0  add     [r14+94h], r13d
0x1800649c7  mov     eax, [r14+94h]
0x1800649ce  mov     [rdx+10h], eax
0x1800649d1  mov     r12, [rdx+28h]
0x1800649d5  mov     rax, [rdx+20h]
0x1800649d9  mov     [rsp+118h+var_C8], r12
0x1800649de  mov     [rsp+118h+var_80], rax
0x1800649e6  cmp     [r14+198h], r8
0x1800649ed  jz      short loc_180064A20
0x1800649ef  test    dword ptr [rdx+4], 200000h
0x1800649f6  jz      short loc_180064A20
0x1800649f8  mov     rax, [rdx+68h]
0x1800649fc  test    rax, rax
0x1800649ff  jnz     short loc_180064A1C
0x180064a01  lea     edx, [rax+40h]
0x180064a04  mov     rcx, rbx
0x180064a07  call    sqlite3DbMallocZero
0x180064a0c  xor     r8d, r8d
0x180064a0f  mov     [rsi+68h], rax
0x180064a13  test    rax, rax
0x180064a16  jz      loc_180064A9F
0x180064a1c  mov     [rax+4], r13d
0x180064a20  mov     rcx, [rsi+68h]
0x180064a24  test    rcx, rcx
0x180064a27  jz      short loc_180064A41
0x180064a29  cmp     [r14+30h], r8d
0x180064a2d  jnz     short loc_180064A41
0x180064a2f  mov     rax, [r14+198h]
0x180064a36  mov     [rcx+8], rax
0x180064a3a  mov     [r14+198h], rcx
0x180064a41  mov     rdx, r12
0x180064a44  mov     rcx, r14
0x180064a47  call    sqlite3SrcListAssignCursors
0x180064a4c  lea     rax, [r12+8]
0x180064a51  mov     ebp, r8d
0x180064a54  mov     rdi, rax
0x180064a57  mov     [rsp+118h+var_70], rax
0x180064a5f  cmp     [r12], r8d
0x180064a63  jle     loc_180064C60
0x180064a69  cmp     [rdi+20h], r8
0x180064a6d  jnz     loc_180064C0F
0x180064a73  cmp     [rdi+10h], r8
0x180064a77  jnz     short loc_180064AB8
0x180064a79  mov     rdx, [rdi+28h]
0x180064a7d  mov     rcx, r15
0x180064a80  call    sqlite3WalkSelect
0x180064a85  test    eax, eax
0x180064a87  jnz     short loc_180064A9F
0x180064a89  mov     rdx, rdi
0x180064a8c  mov     rcx, r14
0x180064a8f  call    sqlite3ExpandSubquery
0x180064a94  xor     r8d, r8d
0x180064a97  test    eax, eax
0x180064a99  jz      loc_180064BF3
0x180064a9f  mov     eax, 2
0x180064aa4  add     rsp, 0D8h
0x180064aab  pop     r15
0x180064aad  pop     r14
0x180064aaf  pop     r13
0x180064ab1  pop     r12
0x180064ab3  pop     rdi
0x180064ab4  pop     rsi
0x180064ab5  pop     rbp
0x180064ab6  pop     rbx
0x180064ab7  retn
0x180064ab8  mov     r8, rdi
0x180064abb  mov     rdx, r15
0x180064abe  mov     rcx, r14
0x180064ac1  call    resolveFromTermToCte
0x180064ac6  xor     r8d, r8d
0x180064ac9  test    eax, eax
0x180064acb  jz      short loc_180064AD7
0x180064acd  cmp     eax, r13d
0x180064ad0  jg      short loc_180064A9F
0x180064ad2  jmp     loc_180064BF3
0x180064ad7  mov     r8, rdi
0x180064ada  xor     edx, edx
0x180064adc  mov     rcx, r14
0x180064adf  call    sqlite3LocateTableItem
0x180064ae4  xor     r8d, r8d
0x180064ae7  mov     [rdi+20h], rax
0x180064aeb  mov     rsi, rax
0x180064aee  test    rax, rax
0x180064af1  jz      short loc_180064A9F
0x180064af3  mov     eax, [rax+2Ch]
0x180064af6  cmp     eax, 0FFFFh
0x180064afb  jnb     loc_180064C39
0x180064b01  inc     eax
0x180064b03  mov     [rsi+2Ch], eax
0x180064b06  mov     al, [rsi+3Fh]
0x180064b09  cmp     al, r13b
0x180064b0c  jz      short loc_180064B18
0x180064b0e  test    byte ptr [rdi+40h], 4
0x180064b12  jnz     loc_180064C21
0x180064b18  test    al, al
0x180064b1a  jz      loc_180064BF3
0x180064b20  movzx   r12d, byte ptr [r15+24h]
0x180064b25  cmp     al, r13b
0x180064b28  jz      short loc_180064B31
0x180064b2a  cmp     [rsi+36h], r8w
0x180064b2f  jg      short loc_180064B44
0x180064b31  mov     rdx, rsi
0x180064b34  mov     rcx, r14
0x180064b37  call    viewGetColumnNames
0x180064b3c  test    eax, eax
0x180064b3e  jnz     loc_180064A9F
0x180064b44  cmp     byte ptr [rsi+3Fh], 2
0x180064b48  jnz     short loc_180064B89
0x180064b4a  mov     eax, [rbx+30h]
0x180064b4d  bt      rax, 1Fh
0x180064b52  jb      short loc_180064B74
0x180064b54  mov     rax, [rbx+20h]
0x180064b58  mov     rcx, [rax+38h]
0x180064b5c  cmp     [rsi+60h], rcx
0x180064b60  jz      short loc_180064B74
0x180064b62  mov     r8, [rsi]
0x180064b65  lea     rdx, aAccessToViewSP; "access to view \"%s\" prohibited"
0x180064b6c  mov     rcx, r14
0x180064b6f  call    sqlite3ErrorMsg
0x180064b74  mov     rdx, [rsi+40h]
0x180064b78  xor     r8d, r8d
0x180064b7b  mov     rcx, rbx
0x180064b7e  call    sqlite3SelectDup
0x180064b83  mov     [rdi+28h], rax
0x180064b87  jmp     short loc_180064BC2
0x180064b89  cmp     [rsi+3Fh], r13b
0x180064b8d  jnz     short loc_180064BC2
0x180064b8f  test    byte ptr [rdi+40h], 80h
0x180064b93  jz      short loc_180064BC2
0x180064b95  mov     rax, [rsi+50h]
0x180064b99  test    rax, rax
0x180064b9c  jz      short loc_180064BC2
0x180064b9e  mov     ecx, [rbx+30h]
0x180064ba1  movzx   eax, byte ptr [rax+1Eh]
0x180064ba5  shr     rcx, 7
0x180064ba9  and     ecx, r13d
0x180064bac  cmp     eax, ecx
0x180064bae  jbe     short loc_180064BC2
0x180064bb0  mov     r8, [rsi]
0x180064bb3  lea     rdx, aUnsafeUseOfVir; "unsafe use of virtual table \"%s\""
0x180064bba  mov     rcx, r14
0x180064bbd  call    sqlite3ErrorMsg
0x180064bc2  movzx   ebx, word ptr [rsi+36h]
0x180064bc6  mov     rcx, r15
0x180064bc9  mov     word ptr [rsi+36h], 0FFFFh
0x180064bcf  mov     [r15+24h], r13w
0x180064bd4  mov     rdx, [rdi+28h]
0x180064bd8  call    sqlite3WalkSelect
0x180064bdd  mov     [r15+24h], r12w
0x180064be2  xor     r8d, r8d
0x180064be5  mov     r12, [rsp+118h+var_C8]
0x180064bea  mov     [rsi+36h], bx
0x180064bee  mov     rbx, [rsp+118h+var_A8]
0x180064bf3  test    byte ptr [rdi+40h], 2
0x180064bf7  jz      short loc_180064C0F
0x180064bf9  mov     rdx, rdi
0x180064bfc  mov     rcx, r14
0x180064bff  call    sqlite3IndexedByLookup
0x180064c04  xor     r8d, r8d
0x180064c07  test    eax, eax
0x180064c09  jnz     loc_180064A9F
0x180064c0f  add     ebp, r13d
0x180064c12  cmp     ebp, [r12]
0x180064c16  jge     short loc_180064C58
0x180064c18  add     rdi, 68h ; 'h'
0x180064c1c  jmp     loc_180064A69
0x180064c21  mov     r8, [rdi+10h]
0x180064c25  lea     rdx, aSIsNotAFunctio; "'%s' is not a function"
0x180064c2c  mov     rcx, r14
0x180064c2f  call    sqlite3ErrorMsg
0x180064c34  jmp     loc_180064A9F
0x180064c39  mov     r8, [rsi]
0x180064c3c  lea     rdx, aTooManyReferen; "too many references to \"%s\": max 6553"...
0x180064c43  mov     rcx, r14
0x180064c46  call    sqlite3ErrorMsg
0x180064c4b  mov     qword ptr [rdi+20h], 0
0x180064c53  jmp     loc_180064A9F
0x180064c58  mov     rsi, [rsp+118h+arg_8]
0x180064c60  cmp     [r14+30h], r8d
0x180064c64  jnz     loc_180064A9F
0x180064c6a  mov     rdx, rsi
0x180064c6d  mov     rcx, r14
0x180064c70  call    sqlite3ProcessJoin
0x180064c75  xor     edx, edx
0x180064c77  test    eax, eax
0x180064c79  jnz     loc_180064A9F
0x180064c7f  mov     rbp, [rsp+118h+var_80]
0x180064c87  mov     r8d, edx
0x180064c8a  mov     [rsp+118h+var_DC], edx
0x180064c8e  mov     ecx, edx
0x180064c90  cmp     [rbp+0], edx
0x180064c93  jle     short loc_180064CC4
0x180064c95  mov     eax, ecx
0x180064c97  shl     rax, 5
0x180064c9b  mov     rdx, [rax+rbp+8]
0x180064ca0  cmp     byte ptr [rdx], 0B4h
0x180064ca3  jz      short loc_180064CCD
0x180064ca5  cmp     byte ptr [rdx], 8Dh
0x180064ca8  jnz     short loc_180064CB3
0x180064caa  mov     rax, [rdx+18h]
0x180064cae  cmp     byte ptr [rax], 0B4h
0x180064cb1  jz      short loc_180064CCD
0x180064cb3  or      r8d, [rdx+4]
0x180064cb7  add     ecx, r13d
0x180064cba  mov     [rsp+118h+var_DC], r8d
0x180064cbf  cmp     ecx, [rbp+0]
0x180064cc2  jl      short loc_180064C95
0x180064cc4  cmp     ecx, [rbp+0]
0x180064cc7  jge     loc_180065509
0x180064ccd  mov     rax, [r14]
0x180064cd0  xor     edx, edx
0x180064cd2  mov     r12d, edx
0x180064cd5  mov     [rsp+118h+var_B8], edx
0x180064cd9  mov     eax, [rax+30h]
0x180064cdc  and     eax, 44h
0x180064cdf  mov     [rsp+118h+var_90], eax
0x180064ce6  mov     eax, edx
0x180064ce8  cmp     [rbp+0], edx
0x180064ceb  jle     loc_1800654F5
0x180064cf1  movsxd  rbx, eax
0x180064cf4  shl     rbx, 5
0x180064cf8  mov     rcx, [rbx+rbp+8]
0x180064cfd  mov     [rsp+118h+var_68], rcx
0x180064d05  or      r8d, [rcx+4]
0x180064d09  cmp     byte ptr [rcx], 0B4h
0x180064d0c  mov     [rsp+118h+var_DC], r8d
0x180064d11  jz      short loc_180064D80
0x180064d13  cmp     byte ptr [rcx], 8Dh
0x180064d16  jnz     short loc_180064D2F
0x180064d18  mov     rax, [rcx+18h]
0x180064d1c  cmp     byte ptr [rax], 0B4h
0x180064d1f  jnz     short loc_180064D2F
0x180064d21  mov     rax, [rcx+10h]
0x180064d25  mov     rdi, [rax+8]
0x180064d29  mov     rax, [rcx+18h]
0x180064d2d  jmp     short loc_180064D86
0x180064d2f  mov     r8, rcx
0x180064d32  mov     rdx, r12
0x180064d35  mov     rcx, r14
0x180064d38  call    sqlite3ExprListAppend
0x180064d3d  xor     edx, edx
0x180064d3f  mov     r12, rax
0x180064d42  test    rax, rax
0x180064d45  jz      short loc_180064D76
0x180064d47  movsxd  rcx, dword ptr [rax]
0x180064d4a  mov     rax, [rbx+rbp+10h]
0x180064d4f  shl     rcx, 5
0x180064d53  mov     [rcx+r12-10h], rax
0x180064d58  movsxd  rcx, dword ptr [r12]
0x180064d5c  shl     rcx, 5
0x180064d60  mov     eax, [rcx+r12-4]
0x180064d65  xor     eax, [rbx+rbp+1Ch]
0x180064d69  and     eax, 3
0x180064d6c  xor     [rcx+r12-4], eax
0x180064d71  mov     [rbx+rbp+10h], rdx
0x180064d76  mov     [rbx+rbp+8], rdx
0x180064d7b  jmp     loc_1800654D7
0x180064d80  mov     rdi, rdx
0x180064d83  mov     rax, rcx
0x180064d86  mov     r10, [rsp+118h+var_C8]
0x180064d8b  mov     r9d, edx
0x180064d8e  mov     rbx, [rsp+118h+var_70]
0x180064d96  mov     eax, [rax+34h]
0x180064d99  mov     [rsp+118h+var_B0], rdi
0x180064d9e  mov     [rsp+118h+var_D0], edx
0x180064da2  mov     [rsp+118h+var_C0], eax
0x180064da6  mov     [rsp+118h+arg_18], edx
0x180064dad  mov     [rsp+118h+var_D8], rbx
0x180064db2  cmp     [r10], edx
0x180064db5  jle     loc_180065499
0x180064dbb  mov     rax, [rbx+18h]
0x180064dbf  mov     r11, [rbx+20h]
  ... truncated ...
```

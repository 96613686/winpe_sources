# selectExpander

- ea: `0x18002b9d0`
- end: `0x18002c515`
- name: `selectExpander`
- size: `2885`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: ``

## callees

- `0x180014434`
- `0x180014464`
- `0x18001ece0`
- `0x180027e60`
- `0x1800283fc`
- `0x18002b8ec`
- `0x18002b9d0`
- `0x18002e290`
- `0x18003138c`
- `0x18003b8bc`
- `0x18003bcbc`
- `0x18003c5f4`
- `0x18003c8d4`
- `0x18003fb88`
- `0x180042c38`
- `0x1800634cc`
- `0x180074d44`
- `0x18007f004`
- `0x18007f0e8`
- `0x180081090`
- `0x180083e50`
- `0x180083f54`
- `0x180085f68`
- `0x180086d48`
- `0x1800899a0`
- `0x18008a2cc`
- `0x18008a99c`

## string_xrefs

- `0x18002bbd1`: `access to view "%s" prohibited`

## pseudocode

```c
__int64 __fastcall selectExpander(__int64 **a1, __int64 a2)
{
  __int64 *v2; // rsi
  __int64 v3; // rbx
  __int16 v4; // bp
  __int64 v6; // r13
  int *v8; // r14
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // r12d
  _DWORD *i; // rdi
  int v13; // eax
  __int64 TableItem; // rax
  unsigned int v15; // ecx
  bool v16; // zf
  const char **v17; // rdx
  char v18; // al
  const char *v19; // rax
  __int16 v20; // di
  _DWORD *v21; // r15
  int v22; // r10d
  int v23; // ecx
  int v24; // edx
  __int64 v25; // r8
  int *v26; // r9
  int v27; // eax
  _DWORD *v28; // rdi
  _DWORD *v29; // r12
  char *v30; // rdx
  char v31; // cl
  int *v32; // rax
  const char *v33; // r11
  __int64 v34; // rax
  int v35; // r12d
  _DWORD *v36; // r15
  const char *v37; // rax
  __int64 v38; // r10
  __int64 v39; // rdx
  int v40; // eax
  int v41; // eax
  __int16 v42; // r8
  int v43; // r12d
  int *v44; // rbp
  _DWORD *v45; // r15
  __int64 v46; // rax
  __int64 v47; // rax
  int *v48; // rax
  int *v49; // rdi
  __int64 v50; // rax
  int v51; // eax
  unsigned int v52; // edi
  __int64 v53; // rax
  const char *v54; // r12
  __int64 v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rdi
  int matched; // eax
  __int64 v59; // rbp
  __int64 v60; // rdi
  __int64 v61; // r9
  __int64 v62; // r8
  __int64 v63; // rax
  int *v64; // rax
  int *v65; // rbp
  __int64 v66; // r12
  __int64 v67; // rax
  int v68; // ecx
  unsigned int v69; // edi
  int v70; // eax
  int v71; // eax
  __int64 v72; // rax
  _DWORD *v73; // rcx
  int *v74; // [rsp+30h] [rbp-C8h]
  const char *v75; // [rsp+38h] [rbp-C0h]
  __int64 v76; // [rsp+40h] [rbp-B8h]
  int v77; // [rsp+48h] [rbp-B0h]
  int v78; // [rsp+4Ch] [rbp-ACh]
  _DWORD *v79; // [rsp+50h] [rbp-A8h]
  const char *v80; // [rsp+50h] [rbp-A8h]
  __int64 v81; // [rsp+58h] [rbp-A0h]
  unsigned int v82; // [rsp+60h] [rbp-98h]
  int v83; // [rsp+64h] [rbp-94h]
  int v84; // [rsp+68h] [rbp-90h]
  int v85; // [rsp+6Ch] [rbp-8Ch]
  int v86; // [rsp+70h] [rbp-88h]
  const char *v87; // [rsp+78h] [rbp-80h]
  __int64 v88; // [rsp+78h] [rbp-80h]
  const char *v89; // [rsp+80h] [rbp-78h]
  int v90; // [rsp+88h] [rbp-70h]
  int *v91; // [rsp+90h] [rbp-68h]
  _DWORD *v92; // [rsp+98h] [rbp-60h]
  char *v93; // [rsp+A0h] [rbp-58h]
  unsigned __int8 v94; // [rsp+100h] [rbp+8h]
  __int16 v95; // [rsp+100h] [rbp+8h]
  __int16 v97; // [rsp+110h] [rbp+18h]
  const char **v98; // [rsp+118h] [rbp+20h]
  _DWORD *v99; // [rsp+118h] [rbp+20h]
  int v100; // [rsp+118h] [rbp+20h]

  v2 = *a1;
  v3 = a2;
  v4 = *(_WORD *)(a2 + 4);
  v97 = v4;
  v6 = **a1;
  *(_DWORD *)(a2 + 4) |= 0x40u;
  if ( *(_BYTE *)(v6 + 103) )
    return 2;
  if ( (v4 & 0x40) != 0 )
    return 1;
  if ( *((_WORD *)a1 + 18) )
    *(_DWORD *)(a2 + 16) = ++*((_DWORD *)v2 + 37);
  v8 = *(int **)(a2 + 40);
  v92 = *(_DWORD **)(a2 + 32);
  if ( v2[51] && (*(_DWORD *)(a2 + 4) & 0x200000) != 0 )
  {
    v9 = *(_QWORD *)(a2 + 104);
    if ( !v9 )
    {
      v9 = sqlite3DbMallocZero(v6, 64);
      *(_QWORD *)(v3 + 104) = v9;
      if ( !v9 )
        return 2;
    }
    *(_DWORD *)(v9 + 4) = 1;
  }
  v10 = *(_QWORD *)(v3 + 104);
  if ( v10 && !*((_DWORD *)v2 + 12) )
  {
    *(_QWORD *)(v10 + 8) = v2[51];
    v2[51] = v10;
  }
  sqlite3SrcListAssignCursors(v2, v8);
  v11 = 0;
  for ( i = v8 + 2; ; i += 26 )
  {
    v79 = i;
    if ( v11 >= *v8 )
      break;
    if ( *((_QWORD *)i + 4) )
      goto LABEL_45;
    if ( !*((_QWORD *)i + 2) )
    {
      if ( (unsigned int)sqlite3WalkSelect(a1, *((_QWORD *)i + 5)) || (unsigned int)sqlite3ExpandSubquery(v2, i) )
        return 2;
      goto LABEL_43;
    }
    v13 = resolveFromTermToCte(v2, a1, i);
    if ( !v13 )
    {
      TableItem = sqlite3LocateTableItem(v2, 0, i);
      v98 = (const char **)TableItem;
      *((_QWORD *)i + 4) = TableItem;
      if ( !TableItem )
        return 2;
      v15 = *(_DWORD *)(TableItem + 44);
      if ( v15 >= 0xFFFF )
      {
        sqlite3ErrorMsg(v2, "too many references to \"%s\": max 65535", *(const char **)TableItem);
        *((_QWORD *)i + 4) = 0;
        return 2;
      }
      v16 = *(_BYTE *)(TableItem + 63) == 1;
      *(_DWORD *)(TableItem + 44) = v15 + 1;
      if ( !v16 )
      {
        if ( (unsigned int)cannotBeFunction(v2, i) )
          return 2;
        TableItem = (__int64)v98;
      }
      if ( !*(_BYTE *)(TableItem + 63) )
        goto LABEL_43;
      v94 = *((_BYTE *)a1 + 36);
      if ( (unsigned int)sqlite3ViewGetColumnNames(v2, TableItem) )
        return 2;
      v17 = v98;
      v18 = *((_BYTE *)v98 + 63);
      if ( v18 == 2 )
      {
        if ( (*(_DWORD *)(v6 + 48) & 0x80000000) == 0 && v98[12] != *(const char **)(*(_QWORD *)(v6 + 32) + 56LL) )
        {
          sqlite3ErrorMsg(v2, "access to view \"%s\" prohibited", *v98);
          v17 = v98;
        }
        *((_QWORD *)i + 5) = sqlite3SelectDup(v6, v17[8], 0);
LABEL_41:
        v17 = v98;
      }
      else if ( v18 == 1 && *((char *)i + 64) < 0 )
      {
        v19 = v98[10];
        if ( v19 )
        {
          if ( *((unsigned __int8 *)v19 + 30) > ((*(_DWORD *)(v6 + 48) >> 7) & 1u) )
          {
            sqlite3ErrorMsg(v2, "unsafe use of virtual table \"%s\"", *v98);
            goto LABEL_41;
          }
        }
      }
      v20 = *((_WORD *)v17 + 27);
      *((_WORD *)v17 + 27) = -1;
      *((_WORD *)a1 + 18) = 1;
      sqlite3WalkSelect(a1, *((_QWORD *)v79 + 5));
      *((_WORD *)a1 + 18) = v94;
      *((_WORD *)v98 + 27) = v20;
      i = v79;
      goto LABEL_43;
    }
    if ( v13 > 1 )
      return 2;
LABEL_43:
    if ( (i[16] & 2) != 0 && (unsigned int)sqlite3IndexedByLookup(v2, i) )
      return 2;
LABEL_45:
    ++v11;
  }
  if ( *((_DWORD *)v2 + 12) || (unsigned int)sqlite3ProcessJoin(v2, v3) )
    return 2;
  v21 = v92;
  v22 = 0;
  v23 = 0;
  v78 = 0;
  v24 = *v92;
  if ( (int)*v92 <= 0 )
  {
LABEL_54:
    if ( v23 < v24 )
      goto LABEL_55;
  }
  else
  {
    while ( 1 )
    {
      v25 = *(_QWORD *)&v92[8 * v23 + 2];
      if ( *(_BYTE *)v25 == 0xB4 || *(_BYTE *)v25 == 0x8D && **(_BYTE **)(v25 + 24) == 0xB4 )
        break;
      v22 |= *(_DWORD *)(v25 + 4);
      ++v23;
      v78 = v22;
      if ( v23 >= v24 )
        goto LABEL_54;
    }
LABEL_55:
    v26 = 0;
    v74 = 0;
    v90 = *(_DWORD *)(*v2 + 48) & 0x44;
    v27 = 0;
    v86 = 0;
    if ( v24 > 0 )
    {
      v28 = v8 + 2;
      do
      {
        v29 = &v21[8 * v27];
        v30 = (char *)*((_QWORD *)v29 + 1);
        v93 = v30;
        v31 = *v30;
        v78 = *((_DWORD *)v30 + 1) | v22;
        if ( *v30 != -76 && (v31 != -115 || **((_BYTE **)v30 + 3) != 0xB4) )
        {
          v32 = (int *)sqlite3ExprListAppend(v2, v26, v30);
          v74 = v32;
          v26 = v32;
          if ( v32 )
          {
            *(_QWORD *)&v32[8 * *v32 - 4] = *((_QWORD *)v29 + 2);
            v32[8 * *v32 - 1] ^= (v29[7] ^ v32[8 * *v32 - 1]) & 3;
            *((_QWORD *)v29 + 2) = 0;
          }
          *((_QWORD *)v29 + 1) = 0;
          goto LABEL_158;
        }
        v85 = 0;
        if ( v31 == -115 )
        {
          v33 = *(const char **)(*((_QWORD *)v30 + 2) + 8LL);
          v34 = *((_QWORD *)v30 + 3);
        }
        else
        {
          v33 = 0;
          v34 = *((_QWORD *)v29 + 1);
        }
        v35 = *v8;
        v75 = v33;
        v82 = *(_DWORD *)(v34 + 52);
        v77 = 0;
        v99 = v28;
        v84 = 0;
        if ( *v8 <= 0 )
          goto LABEL_154;
        v36 = v28;
        do
        {
          v37 = (const char *)*((_QWORD *)v36 + 3);
          v38 = *((_QWORD *)v36 + 4);
          v76 = v38;
          v80 = v37;
          if ( !v37 )
          {
            v37 = *(const char **)v38;
            v80 = *(const char **)v38;
          }
          if ( *(_BYTE *)(v6 + 103) )
            break;
          if ( (v36[16] & 0x2000) != 0 )
          {
            v89 = 0;
            v39 = *(_QWORD *)(*((_QWORD *)v36 + 5) + 32LL);
            v81 = v39;
          }
          else
          {
            if ( v33 )
            {
              v40 = sqlite3StrICmp(v33, v37);
              v26 = v74;
              v33 = v75;
              if ( v40 )
                goto LABEL_152;
              v38 = v76;
            }
            v81 = 0;
            v41 = sqlite3SchemaToIndex(v6, *(_QWORD *)(v38 + 96));
            v39 = 0;
            if ( v41 < 0 )
            {
              v89 = "*";
            }
            else
            {
              _mm_lfence();
              v89 = *(const char **)(32LL * v41 + *(_QWORD *)(v6 + 32));
            }
          }
          if ( v77 + 1 < v35 && (v36[42] & 0x400) != 0 && (v42 = v4 & 0x800, v95 = v4 & 0x800, (v4 & 0x800) != 0) )
          {
            v43 = 0;
            v91 = (int *)*((_QWORD *)v36 + 22);
            if ( *v91 > 0 )
            {
              v44 = v74;
              v45 = (_DWORD *)*((_QWORD *)v36 + 22);
              do
              {
                v87 = *(const char **)&v45[4 * v43 + 2];
                v46 = sqlite3Expr(v6, 59, v87);
                v47 = sqlite3ExprSetErrorOffset(v46, v82);
                v48 = (int *)sqlite3ExprListAppend(v2, v44, v47);
                v44 = v48;
                if ( v48 )
                {
                  v49 = &v48[8 * *v48 - 8];
                  v50 = sqlite3MPrintf(v6, "..%s", v87);
                  v49[7] &= ~1u;
                  v49[7] |= 0x82u;
                  *((_QWORD *)v49 + 2) = v50;
                }
                ++v43;
              }
              while ( v43 < *v45 );
              v3 = a2;
              v36 = v99;
              v42 = v95;
              v38 = v76;
              v33 = v75;
              v39 = v81;
              v74 = v44;
              v26 = v44;
              v4 = v97;
            }
          }
          else
          {
            v91 = 0;
            v42 = v4 & 0x800;
            v95 = v4 & 0x800;
          }
          v51 = *(__int16 *)(v38 + 54);
          v83 = v51;
          if ( (*(_DWORD *)(v38 + 48) & 0x200) == 0 && v42 )
            v83 = ++v51;
          v52 = 0;
          v100 = 0;
          if ( v51 > 0 )
          {
            while ( 1 )
            {
              if ( v52 == *(__int16 *)(v38 + 54) )
              {
                v53 = sqlite3RowidAlias(v38);
                v42 = v95;
                v54 = (const char *)v53;
                v33 = v75;
                v88 = v53;
                if ( !v53 )
                  goto LABEL_145;
              }
              else
              {
                v55 = v52;
                if ( v39 )
                {
                  v56 = 32LL * v52 + v39;
                  if ( (*(_BYTE *)(v56 + 28) & 3) == 3 )
                    goto LABEL_147;
                }
                else
                {
                  LODWORD(v56) = 32 * v52;
                }
                v57 = 24LL * v52;
                v54 = *(const char **)(24 * v55 + *(_QWORD *)(v38 + 8));
                v88 = (__int64)v54;
                if ( v33 )
                {
                  if ( v81 )
                  {
                    matched = sqlite3MatchEName((int)v56 + 8, 0, (_DWORD)v33, 0, 0);
                    v42 = v95;
                    v26 = v74;
                    v38 = v76;
                    v33 = v75;
                    if ( !matched )
                      goto LABEL_147;
                  }
                }
                if ( (*(_DWORD *)(v3 + 4) & 0x20000) == 0 && (*(_BYTE *)(*(_QWORD *)(v38 + 8) + v57 + 18) & 2) != 0
                  || (*(_WORD *)(*(_QWORD *)(v38 + 8) + v57 + 18) & 0x400) != 0 && !v33 && !v42 )
                {
                  goto LABEL_147;
                }
                v52 = v100;
              }
              v85 = 1;
              if ( v77 > 0
                && !v33
                && !v42
                && (v36[16] & 0x400) != 0
                && (int)sqlite3IdListIndex(*((_QWORD *)v36 + 9), v54) >= 0 )
              {
                goto LABEL_144;
              }
              v59 = sqlite3Expr(v6, 59, v54);
              if ( *v8 > 1
                && ((v36[15] & 0x40) == 0 || v95
                                          || !(unsigned int)inAnyUsingClause(v54, v36, (unsigned int)(*v8 + ~v84)))
                || *((_BYTE *)v2 + 308) >= 2u )
              {
                v60 = sqlite3Expr(v6, 59, v80);
                v59 = sqlite3PExpr(v2, 141, v60, v59);
                if ( *((_BYTE *)v2 + 308) >= 2u )
                {
                  v62 = *((_QWORD *)v93 + 2);
                  if ( v62 )
                    sqlite3RenameTokenRemap(v2, v60, v62, v61);
                }
                if ( v89 )
                {
                  v63 = sqlite3Expr(v6, 59, v89);
                  v59 = sqlite3PExpr(v2, 141, v63, v59);
                }
                v52 = v100;
              }
              sqlite3ExprSetErrorOffset(v59, v82);
              v64 = (int *)sqlite3ExprListAppend(v2, v74, v59);
              v74 = v64;
              v26 = v64;
              if ( !v64 )
              {
                v33 = v75;
LABEL_151:
                v4 = v97;
                break;
              }
              v65 = &v64[8 * *v64];
              if ( !v95 || *((_BYTE *)v2 + 308) >= 2u )
              {
                if ( v90 == 4 )
                  v72 = sqlite3MPrintf(v6, "%s.%s", v80, v54);
                else
                  v72 = sqlite3DbStrDup(v6, v54);
                *(v65 - 1) &= 0xFFFFFFFC;
                *((_QWORD *)v65 - 2) = v72;
LABEL_144:
                v33 = v75;
                v42 = v95;
LABEL_145:
                v38 = v76;
                goto LABEL_146;
              }
              if ( v81 )
              {
                v66 = v52;
                v67 = sqlite3DbStrDup(v6, *(_QWORD *)(32LL * v52 + v81 + 16));
              }
              else
              {
                v67 = sqlite3MPrintf(v6, "%s.%s.%s", v89, v80, v54);
                v66 = v52;
              }
              v38 = v76;
              v68 = v100;
              *((_QWORD *)v65 - 2) = v67;
              v69 = *(v65 - 1) & 0xFFFFFFFC | ((v100 == *(__int16 *)(v76 + 54)) + 2);
              *(v65 - 1) = v69;
              if ( (v36[16] & 0x400) != 0 )
              {
                v70 = sqlite3IdListIndex(*((_QWORD *)v36 + 9), v88);
                v38 = v76;
                if ( v70 >= 0 )
                  goto LABEL_139;
                v68 = v100;
              }
              if ( !v91 )
                goto LABEL_137;
              v71 = sqlite3IdListIndex(v91, v88);
              v38 = v76;
              if ( v71 < 0 )
              {
                v68 = v100;
LABEL_137:
                if ( v68 >= *(__int16 *)(v38 + 54) || (*(_WORD *)(*(_QWORD *)(v38 + 8) + 24 * v66 + 18) & 0x400) == 0 )
                  goto LABEL_140;
              }
LABEL_139:
              *(v65 - 1) = v69 | 0x100;
LABEL_140:
              v42 = v95;
              v33 = v75;
LABEL_146:
              v26 = v74;
LABEL_147:
              v39 = v81;
              v52 = ++v100;
              if ( v100 >= v83 )
                goto LABEL_151;
            }
          }
LABEL_152:
          v36 += 26;
          v35 = *v8;
          ++v77;
          v99 = v36;
          v84 = v77;
        }
        while ( v77 < *v8 );
        v28 = v8 + 2;
        v21 = v92;
        if ( !v85 )
        {
LABEL_154:
          if ( v33 )
            sqlite3ErrorMsg(v2, "no such table: %s", v33);
          else
            sqlite3ErrorMsg(v2, "no tables specified", 1024);
          v26 = v74;
        }
LABEL_158:
        v22 = v78;
        v27 = v86 + 1;
        v86 = v27;
      }
      while ( v27 < *v21 );
    }
    exprListDeleteNN(v6, v21);
    v22 = v78;
    *(_QWORD *)(v3 + 32) = v74;
  }
  v73 = *(_DWORD **)(v3 + 32);
  if ( v73 )
  {
    if ( *v73 > *(_DWORD *)(v6 + 144) )
    {
      sqlite3ErrorMsg(v2, "too many columns in result set");
      return 2;
    }
    if ( (v22 & 0x400008) != 0 )
      *(_DWORD *)(v3 + 4) |= 0x40000u;
  }
  return 0;
}

```

## disassembly

```asm
0x18002b9d0  mov     [rsp+arg_8], rdx
0x18002b9d5  push    rbx
0x18002b9d6  push    rbp
0x18002b9d7  push    rsi
0x18002b9d8  push    rdi
0x18002b9d9  push    r12
0x18002b9db  push    r13
0x18002b9dd  push    r14
0x18002b9df  push    r15
0x18002b9e1  sub     rsp, 0B8h
0x18002b9e8  mov     rsi, [rcx]
0x18002b9eb  mov     rbx, rdx
0x18002b9ee  movzx   ebp, word ptr [rdx+4]
0x18002b9f2  mov     r15, rcx
0x18002b9f5  mov     [rsp+0F8h+arg_10], bp
0x18002b9fd  mov     r13, [rsi]
0x18002ba00  or      dword ptr [rdx+4], 40h
0x18002ba04  cmp     byte ptr [r13+67h], 0
0x18002ba09  jnz     loc_18002BAF4
0x18002ba0f  test    bpl, 40h
0x18002ba13  jz      short loc_18002BA1F
0x18002ba15  mov     eax, 1
0x18002ba1a  jmp     loc_18002BAF9
0x18002ba1f  cmp     word ptr [rcx+24h], 0
0x18002ba24  jz      short loc_18002BA35
0x18002ba26  inc     dword ptr [rsi+94h]
0x18002ba2c  mov     eax, [rsi+94h]
0x18002ba32  mov     [rdx+10h], eax
0x18002ba35  cmp     qword ptr [rsi+198h], 0
0x18002ba3d  mov     rax, [rdx+20h]
0x18002ba41  mov     r14, [rdx+28h]
0x18002ba45  mov     [rsp+0F8h+var_60], rax
0x18002ba4d  jz      short loc_18002BA7E
0x18002ba4f  test    dword ptr [rdx+4], 200000h
0x18002ba56  jz      short loc_18002BA7E
0x18002ba58  mov     rax, [rdx+68h]
0x18002ba5c  test    rax, rax
0x18002ba5f  jnz     short loc_18002BA77
0x18002ba61  mov     edx, 40h ; '@'
0x18002ba66  mov     rcx, r13
0x18002ba69  call    sqlite3DbMallocZero
0x18002ba6e  mov     [rbx+68h], rax
0x18002ba72  test    rax, rax
0x18002ba75  jz      short loc_18002BAF4
0x18002ba77  mov     dword ptr [rax+4], 1
0x18002ba7e  mov     rcx, [rbx+68h]
0x18002ba82  test    rcx, rcx
0x18002ba85  jz      short loc_18002BA9F
0x18002ba87  cmp     dword ptr [rsi+30h], 0
0x18002ba8b  jnz     short loc_18002BA9F
0x18002ba8d  mov     rax, [rsi+198h]
0x18002ba94  mov     [rcx+8], rax
0x18002ba98  mov     [rsi+198h], rcx
0x18002ba9f  mov     rdx, r14
0x18002baa2  mov     rcx, rsi
0x18002baa5  call    sqlite3SrcListAssignCursors
0x18002baaa  xor     r12d, r12d
0x18002baad  lea     rdi, [r14+8]
0x18002bab1  mov     [rsp+0F8h+var_A8], rdi
0x18002bab6  cmp     r12d, [r14]
0x18002bab9  jge     loc_18002BCBE
0x18002babf  cmp     qword ptr [rdi+20h], 0
0x18002bac4  jnz     loc_18002BC93
0x18002baca  cmp     qword ptr [rdi+10h], 0
0x18002bacf  jnz     short loc_18002BB0D
0x18002bad1  mov     rdx, [rdi+28h]
0x18002bad5  mov     rcx, r15
0x18002bad8  call    sqlite3WalkSelect
0x18002badd  test    eax, eax
0x18002badf  jnz     short loc_18002BAF4
0x18002bae1  mov     rdx, rdi
0x18002bae4  mov     rcx, rsi
0x18002bae7  call    sqlite3ExpandSubquery
0x18002baec  test    eax, eax
0x18002baee  jz      loc_18002BC7A
0x18002baf4  mov     eax, 2
0x18002baf9  add     rsp, 0B8h
0x18002bb00  pop     r15
0x18002bb02  pop     r14
0x18002bb04  pop     r13
0x18002bb06  pop     r12
0x18002bb08  pop     rdi
0x18002bb09  pop     rsi
0x18002bb0a  pop     rbp
0x18002bb0b  pop     rbx
0x18002bb0c  retn
0x18002bb0d  mov     r8, rdi
0x18002bb10  mov     rdx, r15
0x18002bb13  mov     rcx, rsi
0x18002bb16  call    resolveFromTermToCte
0x18002bb1b  test    eax, eax
0x18002bb1d  jz      short loc_18002BB2A
0x18002bb1f  cmp     eax, 1
0x18002bb22  jle     loc_18002BC7A
0x18002bb28  jmp     short loc_18002BAF4
0x18002bb2a  mov     r8, rdi
0x18002bb2d  xor     edx, edx
0x18002bb2f  mov     rcx, rsi
0x18002bb32  call    sqlite3LocateTableItem
0x18002bb37  mov     [rsp+0F8h+arg_18], rax
0x18002bb3f  mov     [rdi+20h], rax
0x18002bb43  test    rax, rax
0x18002bb46  jz      short loc_18002BAF4
0x18002bb48  mov     ecx, [rax+2Ch]
0x18002bb4b  cmp     ecx, 0FFFFh
0x18002bb51  jnb     loc_18002BC9F
0x18002bb57  inc     ecx
0x18002bb59  cmp     byte ptr [rax+3Fh], 1
0x18002bb5d  mov     [rax+2Ch], ecx
0x18002bb60  jz      short loc_18002BB79
0x18002bb62  mov     rdx, rdi
0x18002bb65  mov     rcx, rsi
0x18002bb68  call    cannotBeFunction
0x18002bb6d  test    eax, eax
0x18002bb6f  jnz     short loc_18002BAF4
0x18002bb71  mov     rax, [rsp+0F8h+arg_18]
0x18002bb79  cmp     byte ptr [rax+3Fh], 0
0x18002bb7d  jz      loc_18002BC7A
0x18002bb83  movzx   ecx, byte ptr [r15+24h]
0x18002bb88  mov     rdx, rax
0x18002bb8b  mov     byte ptr [rsp+0F8h+arg_0], cl
0x18002bb92  mov     rcx, rsi
0x18002bb95  call    sqlite3ViewGetColumnNames
0x18002bb9a  test    eax, eax
0x18002bb9c  jnz     loc_18002BAF4
0x18002bba2  mov     rdx, [rsp+0F8h+arg_18]
0x18002bbaa  movzx   eax, byte ptr [rdx+3Fh]
0x18002bbae  cmp     al, 2
0x18002bbb0  jnz     short loc_18002BBFA
0x18002bbb2  mov     eax, [r13+30h]
0x18002bbb6  bt      rax, 1Fh
0x18002bbbb  jb      short loc_18002BBE5
0x18002bbbd  mov     rax, [r13+20h]
0x18002bbc1  mov     rcx, [rax+38h]
0x18002bbc5  cmp     [rdx+60h], rcx
0x18002bbc9  jz      short loc_18002BBE5
0x18002bbcb  mov     r8, [rdx]
0x18002bbce  mov     rcx, rsi
0x18002bbd1  lea     rdx, aAccessToViewSP; "access to view \"%s\" prohibited"
0x18002bbd8  call    sqlite3ErrorMsg
0x18002bbdd  mov     rdx, [rsp+0F8h+arg_18]
0x18002bbe5  mov     rdx, [rdx+40h]
0x18002bbe9  xor     r8d, r8d
0x18002bbec  mov     rcx, r13
0x18002bbef  call    sqlite3SelectDup
0x18002bbf4  mov     [rdi+28h], rax
0x18002bbf8  jmp     short loc_18002BC32
0x18002bbfa  cmp     al, 1
0x18002bbfc  jnz     short loc_18002BC3A
0x18002bbfe  test    byte ptr [rdi+40h], 80h
0x18002bc02  jz      short loc_18002BC3A
0x18002bc04  mov     rax, [rdx+50h]
0x18002bc08  test    rax, rax
0x18002bc0b  jz      short loc_18002BC3A
0x18002bc0d  mov     ecx, [r13+30h]
0x18002bc11  movzx   eax, byte ptr [rax+1Eh]
0x18002bc15  shr     rcx, 7
0x18002bc19  and     ecx, 1
0x18002bc1c  cmp     eax, ecx
0x18002bc1e  jbe     short loc_18002BC3A
0x18002bc20  mov     r8, [rdx]
0x18002bc23  mov     rcx, rsi
0x18002bc26  lea     rdx, aUnsafeUseOfVir; "unsafe use of virtual table \"%s\""
0x18002bc2d  call    sqlite3ErrorMsg
0x18002bc32  mov     rdx, [rsp+0F8h+arg_18]
0x18002bc3a  movzx   edi, word ptr [rdx+36h]
0x18002bc3e  mov     rcx, r15
0x18002bc41  mov     word ptr [rdx+36h], 0FFFFh
0x18002bc47  mov     rdx, [rsp+0F8h+var_A8]
0x18002bc4c  mov     word ptr [r15+24h], 1
0x18002bc53  mov     rdx, [rdx+28h]
0x18002bc57  call    sqlite3WalkSelect
0x18002bc5c  movzx   eax, byte ptr [rsp+0F8h+arg_0]
0x18002bc64  mov     [r15+24h], ax
0x18002bc69  mov     rax, [rsp+0F8h+arg_18]
0x18002bc71  mov     [rax+36h], di
0x18002bc75  mov     rdi, [rsp+0F8h+var_A8]
0x18002bc7a  test    byte ptr [rdi+40h], 2
0x18002bc7e  jz      short loc_18002BC93
0x18002bc80  mov     rdx, rdi
0x18002bc83  mov     rcx, rsi
0x18002bc86  call    sqlite3IndexedByLookup
0x18002bc8b  test    eax, eax
0x18002bc8d  jnz     loc_18002BAF4
0x18002bc93  inc     r12d
0x18002bc96  add     rdi, 68h ; 'h'
0x18002bc9a  jmp     loc_18002BAB1
0x18002bc9f  mov     r8, [rax]
0x18002bca2  lea     rdx, aTooManyReferen; "too many references to \"%s\": max 6553"...
0x18002bca9  mov     rcx, rsi
0x18002bcac  call    sqlite3ErrorMsg
0x18002bcb1  mov     qword ptr [rdi+20h], 0
0x18002bcb9  jmp     loc_18002BAF4
0x18002bcbe  cmp     dword ptr [rsi+30h], 0
0x18002bcc2  jnz     loc_18002BAF4
0x18002bcc8  mov     rdx, rbx
0x18002bccb  mov     rcx, rsi
0x18002bcce  call    sqlite3ProcessJoin
0x18002bcd3  test    eax, eax
0x18002bcd5  jnz     loc_18002BAF4
0x18002bcdb  mov     r15, [rsp+0F8h+var_60]
0x18002bce3  xor     r10d, r10d
0x18002bce6  xor     ecx, ecx
0x18002bce8  mov     [rsp+0F8h+var_AC], r10d
0x18002bced  mov     edx, [r15]
0x18002bcf0  test    edx, edx
0x18002bcf2  jle     short loc_18002BD23
0x18002bcf4  mov     eax, ecx
0x18002bcf6  shl     rax, 5
0x18002bcfa  mov     r8, [rax+r15+8]
0x18002bcff  movzx   eax, byte ptr [r8]
0x18002bd03  cmp     al, 0B4h
0x18002bd05  jz      short loc_18002BD2B
0x18002bd07  cmp     al, 8Dh
0x18002bd09  jnz     short loc_18002BD14
0x18002bd0b  mov     rax, [r8+18h]
0x18002bd0f  cmp     byte ptr [rax], 0B4h
0x18002bd12  jz      short loc_18002BD2B
0x18002bd14  or      r10d, [r8+4]
0x18002bd18  inc     ecx
0x18002bd1a  mov     [rsp+0F8h+var_AC], r10d
0x18002bd1f  cmp     ecx, edx
0x18002bd21  jl      short loc_18002BCF4
0x18002bd23  cmp     ecx, edx
0x18002bd25  jge     loc_18002C4D6
0x18002bd2b  mov     rax, [rsi]
0x18002bd2e  xor     r9d, r9d
0x18002bd31  mov     [rsp+0F8h+var_C8], r9
0x18002bd36  mov     eax, [rax+30h]
0x18002bd39  and     eax, 44h
0x18002bd3c  mov     [rsp+0F8h+var_70], eax
0x18002bd43  xor     eax, eax
0x18002bd45  mov     [rsp+0F8h+var_88], eax
0x18002bd49  test    edx, edx
0x18002bd4b  jle     loc_18002C4BD
0x18002bd51  mov     r8d, 400h
0x18002bd57  lea     rdi, [r14+8]
0x18002bd5b  movsxd  r12, eax
0x18002bd5e  shl     r12, 5
0x18002bd62  add     r12, r15
0x18002bd65  mov     rdx, [r12+8]
0x18002bd6a  mov     [rsp+0F8h+var_58], rdx
0x18002bd72  or      r10d, [rdx+4]
0x18002bd76  movzx   ecx, byte ptr [rdx]
0x18002bd79  mov     [rsp+0F8h+var_AC], r10d
0x18002bd7e  cmp     cl, 0B4h
0x18002bd81  jz      short loc_18002BDED
0x18002bd83  cmp     cl, 8Dh
0x18002bd86  jnz     short loc_18002BD91
0x18002bd88  mov     rax, [rdx+18h]
0x18002bd8c  cmp     byte ptr [rax], 0B4h
0x18002bd8f  jz      short loc_18002BDED
0x18002bd91  mov     r8, rdx
0x18002bd94  mov     rcx, rsi
0x18002bd97  mov     rdx, r9
0x18002bd9a  call    sqlite3ExprListAppend
0x18002bd9f  mov     [rsp+0F8h+var_C8], rax
0x18002bda4  mov     r9, rax
0x18002bda7  test    rax, rax
0x18002bdaa  jz      short loc_18002BDDF
0x18002bdac  movsxd  rcx, dword ptr [rax]
0x18002bdaf  mov     rax, [r12+10h]
0x18002bdb4  shl     rcx, 5
0x18002bdb8  mov     [rcx+r9-10h], rax
0x18002bdbd  movsxd  rdx, dword ptr [r9]
0x18002bdc0  shl     rdx, 5
0x18002bdc4  mov     ecx, [rdx+r9-4]
0x18002bdc9  xor     ecx, [r12+1Ch]
0x18002bdce  and     ecx, 3
0x18002bdd1  xor     [rdx+r9-4], ecx
0x18002bdd6  mov     qword ptr [r12+10h], 0
0x18002bddf  mov     qword ptr [r12+8], 0
0x18002bde8  jmp     loc_18002C49F
0x18002bded  xor     eax, eax
0x18002bdef  mov     [rsp+0F8h+var_8C], eax
0x18002bdf3  cmp     cl, 8Dh
0x18002bdf6  jnz     short loc_18002BE06
0x18002bdf8  mov     rax, [rdx+10h]
0x18002bdfc  mov     r11, [rax+8]
0x18002be00  mov     rax, [rdx+18h]
0x18002be04  jmp     short loc_18002BE0C
0x18002be06  xor     r11d, r11d
0x18002be09  mov     rax, rdx
0x18002be0c  mov     r12d, [r14]
0x18002be0f  mov     eax, [rax+34h]
0x18002be12  mov     [rsp+0F8h+var_C0], r11
0x18002be17  mov     [rsp+0F8h+var_98], eax
0x18002be1b  mov     [rsp+0F8h+var_B0], 0
0x18002be23  mov     [rsp+0F8h+arg_18], rdi
0x18002be2b  mov     [rsp+0F8h+var_90], 0
0x18002be33  test    r12d, r12d
0x18002be36  jle     loc_18002C475
0x18002be3c  mov     r15, rdi
0x18002be3f  mov     rax, [r15+18h]
0x18002be43  mov     r10, [r15+20h]
0x18002be47  mov     [rsp+0F8h+var_B8], r10
0x18002be4c  mov     [rsp+0F8h+var_A8], rax
0x18002be51  test    rax, rax
0x18002be54  jnz     short loc_18002BE5E
0x18002be56  mov     rax, [r10]
  ... truncated ...
```

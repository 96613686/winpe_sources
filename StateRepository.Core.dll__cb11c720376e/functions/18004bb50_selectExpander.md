# selectExpander

- ea: `0x18004bb50`
- end: `0x18004c6a3`
- name: `selectExpander`
- size: `2899`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: ``

## callees

- `0x1800055cc`
- `0x18000c930`
- `0x18000e5c0`
- `0x18000f720`
- `0x180010950`
- `0x180013bc0`
- `0x1800143f0`
- `0x180018600`
- `0x1800256c4`
- `0x18003465c`
- `0x18003a828`
- `0x18003f6dc`
- `0x18003fe98`
- `0x18004bb50`
- `0x18004c6b0`
- `0x18004c728`
- `0x180060868`
- `0x180060c3c`
- `0x180060ce8`
- `0x1800610f0`
- `0x180065f64`
- `0x180067d94`
- `0x180068404`
- `0x180071c48`
- `0x1800846f0`
- `0x180085018`
- `0x180086fcc`

## string_xrefs

- `0x18004bf2c`: `access to view "%s" prohibited`

## pseudocode

```c
__int64 __fastcall selectExpander(__int64 **a1, __int64 a2)
{
  __int64 *v2; // rsi
  __int16 v3; // ax
  __int64 v4; // rbp
  __int64 v6; // r13
  int *v7; // r8
  __int64 v8; // rcx
  int *v9; // r8
  int v10; // r12d
  _DWORD *v11; // rdi
  int v12; // eax
  __int64 v13; // r10
  _DWORD *v14; // rdi
  __int64 v15; // r8
  int i; // ecx
  _DWORD *v17; // rcx
  __int64 v19; // rdx
  int *v20; // r12
  int v21; // eax
  int v22; // eax
  __int64 TableItem; // rax
  __int64 v24; // rbx
  unsigned int v25; // eax
  __int16 v26; // r13
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rcx
  int *v31; // rax
  const char *v32; // rbx
  __int64 v33; // rax
  int v34; // edi
  _DWORD *v35; // r14
  int v36; // r11d
  const char *v37; // rax
  __int64 v38; // r9
  int v39; // eax
  int v40; // eax
  __int16 v41; // bx
  int v42; // edi
  _DWORD *v43; // rbp
  const char *v44; // r14
  __int64 v45; // rax
  __int64 v46; // rax
  int *v47; // rax
  __int64 v48; // rbx
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rax
  const char *v53; // r13
  const char *v54; // rdi
  __int64 v55; // rcx
  __int64 v56; // rbx
  int matched; // eax
  bool v58; // zf
  int v59; // eax
  __int64 v60; // rdi
  __int64 v61; // r14
  __int64 v62; // rbx
  __int64 v63; // r9
  __int64 v64; // r8
  __int64 v65; // rax
  int *v66; // rax
  __int64 v67; // rbx
  __int64 v68; // r14
  __int64 v69; // rax
  unsigned int v70; // edx
  unsigned int v71; // edi
  int v72; // eax
  int v73; // eax
  __int64 v74; // rax
  __int64 v75; // [rsp+30h] [rbp-C8h]
  int v76; // [rsp+38h] [rbp-C0h]
  unsigned int v77; // [rsp+3Ch] [rbp-BCh]
  __int64 v78; // [rsp+40h] [rbp-B8h]
  int *v79; // [rsp+48h] [rbp-B0h]
  unsigned int v80; // [rsp+50h] [rbp-A8h]
  int v81; // [rsp+54h] [rbp-A4h]
  int v82; // [rsp+58h] [rbp-A0h]
  int v83; // [rsp+5Ch] [rbp-9Ch]
  int v84; // [rsp+60h] [rbp-98h]
  int v85; // [rsp+64h] [rbp-94h]
  const char *v86; // [rsp+68h] [rbp-90h]
  _DWORD *v87; // [rsp+70h] [rbp-88h]
  const char *v88; // [rsp+78h] [rbp-80h]
  const char *v89; // [rsp+80h] [rbp-78h]
  _DWORD *v90; // [rsp+88h] [rbp-70h]
  __int64 v91; // [rsp+90h] [rbp-68h]
  _DWORD *v92; // [rsp+98h] [rbp-60h]
  _DWORD *v93; // [rsp+A0h] [rbp-58h]
  __int64 v94; // [rsp+A8h] [rbp-50h]
  unsigned __int8 v95; // [rsp+100h] [rbp+8h]
  __int16 v96; // [rsp+100h] [rbp+8h]
  __int16 v98; // [rsp+110h] [rbp+18h]
  unsigned int v99; // [rsp+118h] [rbp+20h]

  v2 = *a1;
  v3 = *(_WORD *)(a2 + 4);
  v4 = a2;
  v98 = v3;
  v6 = **a1;
  *(_DWORD *)(a2 + 4) |= 0x40u;
  v78 = v6;
  if ( *(_BYTE *)(v6 + 103) )
    return 2;
  if ( (v3 & 0x40) != 0 )
    return 1;
  if ( *((_WORD *)a1 + 18) )
    *(_DWORD *)(a2 + 16) = ++*((_DWORD *)v2 + 37);
  v7 = *(int **)(a2 + 40);
  v79 = v7;
  v90 = *(_DWORD **)(a2 + 32);
  if ( v2[51] && (*(_DWORD *)(a2 + 4) & 0x200000) != 0 )
  {
    v28 = *(_QWORD *)(a2 + 104);
    if ( !v28 )
    {
      v28 = sqlite3DbMallocZero(v6, 64);
      *(_QWORD *)(v4 + 104) = v28;
      if ( !v28 )
        return 2;
      v7 = v79;
    }
    *(_DWORD *)(v28 + 4) = 1;
  }
  v8 = *(_QWORD *)(v4 + 104);
  if ( v8 && !*((_DWORD *)v2 + 13) )
  {
    *(_QWORD *)(v8 + 8) = v2[51];
    v2[51] = v8;
  }
  sqlite3SrcListAssignCursors(v2, v7);
  v10 = 0;
  v93 = v9 + 2;
  v11 = v9 + 2;
  while ( v10 < *v9 )
  {
    if ( !*((_QWORD *)v11 + 2) )
    {
      if ( *(_QWORD *)v11 )
      {
        v22 = resolveFromTermToCte(v2, a1, v11);
        if ( v22 )
        {
          if ( v22 > 1 )
            return 2;
        }
        else
        {
          TableItem = sqlite3LocateTableItem(v2, 0, v11);
          *((_QWORD *)v11 + 2) = TableItem;
          v24 = TableItem;
          if ( !TableItem )
            return 2;
          v25 = *(_DWORD *)(TableItem + 44);
          if ( v25 >= 0xFFFF )
          {
            sqlite3ErrorMsg(v2, "too many references to \"%s\": max 65535", *(const char **)v24);
            *((_QWORD *)v11 + 2) = 0;
            return 2;
          }
          *(_DWORD *)(v24 + 44) = v25 + 1;
          if ( *(_BYTE *)(v24 + 63) != 1 && (unsigned int)cannotBeFunction(v2, v11) )
            return 2;
          if ( *(_BYTE *)(v24 + 63) )
          {
            v95 = *((_BYTE *)a1 + 36);
            if ( (unsigned int)sqlite3ViewGetColumnNames(v2, v24) )
              return 2;
            if ( *(_BYTE *)(v24 + 63) == 2 )
            {
              if ( (*(_DWORD *)(v6 + 48) & 0x80000000) == 0
                && *(_QWORD *)(v24 + 96) != *(_QWORD *)(*(_QWORD *)(v6 + 32) + 56LL) )
              {
                sqlite3ErrorMsg(v2, "access to view \"%s\" prohibited", *(const char **)v24);
              }
              sqlite3SrcItemAttachSubquery(v2, v11, *(_QWORD *)(v24 + 64), 1);
            }
            else if ( *(_BYTE *)(v24 + 63) == 1 && (v11[7] & 0x100) != 0 )
            {
              v27 = *(_QWORD *)(v24 + 80);
              if ( v27 )
              {
                if ( *(unsigned __int8 *)(v27 + 30) > ((*(_DWORD *)(v6 + 48) >> 7) & 1u) )
                  sqlite3ErrorMsg(v2, "unsafe use of virtual table \"%s\"", *(const char **)v24);
              }
            }
            v26 = *(_WORD *)(v24 + 54);
            *(_WORD *)(v24 + 54) = -1;
            *((_WORD *)a1 + 18) = 1;
            if ( (v11[7] & 4) != 0 )
              sqlite3WalkSelect(a1, **((_QWORD **)v11 + 9));
            *((_WORD *)a1 + 18) = v95;
            *(_WORD *)(v24 + 54) = v26;
            v6 = v78;
          }
        }
      }
      else if ( (unsigned int)sqlite3WalkSelect(a1, **((_QWORD **)v11 + 9))
             || (unsigned int)sqlite3ExpandSubquery(v2, v11) )
      {
        return 2;
      }
      if ( (v11[7] & 2) != 0 && (unsigned int)sqlite3IndexedByLookup(v2, v11) )
        return 2;
      v9 = v79;
    }
    ++v10;
    v11 += 20;
  }
  if ( *((_DWORD *)v2 + 13) )
    return 2;
  v12 = sqlite3ProcessJoin(v2, v4);
  v13 = 0;
  if ( v12 )
    return 2;
  v14 = v90;
  v15 = 0;
  v77 = 0;
  for ( i = 0; i < *v90; v77 = v15 )
  {
    v19 = *(_QWORD *)&v90[8 * i + 2];
    if ( *(_BYTE *)v19 == 0xB4 || *(_BYTE *)v19 == 0x8E && **(_BYTE **)(v19 + 24) == 0xB4 )
      goto LABEL_20;
    v15 = *(_DWORD *)(v19 + 4) | (unsigned int)v15;
    ++i;
  }
  if ( i < *v90 )
  {
LABEL_20:
    v20 = 0;
    if ( (*(_BYTE *)(*v2 + 48) & 4) == 0 || (v81 = 1, (*(_BYTE *)(*v2 + 48) & 0x40) != 0) )
      v81 = 0;
    v21 = 0;
    v85 = 0;
    if ( (int)*v90 <= 0 )
    {
LABEL_23:
      sqlite3ExprListDeleteGeneric(v6, v14);
      v15 = v77;
      *(_QWORD *)(v4 + 32) = v20;
      goto LABEL_13;
    }
LABEL_73:
    v29 = 8LL * v21;
    v30 = *(_QWORD *)&v14[v29 + 2];
    v94 = v30;
    v77 = *(_DWORD *)(v30 + 4) | v15;
    if ( *(_BYTE *)v30 != 0xB4 && (*(_BYTE *)v30 != 0x8E || **(_BYTE **)(v30 + 24) != 0xB4) )
    {
      v31 = (int *)sqlite3ExprListAppend(v2, v20, v30);
      v13 = 0;
      v20 = v31;
      if ( v31 )
      {
        *(_QWORD *)&v31[8 * *v31 - 4] = *(_QWORD *)&v14[v29 + 4];
        v31[8 * *v31 - 1] ^= (v14[v29 + 7] ^ v31[8 * *v31 - 1]) & 3;
        *(_QWORD *)&v14[v29 + 4] = 0;
      }
      *(_QWORD *)&v14[v29 + 2] = 0;
      goto LABEL_170;
    }
    v84 = v13;
    if ( *(_BYTE *)v30 == 0x8E )
    {
      v32 = *(const char **)(*(_QWORD *)(v30 + 16) + 8LL);
      v33 = *(_QWORD *)(v30 + 24);
    }
    else
    {
      v32 = (const char *)v13;
      v33 = v30;
    }
    v34 = v13;
    v35 = v93;
    v80 = *(_DWORD *)(v33 + 52);
    v86 = v32;
    v76 = v13;
    v87 = v93;
    v36 = *v79;
    v83 = v13;
    if ( *v79 <= 0 )
    {
LABEL_165:
      if ( v32 )
        sqlite3ErrorMsg(v2, "no such table: %s", v32);
      else
        sqlite3ErrorMsg(v2, "no tables specified");
      v13 = 0;
      goto LABEL_169;
    }
    while ( 1 )
    {
      v37 = (const char *)*((_QWORD *)v35 + 1);
      v38 = *((_QWORD *)v35 + 2);
      v75 = v38;
      v89 = v37;
      if ( !v37 )
      {
        v37 = *(const char **)v38;
        v89 = *(const char **)v38;
      }
      if ( *(_BYTE *)(v6 + 103) != (_BYTE)v13 )
      {
LABEL_164:
        if ( !v84 )
          goto LABEL_165;
LABEL_169:
        v14 = v90;
LABEL_170:
        LODWORD(v15) = v77;
        v21 = v85 + 1;
        v85 = v21;
        if ( v21 >= *v14 )
          goto LABEL_23;
        goto LABEL_73;
      }
      if ( (v35[7] & 0x4000) != 0 )
      {
        v88 = (const char *)v13;
        v91 = *(_QWORD *)(**((_QWORD **)v35 + 9) + 32LL);
        v13 = 0;
      }
      else
      {
        if ( v32 )
        {
          v39 = sqlite3StrICmp(v32, v37);
          v13 = 0;
          if ( v39 )
            goto LABEL_163;
          v38 = v75;
        }
        v91 = v13;
        v40 = sqlite3SchemaToIndex(v6, *(_QWORD *)(v38 + 96));
        if ( v40 < 0 )
        {
          v88 = "*";
        }
        else
        {
          _mm_lfence();
          v88 = *(const char **)(32LL * v40 + *(_QWORD *)(v6 + 32));
        }
      }
      if ( v34 + 1 < v36 && (v35[27] & 0x800) != 0 && (v41 = v98 & 0x800, v96 = v98 & 0x800, (v98 & 0x800) != 0) )
      {
        v42 = v13;
        v92 = (_DWORD *)*((_QWORD *)v35 + 18);
        if ( *v92 > (int)v13 )
        {
          v43 = (_DWORD *)*((_QWORD *)v35 + 18);
          do
          {
            v44 = *(const char **)&v43[4 * v42 + 2];
            v45 = sqlite3Expr(v6, 60, v44);
            v46 = sqlite3ExprSetErrorOffset(v45, v80);
            v47 = (int *)sqlite3ExprListAppend(v2, v20, v46);
            v13 = 0;
            v20 = v47;
            if ( v47 )
            {
              v48 = 8 * (*v47 - 1LL);
              v49 = sqlite3MPrintf(v6, "..%s", v44);
              v20[v48 + 7] &= ~1u;
              v20[v48 + 7] |= 0x82u;
              v13 = 0;
              *(_QWORD *)&v20[v48 + 4] = v49;
            }
            ++v42;
          }
          while ( v42 < *v43 );
          v4 = a2;
          v35 = v87;
          v41 = v98 & 0x800;
          v38 = v75;
        }
        v34 = v76;
      }
      else
      {
        v41 = v98 & 0x800;
        v92 = (_DWORD *)v13;
        v96 = v98 & 0x800;
      }
      v50 = *(__int16 *)(v38 + 54);
      v82 = v50;
      if ( (*(_DWORD *)(v38 + 48) & 0x200) == 0 && v41 )
        v82 = ++v50;
      v51 = (unsigned int)v13;
      v99 = v13;
      if ( v50 > 0 )
      {
        while ( 1 )
        {
          if ( (_DWORD)v51 == *(__int16 *)(v38 + 54) )
          {
            v52 = sqlite3RowidAlias(v38);
            v13 = 0;
            v53 = (const char *)v52;
            if ( !v52 )
              goto LABEL_159;
            v54 = v86;
          }
          else
          {
            v55 = 32 * v51;
            if ( v91 && (*(_BYTE *)(v55 + v91 + 28) & 3) == 3 )
              goto LABEL_160;
            v56 = 3 * v51;
            v54 = v86;
            v53 = *(const char **)(*(_QWORD *)(v38 + 8) + 24 * v51);
            if ( v86 )
            {
              if ( v91 )
              {
                matched = sqlite3MatchEName((int)v91 + 8 + (int)v55, 0, (_DWORD)v86, 0, v13);
                v38 = v75;
                v13 = 0;
                if ( !matched )
                  goto LABEL_148;
              }
            }
            if ( (*(_DWORD *)(v4 + 4) & 0x20000) == 0 && (*(_BYTE *)(*(_QWORD *)(v38 + 8) + 8 * v56 + 18) & 2) != 0 )
              goto LABEL_148;
            v58 = (*(_WORD *)(*(_QWORD *)(v38 + 8) + 8 * v56 + 18) & 0x400) == 0;
            v41 = v96;
            if ( !v58 && !v86 && !v96 )
              goto LABEL_160;
          }
          v84 = 1;
          if ( v76 > (int)v13 && !v54 && !v41 && (v35[7] & 0x800) != 0 )
          {
            v59 = sqlite3IdListIndex(*((_QWORD *)v35 + 8), v53);
            v13 = 0;
            if ( v59 >= 0 )
              goto LABEL_159;
          }
          v60 = sqlite3Expr(v78, 60, v53);
          if ( (*v79 <= 1
             || (v35[6] & 0x40) != 0 && !v41 && (unsigned int)inAnyUsingClause(v53, v35, (unsigned int)(*v79 + ~v83)))
            && *((_BYTE *)v2 + 308) < 2u )
          {
            v61 = v78;
          }
          else
          {
            v61 = v78;
            v62 = sqlite3Expr(v78, 60, v89);
            v60 = sqlite3PExpr(v2, 142, v62);
            if ( *((_BYTE *)v2 + 308) >= 2u )
            {
              v64 = *(_QWORD *)(v94 + 16);
              if ( v64 )
                sqlite3RenameTokenRemap(v2, v62, v64, v63);
            }
            if ( v88 )
            {
              v65 = sqlite3Expr(v78, 60, v88);
              v60 = sqlite3PExpr(v2, 142, v65);
            }
          }
          sqlite3ExprSetErrorOffset(v60, v80);
          v66 = (int *)sqlite3ExprListAppend(v2, v20, v60);
          v13 = 0;
          v20 = v66;
          if ( !v66 )
          {
LABEL_161:
            v35 = v87;
            v6 = v78;
            v34 = v76;
            break;
          }
          v67 = 8LL * *v66;
          if ( !v96 || *((_BYTE *)v2 + 308) >= 2u )
          {
            if ( v81 )
              v74 = sqlite3MPrintf(v61, "%s.%s", v89, v53);
            else
              v74 = sqlite3DbStrDup(v61, v53);
            v20[v67 - 1] &= 0xFFFFFFFC;
            *(_QWORD *)&v20[v67 - 4] = v74;
            v13 = 0;
            v41 = v96;
LABEL_159:
            v38 = v75;
            goto LABEL_160;
          }
          if ( v91 )
          {
            v68 = v99;
            v69 = sqlite3DbStrDup(v78, *(_QWORD *)(32LL * v99 + v91 + 16));
            v70 = v99;
          }
          else
          {
            v69 = sqlite3MPrintf(v61, "%s.%s.%s", v88, v89, v53);
            v70 = v99;
            v68 = v99;
          }
          *(_QWORD *)&v20[v67 - 4] = v69;
          v71 = v20[v67 - 1] & 0xFFFFFFFC | (3 - (*(__int16 *)(v75 + 54) != v70));
          v20[v67 - 1] = v71;
          if ( (v87[7] & 0x800) != 0 )
          {
            v72 = sqlite3IdListIndex(*((_QWORD *)v87 + 8), v53);
            v13 = 0;
            if ( v72 >= 0 )
              goto LABEL_146;
          }
          else
          {
            v13 = 0;
          }
          if ( !v92 || (v73 = sqlite3IdListIndex(v92, v53), v13 = 0, v73 < 0) )
          {
            v38 = v75;
            if ( (int)v99 >= *(__int16 *)(v75 + 54) || (*(_WORD *)(*(_QWORD *)(v75 + 8) + 24 * v68 + 18) & 0x400) == 0 )
              goto LABEL_148;
            goto LABEL_147;
          }
LABEL_146:
          v38 = v75;
LABEL_147:
          v20[v67 - 1] = v71 | 0x100;
LABEL_148:
          v41 = v96;
LABEL_160:
          v35 = v87;
          v51 = v99 + 1;
          v99 = v51;
          if ( (int)v51 >= v82 )
            goto LABEL_161;
        }
      }
      v32 = v86;
LABEL_163:
      ++v34;
      v35 += 20;
      v76 = v34;
      v87 = v35;
      v83 = v34;
      v36 = *v79;
      if ( v34 >= *v79 )
        goto LABEL_164;
    }
  }
LABEL_13:
  v17 = *(_DWORD **)(v4 + 32);
  if ( v17 )
  {
    if ( *v17 > *(_DWORD *)(v6 + 144) )
    {
      sqlite3ErrorMsg(v2, "too many columns in result set", v15);
      return 2;
    }
    if ( (v15 & 0x400008) != 0 )
      *(_DWORD *)(v4 + 4) |= 0x40000u;
  }
  return 0;
}

```

## disassembly

```asm
0x18004bb50  mov     [rsp+arg_8], rdx
0x18004bb55  push    rbx
0x18004bb56  push    rbp
0x18004bb57  push    rsi
0x18004bb58  push    rdi
0x18004bb59  push    r12
0x18004bb5b  push    r13
0x18004bb5d  push    r14
0x18004bb5f  push    r15
0x18004bb61  sub     rsp, 0B8h
0x18004bb68  mov     rsi, [rcx]
0x18004bb6b  xor     ebx, ebx
0x18004bb6d  movzx   eax, word ptr [rdx+4]
0x18004bb71  mov     rbp, rdx
0x18004bb74  mov     r14, rcx
0x18004bb77  mov     [rsp+0F8h+arg_10], ax
0x18004bb7f  mov     r13, [rsi]
0x18004bb82  or      dword ptr [rdx+4], 40h
0x18004bb86  mov     [rsp+0F8h+var_B8], r13
0x18004bb8b  cmp     [r13+67h], bl
0x18004bb8f  jnz     loc_18004BE08
0x18004bb95  test    al, 40h
0x18004bb97  jnz     loc_18004BE6D
0x18004bb9d  lea     r15d, [rbx+1]
0x18004bba1  cmp     [rcx+24h], bx
0x18004bba5  jnz     loc_18004BE77
0x18004bbab  mov     r8, [rdx+28h]
0x18004bbaf  mov     rax, [rdx+20h]
0x18004bbb3  mov     [rsp+0F8h+var_B0], r8
0x18004bbb8  mov     [rsp+0F8h+var_70], rax
0x18004bbc0  cmp     [rsi+198h], rbx
0x18004bbc7  jnz     loc_18004BE8C
0x18004bbcd  mov     rcx, [rbp+68h]
0x18004bbd1  test    rcx, rcx
0x18004bbd4  jnz     loc_18004BEC8
0x18004bbda  mov     rdx, r8
0x18004bbdd  mov     rcx, rsi
0x18004bbe0  call    sqlite3SrcListAssignCursors
0x18004bbe5  lea     rax, [r8+8]
0x18004bbe9  mov     r12d, ebx
0x18004bbec  mov     [rsp+0F8h+var_58], rax
0x18004bbf4  mov     rdi, rax
0x18004bbf7  cmp     r12d, [r8]
0x18004bbfa  jl      loc_18004BCCC
0x18004bc00  cmp     [rsi+34h], ebx
0x18004bc03  jnz     loc_18004BE08
0x18004bc09  mov     rdx, rbp
0x18004bc0c  mov     rcx, rsi
0x18004bc0f  call    sqlite3ProcessJoin
0x18004bc14  xor     r10d, r10d
0x18004bc17  test    eax, eax
0x18004bc19  jnz     loc_18004BE08
0x18004bc1f  mov     rdi, [rsp+0F8h+var_70]
0x18004bc27  mov     r8d, r10d
0x18004bc2a  mov     [rsp+0F8h+var_BC], r10d
0x18004bc2f  mov     ecx, r10d
0x18004bc32  cmp     [rdi], r10d
0x18004bc35  jg      short loc_18004BC5E
0x18004bc37  cmp     ecx, [rdi]
0x18004bc39  jl      short loc_18004BC8E
0x18004bc3b  mov     rcx, [rbp+20h]
0x18004bc3f  test    rcx, rcx
0x18004bc42  jnz     loc_18004BD4E
0x18004bc48  xor     eax, eax
0x18004bc4a  add     rsp, 0B8h
0x18004bc51  pop     r15
0x18004bc53  pop     r14
0x18004bc55  pop     r13
0x18004bc57  pop     r12
0x18004bc59  pop     rdi
0x18004bc5a  pop     rsi
0x18004bc5b  pop     rbp
0x18004bc5c  pop     rbx
0x18004bc5d  retn
0x18004bc5e  mov     eax, ecx
0x18004bc60  shl     rax, 5
0x18004bc64  mov     rdx, [rax+rdi+8]
0x18004bc69  cmp     byte ptr [rdx], 0B4h
0x18004bc6c  jz      short loc_18004BC8E
0x18004bc6e  cmp     byte ptr [rdx], 8Eh
0x18004bc71  jnz     short loc_18004BC7C
0x18004bc73  mov     rax, [rdx+18h]
0x18004bc77  cmp     byte ptr [rax], 0B4h
0x18004bc7a  jz      short loc_18004BC8E
0x18004bc7c  or      r8d, [rdx+4]
0x18004bc80  add     ecx, r15d
0x18004bc83  mov     [rsp+0F8h+var_BC], r8d
0x18004bc88  cmp     ecx, [rdi]
0x18004bc8a  jge     short loc_18004BC37
0x18004bc8c  jmp     short loc_18004BC5E
0x18004bc8e  mov     rax, [rsi]
0x18004bc91  mov     r12, r10
0x18004bc94  test    byte ptr [rax+30h], 4
0x18004bc98  jnz     loc_18004BF8B
0x18004bc9e  mov     [rsp+0F8h+var_A4], r10d
0x18004bca3  mov     eax, r10d
0x18004bca6  mov     [rsp+0F8h+var_94], eax
0x18004bcaa  cmp     [rdi], r10d
0x18004bcad  jg      loc_18004BF9F
0x18004bcb3  mov     rdx, rdi
0x18004bcb6  mov     rcx, r13
0x18004bcb9  call    sqlite3ExprListDeleteGeneric
0x18004bcbe  mov     r8d, [rsp+0F8h+var_BC]
0x18004bcc3  mov     [rbp+20h], r12
0x18004bcc7  jmp     loc_18004BC3B
0x18004bccc  cmp     [rdi+10h], rbx
0x18004bcd0  jnz     short loc_18004BD42
0x18004bcd2  cmp     [rdi], rbx
0x18004bcd5  jz      loc_18004BEE8
0x18004bcdb  mov     r8, rdi
0x18004bcde  mov     rdx, r14
0x18004bce1  mov     rcx, rsi
0x18004bce4  call    resolveFromTermToCte
0x18004bce9  test    eax, eax
0x18004bceb  jnz     loc_18004BD74
0x18004bcf1  mov     r8, rdi
0x18004bcf4  xor     edx, edx
0x18004bcf6  mov     rcx, rsi
0x18004bcf9  call    sqlite3LocateTableItem
0x18004bcfe  mov     [rdi+10h], rax
0x18004bd02  mov     rbx, rax
0x18004bd05  test    rax, rax
0x18004bd08  jz      loc_18004BE08
0x18004bd0e  mov     eax, [rax+2Ch]
0x18004bd11  cmp     eax, 0FFFFh
0x18004bd16  jnb     loc_18004BF6C
0x18004bd1c  inc     eax
0x18004bd1e  mov     [rbx+2Ch], eax
0x18004bd21  cmp     [rbx+3Fh], r15b
0x18004bd25  jnz     loc_18004BE12
0x18004bd2b  cmp     byte ptr [rbx+3Fh], 0
0x18004bd2f  jnz     short loc_18004BD7E
0x18004bd31  xor     ebx, ebx
0x18004bd33  test    byte ptr [rdi+1Ch], 2
0x18004bd37  jnz     loc_18004BF54
0x18004bd3d  mov     r8, [rsp+0F8h+var_B0]
0x18004bd42  add     r12d, r15d
0x18004bd45  add     rdi, 50h ; 'P'
0x18004bd49  jmp     loc_18004BBF7
0x18004bd4e  mov     eax, [r13+90h]
0x18004bd55  cmp     [rcx], eax
0x18004bd57  jg      loc_18004BDF9
0x18004bd5d  test    r8d, 400008h
0x18004bd64  jz      loc_18004BC48
0x18004bd6a  bts     dword ptr [rbp+4], 12h
0x18004bd6f  jmp     loc_18004BC48
0x18004bd74  cmp     eax, r15d
0x18004bd77  jle     short loc_18004BD33
0x18004bd79  jmp     loc_18004BE08
0x18004bd7e  mov     al, [r14+24h]
0x18004bd82  mov     rdx, rbx
0x18004bd85  mov     rcx, rsi
0x18004bd88  mov     byte ptr [rsp+0F8h+arg_0], al
0x18004bd8f  call    sqlite3ViewGetColumnNames
0x18004bd94  test    eax, eax
0x18004bd96  jnz     short loc_18004BE08
0x18004bd98  cmp     byte ptr [rbx+3Fh], 2
0x18004bd9c  jnz     loc_18004BE27
0x18004bda2  mov     eax, [r13+30h]
0x18004bda6  bt      rax, 1Fh
0x18004bdab  jnb     loc_18004BF17
0x18004bdb1  mov     r8, [rbx+40h]
0x18004bdb5  mov     r9d, r15d
0x18004bdb8  mov     rdx, rdi
0x18004bdbb  mov     rcx, rsi
0x18004bdbe  call    sqlite3SrcItemAttachSubquery
0x18004bdc3  movzx   r13d, word ptr [rbx+36h]
0x18004bdc8  mov     word ptr [rbx+36h], 0FFFFh
0x18004bdce  mov     [r14+24h], r15w
0x18004bdd3  test    byte ptr [rdi+1Ch], 4
0x18004bdd7  jnz     loc_18004BF40
0x18004bddd  movzx   eax, byte ptr [rsp+0F8h+arg_0]
0x18004bde5  mov     [r14+24h], ax
0x18004bdea  mov     [rbx+36h], r13w
0x18004bdef  mov     r13, [rsp+0F8h+var_B8]
0x18004bdf4  jmp     loc_18004BD31
0x18004bdf9  lea     rdx, aTooManyColumns; "too many columns in result set"
0x18004be00  mov     rcx, rsi
0x18004be03  call    sqlite3ErrorMsg
0x18004be08  mov     eax, 2
0x18004be0d  jmp     loc_18004BC4A
0x18004be12  mov     rdx, rdi
0x18004be15  mov     rcx, rsi
0x18004be18  call    cannotBeFunction
0x18004be1d  test    eax, eax
0x18004be1f  jz      loc_18004BD2B
0x18004be25  jmp     short loc_18004BE08
0x18004be27  cmp     [rbx+3Fh], r15b
0x18004be2b  jnz     short loc_18004BDC3
0x18004be2d  test    dword ptr [rdi+1Ch], 100h
0x18004be34  jz      short loc_18004BDC3
0x18004be36  mov     rax, [rbx+50h]
0x18004be3a  test    rax, rax
0x18004be3d  jz      short loc_18004BDC3
0x18004be3f  mov     ecx, [r13+30h]
0x18004be43  movzx   eax, byte ptr [rax+1Eh]
0x18004be47  shr     rcx, 7
0x18004be4b  and     ecx, r15d
0x18004be4e  cmp     eax, ecx
0x18004be50  jbe     loc_18004BDC3
0x18004be56  mov     r8, [rbx]
0x18004be59  lea     rdx, aUnsafeUseOfVir; "unsafe use of virtual table \"%s\""
0x18004be60  mov     rcx, rsi
0x18004be63  call    sqlite3ErrorMsg
0x18004be68  jmp     loc_18004BDC3
0x18004be6d  mov     eax, 1
0x18004be72  jmp     loc_18004BC4A
0x18004be77  add     [rsi+94h], r15d
0x18004be7e  mov     eax, [rsi+94h]
0x18004be84  mov     [rdx+10h], eax
0x18004be87  jmp     loc_18004BBAB
0x18004be8c  test    dword ptr [rdx+4], 200000h
0x18004be93  jz      loc_18004BBCD
0x18004be99  mov     rax, [rdx+68h]
0x18004be9d  test    rax, rax
0x18004bea0  jnz     short loc_18004BEBF
0x18004bea2  lea     edx, [rax+40h]
0x18004bea5  mov     rcx, r13
0x18004bea8  call    sqlite3DbMallocZero
0x18004bead  mov     [rbp+68h], rax
0x18004beb1  test    rax, rax
0x18004beb4  jz      loc_18004BE08
0x18004beba  mov     r8, [rsp+0F8h+var_B0]
0x18004bebf  mov     [rax+4], r15d
0x18004bec3  jmp     loc_18004BBCD
0x18004bec8  cmp     [rsi+34h], ebx
0x18004becb  jnz     loc_18004BBDA
0x18004bed1  mov     rax, [rsi+198h]
0x18004bed8  mov     [rcx+8], rax
0x18004bedc  mov     [rsi+198h], rcx
0x18004bee3  jmp     loc_18004BBDA
0x18004bee8  mov     rdx, [rdi+48h]
0x18004beec  mov     rcx, r14
0x18004beef  mov     rdx, [rdx]
0x18004bef2  call    sqlite3WalkSelect
0x18004bef7  test    eax, eax
0x18004bef9  jnz     loc_18004BE08
0x18004beff  mov     rdx, rdi
0x18004bf02  mov     rcx, rsi
0x18004bf05  call    sqlite3ExpandSubquery
0x18004bf0a  test    eax, eax
0x18004bf0c  jnz     loc_18004BE08
0x18004bf12  jmp     loc_18004BD33
0x18004bf17  mov     rax, [r13+20h]
0x18004bf1b  mov     rcx, [rax+38h]
0x18004bf1f  cmp     [rbx+60h], rcx
0x18004bf23  jz      loc_18004BDB1
0x18004bf29  mov     r8, [rbx]
0x18004bf2c  lea     rdx, aAccessToViewSP; "access to view \"%s\" prohibited"
0x18004bf33  mov     rcx, rsi
0x18004bf36  call    sqlite3ErrorMsg
0x18004bf3b  jmp     loc_18004BDB1
0x18004bf40  mov     rdx, [rdi+48h]
0x18004bf44  mov     rcx, r14
0x18004bf47  mov     rdx, [rdx]
0x18004bf4a  call    sqlite3WalkSelect
0x18004bf4f  jmp     loc_18004BDDD
0x18004bf54  mov     rdx, rdi
0x18004bf57  mov     rcx, rsi
0x18004bf5a  call    sqlite3IndexedByLookup
0x18004bf5f  test    eax, eax
0x18004bf61  jnz     loc_18004BE08
0x18004bf67  jmp     loc_18004BD3D
0x18004bf6c  mov     r8, [rbx]
0x18004bf6f  lea     rdx, aTooManyReferen; "too many references to \"%s\": max 6553"...
0x18004bf76  mov     rcx, rsi
0x18004bf79  call    sqlite3ErrorMsg
0x18004bf7e  mov     qword ptr [rdi+10h], 0
0x18004bf86  jmp     loc_18004BE08
0x18004bf8b  test    byte ptr [rax+30h], 40h
0x18004bf8f  mov     [rsp+0F8h+var_A4], r15d
0x18004bf94  jz      loc_18004BCA3
0x18004bf9a  jmp     loc_18004BC9E
0x18004bf9f  mov     edx, 800h
0x18004bfa4  movsxd  rbx, eax
0x18004bfa7  shl     rbx, 5
0x18004bfab  mov     rcx, [rbx+rdi+8]
0x18004bfb0  mov     [rsp+0F8h+var_50], rcx
0x18004bfb8  or      r8d, [rcx+4]
0x18004bfbc  cmp     byte ptr [rcx], 0B4h
0x18004bfbf  mov     [rsp+0F8h+var_BC], r8d
0x18004bfc4  jz      short loc_18004C026
0x18004bfc6  cmp     byte ptr [rcx], 8Eh
0x18004bfc9  jnz     short loc_18004BFD4
0x18004bfcb  mov     rax, [rcx+18h]
0x18004bfcf  cmp     byte ptr [rax], 0B4h
0x18004bfd2  jz      short loc_18004C026
0x18004bfd4  mov     r8, rcx
0x18004bfd7  mov     rdx, r12
0x18004bfda  mov     rcx, rsi
0x18004bfdd  call    sqlite3ExprListAppend
0x18004bfe2  xor     r10d, r10d
0x18004bfe5  mov     r12, rax
0x18004bfe8  test    rax, rax
0x18004bfeb  jz      short loc_18004C01C
0x18004bfed  movsxd  rcx, dword ptr [rax]
0x18004bff0  mov     rax, [rbx+rdi+10h]
0x18004bff5  shl     rcx, 5
0x18004bff9  mov     [rcx+r12-10h], rax
0x18004bffe  movsxd  rcx, dword ptr [r12]
  ... truncated ...
```

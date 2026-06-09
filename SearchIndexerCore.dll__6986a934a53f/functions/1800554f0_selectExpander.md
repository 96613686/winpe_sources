# selectExpander

- ea: `0x1800554f0`
- end: `0x180055fb7`
- name: `selectExpander`
- size: `2759`
- prototype: `__int64 __fastcall(__int64 **, __int64)`
- caller_count: `0`
- callee_count: `27`
- tags: ``

## callees

- `0x1800087d0`
- `0x180009fe0`
- `0x18000a710`
- `0x18000e818`
- `0x180011bcc`
- `0x18001351c`
- `0x180014270`
- `0x180015540`
- `0x180018fd0`
- `0x18001bc40`
- `0x18001f418`
- `0x18001f8f0`
- `0x18003d380`
- `0x180040e00`
- `0x1800554f0`
- `0x180055fc0`
- `0x18005601c`
- `0x18005645c`
- `0x1800599b8`
- `0x180059a18`
- `0x18005df58`
- `0x180060434`
- `0x180060c34`
- `0x180063d5c`
- `0x180075ad4`
- `0x180093338`
- `0x180097f08`

## string_xrefs

- `0x1800556dc`: `access to view "%s" prohibited`

## pseudocode

```c
__int64 __fastcall selectExpander(__int64 **a1, __int64 a2)
{
  __int64 *v2; // r14
  __int16 v3; // ax
  __int64 v4; // rbp
  __int64 v6; // rbx
  int *v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  int *v11; // r8
  int v12; // r12d
  _DWORD *v13; // rsi
  int v14; // eax
  __int64 TableItem; // rax
  const char **v16; // rdi
  unsigned int v17; // eax
  const char *v18; // rax
  __int16 v19; // bx
  int v20; // eax
  __int64 v21; // r10
  _DWORD *v22; // rdi
  __int64 v23; // r8
  int v24; // ecx
  __int64 v25; // rdx
  int *v26; // r15
  int v27; // eax
  int *v28; // r12
  __int64 v29; // rbx
  __int64 v30; // rcx
  int *v31; // rax
  const char *v32; // rdi
  __int64 v33; // rax
  int v34; // r11d
  _DWORD *v35; // rbx
  int v36; // esi
  const char *v37; // rax
  __int64 v38; // r9
  int v39; // eax
  int v40; // eax
  __int16 v41; // cx
  int v42; // edi
  _DWORD *v43; // rbp
  const char *v44; // rsi
  __int64 v45; // rax
  __int64 v46; // rax
  int *v47; // rax
  __int64 v48; // rbx
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rax
  const char *v53; // rsi
  const char *v54; // rdi
  __int16 v55; // cx
  int v56; // eax
  __int64 v57; // rdi
  __int64 v58; // rbx
  __int64 v59; // rax
  int *v60; // rax
  __int64 v61; // rbx
  __int64 v62; // rsi
  __int64 v63; // rax
  unsigned int v64; // edx
  __int64 v65; // rcx
  __int64 v66; // rbx
  int matched; // eax
  unsigned int v68; // edi
  int v69; // eax
  int v70; // eax
  __int64 v71; // rax
  _DWORD *v72; // rcx
  __int64 v73; // [rsp+30h] [rbp-D8h]
  int v74; // [rsp+38h] [rbp-D0h]
  unsigned int v75; // [rsp+3Ch] [rbp-CCh]
  _DWORD *v76; // [rsp+40h] [rbp-C8h]
  int *v77; // [rsp+48h] [rbp-C0h]
  unsigned int v78; // [rsp+50h] [rbp-B8h]
  int v79; // [rsp+54h] [rbp-B4h]
  int v80; // [rsp+58h] [rbp-B0h]
  int v81; // [rsp+5Ch] [rbp-ACh]
  int v82; // [rsp+60h] [rbp-A8h]
  const char *v83; // [rsp+68h] [rbp-A0h]
  const char *v84; // [rsp+70h] [rbp-98h]
  const char *v85; // [rsp+78h] [rbp-90h]
  _DWORD *v86; // [rsp+80h] [rbp-88h]
  int v87; // [rsp+88h] [rbp-80h]
  __int64 v88; // [rsp+90h] [rbp-78h]
  _DWORD *v89; // [rsp+98h] [rbp-70h]
  __int64 v90; // [rsp+A0h] [rbp-68h]
  __int64 v91; // [rsp+A8h] [rbp-60h]
  __int64 v92; // [rsp+B0h] [rbp-58h]
  unsigned __int8 v93; // [rsp+110h] [rbp+8h]
  __int16 v94; // [rsp+110h] [rbp+8h]
  __int16 v96; // [rsp+120h] [rbp+18h]
  unsigned int v97; // [rsp+128h] [rbp+20h]

  v2 = *a1;
  v3 = *(_WORD *)(a2 + 4);
  v4 = a2;
  v96 = v3;
  v6 = **a1;
  *(_DWORD *)(a2 + 4) |= 0x40u;
  v91 = v6;
  if ( *(_BYTE *)(v6 + 103) )
    return 2;
  if ( (v3 & 0x40) != 0 )
    return 1;
  if ( *((_WORD *)a1 + 18) )
    *(_DWORD *)(a2 + 16) = ++*((_DWORD *)v2 + 37);
  v8 = *(int **)(a2 + 40);
  v77 = v8;
  v86 = *(_DWORD **)(a2 + 32);
  if ( v2[51] && (*(_DWORD *)(a2 + 4) & 0x200000) != 0 )
  {
    v9 = *(_QWORD *)(a2 + 104);
    if ( !v9 )
    {
      v9 = sqlite3DbMallocZero(v6, 64);
      *(_QWORD *)(v4 + 104) = v9;
      if ( !v9 )
        return 2;
      v8 = v77;
    }
    *(_DWORD *)(v9 + 4) = 1;
  }
  v10 = *(_QWORD *)(v4 + 104);
  if ( v10 && !*((_DWORD *)v2 + 12) )
  {
    *(_QWORD *)(v10 + 8) = v2[51];
    v2[51] = v10;
  }
  sqlite3SrcListAssignCursors(v2, v8);
  v12 = 0;
  v13 = v11 + 2;
  while ( v12 < *v11 )
  {
    if ( !*((_QWORD *)v13 + 4) )
    {
      if ( *((_QWORD *)v13 + 2) )
      {
        v14 = resolveFromTermToCte(v2, a1, v13);
        if ( v14 )
        {
          if ( v14 > 1 )
            return 2;
        }
        else
        {
          TableItem = sqlite3LocateTableItem(v2, 0, v13);
          *((_QWORD *)v13 + 4) = TableItem;
          v16 = (const char **)TableItem;
          if ( !TableItem )
            return 2;
          v17 = *(_DWORD *)(TableItem + 44);
          if ( v17 >= 0xFFFF )
          {
            sqlite3ErrorMsg(v2, "too many references to \"%s\": max 65535", *v16);
            *((_QWORD *)v13 + 4) = 0;
            return 2;
          }
          *((_DWORD *)v16 + 11) = v17 + 1;
          if ( *((_BYTE *)v16 + 63) != 1 && (unsigned int)cannotBeFunction(v2, v13) )
            return 2;
          if ( *((_BYTE *)v16 + 63) )
          {
            v93 = *((_BYTE *)a1 + 36);
            if ( (unsigned int)sqlite3ViewGetColumnNames(v2, v16) )
              return 2;
            if ( *((_BYTE *)v16 + 63) == 2 )
            {
              if ( (*(_DWORD *)(v6 + 48) & 0x80000000) == 0 && v16[12] != *(const char **)(*(_QWORD *)(v6 + 32) + 56LL) )
                sqlite3ErrorMsg(v2, "access to view \"%s\" prohibited", *v16);
              *((_QWORD *)v13 + 5) = sqlite3SelectDup(v6, v16[8], 0);
            }
            else if ( *((_BYTE *)v16 + 63) == 1 && *((char *)v13 + 64) < 0 )
            {
              v18 = v16[10];
              if ( v18 )
              {
                if ( *((unsigned __int8 *)v18 + 30) > ((*(_DWORD *)(v6 + 48) >> 7) & 1u) )
                  sqlite3ErrorMsg(v2, "unsafe use of virtual table \"%s\"", *v16);
              }
            }
            v19 = *((_WORD *)v16 + 27);
            *((_WORD *)v16 + 27) = -1;
            *((_WORD *)a1 + 18) = 1;
            sqlite3WalkSelect(a1, *((_QWORD *)v13 + 5));
            *((_WORD *)a1 + 18) = v93;
            *((_WORD *)v16 + 27) = v19;
            v6 = v91;
          }
        }
      }
      else if ( (unsigned int)sqlite3WalkSelect(a1, *((_QWORD *)v13 + 5))
             || (unsigned int)sqlite3ExpandSubquery(v2, v13) )
      {
        return 2;
      }
      if ( (v13[16] & 2) != 0 && (unsigned int)sqlite3IndexedByLookup(v2, v13) )
        return 2;
      v11 = v77;
    }
    ++v12;
    v13 += 26;
  }
  if ( *((_DWORD *)v2 + 12) )
    return 2;
  v20 = sqlite3ProcessJoin(v2, v4);
  v21 = 0;
  if ( v20 )
    return 2;
  v22 = v86;
  v23 = 0;
  v75 = 0;
  v24 = 0;
  if ( (int)*v86 <= 0 )
  {
LABEL_54:
    if ( v24 >= *v86 )
      goto LABEL_156;
  }
  else
  {
    while ( 1 )
    {
      v25 = *(_QWORD *)&v86[8 * v24 + 2];
      if ( *(_BYTE *)v25 == 0xB4 || *(_BYTE *)v25 == 0x8D && **(_BYTE **)(v25 + 24) == 0xB4 )
        break;
      v23 = *(_DWORD *)(v25 + 4) | (unsigned int)v23;
      ++v24;
      v75 = v23;
      if ( v24 >= *v86 )
        goto LABEL_54;
    }
  }
  v26 = 0;
  v87 = *(_DWORD *)(*v2 + 48) & 0x44;
  v27 = 0;
  v82 = 0;
  if ( (int)*v86 > 0 )
  {
    v28 = v77;
LABEL_57:
    v29 = 8LL * v27;
    v30 = *(_QWORD *)&v22[v29 + 2];
    v92 = v30;
    v75 = *(_DWORD *)(v30 + 4) | v23;
    if ( *(_BYTE *)v30 != 0xB4 && (*(_BYTE *)v30 != 0x8D || **(_BYTE **)(v30 + 24) != 0xB4) )
    {
      v31 = (int *)sqlite3ExprListAppend(v2, v26, v30);
      v21 = 0;
      v26 = v31;
      if ( v31 )
      {
        *(_QWORD *)&v31[8 * *v31 - 4] = *(_QWORD *)&v22[v29 + 4];
        v31[8 * *v31 - 1] ^= (v22[v29 + 7] ^ v31[8 * *v31 - 1]) & 3;
        *(_QWORD *)&v22[v29 + 4] = 0;
      }
      *(_QWORD *)&v22[v29 + 2] = 0;
      goto LABEL_153;
    }
    v81 = v21;
    if ( *(_BYTE *)v30 == 0x8D )
    {
      v32 = *(const char **)(*(_QWORD *)(v30 + 16) + 8LL);
      v33 = *(_QWORD *)(v30 + 24);
    }
    else
    {
      v32 = (const char *)v21;
      v33 = v30;
    }
    v34 = *v28;
    v35 = v28 + 2;
    v36 = v21;
    v76 = v28 + 2;
    v83 = v32;
    v78 = *(_DWORD *)(v33 + 52);
    v74 = v21;
    v80 = v21;
    if ( *v28 <= 0 )
    {
LABEL_148:
      if ( v32 )
        sqlite3ErrorMsg(v2, "no such table: %s", v32);
      else
        sqlite3ErrorMsg(v2, "no tables specified");
      v21 = 0;
      goto LABEL_152;
    }
    while ( 1 )
    {
      v37 = (const char *)*((_QWORD *)v35 + 3);
      v38 = *((_QWORD *)v35 + 4);
      v73 = v38;
      v85 = v37;
      if ( !v37 )
      {
        v37 = *(const char **)v38;
        v85 = *(const char **)v38;
      }
      if ( *(_BYTE *)(v91 + 103) != (_BYTE)v21 )
      {
LABEL_147:
        v28 = v77;
        if ( !v81 )
          goto LABEL_148;
LABEL_152:
        v22 = v86;
LABEL_153:
        LODWORD(v23) = v75;
        v27 = v82 + 1;
        v82 = v27;
        if ( v27 >= *v22 )
        {
          v6 = v91;
          break;
        }
        goto LABEL_57;
      }
      if ( (v35[16] & 0x2000) != 0 )
      {
        v84 = (const char *)v21;
        v88 = *(_QWORD *)(*((_QWORD *)v35 + 5) + 32LL);
        v21 = 0;
      }
      else
      {
        if ( v32 )
        {
          v39 = sqlite3StrICmp(v32, v37);
          v21 = 0;
          if ( v39 )
            goto LABEL_146;
          v38 = v73;
        }
        v88 = v21;
        v40 = sqlite3SchemaToIndex(v91, *(_QWORD *)(v38 + 96));
        if ( v40 < 0 )
        {
          v84 = "*";
        }
        else
        {
          _mm_lfence();
          v84 = *(const char **)(32LL * v40 + *(_QWORD *)(v91 + 32));
        }
      }
      if ( v36 + 1 < v34 && (v35[42] & 0x400) != 0 && (v41 = v96 & 0x800, v94 = v96 & 0x800, (v96 & 0x800) != 0) )
      {
        v42 = v21;
        v89 = (_DWORD *)*((_QWORD *)v35 + 22);
        if ( *v89 > (int)v21 )
        {
          v43 = (_DWORD *)*((_QWORD *)v35 + 22);
          do
          {
            v44 = *(const char **)&v43[4 * v42 + 2];
            v45 = sqlite3Expr(v91, 59, v44);
            v46 = sqlite3ExprSetErrorOffset(v45, v78);
            v47 = (int *)sqlite3ExprListAppend(v2, v26, v46);
            v21 = 0;
            v26 = v47;
            if ( v47 )
            {
              v48 = 8 * (*v47 - 1LL);
              v49 = sqlite3MPrintf(v91, "..%s", v44);
              v26[v48 + 7] &= ~1u;
              v26[v48 + 7] |= 0x82u;
              v21 = 0;
              *(_QWORD *)&v26[v48 + 4] = v49;
            }
            ++v42;
          }
          while ( v42 < *v43 );
          v4 = a2;
          v35 = v76;
          v41 = v96 & 0x800;
          v38 = v73;
          v36 = v74;
        }
      }
      else
      {
        v41 = v96 & 0x800;
        v89 = (_DWORD *)v21;
        v94 = v96 & 0x800;
      }
      v50 = *(__int16 *)(v38 + 54);
      v79 = v50;
      if ( (*(_DWORD *)(v38 + 48) & 0x200) == 0 && v41 )
        v79 = ++v50;
      v51 = (unsigned int)v21;
      v97 = v21;
      if ( v50 > 0 )
      {
        while ( (_DWORD)v51 != *(__int16 *)(v38 + 54) )
        {
          v65 = 32 * v51;
          if ( v88 && (*(_BYTE *)(v88 + v65 + 28) & 3) == 3 )
            goto LABEL_143;
          v66 = 3 * v51;
          v54 = v83;
          v53 = *(const char **)(*(_QWORD *)(v38 + 8) + 24 * v51);
          v90 = (__int64)v53;
          if ( v83 )
          {
            if ( v88 )
            {
              matched = sqlite3MatchEName((int)v88 + 8 + (int)v65, 0, (_DWORD)v83, 0, v21);
              v38 = v73;
              v21 = 0;
              if ( !matched )
                goto LABEL_143;
            }
          }
          if ( (*(_DWORD *)(v4 + 4) & 0x20000) == 0 && (*(_BYTE *)(*(_QWORD *)(v38 + 8) + 8 * v66 + 18) & 2) != 0 )
            goto LABEL_143;
          if ( (*(_WORD *)(*(_QWORD *)(v38 + 8) + 8 * v66 + 18) & 0x400) == 0 )
            goto LABEL_95;
          v55 = v94;
          if ( !v83 && !v94 )
            goto LABEL_143;
LABEL_96:
          v81 = 1;
          if ( v74 > (int)v21 && !v54 && !v55 && (v76[16] & 0x400) != 0 )
          {
            v56 = sqlite3IdListIndex(*((_QWORD *)v76 + 9), v53);
            v21 = 0;
            if ( v56 >= 0 )
              goto LABEL_142;
          }
          v57 = sqlite3Expr(v91, 59, v53);
          if ( *v77 > 1
            && ((v76[15] & 0x40) == 0 || v94 || !(unsigned int)inAnyUsingClause(v53, v76, (unsigned int)(*v77 + ~v80)))
            || *((_BYTE *)v2 + 308) >= 2u )
          {
            v58 = sqlite3Expr(v91, 59, v85);
            v57 = sqlite3PExpr(v2, 141, v58, v57);
            if ( *((_BYTE *)v2 + 308) >= 2u && *(_QWORD *)(v92 + 16) )
              sqlite3RenameTokenRemap(v2, v58);
            if ( v84 )
            {
              v59 = sqlite3Expr(v91, 59, v84);
              v57 = sqlite3PExpr(v2, 141, v59, v57);
            }
          }
          sqlite3ExprSetErrorOffset(v57, v78);
          v60 = (int *)sqlite3ExprListAppend(v2, v26, v57);
          v21 = 0;
          v26 = v60;
          if ( !v60 )
          {
LABEL_144:
            v35 = v76;
            v36 = v74;
            goto LABEL_145;
          }
          v61 = 8LL * *v60;
          if ( !v94 || *((_BYTE *)v2 + 308) >= 2u )
          {
            if ( v87 == 4 )
              v71 = sqlite3MPrintf(v91, "%s.%s", v85, v53);
            else
              v71 = sqlite3DbStrDup(v91, v53);
            v26[v61 - 1] &= 0xFFFFFFFC;
            v21 = 0;
            *(_QWORD *)&v26[v61 - 4] = v71;
LABEL_142:
            v38 = v73;
            goto LABEL_143;
          }
          if ( v88 )
          {
            v62 = v97;
            v63 = sqlite3DbStrDup(v91, *(_QWORD *)(32LL * v97 + v88 + 16));
            v64 = v97;
          }
          else
          {
            v63 = sqlite3MPrintf(v91, "%s.%s.%s", v84, v85, v53);
            v64 = v97;
            v62 = v97;
          }
          *(_QWORD *)&v26[v61 - 4] = v63;
          v68 = v26[v61 - 1] & 0xFFFFFFFC | (3 - (*(__int16 *)(v73 + 54) != v64));
          v26[v61 - 1] = v68;
          if ( (v76[16] & 0x400) != 0 )
          {
            v69 = sqlite3IdListIndex(*((_QWORD *)v76 + 9), v90);
            v21 = 0;
            if ( v69 >= 0 )
              goto LABEL_130;
          }
          else
          {
            v21 = 0;
          }
          if ( !v89 || (v70 = sqlite3IdListIndex(v89, v90), v21 = 0, v70 < 0) )
          {
            v38 = v73;
            if ( (int)v97 >= *(__int16 *)(v73 + 54) || (*(_WORD *)(*(_QWORD *)(v73 + 8) + 24 * v62 + 18) & 0x400) == 0 )
              goto LABEL_143;
            goto LABEL_131;
          }
LABEL_130:
          v38 = v73;
LABEL_131:
          v26[v61 - 1] = v68 | 0x100;
LABEL_143:
          v51 = v97 + 1;
          v97 = v51;
          if ( (int)v51 >= v79 )
            goto LABEL_144;
        }
        v52 = sqlite3RowidAlias(v38);
        v21 = 0;
        v90 = v52;
        v53 = (const char *)v52;
        if ( !v52 )
          goto LABEL_142;
        v54 = v83;
LABEL_95:
        v55 = v94;
        goto LABEL_96;
      }
LABEL_145:
      v32 = v83;
LABEL_146:
      ++v36;
      v35 += 26;
      v74 = v36;
      v76 = v35;
      v80 = v36;
      v34 = *v77;
      if ( v36 >= *v77 )
        goto LABEL_147;
    }
  }
  sqlite3ExprListDeleteGeneric(v6, v22);
  v23 = v75;
  *(_QWORD *)(v4 + 32) = v26;
LABEL_156:
  v72 = *(_DWORD **)(v4 + 32);
  if ( v72 )
  {
    if ( *v72 > *(_DWORD *)(v6 + 144) )
    {
      sqlite3ErrorMsg(v2, "too many columns in result set", v23);
      return 2;
    }
    if ( (v23 & 0x400008) != 0 )
      *(_DWORD *)(v4 + 4) |= 0x40000u;
  }
  return 0;
}

```

## disassembly

```asm
0x1800554f0  mov     [rsp+arg_8], rdx
0x1800554f5  push    rbx
0x1800554f6  push    rbp
0x1800554f7  push    rsi
0x1800554f8  push    rdi
0x1800554f9  push    r12
0x1800554fb  push    r13
0x1800554fd  push    r14
0x1800554ff  push    r15
0x180055501  sub     rsp, 0C8h
0x180055508  mov     r14, [rcx]
0x18005550b  xor     edi, edi
0x18005550d  movzx   eax, word ptr [rdx+4]
0x180055511  mov     rbp, rdx
0x180055514  mov     r15, rcx
0x180055517  mov     [rsp+108h+arg_10], ax
0x18005551f  mov     rbx, [r14]
0x180055522  or      dword ptr [rdx+4], 40h
0x180055526  mov     [rsp+108h+var_60], rbx
0x18005552e  cmp     [rbx+67h], dil
0x180055532  jnz     loc_18005561D
0x180055538  test    al, 40h
0x18005553a  jz      short loc_180055544
0x18005553c  lea     eax, [rdi+1]
0x18005553f  jmp     loc_180055622
0x180055544  mov     r13d, 1
0x18005554a  cmp     [rcx+24h], di
0x18005554e  jz      short loc_180055561
0x180055550  add     [r14+94h], r13d
0x180055557  mov     eax, [r14+94h]
0x18005555e  mov     [rdx+10h], eax
0x180055561  mov     r8, [rdx+28h]
0x180055565  mov     rax, [rdx+20h]
0x180055569  mov     [rsp+108h+var_C0], r8
0x18005556e  mov     [rsp+108h+var_88], rax
0x180055576  cmp     [r14+198h], rdi
0x18005557d  jz      short loc_1800555AE
0x18005557f  test    dword ptr [rdx+4], 200000h
0x180055586  jz      short loc_1800555AE
0x180055588  mov     rax, [rdx+68h]
0x18005558c  test    rax, rax
0x18005558f  jnz     short loc_1800555AA
0x180055591  lea     edx, [rax+40h]
0x180055594  mov     rcx, rbx
0x180055597  call    sqlite3DbMallocZero
0x18005559c  mov     [rbp+68h], rax
0x1800555a0  test    rax, rax
0x1800555a3  jz      short loc_18005561D
0x1800555a5  mov     r8, [rsp+108h+var_C0]
0x1800555aa  mov     [rax+4], r13d
0x1800555ae  mov     rcx, [rbp+68h]
0x1800555b2  test    rcx, rcx
0x1800555b5  jz      short loc_1800555CF
0x1800555b7  cmp     [r14+30h], edi
0x1800555bb  jnz     short loc_1800555CF
0x1800555bd  mov     rax, [r14+198h]
0x1800555c4  mov     [rcx+8], rax
0x1800555c8  mov     [r14+198h], rcx
0x1800555cf  mov     rdx, r8
0x1800555d2  mov     rcx, r14
0x1800555d5  call    sqlite3SrcListAssignCursors
0x1800555da  mov     r12d, edi
0x1800555dd  lea     rsi, [r8+8]
0x1800555e1  cmp     r12d, [r8]
0x1800555e4  jge     loc_1800557B8
0x1800555ea  cmp     [rsi+20h], rdi
0x1800555ee  jnz     loc_18005578D
0x1800555f4  cmp     [rsi+10h], rdi
0x1800555f8  jnz     short loc_180055636
0x1800555fa  mov     rdx, [rsi+28h]
0x1800555fe  mov     rcx, r15
0x180055601  call    sqlite3WalkSelect
0x180055606  test    eax, eax
0x180055608  jnz     short loc_18005561D
0x18005560a  mov     rdx, rsi
0x18005560d  mov     rcx, r14
0x180055610  call    sqlite3ExpandSubquery
0x180055615  test    eax, eax
0x180055617  jz      loc_18005576F
0x18005561d  mov     eax, 2
0x180055622  add     rsp, 0C8h
0x180055629  pop     r15
0x18005562b  pop     r14
0x18005562d  pop     r13
0x18005562f  pop     r12
0x180055631  pop     rdi
0x180055632  pop     rsi
0x180055633  pop     rbp
0x180055634  pop     rbx
0x180055635  retn
0x180055636  mov     r8, rsi
0x180055639  mov     rdx, r15
0x18005563c  mov     rcx, r14
0x18005563f  call    resolveFromTermToCte
0x180055644  test    eax, eax
0x180055646  jz      short loc_180055652
0x180055648  cmp     eax, r13d
0x18005564b  jg      short loc_18005561D
0x18005564d  jmp     loc_18005576F
0x180055652  mov     r8, rsi
0x180055655  xor     edx, edx
0x180055657  mov     rcx, r14
0x18005565a  call    sqlite3LocateTableItem
0x18005565f  mov     [rsi+20h], rax
0x180055663  mov     rdi, rax
0x180055666  test    rax, rax
0x180055669  jz      short loc_18005561D
0x18005566b  mov     eax, [rax+2Ch]
0x18005566e  cmp     eax, 0FFFFh
0x180055673  jnb     loc_180055799
0x180055679  inc     eax
0x18005567b  mov     [rdi+2Ch], eax
0x18005567e  cmp     [rdi+3Fh], r13b
0x180055682  jz      short loc_180055693
0x180055684  mov     rdx, rsi
0x180055687  mov     rcx, r14
0x18005568a  call    cannotBeFunction
0x18005568f  test    eax, eax
0x180055691  jnz     short loc_18005561D
0x180055693  cmp     byte ptr [rdi+3Fh], 0
0x180055697  jz      loc_18005576D
0x18005569d  mov     al, [r15+24h]
0x1800556a1  mov     rdx, rdi
0x1800556a4  mov     rcx, r14
0x1800556a7  mov     byte ptr [rsp+108h+arg_0], al
0x1800556ae  call    sqlite3ViewGetColumnNames
0x1800556b3  test    eax, eax
0x1800556b5  jnz     loc_18005561D
0x1800556bb  cmp     byte ptr [rdi+3Fh], 2
0x1800556bf  jnz     short loc_180055700
0x1800556c1  mov     eax, [rbx+30h]
0x1800556c4  bt      rax, 1Fh
0x1800556c9  jb      short loc_1800556EB
0x1800556cb  mov     rax, [rbx+20h]
0x1800556cf  mov     rcx, [rax+38h]
0x1800556d3  cmp     [rdi+60h], rcx
0x1800556d7  jz      short loc_1800556EB
0x1800556d9  mov     r8, [rdi]
0x1800556dc  lea     rdx, aAccessToViewSP; "access to view \"%s\" prohibited"
0x1800556e3  mov     rcx, r14
0x1800556e6  call    sqlite3ErrorMsg
0x1800556eb  mov     rdx, [rdi+40h]
0x1800556ef  xor     r8d, r8d
0x1800556f2  mov     rcx, rbx
0x1800556f5  call    sqlite3SelectDup
0x1800556fa  mov     [rsi+28h], rax
0x1800556fe  jmp     short loc_180055739
0x180055700  cmp     [rdi+3Fh], r13b
0x180055704  jnz     short loc_180055739
0x180055706  test    byte ptr [rsi+40h], 80h
0x18005570a  jz      short loc_180055739
0x18005570c  mov     rax, [rdi+50h]
0x180055710  test    rax, rax
0x180055713  jz      short loc_180055739
0x180055715  mov     ecx, [rbx+30h]
0x180055718  movzx   eax, byte ptr [rax+1Eh]
0x18005571c  shr     rcx, 7
0x180055720  and     ecx, r13d
0x180055723  cmp     eax, ecx
0x180055725  jbe     short loc_180055739
0x180055727  mov     r8, [rdi]
0x18005572a  lea     rdx, aUnsafeUseOfVir; "unsafe use of virtual table \"%s\""
0x180055731  mov     rcx, r14
0x180055734  call    sqlite3ErrorMsg
0x180055739  movzx   ebx, word ptr [rdi+36h]
0x18005573d  mov     rcx, r15
0x180055740  mov     word ptr [rdi+36h], 0FFFFh
0x180055746  mov     [r15+24h], r13w
0x18005574b  mov     rdx, [rsi+28h]
0x18005574f  call    sqlite3WalkSelect
0x180055754  movzx   eax, byte ptr [rsp+108h+arg_0]
0x18005575c  mov     [r15+24h], ax
0x180055761  mov     [rdi+36h], bx
0x180055765  mov     rbx, [rsp+108h+var_60]
0x18005576d  xor     edi, edi
0x18005576f  test    byte ptr [rsi+40h], 2
0x180055773  jz      short loc_180055788
0x180055775  mov     rdx, rsi
0x180055778  mov     rcx, r14
0x18005577b  call    sqlite3IndexedByLookup
0x180055780  test    eax, eax
0x180055782  jnz     loc_18005561D
0x180055788  mov     r8, [rsp+108h+var_C0]
0x18005578d  add     r12d, r13d
0x180055790  add     rsi, 68h ; 'h'
0x180055794  jmp     loc_1800555E1
0x180055799  mov     r8, [rdi]
0x18005579c  lea     rdx, aTooManyReferen; "too many references to \"%s\": max 6553"...
0x1800557a3  mov     rcx, r14
0x1800557a6  call    sqlite3ErrorMsg
0x1800557ab  mov     qword ptr [rsi+20h], 0
0x1800557b3  jmp     loc_18005561D
0x1800557b8  cmp     [r14+30h], edi
0x1800557bc  jnz     loc_18005561D
0x1800557c2  mov     rdx, rbp
0x1800557c5  mov     rcx, r14
0x1800557c8  call    sqlite3ProcessJoin
0x1800557cd  xor     r10d, r10d
0x1800557d0  test    eax, eax
0x1800557d2  jnz     loc_18005561D
0x1800557d8  mov     rdi, [rsp+108h+var_88]
0x1800557e0  mov     r8d, r10d
0x1800557e3  mov     [rsp+108h+var_CC], r10d
0x1800557e8  mov     ecx, r10d
0x1800557eb  cmp     [rdi], r10d
0x1800557ee  jle     short loc_18005581E
0x1800557f0  mov     eax, ecx
0x1800557f2  shl     rax, 5
0x1800557f6  mov     rdx, [rax+rdi+8]
0x1800557fb  cmp     byte ptr [rdx], 0B4h
0x1800557fe  jz      short loc_180055826
0x180055800  cmp     byte ptr [rdx], 8Dh
0x180055803  jnz     short loc_18005580E
0x180055805  mov     rax, [rdx+18h]
0x180055809  cmp     byte ptr [rax], 0B4h
0x18005580c  jz      short loc_180055826
0x18005580e  or      r8d, [rdx+4]
0x180055812  add     ecx, r13d
0x180055815  mov     [rsp+108h+var_CC], r8d
0x18005581a  cmp     ecx, [rdi]
0x18005581c  jl      short loc_1800557F0
0x18005581e  cmp     ecx, [rdi]
0x180055820  jge     loc_180055F7B
0x180055826  mov     rax, [r14]
0x180055829  mov     r15, r10
0x18005582c  mov     eax, [rax+30h]
0x18005582f  and     eax, 44h
0x180055832  mov     [rsp+108h+var_80], eax
0x180055839  mov     eax, r10d
0x18005583c  mov     [rsp+108h+var_A8], eax
0x180055840  cmp     [rdi], r10d
0x180055843  jle     loc_180055F67
0x180055849  mov     r12, [rsp+108h+var_C0]
0x18005584e  mov     edx, 400h
0x180055853  movsxd  rbx, eax
0x180055856  shl     rbx, 5
0x18005585a  mov     rcx, [rbx+rdi+8]
0x18005585f  mov     [rsp+108h+var_58], rcx
0x180055867  or      r8d, [rcx+4]
0x18005586b  cmp     byte ptr [rcx], 0B4h
0x18005586e  mov     [rsp+108h+var_CC], r8d
0x180055873  jz      short loc_1800558D4
0x180055875  cmp     byte ptr [rcx], 8Dh
0x180055878  jnz     short loc_180055883
0x18005587a  mov     rax, [rcx+18h]
0x18005587e  cmp     byte ptr [rax], 0B4h
0x180055881  jz      short loc_1800558D4
0x180055883  mov     r8, rcx
0x180055886  mov     rdx, r15
0x180055889  mov     rcx, r14
0x18005588c  call    sqlite3ExprListAppend
0x180055891  xor     r10d, r10d
0x180055894  mov     r15, rax
0x180055897  test    rax, rax
0x18005589a  jz      short loc_1800558CA
0x18005589c  movsxd  rcx, dword ptr [rax]
0x18005589f  mov     rax, [rbx+rdi+10h]
0x1800558a4  shl     rcx, 5
0x1800558a8  mov     [rcx+r15-10h], rax
0x1800558ad  movsxd  rcx, dword ptr [r15]
0x1800558b0  shl     rcx, 5
0x1800558b4  mov     eax, [rcx+r15-4]
0x1800558b9  xor     eax, [rbx+rdi+1Ch]
0x1800558bd  and     eax, 3
0x1800558c0  xor     [rcx+r15-4], eax
0x1800558c5  mov     [rbx+rdi+10h], r10
0x1800558ca  mov     [rbx+rdi+8], r10
0x1800558cf  jmp     loc_180055F42
0x1800558d4  cmp     byte ptr [rcx], 8Dh
0x1800558d7  mov     [rsp+108h+var_AC], r10d
0x1800558dc  jnz     short loc_1800558EC
0x1800558de  mov     rax, [rcx+10h]
0x1800558e2  mov     rdi, [rax+8]
0x1800558e6  mov     rax, [rcx+18h]
0x1800558ea  jmp     short loc_1800558F2
0x1800558ec  mov     rdi, r10
0x1800558ef  mov     rax, rcx
0x1800558f2  mov     r11d, [r12]
0x1800558f6  lea     rbx, [r12+8]
0x1800558fb  mov     eax, [rax+34h]
0x1800558fe  mov     esi, r10d
0x180055901  mov     [rsp+108h+var_C8], rbx
0x180055906  mov     [rsp+108h+var_A0], rdi
0x18005590b  mov     [rsp+108h+var_B8], eax
0x18005590f  mov     [rsp+108h+var_D0], r10d
0x180055914  mov     [rsp+108h+var_B0], r10d
0x180055919  test    r11d, r11d
0x18005591c  jle     loc_180055F12
0x180055922  mov     r12, [rsp+108h+var_60]
0x18005592a  mov     rax, [rbx+18h]
0x18005592e  mov     r9, [rbx+20h]
0x180055932  mov     [rsp+108h+var_D8], r9
0x180055937  mov     [rsp+108h+var_90], rax
0x18005593c  test    rax, rax
0x18005593f  jnz     short loc_180055949
0x180055941  mov     rax, [r9]
0x180055944  mov     [rsp+108h+var_90], rax
0x180055949  cmp     [r12+67h], r10b
0x18005594e  jnz     loc_180055F06
0x180055954  test    dword ptr [rbx+40h], 2000h
  ... truncated ...
```

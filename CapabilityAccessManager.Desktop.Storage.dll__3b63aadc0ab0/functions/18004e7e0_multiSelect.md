# multiSelect

- ea: `0x18004e7e0`
- end: `0x18004f646`
- name: `multiSelect`
- size: `3686`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x1800971f0`

## callees

- `0x180042af0`
- `0x180044640`
- `0x18004e7e0`
- `0x18004f650`
- `0x18004f6d0`
- `0x180060370`
- `0x1800714d0`
- `0x180075510`
- `0x180077210`
- `0x180078dc0`
- `0x1800795a0`
- `0x18007a350`
- `0x180086bd0`
- `0x180088240`
- `0x1800882e0`
- `0x18008c160`
- `0x1800971f0`
- `0x18009b280`
- `0x1800a2fd0`
- `0x1800a3040`
- `0x1800a30b0`
- `0x1800a3210`
- `0x1800a3b40`
- `0x1800ad880`
- `0x1800ad9e0`
- `0x1800aded0`
- `0x1800ae640`
- `0x1800b16b0`
- `0x1800c3f40`

## string_xrefs

- `0x18004e9fe`: `COMPOUND QUERY`
- `0x18004eaf8`: `%s USING TEMP B-TREE`
- `0x18004f1b5`: `%s USING TEMP B-TREE`

## pseudocode

```c
__int64 __fastcall multiSelect(__int64 *a1, unsigned __int8 *a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __int64 v4; // r15
  __int128 *v5; // rbx
  __int64 v6; // rdi
  unsigned __int8 *v7; // rsi
  __int64 v8; // r14
  __int64 *v9; // r13
  __int128 v10; // xmm1
  char v11; // dl
  int v12; // r8d
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // r8d
  __int64 v19; // r12
  unsigned __int8 *v20; // rbx
  int v21; // edi
  __int64 v22; // rax
  unsigned __int8 *v23; // rax
  const char *v25; // rax
  unsigned int v26; // ecx
  unsigned int v27; // ebx
  _QWORD *v28; // r12
  unsigned __int8 *i; // rax
  unsigned int v30; // edi
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rbx
  const char *v34; // rax
  unsigned int v35; // edi
  __int16 v36; // ax
  __int64 v37; // rdx
  unsigned int v38; // r14d
  __int64 v39; // rbx
  unsigned int v40; // edi
  __int64 v41; // r14
  unsigned __int8 *v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rcx
  __int16 v45; // ax
  __int64 v46; // rbx
  unsigned int v47; // eax
  __int64 v48; // rdx
  unsigned int v49; // ebx
  __int64 v50; // rdi
  unsigned int v51; // eax
  unsigned int v52; // ecx
  unsigned int v53; // edi
  char v54; // al
  unsigned int v55; // ebx
  unsigned __int8 v56; // al
  unsigned int v57; // edi
  __int64 v58; // rcx
  unsigned int v59; // edi
  __int64 v60; // r8
  unsigned int v61; // eax
  int v62; // ecx
  unsigned int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int16 v67; // ax
  __int64 v68; // rcx
  __int16 v69; // bx
  unsigned __int8 *v70; // rcx
  unsigned __int64 v71; // rax
  __int64 v72; // rcx
  __int16 v73; // dx
  unsigned __int64 v74; // rcx
  __int16 v75; // r8
  __int16 v76; // r8
  __int16 v77; // dx
  unsigned int v78; // ebx
  unsigned __int8 *j; // rax
  char v80; // cl
  __int64 v81; // rbx
  const char *v82; // rax
  unsigned int v83; // eax
  bool v84; // zf
  __int64 v85; // rdx
  unsigned int v86; // ebx
  __int64 v87; // r14
  unsigned int v88; // r12d
  __int64 v89; // rdi
  unsigned __int8 *v90; // rcx
  __int64 v91; // r8
  __int64 v92; // rcx
  __int16 v93; // ax
  unsigned int v94; // ebx
  unsigned int v95; // r14d
  unsigned int v96; // edi
  unsigned int v97; // ebx
  unsigned int v98; // r12d
  int v99; // r12d
  __int64 v100; // rax
  __int64 v101; // rbx
  int v102; // edi
  __int64 *v103; // r14
  __int64 v104; // rbx
  __int64 v105; // rdx
  __int64 v106; // rax
  int *v107; // rcx
  int v108; // r13d
  __int64 v109; // r14
  _QWORD *v110; // rdi
  unsigned __int8 *v111; // r12
  __int64 v112; // rdx
  __int64 *v113; // rax
  int v114; // ecx
  __int64 v115; // rdx
  unsigned int v116; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v117; // [rsp+44h] [rbp-95h] BYREF
  unsigned int v118; // [rsp+48h] [rbp-91h]
  unsigned int v119; // [rsp+4Ch] [rbp-8Dh]
  unsigned int v120; // [rsp+50h] [rbp-89h]
  __int64 v121; // [rsp+58h] [rbp-81h]
  __int64 v122; // [rsp+60h] [rbp-79h]
  __int64 v123; // [rsp+68h] [rbp-71h]
  __int128 v124; // [rsp+70h] [rbp-69h] BYREF
  __int128 v125; // [rsp+80h] [rbp-59h]
  __int64 v126; // [rsp+90h] [rbp-49h]
  _BYTE v127[4]; // [rsp+98h] [rbp-41h] BYREF
  unsigned int v128; // [rsp+9Ch] [rbp-3Dh]
  __int64 v129; // [rsp+A0h] [rbp-39h]
  int v130; // [rsp+A8h] [rbp-31h]
  __int64 v131; // [rsp+B0h] [rbp-29h]
  _BYTE v132[4]; // [rsp+C0h] [rbp-19h] BYREF
  unsigned int v133; // [rsp+C4h] [rbp-15h]
  __int64 v134; // [rsp+C8h] [rbp-11h]
  int v135; // [rsp+D0h] [rbp-9h]
  __int64 v136; // [rsp+D8h] [rbp-1h]
  unsigned int v138; // [rsp+148h] [rbp+6Fh]
  int v140; // [rsp+158h] [rbp+7Fh] BYREF

  v3 = *a3;
  v4 = a1[2];
  v5 = a3;
  v6 = *a1;
  v7 = a2;
  v8 = *((_QWORD *)a2 + 10);
  v9 = a1;
  v122 = *a1;
  v10 = a3[1];
  v124 = v3;
  v126 = *((_QWORD *)a3 + 4);
  v125 = v10;
  if ( !v4 )
  {
    if ( !a1[21] && (*(_BYTE *)(v6 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v4 = sqlite3VdbeCreate(a1);
  }
  v11 = v124;
  if ( (_BYTE)v124 == 12 )
  {
    v12 = DWORD1(v124);
    v13 = **((unsigned int **)v7 + 4);
    v14 = *(int *)(v4 + 144);
    if ( *(_DWORD *)(v4 + 148) > (int)v14 )
    {
      *(_DWORD *)(v4 + 144) = v14 + 1;
      v15 = 3 * v14;
      v16 = *(_QWORD *)(v4 + 136);
      *(_DWORD *)(v16 + 8 * v15) = 118;
      *(_DWORD *)(v16 + 8 * v15 + 4) = v12;
      *(_DWORD *)(v16 + 8 * v15 + 8) = v13;
      v17 = v16 + 8 * v15;
      *(_DWORD *)(v17 + 12) = 0;
      *(_QWORD *)(v17 + 16) = 0;
    }
    else
    {
      growOp3(v4, 118, DWORD1(v124), v13, 0);
    }
    v11 = 14;
    LOBYTE(v124) = 14;
  }
  v18 = *((_DWORD *)v7 + 1);
  if ( (v18 & 0x400) != 0 )
  {
    v19 = *((_QWORD *)v7 + 12);
    v20 = v7;
    v21 = 1;
    if ( !*((_QWORD *)v7 + 14) )
    {
      while ( 1 )
      {
        v22 = *((_QWORD *)v20 + 10);
        if ( !v22 )
          break;
        v21 += v19 == 0;
        v20 = (unsigned __int8 *)*((_QWORD *)v20 + 10);
        if ( *(_QWORD *)(v22 + 112) )
          goto LABEL_15;
      }
      v25 = "S";
      if ( v21 == 1 )
        v25 = byte_180122168;
      sqlite3VdbeExplain(v9, 0, "SCAN %d CONSTANT ROW%s", v21, v25);
      do
      {
        selectInnerLoop((_DWORD)v9, (_DWORD)v20, -1, 0, 0, (__int64)&v124, 1, 1);
        if ( v19 )
          break;
        *((_WORD *)v20 + 1) = v21;
        v20 = (unsigned __int8 *)*((_QWORD *)v20 + 11);
      }
      while ( v20 );
      v26 = 0;
      *((_DWORD *)a3 + 3) = HIDWORD(v124);
      *((_DWORD *)a3 + 4) = v125;
      return v26;
    }
LABEL_15:
    v6 = v122;
    v5 = a3;
  }
  v123 = 0;
  if ( (v18 & 0x2000) == 0 )
  {
LABEL_20:
    if ( *((_QWORD *)v7 + 9) )
      return multiSelectOrderBy(v9, v7, v5);
    if ( !*(_QWORD *)(v8 + 80) )
    {
      sqlite3VdbeExplain(v9, 1, "COMPOUND QUERY");
      sqlite3VdbeExplain(v9, 1, "LEFT-MOST SUBQUERY");
      v11 = v124;
    }
    if ( *v7 == 134 )
      goto LABEL_133;
    if ( *v7 != 135 )
    {
      if ( *v7 != 136 )
      {
        v116 = *((_DWORD *)v9 + 13);
        v27 = v116;
        *((_DWORD *)v9 + 13) = v116 + 2;
        *((_DWORD *)v7 + 5) = sqlite3VdbeAddOp2(v4, 118, v27, 0);
        v28 = v7 + 88;
        for ( i = v7; *((_QWORD *)i + 11); i = (unsigned __int8 *)*((_QWORD *)i + 11) )
          ;
        *((_DWORD *)i + 1) |= 0x20u;
        v127[0] = 1;
        v129 = 0;
        v131 = 0;
        v130 = 0;
        v128 = v27;
        v138 = sqlite3Select(v9, v8, v127);
        v26 = v138;
        if ( v138 )
          goto LABEL_209;
        v30 = v27 + 1;
        v120 = v27 + 1;
        v31 = sqlite3VdbeAddOp2(v4, 118, v27 + 1, 0);
        v32 = *v7;
        *((_DWORD *)v7 + 6) = v31;
        v33 = *((_QWORD *)v7 + 12);
        *((_QWORD *)v7 + 10) = 0;
        *((_QWORD *)v7 + 12) = 0;
        v128 = v30;
        v34 = (const char *)sqlite3SelectOpName(v32);
        sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v34);
        v35 = sqlite3Select(v9, v7, v127);
        v138 = v35;
        v123 = *((_QWORD *)v7 + 10);
        *((_QWORD *)v7 + 10) = v8;
        v36 = *(_WORD *)(v8 + 2);
        if ( *((__int16 *)v7 + 1) > v36 )
          *((_WORD *)v7 + 1) = v36;
        v37 = *((_QWORD *)v7 + 12);
        if ( v37 )
          sqlite3ExprDeleteNN(v122, v37);
        *((_QWORD *)v7 + 12) = v33;
        if ( v35 )
          goto LABEL_172;
        v38 = *((_DWORD *)v9 + 17) - 1;
        v119 = v38;
        *((_DWORD *)v9 + 17) = v38 - 1;
        if ( *((_DWORD *)v7 + 2) )
          goto LABEL_86;
        v39 = *((_QWORD *)v7 + 12);
        v121 = v39;
        if ( !v39 )
          goto LABEL_86;
        v40 = ++*((_DWORD *)v9 + 14);
        *((_DWORD *)v7 + 2) = v40;
        v41 = v9[2];
        v118 = v40;
        if ( !v41 )
        {
          if ( !v9[21] && (*(_BYTE *)(*v9 + 96) & 8) == 0 )
            *((_BYTE *)v9 + 35) = 1;
          v41 = sqlite3VdbeCreate(v9);
        }
        v42 = *(unsigned __int8 **)(v39 + 16);
        if ( v42 )
        {
          if ( (*((_DWORD *)v42 + 1) & 0x800) != 0 )
          {
            v43 = *((unsigned int *)v42 + 2);
LABEL_58:
            v140 = v43;
LABEL_59:
            sqlite3VdbeAddOp2(v41, 71, v43, v40);
            if ( v140 )
            {
              if ( v140 >= 0 )
              {
                v45 = sqlite3LogEst(v140);
                if ( *((__int16 *)v7 + 1) > v45 )
                {
                  *((_DWORD *)v7 + 1) |= 0x4000u;
                  *((_WORD *)v7 + 1) = v45;
                }
              }
            }
            else
            {
              sqlite3VdbeGoto(v41, v119);
            }
LABEL_74:
            if ( *(_QWORD *)(v39 + 24) )
            {
              v49 = *((_DWORD *)v9 + 14) + 1;
              *((_DWORD *)v9 + 14) = v49;
              *((_DWORD *)v7 + 3) = v49;
              ++*((_DWORD *)v9 + 14);
              if ( v9[2] )
              {
                v50 = *(_QWORD *)(v121 + 24);
                v51 = sqlite3ExprCodeTarget(v9, v50, v49);
                if ( v51 != v49 )
                {
                  if ( v50 && ((*(_DWORD *)(v50 + 4) & 0x400000) != 0 || *(_BYTE *)v50 == 0xB0) )
                    v52 = 80;
                  else
                    v52 = 81;
                  sqlite3VdbeAddOp2(v9[2], v52, v51, v49);
                }
                v40 = v118;
              }
              sqlite3VdbeAddOp1(v41, 13, v49);
              sqlite3VdbeAddOp3(v41, 160, v40, v49 + 1, v49);
            }
            v38 = v119;
LABEL_86:
            v53 = v116;
            sqlite3VdbeAddOp2(v4, 36, v116, v38);
            v54 = *((_BYTE *)v9 + 31);
            if ( v54 )
            {
              v56 = v54 - 1;
              *((_BYTE *)v9 + 31) = v56;
              v55 = *((_DWORD *)v9 + v56 + 56);
            }
            else
            {
              v55 = ++*((_DWORD *)v9 + 14);
            }
            v57 = sqlite3VdbeAddOp2(v4, 134, v53, v55);
            sqlite3VdbeAddOp4Int(v4, 28, v120, v38 - 1, v55, 0);
            if ( v55 )
            {
              v58 = *((unsigned __int8 *)v9 + 31);
              if ( (unsigned __int8)v58 < 8u )
              {
                *((_DWORD *)v9 + v58 + 56) = v55;
                ++*((_BYTE *)v9 + 31);
              }
            }
            selectInnerLoop((_DWORD)v9, (_DWORD)v7, v116, 0, 0, (__int64)&v124, v38 - 1, v38);
            sqlite3VdbeResolveLabel(v4, v38 - 1);
            sqlite3VdbeAddOp2(v4, 39, v116, v57);
            sqlite3VdbeResolveLabel(v4, v38);
            sqlite3VdbeAddOp2(v4, 122, v116 + 1, 0);
            sqlite3VdbeAddOp2(v4, 122, v116, 0);
            goto LABEL_172;
          }
          if ( *v42 == 173 )
          {
            v44 = *((_QWORD *)v42 + 2);
            v117 = 0;
            if ( (unsigned int)sqlite3ExprIsInteger(v44, &v117) )
            {
              v43 = -v117;
              goto LABEL_58;
            }
          }
          else if ( *v42 == 174 && (unsigned int)sqlite3ExprIsInteger(*((_QWORD *)v42 + 2), &v140) )
          {
            v43 = (unsigned int)v140;
            goto LABEL_59;
          }
        }
        if ( v9[2] )
        {
          v46 = *(_QWORD *)(v39 + 16);
          v47 = sqlite3ExprCodeTarget(v9, v46, v40);
          if ( v47 != v40 )
          {
            if ( v46 && ((*(_DWORD *)(v46 + 4) & 0x400000) != 0 || *(_BYTE *)v46 == 0xB0) )
              v48 = 80;
            else
              v48 = 81;
            sqlite3VdbeAddOp2(v9[2], v48, v47, v40);
          }
          v39 = v121;
        }
        sqlite3VdbeAddOp1(v41, 13, v40);
        sqlite3VdbeAddOp2(v41, 17, v40, v119);
        goto LABEL_74;
      }
LABEL_133:
      if ( v11 == 1 )
      {
        v78 = DWORD1(v124);
        v28 = v7 + 88;
        v118 = DWORD1(v124);
      }
      else
      {
        v118 = *((_DWORD *)v9 + 13);
        v78 = v118;
        *((_DWORD *)v9 + 13) = v118 + 1;
        *((_DWORD *)v7 + 5) = sqlite3VdbeAddOp2(v4, 118, v78, 0);
        v28 = v7 + 88;
        for ( j = v7; *((_QWORD *)j + 11); j = (unsigned __int8 *)*((_QWORD *)j + 11) )
          ;
        *((_DWORD *)j + 1) |= 0x20u;
      }
      v133 = v78;
      v132[0] = 1;
      v134 = 0;
      v136 = 0;
      v135 = 0;
      v138 = sqlite3Select(v9, v8, v132);
      v26 = v138;
      if ( v138 )
        goto LABEL_209;
      v80 = *v7;
      *((_QWORD *)v7 + 10) = 0;
      v81 = *((_QWORD *)v7 + 12);
      *((_QWORD *)v7 + 12) = 0;
      v132[0] = (v80 == -120) + 1;
      v82 = (const char *)((__int64 (*)(void))sqlite3SelectOpName)();
      sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v82);
      v83 = sqlite3Select(v9, v7, v132);
      v84 = *v7 == 0x86;
      v138 = v83;
      v123 = *((_QWORD *)v7 + 10);
      *((_QWORD *)v7 + 10) = v8;
      *((_QWORD *)v7 + 9) = 0;
      if ( v84 )
        *((_WORD *)v7 + 1) = sqlite3LogEstAdd(*((unsigned __int16 *)v7 + 1), *(unsigned __int16 *)(v8 + 2));
      v85 = *((_QWORD *)v7 + 12);
      if ( v85 )
        sqlite3ExprDeleteNN(v6, v85);
      *((_QWORD *)v7 + 12) = v81;
      v84 = (_BYTE)v124 == 1;
      *((_QWORD *)v7 + 1) = 0;
      if ( v84 || *(_BYTE *)(v6 + 103) )
        goto LABEL_172;
      v86 = *((_DWORD *)v9 + 17) - 1;
      v117 = v86;
      *((_DWORD *)v9 + 17) = v86 - 1;
      if ( *((_DWORD *)v7 + 2) )
        goto LABEL_170;
      v87 = *((_QWORD *)v7 + 12);
      if ( !v87 )
        goto LABEL_170;
      v88 = ++*((_DWORD *)v9 + 14);
      *((_DWORD *)v7 + 2) = v88;
      v89 = v9[2];
      if ( !v89 )
      {
        if ( !v9[21] && (*(_BYTE *)(*v9 + 96) & 8) == 0 )
          *((_BYTE *)v9 + 35) = 1;
        v89 = sqlite3VdbeCreate(v9);
      }
      v90 = *(unsigned __int8 **)(v87 + 16);
      if ( v90 )
      {
        if ( (*((_DWORD *)v90 + 1) & 0x800) != 0 )
        {
          v91 = *((unsigned int *)v90 + 2);
LABEL_161:
          v140 = v91;
LABEL_162:
          sqlite3VdbeAddOp2(v89, 71, v91, v88);
          if ( v140 )
          {
            if ( v140 >= 0 )
            {
              v93 = sqlite3LogEst(v140);
              if ( *((__int16 *)v7 + 1) > v93 )
              {
                *((_DWORD *)v7 + 1) |= 0x4000u;
                *((_WORD *)v7 + 1) = v93;
              }
            }
          }
          else
          {
            sqlite3VdbeGoto(v89, v86);
          }
          goto LABEL_168;
        }
        if ( *v90 == 173 )
        {
          v92 = *((_QWORD *)v90 + 2);
          v116 = 0;
          if ( (unsigned int)sqlite3ExprIsInteger(v92, &v116) )
          {
            v91 = -v116;
            goto LABEL_161;
          }
        }
        else if ( *v90 == 174 && (unsigned int)sqlite3ExprIsInteger(*((_QWORD *)v90 + 2), &v140) )
        {
          v91 = (unsigned int)v140;
          goto LABEL_162;
        }
      }
      sqlite3ExprCode(v9, *(_QWORD *)(v87 + 16), v88);
      sqlite3VdbeAddOp1(v89, 13, v88);
      sqlite3VdbeAddOp2(v89, 17, v88, v86);
LABEL_168:
      if ( *(_QWORD *)(v87 + 24) )
      {
        v94 = *((_DWORD *)v9 + 14) + 1;
        *((_DWORD *)v9 + 14) = v94;
        *((_DWORD *)v7 + 3) = v94;
        ++*((_DWORD *)v9 + 14);
        sqlite3ExprCode(v9, *(_QWORD *)(v87 + 24), v94);
        sqlite3VdbeAddOp1(v89, 13, v94);
        sqlite3VdbeAddOp3(v89, 160, v88, v94 + 1, v94);
        v86 = v117;
      }
LABEL_170:
      v95 = v118;
      sqlite3VdbeAddOp2(v4, 36, v118, v86);
      v96 = v117;
      v97 = *(_DWORD *)(v4 + 144);
      v98 = v117 - 1;
      selectInnerLoop((_DWORD)v9, (_DWORD)v7, v95, 0, 0, (__int64)&v124, v117 - 1, v117);
      sqlite3VdbeResolveLabel(v4, v98);
      sqlite3VdbeAddOp2(v4, 39, v95, v97);
      sqlite3VdbeResolveLabel(v4, v96);
      sqlite3VdbeAddOp2(v4, 122, v95, 0);
LABEL_171:
      v28 = v7 + 88;
LABEL_172:
      if ( !*v28 )
        sqlite3VdbeExplainPop(v9);
      goto LABEL_174;
    }
    *(_DWORD *)(v8 + 8) = *((_DWORD *)v7 + 2);
    *(_DWORD *)(v8 + 12) = *((_DWORD *)v7 + 3);
    *(_QWORD *)(v8 + 96) = *((_QWORD *)v7 + 12);
    v140 = 0;
    v138 = sqlite3Select(v9, v8, &v124);
    v26 = v138;
    *(_QWORD *)(v8 + 96) = 0;
    if ( v138 )
      goto LABEL_209;
    *((_QWORD *)v7 + 10) = 0;
    v59 = 0;
    v60 = *(unsigned int *)(v8 + 8);
    *((_DWORD *)v7 + 2) = v60;
    *((_DWORD *)v7 + 3) = *(_DWORD *)(v8 + 12);
    if ( (_DWORD)v60 )
    {
      v61 = sqlite3VdbeAddOp1(v4, 17, v60);
      v62 = *((_DWORD *)v7 + 3);
      v59 = v61;
      if ( v62 )
        sqlite3VdbeAddOp3(v4, 160, *((_DWORD *)v7 + 2), v62 + 1, v62);
    }
    sqlite3VdbeExplain(v9, 1, "UNION ALL");
    v63 = sqlite3Select(v9, v7, &v124);
    v64 = *((unsigned __int16 *)v7 + 1);
    v138 = v63;
    v65 = *((_QWORD *)v7 + 10);
    *((_QWORD *)v7 + 10) = v8;
    v66 = *(unsigned __int16 *)(v8 + 2);
    v123 = v65;
    v67 = sqlite3LogEstAdd(v64, v66);
    v68 = *((_QWORD *)v7 + 12);
    v69 = v67;
    *((_WORD *)v7 + 1) = v67;
    if ( v68 )
    {
      v70 = *(unsigned __int8 **)(v68 + 16);
      if ( v70 )
      {
        if ( (*((_DWORD *)v70 + 1) & 0x800) != 0 )
        {
          LODWORD(v71) = *((_DWORD *)v70 + 2);
LABEL_107:
          v140 = v71;
LABEL_108:
          if ( (int)v71 <= 0 )
            goto LABEL_131;
          v71 = (int)v71;
          v73 = 40;
          v74 = v71;
          v75 = 40;
          if ( (unsigned __int64)(int)v71 >= 8 )
          {
            if ( (unsigned __int64)(int)v71 > 0xFF )
            {
              do
              {
                v75 += 40;
                v74 >>= 4;
              }
              while ( v74 > 0xFF );
            }
            for ( ; v74 > 0xF; v74 >>= 1 )
              v75 += 10;
          }
          else
          {
            if ( (unsigned __int64)(int)v71 < 2 )
            {
              v76 = 0;
              goto LABEL_119;
            }
            do
            {
              v75 -= 10;
              v74 *= 2LL;
            }
            while ( v74 < 8 );
          }
          v76 = *((_WORD *)qword_18013C8F0 + (v74 & 7)) + v75 - 10;
LABEL_119:
          if ( v69 <= v76 )
            goto LABEL_131;
          if ( (unsigned __int64)(int)v71 >= 8 )
          {
            if ( (unsigned __int64)(int)v71 > 0xFF )
            {
              do
              {
                v73 += 40;
                v71 >>= 4;
              }
              while ( v71 > 0xFF );
            }
            for ( ; v71 > 0xF; v71 >>= 1 )
              v73 += 10;
          }
          else
          {
            if ( (unsigned __int64)(int)v71 < 2 )
            {
              v77 = 0;
LABEL_130:
              *((_WORD *)v7 + 1) = v77;
              goto LABEL_131;
            }
            do
            {
              v73 -= 10;
              v71 *= 2LL;
            }
            while ( v71 < 8 );
          }
          v77 = *((_WORD *)qword_18013C8F0 + (v71 & 7)) + v73 - 10;
          goto LABEL_130;
        }
        if ( *v70 == 173 )
        {
          v72 = *((_QWORD *)v70 + 2);
          v116 = 0;
          if ( !(unsigned int)sqlite3ExprIsInteger(v72, &v116) )
            goto LABEL_131;
          LODWORD(v71) = -v116;
          goto LABEL_107;
        }
        if ( *v70 == 174 && (unsigned int)sqlite3ExprIsInteger(*((_QWORD *)v70 + 2), &v140) )
        {
          LODWORD(v71) = v140;
          goto LABEL_108;
        }
      }
    }
LABEL_131:
    if ( v59 )
      sqlite3VdbeJumpHere(v4, v59);
    goto LABEL_171;
  }
  v23 = v7;
  while ( (*((_DWORD *)v23 + 1) & 0x2000) != 0 )
  {
    v23 = (unsigned __int8 *)*((_QWORD *)v23 + 10);
    if ( !v23 )
      goto LABEL_20;
  }
  generateWithRecursiveQuery(v9, v7, &v124);
  v138 = 0;
LABEL_174:
  if ( !*((_DWORD *)v9 + 12) && (v7[4] & 0x20) != 0 )
  {
    v99 = **((_DWORD **)v7 + 4);
    v100 = sqlite3KeyInfoAlloc(v122, (unsigned int)v99, 1);
    v121 = v100;
    v101 = v100;
    if ( !v100 )
    {
      v26 = 7;
      v138 = 7;
      goto LABEL_209;
    }
    v102 = 0;
    v103 = (__int64 *)(v100 + 32);
    if ( v99 > 0 )
    {
      v104 = v122;
      while ( 1 )
      {
        v105 = *((_QWORD *)v7 + 10);
        if ( !v105 )
          break;
        v106 = multiSelectCollSeq(v9, v105, (unsigned int)v102);
        if ( !v106 )
          goto LABEL_184;
LABEL_186:
        *v103 = v106;
        if ( !v106 )
          *v103 = *(_QWORD *)(v104 + 16);
        ++v102;
        ++v103;
        if ( v102 >= v99 )
        {
          v101 = v121;
          goto LABEL_190;
        }
      }
      v106 = 0;
LABEL_184:
      v107 = (int *)*((_QWORD *)v7 + 4);
      if ( v102 < *v107 )
        v106 = sqlite3ExprCollSeq(v9, *(_QWORD *)&v107[8 * v102 + 2]);
      goto LABEL_186;
    }
LABEL_190:
    v108 = v99;
    do
    {
      v109 = 0;
      v110 = (_QWORD *)(v4 + 136);
      do
      {
        v111 = &v7[4 * v109];
        if ( *((int *)v111 + 5) < 0 )
          break;
        v112 = *(int *)&v7[4 * v109 + 20];
        v113 = *(_BYTE *)(*(_QWORD *)v4 + 103LL) ? &qword_18013FEA8 : (__int64 *)(*v110 + 24 * v112);
        *((_DWORD *)v113 + 2) = v108;
        v114 = (*(_DWORD *)v101)++;
        if ( *(_BYTE *)(*(_QWORD *)v4 + 103LL) )
        {
          if ( !*(_QWORD *)(*(_QWORD *)v4 + 776LL) )
          {
            *(_DWORD *)v101 = v114;
            if ( !v114 )
              sqlite3DbNNFreeNN(*(_QWORD *)(v101 + 16), v101);
          }
          v110 = (_QWORD *)(v4 + 136);
        }
        else
        {
          v84 = *(_BYTE *)(*v110 + 24 * v112 + 1) == 0;
          v115 = *v110 + 24 * v112;
          if ( v84 )
          {
            *(_QWORD *)(v115 + 16) = v101;
            *(_BYTE *)(v115 + 1) = -8;
          }
          else
          {
            vdbeChangeP4Full(v4, v115, v101, 4294967288LL);
          }
        }
        v109 = (unsigned int)(v109 + 1);
        *((_DWORD *)v111 + 5) = -1;
      }
      while ( (int)v109 < 2 );
      v7 = (unsigned __int8 *)*((_QWORD *)v7 + 10);
    }
    while ( v7 );
    v84 = (*(_DWORD *)v101)-- == 1;
    v9 = a1;
    if ( v84 )
      sqlite3DbNNFreeNN(*(_QWORD *)(v101 + 16), v101);
  }
  v26 = v138;
LABEL_209:
  *((_DWORD *)a3 + 3) = HIDWORD(v124);
  *((_DWORD *)a3 + 4) = v125;
  if ( v123 )
  {
    sqlite3ParserAddCleanup(v9, sqlite3SelectDelete);
    return v138;
  }
  return v26;
}

```

## disassembly

```asm
0x18004e7e0  mov     [rsp-8+arg_10], r8
0x18004e7e5  mov     [rsp-8+arg_0], rcx
0x18004e7ea  push    rbp
0x18004e7eb  push    rbx
0x18004e7ec  push    rsi
0x18004e7ed  push    rdi
0x18004e7ee  push    r12
0x18004e7f0  push    r13
0x18004e7f2  push    r14
0x18004e7f4  push    r15
0x18004e7f6  lea     rbp, [rsp-1Fh]
0x18004e7fb  sub     rsp, 0F8h
0x18004e802  movups  xmm0, xmmword ptr [r8]
0x18004e806  mov     r15, [rcx+10h]
0x18004e80a  mov     rbx, r8
0x18004e80d  mov     rdi, [rcx]
0x18004e810  mov     rsi, rdx
0x18004e813  mov     r14, [rdx+50h]
0x18004e817  mov     r13, rcx
0x18004e81a  mov     [rbp+57h+var_D0], rdi
0x18004e81e  movups  xmm1, xmmword ptr [r8+10h]
0x18004e823  movups  [rbp+57h+var_C0], xmm0
0x18004e827  movsd   xmm0, qword ptr [r8+20h]
0x18004e82d  movsd   [rbp+57h+var_A0], xmm0
0x18004e832  movups  [rbp+57h+var_B0], xmm1
0x18004e836  test    r15, r15
0x18004e839  jnz     short loc_18004E856
0x18004e83b  cmp     [rcx+0A8h], r15
0x18004e842  jnz     short loc_18004E84E
0x18004e844  test    byte ptr [rdi+60h], 8
0x18004e848  jnz     short loc_18004E84E
0x18004e84a  mov     byte ptr [rcx+23h], 1
0x18004e84e  call    sqlite3VdbeCreate
0x18004e853  mov     r15, rax
0x18004e856  movzx   edx, byte ptr [rbp+57h+var_C0]
0x18004e85a  xor     r12d, r12d
0x18004e85d  cmp     dl, 0Ch
0x18004e860  jnz     short loc_18004E8C8
0x18004e862  mov     rcx, [rsi+20h]
0x18004e866  mov     r8d, dword ptr [rbp+57h+var_C0+4]
0x18004e86a  mov     r9d, [rcx]
0x18004e86d  movsxd  rcx, dword ptr [r15+90h]
0x18004e874  cmp     [r15+94h], ecx
0x18004e87b  jg      short loc_18004E891
0x18004e87d  mov     edx, 76h ; 'v'
0x18004e882  mov     dword ptr [rsp+130h+var_110], r12d
0x18004e887  mov     rcx, r15
0x18004e88a  call    growOp3
0x18004e88f  jmp     short loc_18004E8C3
0x18004e891  lea     eax, [rcx+1]
0x18004e894  mov     [r15+90h], eax
0x18004e89b  lea     rcx, [rcx+rcx*2]
0x18004e89f  mov     rax, [r15+88h]
0x18004e8a6  mov     dword ptr [rax+rcx*8], 76h ; 'v'
0x18004e8ad  mov     [rax+rcx*8+4], r8d
0x18004e8b2  mov     [rax+rcx*8+8], r9d
0x18004e8b7  lea     rdx, [rax+rcx*8]
0x18004e8bb  mov     [rdx+0Ch], r12d
0x18004e8bf  mov     [rdx+10h], r12
0x18004e8c3  mov     dl, 0Eh
0x18004e8c5  mov     byte ptr [rbp+57h+var_C0], dl
0x18004e8c8  mov     r8d, [rsi+4]
0x18004e8cc  bt      r8d, 0Ah
0x18004e8d1  jnb     short loc_18004E910
0x18004e8d3  mov     r12, [rsi+60h]
0x18004e8d7  xor     ecx, ecx
0x18004e8d9  test    r12, r12
0x18004e8dc  mov     rbx, rsi
0x18004e8df  mov     edi, 1
0x18004e8e4  setz    cl
0x18004e8e7  cmp     qword ptr [rsi+70h], 0
0x18004e8ec  jnz     short loc_18004E905
0x18004e8ee  xchg    ax, ax
0x18004e8f0  mov     rax, [rbx+50h]
0x18004e8f4  test    rax, rax
0x18004e8f7  jz      short loc_18004E954
0x18004e8f9  add     edi, ecx
0x18004e8fb  mov     rbx, rax
0x18004e8fe  cmp     qword ptr [rax+70h], 0
0x18004e903  jz      short loc_18004E8F0
0x18004e905  mov     rdi, [rbp+57h+var_D0]
0x18004e909  xor     r12d, r12d
0x18004e90c  mov     rbx, [rbp+57h+arg_10]
0x18004e910  mov     [rbp+57h+var_C8], r12
0x18004e914  bt      r8d, 0Dh
0x18004e919  jnb     short loc_18004E936
0x18004e91b  mov     rax, rsi
0x18004e91e  xchg    ax, ax
0x18004e920  test    dword ptr [rax+4], 2000h
0x18004e927  jz      loc_18004E9DF
0x18004e92d  mov     rax, [rax+50h]
0x18004e931  test    rax, rax
0x18004e934  jnz     short loc_18004E920
0x18004e936  cmp     qword ptr [rsi+48h], 0
0x18004e93b  jz      loc_18004E9F7
0x18004e941  mov     r8, rbx
0x18004e944  mov     rdx, rsi
0x18004e947  mov     rcx, r13
0x18004e94a  call    multiSelectOrderBy
0x18004e94f  jmp     loc_18004F632
0x18004e954  lea     rcx, byte_180122168
0x18004e95b  cmp     edi, 1
0x18004e95e  lea     rax, aS; "S"
0x18004e965  mov     r9d, edi
0x18004e968  cmovz   rax, rcx
0x18004e96c  lea     r8, aScanDConstantR; "SCAN %d CONSTANT ROW%s"
0x18004e973  xor     edx, edx
0x18004e975  mov     [rsp+130h+var_110], rax
0x18004e97a  mov     rcx, r13
0x18004e97d  call    sqlite3VdbeExplain
0x18004e982  xor     esi, esi
0x18004e984  mov     [rsp+130h+var_F8], 1
0x18004e98c  lea     rax, [rbp+57h+var_C0]
0x18004e990  mov     [rsp+130h+var_100], 1
0x18004e998  xor     r9d, r9d
0x18004e99b  mov     [rsp+130h+var_108], rax
0x18004e9a0  mov     r8d, 0FFFFFFFFh
0x18004e9a6  mov     rdx, rbx
0x18004e9a9  mov     [rsp+130h+var_110], rsi
0x18004e9ae  mov     rcx, r13
0x18004e9b1  call    selectInnerLoop
0x18004e9b6  test    r12, r12
0x18004e9b9  jnz     short loc_18004E9C8
0x18004e9bb  mov     [rbx+2], di
0x18004e9bf  mov     rbx, [rbx+58h]
0x18004e9c3  test    rbx, rbx
0x18004e9c6  jnz     short loc_18004E984
0x18004e9c8  mov     rdx, [rbp+57h+arg_10]
0x18004e9cc  mov     ecx, esi
0x18004e9ce  mov     eax, dword ptr [rbp+57h+var_C0+0Ch]
0x18004e9d1  mov     [rdx+0Ch], eax
0x18004e9d4  mov     eax, dword ptr [rbp+57h+var_B0]
0x18004e9d7  mov     [rdx+10h], eax
0x18004e9da  jmp     loc_18004F630
0x18004e9df  lea     r8, [rbp+57h+var_C0]
0x18004e9e3  mov     rdx, rsi
0x18004e9e6  mov     rcx, r13
0x18004e9e9  call    generateWithRecursiveQuery
0x18004e9ee  mov     [rbp+57h+arg_8], r12d
0x18004e9f2  jmp     loc_18004F466
0x18004e9f7  cmp     qword ptr [r14+50h], 0
0x18004e9fc  jnz     short loc_18004EA2A
0x18004e9fe  lea     r8, aCompoundQuery; "COMPOUND QUERY"
0x18004ea05  mov     edx, 1
0x18004ea0a  mov     rcx, r13
0x18004ea0d  call    sqlite3VdbeExplain
0x18004ea12  lea     r8, aLeftMostSubque; "LEFT-MOST SUBQUERY"
0x18004ea19  mov     edx, 1
0x18004ea1e  mov     rcx, r13
0x18004ea21  call    sqlite3VdbeExplain
0x18004ea26  movzx   edx, byte ptr [rbp+57h+var_C0]
0x18004ea2a  movzx   ecx, byte ptr [rsi]
0x18004ea2d  sub     ecx, 86h
0x18004ea33  jz      loc_18004F104
0x18004ea39  sub     ecx, 1
0x18004ea3c  jz      loc_18004EEA8
0x18004ea42  cmp     ecx, 1
0x18004ea45  jz      loc_18004F104
0x18004ea4b  mov     ebx, [r13+34h]
0x18004ea4f  xor     r9d, r9d
0x18004ea52  mov     r8d, ebx
0x18004ea55  mov     [rsp+130h+var_F0], ebx
0x18004ea59  mov     edx, 76h ; 'v'
0x18004ea5e  mov     rcx, r15
0x18004ea61  lea     eax, [rbx+2]
0x18004ea64  mov     [r13+34h], eax
0x18004ea68  call    sqlite3VdbeAddOp2
0x18004ea6d  mov     [rsi+14h], eax
0x18004ea70  lea     r12, [rsi+58h]
0x18004ea74  cmp     qword ptr [r12], 0
0x18004ea79  mov     rax, rsi
0x18004ea7c  jz      short loc_18004EA8B
0x18004ea7e  xchg    ax, ax
0x18004ea80  mov     rax, [rax+58h]
0x18004ea84  cmp     qword ptr [rax+58h], 0
0x18004ea89  jnz     short loc_18004EA80
0x18004ea8b  or      dword ptr [rax+4], 20h
0x18004ea8f  lea     r8, [rbp+57h+var_98]
0x18004ea93  xor     eax, eax
0x18004ea95  mov     [rbp+57h+var_98], 1
0x18004ea99  mov     rdx, r14
0x18004ea9c  mov     [rbp+57h+var_90], rax
0x18004eaa0  mov     rcx, r13
0x18004eaa3  mov     [rbp+57h+var_80], rax
0x18004eaa7  mov     [rbp+57h+var_88], eax
0x18004eaaa  mov     [rbp+57h+var_94], ebx
0x18004eaad  call    sqlite3Select
0x18004eab2  mov     [rbp+57h+arg_8], eax
0x18004eab5  mov     ecx, eax
0x18004eab7  test    eax, eax
0x18004eab9  jnz     loc_18004F602
0x18004eabf  lea     edi, [rbx+1]
0x18004eac2  xor     r9d, r9d
0x18004eac5  mov     r8d, edi
0x18004eac8  mov     [rsp+130h+var_E0], edi
0x18004eacc  mov     edx, 76h ; 'v'
0x18004ead1  mov     rcx, r15
0x18004ead4  call    sqlite3VdbeAddOp2
0x18004ead9  movzx   ecx, byte ptr [rsi]
0x18004eadc  mov     [rsi+18h], eax
0x18004eadf  xor     eax, eax
0x18004eae1  mov     rbx, [rsi+60h]
0x18004eae5  mov     [rsi+50h], rax
0x18004eae9  mov     [rsi+60h], rax
0x18004eaed  mov     [rbp+57h+var_94], edi
0x18004eaf0  call    sqlite3SelectOpName
0x18004eaf5  mov     r9, rax
0x18004eaf8  lea     r8, aSUsingTempBTre; "%s USING TEMP B-TREE"
0x18004eaff  mov     rcx, r13
0x18004eb02  mov     edx, 1
0x18004eb07  call    sqlite3VdbeExplain
0x18004eb0c  lea     r8, [rbp+57h+var_98]
0x18004eb10  mov     rdx, rsi
0x18004eb13  mov     rcx, r13
0x18004eb16  call    sqlite3Select
0x18004eb1b  mov     edi, eax
0x18004eb1d  mov     [rbp+57h+arg_8], eax
0x18004eb20  mov     rax, [rsi+50h]
0x18004eb24  mov     [rbp+57h+var_C8], rax
0x18004eb28  mov     [rsi+50h], r14
0x18004eb2c  movzx   eax, word ptr [r14+2]
0x18004eb31  cmp     [rsi+2], ax
0x18004eb35  jle     short loc_18004EB3B
0x18004eb37  mov     [rsi+2], ax
0x18004eb3b  mov     rdx, [rsi+60h]
0x18004eb3f  test    rdx, rdx
0x18004eb42  jz      short loc_18004EB4D
0x18004eb44  mov     rcx, [rbp+57h+var_D0]
0x18004eb48  call    sqlite3ExprDeleteNN
0x18004eb4d  mov     [rsi+60h], rbx
0x18004eb51  test    edi, edi
0x18004eb53  jnz     loc_18004F457
0x18004eb59  mov     r14d, [r13+44h]
0x18004eb5d  dec     r14d
0x18004eb60  mov     [rsp+130h+var_E4], r14d
0x18004eb65  lea     eax, [r14-1]
0x18004eb69  mov     [r13+44h], eax
0x18004eb6d  cmp     [rsi+8], edi
0x18004eb70  jnz     loc_18004ED92
0x18004eb76  mov     rbx, [rsi+60h]
0x18004eb7a  mov     [rsp+130h+var_D8], rbx
0x18004eb7f  test    rbx, rbx
0x18004eb82  jz      loc_18004ED92
0x18004eb88  inc     dword ptr [r13+38h]
0x18004eb8c  mov     edi, [r13+38h]
0x18004eb90  mov     [rsi+8], edi
0x18004eb93  mov     r14, [r13+10h]
0x18004eb97  mov     [rsp+130h+var_E8], edi
0x18004eb9b  test    r14, r14
0x18004eb9e  jnz     short loc_18004EBC3
0x18004eba0  cmp     [r13+0A8h], r14
0x18004eba7  jnz     short loc_18004EBB8
0x18004eba9  mov     rax, [r13+0]
0x18004ebad  test    byte ptr [rax+60h], 8
0x18004ebb1  jnz     short loc_18004EBB8
0x18004ebb3  mov     byte ptr [r13+23h], 1
0x18004ebb8  mov     rcx, r13
0x18004ebbb  call    sqlite3VdbeCreate
0x18004ebc0  mov     r14, rax
0x18004ebc3  mov     rcx, [rbx+10h]
0x18004ebc7  test    rcx, rcx
0x18004ebca  jz      loc_18004EC7E
0x18004ebd0  test    dword ptr [rcx+4], 800h
0x18004ebd7  jz      short loc_18004EBDF
0x18004ebd9  mov     r8d, [rcx+8]
0x18004ebdd  jmp     short loc_18004EC2C
0x18004ebdf  movzx   edx, byte ptr [rcx]
0x18004ebe2  sub     edx, 0ADh
0x18004ebe8  jz      short loc_18004EC0A
0x18004ebea  cmp     edx, 1
0x18004ebed  jnz     loc_18004EC7E
0x18004ebf3  mov     rcx, [rcx+10h]
0x18004ebf7  lea     rdx, [rbp+57h+arg_18]
0x18004ebfb  call    sqlite3ExprIsInteger
0x18004ec00  test    eax, eax
0x18004ec02  jz      short loc_18004EC7E
0x18004ec04  mov     r8d, [rbp+57h+arg_18]
0x18004ec08  jmp     short loc_18004EC30
0x18004ec0a  mov     rcx, [rcx+10h]
0x18004ec0e  lea     rdx, [rsp+130h+var_EC]
0x18004ec13  mov     [rsp+130h+var_EC], 0
0x18004ec1b  call    sqlite3ExprIsInteger
0x18004ec20  test    eax, eax
0x18004ec22  jz      short loc_18004EC7E
0x18004ec24  mov     r8d, [rsp+130h+var_EC]
0x18004ec29  neg     r8d
0x18004ec2c  mov     [rbp+57h+arg_18], r8d
0x18004ec30  mov     r9d, edi
0x18004ec33  mov     edx, 47h ; 'G'
0x18004ec38  mov     rcx, r14
0x18004ec3b  call    sqlite3VdbeAddOp2
0x18004ec40  movsxd  rax, [rbp+57h+arg_18]
0x18004ec44  test    eax, eax
0x18004ec46  jnz     short loc_18004EC59
0x18004ec48  mov     edx, [rsp+130h+var_E4]
0x18004ec4c  mov     rcx, r14
0x18004ec4f  call    sqlite3VdbeGoto
0x18004ec54  jmp     loc_18004ECF3
0x18004ec59  js      loc_18004ECF3
0x18004ec5f  mov     rcx, rax
  ... truncated ...
```

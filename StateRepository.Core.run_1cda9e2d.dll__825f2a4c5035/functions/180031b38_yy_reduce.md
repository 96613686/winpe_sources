# yy_reduce

- ea: `0x180031b38`
- end: `0x180034654`
- name: `yy_reduce`
- size: `11036`
- prototype: ``
- caller_count: `1`
- callee_count: `106`
- tags: `file_ops, installer_update`

## callers

- `0x180031928`

## callees

- `0x180003128`
- `0x1800055cc`
- `0x18000c850`
- `0x18000c930`
- `0x18000c950`
- `0x18000ca30`
- `0x18000d01c`
- `0x18000d480`
- `0x18000d770`
- `0x18000ded0`
- `0x18000e4d4`
- `0x18000f720`
- `0x18000f820`
- `0x18000fd7c`
- `0x18000fe40`
- `0x180010950`
- `0x180010e90`
- `0x1800110a0`
- `0x1800137fc`
- `0x1800167c0`
- `0x180017fac`
- `0x1800189c8`
- `0x180019e50`
- `0x18001a810`
- `0x180031b38`
- `0x18003465c`
- `0x1800346b0`
- `0x180034704`
- `0x180034adc`
- `0x180034bec`
- `0x180034c48`
- `0x180034dd4`
- `0x180037194`
- `0x18003e04c`
- `0x180045eb8`
- `0x18004a734`
- `0x18004a7e4`
- `0x18004a834`
- `0x18004abd8`
- `0x18004ad04`
- `0x18004b050`
- `0x18004b280`
- `0x18004d044`
- `0x18004ec84`
- `0x180050420`
- `0x180054724`
- `0x180054b80`
- `0x1800551f0`
- `0x1800555e8`
- `0x1800559cc`

## string_xrefs

- `0x180033c36`: `qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers`
- `0x180033c5a`: `the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers`
- `0x180033c45`: `the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers`

## pseudocode

```c
__int64 __fastcall yy_reduce(__int64 *a1, int a2, __int64 a3, __int64 *a4, _QWORD *a5)
{
  __int64 v5; // r13
  int v6; // r8d
  _WORD *v7; // rcx
  __int64 v8; // rax
  __int64 result; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  _BYTE *v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  _QWORD *v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rbx
  _QWORD *v27; // rbx
  __int64 v28; // rax
  __int64 updated; // rax
  int *v30; // rdx
  __int64 appended; // rax
  int v32; // eax
  __int64 v33; // rax
  __int128 v34; // xmm1
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rbx
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // r8
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rbx
  __int64 v45; // rdi
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 inserted; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  int *v51; // rax
  __int64 v52; // rdi
  __int64 v53; // rdx
  __int64 v54; // rbx
  __int64 v55; // r8
  _QWORD *v56; // rcx
  __int64 v57; // rdx
  int v58; // eax
  __int64 v59; // rdx
  int v60; // r12d
  const char *v61; // r9
  int v62; // r8d
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // rbx
  __int64 v68; // r9
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int64 v72; // r8
  int v73; // eax
  __int64 v74; // r8
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rbx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // r8
  _QWORD *v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  _DWORD *v88; // rdx
  int *v89; // rax
  __int64 v90; // rdx
  __int64 v91; // r10
  int *v92; // r8
  __int64 *v93; // rdi
  __int64 v94; // rax
  __int64 v95; // rbx
  __int64 v96; // rax
  __int64 v97; // rbx
  __int64 v98; // r9
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // r8
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // r14
  __int64 v108; // rbx
  __int64 v109; // r9
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // r8
  __int64 v113; // rbx
  __int64 v114; // rbx
  __int64 v115; // rbx
  __int64 v116; // rbx
  __int64 v117; // rax
  int v118; // ebx
  __int64 v119; // r8
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rax
  int v123; // ebx
  __int64 v124; // r8
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // r9
  unsigned __int8 *v130; // rax
  unsigned __int8 v131; // cl
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rdi
  __int64 v136; // rax
  __int64 v137; // rax
  const char *v138; // r8
  __int64 v139; // rax
  __int64 v140; // rsi
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rdx
  __int64 v144; // rax
  __int64 v145; // rsi
  __int64 v146; // rsi
  __int64 v147; // rax
  __int64 v148; // rdi
  __int64 v149; // rax
  __int64 v150; // r8
  __int64 v151; // rax
  __int64 v152; // r8
  int v153; // edi
  void *v154; // rsi
  int v155; // r14d
  _DWORD *v156; // r15
  __int64 v157; // rax
  _QWORD *v158; // rdx
  __int64 v159; // rdx
  int v160; // edx
  int v161; // r9d
  int v162; // r8d
  int v163; // r9d
  int v164; // r8d
  int v165; // edx
  __int64 v166; // rax
  __int64 v167; // r8
  __int64 v168; // rdx
  __int64 v169; // r8
  __int64 v170; // rdx
  __int64 v171; // rax
  __int64 v172; // rdx
  _QWORD *v173; // rbx
  __int64 v174; // r9
  __int64 v175; // r8
  __int64 v176; // rcx
  char v177; // al
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // rax
  __int64 v181; // rax
  __int128 v182; // [rsp+68h] [rbp-31h] BYREF
  __int128 v183; // [rsp+78h] [rbp-21h] BYREF
  char v184; // [rsp+88h] [rbp-11h] BYREF
  __int16 v185; // [rsp+89h] [rbp-10h]
  char v186; // [rsp+8Bh] [rbp-Eh]
  __int128 v187; // [rsp+8Ch] [rbp-Dh]
  int v188; // [rsp+9Ch] [rbp+3h]
  __int128 v189; // [rsp+A0h] [rbp+7h]

  v5 = *a1;
  switch ( a2 )
  {
    case 0:
      if ( !a5[42] )
        *((_BYTE *)a5 + 307) = 1;
      goto LABEL_4;
    case 1:
      if ( !a5[42] )
        *((_BYTE *)a5 + 307) = 2;
      goto LABEL_4;
    case 2:
      sqlite3FinishCoding(a5);
      goto LABEL_4;
    case 3:
      sqlite3BeginTransaction(a5, *(unsigned int *)(v5 - 16));
      goto LABEL_4;
    case 4:
      *(_DWORD *)(v5 + 32) = 7;
      goto LABEL_4;
    case 5:
    case 6:
    case 7:
    case 89:
    case 91:
    case 262:
    case 324:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      goto LABEL_4;
    case 8:
    case 9:
      sqlite3EndTransaction(a5, *(unsigned __int16 *)(v5 - 22));
      goto LABEL_4;
    case 10:
      v59 = 0;
      goto LABEL_108;
    case 11:
      v59 = 1;
      goto LABEL_108;
    case 12:
      v59 = 2;
LABEL_108:
      sqlite3Savepoint(a5, v59, v5 + 8);
      goto LABEL_4;
    case 13:
      sqlite3StartTable(a5, (_OWORD *)(v5 - 16), v5 + 8, *(_DWORD *)(v5 - 88), 0, 0, *(_DWORD *)(v5 - 40));
      goto LABEL_4;
    case 14:
      ++*((_BYTE *)a5 + 36);
      v37 = *a5;
      ++*(_DWORD *)(v37 + 416);
      *(_WORD *)(v37 + 420) = 0;
      goto LABEL_4;
    case 15:
    case 18:
    case 21:
    case 47:
    case 49:
    case 62:
    case 72:
    case 81:
    case 100:
    case 241:
    case 246:
      *(_DWORD *)(v5 + 32) = 0;
      goto LABEL_4;
    case 16:
      *(_DWORD *)(v5 - 40) = 1;
      goto LABEL_4;
    case 17:
      v60 = *(_BYTE *)(*a5 + 197LL) == 0;
      goto LABEL_114;
    case 19:
      sqlite3EndTable((_DWORD)a5, v5 - 40, v5 - 16, *(_DWORD *)(v5 + 8), 0);
      goto LABEL_4;
    case 20:
      v24 = a5;
      sqlite3EndTable((_DWORD)a5, 0, 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_28;
    case 22:
      *(_DWORD *)(v5 - 40) |= *(_DWORD *)(v5 + 8);
      goto LABEL_4;
    case 23:
      if ( *(_DWORD *)(v5 + 16) != 5 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "rowid") )
      {
        v61 = *(const char **)(v5 + 8);
        v62 = *(_DWORD *)(v5 + 16);
        *(_DWORD *)(v5 - 16) = 0;
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", v62, v61);
      }
      else
      {
        *(_DWORD *)(v5 - 16) = 640;
      }
      goto LABEL_4;
    case 24:
      v60 = 0;
      if ( *(_DWORD *)(v5 + 16) != 6 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "strict") )
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", *(_DWORD *)(v5 + 16), *(const char **)(v5 + 8));
      else
        v60 = 0x10000;
      goto LABEL_114;
    case 25:
      v34 = *(_OWORD *)(v5 - 16);
      v182 = *(_OWORD *)(v5 + 8);
      v183 = v34;
      sqlite3AddColumn(a5, &v183, &v182);
      goto LABEL_4;
    case 26:
    case 65:
    case 106:
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_3;
    case 27:
      *(_DWORD *)(v5 - 56) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64);
      goto LABEL_4;
    case 28:
      *(_DWORD *)(v5 - 104) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 112);
      goto LABEL_4;
    case 29:
      *(_DWORD *)(v5 - 8) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 16);
      goto LABEL_4;
    case 30:
      v10 = *a4;
      goto LABEL_6;
    case 31:
      *(_OWORD *)(v5 + 32) = *(_OWORD *)a4;
      goto LABEL_4;
    case 32:
    case 67:
      *((_OWORD *)a5 + 7) = *(_OWORD *)(v5 + 8);
      goto LABEL_4;
    case 33:
      v63 = *(_QWORD *)(v5 - 16);
      v64 = v63 + *(unsigned int *)(v5 - 8);
      goto LABEL_132;
    case 34:
      v64 = *(_QWORD *)(v5 + 8);
      v63 = *(_QWORD *)(v5 - 40) + 1LL;
      v65 = *(_QWORD *)(v5 - 16);
      goto LABEL_134;
    case 35:
      v64 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v63 = *(_QWORD *)(v5 - 40);
LABEL_132:
      v65 = *(_QWORD *)(v5 + 8);
      goto LABEL_134;
    case 36:
      v65 = sqlite3PExpr(a5, 174, *(_QWORD *)(v5 + 8));
      v64 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v63 = *(_QWORD *)(v5 - 40);
      goto LABEL_134;
    case 37:
      v183 = *(_OWORD *)(v5 + 8);
      v66 = tokenExpr(a5, 118, &v183);
      v67 = v66;
      if ( v66 )
        sqlite3ExprIdToTrueFalse(v66);
      v63 = *(_QWORD *)(v5 + 8);
      v65 = v67;
      v64 = v63 + *(unsigned int *)(v5 + 16);
LABEL_134:
      sqlite3AddDefaultValue(a5, v65, v63, v64);
      goto LABEL_4;
    case 38:
      sqlite3AddNotNull(a5, *(unsigned int *)(v5 + 8));
      goto LABEL_4;
    case 39:
      sqlite3AddPrimaryKey((_DWORD)a5, 0, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40));
      goto LABEL_4;
    case 40:
      sqlite3CreateIndex(a5, 0, 0, 0, 0, *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_4;
    case 41:
      v68 = *(_QWORD *)(v5 + 8);
      v69 = *(_QWORD *)(v5 - 40);
      v70 = *(_QWORD *)(v5 - 16);
      goto LABEL_144;
    case 42:
      sqlite3CreateForeignKey((_DWORD)a5, 0, v5 - 40, *(_QWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_4;
    case 43:
      goto LABEL_147;
    case 44:
      sqlite3AddCollateType(a5, v5 + 8);
      goto LABEL_4;
    case 45:
      v71 = *(_QWORD *)(v5 - 16);
      v72 = 0;
      goto LABEL_150;
    case 46:
      v71 = *(_QWORD *)(v5 - 40);
      v72 = v5 + 8;
LABEL_150:
      sqlite3AddGenerated(a5, v71, v72);
      goto LABEL_4;
    case 48:
    case 98:
    case 124:
    case 139:
    case 281:
      *(_DWORD *)(v5 + 8) = 1;
      goto LABEL_4;
    case 50:
      v32 = *(_DWORD *)(v5 + 8) | *(_DWORD *)(v5 - 16) & ~*(_DWORD *)(v5 + 12);
      goto LABEL_49;
    case 51:
      goto LABEL_153;
    case 52:
      *(_QWORD *)(v5 - 40) = 0;
      goto LABEL_4;
    case 53:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 36) = 255;
      goto LABEL_4;
    case 54:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8) << 8;
      *(_DWORD *)(v5 - 36) = 65280;
      goto LABEL_4;
    case 55:
      *(_DWORD *)(v5 - 16) = 8;
      goto LABEL_4;
    case 56:
      *(_DWORD *)(v5 - 16) = 9;
      goto LABEL_4;
    case 57:
      *(_DWORD *)(v5 + 8) = 10;
      goto LABEL_4;
    case 58:
      *(_DWORD *)(v5 + 8) = 7;
      goto LABEL_4;
    case 59:
    case 64:
    case 141:
      *(_DWORD *)(v5 - 16) = 0;
      goto LABEL_4;
    case 60:
      *(_DWORD *)(v5 - 40) = 0;
      goto LABEL_4;
    case 61:
    case 76:
    case 173:
      v32 = *(_DWORD *)(v5 + 8);
      goto LABEL_49;
    case 63:
    case 80:
    case 142:
    case 219:
    case 222:
    case 247:
      *(_DWORD *)(v5 - 16) = 1;
      goto LABEL_4;
    case 66:
      *((_DWORD *)a5 + 30) = 0;
      goto LABEL_4;
    case 68:
      sqlite3AddPrimaryKey((_DWORD)a5, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40), 0);
      goto LABEL_4;
    case 69:
      sqlite3CreateIndex(a5, 0, 0, 0, *(_DWORD **)(v5 - 40), *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_4;
    case 70:
      v68 = *(_QWORD *)(v5 - 16);
      v69 = *(_QWORD *)(v5 - 64);
      v70 = *(_QWORD *)(v5 - 40);
LABEL_144:
      sqlite3AddCheckConstraint(a5, v70, v69, v68);
      goto LABEL_4;
    case 71:
      sqlite3CreateForeignKey((_DWORD)a5, *(_QWORD *)(v5 - 136), v5 - 64, *(_QWORD *)(v5 - 40), *(_DWORD *)(v5 - 16));
LABEL_147:
      sqlite3DeferForeignKey(a5, *(unsigned int *)(v5 + 8));
      goto LABEL_4;
    case 73:
    case 75:
      *(_DWORD *)(v5 + 32) = 11;
      goto LABEL_4;
    case 74:
      v73 = *(_DWORD *)(v5 + 8);
      goto LABEL_167;
    case 77:
      *(_DWORD *)(v5 + 8) = 4;
      goto LABEL_4;
    case 78:
    case 174:
      *(_DWORD *)(v5 + 8) = 5;
      goto LABEL_4;
    case 79:
      v74 = 0;
      goto LABEL_172;
    case 82:
      sqlite3CreateView(
        (_DWORD)a5,
        v5 - 184,
        v5 - 88,
        v5 - 64,
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 160),
        *(_DWORD *)(v5 - 112));
      goto LABEL_4;
    case 83:
      v74 = 1;
LABEL_172:
      sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), v74, *(unsigned int *)(v5 - 16));
      goto LABEL_4;
    case 84:
      v24 = a5;
      v25 = *(_QWORD *)(v5 + 8);
      v184 = 9;
      v185 = 0;
      v186 = 0;
      v187 = 0;
      v188 = 0;
      v189 = 0;
      sqlite3Select(a5, v25, &v184);
LABEL_28:
      sqlite3SelectDelete(*v24, *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 85:
      v23 = attachWithToSelect(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 16));
      goto LABEL_26;
    case 86:
      v75 = attachWithToSelect(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 16));
      goto LABEL_175;
    case 87:
      v16 = *(_QWORD *)(v5 + 8);
      if ( v16 )
        parserDoubleLinkSelect(a5, v16);
      goto LABEL_4;
    case 88:
      v44 = *(_QWORD *)(v5 + 8);
      v45 = *(_QWORD *)(v5 - 40);
      if ( v44
        && (!*(_QWORD *)(v44 + 80)
         || (v57 = *(_QWORD *)(v5 + 8),
             v183 = 0,
             parserDoubleLinkSelect(a5, v57),
             v58 = sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v183, v44, 0),
             (v44 = sqlite3SelectNew((_DWORD)a5, 0, v58, 0, 0, 0, 0, 0, 0)) != 0)) )
      {
        *(_BYTE *)v44 = *(_BYTE *)(v5 - 16);
        *(_QWORD *)(v44 + 80) = v45;
        if ( v45 )
          *(_DWORD *)(v45 + 4) &= ~0x400u;
        *(_DWORD *)(v44 + 4) &= ~0x400u;
        if ( *(_DWORD *)(v5 - 16) != 136 )
          *((_BYTE *)a5 + 34) = 1;
      }
      else
      {
        sqlite3SelectDelete(*a5, v45);
      }
      goto LABEL_68;
    case 90:
      *(_DWORD *)(v5 - 16) = 136;
      goto LABEL_4;
    case 92:
      updated = sqlite3SelectNew(
                  (_DWORD)a5,
                  *(_QWORD *)(v5 - 136),
                  *(_QWORD *)(v5 - 112),
                  *(_QWORD *)(v5 - 88),
                  *(_QWORD *)(v5 - 64),
                  *(_QWORD *)(v5 - 40),
                  *(_QWORD *)(v5 - 16),
                  *(_DWORD *)(v5 - 160),
                  *(_QWORD *)(v5 + 8));
      goto LABEL_35;
    case 93:
      v76 = sqlite3SelectNew(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              *(_QWORD *)(v5 - 136),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 - 88),
              *(_QWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 16),
              *(_DWORD *)(v5 - 184),
              *(_QWORD *)(v5 + 8));
      v77 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 208) = v76;
      if ( v76 )
        *(_QWORD *)(v76 + 120) = v77;
      else
        sqlite3WindowListDelete(*a5, v77);
      goto LABEL_4;
    case 94:
      v75 = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 512, 0);
      goto LABEL_175;
    case 95:
      sqlite3MultiValuesEnd(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 96:
    case 97:
      appended = sqlite3MultiValues(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16));
      goto LABEL_47;
    case 99:
    case 240:
    case 282:
      *(_DWORD *)(v5 + 8) = 2;
      goto LABEL_4;
    case 101:
    case 107:
    case 110:
    case 134:
    case 144:
    case 146:
    case 148:
    case 153:
    case 155:
    case 166:
    case 175:
    case 232:
    case 233:
    case 234:
    case 237:
    case 242:
    case 252:
    case 268:
    case 287:
LABEL_3:
      *(_QWORD *)(v5 + 32) = 0;
      goto LABEL_4;
    case 102:
      v13 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v13;
      if ( *(_DWORD *)(v5 + 16) )
        sqlite3ExprListSetName(a5, v13, v5 + 8, 1);
      sqlite3ExprListSetSpan(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      goto LABEL_4;
    case 103:
      v54 = sqlite3Expr(*a5, 180, 0);
      sqlite3ExprSetErrorOffset(v54, (unsigned int)(*(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86)));
      v55 = v54;
      v56 = a5;
      goto LABEL_92;
    case 104:
      v78 = sqlite3PExpr(a5, 180, 0);
      sqlite3ExprSetErrorOffset(v78, (unsigned int)(*(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86)));
      v183 = *(_OWORD *)(v5 - 40);
      v79 = tokenExpr(a5, 60, &v183);
      v80 = sqlite3PExpr(a5, 142, v79);
      v81 = *(_QWORD *)(v5 - 88);
      v82 = v80;
      v83 = a5;
      goto LABEL_187;
    case 105:
    case 117:
    case 258:
    case 259:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      goto LABEL_4;
    case 108:
      *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      sqlite3SrcListShiftJoinType(a5);
      goto LABEL_4;
    case 109:
      v30 = *(int **)(v5 - 16);
      if ( v30 && *v30 > 0 )
        LOBYTE(v30[20 * *v30 - 12]) = *(_BYTE *)(v5 + 8);
      goto LABEL_4;
    case 111:
      appended = sqlite3SrcListAppendFromTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 64,
                   (int)v5 - 40,
                   v5 - 16,
                   0,
                   v5 + 8);
      goto LABEL_47;
    case 112:
      v85 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 112),
              (int)v5 - 88,
              (int)v5 - 64,
              v5 - 40,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 112) = v85;
      sqlite3SrcListIndexedBy(a5, v85, v5 - 16);
      goto LABEL_4;
    case 113:
      v86 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              (int)v5 - 136,
              (int)v5 - 112,
              v5 - 16,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 160) = v86;
      sqlite3SrcListFuncArgs(a5, v86);
      goto LABEL_4;
    case 114:
      v50 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_84;
    case 115:
      if ( !*(_QWORD *)(v5 - 112) && !*(_DWORD *)(v5 - 8) && !*(_QWORD *)(v5 + 8) && !*(_QWORD *)(v5 + 16) )
      {
        v50 = *(_QWORD *)(v5 - 64);
LABEL_84:
        *(_QWORD *)(v5 - 112) = v50;
        goto LABEL_4;
      }
      v88 = *(_DWORD **)(v5 - 64);
      if ( !v88 || *v88 != 1 )
      {
        sqlite3SrcListShiftJoinType(a5);
        v87 = sqlite3SelectNew((_DWORD)a5, 0, *(_QWORD *)(v5 - 64), 0, 0, 0, 0, 2048, 0);
        v50 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, v87, v5 + 8);
        goto LABEL_84;
      }
      v89 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, 0, v5 + 8);
      *(_QWORD *)(v5 - 112) = v89;
      if ( v89 )
      {
        v90 = *(_QWORD *)(v5 - 64);
        v91 = 10LL * *v89;
        *(_QWORD *)&v89[2 * v91 - 18] = *(_QWORD *)(v90 + 8);
        v92 = &v89[2 * v91];
        if ( (*(_BYTE *)(v90 + 36) & 4) != 0 )
        {
          *(v92 - 11) |= 4u;
          *(_QWORD *)&v89[2 * v91] = *(_QWORD *)(v90 + 80);
          *(_DWORD *)(v90 + 36) &= ~4u;
          *(_QWORD *)(v90 + 80) = 0;
          if ( (*(_DWORD *)(**(_QWORD **)&v89[2 * v91] + 4LL) & 0x800) != 0 )
            *(v92 - 11) |= 0x4000u;
        }
        else
        {
          *(_QWORD *)&v89[2 * v91] = *(_QWORD *)(v90 + 80);
          *(_QWORD *)(v90 + 80) = 0;
        }
        if ( (*(_BYTE *)(v90 + 36) & 8) != 0 )
        {
          *(_QWORD *)&v89[2 * v91 - 6] = *(_QWORD *)(v90 + 56);
          *(_DWORD *)(v90 + 36) &= ~8u;
          *(_QWORD *)(v90 + 56) = 0;
          *(v92 - 11) |= 8u;
        }
        *(_QWORD *)(v90 + 8) = 0;
      }
      sqlite3SrcListDelete(*a5, *(_QWORD *)(v5 - 64));
      goto LABEL_4;
    case 116:
    case 131:
      *(_QWORD *)(v5 + 32) = 0;
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_4;
    case 118:
      v93 = (__int64 *)(v5 + 8);
      v94 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      v95 = v94;
      if ( *((_BYTE *)a5 + 308) >= 2u && v94 )
        sqlite3RenameTokenMap(a5, *(_QWORD *)(v94 + 8), v5 + 8);
      goto LABEL_213;
    case 119:
      v96 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      v44 = v96;
      if ( *((_BYTE *)a5 + 308) >= 2u && v96 )
        sqlite3RenameTokenMap(a5, *(_QWORD *)(v96 + 8), v5 + 8);
LABEL_68:
      *(_QWORD *)(v5 - 40) = v44;
      goto LABEL_4;
    case 120:
      v15 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      goto LABEL_15;
    case 121:
      v23 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      goto LABEL_26;
    case 122:
      v97 = v5 - 88;
      v98 = v5 - 40;
      goto LABEL_220;
    case 123:
      v97 = v5 - 40;
      v98 = 0;
LABEL_220:
      v99 = sqlite3SrcListAppend(a5, 0, v97, v98);
      *(_QWORD *)v97 = v99;
      if ( v99 )
        *(_QWORD *)(*(_QWORD *)v97 + 16LL) = sqlite3NameFromToken(*a5, v5 + 8);
      goto LABEL_4;
    case 125:
      v32 = sqlite3JoinType(a5, v5 - 16, 0, 0);
LABEL_49:
      *(_DWORD *)(v5 - 16) = v32;
      goto LABEL_4;
    case 126:
      v73 = sqlite3JoinType(a5, v5 - 40, v5 - 16, 0);
LABEL_167:
      *(_DWORD *)(v5 - 40) = v73;
      goto LABEL_4;
    case 127:
      *(_DWORD *)(v5 - 64) = sqlite3JoinType(a5, v5 - 64, v5 - 40, v5 - 16);
      goto LABEL_4;
    case 128:
      v33 = *(_QWORD *)(v5 + 8);
      goto LABEL_52;
    case 129:
      v100 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 64) = 0;
      *(_QWORD *)(v5 - 56) = v100;
      goto LABEL_4;
    case 130:
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 0;
      goto LABEL_4;
    case 132:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      goto LABEL_4;
    case 133:
      *(_DWORD *)(v5 - 8) = 1;
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_4;
    case 135:
    case 145:
      goto LABEL_227;
    case 136:
      v35 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v35;
      goto LABEL_55;
    case 137:
      v35 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 40) = v35;
LABEL_55:
      sqlite3ExprListSetSortOrder(v35, *(unsigned int *)(v5 - 16), *(unsigned int *)(v5 + 8));
      goto LABEL_4;
    case 138:
    case 218:
    case 221:
      v60 = 0;
LABEL_114:
      *(_DWORD *)(v5 + 8) = v60;
      goto LABEL_4;
    case 140:
    case 143:
      *(_DWORD *)(v5 + 32) = -1;
      goto LABEL_4;
    case 147:
    case 154:
    case 156:
    case 231:
    case 251:
    case 269:
    case 288:
    case 336:
      goto LABEL_231;
    case 149:
      v102 = 149;
      goto LABEL_233;
    case 150:
      v104 = *(_QWORD *)(v5 - 40);
      goto LABEL_238;
    case 151:
      v104 = *(_QWORD *)(v5 + 8);
LABEL_238:
      v75 = sqlite3PExpr(a5, 149, v104);
      goto LABEL_175;
    case 152:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 40), v5 - 16);
      sqlite3DeleteFrom((_DWORD)a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8), 0, 0);
      goto LABEL_4;
    case 157:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
LABEL_153:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_4;
    case 158:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      v75 = *(_QWORD *)(v5 - 40);
      goto LABEL_175;
    case 159:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 112), v5 - 88);
      sqlite3ExprListCheckLength(a5, *(_QWORD *)(v5 - 40), "set list");
      v51 = *(int **)(v5 - 16);
      if ( v51 )
      {
        if ( *v51 > 1 )
        {
          v182 = 0;
          v105 = sqlite3SelectNew((_DWORD)a5, 0, (_DWORD)v51, 0, 0, 0, 0, 2048, 0);
          DWORD2(v182) = 0;
          *(_QWORD *)&v182 = 0;
          v51 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v182, v105, 0);
        }
        *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendList(a5, *(_QWORD *)(v5 - 112), v51);
      }
      sqlite3Update(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 112),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 136),
        0,
        0,
        0);
      goto LABEL_4;
    case 160:
      v106 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v106;
      sqlite3ExprListSetName(a5, v106, v5 - 40, 1);
      goto LABEL_4;
    case 161:
      *(_QWORD *)(v5 - 136) = sqlite3ExprListAppendVector(
                                a5,
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 162:
      v52 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      sqlite3ExprListSetName(a5, v52, v5 - 40, 1);
      *(_QWORD *)(v5 - 40) = v52;
      goto LABEL_4;
    case 163:
      appended = sqlite3ExprListAppendVector(a5, 0, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
      goto LABEL_47;
    case 164:
      sqlite3Insert(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 - 40),
        *(_DWORD *)(v5 - 112),
        *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 165:
      sqlite3Insert((_DWORD)a5, *(_QWORD *)(v5 - 88), 0, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 - 136), 0);
      goto LABEL_4;
    case 167:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_250;
    case 168:
      *(_QWORD *)(v5 - 256) = sqlite3UpsertNew(
                                *a5,
                                *(_QWORD *)(v5 - 184),
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 40),
                                *(_QWORD *)(v5 - 16),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 169:
      updated = sqlite3UpsertNew(*a5, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 - 64), 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_35;
    case 170:
      appended = sqlite3UpsertNew(*a5, 0, 0, 0, 0, 0);
      goto LABEL_47;
    case 171:
      inserted = sqlite3UpsertNew(*a5, 0, 0, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_77;
    case 172:
LABEL_250:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 176:
    case 179:
    case 238:
    case 243:
      v23 = *(_QWORD *)(v5 - 16);
      goto LABEL_26;
    case 177:
      v23 = sqlite3IdListAppend(a5, *(_QWORD *)(v5 - 40), v5 + 8);
      goto LABEL_26;
    case 178:
      v15 = sqlite3IdListAppend(a5, 0, v5 + 8);
      goto LABEL_15;
    case 180:
      v14 = 60;
      goto LABEL_14;
    case 181:
      v183 = *(_OWORD *)(v5 - 40);
      v26 = tokenExpr(a5, 60, &v183);
      v183 = *(_OWORD *)(v5 + 8);
      tokenExpr(a5, 60, &v183);
      v20 = 142;
      v21 = v26;
      v22 = a5;
      goto LABEL_25;
    case 182:
      v183 = *(_OWORD *)(v5 - 88);
      v107 = tokenExpr(a5, 60, &v183);
      v183 = *(_OWORD *)(v5 - 40);
      v108 = tokenExpr(a5, 60, &v183);
      v183 = *(_OWORD *)(v5 + 8);
      tokenExpr(a5, 60, &v183);
      sqlite3PExpr(a5, 142, v108);
      if ( *((_BYTE *)a5 + 308) >= 2u )
        sqlite3RenameTokenRemap(a5, 0, v107, v109);
      v41 = v107;
      v43 = 142;
      v42 = a5;
      goto LABEL_64;
    case 183:
    case 184:
      v14 = *(unsigned __int16 *)(v5 + 2);
LABEL_14:
      v183 = *(_OWORD *)(v5 + 8);
      v15 = tokenExpr(a5, v14, &v183);
      goto LABEL_15;
    case 185:
      v27 = (_QWORD *)(v5 + 8);
      v28 = sqlite3ExprAlloc(*a5, 156, v5 + 8, 1);
      if ( v28 )
        *(_DWORD *)(v28 + 52) = *(_DWORD *)v27 - *((_DWORD *)a5 + 86);
      goto LABEL_32;
    case 186:
      v17 = *(_BYTE **)(v5 + 8);
      if ( *v17 == 35 && (byte_18009E630[(unsigned __int8)v17[1]] & 4) != 0 )
      {
        v182 = *(_OWORD *)(v5 + 8);
        if ( *((_BYTE *)a5 + 30) )
        {
          v110 = sqlite3PExpr(a5, 176, 0);
          *(_QWORD *)(v5 + 8) = v110;
          if ( v110 )
            sqlite3GetInt32(v182 + 1, v110 + 44);
        }
        else
        {
          sqlite3ErrorMsg(a5, "near \"%T\": syntax error", &v182);
          *(_QWORD *)(v5 + 8) = 0;
        }
      }
      else
      {
        v18 = *(_DWORD *)(v5 + 16);
        v183 = *(_OWORD *)(v5 + 8);
        v19 = tokenExpr(a5, 157, &v183);
        *(_QWORD *)(v5 + 8) = v19;
        sqlite3ExprAssignVarNumber(a5, v19, v18);
      }
      goto LABEL_4;
    case 187:
      v23 = sqlite3ExprAddCollateToken(a5, *(_QWORD *)(v5 - 40), v5 + 8, 1);
      goto LABEL_26;
    case 188:
      v111 = sqlite3ExprAlloc(*a5, 36, v5 - 16, 1);
      v112 = *(_QWORD *)(v5 - 64);
      *(_QWORD *)(v5 - 112) = v111;
      sqlite3ExprAttachSubtrees(*a5, v111, v112, 0);
      goto LABEL_4;
    case 189:
      appended = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 16), v5 - 88, *(unsigned int *)(v5 - 40));
      goto LABEL_47;
    case 190:
      v93 = (__int64 *)(v5 - 160);
      v95 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 88), v5 - 160, *(unsigned int *)(v5 - 112));
      sqlite3ExprAddFunctionOrderBy(a5, v95, *(_QWORD *)(v5 - 16));
LABEL_213:
      *v93 = v95;
      goto LABEL_4;
    case 191:
      v75 = sqlite3ExprFunction(a5, 0, v5 - 64, 0);
      goto LABEL_175;
    case 192:
      v113 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 40), v5 - 112, *(unsigned int *)(v5 - 64));
      sqlite3WindowAttach(a5, v113, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 112) = v113;
      goto LABEL_4;
    case 193:
      v114 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 112), v5 - 184, *(unsigned int *)(v5 - 136));
      sqlite3WindowAttach(a5, v114, *(_QWORD *)(v5 + 8));
      sqlite3ExprAddFunctionOrderBy(a5, v114, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 184) = v114;
      goto LABEL_4;
    case 194:
      v115 = sqlite3ExprFunction(a5, 0, v5 - 88, 0);
      sqlite3WindowAttach(a5, v115, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v115;
      goto LABEL_4;
    case 195:
      v15 = sqlite3ExprFunction(a5, 0, v5 + 8, 0);
      goto LABEL_15;
    case 196:
      v116 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      v117 = sqlite3PExpr(a5, 177, 0);
      *(_QWORD *)(v5 - 88) = v117;
      if ( v117 )
      {
        *(_QWORD *)(v117 + 32) = v116;
        if ( *(_DWORD *)v116 )
          *(_DWORD *)(*(_QWORD *)(v5 - 88) + 4LL) |= *(_DWORD *)(*(_QWORD *)(v116 + 8) + 4LL) & 0x400208;
      }
      else
      {
        sqlite3ExprListDeleteGeneric(*a5, v116);
      }
      goto LABEL_4;
    case 197:
      v23 = sqlite3ExprAnd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_26;
    case 198:
    case 199:
    case 200:
    case 201:
    case 202:
    case 203:
    case 204:
      v20 = *(unsigned __int16 *)(v5 - 22);
      goto LABEL_24;
    case 205:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) |= 0x80000000;
      goto LABEL_4;
    case 206:
      v118 = *(_DWORD *)(v5 - 8);
      v119 = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) = v118 & 0x7FFFFFFF;
      v120 = sqlite3ExprListAppend(a5, 0, v119);
      v121 = sqlite3ExprListAppend(a5, v120, *(_QWORD *)(v5 - 40));
      v122 = sqlite3ExprFunction(a5, v121, v5 - 16, 0);
      *(_QWORD *)(v5 - 40) = v122;
      if ( v118 < 0 )
      {
        v122 = sqlite3PExpr(a5, 19, v122);
        *(_QWORD *)(v5 - 40) = v122;
      }
      goto LABEL_281;
    case 207:
      v123 = *(_DWORD *)(v5 - 56);
      v124 = *(_QWORD *)(v5 - 40);
      *(_DWORD *)(v5 - 56) = v123 & 0x7FFFFFFF;
      v125 = sqlite3ExprListAppend(a5, 0, v124);
      v126 = sqlite3ExprListAppend(a5, v125, *(_QWORD *)(v5 - 88));
      v127 = sqlite3ExprListAppend(a5, v126, *(_QWORD *)(v5 + 8));
      v122 = sqlite3ExprFunction(a5, v127, v5 - 64, 0);
      *(_QWORD *)(v5 - 88) = v122;
      if ( v123 < 0 )
      {
        v122 = sqlite3PExpr(a5, 19, v122);
        *(_QWORD *)(v5 - 88) = v122;
      }
LABEL_281:
      if ( v122 )
        *(_DWORD *)(v122 + 4) |= 0x100u;
      goto LABEL_4;
    case 208:
      v102 = *(unsigned __int16 *)(v5 + 2);
      v103 = *(_QWORD *)(v5 - 16);
      goto LABEL_234;
    case 209:
      v20 = 52;
LABEL_24:
      v21 = *(_QWORD *)(v5 - 40);
      v22 = a5;
LABEL_25:
      v23 = sqlite3PExpr(v22, v20, v21);
      goto LABEL_26;
    case 210:
      v128 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 40) = v128;
      goto LABEL_289;
    case 211:
      v128 = sqlite3PExpr(a5, 46, *(_QWORD *)(v5 - 64));
      *(_QWORD *)(v5 - 64) = v128;
      goto LABEL_291;
    case 212:
      v128 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 112));
      *(_QWORD *)(v5 - 112) = v128;
LABEL_289:
      v129 = 51;
      goto LABEL_292;
    case 213:
      v128 = sqlite3PExpr(a5, 46, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v128;
LABEL_291:
      v129 = 52;
LABEL_292:
      binaryToUnaryIfNull(a5, *(_QWORD *)(v5 + 8), v128, v129);
      goto LABEL_4;
    case 214:
    case 215:
      v102 = *(unsigned __int16 *)(v5 - 22);
LABEL_233:
      v103 = *(_QWORD *)(v5 + 8);
LABEL_234:
      v101 = sqlite3PExpr(a5, v102, v103);
      goto LABEL_235;
    case 216:
      v130 = *(unsigned __int8 **)(v5 + 8);
      v131 = *(_BYTE *)(v5 - 22) + 66;
      if ( v130 && *v130 == 0xAD )
        *v130 = v131;
      else
        v130 = (unsigned __int8 *)sqlite3PExpr(a5, v131, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 16) = v130;
      goto LABEL_4;
    case 217:
      v132 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v133 = sqlite3ExprListAppend(a5, v132, *(_QWORD *)(v5 + 8));
      v23 = sqlite3ExprFunction(a5, v133, v5 - 16, 0);
      goto LABEL_26;
    case 220:
      v38 = a5;
      v134 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v135 = sqlite3ExprListAppend(a5, v134, *(_QWORD *)(v5 + 8));
      v136 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v136;
      if ( v136 )
        *(_QWORD *)(v136 + 32) = v135;
      else
        sqlite3ExprListDeleteGeneric(*a5, v135);
      goto LABEL_62;
    case 223:
      v137 = *(_QWORD *)(v5 - 16);
      if ( !v137 )
      {
        sqlite3ExprUnmapAndDelete(a5, *(_QWORD *)(v5 - 88));
        v138 = "true";
        if ( !*(_DWORD *)(v5 - 64) )
          v138 = "false";
        v139 = sqlite3Expr(*a5, 118, v138);
        *(_QWORD *)(v5 - 88) = v139;
        if ( v139 )
          sqlite3ExprIdToTrueFalse(v139);
        goto LABEL_4;
      }
      v140 = *(_QWORD *)(v137 + 8);
      if ( *(_DWORD *)v137 == 1 )
      {
        if ( (unsigned int)exprIsConst(a5, *(_QWORD *)(v137 + 8), 1) )
        {
          v27 = (_QWORD *)(v5 - 88);
          if ( **(_BYTE **)(v5 - 88) != 0xB1 )
          {
            *(_QWORD *)(*(_QWORD *)(v5 - 16) + 8LL) = 0;
            sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
            sqlite3PExpr(a5, 173, v140);
            *v27 = sqlite3PExpr(a5, 54, *v27);
            goto LABEL_322;
          }
        }
      }
      if ( **(_DWORD **)(v5 - 16) == 1 && *(_BYTE *)v140 == 0x8B )
      {
        v27 = (_QWORD *)(v5 - 88);
        v141 = sqlite3PExpr(a5, 50, *(_QWORD *)(v5 - 88));
        *(_QWORD *)(v5 - 88) = v141;
        sqlite3PExprAddSelect(a5, v141, *(_QWORD *)(v140 + 32));
        *(_QWORD *)(v140 + 32) = 0;
LABEL_316:
        sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
        goto LABEL_322;
      }
      v27 = (_QWORD *)(v5 - 88);
      v142 = sqlite3PExpr(a5, 50, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v142;
      if ( !v142 )
        goto LABEL_316;
      v143 = *(_QWORD *)(v142 + 16);
      if ( *(_BYTE *)v143 == 0xB1 )
      {
        v144 = sqlite3ExprListToValues(a5, **(unsigned int **)(v143 + 32), *(_QWORD *)(v5 - 16));
        v145 = v144;
        if ( v144 )
        {
          parserDoubleLinkSelect(a5, v144);
          sqlite3PExprAddSelect(a5, *v27, v145);
        }
      }
      else
      {
        *(_QWORD *)(v142 + 32) = *(_QWORD *)(v5 - 16);
        sqlite3ExprSetHeightAndFlags(a5, *v27);
      }
LABEL_322:
      if ( *(_DWORD *)(v5 - 64) )
      {
        v28 = sqlite3PExpr(a5, 19, *v27);
LABEL_32:
        *v27 = v28;
      }
LABEL_4:
      v6 = (unsigned __int16)word_1800A7870[a2];
      v7 = (_WORD *)(v5 + 8 * (3LL * byte_1800A70F0[a2] + 3));
      v8 = v6 + word_1800A74B0[*(unsigned __int16 *)(v5 + 24LL * byte_1800A70F0[a2])];
      *a1 = (__int64)v7;
      result = (unsigned __int16)word_1800A7BE0[v8];
      *v7 = result;
      v7[1] = v6;
      return result;
    case 224:
      v36 = sqlite3PExpr(a5, 139, 0);
      *(_QWORD *)(v5 - 40) = v36;
      goto LABEL_58;
    case 225:
      v38 = a5;
      v39 = sqlite3PExpr(a5, 50, *(_QWORD *)(v5 - 88));
      v40 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 88) = v39;
      sqlite3PExprAddSelect(a5, v39, v40);
      goto LABEL_62;
    case 226:
      v38 = a5;
      v146 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 - 16);
      v147 = sqlite3SelectNew((_DWORD)a5, 0, v146, 0, 0, 0, 0, 0, 0);
      v148 = v147;
      if ( *(_QWORD *)(v5 + 8) )
        sqlite3SrcListFuncArgs(a5, v146 & -(__int64)(v147 != 0));
      v149 = sqlite3PExpr(a5, 50, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v149;
      sqlite3PExprAddSelect(a5, v149, v148);
LABEL_62:
      if ( !*(_DWORD *)(v5 - 64) )
        goto LABEL_4;
      v41 = *(_QWORD *)(v5 - 88);
      v42 = v38;
      v43 = 19;
LABEL_64:
      appended = sqlite3PExpr(v42, v43, v41);
      goto LABEL_47;
    case 227:
      v36 = sqlite3PExpr(a5, 20, 0);
      *(_QWORD *)(v5 - 64) = v36;
LABEL_58:
      sqlite3PExprAddSelect(a5, v36, *(_QWORD *)(v5 - 16));
      goto LABEL_4;
    case 228:
      v46 = sqlite3PExpr(a5, 158, *(_QWORD *)(v5 - 64));
      v47 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 88) = v46;
      if ( v46 )
      {
        v150 = *(_QWORD *)(v5 - 16);
        if ( v150 )
          v47 = sqlite3ExprListAppend(a5, v47, v150);
        *(_QWORD *)(*(_QWORD *)(v5 - 88) + 32LL) = v47;
        sqlite3ExprSetHeightAndFlags(a5, *(_QWORD *)(v5 - 88));
      }
      else
      {
        sqlite3ExprListDeleteGeneric(*a5, v47);
        sqlite3ExprDelete(*a5, *(_QWORD *)(v5 - 16));
      }
      goto LABEL_4;
    case 229:
      v84 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      v82 = *(_QWORD *)(v5 + 8);
      v81 = v84;
      v83 = a5;
      *(_QWORD *)(v5 - 88) = v84;
LABEL_187:
      appended = sqlite3ExprListAppend(v83, v81, v82);
      goto LABEL_47;
    case 230:
      v151 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v152 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 64) = v151;
      v75 = sqlite3ExprListAppend(a5, v151, v152);
      goto LABEL_175;
    case 235:
      v55 = *(_QWORD *)(v5 + 8);
      v56 = a5;
LABEL_92:
      v23 = sqlite3ExprListAppend(v56, *(_QWORD *)(v5 - 40), v55);
      goto LABEL_26;
    case 236:
      v15 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_15;
    case 239:
      v153 = *(_DWORD *)(v5 - 184);
      v154 = *(void **)(v5 + 8);
      v155 = *(_DWORD *)(v5 - 232);
      v156 = *(_DWORD **)(v5 - 40);
      v157 = sqlite3SrcListAppend(a5, 0, v5 - 88, 0);
      sqlite3CreateIndex(a5, v5 - 160, v5 - 136, v157, v156, v155, v5 - 256, v154, 0, v153, 0);
      if ( *((_BYTE *)a5 + 308) >= 2u )
      {
        v158 = (_QWORD *)a5[45];
        if ( v158 )
          sqlite3RenameTokenMap(a5, *v158, v5 - 88);
      }
      goto LABEL_4;
    case 244:
      appended = parserAddExprIdListTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 40,
                   *(_DWORD *)(v5 - 16),
                   *(_DWORD *)(v5 + 8));
      goto LABEL_47;
    case 245:
      v23 = parserAddExprIdListTerm((_DWORD)a5, 0, (int)v5 - 40, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_26;
    case 248:
      sqlite3DropIndex(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_4;
    case 249:
      v159 = 0;
      goto LABEL_343;
    case 250:
      v159 = v5 - 16;
LABEL_343:
      sqlite3Vacuum(a5, v159, *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 253:
      v160 = v5 - 16;
      v161 = 0;
      v162 = v5 + 8;
      goto LABEL_346;
    case 254:
      v161 = v5 + 8;
      v162 = v5 - 40;
      v160 = v5 - 64;
      goto LABEL_346;
    case 255:
      v161 = v5 - 16;
      v162 = v5 - 64;
      v160 = v5 - 88;
LABEL_346:
      sqlite3Pragma((_DWORD)a5, v160, v162, v161, 0);
      goto LABEL_4;
    case 256:
      v163 = v5 + 8;
      v164 = v5 - 40;
      v165 = v5 - 64;
      goto LABEL_348;
    case 257:
      v163 = v5 - 16;
      v164 = v5 - 64;
      v165 = v5 - 88;
LABEL_348:
      sqlite3Pragma((_DWORD)a5, v165, v164, v163, 1);
      goto LABEL_4;
    case 260:
      v53 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)&v182 = *(_QWORD *)(v5 - 64);
      *((_QWORD *)&v182 + 1) = (unsigned int)(*(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64));
      sqlite3FinishTrigger(a5, v53, &v182);
      goto LABEL_4;
    case 261:
      sqlite3BeginTrigger(
        a5,
        v5 - 160,
        v5 - 136,
        *(_DWORD *)(v5 - 112),
        *(_DWORD *)(v5 - 88),
        *(_QWORD *)(v5 - 80),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 232),
        *(_DWORD *)(v5 - 184));
      *(_OWORD *)(v5 - 232) = *(_OWORD *)(v5 - ((-(__int64)(*(_DWORD *)(v5 - 128) != 0) & 0xFFFFFFFFFFFFFFE8uLL) + 160));
      goto LABEL_4;
    case 263:
      *(_DWORD *)(v5 - 16) = 66;
      goto LABEL_4;
    case 264:
      *(_DWORD *)(v5 + 32) = 33;
      goto LABEL_4;
    case 265:
    case 266:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 + 16) = 0;
      goto LABEL_4;
    case 267:
      *(_QWORD *)(v5 - 32) = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 40) = 130;
      goto LABEL_4;
    case 270:
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) + 80LL) = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_4;
    case 271:
      *(_QWORD *)(*(_QWORD *)(v5 - 16) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_4;
    case 272:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      sqlite3ErrorMsg(
        a5,
        "qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers");
      goto LABEL_4;
    case 273:
      sqlite3ErrorMsg(a5, "the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_4;
    case 274:
      sqlite3ErrorMsg(a5, "the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_4;
    case 275:
      updated = sqlite3TriggerUpdateStep(
                  (_DWORD)a5,
                  (int)v5 - 136,
                  *(_QWORD *)(v5 - 40),
                  *(_QWORD *)(v5 - 64),
                  *(_QWORD *)(v5 - 16),
                  *(_BYTE *)(v5 - 160),
                  *(_QWORD *)(v5 - 184),
                  *(_QWORD *)(v5 + 8));
LABEL_35:
      *(_QWORD *)(v5 - 184) = updated;
      goto LABEL_4;
    case 276:
      inserted = sqlite3TriggerInsertStep(
                   (_DWORD)a5,
                   (int)v5 - 88,
                   *(_QWORD *)(v5 - 64),
                   *(_QWORD *)(v5 - 40),
                   *(_BYTE *)(v5 - 136),
                   *(_QWORD *)(v5 - 16),
                   *(_QWORD *)(v5 - 160),
                   *(_QWORD *)(v5 + 8));
LABEL_77:
      *(_QWORD *)(v5 - 160) = inserted;
      goto LABEL_4;
    case 277:
      v50 = sqlite3TriggerDeleteStep(
              (_DWORD)a5,
              (int)v5 - 64,
              *(_QWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 + 8));
      goto LABEL_84;
    case 278:
      v23 = sqlite3TriggerSelectStep(*a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_26;
    case 279:
      v166 = sqlite3PExpr(a5, 72, 0);
      *(_QWORD *)(v5 - 64) = v166;
      if ( v166 )
        *(_BYTE *)(v166 + 1) = 4;
      goto LABEL_4;
    case 280:
      v49 = sqlite3PExpr(a5, 72, *(_QWORD *)(v5 - 16));
      *(_QWORD *)(v5 - 112) = v49;
      if ( v49 )
        *(_BYTE *)(v49 + 1) = *(_BYTE *)(v5 - 64);
      goto LABEL_4;
    case 283:
      *(_DWORD *)(v5 + 8) = 3;
      goto LABEL_4;
    case 284:
      sqlite3DropTrigger(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_4;
    case 285:
      codeAttach(
        (_DWORD)a5,
        24,
        (unsigned int)&unk_18009B360,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 286:
      codeAttach((_DWORD)a5, 25, (unsigned int)&unk_18009B3D0, *(_QWORD *)(v5 + 8), 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 289:
      v167 = 0;
      v168 = 0;
      goto LABEL_371;
    case 290:
      v168 = v5 - 16;
      v167 = v5 + 8;
LABEL_371:
      sqlite3Reindex(a5, v168, v167);
      goto LABEL_4;
    case 291:
      v169 = 0;
      v170 = 0;
      goto LABEL_374;
    case 292:
      v170 = v5 - 16;
      v169 = v5 + 8;
LABEL_374:
      sqlite3Analyze(a5, v170, v169);
      goto LABEL_4;
    case 293:
      sqlite3AlterRenameTable(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_4;
    case 294:
      *(_DWORD *)(v5 - 8) = *((_DWORD *)a5 + 72) + *((_DWORD *)a5 + 74) - *(_DWORD *)(v5 - 16);
      sqlite3AlterFinishAddColumn();
      goto LABEL_4;
    case 295:
      sqlite3AlterDropColumn(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_4;
    case 296:
      ++*((_BYTE *)a5 + 36);
      v171 = *a5;
      ++*(_DWORD *)(v171 + 416);
      *(_WORD *)(v171 + 420) = 0;
      sqlite3AlterBeginAddColumn(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_4;
    case 297:
      sqlite3AlterRenameColumn(a5, *(_QWORD *)(v5 - 112), v5 - 40, v5 + 8);
      goto LABEL_4;
    case 298:
      v172 = 0;
      goto LABEL_382;
    case 299:
      v172 = v5 + 8;
LABEL_382:
      sqlite3VtabFinishParse(a5, v172);
      goto LABEL_4;
    case 300:
      sqlite3VtabBeginParse((_DWORD)a5, v5 - 64, v5 - 40, v5 + 8, *(_DWORD *)(v5 - 88));
      goto LABEL_4;
    case 301:
      addArgumentToVtab(a5);
      a5[48] = 0;
      *((_DWORD *)a5 + 98) = 0;
      goto LABEL_4;
    case 302:
    case 303:
    case 304:
      sqlite3VtabArgExtend(a5, v5 + 8);
      goto LABEL_4;
    case 305:
    case 306:
      LOBYTE(a3) = 1;
      sqlite3WithPush(a5, *(_QWORD *)(v5 + 8), a3);
      goto LABEL_4;
    case 307:
      *(_BYTE *)(v5 + 8) = 1;
      goto LABEL_4;
    case 308:
      *(_BYTE *)(v5 - 16) = 0;
      goto LABEL_4;
    case 309:
      *(_BYTE *)(v5 - 40) = 2;
      goto LABEL_4;
    case 310:
      v50 = sqlite3CteNew((_DWORD)a5, (int)v5 - 112, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16), *(_BYTE *)(v5 - 64));
      goto LABEL_84;
    case 311:
      *((_BYTE *)a5 + 39) = 1;
      goto LABEL_4;
    case 312:
      v15 = sqlite3WithAdd(a5, 0, *(_QWORD *)(v5 + 8));
LABEL_15:
      *(_QWORD *)(v5 + 8) = v15;
      goto LABEL_4;
    case 313:
      v23 = sqlite3WithAdd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_26;
    case 314:
      sqlite3WindowChain(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 64LL) = *(_QWORD *)(v5 - 40);
LABEL_227:
      v23 = *(_QWORD *)(v5 + 8);
      goto LABEL_26;
    case 315:
      v173 = *(_QWORD **)(v5 - 16);
      if ( v173 )
        *v173 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 - 88), *(unsigned int *)(v5 - 80));
      goto LABEL_394;
    case 316:
      appended = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_47;
    case 317:
      v174 = *(_QWORD *)(v5 - 16);
      v27 = (_QWORD *)(v5 - 112);
      v175 = *(_QWORD *)(v5 - 40);
      goto LABEL_399;
    case 318:
      v75 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), 0, *(_QWORD *)(v5 - 16), 0);
      goto LABEL_175;
    case 319:
      v174 = *(_QWORD *)(v5 - 16);
      v27 = (_QWORD *)(v5 - 88);
      goto LABEL_398;
    case 320:
      v27 = (_QWORD *)(v5 - 16);
      LODWORD(v174) = 0;
LABEL_398:
      LODWORD(v175) = 0;
LABEL_399:
      v28 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), v175, v174, (__int64)v27);
      goto LABEL_32;
    case 321:
      v10 = sqlite3WindowAlloc((_DWORD)a5, 0, 91, 0, 86, 0, 0);
LABEL_6:
      *(_QWORD *)(v5 + 32) = v10;
      goto LABEL_4;
    case 322:
      v23 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 40),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              86,
              0,
              *(_BYTE *)(v5 + 8));
LABEL_26:
      *(_QWORD *)(v5 - 40) = v23;
      goto LABEL_4;
    case 323:
      v50 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 112),
              *(_DWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 56),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              *(_BYTE *)(v5 + 8));
      goto LABEL_84;
    case 326:
    case 328:
    case 330:
      LODWORD(v182) = *(unsigned __int16 *)(v5 - 22);
      v33 = v182;
LABEL_52:
      *(_QWORD *)(v5 - 16) = v33;
      *(_QWORD *)(v5 - 8) = 0;
      goto LABEL_4;
    case 329:
      v176 = *(_QWORD *)(v5 - 16);
      LODWORD(v182) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 - 16) = v182;
      *(_QWORD *)(v5 - 8) = v176;
      goto LABEL_4;
    case 331:
      *(_BYTE *)(v5 + 32) = 0;
      goto LABEL_4;
    case 332:
      v177 = *(_BYTE *)(v5 + 8);
      goto LABEL_410;
    case 333:
    case 334:
      v177 = *(_BYTE *)(v5 - 22);
LABEL_410:
      *(_BYTE *)(v5 - 16) = v177;
      goto LABEL_4;
    case 335:
      *(_BYTE *)(v5 + 8) = *(_BYTE *)(v5 + 2);
      goto LABEL_4;
    case 337:
      v178 = *(_QWORD *)(v5 + 8);
      v179 = *(_QWORD *)(v5 - 16);
      if ( v178 )
        *(_QWORD *)(v178 + 72) = v179;
      else
        sqlite3ExprDelete(*a5, v179);
LABEL_231:
      v101 = *(_QWORD *)(v5 + 8);
LABEL_235:
      *(_QWORD *)(v5 - 16) = v101;
      goto LABEL_4;
    case 339:
      v180 = sqlite3DbMallocZero(*a5, 144);
      v12 = v180;
      if ( v180 )
      {
        *(_BYTE *)(v180 + 32) = -89;
        *(_QWORD *)(v180 + 72) = *(_QWORD *)(v5 + 8);
      }
      else
      {
        sqlite3ExprDelete(*a5, *(_QWORD *)(v5 + 8));
      }
      goto LABEL_8;
    case 340:
      v75 = *(_QWORD *)(v5 - 16);
LABEL_175:
      *(_QWORD *)(v5 - 64) = v75;
      goto LABEL_4;
    case 341:
      v181 = sqlite3DbMallocZero(*a5, 144);
      *(_QWORD *)(v5 - 16) = v181;
      v27 = (_QWORD *)v181;
      if ( !v181 )
        goto LABEL_4;
      v28 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 + 16));
      goto LABEL_32;
    case 342:
LABEL_394:
      appended = *(_QWORD *)(v5 - 16);
LABEL_47:
      *(_QWORD *)(v5 - 88) = appended;
      goto LABEL_4;
    case 343:
      v11 = *(unsigned __int16 *)(v5 + 2);
      v183 = *(_OWORD *)(v5 + 8);
      v12 = tokenExpr(a5, v11, &v183);
      sqlite3DequoteNumber(a5, v12);
LABEL_8:
      *(_QWORD *)(v5 + 8) = v12;
      goto LABEL_4;
    default:
      goto LABEL_4;
  }
}

```

## disassembly

```asm
0x180031b38  mov     rax, rsp
0x180031b3b  mov     [rax+18h], rbx
0x180031b3f  mov     [rax+10h], edx
0x180031b42  mov     [rax+8], rcx
0x180031b46  push    rbp
0x180031b47  push    rsi
0x180031b48  push    rdi
0x180031b49  push    r12
0x180031b4b  push    r13
0x180031b4d  push    r14
0x180031b4f  push    r15
0x180031b51  lea     rbp, [rax-57h]
0x180031b55  sub     rsp, 0B0h
0x180031b5c  mov     r13, [rcx]
0x180031b5f  lea     r15, cs:180000000h
0x180031b66  cmp     edx, 157h; switch 344 cases
0x180031b6c  ja      short def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031b6e  mov     eax, edx
0x180031b70  mov     r8d, ds:(jpt_180031B7B - 180000000h)[r15+rax*4]
0x180031b78  add     r8, r15
0x180031b7b  jmp     r8; switch jump
0x180031b7e  xor     r12d, r12d; jumptable 0000000180031B7B cases 15,18,21,47,49,62,72,81,100,241,246
0x180031b81  mov     [r13+20h], r12d
0x180031b85  jmp     short def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031b87  xor     r12d, r12d; jumptable 0000000180031B7B cases 101,107,110,134,144,146,148,153,155,166,175,232-234,237,242,252,268,287
0x180031b8a  mov     [r13+20h], r12
0x180031b8e  mov     eax, [rbp+4Fh+arg_8]; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031b91  mov     rbx, [rsp+0E0h+arg_10]
0x180031b99  movzx   r8d, ds:rva word_1800A7870[r15+rax*2]
0x180031ba2  movsx   rax, ds:rva byte_1800A70F0[r15+rax]
0x180031bab  lea     rdx, [rax+rax*2]
0x180031baf  movzx   eax, word ptr [r13+rdx*8+0]
0x180031bb5  lea     rdx, [rdx+3]
0x180031bb9  lea     rcx, ds:0[rdx*8]
0x180031bc1  mov     rdx, [rbp+4Fh+arg_0]
0x180031bc5  movsx   eax, ds:rva word_1800A74B0[r15+rax*2]
0x180031bce  add     eax, r8d
0x180031bd1  add     rcx, r13
0x180031bd4  cdqe
0x180031bd6  mov     [rdx], rcx
0x180031bd9  movzx   eax, ds:rva word_1800A7BE0[r15+rax*2]
0x180031be2  mov     [rcx], ax
0x180031be5  mov     [rcx+2], r8w
0x180031bea  add     rsp, 0B0h
0x180031bf1  pop     r15
0x180031bf3  pop     r14
0x180031bf5  pop     r13
0x180031bf7  pop     r12
0x180031bf9  pop     rdi
0x180031bfa  pop     rsi
0x180031bfb  pop     rbp
0x180031bfc  retn
0x180031bfd  mov     rax, [r9]; jumptable 0000000180031B7B case 30
0x180031c00  mov     [r13+20h], rax
0x180031c04  jmp     short def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031c06  movups  xmm0, xmmword ptr [r13+8]; jumptable 0000000180031B7B case 343
0x180031c0b  movzx   edx, word ptr [r13+2]
0x180031c10  lea     r8, [rbp+4Fh+var_70]
0x180031c14  mov     rcx, [rbp+4Fh+arg_20]
0x180031c18  movdqu  [rbp+4Fh+var_70], xmm0
0x180031c1d  call    tokenExpr
0x180031c22  mov     rcx, [rbp+4Fh+arg_20]
0x180031c26  mov     rdx, rax
0x180031c29  mov     rbx, rax
0x180031c2c  call    sqlite3DequoteNumber
0x180031c31  mov     [r13+8], rbx
0x180031c35  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031c3a  xor     r12d, r12d; jumptable 0000000180031B7B cases 26,65,106
0x180031c3d  mov     [r13+28h], r12d
0x180031c41  jmp     loc_180031B8A
0x180031c46  mov     rbx, [rbp+4Fh+arg_20]; jumptable 0000000180031B7B case 102
0x180031c4a  mov     r8, [r13-28h]
0x180031c4e  mov     rcx, rbx
0x180031c51  mov     rdx, [r13-58h]
0x180031c55  call    sqlite3ExprListAppend
0x180031c5a  xor     r12d, r12d
0x180031c5d  mov     [r13-58h], rax
0x180031c61  cmp     [r13+10h], r12d
0x180031c65  ja      loc_1800321CE
0x180031c6b  mov     r9, [r13-10h]
0x180031c6f  mov     rcx, rbx
0x180031c72  mov     r8, [r13-40h]
0x180031c76  mov     rdx, [r13-58h]
0x180031c7a  call    sqlite3ExprListSetSpan
0x180031c7f  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031c84  mov     edx, 3Ch ; '<'; jumptable 0000000180031B7B case 180
0x180031c89  movups  xmm0, xmmword ptr [r13+8]
0x180031c8e  mov     rcx, [rbp+4Fh+arg_20]
0x180031c92  lea     r8, [rbp+4Fh+var_70]
0x180031c96  movdqu  [rbp+4Fh+var_70], xmm0
0x180031c9b  call    tokenExpr
0x180031ca0  mov     [r13+8], rax
0x180031ca4  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031ca9  mov     rdx, [r13+8]; jumptable 0000000180031B7B case 87
0x180031cad  test    rdx, rdx
0x180031cb0  jz      def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031cb6  mov     rcx, [rbp+4Fh+arg_20]
0x180031cba  call    parserDoubleLinkSelect
0x180031cbf  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031cc4  xor     r12d, r12d; jumptable 0000000180031B7B cases 116,131
0x180031cc7  mov     [r13+20h], r12
0x180031ccb  mov     [r13+28h], r12d
0x180031ccf  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031cd4  mov     rcx, [rbp+4Fh+arg_20]; jumptable 0000000180031B7B case 2
0x180031cd8  call    sqlite3FinishCoding
0x180031cdd  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031ce2  xor     r12d, r12d; jumptable 0000000180031B7B case 130
0x180031ce5  mov     [r13+20h], r12
0x180031ce9  mov     [r13+28h], r12
0x180031ced  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031cf2  mov     rax, [r13+8]; jumptable 0000000180031B7B case 186
0x180031cf6  cmp     byte ptr [rax], 23h ; '#'
0x180031cf9  jz      loc_1800332F1
0x180031cff  movups  xmm0, xmmword ptr [r13+8]
0x180031d04  mov     rcx, [rbp+4Fh+arg_20]
0x180031d08  lea     r8, [rbp+4Fh+var_70]
0x180031d0c  mov     ebx, [r13+10h]
0x180031d10  mov     edx, 9Dh
0x180031d15  movdqu  [rbp+4Fh+var_70], xmm0
0x180031d1a  call    tokenExpr
0x180031d1f  mov     rcx, [rbp+4Fh+arg_20]
0x180031d23  mov     r8d, ebx
0x180031d26  mov     rdx, rax
0x180031d29  mov     [r13+8], rax
0x180031d2d  call    sqlite3ExprAssignVarNumber
0x180031d32  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031d37  movzx   edx, word ptr [r13-16h]; jumptable 0000000180031B7B cases 198-204
0x180031d3c  mov     r9, [r13+8]
0x180031d40  mov     r8, [r13-28h]
0x180031d44  mov     rcx, [rbp+4Fh+arg_20]
0x180031d48  call    sqlite3PExpr
0x180031d4d  mov     [r13-28h], rax
0x180031d51  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031d56  mov     rbx, [rbp+4Fh+arg_20]; jumptable 0000000180031B7B case 84
0x180031d5a  lea     r8, [rbp+4Fh+var_60]
0x180031d5e  mov     rdx, [r13+8]
0x180031d62  xor     eax, eax
0x180031d64  xorps   xmm0, xmm0
0x180031d67  mov     [rbp+4Fh+var_60], 9
0x180031d6b  mov     rcx, rbx
0x180031d6e  mov     [rbp+4Fh+var_5F], ax
0x180031d72  mov     [rbp+4Fh+var_5D], al
0x180031d75  movups  [rbp+4Fh+var_5C], xmm0
0x180031d79  mov     [rbp+4Fh+var_4C], eax
0x180031d7c  movdqu  [rbp+4Fh+var_48], xmm0
0x180031d81  call    sqlite3Select
0x180031d86  mov     rdx, [r13+8]
0x180031d8a  mov     rcx, [rbx]
0x180031d8d  call    sqlite3SelectDelete
0x180031d92  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031d97  movups  xmm0, xmmword ptr [r13-28h]; jumptable 0000000180031B7B case 181
0x180031d9c  mov     rdi, [rbp+4Fh+arg_20]
0x180031da0  lea     r8, [rbp+4Fh+var_70]
0x180031da4  mov     esi, 3Ch ; '<'
0x180031da9  mov     rcx, rdi
0x180031dac  mov     edx, esi
0x180031dae  movdqu  [rbp+4Fh+var_70], xmm0
0x180031db3  call    tokenExpr
0x180031db8  movups  xmm0, xmmword ptr [r13+8]
0x180031dbd  lea     r8, [rbp+4Fh+var_70]
0x180031dc1  mov     edx, esi
0x180031dc3  mov     rcx, rdi
0x180031dc6  mov     rbx, rax
0x180031dc9  movdqu  [rbp+4Fh+var_70], xmm0
0x180031dce  call    tokenExpr
0x180031dd3  mov     r9, rax
0x180031dd6  lea     edx, [rsi+52h]
0x180031dd9  mov     r8, rbx
0x180031ddc  mov     rcx, rdi
0x180031ddf  jmp     loc_180031D48
0x180031de4  mov     rdi, [rbp+4Fh+arg_20]; jumptable 0000000180031B7B case 185
0x180031de8  lea     rbx, [r13+8]
0x180031dec  mov     r9d, 1
0x180031df2  mov     r8, rbx
0x180031df5  mov     edx, 9Ch
0x180031dfa  mov     rcx, [rdi]
0x180031dfd  call    sqlite3ExprAlloc
0x180031e02  test    rax, rax
0x180031e05  jz      short loc_180031E12
0x180031e07  mov     ecx, [rbx]
0x180031e09  sub     ecx, [rdi+158h]
0x180031e0f  mov     [rax+34h], ecx
0x180031e12  mov     [rbx], rax
0x180031e15  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031e1a  mov     rdx, [r13+8]; jumptable 0000000180031B7B case 108
0x180031e1e  mov     rcx, [rbp+4Fh+arg_20]
0x180031e22  mov     [r13-10h], rdx
0x180031e26  call    sqlite3SrcListShiftJoinType
0x180031e2b  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031e30  mov     rax, [r13+8]; jumptable 0000000180031B7B case 92
0x180031e34  mov     r9, [r13-58h]
0x180031e38  mov     r8, [r13-70h]
0x180031e3c  mov     rdx, [r13-88h]
0x180031e43  mov     rcx, [rbp+4Fh+arg_20]
0x180031e47  mov     qword ptr [rsp+0E0h+var_A0], rax
0x180031e4c  mov     eax, [r13-0A0h]
0x180031e53  mov     dword ptr [rsp+0E0h+var_A8], eax
0x180031e57  mov     rax, [r13-10h]
0x180031e5b  mov     [rsp+0E0h+var_B0], rax
0x180031e60  mov     rax, [r13-28h]
0x180031e64  mov     [rsp+0E0h+var_B8], rax
0x180031e69  mov     rax, [r13-40h]
0x180031e6d  mov     [rsp+0E0h+var_C0], rax
0x180031e72  call    sqlite3SelectNew
0x180031e77  mov     [r13-0B8h], rax
0x180031e7e  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031e83  mov     r8, [r13+8]; jumptable 0000000180031B7B case 197
0x180031e87  mov     rdx, [r13-28h]
0x180031e8b  mov     rcx, [rbp+4Fh+arg_20]
0x180031e8f  call    sqlite3ExprAnd
0x180031e94  jmp     loc_180031D4D
0x180031e99  mov     dword ptr [r13+20h], 0Bh; jumptable 0000000180031B7B cases 73,75
0x180031ea1  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031ea6  mov     dword ptr [r13+20h], 0FFFFFFFFh; jumptable 0000000180031B7B cases 140,143
0x180031eae  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031eb3  mov     byte ptr [r13+8], 1; jumptable 0000000180031B7B case 307
0x180031eb8  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031ebd  movups  xmm0, xmmword ptr [r13+8]; jumptable 0000000180031B7B cases 105,117,258,259
0x180031ec2  movdqu  xmmword ptr [r13-10h], xmm0
0x180031ec8  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031ecd  mov     rax, [rbp+4Fh+arg_20]; jumptable 0000000180031B7B case 311
0x180031ed1  mov     byte ptr [rax+27h], 1
0x180031ed5  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031eda  mov     rdx, [r13-28h]; jumptable 0000000180031B7B case 177
0x180031ede  lea     r8, [r13+8]
0x180031ee2  mov     rcx, [rbp+4Fh+arg_20]
0x180031ee6  call    sqlite3IdListAppend
0x180031eeb  jmp     loc_180031D4D
0x180031ef0  mov     rdx, [r13-10h]; jumptable 0000000180031B7B case 109
0x180031ef4  xor     r12d, r12d
0x180031ef7  test    rdx, rdx
0x180031efa  jz      def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031f00  cmp     [rdx], r12d
0x180031f03  jle     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031f09  movsxd  rax, dword ptr [rdx]
0x180031f0c  lea     rcx, [rax+rax*4]
0x180031f10  mov     al, [r13+8]
0x180031f14  add     rcx, rcx
0x180031f17  mov     [rdx+rcx*8-30h], al
0x180031f1b  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031f20  mov     rdx, [r13-58h]; jumptable 0000000180031B7B case 111
0x180031f24  lea     rax, [r13+8]
0x180031f28  mov     [rsp+0E0h+var_B0], rax
0x180031f2d  lea     rcx, [r13-10h]
0x180031f31  xor     r12d, r12d
0x180031f34  lea     r9, [r13-28h]
0x180031f38  mov     [rsp+0E0h+var_B8], r12
0x180031f3d  lea     r8, [r13-40h]
0x180031f41  mov     [rsp+0E0h+var_C0], rcx
0x180031f46  mov     rcx, [rbp+4Fh+arg_20]
0x180031f4a  call    sqlite3SrcListAppendFromTerm
0x180031f4f  mov     [r13-58h], rax
0x180031f53  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031f58  mov     rcx, [rbp+4Fh+arg_20]; jumptable 0000000180031B7B case 125
0x180031f5c  lea     rdx, [r13-10h]
0x180031f60  xor     r9d, r9d
0x180031f63  xor     r8d, r8d
0x180031f66  call    sqlite3JoinType
0x180031f6b  mov     [r13-10h], eax
0x180031f6f  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031f74  mov     dword ptr [r13+8], 1; jumptable 0000000180031B7B cases 48,98,124,139,281
0x180031f7c  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031f81  mov     rax, [r13+8]; jumptable 0000000180031B7B case 128
0x180031f85  xor     r12d, r12d
0x180031f88  mov     [r13-10h], rax
0x180031f8c  mov     [r13-8], r12
0x180031f90  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031f95  movups  xmm0, xmmword ptr [r13+8]; jumptable 0000000180031B7B case 25
0x180031f9a  mov     rcx, [rbp+4Fh+arg_20]
0x180031f9e  lea     r8, [rbp+4Fh+var_80]
0x180031fa2  movups  xmm1, xmmword ptr [r13-10h]
0x180031fa7  lea     rdx, [rbp+4Fh+var_70]
0x180031fab  movdqu  [rbp+4Fh+var_80], xmm0
0x180031fb0  movdqu  [rbp+4Fh+var_70], xmm1
0x180031fb5  call    sqlite3AddColumn
0x180031fba  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031fbf  mov     r8, [r13-28h]; jumptable 0000000180031B7B case 137
0x180031fc3  xor     edx, edx
0x180031fc5  mov     rcx, [rbp+4Fh+arg_20]
0x180031fc9  call    sqlite3ExprListAppend
0x180031fce  mov     [r13-28h], rax
0x180031fd2  mov     r8d, [r13+8]
0x180031fd6  mov     rcx, rax
0x180031fd9  mov     edx, [r13-10h]
0x180031fdd  call    sqlite3ExprListSetSortOrder
0x180031fe2  jmp     def_180031B7B; jumptable 0000000180031B7B default case, cases 325,327,338
0x180031fe7  mov     r8, [r13-28h]; jumptable 0000000180031B7B case 136
0x180031feb  mov     rdx, [r13-58h]
0x180031fef  mov     rcx, [rbp+4Fh+arg_20]
0x180031ff3  call    sqlite3ExprListAppend
0x180031ff8  mov     [r13-58h], rax
0x180031ffc  jmp     short loc_180031FD2
0x180031ffe  mov     rcx, [rbp+4Fh+arg_20]; jumptable 0000000180031B7B case 227
0x180032002  xor     r9d, r9d
0x180032005  xor     r8d, r8d
0x180032008  lea     edx, [r9+14h]
0x18003200c  call    sqlite3PExpr
0x180032011  mov     [r13-40h], rax
0x180032015  mov     r8, [r13-10h]
0x180032019  mov     rdx, rax
  ... truncated ...
```

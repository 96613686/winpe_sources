# yy_reduce

- ea: `0x18000213c`
- end: `0x180004cb8`
- name: `yy_reduce`
- size: `11132`
- prototype: ``
- caller_count: `1`
- callee_count: `107`
- tags: `file_ops, installer_update`

## callers

- `0x180001f54`

## callees

- `0x180001448`
- `0x180001498`
- `0x18000176c`
- `0x180001980`
- `0x180001e0c`
- `0x180001ea0`
- `0x18000213c`
- `0x180004cc0`
- `0x180005650`
- `0x180008c0c`
- `0x18000a754`
- `0x18000a954`
- `0x18000c680`
- `0x180011bcc`
- `0x180014270`
- `0x1800142d0`
- `0x180014d90`
- `0x180015540`
- `0x180015cf0`
- `0x180016140`
- `0x180016440`
- `0x180018be0`
- `0x18001b818`
- `0x18001bb60`
- `0x18001bc40`
- `0x18001bd68`
- `0x18001c528`
- `0x18001d1c8`
- `0x18001ebb8`
- `0x18001f484`
- `0x18001f530`
- `0x18001f8f0`
- `0x18003c6e0`
- `0x18003d110`
- `0x18003d17c`
- `0x18003d380`
- `0x18003d610`
- `0x18003d760`
- `0x18004a49c`
- `0x18004bfc0`
- `0x1800504a8`
- `0x180051740`
- `0x180057dec`
- `0x18005820c`
- `0x180058a38`
- `0x180058b64`
- `0x18005940c`
- `0x1800597b4`
- `0x18005c7cc`
- `0x18005d15c`

## string_xrefs

- `0x1800041f2`: `qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers`
- `0x180004216`: `the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers`
- `0x180004201`: `the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers`

## pseudocode

```c
__int64 __fastcall yy_reduce(__int64 *a1, unsigned int a2, __int64 a3, __int64 *a4, _QWORD *a5)
{
  __int64 v5; // r13
  __int64 v6; // rax
  int v7; // r8d
  _WORD *v8; // rcx
  __int64 v9; // rax
  __int64 result; // rax
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  _BYTE *v16; // rax
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rax
  int v24; // r12d
  __int64 updated; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // r8
  _QWORD *v30; // rcx
  __int64 v31; // rax
  __int64 appended; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  _QWORD *v37; // rcx
  __int64 v38; // rbx
  __int64 v39; // rax
  _QWORD *v40; // rbx
  __int64 v41; // rax
  int *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdi
  __int64 v46; // rcx
  const char *v47; // r9
  int v48; // r8d
  __int128 v49; // xmm1
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rbx
  __int64 v55; // r9
  __int64 v56; // r8
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // r8
  int v60; // eax
  int v61; // eax
  __int64 v62; // r8
  __int64 v63; // rbx
  __int64 v64; // rdi
  __int64 v65; // rdx
  int v66; // eax
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rbx
  __int64 v70; // rbx
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  _QWORD *v75; // rcx
  __int64 v76; // rax
  int *v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  _DWORD *v82; // rdx
  int *v83; // rax
  int *v84; // r8
  __int64 v85; // rdx
  __int64 v86; // r9
  __int64 v87; // rax
  __int64 *v88; // rdi
  __int64 v89; // rax
  __int64 v90; // rbx
  __int64 v91; // rax
  __int64 v92; // rbx
  __int64 v93; // r9
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // r9
  __int64 v98; // r8
  __int64 v99; // rdx
  __int64 v100; // r8
  __int64 i; // rdx
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 j; // rcx
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 inserted; // rax
  __int64 v108; // rbx
  __int64 v109; // r14
  __int64 v110; // rbx
  __int64 v111; // rax
  __int64 v112; // rbx
  __int64 v113; // r9
  __int64 v114; // r8
  __int64 v115; // rdx
  _QWORD *v116; // rcx
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // r8
  __int64 v120; // rbx
  __int64 v121; // rbx
  __int64 v122; // rbx
  int v123; // ebx
  __int64 v124; // r8
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  int v128; // ebx
  __int64 v129; // r8
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // r9
  unsigned __int8 *v135; // rax
  unsigned __int8 v136; // cl
  __int64 v137; // rax
  __int64 v138; // rax
  _QWORD *v139; // rbx
  __int64 v140; // rax
  __int64 v141; // rdi
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  const char *v145; // r8
  __int64 v146; // rax
  __int64 v147; // rsi
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rdx
  __int64 v152; // rax
  __int64 v153; // rsi
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // r8
  __int64 v157; // rsi
  __int64 v158; // rax
  __int64 v159; // rdi
  __int64 v160; // rax
  __int64 v161; // rdx
  __int64 v162; // r8
  __int64 v163; // rax
  __int64 v164; // r8
  int v165; // edi
  void *v166; // rsi
  int v167; // r14d
  int *v168; // r15
  __int64 v169; // rax
  _QWORD *v170; // rdx
  __int64 v171; // rdx
  __int64 v172; // rdx
  __int64 v173; // r9
  __int64 v174; // r8
  __int64 v175; // r9
  __int64 v176; // r8
  __int64 v177; // rdx
  __int64 v178; // rdx
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // r8
  __int64 v182; // rdx
  __int64 v183; // r8
  __int64 v184; // rdx
  __int64 v185; // rax
  __int64 v186; // rdx
  _QWORD *v187; // rbx
  __int64 v188; // r9
  __int64 v189; // r8
  __int64 v190; // rcx
  char v191; // al
  __int64 v192; // rax
  __int64 v193; // rdx
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // [rsp+28h] [rbp-71h]
  __int128 v197; // [rsp+68h] [rbp-31h] BYREF
  __int128 v198; // [rsp+78h] [rbp-21h] BYREF
  char v199; // [rsp+88h] [rbp-11h] BYREF
  __int16 v200; // [rsp+89h] [rbp-10h]
  char v201; // [rsp+8Bh] [rbp-Eh]
  __int128 v202; // [rsp+8Ch] [rbp-Dh]
  int v203; // [rsp+9Ch] [rbp+3h]
  __int128 v204; // [rsp+A0h] [rbp+7h]

  v5 = *a1;
  switch ( a2 )
  {
    case 0u:
      if ( !a5[42] )
        *((_BYTE *)a5 + 307) = 1;
      goto LABEL_5;
    case 1u:
      if ( !a5[42] )
        *((_BYTE *)a5 + 307) = 2;
      goto LABEL_5;
    case 2u:
      sqlite3FinishCoding(a5);
      goto LABEL_5;
    case 3u:
      sqlite3BeginTransaction(a5, *(unsigned int *)(v5 - 16));
      goto LABEL_5;
    case 4u:
      *(_DWORD *)(v5 + 32) = 7;
      goto LABEL_5;
    case 5u:
    case 6u:
    case 7u:
    case 0x59u:
    case 0x5Bu:
    case 0x106u:
    case 0x144u:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      goto LABEL_5;
    case 8u:
    case 9u:
      sqlite3EndTransaction(a5, *(unsigned __int16 *)(v5 - 22));
      goto LABEL_5;
    case 0xAu:
      v20 = 0;
      goto LABEL_22;
    case 0xBu:
      v20 = 1;
      goto LABEL_22;
    case 0xCu:
      v20 = 2;
LABEL_22:
      sqlite3Savepoint(a5, v20, v5 + 8);
      goto LABEL_5;
    case 0xDu:
      sqlite3StartTable(a5, (_OWORD *)(v5 - 16), v5 + 8, *(_DWORD *)(v5 - 88), 0, 0, *(_DWORD *)(v5 - 40));
      goto LABEL_5;
    case 0xEu:
      ++*((_BYTE *)a5 + 36);
      v46 = *a5;
      ++*(_DWORD *)(v46 + 416);
      *(_WORD *)(v46 + 420) = 0;
      goto LABEL_5;
    case 0xFu:
    case 0x12u:
    case 0x15u:
    case 0x2Fu:
    case 0x31u:
    case 0x3Eu:
    case 0x48u:
    case 0x51u:
    case 0x64u:
    case 0xF1u:
    case 0xF6u:
      *(_DWORD *)(v5 + 32) = 0;
      goto LABEL_5;
    case 0x10u:
      *(_DWORD *)(v5 - 40) = 1;
      goto LABEL_5;
    case 0x11u:
      v24 = *(_BYTE *)(*a5 + 197LL) == 0;
      goto LABEL_32;
    case 0x13u:
      sqlite3EndTable((_DWORD)a5, v5 - 40, v5 - 16, *(_DWORD *)(v5 + 8), 0);
      goto LABEL_5;
    case 0x14u:
      v21 = a5;
      sqlite3EndTable((_DWORD)a5, 0, 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_27;
    case 0x16u:
      *(_DWORD *)(v5 - 40) |= *(_DWORD *)(v5 + 8);
      goto LABEL_5;
    case 0x17u:
      if ( *(_DWORD *)(v5 + 16) != 5 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "rowid", 5) )
      {
        v47 = *(const char **)(v5 + 8);
        v48 = *(_DWORD *)(v5 + 16);
        *(_DWORD *)(v5 - 16) = 0;
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", v48, v47);
      }
      else
      {
        *(_DWORD *)(v5 - 16) = 640;
      }
      goto LABEL_5;
    case 0x18u:
      v24 = 0;
      if ( *(_DWORD *)(v5 + 16) != 6 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "strict", 6) )
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", *(_DWORD *)(v5 + 16), *(const char **)(v5 + 8));
      else
        v24 = 0x10000;
      goto LABEL_32;
    case 0x19u:
      v49 = *(_OWORD *)(v5 - 16);
      v197 = *(_OWORD *)(v5 + 8);
      v198 = v49;
      sqlite3AddColumn(a5, &v198, &v197);
      goto LABEL_5;
    case 0x1Au:
    case 0x41u:
    case 0x6Au:
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_4;
    case 0x1Bu:
      *(_DWORD *)(v5 - 56) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64);
      goto LABEL_5;
    case 0x1Cu:
      *(_DWORD *)(v5 - 104) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 112);
      goto LABEL_5;
    case 0x1Du:
      *(_DWORD *)(v5 - 8) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 16);
      goto LABEL_5;
    case 0x1Eu:
      v6 = *a4;
      goto LABEL_3;
    case 0x1Fu:
      *(_OWORD *)(v5 + 32) = *(_OWORD *)a4;
      goto LABEL_5;
    case 0x20u:
    case 0x43u:
      *((_OWORD *)a5 + 7) = *(_OWORD *)(v5 + 8);
      goto LABEL_5;
    case 0x21u:
      v50 = *(_QWORD *)(v5 - 16);
      v51 = v50 + *(unsigned int *)(v5 - 8);
      goto LABEL_101;
    case 0x22u:
      v51 = *(_QWORD *)(v5 + 8);
      v50 = *(_QWORD *)(v5 - 40) + 1LL;
      v52 = *(_QWORD *)(v5 - 16);
      goto LABEL_103;
    case 0x23u:
      v51 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v50 = *(_QWORD *)(v5 - 40);
LABEL_101:
      v52 = *(_QWORD *)(v5 + 8);
      goto LABEL_103;
    case 0x24u:
      v52 = sqlite3PExpr(a5, 174, *(_QWORD *)(v5 + 8), 0);
      v51 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v50 = *(_QWORD *)(v5 - 40);
      goto LABEL_103;
    case 0x25u:
      v198 = *(_OWORD *)(v5 + 8);
      v53 = tokenExpr(a5, 117, &v198);
      v54 = v53;
      if ( v53 )
        sqlite3ExprIdToTrueFalse(v53);
      v50 = *(_QWORD *)(v5 + 8);
      v52 = v54;
      v51 = v50 + *(unsigned int *)(v5 + 16);
LABEL_103:
      sqlite3AddDefaultValue(a5, v52, v50, v51);
      goto LABEL_5;
    case 0x26u:
      sqlite3AddNotNull(a5, *(unsigned int *)(v5 + 8));
      goto LABEL_5;
    case 0x27u:
      sqlite3AddPrimaryKey((_DWORD)a5, 0, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40));
      goto LABEL_5;
    case 0x28u:
      sqlite3CreateIndex(a5, 0, 0, 0, 0, *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_5;
    case 0x29u:
      v55 = *(_QWORD *)(v5 + 8);
      v56 = *(_QWORD *)(v5 - 40);
      v57 = *(_QWORD *)(v5 - 16);
      goto LABEL_114;
    case 0x2Au:
      sqlite3CreateForeignKey((_DWORD)a5, 0, v5 - 40, *(_QWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_5;
    case 0x2Bu:
      goto LABEL_117;
    case 0x2Cu:
      sqlite3AddCollateType(a5, v5 + 8);
      goto LABEL_5;
    case 0x2Du:
      v58 = *(_QWORD *)(v5 - 16);
      v59 = 0;
      goto LABEL_121;
    case 0x2Eu:
      v58 = *(_QWORD *)(v5 - 40);
      v59 = v5 + 8;
LABEL_121:
      sqlite3AddGenerated(a5, v58, v59);
      goto LABEL_5;
    case 0x30u:
    case 0x62u:
    case 0x7Cu:
    case 0x8Bu:
    case 0x119u:
      *(_DWORD *)(v5 + 8) = 1;
      goto LABEL_5;
    case 0x32u:
      v60 = *(_DWORD *)(v5 + 8) | *(_DWORD *)(v5 - 16) & ~*(_DWORD *)(v5 + 12);
      goto LABEL_124;
    case 0x33u:
      goto LABEL_126;
    case 0x34u:
      *(_QWORD *)(v5 - 40) = 0;
      goto LABEL_5;
    case 0x35u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 36) = 255;
      goto LABEL_5;
    case 0x36u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8) << 8;
      *(_DWORD *)(v5 - 36) = 65280;
      goto LABEL_5;
    case 0x37u:
      *(_DWORD *)(v5 - 16) = 8;
      goto LABEL_5;
    case 0x38u:
      *(_DWORD *)(v5 - 16) = 9;
      goto LABEL_5;
    case 0x39u:
      *(_DWORD *)(v5 + 8) = 10;
      goto LABEL_5;
    case 0x3Au:
      *(_DWORD *)(v5 + 8) = 7;
      goto LABEL_5;
    case 0x3Bu:
    case 0x40u:
    case 0x8Du:
      *(_DWORD *)(v5 - 16) = 0;
      goto LABEL_5;
    case 0x3Cu:
      *(_DWORD *)(v5 - 40) = 0;
      goto LABEL_5;
    case 0x3Du:
    case 0x4Cu:
    case 0xADu:
      v60 = *(_DWORD *)(v5 + 8);
      goto LABEL_124;
    case 0x3Fu:
    case 0x50u:
    case 0x8Eu:
    case 0xDBu:
    case 0xDEu:
    case 0xF7u:
      *(_DWORD *)(v5 - 16) = 1;
      goto LABEL_5;
    case 0x42u:
      *((_DWORD *)a5 + 30) = 0;
      goto LABEL_5;
    case 0x44u:
      sqlite3AddPrimaryKey((_DWORD)a5, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40), 0);
      goto LABEL_5;
    case 0x45u:
      sqlite3CreateIndex(a5, 0, 0, 0, *(int **)(v5 - 40), *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_5;
    case 0x46u:
      v55 = *(_QWORD *)(v5 - 16);
      v56 = *(_QWORD *)(v5 - 64);
      v57 = *(_QWORD *)(v5 - 40);
LABEL_114:
      sqlite3AddCheckConstraint(a5, v57, v56, v55);
      goto LABEL_5;
    case 0x47u:
      sqlite3CreateForeignKey((_DWORD)a5, *(_QWORD *)(v5 - 136), v5 - 64, *(_QWORD *)(v5 - 40), *(_DWORD *)(v5 - 16));
LABEL_117:
      sqlite3DeferForeignKey(a5, *(unsigned int *)(v5 + 8));
      goto LABEL_5;
    case 0x49u:
    case 0x4Bu:
      *(_DWORD *)(v5 + 32) = 11;
      goto LABEL_5;
    case 0x4Au:
      v61 = *(_DWORD *)(v5 + 8);
      goto LABEL_140;
    case 0x4Du:
      *(_DWORD *)(v5 + 8) = 4;
      goto LABEL_5;
    case 0x4Eu:
    case 0xAEu:
      *(_DWORD *)(v5 + 8) = 5;
      goto LABEL_5;
    case 0x4Fu:
      v62 = 0;
      goto LABEL_145;
    case 0x52u:
      sqlite3CreateView(
        (_DWORD)a5,
        v5 - 184,
        v5 - 88,
        v5 - 64,
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 160),
        *(_DWORD *)(v5 - 112));
      goto LABEL_5;
    case 0x53u:
      v62 = 1;
LABEL_145:
      sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), v62, *(unsigned int *)(v5 - 16));
      goto LABEL_5;
    case 0x54u:
      v21 = a5;
      v22 = *(_QWORD *)(v5 + 8);
      v199 = 9;
      v200 = 0;
      v201 = 0;
      v202 = 0;
      v203 = 0;
      v204 = 0;
      sqlite3Select(a5, v22, &v199);
LABEL_27:
      sqlite3SelectDelete(*v21, *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0x55u:
      v23 = attachWithToSelect(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 16));
      goto LABEL_30;
    case 0x56u:
      v31 = attachWithToSelect(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 16));
      goto LABEL_44;
    case 0x57u:
      v15 = *(_QWORD *)(v5 + 8);
      if ( v15 )
        parserDoubleLinkSelect(a5, v15);
      goto LABEL_5;
    case 0x58u:
      v63 = *(_QWORD *)(v5 + 8);
      v64 = *(_QWORD *)(v5 - 40);
      if ( v63
        && (!*(_QWORD *)(v63 + 80)
         || (v65 = *(_QWORD *)(v5 + 8),
             v198 = 0,
             parserDoubleLinkSelect(a5, v65),
             v66 = sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v198, v63, 0),
             (v63 = sqlite3SelectNew((_DWORD)a5, 0, v66, 0, 0, 0, 0, 0, 0)) != 0)) )
      {
        *(_BYTE *)v63 = *(_BYTE *)(v5 - 16);
        *(_QWORD *)(v63 + 80) = v64;
        if ( v64 )
          *(_DWORD *)(v64 + 4) &= ~0x400u;
        *(_DWORD *)(v63 + 4) &= ~0x400u;
        if ( *(_DWORD *)(v5 - 16) != 135 )
          *((_BYTE *)a5 + 34) = 1;
      }
      else
      {
        sqlite3SelectDelete(*a5, v64);
      }
      goto LABEL_157;
    case 0x5Au:
      *(_DWORD *)(v5 - 16) = 135;
      goto LABEL_5;
    case 0x5Cu:
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
      goto LABEL_34;
    case 0x5Du:
      v67 = sqlite3SelectNew(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              *(_QWORD *)(v5 - 136),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 - 88),
              *(_QWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 16),
              *(_DWORD *)(v5 - 184),
              *(_QWORD *)(v5 + 8));
      v68 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 208) = v67;
      if ( v67 )
        *(_QWORD *)(v67 + 120) = v68;
      else
        sqlite3WindowListDelete(*a5, v68);
      goto LABEL_5;
    case 0x5Eu:
      v31 = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 512, 0);
      goto LABEL_44;
    case 0x5Fu:
      sqlite3MultiValuesEnd(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0x60u:
    case 0x61u:
      appended = sqlite3MultiValues(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16));
      goto LABEL_46;
    case 0x63u:
    case 0xF0u:
    case 0x11Au:
      *(_DWORD *)(v5 + 8) = 2;
      goto LABEL_5;
    case 0x65u:
    case 0x6Bu:
    case 0x6Eu:
    case 0x86u:
    case 0x90u:
    case 0x92u:
    case 0x94u:
    case 0x99u:
    case 0x9Bu:
    case 0xA6u:
    case 0xAFu:
    case 0xE8u:
    case 0xE9u:
    case 0xEAu:
    case 0xEDu:
    case 0xF2u:
    case 0xFCu:
    case 0x10Cu:
    case 0x11Fu:
LABEL_4:
      *(_QWORD *)(v5 + 32) = 0;
      goto LABEL_5;
    case 0x66u:
      v19 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v19;
      if ( *(_DWORD *)(v5 + 16) )
        sqlite3ExprListSetName(a5, v19, v5 + 8, 1);
      sqlite3ExprListSetSpan(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      goto LABEL_5;
    case 0x67u:
      v69 = sqlite3Expr(*a5, 180, 0);
      sqlite3ExprSetErrorOffset(v69, (unsigned int)(*(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86)));
      v36 = v69;
      v37 = a5;
      goto LABEL_54;
    case 0x68u:
      v70 = sqlite3PExpr(a5, 180, 0, 0);
      sqlite3ExprSetErrorOffset(v70, (unsigned int)(*(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86)));
      v198 = *(_OWORD *)(v5 - 40);
      v71 = tokenExpr(a5, 59, &v198);
      v72 = sqlite3PExpr(a5, 141, v71, v70);
      v73 = *(_QWORD *)(v5 - 88);
      v74 = v72;
      v75 = a5;
      goto LABEL_169;
    case 0x69u:
    case 0x75u:
    case 0x102u:
    case 0x103u:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      goto LABEL_5;
    case 0x6Cu:
      *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      sqlite3SrcListShiftJoinType(a5);
      goto LABEL_5;
    case 0x6Du:
      v77 = *(int **)(v5 - 16);
      if ( v77 && *v77 > 0 )
        LOBYTE(v77[26 * *v77 - 9]) = *(_BYTE *)(v5 + 8);
      goto LABEL_5;
    case 0x6Fu:
      appended = sqlite3SrcListAppendFromTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 64,
                   (int)v5 - 40,
                   v5 - 16,
                   0,
                   v5 + 8);
      goto LABEL_46;
    case 0x70u:
      v78 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 112),
              (int)v5 - 88,
              (int)v5 - 64,
              v5 - 40,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 112) = v78;
      sqlite3SrcListIndexedBy(a5, v78, v5 - 16);
      goto LABEL_5;
    case 0x71u:
      v79 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              (int)v5 - 136,
              (int)v5 - 112,
              v5 - 16,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 160) = v79;
      sqlite3SrcListFuncArgs(a5, v79);
      goto LABEL_5;
    case 0x72u:
      v80 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_180;
    case 0x73u:
      if ( *(_QWORD *)(v5 - 112) || *(_DWORD *)(v5 - 8) || *(_QWORD *)(v5 + 8) || *(_QWORD *)(v5 + 16) )
      {
        v82 = *(_DWORD **)(v5 - 64);
        if ( v82 && *v82 == 1 )
        {
          v83 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, 0, v5 + 8);
          *(_QWORD *)(v5 - 112) = v83;
          v84 = v83;
          if ( v83 )
          {
            v85 = *(_QWORD *)(v5 - 64);
            v86 = 26LL * *v83;
            *(_QWORD *)&v83[v86 - 20] = *(_QWORD *)(v85 + 24);
            *(_QWORD *)&v83[v86 - 22] = *(_QWORD *)(v85 + 16);
            v87 = *(_QWORD *)(v85 + 48);
            *(_QWORD *)&v84[v86 - 14] = v87;
            if ( v87 && (*(_DWORD *)(v87 + 4) & 0x800) != 0 )
              v84[v86 - 8] |= 0x2000u;
            if ( (*(_BYTE *)(v85 + 72) & 4) != 0 )
            {
              *(_QWORD *)&v84[v86 - 2] = *(_QWORD *)(v85 + 96);
              *(_DWORD *)(v85 + 72) &= ~4u;
              *(_QWORD *)(v85 + 96) = 0;
              v84[v86 - 8] |= 4u;
            }
            *(_QWORD *)(v85 + 16) = 0;
            *(_QWORD *)(v85 + 24) = 0;
            *(_QWORD *)(v85 + 48) = 0;
          }
          sqlite3SrcListDelete(*a5, *(_QWORD *)(v5 - 64));
          goto LABEL_5;
        }
        sqlite3SrcListShiftJoinType(a5);
        v81 = sqlite3SelectNew((_DWORD)a5, 0, *(_QWORD *)(v5 - 64), 0, 0, 0, 0, 2048, 0);
        v80 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, v81, v5 + 8);
      }
      else
      {
        v80 = *(_QWORD *)(v5 - 64);
      }
LABEL_180:
      *(_QWORD *)(v5 - 112) = v80;
      goto LABEL_5;
    case 0x74u:
    case 0x83u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_5;
    case 0x76u:
      v88 = (__int64 *)(v5 + 8);
      v89 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      v90 = v89;
      if ( *((_BYTE *)a5 + 308) >= 2u && v89 )
        sqlite3RenameTokenMap(a5, *(_QWORD *)(v89 + 24), v5 + 8);
      goto LABEL_199;
    case 0x77u:
      v91 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      v63 = v91;
      if ( *((_BYTE *)a5 + 308) >= 2u && v91 )
        sqlite3RenameTokenMap(a5, *(_QWORD *)(v91 + 24), v5 + 8);
LABEL_157:
      *(_QWORD *)(v5 - 40) = v63;
      goto LABEL_5;
    case 0x78u:
      v14 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      goto LABEL_11;
    case 0x79u:
      v23 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      goto LABEL_30;
    case 0x7Au:
      v92 = v5 - 88;
      v93 = v5 - 40;
      goto LABEL_206;
    case 0x7Bu:
      v92 = v5 - 40;
      v93 = 0;
LABEL_206:
      v94 = sqlite3SrcListAppend(a5, 0, v92, v93);
      *(_QWORD *)v92 = v94;
      if ( v94 )
        *(_QWORD *)(*(_QWORD *)v92 + 32LL) = sqlite3NameFromToken(*a5, v5 + 8);
      goto LABEL_5;
    case 0x7Du:
      v60 = sqlite3JoinType(a5, v5 - 16, 0, 0);
LABEL_124:
      *(_DWORD *)(v5 - 16) = v60;
      goto LABEL_5;
    case 0x7Eu:
      v61 = sqlite3JoinType(a5, v5 - 40, v5 - 16, 0);
LABEL_140:
      *(_DWORD *)(v5 - 40) = v61;
      goto LABEL_5;
    case 0x7Fu:
      *(_DWORD *)(v5 - 64) = sqlite3JoinType(a5, v5 - 64, v5 - 40, v5 - 16);
      goto LABEL_5;
    case 0x80u:
      v95 = *(_QWORD *)(v5 + 8);
      goto LABEL_211;
    case 0x81u:
      v96 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 64) = 0;
      *(_QWORD *)(v5 - 56) = v96;
      goto LABEL_5;
    case 0x82u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 0;
      goto LABEL_5;
    case 0x84u:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      goto LABEL_5;
    case 0x85u:
      *(_DWORD *)(v5 - 8) = 1;
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_5;
    case 0x87u:
    case 0x91u:
      goto LABEL_216;
    case 0x88u:
      v26 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v26;
      goto LABEL_37;
    case 0x89u:
      v26 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 40) = v26;
LABEL_37:
      sqlite3ExprListSetSortOrder(v26, *(unsigned int *)(v5 - 16), *(unsigned int *)(v5 + 8));
      goto LABEL_5;
    case 0x8Au:
    case 0xDAu:
    case 0xDDu:
      v24 = 0;
LABEL_32:
      *(_DWORD *)(v5 + 8) = v24;
      goto LABEL_5;
    case 0x8Cu:
    case 0x8Fu:
      *(_DWORD *)(v5 + 32) = -1;
      goto LABEL_5;
    case 0x93u:
    case 0x9Au:
    case 0x9Cu:
    case 0xE7u:
    case 0xFBu:
    case 0x10Du:
    case 0x120u:
    case 0x150u:
      goto LABEL_221;
    case 0x95u:
      v33 = 148;
      goto LABEL_49;
    case 0x96u:
      v97 = *(_QWORD *)(v5 + 8);
      v98 = *(_QWORD *)(v5 - 40);
      goto LABEL_224;
    case 0x97u:
      v97 = *(_QWORD *)(v5 - 40);
      v98 = *(_QWORD *)(v5 + 8);
LABEL_224:
      v31 = sqlite3PExpr(a5, 148, v98, v97);
      goto LABEL_44;
    case 0x98u:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 88), v5 - 64);
      v99 = *(_QWORD *)(v5 - 16);
      v100 = *(_QWORD *)(v5 + 8);
      if ( v99 || v100 )
      {
        updateDeleteLimitError(a5, v99, v100);
        for ( i = 0; i != 2; ++i )
        {
          v102 = 3 * i;
          *(_QWORD *)(v5 + 8 * v102 - 16) = 0;
        }
      }
      sqlite3DeleteFrom(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 88),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0x9Du:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
LABEL_126:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_5;
    case 0x9Eu:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      v31 = *(_QWORD *)(v5 - 40);
      goto LABEL_44;
    case 0x9Fu:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 160), v5 - 136);
      v42 = *(int **)(v5 - 64);
      if ( v42 )
      {
        if ( *v42 > 1 )
        {
          v197 = 0;
          v103 = sqlite3SelectNew((_DWORD)a5, 0, (_DWORD)v42, 0, 0, 0, 0, 2048, 0);
          DWORD2(v197) = 0;
          *(_QWORD *)&v197 = 0;
          v42 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v197, v103, 0);
        }
        *(_QWORD *)(v5 - 160) = sqlite3SrcListAppendList(a5, *(_QWORD *)(v5 - 160), v42);
      }
      sqlite3ExprListCheckLength(a5, *(_QWORD *)(v5 - 88), "set list");
      v43 = *(_QWORD *)(v5 - 16);
      v44 = *(_QWORD *)(v5 + 8);
      if ( v43 || v44 )
      {
        updateDeleteLimitError(a5, v43, v44);
        for ( j = 0; j != 2; ++j )
        {
          v105 = 3 * j;
          *(_QWORD *)(v5 + 8 * v105 - 16) = 0;
        }
      }
      LODWORD(v196) = *(_DWORD *)(v5 - 184);
      sqlite3Update(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 160),
        *(_QWORD *)(v5 - 88),
        *(_QWORD *)(v5 - 40),
        v196,
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 + 8),
        0);
      goto LABEL_5;
    case 0xA0u:
      v106 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v106;
      sqlite3ExprListSetName(a5, v106, v5 - 40, 1);
      goto LABEL_5;
    case 0xA1u:
      *(_QWORD *)(v5 - 136) = sqlite3ExprListAppendVector(
                                a5,
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0xA2u:
      v45 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      sqlite3ExprListSetName(a5, v45, v5 - 40, 1);
      *(_QWORD *)(v5 - 40) = v45;
      goto LABEL_5;
    case 0xA3u:
      appended = sqlite3ExprListAppendVector(a5, 0, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
      goto LABEL_46;
    case 0xA4u:
      sqlite3Insert(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 - 40),
        *(_DWORD *)(v5 - 112),
        *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0xA5u:
      sqlite3Insert((_DWORD)a5, *(_QWORD *)(v5 - 88), 0, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 - 136), 0);
      goto LABEL_5;
    case 0xA7u:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_244;
    case 0xA8u:
      *(_QWORD *)(v5 - 256) = sqlite3UpsertNew(
                                *a5,
                                *(_QWORD *)(v5 - 184),
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 40),
                                *(_QWORD *)(v5 - 16),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0xA9u:
      updated = sqlite3UpsertNew(*a5, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 - 64), 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_34;
    case 0xAAu:
      appended = sqlite3UpsertNew(*a5, 0, 0, 0, 0, 0);
      goto LABEL_46;
    case 0xABu:
      inserted = sqlite3UpsertNew(*a5, 0, 0, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_250;
    case 0xACu:
LABEL_244:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0xB0u:
    case 0xB3u:
    case 0xEEu:
    case 0xF3u:
      v23 = *(_QWORD *)(v5 - 16);
      goto LABEL_30;
    case 0xB1u:
      v23 = sqlite3IdListAppend(a5, *(_QWORD *)(v5 - 40), v5 + 8);
      goto LABEL_30;
    case 0xB2u:
      v14 = sqlite3IdListAppend(a5, 0, v5 + 8);
      goto LABEL_11;
    case 0xB4u:
      v13 = 59;
      goto LABEL_10;
    case 0xB5u:
      v198 = *(_OWORD *)(v5 - 40);
      v108 = tokenExpr(a5, 59, &v198);
      v198 = *(_OWORD *)(v5 + 8);
      v28 = tokenExpr(a5, 59, &v198);
      v27 = 141;
      v29 = v108;
      v30 = a5;
      goto LABEL_41;
    case 0xB6u:
      v198 = *(_OWORD *)(v5 - 88);
      v109 = tokenExpr(a5, 59, &v198);
      v198 = *(_OWORD *)(v5 - 40);
      v110 = tokenExpr(a5, 59, &v198);
      v198 = *(_OWORD *)(v5 + 8);
      v111 = tokenExpr(a5, 59, &v198);
      v112 = sqlite3PExpr(a5, 141, v110, v111);
      if ( *((_BYTE *)a5 + 308) >= 2u )
        sqlite3RenameTokenRemap(a5, 0);
      v113 = v112;
      v114 = v109;
      v115 = 141;
      v116 = a5;
      goto LABEL_258;
    case 0xB7u:
    case 0xB8u:
      v13 = *(unsigned __int16 *)(v5 + 2);
LABEL_10:
      v198 = *(_OWORD *)(v5 + 8);
      v14 = tokenExpr(a5, v13, &v198);
      goto LABEL_11;
    case 0xB9u:
      v40 = (_QWORD *)(v5 + 8);
      v41 = sqlite3ExprAlloc(*a5, 155, v5 + 8);
      if ( v41 )
        *(_DWORD *)(v41 + 52) = *(_DWORD *)v40 - *((_DWORD *)a5 + 86);
      goto LABEL_61;
    case 0xBAu:
      v16 = *(_BYTE **)(v5 + 8);
      if ( *v16 == 35 && (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)v16[1]) & 4) != 0 )
      {
        v197 = *(_OWORD *)(v5 + 8);
        if ( *((_BYTE *)a5 + 30) )
        {
          v117 = sqlite3PExpr(a5, 176, 0, 0);
          *(_QWORD *)(v5 + 8) = v117;
          if ( v117 )
            sqlite3GetInt32(v197 + 1, v117 + 44);
        }
        else
        {
          sqlite3ErrorMsg(a5, "near \"%T\": syntax error", &v197);
          *(_QWORD *)(v5 + 8) = 0;
        }
      }
      else
      {
        v17 = *(_DWORD *)(v5 + 16);
        v198 = *(_OWORD *)(v5 + 8);
        v18 = tokenExpr(a5, 156, &v198);
        *(_QWORD *)(v5 + 8) = v18;
        sqlite3ExprAssignVarNumber(a5, v18, v17);
      }
      goto LABEL_5;
    case 0xBBu:
      v23 = sqlite3ExprAddCollateToken(a5, *(_QWORD *)(v5 - 40), v5 + 8, 1);
      goto LABEL_30;
    case 0xBCu:
      v118 = sqlite3ExprAlloc(*a5, 36, v5 - 16);
      v119 = *(_QWORD *)(v5 - 64);
      *(_QWORD *)(v5 - 112) = v118;
      sqlite3ExprAttachSubtrees(*a5, v118, v119, 0);
      goto LABEL_5;
    case 0xBDu:
      appended = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 16), v5 - 88, *(unsigned int *)(v5 - 40));
      goto LABEL_46;
    case 0xBEu:
      v88 = (__int64 *)(v5 - 160);
      v90 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 88), v5 - 160, *(unsigned int *)(v5 - 112));
      sqlite3ExprAddFunctionOrderBy(a5, v90, *(_QWORD *)(v5 - 16));
LABEL_199:
      *v88 = v90;
      goto LABEL_5;
    case 0xBFu:
      v31 = sqlite3ExprFunction(a5, 0, v5 - 64, 0);
      goto LABEL_44;
    case 0xC0u:
      v120 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 40), v5 - 112, *(unsigned int *)(v5 - 64));
      sqlite3WindowAttach(a5, v120, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 112) = v120;
      goto LABEL_5;
    case 0xC1u:
      v121 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 112), v5 - 184, *(unsigned int *)(v5 - 136));
      sqlite3WindowAttach(a5, v121, *(_QWORD *)(v5 + 8));
      sqlite3ExprAddFunctionOrderBy(a5, v121, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 184) = v121;
      goto LABEL_5;
    case 0xC2u:
      v122 = sqlite3ExprFunction(a5, 0, v5 - 88, 0);
      sqlite3WindowAttach(a5, v122, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v122;
      goto LABEL_5;
    case 0xC3u:
      v14 = sqlite3ExprFunction(a5, 0, v5 + 8, 0);
      goto LABEL_11;
    case 0xC4u:
      v38 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      v39 = sqlite3PExpr(a5, 177, 0, 0);
      *(_QWORD *)(v5 - 88) = v39;
      if ( v39 )
      {
        *(_QWORD *)(v39 + 32) = v38;
        if ( *(_DWORD *)v38 )
          *(_DWORD *)(*(_QWORD *)(v5 - 88) + 4LL) |= *(_DWORD *)(*(_QWORD *)(v38 + 8) + 4LL) & 0x400208;
      }
      else
      {
        sqlite3ExprListDeleteGeneric(*a5, v38);
      }
      goto LABEL_5;
    case 0xC5u:
      v23 = sqlite3ExprAnd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_30;
    case 0xC6u:
    case 0xC7u:
    case 0xC8u:
    case 0xC9u:
    case 0xCAu:
    case 0xCBu:
    case 0xCCu:
      v27 = *(unsigned __int16 *)(v5 - 22);
      v28 = *(_QWORD *)(v5 + 8);
      goto LABEL_40;
    case 0xCDu:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) |= 0x80000000;
      goto LABEL_5;
    case 0xCEu:
      v123 = *(_DWORD *)(v5 - 8);
      v124 = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) = v123 & 0x7FFFFFFF;
      v125 = sqlite3ExprListAppend(a5, 0, v124);
      v126 = sqlite3ExprListAppend(a5, v125, *(_QWORD *)(v5 - 40));
      v127 = sqlite3ExprFunction(a5, v126, v5 - 16, 0);
      *(_QWORD *)(v5 - 40) = v127;
      if ( v123 < 0 )
      {
        v127 = sqlite3PExpr(a5, 19, v127, 0);
        *(_QWORD *)(v5 - 40) = v127;
      }
      goto LABEL_275;
    case 0xCFu:
      v128 = *(_DWORD *)(v5 - 56);
      v129 = *(_QWORD *)(v5 - 40);
      *(_DWORD *)(v5 - 56) = v128 & 0x7FFFFFFF;
      v130 = sqlite3ExprListAppend(a5, 0, v129);
      v131 = sqlite3ExprListAppend(a5, v130, *(_QWORD *)(v5 - 88));
      v132 = sqlite3ExprListAppend(a5, v131, *(_QWORD *)(v5 + 8));
      v127 = sqlite3ExprFunction(a5, v132, v5 - 64, 0);
      *(_QWORD *)(v5 - 88) = v127;
      if ( v128 < 0 )
      {
        v127 = sqlite3PExpr(a5, 19, v127, 0);
        *(_QWORD *)(v5 - 88) = v127;
      }
LABEL_275:
      if ( v127 )
        *(_DWORD *)(v127 + 4) |= 0x100u;
      goto LABEL_5;
    case 0xD0u:
      v33 = *(unsigned __int16 *)(v5 + 2);
      v34 = *(_QWORD *)(v5 - 16);
      goto LABEL_50;
    case 0xD1u:
      v28 = 0;
      v27 = 51;
LABEL_40:
      v29 = *(_QWORD *)(v5 - 40);
      v30 = a5;
LABEL_41:
      v23 = sqlite3PExpr(v30, v27, v29, v28);
      goto LABEL_30;
    case 0xD2u:
      v133 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 40) = v133;
      goto LABEL_283;
    case 0xD3u:
      v133 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 64) = v133;
      goto LABEL_285;
    case 0xD4u:
      v133 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 112) = v133;
LABEL_283:
      v134 = 50;
      goto LABEL_286;
    case 0xD5u:
      v133 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v133;
LABEL_285:
      v134 = 51;
LABEL_286:
      binaryToUnaryIfNull(a5, *(_QWORD *)(v5 + 8), v133, v134);
      goto LABEL_5;
    case 0xD6u:
    case 0xD7u:
      v33 = *(unsigned __int16 *)(v5 - 22);
LABEL_49:
      v34 = *(_QWORD *)(v5 + 8);
LABEL_50:
      v35 = sqlite3PExpr(a5, v33, v34, 0);
      goto LABEL_51;
    case 0xD8u:
      v135 = *(unsigned __int8 **)(v5 + 8);
      v136 = *(_BYTE *)(v5 - 22) + 67;
      if ( v135 && *v135 == 0xAD )
        *v135 = v136;
      else
        v135 = (unsigned __int8 *)sqlite3PExpr(a5, v136, *(_QWORD *)(v5 + 8), 0);
      *(_QWORD *)(v5 - 16) = v135;
      goto LABEL_5;
    case 0xD9u:
      v137 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v138 = sqlite3ExprListAppend(a5, v137, *(_QWORD *)(v5 + 8));
      v23 = sqlite3ExprFunction(a5, v138, v5 - 16, 0);
      goto LABEL_30;
    case 0xDCu:
      v139 = a5;
      v140 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v141 = sqlite3ExprListAppend(a5, v140, *(_QWORD *)(v5 + 8));
      v142 = sqlite3PExpr(a5, 48, *(_QWORD *)(v5 - 88), 0);
      *(_QWORD *)(v5 - 88) = v142;
      if ( v142 )
        *(_QWORD *)(v142 + 32) = v141;
      else
        sqlite3ExprListDeleteGeneric(*a5, v141);
      goto LABEL_299;
    case 0xDFu:
      v144 = *(_QWORD *)(v5 - 16);
      if ( !v144 )
      {
        sqlite3ExprUnmapAndDelete(a5, *(_QWORD *)(v5 - 88));
        v145 = "true";
        if ( !*(_DWORD *)(v5 - 64) )
          v145 = "false";
        v146 = sqlite3Expr(*a5, 117, v145);
        *(_QWORD *)(v5 - 88) = v146;
        if ( v146 )
          sqlite3ExprIdToTrueFalse(v146);
        goto LABEL_5;
      }
      v147 = *(_QWORD *)(v144 + 8);
      if ( *(_DWORD *)v144 == 1 )
      {
        if ( (unsigned int)exprIsConst(a5, *(_QWORD *)(v144 + 8), 1) )
        {
          v40 = (_QWORD *)(v5 - 88);
          if ( **(_BYTE **)(v5 - 88) != 0xB1 )
          {
            *(_QWORD *)(*(_QWORD *)(v5 - 16) + 8LL) = 0;
            sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
            v148 = sqlite3PExpr(a5, 173, v147, 0);
            *v40 = sqlite3PExpr(a5, 53, *v40, v148);
            goto LABEL_319;
          }
        }
      }
      if ( **(_DWORD **)(v5 - 16) == 1 && *(_BYTE *)v147 == 0x8A )
      {
        v40 = (_QWORD *)(v5 - 88);
        v149 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
        *(_QWORD *)(v5 - 88) = v149;
        sqlite3PExprAddSelect(a5, v149, *(_QWORD *)(v147 + 32));
        *(_QWORD *)(v147 + 32) = 0;
LABEL_313:
        sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
        goto LABEL_319;
      }
      v40 = (_QWORD *)(v5 - 88);
      v150 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
      *(_QWORD *)(v5 - 88) = v150;
      if ( !v150 )
        goto LABEL_313;
      v151 = *(_QWORD *)(v150 + 16);
      if ( *(_BYTE *)v151 == 0xB1 )
      {
        v152 = sqlite3ExprListToValues(a5, **(unsigned int **)(v151 + 32), *(_QWORD *)(v5 - 16));
        v153 = v152;
        if ( v152 )
        {
          parserDoubleLinkSelect(a5, v152);
          sqlite3PExprAddSelect(a5, *v40, v153);
        }
      }
      else
      {
        *(_QWORD *)(v150 + 32) = *(_QWORD *)(v5 - 16);
        sqlite3ExprSetHeightAndFlags(a5, *v40);
      }
LABEL_319:
      if ( *(_DWORD *)(v5 - 64) )
      {
        v41 = sqlite3PExpr(a5, 19, *v40, 0);
LABEL_61:
        *v40 = v41;
      }
LABEL_5:
      v7 = (unsigned __int16)word_1800BE480[a2];
      v8 = (_WORD *)(v5 + 8 * (3LL * *((char *)qword_1800B4CA0 + a2) + 3));
      v9 = v7 + word_1800BE0D0[*(unsigned __int16 *)(v5 + 24LL * *((char *)qword_1800B4CA0 + a2))];
      *a1 = (__int64)v8;
      result = (unsigned __int16)word_1800BE800[v9];
      *v8 = result;
      v8[1] = v7;
      return result;
    case 0xE0u:
      v154 = sqlite3PExpr(a5, 138, 0, 0);
      *(_QWORD *)(v5 - 40) = v154;
      goto LABEL_323;
    case 0xE1u:
      v139 = a5;
      v155 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
      v156 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 88) = v155;
      sqlite3PExprAddSelect(a5, v155, v156);
      goto LABEL_299;
    case 0xE2u:
      v139 = a5;
      v157 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 - 16);
      v158 = sqlite3SelectNew((_DWORD)a5, 0, v157, 0, 0, 0, 0, 0, 0);
      v159 = v158;
      if ( *(_QWORD *)(v5 + 8) )
        sqlite3SrcListFuncArgs(a5, v157 & -(__int64)(v158 != 0));
      v143 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
      *(_QWORD *)(v5 - 88) = v143;
      sqlite3PExprAddSelect(a5, v143, v159);
LABEL_299:
      if ( !*(_DWORD *)(v5 - 64) )
        goto LABEL_5;
      v114 = *(_QWORD *)(v5 - 88);
      v113 = 0;
      v116 = v139;
      v115 = 19;
LABEL_258:
      appended = sqlite3PExpr(v116, v115, v114, v113);
      goto LABEL_46;
    case 0xE3u:
      v154 = sqlite3PExpr(a5, 20, 0, 0);
      *(_QWORD *)(v5 - 64) = v154;
LABEL_323:
      sqlite3PExprAddSelect(a5, v154, *(_QWORD *)(v5 - 16));
      goto LABEL_5;
    case 0xE4u:
      v160 = sqlite3PExpr(a5, 157, *(_QWORD *)(v5 - 64), 0);
      v161 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 88) = v160;
      if ( v160 )
      {
        v162 = *(_QWORD *)(v5 - 16);
        if ( v162 )
          v161 = sqlite3ExprListAppend(a5, v161, v162);
        *(_QWORD *)(*(_QWORD *)(v5 - 88) + 32LL) = v161;
        sqlite3ExprSetHeightAndFlags(a5, *(_QWORD *)(v5 - 88));
      }
      else
      {
        sqlite3ExprListDeleteGeneric(*a5, v161);
        sqlite3ExprDelete(*a5, *(_QWORD *)(v5 - 16));
      }
      goto LABEL_5;
    case 0xE5u:
      v76 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      v74 = *(_QWORD *)(v5 + 8);
      v73 = v76;
      v75 = a5;
      *(_QWORD *)(v5 - 88) = v76;
LABEL_169:
      appended = sqlite3ExprListAppend(v75, v73, v74);
      goto LABEL_46;
    case 0xE6u:
      v163 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v164 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 64) = v163;
      v31 = sqlite3ExprListAppend(a5, v163, v164);
      goto LABEL_44;
    case 0xEBu:
      v36 = *(_QWORD *)(v5 + 8);
      v37 = a5;
LABEL_54:
      v23 = sqlite3ExprListAppend(v37, *(_QWORD *)(v5 - 40), v36);
      goto LABEL_30;
    case 0xECu:
      v14 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_11;
    case 0xEFu:
      v165 = *(_DWORD *)(v5 - 184);
      v166 = *(void **)(v5 + 8);
      v167 = *(_DWORD *)(v5 - 232);
      v168 = *(int **)(v5 - 40);
      v169 = sqlite3SrcListAppend(a5, 0, v5 - 88, 0);
      sqlite3CreateIndex(a5, v5 - 160, v5 - 136, v169, v168, v167, v5 - 256, v166, 0, v165, 0);
      if ( *((_BYTE *)a5 + 308) >= 2u )
      {
        v170 = (_QWORD *)a5[45];
        if ( v170 )
          sqlite3RenameTokenMap(a5, *v170, v5 - 88);
      }
      goto LABEL_5;
    case 0xF4u:
      appended = parserAddExprIdListTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 40,
                   *(_DWORD *)(v5 - 16),
                   *(_DWORD *)(v5 + 8));
      goto LABEL_46;
    case 0xF5u:
      v23 = parserAddExprIdListTerm((_DWORD)a5, 0, (int)v5 - 40, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_30;
    case 0xF8u:
      sqlite3DropIndex(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_5;
    case 0xF9u:
      v171 = 0;
      goto LABEL_342;
    case 0xFAu:
      v171 = v5 - 16;
LABEL_342:
      sqlite3Vacuum(a5, v171, *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0xFDu:
      v172 = v5 - 16;
      v173 = 0;
      v174 = v5 + 8;
      goto LABEL_345;
    case 0xFEu:
      v173 = v5 + 8;
      v174 = v5 - 40;
      v172 = v5 - 64;
      goto LABEL_345;
    case 0xFFu:
      v173 = v5 - 16;
      v174 = v5 - 64;
      v172 = v5 - 88;
LABEL_345:
      sqlite3Pragma(a5, v172, v174, v173, 0);
      goto LABEL_5;
    case 0x100u:
      v175 = v5 + 8;
      v176 = v5 - 40;
      v177 = v5 - 64;
      goto LABEL_347;
    case 0x101u:
      v175 = v5 - 16;
      v176 = v5 - 64;
      v177 = v5 - 88;
LABEL_347:
      sqlite3Pragma(a5, v177, v176, v175, 1);
      goto LABEL_5;
    case 0x104u:
      v178 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)&v197 = *(_QWORD *)(v5 - 64);
      *((_QWORD *)&v197 + 1) = (unsigned int)(*(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64));
      sqlite3FinishTrigger(a5, v178, &v197);
      goto LABEL_5;
    case 0x105u:
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
      goto LABEL_5;
    case 0x107u:
      *(_DWORD *)(v5 - 16) = 65;
      goto LABEL_5;
    case 0x108u:
      *(_DWORD *)(v5 + 32) = 33;
      goto LABEL_5;
    case 0x109u:
    case 0x10Au:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 + 16) = 0;
      goto LABEL_5;
    case 0x10Bu:
      *(_QWORD *)(v5 - 32) = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 40) = 129;
      goto LABEL_5;
    case 0x10Eu:
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) + 80LL) = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_5;
    case 0x10Fu:
      *(_QWORD *)(*(_QWORD *)(v5 - 16) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_5;
    case 0x110u:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      sqlite3ErrorMsg(
        a5,
        "qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers");
      goto LABEL_5;
    case 0x111u:
      sqlite3ErrorMsg(a5, "the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_5;
    case 0x112u:
      sqlite3ErrorMsg(a5, "the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_5;
    case 0x113u:
      updated = sqlite3TriggerUpdateStep(
                  (_DWORD)a5,
                  (int)v5 - 136,
                  *(_QWORD *)(v5 - 40),
                  *(_QWORD *)(v5 - 64),
                  *(_QWORD *)(v5 - 16),
                  *(_BYTE *)(v5 - 160),
                  *(_QWORD *)(v5 - 184),
                  *(_QWORD *)(v5 + 8));
LABEL_34:
      *(_QWORD *)(v5 - 184) = updated;
      goto LABEL_5;
    case 0x114u:
      inserted = sqlite3TriggerInsertStep(
                   (_DWORD)a5,
                   (int)v5 - 88,
                   *(_QWORD *)(v5 - 64),
                   *(_QWORD *)(v5 - 40),
                   *(_BYTE *)(v5 - 136),
                   *(_QWORD *)(v5 - 16),
                   *(_QWORD *)(v5 - 160),
                   *(_QWORD *)(v5 + 8));
LABEL_250:
      *(_QWORD *)(v5 - 160) = inserted;
      goto LABEL_5;
    case 0x115u:
      v80 = sqlite3TriggerDeleteStep(
              (_DWORD)a5,
              (int)v5 - 64,
              *(_QWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 + 8));
      goto LABEL_180;
    case 0x116u:
      v23 = sqlite3TriggerSelectStep(*a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_30;
    case 0x117u:
      v179 = sqlite3PExpr(a5, 71, 0, 0);
      *(_QWORD *)(v5 - 64) = v179;
      if ( v179 )
        *(_BYTE *)(v179 + 1) = 4;
      goto LABEL_5;
    case 0x118u:
      v180 = sqlite3ExprAlloc(*a5, 71, v5 - 16);
      *(_QWORD *)(v5 - 112) = v180;
      if ( v180 )
        *(_BYTE *)(v180 + 1) = *(_BYTE *)(v5 - 64);
      goto LABEL_5;
    case 0x11Bu:
      *(_DWORD *)(v5 + 8) = 3;
      goto LABEL_5;
    case 0x11Cu:
      sqlite3DropTrigger(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_5;
    case 0x11Du:
      codeAttach(
        (_DWORD)a5,
        24,
        (unsigned int)qword_1800B1980,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0x11Eu:
      codeAttach((_DWORD)a5, 25, (unsigned int)qword_1800B19D0, *(_QWORD *)(v5 + 8), 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0x121u:
      v181 = 0;
      v182 = 0;
      goto LABEL_376;
    case 0x122u:
      v182 = v5 - 16;
      v181 = v5 + 8;
LABEL_376:
      sqlite3Reindex(a5, v182, v181);
      goto LABEL_5;
    case 0x123u:
      v183 = 0;
      v184 = 0;
      goto LABEL_379;
    case 0x124u:
      v184 = v5 - 16;
      v183 = v5 + 8;
LABEL_379:
      sqlite3Analyze(a5, v184, v183);
      goto LABEL_5;
    case 0x125u:
      sqlite3AlterRenameTable(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_5;
    case 0x126u:
      *(_DWORD *)(v5 - 8) = *((_DWORD *)a5 + 72) + *((_DWORD *)a5 + 74) - *(_DWORD *)(v5 - 16);
      sqlite3AlterFinishAddColumn();
      goto LABEL_5;
    case 0x127u:
      sqlite3AlterDropColumn(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_5;
    case 0x128u:
      ++*((_BYTE *)a5 + 36);
      v185 = *a5;
      ++*(_DWORD *)(v185 + 416);
      *(_WORD *)(v185 + 420) = 0;
      sqlite3AlterBeginAddColumn(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_5;
    case 0x129u:
      sqlite3AlterRenameColumn(a5, *(_QWORD *)(v5 - 112), v5 - 40, v5 + 8);
      goto LABEL_5;
    case 0x12Au:
      v186 = 0;
      goto LABEL_387;
    case 0x12Bu:
      v186 = v5 + 8;
LABEL_387:
      sqlite3VtabFinishParse(a5, v186);
      goto LABEL_5;
    case 0x12Cu:
      sqlite3VtabBeginParse((_DWORD)a5, v5 - 64, v5 - 40, v5 + 8, *(_DWORD *)(v5 - 88));
      goto LABEL_5;
    case 0x12Du:
      addArgumentToVtab(a5);
      a5[48] = 0;
      *((_DWORD *)a5 + 98) = 0;
      goto LABEL_5;
    case 0x12Eu:
    case 0x12Fu:
    case 0x130u:
      sqlite3VtabArgExtend(a5, v5 + 8);
      goto LABEL_5;
    case 0x131u:
    case 0x132u:
      LOBYTE(a3) = 1;
      sqlite3WithPush(a5, *(_QWORD *)(v5 + 8), a3);
      goto LABEL_5;
    case 0x133u:
      *(_BYTE *)(v5 + 8) = 1;
      goto LABEL_5;
    case 0x134u:
      *(_BYTE *)(v5 - 16) = 0;
      goto LABEL_5;
    case 0x135u:
      *(_BYTE *)(v5 - 40) = 2;
      goto LABEL_5;
    case 0x136u:
      v80 = sqlite3CteNew((_DWORD)a5, (int)v5 - 112, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16), *(_BYTE *)(v5 - 64));
      goto LABEL_180;
    case 0x137u:
      *((_BYTE *)a5 + 39) = 1;
      goto LABEL_5;
    case 0x138u:
      v14 = sqlite3WithAdd(a5, 0, *(_QWORD *)(v5 + 8));
LABEL_11:
      *(_QWORD *)(v5 + 8) = v14;
      goto LABEL_5;
    case 0x139u:
      v23 = sqlite3WithAdd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_30;
    case 0x13Au:
      sqlite3WindowChain(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 64LL) = *(_QWORD *)(v5 - 40);
LABEL_216:
      v23 = *(_QWORD *)(v5 + 8);
      goto LABEL_30;
    case 0x13Bu:
      v187 = *(_QWORD **)(v5 - 16);
      if ( v187 )
        *v187 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 - 88), *(unsigned int *)(v5 - 80));
      goto LABEL_401;
    case 0x13Cu:
      appended = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_46;
    case 0x13Du:
      v188 = *(_QWORD *)(v5 - 16);
      v40 = (_QWORD *)(v5 - 112);
      v189 = *(_QWORD *)(v5 - 40);
      goto LABEL_406;
    case 0x13Eu:
      v31 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), 0, *(_QWORD *)(v5 - 16), 0);
      goto LABEL_44;
    case 0x13Fu:
      v188 = *(_QWORD *)(v5 - 16);
      v40 = (_QWORD *)(v5 - 88);
      goto LABEL_405;
    case 0x140u:
      v40 = (_QWORD *)(v5 - 16);
      LODWORD(v188) = 0;
LABEL_405:
      LODWORD(v189) = 0;
LABEL_406:
      v41 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), v189, v188, (__int64)v40);
      goto LABEL_61;
    case 0x141u:
      v6 = sqlite3WindowAlloc((_DWORD)a5, 0, 90, 0, 85, 0, 0);
LABEL_3:
      *(_QWORD *)(v5 + 32) = v6;
      goto LABEL_5;
    case 0x142u:
      v23 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 40),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              85,
              0,
              *(_BYTE *)(v5 + 8));
LABEL_30:
      *(_QWORD *)(v5 - 40) = v23;
      goto LABEL_5;
    case 0x143u:
      v80 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 112),
              *(_DWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 56),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              *(_BYTE *)(v5 + 8));
      goto LABEL_180;
    case 0x146u:
    case 0x148u:
    case 0x14Au:
      LODWORD(v197) = *(unsigned __int16 *)(v5 - 22);
      v95 = v197;
LABEL_211:
      *(_QWORD *)(v5 - 16) = v95;
      *(_QWORD *)(v5 - 8) = 0;
      goto LABEL_5;
    case 0x149u:
      v190 = *(_QWORD *)(v5 - 16);
      LODWORD(v197) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 - 16) = v197;
      *(_QWORD *)(v5 - 8) = v190;
      goto LABEL_5;
    case 0x14Bu:
      *(_BYTE *)(v5 + 32) = 0;
      goto LABEL_5;
    case 0x14Cu:
      v191 = *(_BYTE *)(v5 + 8);
      goto LABEL_416;
    case 0x14Du:
    case 0x14Eu:
      v191 = *(_BYTE *)(v5 - 22);
LABEL_416:
      *(_BYTE *)(v5 - 16) = v191;
      goto LABEL_5;
    case 0x14Fu:
      *(_BYTE *)(v5 + 8) = *(_BYTE *)(v5 + 2);
      goto LABEL_5;
    case 0x151u:
      v192 = *(_QWORD *)(v5 + 8);
      v193 = *(_QWORD *)(v5 - 16);
      if ( v192 )
        *(_QWORD *)(v192 + 72) = v193;
      else
        sqlite3ExprDelete(*a5, v193);
LABEL_221:
      v35 = *(_QWORD *)(v5 + 8);
LABEL_51:
      *(_QWORD *)(v5 - 16) = v35;
      goto LABEL_5;
    case 0x153u:
      v194 = sqlite3DbMallocZero(*a5, 144);
      v12 = v194;
      if ( v194 )
      {
        *(_BYTE *)(v194 + 32) = -90;
        *(_QWORD *)(v194 + 72) = *(_QWORD *)(v5 + 8);
      }
      else
      {
        sqlite3ExprDelete(*a5, *(_QWORD *)(v5 + 8));
      }
      goto LABEL_7;
    case 0x154u:
      v31 = *(_QWORD *)(v5 - 16);
LABEL_44:
      *(_QWORD *)(v5 - 64) = v31;
      goto LABEL_5;
    case 0x155u:
      v195 = sqlite3DbMallocZero(*a5, 144);
      *(_QWORD *)(v5 - 16) = v195;
      v40 = (_QWORD *)v195;
      if ( !v195 )
        goto LABEL_5;
      v41 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 + 16));
      goto LABEL_61;
    case 0x156u:
LABEL_401:
      appended = *(_QWORD *)(v5 - 16);
LABEL_46:
      *(_QWORD *)(v5 - 88) = appended;
      goto LABEL_5;
    case 0x157u:
      v11 = *(unsigned __int16 *)(v5 + 2);
      v198 = *(_OWORD *)(v5 + 8);
      v12 = tokenExpr(a5, v11, &v198);
      sqlite3DequoteNumber(a5, v12);
LABEL_7:
      *(_QWORD *)(v5 + 8) = v12;
      goto LABEL_5;
    default:
      goto LABEL_5;
  }
}

```

## disassembly

```asm
0x18000213c  mov     rax, rsp
0x18000213f  mov     [rax+18h], rbx
0x180002143  mov     [rax+10h], edx
0x180002146  mov     [rax+8], rcx
0x18000214a  push    rbp
0x18000214b  push    rsi
0x18000214c  push    rdi
0x18000214d  push    r12
0x18000214f  push    r13
0x180002151  push    r14
0x180002153  push    r15
0x180002155  lea     rbp, [rax-57h]
0x180002159  sub     rsp, 0B0h
0x180002160  mov     r13, [rcx]
0x180002163  lea     r15, __ImageBase
0x18000216a  cmp     edx, 157h; switch 344 cases
0x180002170  ja      short def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002172  mov     eax, edx
0x180002174  mov     r8d, ds:(jpt_18000217F - 180000000h)[r15+rax*4]
0x18000217c  add     r8, r15
0x18000217f  jmp     r8; switch jump
0x180002182  mov     rax, [r9]; jumptable 000000018000217F case 30
0x180002185  mov     [r13+20h], rax
0x180002189  jmp     short def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x18000218b  xor     r12d, r12d; jumptable 000000018000217F cases 101,107,110,134,144,146,148,153,155,166,175,232-234,237,242,252,268,287
0x18000218e  mov     [r13+20h], r12
0x180002192  mov     eax, [rbp+4Fh+arg_8]; jumptable 000000018000217F default case, cases 325,327,338
0x180002195  mov     rbx, [rsp+0E0h+arg_10]
0x18000219d  movzx   r8d, ds:rva word_1800BE480[r15+rax*2]
0x1800021a6  movsx   rax, byte ptr [rax+r15+0B4CA0h]
0x1800021af  lea     rdx, [rax+rax*2]
0x1800021b3  movzx   eax, word ptr [r13+rdx*8+0]
0x1800021b9  lea     rdx, [rdx+3]
0x1800021bd  lea     rcx, ds:0[rdx*8]
0x1800021c5  mov     rdx, [rbp+4Fh+arg_0]
0x1800021c9  movsx   eax, ds:rva word_1800BE0D0[r15+rax*2]
0x1800021d2  add     eax, r8d
0x1800021d5  add     rcx, r13
0x1800021d8  cdqe
0x1800021da  mov     [rdx], rcx
0x1800021dd  movzx   eax, ds:rva word_1800BE800[r15+rax*2]
0x1800021e6  mov     [rcx], ax
0x1800021e9  mov     [rcx+2], r8w
0x1800021ee  add     rsp, 0B0h
0x1800021f5  pop     r15
0x1800021f7  pop     r14
0x1800021f9  pop     r13
0x1800021fb  pop     r12
0x1800021fd  pop     rdi
0x1800021fe  pop     rsi
0x1800021ff  pop     rbp
0x180002200  retn
0x180002201  movups  xmm0, xmmword ptr [r13+8]; jumptable 000000018000217F case 343
0x180002206  movzx   edx, word ptr [r13+2]
0x18000220b  lea     r8, [rbp+4Fh+var_70]
0x18000220f  mov     rcx, [rbp+4Fh+arg_20]
0x180002213  movdqu  [rbp+4Fh+var_70], xmm0
0x180002218  call    tokenExpr
0x18000221d  mov     rcx, [rbp+4Fh+arg_20]
0x180002221  mov     rdx, rax
0x180002224  mov     rbx, rax
0x180002227  call    sqlite3DequoteNumber
0x18000222c  mov     [r13+8], rbx
0x180002230  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002235  xor     r12d, r12d; jumptable 000000018000217F cases 15,18,21,47,49,62,72,81,100,241,246
0x180002238  mov     [r13+20h], r12d
0x18000223c  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002241  mov     edx, 3Bh ; ';'; jumptable 000000018000217F case 180
0x180002246  movups  xmm0, xmmword ptr [r13+8]
0x18000224b  mov     rcx, [rbp+4Fh+arg_20]
0x18000224f  lea     r8, [rbp+4Fh+var_70]
0x180002253  movdqu  [rbp+4Fh+var_70], xmm0
0x180002258  call    tokenExpr
0x18000225d  mov     [r13+8], rax
0x180002261  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002266  mov     rdx, [r13+8]; jumptable 000000018000217F case 87
0x18000226a  test    rdx, rdx
0x18000226d  jz      def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002273  mov     rcx, [rbp+4Fh+arg_20]
0x180002277  call    parserDoubleLinkSelect
0x18000227c  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002281  mov     rcx, [rbp+4Fh+arg_20]; jumptable 000000018000217F case 2
0x180002285  call    sqlite3FinishCoding
0x18000228a  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x18000228f  xor     r12d, r12d; jumptable 000000018000217F cases 26,65,106
0x180002292  mov     [r13+28h], r12d
0x180002296  jmp     loc_18000218E
0x18000229b  mov     rax, [r13+8]; jumptable 000000018000217F case 186
0x18000229f  cmp     byte ptr [rax], 23h ; '#'
0x1800022a2  jz      loc_1800037F1
0x1800022a8  movups  xmm0, xmmword ptr [r13+8]
0x1800022ad  mov     rcx, [rbp+4Fh+arg_20]
0x1800022b1  lea     r8, [rbp+4Fh+var_70]
0x1800022b5  mov     ebx, [r13+10h]
0x1800022b9  mov     edx, 9Ch
0x1800022be  movdqu  [rbp+4Fh+var_70], xmm0
0x1800022c3  call    tokenExpr
0x1800022c8  mov     rcx, [rbp+4Fh+arg_20]
0x1800022cc  mov     r8d, ebx
0x1800022cf  mov     rdx, rax
0x1800022d2  mov     [r13+8], rax
0x1800022d6  call    sqlite3ExprAssignVarNumber
0x1800022db  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800022e0  mov     rbx, [rbp+4Fh+arg_20]; jumptable 000000018000217F case 102
0x1800022e4  mov     r8, [r13-28h]
0x1800022e8  mov     rcx, rbx
0x1800022eb  mov     rdx, [r13-58h]
0x1800022ef  call    sqlite3ExprListAppend
0x1800022f4  xor     r12d, r12d
0x1800022f7  mov     [r13-58h], rax
0x1800022fb  cmp     [r13+10h], r12d
0x1800022ff  ja      loc_180002EAB
0x180002305  mov     r9, [r13-10h]
0x180002309  mov     rcx, rbx
0x18000230c  mov     r8, [r13-40h]
0x180002310  mov     rdx, [r13-58h]
0x180002314  call    sqlite3ExprListSetSpan
0x180002319  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x18000231e  mov     edx, 1; jumptable 000000018000217F case 11
0x180002323  mov     rcx, [rbp+4Fh+arg_20]
0x180002327  lea     r8, [r13+8]
0x18000232b  call    sqlite3Savepoint
0x180002330  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002335  xor     r12d, r12d; jumptable 000000018000217F case 130
0x180002338  mov     [r13+20h], r12
0x18000233c  mov     [r13+28h], r12
0x180002340  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002345  xor     r12d, r12d; jumptable 000000018000217F cases 116,131
0x180002348  mov     [r13+20h], r12
0x18000234c  mov     [r13+28h], r12d
0x180002350  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002355  xor     edx, edx; jumptable 000000018000217F case 10
0x180002357  jmp     short loc_180002323
0x180002359  mov     rbx, [rbp+4Fh+arg_20]; jumptable 000000018000217F case 84
0x18000235d  lea     r8, [rbp+4Fh+var_60]
0x180002361  mov     rdx, [r13+8]
0x180002365  xor     eax, eax
0x180002367  xorps   xmm0, xmm0
0x18000236a  mov     [rbp+4Fh+var_60], 9
0x18000236e  mov     rcx, rbx
0x180002371  mov     [rbp+4Fh+var_5F], ax
0x180002375  mov     [rbp+4Fh+var_5D], al
0x180002378  movups  [rbp+4Fh+var_5C], xmm0
0x18000237c  mov     [rbp+4Fh+var_4C], eax
0x18000237f  movdqu  [rbp+4Fh+var_48], xmm0
0x180002384  call    sqlite3Select
0x180002389  mov     rdx, [r13+8]
0x18000238d  mov     rcx, [rbx]
0x180002390  call    sqlite3SelectDelete
0x180002395  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x18000239a  mov     dword ptr [r13+20h], 0FFFFFFFFh; jumptable 000000018000217F cases 140,143
0x1800023a2  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800023a7  mov     r8, [r13+8]; jumptable 000000018000217F case 197
0x1800023ab  mov     rdx, [r13-28h]
0x1800023af  mov     rcx, [rbp+4Fh+arg_20]
0x1800023b3  call    sqlite3ExprAnd
0x1800023b8  mov     [r13-28h], rax
0x1800023bc  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800023c1  xor     r12d, r12d; jumptable 000000018000217F cases 138,218,221
0x1800023c4  mov     [r13+8], r12d
0x1800023c8  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800023cd  mov     rax, [r13+8]; jumptable 000000018000217F case 92
0x1800023d1  mov     r9, [r13-58h]
0x1800023d5  mov     r8, [r13-70h]
0x1800023d9  mov     rdx, [r13-88h]
0x1800023e0  mov     rcx, [rbp+4Fh+arg_20]
0x1800023e4  mov     qword ptr [rsp+0E0h+var_A0], rax
0x1800023e9  mov     eax, [r13-0A0h]
0x1800023f0  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1800023f4  mov     rax, [r13-10h]
0x1800023f8  mov     [rsp+0E0h+var_B0], rax
0x1800023fd  mov     rax, [r13-28h]
0x180002401  mov     [rsp+0E0h+var_B8], rax
0x180002406  mov     rax, [r13-40h]
0x18000240a  mov     [rsp+0E0h+var_C0], rax
0x18000240f  call    sqlite3SelectNew
0x180002414  mov     [r13-0B8h], rax
0x18000241b  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002420  mov     r8, [r13+8]; jumptable 000000018000217F case 236
0x180002424  xor     edx, edx
0x180002426  mov     rcx, [rbp+4Fh+arg_20]
0x18000242a  call    sqlite3ExprListAppend
0x18000242f  jmp     loc_18000225D
0x180002434  mov     r8, [r13-28h]; jumptable 000000018000217F case 137
0x180002438  xor     edx, edx
0x18000243a  mov     rcx, [rbp+4Fh+arg_20]
0x18000243e  call    sqlite3ExprListAppend
0x180002443  mov     [r13-28h], rax
0x180002447  mov     r8d, [r13+8]
0x18000244b  mov     rcx, rax
0x18000244e  mov     edx, [r13-10h]
0x180002452  call    sqlite3ExprListSetSortOrder
0x180002457  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x18000245c  mov     dword ptr [r13+20h], 0Bh; jumptable 000000018000217F cases 73,75
0x180002464  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002469  movzx   edx, word ptr [r13-16h]; jumptable 000000018000217F cases 198-204
0x18000246e  mov     r9, [r13+8]
0x180002472  mov     r8, [r13-28h]
0x180002476  mov     rcx, [rbp+4Fh+arg_20]
0x18000247a  call    sqlite3PExpr
0x18000247f  jmp     loc_1800023B8
0x180002484  mov     rdx, [r13-28h]; jumptable 000000018000217F case 187
0x180002488  lea     r8, [r13+8]
0x18000248c  mov     rcx, [rbp+4Fh+arg_20]
0x180002490  mov     r9d, 1
0x180002496  call    sqlite3ExprAddCollateToken
0x18000249b  jmp     loc_1800023B8
0x1800024a0  mov     rcx, [rbp+4Fh+arg_20]; jumptable 000000018000217F case 191
0x1800024a4  lea     r8, [r13-40h]
0x1800024a8  xor     r9d, r9d
0x1800024ab  xor     edx, edx
0x1800024ad  call    sqlite3ExprFunction
0x1800024b2  mov     [r13-40h], rax
0x1800024b6  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800024bb  mov     rdx, [r13-58h]; jumptable 000000018000217F case 111
0x1800024bf  lea     rax, [r13+8]
0x1800024c3  mov     [rsp+0E0h+var_B0], rax
0x1800024c8  lea     rcx, [r13-10h]
0x1800024cc  xor     r12d, r12d
0x1800024cf  lea     r9, [r13-28h]
0x1800024d3  mov     [rsp+0E0h+var_B8], r12
0x1800024d8  lea     r8, [r13-40h]
0x1800024dc  mov     [rsp+0E0h+var_C0], rcx
0x1800024e1  mov     rcx, [rbp+4Fh+arg_20]
0x1800024e5  call    sqlite3SrcListAppendFromTerm
0x1800024ea  mov     [r13-58h], rax
0x1800024ee  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800024f3  mov     rdx, [r13+8]; jumptable 000000018000217F case 108
0x1800024f7  mov     rcx, [rbp+4Fh+arg_20]
0x1800024fb  mov     [r13-10h], rdx
0x1800024ff  call    sqlite3SrcListShiftJoinType
0x180002504  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002509  mov     edx, 94h; jumptable 000000018000217F case 149
0x18000250e  mov     r8, [r13+8]
0x180002512  mov     rcx, [rbp+4Fh+arg_20]
0x180002516  xor     r9d, r9d
0x180002519  call    sqlite3PExpr
0x18000251e  mov     [r13-10h], rax
0x180002522  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002527  mov     dword ptr [r13+20h], 7; jumptable 000000018000217F case 4
0x18000252f  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x180002534  mov     r8, [r13+8]; jumptable 000000018000217F case 235
0x180002538  mov     rcx, [rbp+4Fh+arg_20]
0x18000253c  mov     rdx, [r13-28h]
0x180002540  call    sqlite3ExprListAppend
0x180002545  jmp     loc_1800023B8
0x18000254a  mov     r8, [r13-28h]; jumptable 000000018000217F case 136
0x18000254e  mov     rdx, [r13-58h]
0x180002552  mov     rcx, [rbp+4Fh+arg_20]
0x180002556  call    sqlite3ExprListAppend
0x18000255b  mov     [r13-58h], rax
0x18000255f  jmp     loc_180002447
0x180002564  mov     rdi, [rbp+4Fh+arg_20]; jumptable 000000018000217F case 196
0x180002568  mov     r8, [r13-10h]
0x18000256c  mov     rcx, rdi
0x18000256f  mov     rdx, [r13-40h]
0x180002573  call    sqlite3ExprListAppend
0x180002578  xor     r9d, r9d
0x18000257b  xor     r8d, r8d
0x18000257e  mov     edx, 0B1h
0x180002583  mov     rcx, rdi
0x180002586  mov     rbx, rax
0x180002589  call    sqlite3PExpr
0x18000258e  xor     r12d, r12d
0x180002591  mov     [r13-58h], rax
0x180002595  test    rax, rax
0x180002598  jz      loc_180003974
0x18000259e  mov     [rax+20h], rbx
0x1800025a2  cmp     [rbx], r12d
0x1800025a5  jz      def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800025ab  mov     rax, [rbx+8]
0x1800025af  mov     rdx, [r13-58h]
0x1800025b3  mov     ecx, [rax+4]
0x1800025b6  and     ecx, 400208h
0x1800025bc  or      [rdx+4], ecx
0x1800025bf  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800025c4  mov     rdi, [rbp+4Fh+arg_20]; jumptable 000000018000217F case 185
0x1800025c8  lea     rbx, [r13+8]
0x1800025cc  mov     r9d, 1
0x1800025d2  mov     r8, rbx
0x1800025d5  mov     edx, 9Bh
0x1800025da  mov     rcx, [rdi]
0x1800025dd  call    sqlite3ExprAlloc
0x1800025e2  test    rax, rax
0x1800025e5  jz      short loc_1800025F2
0x1800025e7  mov     ecx, [rbx]
0x1800025e9  sub     ecx, [rdi+158h]
0x1800025ef  mov     [rax+34h], ecx
0x1800025f2  mov     [rbx], rax
0x1800025f5  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x1800025fa  movzx   edx, word ptr [r13-16h]; jumptable 000000018000217F cases 8,9
0x1800025ff  mov     rcx, [rbp+4Fh+arg_20]
0x180002603  call    sqlite3EndTransaction
0x180002608  jmp     def_18000217F; jumptable 000000018000217F default case, cases 325,327,338
0x18000260d  mov     rcx, [rbp+4Fh+arg_20]; jumptable 000000018000217F case 120
0x180002611  lea     r8, [r13+8]
0x180002615  xor     r9d, r9d
0x180002618  xor     edx, edx
0x18000261a  call    sqlite3SrcListAppend
0x18000261f  jmp     loc_18000225D
  ... truncated ...
```

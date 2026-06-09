# yy_reduce

- ea: `0x1800c3bd8`
- end: `0x1800c6bc8`
- name: `yy_reduce`
- size: `12272`
- prototype: ``
- caller_count: `1`
- callee_count: `106`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x180084094`

## callees

- `0x18003cf7c`
- `0x180042a08`
- `0x1800459b0`
- `0x180045b1c`
- `0x18005c38c`
- `0x18005c3fc`
- `0x1800669ac`
- `0x180066aac`
- `0x180066b64`
- `0x180066ed4`
- `0x180067018`
- `0x1800671bc`
- `0x180067230`
- `0x1800674dc`
- `0x1800677bc`
- `0x18006799c`
- `0x180067ef8`
- `0x1800682a4`
- `0x180068554`
- `0x1800689e0`
- `0x18006937c`
- `0x18006973c`
- `0x180069814`
- `0x18006ff78`
- `0x180070678`
- `0x180071400`
- `0x180071650`
- `0x1800718ac`
- `0x180071aac`
- `0x180071d34`
- `0x180072960`
- `0x1800729c0`
- `0x180072b2c`
- `0x180072b68`
- `0x180072d54`
- `0x180072ff4`
- `0x180073228`
- `0x1800739c4`
- `0x180073aec`
- `0x180073eb8`
- `0x180073f70`
- `0x1800740f0`
- `0x18007429c`
- `0x180074344`
- `0x180074528`
- `0x180076d50`
- `0x180076d6c`
- `0x180076ef4`
- `0x180076fa8`
- `0x180077a60`

## string_xrefs

- `0x1800c5fd5`: `qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers`
- `0x1800c5ff1`: `the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers`
- `0x1800c5ffa`: `the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers`

## pseudocode

```c
__int64 __fastcall yy_reduce(__int64 *a1, unsigned int a2, __int64 a3, __int64 *a4, _QWORD *a5)
{
  __int64 v5; // r12
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r13d
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  const char *v11; // r9
  int v12; // r8d
  __int128 v13; // xmm1
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdi
  __int64 v39; // rdx
  int v40; // eax
  __int64 updated; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdi
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 appended; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r8
  _QWORD *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  _QWORD *v58; // rcx
  int *v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  _DWORD *v63; // rdx
  int *v64; // rax
  int *v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r9
  __int64 v68; // rax
  __int64 v69; // rax
  _OWORD *v70; // rsi
  __int64 v71; // rdi
  unsigned __int8 v72; // al
  __int64 v73; // r14
  __int64 v74; // rax
  __int64 v75; // rdi
  unsigned __int8 v76; // al
  __int64 v77; // r15
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rbx
  __int64 v81; // r9
  __int64 v82; // rax
  __int64 v83; // r13
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // r8
  __int64 i; // rdx
  __int64 v94; // rax
  int *v95; // rax
  __int64 v96; // rax
  _DWORD *v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // r8
  __int64 j; // rcx
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // r13
  __int64 inserted; // rax
  __int64 v106; // rdx
  __int64 v107; // rbx
  __int64 v108; // rdx
  __int64 v109; // r8
  _QWORD *v110; // rcx
  __int64 v111; // r14
  __int64 v112; // rbx
  _QWORD *v113; // rcx
  __int64 v114; // r8
  __int64 v115; // rdx
  _QWORD *v116; // rcx
  _QWORD *v117; // rbx
  __int64 v118; // rax
  _BYTE *v119; // rax
  __int64 v120; // rax
  unsigned int v121; // ebx
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // r8
  __int64 v126; // rbx
  __int64 v127; // rbx
  __int64 v128; // rbx
  __int64 v129; // rbx
  __int64 v130; // rbx
  __int64 v131; // rax
  int v132; // ebx
  __int64 v133; // r8
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  int v137; // ebx
  __int64 v138; // r8
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rax
  _QWORD *v142; // rdi
  __int64 v143; // rax
  __int64 v144; // rbx
  _BYTE *v145; // rax
  __int64 v146; // rcx
  __int64 v147; // rdx
  _QWORD *v148; // rdi
  __int64 v149; // rax
  _BYTE *v150; // rax
  unsigned __int8 *v151; // rax
  unsigned __int8 v152; // cl
  __int64 v153; // rax
  __int64 v154; // rax
  _QWORD *v155; // rbx
  __int64 v156; // rax
  __int64 v157; // rdi
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rdi
  const char *v161; // r8
  __int64 v162; // rax
  __int64 v163; // rsi
  __int64 v164; // rdx
  __int64 v165; // rax
  __int64 v166; // rdx
  __int64 v167; // rax
  __int64 v168; // rdx
  __int64 v169; // rax
  __int64 v170; // rsi
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // r8
  __int64 v174; // rsi
  __int64 v175; // rax
  __int64 v176; // rdi
  __int64 v177; // rax
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // r8
  __int64 v181; // rax
  __int64 v182; // rax
  __int64 v183; // r8
  int v184; // edi
  void *v185; // rsi
  int v186; // r14d
  int *v187; // r15
  __int64 v188; // rax
  _QWORD *v189; // rdx
  __int64 v190; // rdx
  const char **v191; // r8
  __int64 v192; // r9
  __int64 v193; // rdx
  __int64 v194; // r9
  const char **v195; // r8
  __int64 v196; // rdx
  __int64 v197; // rdx
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // r8
  __int64 v201; // rdx
  __int64 v202; // r8
  __int64 v203; // rdx
  __int64 v204; // rdx
  _QWORD *v205; // rbx
  __int64 v206; // r9
  __int64 v207; // r8
  __int64 v208; // rcx
  char v209; // al
  __int64 v210; // rax
  __int64 v211; // rdx
  __int64 v212; // rax
  __int64 v213; // rbx
  __int64 v214; // rax
  __int64 v215; // rdx
  unsigned __int16 v216; // di
  __int64 v217; // rax
  __int64 v218; // rbx
  __int64 result; // rax
  _WORD *v220; // rcx
  __int128 v221; // [rsp+68h] [rbp-31h] BYREF
  __int128 v222; // [rsp+78h] [rbp-21h] BYREF
  char v223; // [rsp+88h] [rbp-11h] BYREF
  __int16 v224; // [rsp+89h] [rbp-10h]
  char v225; // [rsp+8Bh] [rbp-Eh]
  __int128 v226; // [rsp+8Ch] [rbp-Dh]
  int v227; // [rsp+9Ch] [rbp+3h]
  __int128 v228; // [rsp+A0h] [rbp+7h]

  v5 = *a1;
  switch ( a2 )
  {
    case 0u:
      if ( !a5[42] )
        *((_BYTE *)a5 + 307) = 1;
      goto LABEL_481;
    case 1u:
      if ( !a5[42] )
        *((_BYTE *)a5 + 307) = 2;
      goto LABEL_481;
    case 2u:
      sqlite3FinishCoding(a5);
      goto LABEL_481;
    case 3u:
      sqlite3BeginTransaction(a5, *(unsigned int *)(v5 - 16));
      goto LABEL_481;
    case 4u:
      *(_DWORD *)(v5 + 32) = 7;
      goto LABEL_481;
    case 5u:
    case 6u:
    case 7u:
    case 0x59u:
    case 0x5Bu:
    case 0x106u:
    case 0x144u:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      goto LABEL_481;
    case 8u:
    case 9u:
      sqlite3EndTransaction(a5, *(unsigned __int16 *)(v5 - 22));
      goto LABEL_481;
    case 0xAu:
      v6 = 0;
      goto LABEL_12;
    case 0xBu:
      v6 = 1;
      goto LABEL_12;
    case 0xCu:
      v6 = 2;
LABEL_12:
      sqlite3Savepoint(a5, v6, v5 + 8);
      goto LABEL_481;
    case 0xDu:
      sqlite3StartTable(a5, (_OWORD *)(v5 - 16), v5 + 8, *(_DWORD *)(v5 - 88), 0, 0, *(_DWORD *)(v5 - 40));
      goto LABEL_481;
    case 0xEu:
      ++*((_BYTE *)a5 + 36);
      v7 = *a5;
      ++*(_DWORD *)(v7 + 416);
      *(_WORD *)(v7 + 420) = 0;
      goto LABEL_481;
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
      goto LABEL_481;
    case 0x10u:
      *(_DWORD *)(v5 - 40) = 1;
      goto LABEL_481;
    case 0x11u:
      v8 = *(_BYTE *)(*a5 + 197LL) == 0;
      goto LABEL_19;
    case 0x13u:
      sqlite3EndTable((_DWORD)a5, v5 - 40, v5 - 16, *(_DWORD *)(v5 + 8), 0);
      goto LABEL_481;
    case 0x14u:
      v9 = a5;
      sqlite3EndTable((_DWORD)a5, 0, 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_22;
    case 0x16u:
      *(_DWORD *)(v5 - 40) |= *(_DWORD *)(v5 + 8);
      goto LABEL_481;
    case 0x17u:
      if ( *(_DWORD *)(v5 + 16) != 5 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "rowid", 5) )
      {
        v11 = *(const char **)(v5 + 8);
        v12 = *(_DWORD *)(v5 + 16);
        *(_DWORD *)(v5 - 16) = 0;
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", v12, v11);
      }
      else
      {
        *(_DWORD *)(v5 - 16) = 640;
      }
      goto LABEL_481;
    case 0x18u:
      v8 = 0;
      if ( *(_DWORD *)(v5 + 16) != 6 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "strict", 6) )
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", *(_DWORD *)(v5 + 16), *(const char **)(v5 + 8));
      else
        v8 = 0x10000;
      goto LABEL_19;
    case 0x19u:
      v13 = *(_OWORD *)(v5 - 16);
      v221 = *(_OWORD *)(v5 + 8);
      v222 = v13;
      sqlite3AddColumn(a5, &v222, &v221);
      goto LABEL_481;
    case 0x1Au:
    case 0x41u:
    case 0x6Au:
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_35;
    case 0x1Bu:
      *(_DWORD *)(v5 - 56) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64);
      goto LABEL_481;
    case 0x1Cu:
      *(_DWORD *)(v5 - 104) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 112);
      goto LABEL_481;
    case 0x1Du:
      *(_DWORD *)(v5 - 8) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 16);
      goto LABEL_481;
    case 0x1Eu:
      v14 = *a4;
      goto LABEL_40;
    case 0x1Fu:
      *(_OWORD *)(v5 + 32) = *(_OWORD *)a4;
      goto LABEL_481;
    case 0x20u:
    case 0x43u:
      *((_OWORD *)a5 + 7) = *(_OWORD *)(v5 + 8);
      goto LABEL_481;
    case 0x21u:
      v15 = *(_QWORD *)(v5 - 16);
      v16 = v15 + *(unsigned int *)(v5 - 8);
      goto LABEL_44;
    case 0x22u:
      v16 = *(_QWORD *)(v5 + 8);
      v15 = *(_QWORD *)(v5 - 40) + 1LL;
      v17 = *(_QWORD *)(v5 - 16);
      goto LABEL_45;
    case 0x23u:
      v16 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v15 = *(_QWORD *)(v5 - 40);
LABEL_44:
      v17 = *(_QWORD *)(v5 + 8);
      goto LABEL_45;
    case 0x24u:
      v17 = sqlite3PExpr(a5, 174, *(_QWORD *)(v5 + 8));
      v16 = *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8);
      v15 = *(_QWORD *)(v5 - 40);
      goto LABEL_45;
    case 0x25u:
      v222 = *(_OWORD *)(v5 + 8);
      v18 = tokenExpr(a5, 117, &v222);
      v19 = v18;
      if ( v18 )
        sqlite3ExprIdToTrueFalse(v18);
      v15 = *(_QWORD *)(v5 + 8);
      v17 = v19;
      v16 = v15 + *(unsigned int *)(v5 + 16);
LABEL_45:
      sqlite3AddDefaultValue(a5, v17, v15, v16);
      goto LABEL_481;
    case 0x26u:
      sqlite3AddNotNull(a5, *(unsigned int *)(v5 + 8));
      goto LABEL_481;
    case 0x27u:
      sqlite3AddPrimaryKey((_DWORD)a5, 0, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40));
      goto LABEL_481;
    case 0x28u:
      sqlite3CreateIndex(a5, 0, 0, 0, 0, *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_481;
    case 0x29u:
      v20 = *(_QWORD *)(v5 + 8);
      v21 = *(_QWORD *)(v5 - 40);
      v22 = *(_QWORD *)(v5 - 16);
      goto LABEL_58;
    case 0x2Au:
      sqlite3CreateForeignKey((_DWORD)a5, 0, v5 - 40, *(_QWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_481;
    case 0x2Bu:
      v23 = a5[44];
      if ( v23 )
      {
        if ( !*(_BYTE *)(v23 + 63) )
        {
          v24 = *(_QWORD *)(v23 + 72);
          if ( v24 )
            *(_BYTE *)(v24 + 44) = *(_BYTE *)(v5 + 8);
        }
      }
      goto LABEL_481;
    case 0x2Cu:
      sqlite3AddCollateType(a5, v5 + 8);
      goto LABEL_481;
    case 0x2Du:
      v25 = *(_QWORD *)(v5 - 16);
      v26 = 0;
      goto LABEL_66;
    case 0x2Eu:
      v25 = *(_QWORD *)(v5 - 40);
      v26 = v5 + 8;
LABEL_66:
      sqlite3AddGenerated(a5, v25, v26);
      goto LABEL_481;
    case 0x30u:
    case 0x62u:
    case 0x7Cu:
    case 0x8Bu:
    case 0x119u:
      *(_DWORD *)(v5 + 8) = 1;
      goto LABEL_481;
    case 0x32u:
      v27 = *(_DWORD *)(v5 + 8) | *(_DWORD *)(v5 - 16) & ~*(_DWORD *)(v5 + 12);
      goto LABEL_71;
    case 0x33u:
      goto LABEL_222;
    case 0x34u:
      *(_QWORD *)(v5 - 40) = 0;
      goto LABEL_481;
    case 0x35u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 36) = 255;
      goto LABEL_481;
    case 0x36u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8) << 8;
      *(_DWORD *)(v5 - 36) = 65280;
      goto LABEL_481;
    case 0x37u:
      *(_DWORD *)(v5 - 16) = 8;
      goto LABEL_481;
    case 0x38u:
      *(_DWORD *)(v5 - 16) = 9;
      goto LABEL_481;
    case 0x39u:
      *(_DWORD *)(v5 + 8) = 10;
      goto LABEL_481;
    case 0x3Au:
      *(_DWORD *)(v5 + 8) = 7;
      goto LABEL_481;
    case 0x3Bu:
    case 0x40u:
    case 0x8Du:
      *(_DWORD *)(v5 - 16) = 0;
      goto LABEL_481;
    case 0x3Cu:
      *(_DWORD *)(v5 - 40) = 0;
      goto LABEL_481;
    case 0x3Du:
    case 0x4Cu:
    case 0xADu:
      v27 = *(_DWORD *)(v5 + 8);
      goto LABEL_71;
    case 0x3Fu:
    case 0x50u:
    case 0x8Eu:
    case 0xDBu:
    case 0xDEu:
    case 0xF7u:
      *(_DWORD *)(v5 - 16) = 1;
      goto LABEL_481;
    case 0x42u:
      *((_DWORD *)a5 + 30) = 0;
      goto LABEL_481;
    case 0x44u:
      sqlite3AddPrimaryKey((_DWORD)a5, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40), 0);
      goto LABEL_481;
    case 0x45u:
      sqlite3CreateIndex(a5, 0, 0, 0, *(int **)(v5 - 40), *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_481;
    case 0x46u:
      v20 = *(_QWORD *)(v5 - 16);
      v21 = *(_QWORD *)(v5 - 64);
      v22 = *(_QWORD *)(v5 - 40);
LABEL_58:
      sqlite3AddCheckConstraint(a5, v22, v21, v20);
      goto LABEL_481;
    case 0x47u:
      sqlite3CreateForeignKey((_DWORD)a5, *(_QWORD *)(v5 - 136), v5 - 64, *(_QWORD *)(v5 - 40), *(_DWORD *)(v5 - 16));
      v28 = a5[44];
      if ( v28 )
      {
        if ( !*(_BYTE *)(v28 + 63) )
        {
          v29 = *(_QWORD *)(v28 + 72);
          if ( v29 )
            *(_BYTE *)(v29 + 44) = *(_BYTE *)(v5 + 8);
        }
      }
      goto LABEL_481;
    case 0x49u:
    case 0x4Bu:
      *(_DWORD *)(v5 + 32) = 11;
      goto LABEL_481;
    case 0x4Au:
      v30 = *(_DWORD *)(v5 + 8);
      goto LABEL_93;
    case 0x4Du:
      *(_DWORD *)(v5 + 8) = 4;
      goto LABEL_481;
    case 0x4Eu:
    case 0xAEu:
      *(_DWORD *)(v5 + 8) = 5;
      goto LABEL_481;
    case 0x4Fu:
      v31 = 0;
      goto LABEL_97;
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
      goto LABEL_481;
    case 0x53u:
      v31 = 1;
LABEL_97:
      sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), v31, *(unsigned int *)(v5 - 16));
      goto LABEL_481;
    case 0x54u:
      v9 = a5;
      v32 = *(_QWORD *)(v5 + 8);
      v223 = 9;
      v224 = 0;
      v225 = 0;
      v226 = 0;
      v227 = 0;
      v228 = 0;
      sqlite3Select(a5, v32, &v223);
LABEL_22:
      v10 = *(_QWORD *)(v5 + 8);
      if ( v10 )
        clearSelect(*v9, v10, 1);
      goto LABEL_481;
    case 0x55u:
      v33 = *(_QWORD *)(v5 + 8);
      v34 = *(_QWORD *)(v5 - 16);
      if ( v33 )
      {
        *(_QWORD *)(v33 + 104) = v34;
        parserDoubleLinkSelect(a5, v33);
      }
      else
      {
        sqlite3WithDelete(*a5, v34);
      }
      goto LABEL_104;
    case 0x56u:
      v35 = *(_QWORD *)(v5 + 8);
      v36 = *(_QWORD *)(v5 - 16);
      if ( v35 )
      {
        *(_QWORD *)(v35 + 104) = v36;
        parserDoubleLinkSelect(a5, v35);
      }
      else
      {
        sqlite3WithDelete(*a5, v36);
      }
      *(_QWORD *)(v5 - 64) = v35;
      goto LABEL_481;
    case 0x57u:
      v37 = *(_QWORD *)(v5 + 8);
      if ( v37 )
        parserDoubleLinkSelect(a5, v37);
      goto LABEL_481;
    case 0x58u:
      v33 = *(_QWORD *)(v5 + 8);
      v38 = *(_QWORD *)(v5 - 40);
      if ( v33
        && (!*(_QWORD *)(v33 + 80)
         || (v39 = *(_QWORD *)(v5 + 8),
             v222 = 0,
             parserDoubleLinkSelect(a5, v39),
             v40 = sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v222, v33, 0),
             (v33 = sqlite3SelectNew((_DWORD)a5, 0, v40, 0, 0, 0, 0, 0, 0)) != 0)) )
      {
        *(_BYTE *)v33 = *(_BYTE *)(v5 - 16);
        *(_QWORD *)(v33 + 80) = v38;
        if ( v38 )
          *(_DWORD *)(v38 + 4) &= ~0x400u;
        *(_DWORD *)(v33 + 4) &= ~0x400u;
        if ( *(_DWORD *)(v5 - 16) != 135 )
          *((_BYTE *)a5 + 34) = 1;
      }
      else if ( v38 )
      {
        clearSelect(*a5, v38, 1);
      }
      goto LABEL_104;
    case 0x5Au:
      *(_DWORD *)(v5 - 16) = 135;
      goto LABEL_481;
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
      goto LABEL_122;
    case 0x5Du:
      v42 = sqlite3SelectNew(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              *(_QWORD *)(v5 - 136),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 - 88),
              *(_QWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 16),
              *(_DWORD *)(v5 - 184),
              *(_QWORD *)(v5 + 8));
      v43 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 208) = v42;
      if ( v42 )
      {
        *(_QWORD *)(v42 + 120) = v43;
      }
      else
      {
        v44 = *a5;
        if ( v43 )
        {
          do
          {
            v45 = *(_QWORD *)(v43 + 64);
            sqlite3WindowDelete(v44);
            v43 = v45;
          }
          while ( v45 );
        }
      }
      goto LABEL_481;
    case 0x5Eu:
      v46 = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 512, 0);
      goto LABEL_129;
    case 0x5Fu:
      sqlite3MultiValuesEnd(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0x60u:
    case 0x61u:
      appended = sqlite3MultiValues(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16));
      goto LABEL_132;
    case 0x63u:
    case 0xF0u:
    case 0x11Au:
      *(_DWORD *)(v5 + 8) = 2;
      goto LABEL_481;
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
LABEL_35:
      *(_QWORD *)(v5 + 32) = 0;
      goto LABEL_481;
    case 0x66u:
      v48 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v48;
      if ( *(_DWORD *)(v5 + 16) )
        sqlite3ExprListSetName(a5, v48, v5 + 8, 1);
      sqlite3ExprListSetSpan(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      goto LABEL_481;
    case 0x67u:
      v49 = sqlite3Expr(*a5, 180, 0);
      if ( v49 && (*(_BYTE *)(v49 + 4) & 3) == 0 )
        *(_DWORD *)(v49 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86);
      v50 = v49;
      v51 = a5;
      goto LABEL_140;
    case 0x68u:
      v53 = sqlite3PExpr(a5, 180, 0);
      if ( v53 && (*(_BYTE *)(v53 + 4) & 3) == 0 )
        *(_DWORD *)(v53 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86);
      v222 = *(_OWORD *)(v5 - 40);
      v54 = tokenExpr(a5, 59, &v222);
      v55 = sqlite3PExpr(a5, 141, v54);
      v56 = *(_QWORD *)(v5 - 88);
      v57 = v55;
      v58 = a5;
      goto LABEL_146;
    case 0x69u:
    case 0x75u:
    case 0x102u:
    case 0x103u:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      goto LABEL_481;
    case 0x6Cu:
      *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      sqlite3SrcListShiftJoinType(a5);
      goto LABEL_481;
    case 0x6Du:
      v59 = *(int **)(v5 - 16);
      if ( v59 && *v59 > 0 )
        LOBYTE(v59[26 * *v59 - 9]) = *(_BYTE *)(v5 + 8);
      goto LABEL_481;
    case 0x6Fu:
      appended = sqlite3SrcListAppendFromTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 64,
                   (int)v5 - 40,
                   v5 - 16,
                   0,
                   v5 + 8);
      goto LABEL_132;
    case 0x70u:
      v60 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 112),
              (int)v5 - 88,
              (int)v5 - 64,
              v5 - 40,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 112) = v60;
      sqlite3SrcListIndexedBy(a5, v60, v5 - 16);
      goto LABEL_481;
    case 0x71u:
      v61 = sqlite3SrcListAppendFromTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              (int)v5 - 136,
              (int)v5 - 112,
              v5 - 16,
              0,
              v5 + 8);
      *(_QWORD *)(v5 - 160) = v61;
      sqlite3SrcListFuncArgs(a5, v61);
      goto LABEL_481;
    case 0x72u:
      v62 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_156;
    case 0x73u:
      if ( !*(_QWORD *)(v5 - 112) && !*(_DWORD *)(v5 - 8) && !*(_QWORD *)(v5 + 8) && !*(_QWORD *)(v5 + 16) )
      {
        v62 = *(_QWORD *)(v5 - 64);
LABEL_156:
        *(_QWORD *)(v5 - 112) = v62;
        goto LABEL_481;
      }
      v63 = *(_DWORD **)(v5 - 64);
      if ( !v63 || *v63 != 1 )
      {
        sqlite3SrcListShiftJoinType(a5);
        v69 = sqlite3SelectNew((_DWORD)a5, 0, *(_QWORD *)(v5 - 64), 0, 0, 0, 0, 2048, 0);
        v62 = sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, v69, v5 + 8);
        goto LABEL_156;
      }
      v64 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, *(_QWORD *)(v5 - 112), 0, 0, v5 - 16, 0, v5 + 8);
      *(_QWORD *)(v5 - 112) = v64;
      v65 = v64;
      if ( v64 )
      {
        v66 = *(_QWORD *)(v5 - 64);
        v67 = 26LL * *v64;
        *(_QWORD *)&v64[v67 - 20] = *(_QWORD *)(v66 + 24);
        *(_QWORD *)&v64[v67 - 22] = *(_QWORD *)(v66 + 16);
        v68 = *(_QWORD *)(v66 + 48);
        *(_QWORD *)&v65[v67 - 14] = v68;
        if ( v68 && (*(_DWORD *)(v68 + 4) & 0x800) != 0 )
          v65[v67 - 8] |= 0x2000u;
        if ( (*(_BYTE *)(v66 + 72) & 4) != 0 )
        {
          *(_QWORD *)&v65[v67 - 2] = *(_QWORD *)(v66 + 96);
          *(_DWORD *)(v66 + 72) &= ~4u;
          *(_QWORD *)(v66 + 96) = 0;
          v65[v67 - 8] |= 4u;
        }
        *(_QWORD *)(v66 + 16) = 0;
        *(_QWORD *)(v66 + 24) = 0;
        *(_QWORD *)(v66 + 48) = 0;
      }
      sqlite3SrcListDelete(*a5, *(_QWORD *)(v5 - 64));
LABEL_481:
      v216 = word_1800FBBF0[a2];
      v217 = *((char *)qword_1800FB1A0 + a2);
      v218 = 3 * v217;
      result = yy_find_reduce_action(*(unsigned __int16 *)(v5 + 24 * v217), v216);
      v220 = (_WORD *)(v5 + 8 * (v218 + 3));
      *a1 = (__int64)v220;
      *v220 = result;
      v220[1] = v216;
      return result;
    case 0x74u:
    case 0x83u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_481;
    case 0x76u:
      v70 = (_OWORD *)(v5 + 8);
      v71 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      v72 = *((_BYTE *)a5 + 308);
      if ( v72 >= 2u )
      {
        if ( v71 )
        {
          if ( v72 != 3 )
          {
            v73 = *(_QWORD *)(v71 + 24);
            v74 = sqlite3DbMallocZero(*a5, 32);
            if ( v74 )
            {
              *(_QWORD *)v74 = v73;
              *(_OWORD *)(v74 + 8) = *v70;
              *(_QWORD *)(v74 + 24) = a5[52];
              a5[52] = v74;
            }
          }
        }
      }
      *(_QWORD *)v70 = v71;
      goto LABEL_481;
    case 0x77u:
      v75 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      v76 = *((_BYTE *)a5 + 308);
      if ( v76 >= 2u )
      {
        if ( v75 )
        {
          if ( v76 != 3 )
          {
            v77 = *(_QWORD *)(v75 + 24);
            v78 = sqlite3DbMallocZero(*a5, 32);
            if ( v78 )
            {
              *(_QWORD *)v78 = v77;
              *(_OWORD *)(v78 + 8) = *(_OWORD *)(v5 + 8);
              *(_QWORD *)(v78 + 24) = a5[52];
              a5[52] = v78;
            }
          }
        }
      }
      goto LABEL_185;
    case 0x78u:
      v79 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      goto LABEL_187;
    case 0x79u:
      v52 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      goto LABEL_141;
    case 0x7Au:
      v80 = v5 - 88;
      v81 = v5 - 40;
      goto LABEL_190;
    case 0x7Bu:
      v80 = v5 - 40;
      v81 = 0;
LABEL_190:
      v82 = sqlite3SrcListAppend(a5, 0, v80, v81);
      v83 = 0;
      *(_QWORD *)v80 = v82;
      if ( v82 )
      {
        if ( v5 != -8 )
        {
          v83 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 + 16));
          sqlite3Dequote(v83);
        }
        *(_QWORD *)(*(_QWORD *)v80 + 32LL) = v83;
      }
      goto LABEL_481;
    case 0x7Du:
      v27 = sqlite3JoinType(a5, v5 - 16, 0, 0);
LABEL_71:
      *(_DWORD *)(v5 - 16) = v27;
      goto LABEL_481;
    case 0x7Eu:
      v30 = sqlite3JoinType(a5, v5 - 40, v5 - 16, 0);
LABEL_93:
      *(_DWORD *)(v5 - 40) = v30;
      goto LABEL_481;
    case 0x7Fu:
      *(_DWORD *)(v5 - 64) = sqlite3JoinType(a5, v5 - 64, v5 - 40, v5 - 16);
      goto LABEL_481;
    case 0x80u:
      v84 = *(_QWORD *)(v5 + 8);
      goto LABEL_199;
    case 0x81u:
      v85 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 64) = 0;
      *(_QWORD *)(v5 - 56) = v85;
      goto LABEL_481;
    case 0x82u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 0;
      goto LABEL_481;
    case 0x84u:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      goto LABEL_481;
    case 0x85u:
      *(_DWORD *)(v5 - 8) = 1;
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_481;
    case 0x87u:
    case 0x91u:
      goto LABEL_449;
    case 0x88u:
      v86 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v86;
      goto LABEL_205;
    case 0x89u:
      v86 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 40) = v86;
LABEL_205:
      sqlite3ExprListSetSortOrder(v86, *(unsigned int *)(v5 - 16), *(unsigned int *)(v5 + 8));
      goto LABEL_481;
    case 0x8Au:
    case 0xDAu:
    case 0xDDu:
      v8 = 0;
LABEL_19:
      *(_DWORD *)(v5 + 8) = v8;
      goto LABEL_481;
    case 0x8Cu:
    case 0x8Fu:
      *(_DWORD *)(v5 + 32) = -1;
      goto LABEL_481;
    case 0x93u:
    case 0x9Au:
    case 0x9Cu:
    case 0xE7u:
    case 0xFBu:
    case 0x10Du:
    case 0x120u:
    case 0x150u:
      goto LABEL_208;
    case 0x95u:
      v88 = 148;
      goto LABEL_211;
    case 0x96u:
      v90 = *(_QWORD *)(v5 - 40);
      goto LABEL_214;
    case 0x97u:
      v90 = *(_QWORD *)(v5 + 8);
LABEL_214:
      v46 = sqlite3PExpr(a5, 148, v90);
      goto LABEL_129;
    case 0x98u:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 88), v5 - 64);
      v91 = *(_QWORD *)(v5 - 16);
      v92 = *(_QWORD *)(v5 + 8);
      if ( v91 || v92 )
      {
        updateDeleteLimitError(a5, v91, v92);
        for ( i = 0; i != 2; ++i )
        {
          v94 = 3 * i;
          *(_QWORD *)(v5 + 8 * v94 - 16) = 0;
        }
      }
      sqlite3DeleteFrom(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 88),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0x9Du:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
LABEL_222:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_481;
    case 0x9Eu:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      v46 = *(_QWORD *)(v5 - 40);
      goto LABEL_129;
    case 0x9Fu:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 160), v5 - 136);
      v95 = *(int **)(v5 - 64);
      if ( v95 )
      {
        if ( *v95 > 1 )
        {
          v221 = 0;
          v96 = sqlite3SelectNew((_DWORD)a5, 0, (_DWORD)v95, 0, 0, 0, 0, 2048, 0);
          DWORD2(v221) = 0;
          *(_QWORD *)&v221 = 0;
          v95 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v221, v96, 0);
        }
        *(_QWORD *)(v5 - 160) = sqlite3SrcListAppendList(a5, *(_QWORD *)(v5 - 160), v95);
      }
      v97 = *(_DWORD **)(v5 - 88);
      if ( v97 && *v97 > *(_DWORD *)(*a5 + 144LL) )
        sqlite3ErrorMsg(a5, "too many columns in %s", "set list");
      v98 = *(_QWORD *)(v5 - 16);
      v99 = *(_QWORD *)(v5 + 8);
      if ( v98 || v99 )
      {
        updateDeleteLimitError(a5, v98, v99);
        for ( j = 0; j != 2; ++j )
        {
          v101 = 3 * j;
          *(_QWORD *)(v5 + 8 * v101 - 16) = 0;
        }
      }
      sqlite3Update(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 160),
        *(_QWORD *)(v5 - 88),
        *(_QWORD *)(v5 - 40),
        *(_DWORD *)(v5 - 184),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 + 8),
        0);
      goto LABEL_481;
    case 0xA0u:
      v102 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v102;
      sqlite3ExprListSetName(a5, v102, v5 - 40, 1);
      goto LABEL_481;
    case 0xA1u:
      *(_QWORD *)(v5 - 136) = sqlite3ExprListAppendVector(
                                a5,
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0xA2u:
      v75 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      sqlite3ExprListSetName(a5, v75, v5 - 40, 1);
LABEL_185:
      *(_QWORD *)(v5 - 40) = v75;
      goto LABEL_481;
    case 0xA3u:
      appended = sqlite3ExprListAppendVector(a5, 0, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
      goto LABEL_132;
    case 0xA4u:
      sqlite3Insert(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 - 40),
        *(_DWORD *)(v5 - 112),
        *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0xA5u:
      sqlite3Insert((_DWORD)a5, *(_QWORD *)(v5 - 88), 0, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 - 136), 0);
      goto LABEL_481;
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
      goto LABEL_481;
    case 0xA9u:
      updated = sqlite3UpsertNew(*a5, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 - 64), 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_122;
    case 0xAAu:
      v103 = sqlite3DbMallocZero(*a5, 88);
      v104 = 0;
      if ( v103 )
      {
        *(_QWORD *)v103 = 0;
        *(_QWORD *)(v103 + 8) = 0;
        *(_QWORD *)(v103 + 16) = 0;
        *(_QWORD *)(v103 + 24) = 0;
        *(_BYTE *)(v103 + 40) = 0;
        *(_QWORD *)(v103 + 32) = 0;
        v104 = v103;
      }
      *(_QWORD *)(v5 - 88) = v104;
      goto LABEL_481;
    case 0xABu:
      inserted = sqlite3UpsertNew(*a5, 0, 0, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_251;
    case 0xACu:
LABEL_244:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0xB0u:
    case 0xB3u:
    case 0xEEu:
    case 0xF3u:
      v52 = *(_QWORD *)(v5 - 16);
      goto LABEL_141;
    case 0xB1u:
      v52 = sqlite3IdListAppend(a5, *(_QWORD *)(v5 - 40), v5 + 8);
      goto LABEL_141;
    case 0xB2u:
      v79 = sqlite3IdListAppend(a5, 0, v5 + 8);
      goto LABEL_187;
    case 0xB4u:
      v106 = 59;
      goto LABEL_256;
    case 0xB5u:
      v222 = *(_OWORD *)(v5 - 40);
      v107 = tokenExpr(a5, 59, &v222);
      v222 = *(_OWORD *)(v5 + 8);
      tokenExpr(a5, 59, &v222);
      v108 = 141;
      v109 = v107;
      v110 = a5;
      goto LABEL_258;
    case 0xB6u:
      v222 = *(_OWORD *)(v5 - 88);
      v111 = tokenExpr(a5, 59, &v222);
      v222 = *(_OWORD *)(v5 - 40);
      v112 = tokenExpr(a5, 59, &v222);
      v222 = *(_OWORD *)(v5 + 8);
      tokenExpr(a5, 59, &v222);
      sqlite3PExpr(a5, 141, v112);
      if ( *((_BYTE *)a5 + 308) < 2u )
        goto LABEL_266;
      v113 = (_QWORD *)a5[52];
      while ( 2 )
      {
        if ( v113 )
        {
          if ( *v113 != v111 )
          {
            v113 = (_QWORD *)v113[3];
            continue;
          }
          *v113 = 0;
        }
        break;
      }
LABEL_266:
      v114 = v111;
      v115 = 141;
      v116 = a5;
LABEL_267:
      appended = sqlite3PExpr(v116, v115, v114);
LABEL_132:
      *(_QWORD *)(v5 - 88) = appended;
      goto LABEL_481;
    case 0xB7u:
    case 0xB8u:
      v106 = *(unsigned __int16 *)(v5 + 2);
LABEL_256:
      v222 = *(_OWORD *)(v5 + 8);
      v79 = tokenExpr(a5, v106, &v222);
      goto LABEL_187;
    case 0xB9u:
      v117 = (_QWORD *)(v5 + 8);
      v118 = sqlite3ExprAlloc(*a5, 155, v5 + 8);
      if ( v118 )
        *(_DWORD *)(v118 + 52) = *(_DWORD *)v117 - *((_DWORD *)a5 + 86);
      goto LABEL_271;
    case 0xBAu:
      v119 = *(_BYTE **)(v5 + 8);
      if ( *v119 == 35 && (*((_BYTE *)&qword_1800FB500 + (unsigned __int8)v119[1]) & 4) != 0 )
      {
        v221 = *(_OWORD *)(v5 + 8);
        if ( *((_BYTE *)a5 + 30) )
        {
          v120 = sqlite3PExpr(a5, 176, 0);
          *(_QWORD *)(v5 + 8) = v120;
          if ( v120 )
            sqlite3GetInt32(v221 + 1, v120 + 44);
        }
        else
        {
          sqlite3ErrorMsg(a5, "near \"%T\": syntax error", &v221);
          *(_QWORD *)(v5 + 8) = 0;
        }
      }
      else
      {
        v121 = *(_DWORD *)(v5 + 16);
        v222 = *(_OWORD *)(v5 + 8);
        v122 = tokenExpr(a5, 156, &v222);
        *(_QWORD *)(v5 + 8) = v122;
        sqlite3ExprAssignVarNumber(a5, v122, v121);
      }
      goto LABEL_481;
    case 0xBBu:
      v33 = *(_QWORD *)(v5 - 40);
      if ( *(_DWORD *)(v5 + 16) )
      {
        v123 = sqlite3ExprAlloc(*a5, 113, v5 + 8);
        if ( v123 )
        {
          *(_DWORD *)(v123 + 4) |= 0x2200u;
          *(_QWORD *)(v123 + 16) = v33;
          v33 = v123;
        }
      }
LABEL_104:
      *(_QWORD *)(v5 - 40) = v33;
      goto LABEL_481;
    case 0xBCu:
      v124 = sqlite3ExprAlloc(*a5, 36, v5 - 16);
      v125 = *(_QWORD *)(v5 - 64);
      *(_QWORD *)(v5 - 112) = v124;
      sqlite3ExprAttachSubtrees(*a5, v124, v125, 0);
      goto LABEL_481;
    case 0xBDu:
      appended = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 16), v5 - 88, *(unsigned int *)(v5 - 40));
      goto LABEL_132;
    case 0xBEu:
      v126 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 88), v5 - 160, *(unsigned int *)(v5 - 112));
      sqlite3ExprAddFunctionOrderBy(a5, v126, *(_QWORD *)(v5 - 16));
      *(_QWORD *)(v5 - 160) = v126;
      goto LABEL_481;
    case 0xBFu:
      v46 = sqlite3ExprFunction(a5, 0, v5 - 64, 0);
      goto LABEL_129;
    case 0xC0u:
      v127 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 40), v5 - 112, *(unsigned int *)(v5 - 64));
      sqlite3WindowAttach(a5, v127, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 112) = v127;
      goto LABEL_481;
    case 0xC1u:
      v128 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 112), v5 - 184, *(unsigned int *)(v5 - 136));
      sqlite3WindowAttach(a5, v128, *(_QWORD *)(v5 + 8));
      sqlite3ExprAddFunctionOrderBy(a5, v128, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 184) = v128;
      goto LABEL_481;
    case 0xC2u:
      v129 = sqlite3ExprFunction(a5, 0, v5 - 88, 0);
      sqlite3WindowAttach(a5, v129, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v129;
      goto LABEL_481;
    case 0xC3u:
      v79 = sqlite3ExprFunction(a5, 0, v5 + 8, 0);
      goto LABEL_187;
    case 0xC4u:
      v130 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      v131 = sqlite3PExpr(a5, 177, 0);
      *(_QWORD *)(v5 - 88) = v131;
      if ( v131 )
      {
        *(_QWORD *)(v131 + 32) = v130;
        if ( *(_DWORD *)v130 )
          *(_DWORD *)(*(_QWORD *)(v5 - 88) + 4LL) |= *(_DWORD *)(*(_QWORD *)(v130 + 8) + 4LL) & 0x400208;
      }
      else if ( v130 )
      {
        exprListDeleteNN(*a5, v130);
      }
      goto LABEL_481;
    case 0xC5u:
      v52 = sqlite3ExprAnd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_141;
    case 0xC6u:
    case 0xC7u:
    case 0xC8u:
    case 0xC9u:
    case 0xCAu:
    case 0xCBu:
    case 0xCCu:
      v108 = *(unsigned __int16 *)(v5 - 22);
      goto LABEL_297;
    case 0xCDu:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) |= 0x80000000;
      goto LABEL_481;
    case 0xCEu:
      v132 = *(_DWORD *)(v5 - 8);
      v133 = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) = v132 & 0x7FFFFFFF;
      v134 = sqlite3ExprListAppend(a5, 0, v133);
      v135 = sqlite3ExprListAppend(a5, v134, *(_QWORD *)(v5 - 40));
      v136 = sqlite3ExprFunction(a5, v135, v5 - 16, 0);
      *(_QWORD *)(v5 - 40) = v136;
      if ( v132 < 0 )
      {
        v136 = sqlite3PExpr(a5, 19, v136);
        *(_QWORD *)(v5 - 40) = v136;
      }
      goto LABEL_301;
    case 0xCFu:
      v137 = *(_DWORD *)(v5 - 56);
      v138 = *(_QWORD *)(v5 - 40);
      *(_DWORD *)(v5 - 56) = v137 & 0x7FFFFFFF;
      v139 = sqlite3ExprListAppend(a5, 0, v138);
      v140 = sqlite3ExprListAppend(a5, v139, *(_QWORD *)(v5 - 88));
      v141 = sqlite3ExprListAppend(a5, v140, *(_QWORD *)(v5 + 8));
      v136 = sqlite3ExprFunction(a5, v141, v5 - 64, 0);
      *(_QWORD *)(v5 - 88) = v136;
      if ( v137 < 0 )
      {
        v136 = sqlite3PExpr(a5, 19, v136);
        *(_QWORD *)(v5 - 88) = v136;
      }
LABEL_301:
      if ( v136 )
        *(_DWORD *)(v136 + 4) |= 0x100u;
      goto LABEL_481;
    case 0xD0u:
      v88 = *(unsigned __int16 *)(v5 + 2);
      v89 = *(_QWORD *)(v5 - 16);
      goto LABEL_212;
    case 0xD1u:
      v108 = 51;
LABEL_297:
      v109 = *(_QWORD *)(v5 - 40);
      v110 = a5;
LABEL_258:
      v52 = sqlite3PExpr(v110, v108, v109);
      goto LABEL_141;
    case 0xD2u:
      v142 = a5;
      v143 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 40));
      v144 = v143;
      *(_QWORD *)(v5 - 40) = v143;
      goto LABEL_308;
    case 0xD3u:
      v148 = a5;
      v149 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 64));
      v144 = v149;
      *(_QWORD *)(v5 - 64) = v149;
      goto LABEL_317;
    case 0xD4u:
      v142 = a5;
      v143 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 112));
      v144 = v143;
      *(_QWORD *)(v5 - 112) = v143;
LABEL_308:
      if ( !v143 )
        goto LABEL_481;
      v145 = *(_BYTE **)(v5 + 8);
      if ( !v145 || *v145 != 121 || *((_BYTE *)v142 + 308) >= 2u )
        goto LABEL_481;
      v146 = *v142;
      *(_BYTE *)v144 = 50;
      goto LABEL_313;
    case 0xD5u:
      v148 = a5;
      v149 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 88));
      v144 = v149;
      *(_QWORD *)(v5 - 88) = v149;
LABEL_317:
      if ( !v149 )
        goto LABEL_481;
      v150 = *(_BYTE **)(v5 + 8);
      if ( !v150 || *v150 != 121 || *((_BYTE *)v148 + 308) >= 2u )
        goto LABEL_481;
      v146 = *v148;
      *(_BYTE *)v144 = 51;
LABEL_313:
      v147 = *(_QWORD *)(v144 + 24);
      if ( v147 )
        sqlite3ExprDeleteNN(v146, v147);
      *(_QWORD *)(v144 + 24) = 0;
      goto LABEL_481;
    case 0xD6u:
    case 0xD7u:
      v88 = *(unsigned __int16 *)(v5 - 22);
LABEL_211:
      v89 = *(_QWORD *)(v5 + 8);
LABEL_212:
      v87 = sqlite3PExpr(a5, v88, v89);
      goto LABEL_209;
    case 0xD8u:
      v151 = *(unsigned __int8 **)(v5 + 8);
      v152 = *(_BYTE *)(v5 - 22) + 67;
      if ( v151 && *v151 == 0xAD )
        *v151 = v152;
      else
        v151 = (unsigned __int8 *)sqlite3PExpr(a5, v152, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 16) = v151;
      goto LABEL_481;
    case 0xD9u:
      v153 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v154 = sqlite3ExprListAppend(a5, v153, *(_QWORD *)(v5 + 8));
      v52 = sqlite3ExprFunction(a5, v154, v5 - 16, 0);
      goto LABEL_141;
    case 0xDCu:
      v155 = a5;
      v156 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v157 = sqlite3ExprListAppend(a5, v156, *(_QWORD *)(v5 + 8));
      v158 = sqlite3PExpr(a5, 48, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v158;
      if ( v158 )
      {
        *(_QWORD *)(v158 + 32) = v157;
      }
      else if ( v157 )
      {
        exprListDeleteNN(*a5, v157);
      }
      goto LABEL_336;
    case 0xDFu:
      v159 = *(_QWORD *)(v5 - 16);
      if ( v159 )
      {
        v163 = *(_QWORD *)(v159 + 8);
        if ( *(_DWORD *)v159 == 1
          && (unsigned int)exprIsConst(a5, *(_QWORD *)(v159 + 8), 1)
          && (v117 = (_QWORD *)(v5 - 88), **(_BYTE **)(v5 - 88) != 0xB1) )
        {
          *(_QWORD *)(*(_QWORD *)(v5 - 16) + 8LL) = 0;
          v164 = *(_QWORD *)(v5 - 16);
          if ( v164 )
            exprListDeleteNN(*a5, v164);
          sqlite3PExpr(a5, 173, v163);
          *v117 = sqlite3PExpr(a5, 53, *v117);
        }
        else if ( **(_DWORD **)(v5 - 16) == 1 && *(_BYTE *)v163 == 0x8A )
        {
          v117 = (_QWORD *)(v5 - 88);
          v165 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
          *(_QWORD *)(v5 - 88) = v165;
          sqlite3PExprAddSelect(a5, v165, *(_QWORD *)(v163 + 32));
          *(_QWORD *)(v163 + 32) = 0;
          v166 = *(_QWORD *)(v5 - 16);
          if ( v166 )
            exprListDeleteNN(*a5, v166);
        }
        else
        {
          v117 = (_QWORD *)(v5 - 88);
          v167 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
          *(_QWORD *)(v5 - 88) = v167;
          if ( v167 )
          {
            v168 = *(_QWORD *)(v167 + 16);
            if ( *(_BYTE *)v168 == 0xB1 )
            {
              v169 = sqlite3ExprListToValues(a5, **(unsigned int **)(v168 + 32), *(_QWORD *)(v5 - 16));
              v170 = v169;
              if ( v169 )
              {
                parserDoubleLinkSelect(a5, v169);
                sqlite3PExprAddSelect(a5, *v117, v170);
              }
            }
            else
            {
              *(_QWORD *)(v167 + 32) = *(_QWORD *)(v5 - 16);
              sqlite3ExprSetHeightAndFlags(a5, *v117);
            }
          }
          else
          {
            sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
          }
        }
        if ( *(_DWORD *)(v5 - 64) )
        {
          v118 = sqlite3PExpr(a5, 19, *v117);
LABEL_271:
          *v117 = v118;
        }
      }
      else
      {
        v160 = *(_QWORD *)(v5 - 88);
        if ( v160 )
        {
          if ( *((_BYTE *)a5 + 308) >= 2u )
            sqlite3RenameExprUnmap(a5, *(_QWORD *)(v5 - 88));
          sqlite3ExprDeleteNN(*a5, v160);
        }
        v161 = "true";
        if ( !*(_DWORD *)(v5 - 64) )
          v161 = "false";
        v162 = sqlite3Expr(*a5, 117, v161);
        *(_QWORD *)(v5 - 88) = v162;
        if ( v162 )
          sqlite3ExprIdToTrueFalse(v162);
      }
      goto LABEL_481;
    case 0xE0u:
      v171 = sqlite3PExpr(a5, 138, 0);
      *(_QWORD *)(v5 - 40) = v171;
      goto LABEL_366;
    case 0xE1u:
      v155 = a5;
      v172 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
      v173 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 88) = v172;
      sqlite3PExprAddSelect(a5, v172, v173);
      goto LABEL_336;
    case 0xE2u:
      v155 = a5;
      v174 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 - 16);
      v175 = sqlite3SelectNew((_DWORD)a5, 0, v174, 0, 0, 0, 0, 0, 0);
      v176 = v175;
      if ( *(_QWORD *)(v5 + 8) )
        sqlite3SrcListFuncArgs(a5, v174 & -(__int64)(v175 != 0));
      v177 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88));
      *(_QWORD *)(v5 - 88) = v177;
      sqlite3PExprAddSelect(a5, v177, v176);
LABEL_336:
      if ( !*(_DWORD *)(v5 - 64) )
        goto LABEL_481;
      v114 = *(_QWORD *)(v5 - 88);
      v116 = v155;
      v115 = 19;
      goto LABEL_267;
    case 0xE3u:
      v171 = sqlite3PExpr(a5, 20, 0);
      *(_QWORD *)(v5 - 64) = v171;
LABEL_366:
      sqlite3PExprAddSelect(a5, v171, *(_QWORD *)(v5 - 16));
      goto LABEL_481;
    case 0xE4u:
      v178 = sqlite3PExpr(a5, 157, *(_QWORD *)(v5 - 64));
      v179 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 88) = v178;
      if ( v178 )
      {
        v180 = *(_QWORD *)(v5 - 16);
        if ( v180 )
          v179 = sqlite3ExprListAppend(a5, v179, v180);
        *(_QWORD *)(*(_QWORD *)(v5 - 88) + 32LL) = v179;
        sqlite3ExprSetHeightAndFlags(a5, *(_QWORD *)(v5 - 88));
      }
      else
      {
        sqlite3ExprListDeleteGeneric(*a5, v179);
        sqlite3ExprDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
      }
      goto LABEL_481;
    case 0xE5u:
      v181 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      v57 = *(_QWORD *)(v5 + 8);
      v56 = v181;
      v58 = a5;
      *(_QWORD *)(v5 - 88) = v181;
LABEL_146:
      appended = sqlite3ExprListAppend(v58, v56, v57);
      goto LABEL_132;
    case 0xE6u:
      v182 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      v183 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 64) = v182;
      v46 = sqlite3ExprListAppend(a5, v182, v183);
      goto LABEL_129;
    case 0xEBu:
      v50 = *(_QWORD *)(v5 + 8);
      v51 = a5;
LABEL_140:
      v52 = sqlite3ExprListAppend(v51, *(_QWORD *)(v5 - 40), v50);
      goto LABEL_141;
    case 0xECu:
      v79 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_187;
    case 0xEFu:
      v184 = *(_DWORD *)(v5 - 184);
      v185 = *(void **)(v5 + 8);
      v186 = *(_DWORD *)(v5 - 232);
      v187 = *(int **)(v5 - 40);
      v188 = sqlite3SrcListAppend(a5, 0, v5 - 88, 0);
      sqlite3CreateIndex(a5, v5 - 160, v5 - 136, v188, v187, v186, v5 - 256, v185, 0, v184, 0);
      if ( *((_BYTE *)a5 + 308) >= 2u )
      {
        v189 = (_QWORD *)a5[45];
        if ( v189 )
          sqlite3RenameTokenMap(a5, *v189, v5 - 88);
      }
      goto LABEL_481;
    case 0xF4u:
      appended = parserAddExprIdListTerm(
                   (_DWORD)a5,
                   *(_QWORD *)(v5 - 88),
                   (int)v5 - 40,
                   *(_DWORD *)(v5 - 16),
                   *(_DWORD *)(v5 + 8));
      goto LABEL_132;
    case 0xF5u:
      v52 = parserAddExprIdListTerm((_DWORD)a5, 0, (int)v5 - 40, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_141;
    case 0xF8u:
      sqlite3DropIndex(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_481;
    case 0xF9u:
      v190 = 0;
      goto LABEL_389;
    case 0xFAu:
      v190 = v5 - 16;
LABEL_389:
      sqlite3Vacuum(a5, v190, *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0xFDu:
      v191 = (const char **)(v5 + 8);
      v192 = 0;
      v193 = v5 - 16;
      goto LABEL_392;
    case 0xFEu:
      v192 = v5 + 8;
      v191 = (const char **)(v5 - 40);
      v193 = v5 - 64;
      goto LABEL_392;
    case 0xFFu:
      v192 = v5 - 16;
      v191 = (const char **)(v5 - 64);
      v193 = v5 - 88;
LABEL_392:
      sqlite3Pragma(a5, v193, v191, v192, 0);
      goto LABEL_481;
    case 0x100u:
      v194 = v5 + 8;
      v195 = (const char **)(v5 - 40);
      v196 = v5 - 64;
      goto LABEL_397;
    case 0x101u:
      v194 = v5 - 16;
      v195 = (const char **)(v5 - 64);
      v196 = v5 - 88;
LABEL_397:
      sqlite3Pragma(a5, v196, v195, v194, 1);
      goto LABEL_481;
    case 0x104u:
      v197 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)&v221 = *(_QWORD *)(v5 - 64);
      *((_QWORD *)&v221 + 1) = (unsigned int)(*(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64));
      sqlite3FinishTrigger(a5, v197, &v221);
      goto LABEL_481;
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
      goto LABEL_481;
    case 0x107u:
      *(_DWORD *)(v5 - 16) = 65;
      goto LABEL_481;
    case 0x108u:
      *(_DWORD *)(v5 + 32) = 33;
      goto LABEL_481;
    case 0x109u:
    case 0x10Au:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 + 16) = 0;
      goto LABEL_481;
    case 0x10Bu:
      *(_QWORD *)(v5 - 32) = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 40) = 129;
      goto LABEL_481;
    case 0x10Eu:
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) + 80LL) = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_481;
    case 0x10Fu:
      *(_QWORD *)(*(_QWORD *)(v5 - 16) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_481;
    case 0x110u:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      sqlite3ErrorMsg(
        a5,
        "qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers");
      goto LABEL_481;
    case 0x111u:
      sqlite3ErrorMsg(a5, "the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_481;
    case 0x112u:
      sqlite3ErrorMsg(a5, "the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_481;
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
LABEL_122:
      *(_QWORD *)(v5 - 184) = updated;
      goto LABEL_481;
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
LABEL_251:
      *(_QWORD *)(v5 - 160) = inserted;
      goto LABEL_481;
    case 0x115u:
      v62 = sqlite3TriggerDeleteStep(
              (_DWORD)a5,
              (int)v5 - 64,
              *(_QWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 + 8));
      goto LABEL_156;
    case 0x116u:
      v52 = sqlite3TriggerSelectStep(*a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_141;
    case 0x117u:
      v198 = sqlite3PExpr(a5, 71, 0);
      *(_QWORD *)(v5 - 64) = v198;
      if ( v198 )
        *(_BYTE *)(v198 + 1) = 4;
      goto LABEL_481;
    case 0x118u:
      v199 = sqlite3ExprAlloc(*a5, 71, v5 - 16);
      *(_QWORD *)(v5 - 112) = v199;
      if ( v199 )
        *(_BYTE *)(v199 + 1) = *(_BYTE *)(v5 - 64);
      goto LABEL_481;
    case 0x11Bu:
      *(_DWORD *)(v5 + 8) = 3;
      goto LABEL_481;
    case 0x11Cu:
      sqlite3DropTrigger(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_481;
    case 0x11Du:
      sqlite3Attach(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0x11Eu:
      sqlite3Detach(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0x121u:
      v200 = 0;
      v201 = 0;
      goto LABEL_424;
    case 0x122u:
      v200 = v5 + 8;
      v201 = v5 - 16;
LABEL_424:
      sqlite3Reindex(a5, v201, v200);
      goto LABEL_481;
    case 0x123u:
      v202 = 0;
      v203 = 0;
      goto LABEL_427;
    case 0x124u:
      v202 = v5 + 8;
      v203 = v5 - 16;
LABEL_427:
      sqlite3Analyze(a5, v203, v202);
      goto LABEL_481;
    case 0x125u:
      sqlite3AlterRenameTable(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_481;
    case 0x126u:
      *(_DWORD *)(v5 - 8) = *((_DWORD *)a5 + 72) + *((_DWORD *)a5 + 74) - *(_DWORD *)(v5 - 16);
      sqlite3AlterFinishAddColumn();
      goto LABEL_481;
    case 0x127u:
      sqlite3AlterDropColumn(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_481;
    case 0x128u:
      disableLookaside(a5);
      sqlite3AlterBeginAddColumn(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_481;
    case 0x129u:
      sqlite3AlterRenameColumn(a5, *(_QWORD *)(v5 - 112), v5 - 40, (unsigned __int8 **)(v5 + 8));
      goto LABEL_481;
    case 0x12Au:
      v204 = 0;
      goto LABEL_435;
    case 0x12Bu:
      v204 = v5 + 8;
LABEL_435:
      sqlite3VtabFinishParse(a5, v204);
      goto LABEL_481;
    case 0x12Cu:
      sqlite3VtabBeginParse((_DWORD)a5, v5 - 64, v5 - 40, v5 + 8, *(_DWORD *)(v5 - 88));
      goto LABEL_481;
    case 0x12Du:
      sqlite3VtabArgInit(a5);
      goto LABEL_481;
    case 0x12Eu:
    case 0x12Fu:
    case 0x130u:
      sqlite3VtabArgExtend(a5, v5 + 8);
      goto LABEL_481;
    case 0x131u:
    case 0x132u:
      LOBYTE(a3) = 1;
      sqlite3WithPush(a5, *(_QWORD *)(v5 + 8), a3);
      goto LABEL_481;
    case 0x133u:
      *(_BYTE *)(v5 + 8) = 1;
      goto LABEL_481;
    case 0x134u:
      *(_BYTE *)(v5 - 16) = 0;
      goto LABEL_481;
    case 0x135u:
      *(_BYTE *)(v5 - 40) = 2;
      goto LABEL_481;
    case 0x136u:
      v62 = sqlite3CteNew((_DWORD)a5, (int)v5 - 112, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16), *(_BYTE *)(v5 - 64));
      goto LABEL_156;
    case 0x137u:
      *((_BYTE *)a5 + 39) = 1;
      goto LABEL_481;
    case 0x138u:
      v79 = sqlite3WithAdd(a5, 0, *(_QWORD *)(v5 + 8));
LABEL_187:
      *(_QWORD *)(v5 + 8) = v79;
      goto LABEL_481;
    case 0x139u:
      v52 = sqlite3WithAdd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_141;
    case 0x13Au:
      sqlite3WindowChain(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 64LL) = *(_QWORD *)(v5 - 40);
LABEL_449:
      v52 = *(_QWORD *)(v5 + 8);
      goto LABEL_141;
    case 0x13Bu:
      v205 = *(_QWORD **)(v5 - 16);
      if ( v205 )
        *v205 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 - 88), *(unsigned int *)(v5 - 80));
      goto LABEL_452;
    case 0x13Cu:
      appended = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_132;
    case 0x13Du:
      v206 = *(_QWORD *)(v5 - 16);
      v117 = (_QWORD *)(v5 - 112);
      v207 = *(_QWORD *)(v5 - 40);
      goto LABEL_455;
    case 0x13Eu:
      v46 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), 0, *(_QWORD *)(v5 - 16), 0);
      goto LABEL_129;
    case 0x13Fu:
      v206 = *(_QWORD *)(v5 - 16);
      v117 = (_QWORD *)(v5 - 88);
      goto LABEL_458;
    case 0x140u:
      v117 = (_QWORD *)(v5 - 16);
      LODWORD(v206) = 0;
LABEL_458:
      LODWORD(v207) = 0;
LABEL_455:
      v118 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), v207, v206, (__int64)v117);
      goto LABEL_271;
    case 0x141u:
      v14 = sqlite3WindowAlloc((_DWORD)a5, 0, 90, 0, 85, 0, 0);
LABEL_40:
      *(_QWORD *)(v5 + 32) = v14;
      goto LABEL_481;
    case 0x142u:
      v52 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 40),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              85,
              0,
              *(_BYTE *)(v5 + 8));
LABEL_141:
      *(_QWORD *)(v5 - 40) = v52;
      goto LABEL_481;
    case 0x143u:
      v62 = sqlite3WindowAlloc(
              (_DWORD)a5,
              *(_DWORD *)(v5 - 112),
              *(_DWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 56),
              *(_DWORD *)(v5 - 16),
              *(_QWORD *)(v5 - 8),
              *(_BYTE *)(v5 + 8));
      goto LABEL_156;
    case 0x146u:
    case 0x148u:
    case 0x14Au:
      LODWORD(v221) = *(unsigned __int16 *)(v5 - 22);
      v84 = v221;
LABEL_199:
      *(_QWORD *)(v5 - 16) = v84;
      *(_QWORD *)(v5 - 8) = 0;
      goto LABEL_481;
    case 0x149u:
      v208 = *(_QWORD *)(v5 - 16);
      LODWORD(v221) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 - 16) = v221;
      *(_QWORD *)(v5 - 8) = v208;
      goto LABEL_481;
    case 0x14Bu:
      *(_BYTE *)(v5 + 32) = 0;
      goto LABEL_481;
    case 0x14Cu:
      v209 = *(_BYTE *)(v5 + 8);
      goto LABEL_467;
    case 0x14Du:
    case 0x14Eu:
      v209 = *(_BYTE *)(v5 - 22);
LABEL_467:
      *(_BYTE *)(v5 - 16) = v209;
      goto LABEL_481;
    case 0x14Fu:
      *(_BYTE *)(v5 + 8) = *(_BYTE *)(v5 + 2);
      goto LABEL_481;
    case 0x151u:
      v210 = *(_QWORD *)(v5 + 8);
      v211 = *(_QWORD *)(v5 - 16);
      if ( v210 )
        *(_QWORD *)(v210 + 72) = v211;
      else
        sqlite3ExprDeleteGeneric(*a5, v211);
LABEL_208:
      v87 = *(_QWORD *)(v5 + 8);
LABEL_209:
      *(_QWORD *)(v5 - 16) = v87;
      goto LABEL_481;
    case 0x153u:
      v212 = sqlite3DbMallocZero(*a5, 144);
      v213 = v212;
      if ( v212 )
      {
        *(_BYTE *)(v212 + 32) = -90;
        *(_QWORD *)(v212 + 72) = *(_QWORD *)(v5 + 8);
      }
      else
      {
        sqlite3ExprDeleteGeneric(*a5, *(_QWORD *)(v5 + 8));
      }
      goto LABEL_480;
    case 0x154u:
      v46 = *(_QWORD *)(v5 - 16);
LABEL_129:
      *(_QWORD *)(v5 - 64) = v46;
      goto LABEL_481;
    case 0x155u:
      v214 = sqlite3DbMallocZero(*a5, 144);
      *(_QWORD *)(v5 - 16) = v214;
      v117 = (_QWORD *)v214;
      if ( !v214 )
        goto LABEL_481;
      v118 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 + 16));
      goto LABEL_271;
    case 0x156u:
LABEL_452:
      appended = *(_QWORD *)(v5 - 16);
      goto LABEL_132;
    case 0x157u:
      v215 = *(unsigned __int16 *)(v5 + 2);
      v222 = *(_OWORD *)(v5 + 8);
      v213 = tokenExpr(a5, v215, &v222);
      sqlite3DequoteNumber(a5, v213);
LABEL_480:
      *(_QWORD *)(v5 + 8) = v213;
      goto LABEL_481;
    default:
      goto LABEL_481;
  }
}

```

## disassembly

```asm
0x1800c3bd8  mov     rax, rsp
0x1800c3bdb  mov     [rax+18h], rbx
0x1800c3bdf  mov     [rax+10h], edx
0x1800c3be2  mov     [rax+8], rcx
0x1800c3be6  push    rbp
0x1800c3be7  push    rsi
0x1800c3be8  push    rdi
0x1800c3be9  push    r12
0x1800c3beb  push    r13
0x1800c3bed  push    r14
0x1800c3bef  push    r15
0x1800c3bf1  lea     rbp, [rax-57h]
0x1800c3bf5  sub     rsp, 0B0h
0x1800c3bfc  mov     r12, [rcx]
0x1800c3bff  lea     rcx, cs:180000000h
0x1800c3c06  cmp     edx, 157h; switch 344 cases
0x1800c3c0c  ja      def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c12  mov     eax, edx
0x1800c3c14  mov     r8d, ds:(jpt_1800C3C1F - 180000000h)[rcx+rax*4]
0x1800c3c1c  add     r8, rcx
0x1800c3c1f  jmp     r8; switch jump
0x1800c3c22  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F case 0
0x1800c3c26  xor     r13d, r13d
0x1800c3c29  cmp     [rax+150h], r13
0x1800c3c30  jnz     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c36  mov     byte ptr [rax+133h], 1
0x1800c3c3d  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c42  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F case 1
0x1800c3c46  xor     r13d, r13d
0x1800c3c49  cmp     [rax+150h], r13
0x1800c3c50  jnz     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c56  mov     byte ptr [rax+133h], 2
0x1800c3c5d  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c62  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F case 2
0x1800c3c66  call    sqlite3FinishCoding
0x1800c3c6b  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c70  mov     edx, [r12-10h]; jumptable 00000001800C3C1F case 3
0x1800c3c75  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3c79  call    sqlite3BeginTransaction
0x1800c3c7e  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c83  mov     dword ptr [r12+20h], 7; jumptable 00000001800C3C1F case 4
0x1800c3c8c  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3c91  movzx   eax, word ptr [r12+2]; jumptable 00000001800C3C1F cases 5-7,89,91,262,324
0x1800c3c97  mov     [r12+8], eax
0x1800c3c9c  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3ca1  movzx   edx, word ptr [r12-16h]; jumptable 00000001800C3C1F cases 8,9
0x1800c3ca7  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3cab  call    sqlite3EndTransaction
0x1800c3cb0  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3cb5  xor     edx, edx; jumptable 00000001800C3C1F case 10
0x1800c3cb7  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3cbb  lea     r8, [r12+8]
0x1800c3cc0  call    sqlite3Savepoint
0x1800c3cc5  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3cca  mov     edx, 1; jumptable 00000001800C3C1F case 11
0x1800c3ccf  jmp     short loc_1800C3CB7
0x1800c3cd1  mov     edx, 2; jumptable 00000001800C3C1F case 12
0x1800c3cd6  jmp     short loc_1800C3CB7
0x1800c3cd8  mov     eax, [r12-28h]; jumptable 00000001800C3C1F case 13
0x1800c3cdd  lea     r8, [r12+8]
0x1800c3ce2  mov     r9d, [r12-58h]
0x1800c3ce7  lea     rdx, [r12-10h]
0x1800c3cec  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3cf0  xor     r13d, r13d
0x1800c3cf3  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1800c3cf7  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x1800c3cfc  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x1800c3d01  call    sqlite3StartTable
0x1800c3d06  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3d0b  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F case 14
0x1800c3d0f  inc     byte ptr [rax+24h]
0x1800c3d12  mov     rcx, [rax]
0x1800c3d15  inc     dword ptr [rcx+1A0h]
0x1800c3d1b  xor     r13d, r13d
0x1800c3d1e  mov     [rcx+1A4h], r13w
0x1800c3d26  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3d2b  mov     dword ptr [r12-28h], 1; jumptable 00000001800C3C1F case 16
0x1800c3d34  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3d39  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F case 17
0x1800c3d3d  xor     r13d, r13d
0x1800c3d40  mov     rcx, [rax]
0x1800c3d43  cmp     [rcx+0C5h], r13b
0x1800c3d4a  setz    r13b
0x1800c3d4e  mov     [r12+8], r13d
0x1800c3d53  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3d58  mov     r9d, [r12+8]; jumptable 00000001800C3C1F case 19
0x1800c3d5d  lea     r8, [r12-10h]
0x1800c3d62  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3d66  lea     rdx, [r12-28h]
0x1800c3d6b  xor     r13d, r13d
0x1800c3d6e  mov     [rsp+0E0h+var_C0], r13
0x1800c3d73  call    sqlite3EndTable
0x1800c3d78  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3d7d  mov     rax, [r12+8]; jumptable 00000001800C3C1F case 20
0x1800c3d82  xor     r9d, r9d
0x1800c3d85  mov     rbx, [rbp+4Fh+arg_20]
0x1800c3d89  xor     r8d, r8d
0x1800c3d8c  mov     rcx, rbx
0x1800c3d8f  mov     [rsp+0E0h+var_C0], rax
0x1800c3d94  xor     edx, edx
0x1800c3d96  call    sqlite3EndTable
0x1800c3d9b  mov     rdx, [r12+8]
0x1800c3da0  test    rdx, rdx
0x1800c3da3  jz      def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3da9  mov     rcx, [rbx]
0x1800c3dac  mov     r8d, 1
0x1800c3db2  call    clearSelect
0x1800c3db7  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3dbc  mov     eax, [r12+8]; jumptable 00000001800C3C1F case 22
0x1800c3dc1  or      [r12-28h], eax
0x1800c3dc6  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3dcb  xor     r13d, r13d; jumptable 00000001800C3C1F case 23
0x1800c3dce  cmp     dword ptr [r12+10h], 5
0x1800c3dd4  jnz     short loc_1800C3DFD
0x1800c3dd6  mov     rcx, [r12+8]
0x1800c3ddb  lea     r8d, [r13+5]
0x1800c3ddf  lea     rdx, aRowid_1; "rowid"
0x1800c3de6  call    sqlite3_strnicmp
0x1800c3deb  test    eax, eax
0x1800c3ded  jnz     short loc_1800C3DFD
0x1800c3def  mov     dword ptr [r12-10h], 280h
0x1800c3df8  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3dfd  mov     r9, [r12+8]
0x1800c3e02  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x1800c3e09  mov     r8d, [r12+10h]
0x1800c3e0e  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3e12  mov     [r12-10h], r13d
0x1800c3e17  call    sqlite3ErrorMsg
0x1800c3e1c  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3e21  xor     r13d, r13d; jumptable 00000001800C3C1F case 24
0x1800c3e24  lea     r8d, [r13+6]
0x1800c3e28  cmp     [r12+10h], r8d
0x1800c3e2d  jnz     short loc_1800C3E4F
0x1800c3e2f  mov     rcx, [r12+8]
0x1800c3e34  lea     rdx, aStrict; "strict"
0x1800c3e3b  call    sqlite3_strnicmp
0x1800c3e40  test    eax, eax
0x1800c3e42  jnz     short loc_1800C3E4F
0x1800c3e44  mov     r13d, 10000h
0x1800c3e4a  jmp     loc_1800C3D4E
0x1800c3e4f  mov     r9, [r12+8]
0x1800c3e54  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x1800c3e5b  mov     r8d, [r12+10h]
0x1800c3e60  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3e64  call    sqlite3ErrorMsg
0x1800c3e69  jmp     loc_1800C3D4E
0x1800c3e6e  movups  xmm0, xmmword ptr [r12+8]; jumptable 00000001800C3C1F case 25
0x1800c3e74  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3e78  lea     r8, [rbp+4Fh+var_80]
0x1800c3e7c  movups  xmm1, xmmword ptr [r12-10h]
0x1800c3e82  lea     rdx, [rbp+4Fh+var_70]
0x1800c3e86  movdqu  [rbp+4Fh+var_80], xmm0
0x1800c3e8b  movdqu  [rbp+4Fh+var_70], xmm1
0x1800c3e90  call    sqlite3AddColumn
0x1800c3e95  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3e9a  xor     r13d, r13d; jumptable 00000001800C3C1F cases 26,65,106
0x1800c3e9d  mov     [r12+28h], r13d
0x1800c3ea2  mov     [r12+20h], r13
0x1800c3ea7  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3eac  mov     eax, [r12+10h]; jumptable 00000001800C3C1F case 27
0x1800c3eb1  sub     eax, [r12-40h]
0x1800c3eb6  add     eax, [r12+8]
0x1800c3ebb  mov     [r12-38h], eax
0x1800c3ec0  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3ec5  mov     eax, [r12+10h]; jumptable 00000001800C3C1F case 28
0x1800c3eca  sub     eax, [r12-70h]
0x1800c3ecf  add     eax, [r12+8]
0x1800c3ed4  mov     [r12-68h], eax
0x1800c3ed9  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3ede  mov     eax, [r12+10h]; jumptable 00000001800C3C1F case 29
0x1800c3ee3  sub     eax, [r12-10h]
0x1800c3ee8  add     eax, [r12+8]
0x1800c3eed  mov     [r12-8], eax
0x1800c3ef2  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3ef7  mov     rax, [r9]; jumptable 00000001800C3C1F case 30
0x1800c3efa  mov     [r12+20h], rax
0x1800c3eff  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3f04  movups  xmm0, xmmword ptr [r9]; jumptable 00000001800C3C1F case 31
0x1800c3f08  movdqu  xmmword ptr [r12+20h], xmm0
0x1800c3f0f  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3f14  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F cases 32,67
0x1800c3f18  movups  xmm0, xmmword ptr [r12+8]
0x1800c3f1e  movdqu  xmmword ptr [rax+70h], xmm0
0x1800c3f23  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3f28  mov     r8, [r12-10h]; jumptable 00000001800C3C1F case 33
0x1800c3f2d  mov     r9d, [r12-8]
0x1800c3f32  add     r9, r8
0x1800c3f35  mov     rdx, [r12+8]
0x1800c3f3a  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3f3e  call    sqlite3AddDefaultValue
0x1800c3f43  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3f48  mov     r8, [r12-28h]; jumptable 00000001800C3C1F case 34
0x1800c3f4d  mov     r9, [r12+8]
0x1800c3f52  inc     r8
0x1800c3f55  mov     rdx, [r12-10h]
0x1800c3f5a  jmp     short loc_1800C3F3A
0x1800c3f5c  mov     r9d, [r12-8]; jumptable 00000001800C3C1F case 35
0x1800c3f61  add     r9, [r12-10h]
0x1800c3f66  mov     r8, [r12-28h]
0x1800c3f6b  jmp     short loc_1800C3F35
0x1800c3f6d  mov     r8, [r12+8]; jumptable 00000001800C3C1F case 36
0x1800c3f72  xor     r9d, r9d
0x1800c3f75  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3f79  mov     edx, 0AEh
0x1800c3f7e  call    sqlite3PExpr
0x1800c3f83  mov     r9d, [r12-8]
0x1800c3f88  mov     rdx, rax
0x1800c3f8b  add     r9, [r12-10h]
0x1800c3f90  mov     r8, [r12-28h]
0x1800c3f95  jmp     short loc_1800C3F3A
0x1800c3f97  movups  xmm0, xmmword ptr [r12+8]; jumptable 00000001800C3C1F case 37
0x1800c3f9d  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3fa1  lea     r8, [rbp+4Fh+var_70]
0x1800c3fa5  mov     edx, 75h ; 'u'
0x1800c3faa  movdqu  [rbp+4Fh+var_70], xmm0
0x1800c3faf  call    tokenExpr
0x1800c3fb4  mov     rbx, rax
0x1800c3fb7  test    rax, rax
0x1800c3fba  jz      short loc_1800C3FC4
0x1800c3fbc  mov     rcx, rax
0x1800c3fbf  call    sqlite3ExprIdToTrueFalse
0x1800c3fc4  mov     r8, [r12+8]
0x1800c3fc9  mov     rdx, rbx
0x1800c3fcc  mov     r9d, [r12+10h]
0x1800c3fd1  add     r9, r8
0x1800c3fd4  jmp     loc_1800C3F3A
0x1800c3fd9  mov     edx, [r12+8]; jumptable 00000001800C3C1F case 38
0x1800c3fde  mov     rcx, [rbp+4Fh+arg_20]
0x1800c3fe2  call    sqlite3AddNotNull
0x1800c3fe7  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c3fec  mov     eax, [r12-28h]; jumptable 00000001800C3C1F case 39
0x1800c3ff1  xor     edx, edx
0x1800c3ff3  mov     r9d, [r12+8]
0x1800c3ff8  mov     r8d, [r12-10h]
0x1800c3ffd  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800c4001  mov     rcx, [rbp+4Fh+arg_20]
0x1800c4005  call    sqlite3AddPrimaryKey
0x1800c400a  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c400f  mov     eax, [r12+8]; jumptable 00000001800C3C1F case 40
0x1800c4014  xor     r13d, r13d
0x1800c4017  mov     byte ptr [rsp+50h], 1
0x1800c401c  mov     dword ptr [rsp+0E0h+var_98], r13d
0x1800c4021  mov     [rsp+0E0h+var_A0], r13d
0x1800c4026  mov     [rsp+0E0h+var_A8], r13
0x1800c402b  mov     [rsp+0E0h+var_B0], r13
0x1800c4030  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800c4034  mov     [rsp+0E0h+var_C0], r13
0x1800c4039  mov     rcx, [rbp+4Fh+arg_20]
0x1800c403d  xor     r9d, r9d
0x1800c4040  xor     r8d, r8d
0x1800c4043  xor     edx, edx
0x1800c4045  call    sqlite3CreateIndex
0x1800c404a  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c404f  mov     r9, [r12+8]; jumptable 00000001800C3C1F case 41
0x1800c4054  mov     r8, [r12-28h]
0x1800c4059  mov     rdx, [r12-10h]
0x1800c405e  mov     rcx, [rbp+4Fh+arg_20]
0x1800c4062  call    sqlite3AddCheckConstraint
0x1800c4067  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c406c  mov     eax, [r12+8]; jumptable 00000001800C3C1F case 42
0x1800c4071  lea     r8, [r12-28h]
0x1800c4076  mov     r9, [r12-10h]
0x1800c407b  xor     edx, edx
0x1800c407d  mov     rcx, [rbp+4Fh+arg_20]
0x1800c4081  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800c4085  call    sqlite3CreateForeignKey
0x1800c408a  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c408f  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F case 43
0x1800c4093  xor     r13d, r13d
0x1800c4096  mov     rcx, [rax+160h]
0x1800c409d  test    rcx, rcx
0x1800c40a0  jz      def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c40a6  cmp     [rcx+3Fh], r13b
0x1800c40aa  jnz     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c40b0  mov     rdx, [rcx+48h]
0x1800c40b4  test    rdx, rdx
0x1800c40b7  jz      def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c40bd  mov     al, [r12+8]
0x1800c40c2  mov     [rdx+2Ch], al
0x1800c40c5  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c40ca  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001800C3C1F case 44
0x1800c40ce  lea     rdx, [r12+8]
0x1800c40d3  call    sqlite3AddCollateType
0x1800c40d8  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c40dd  mov     rdx, [r12-10h]; jumptable 00000001800C3C1F case 45
0x1800c40e2  xor     r8d, r8d
0x1800c40e5  mov     rcx, [rbp+4Fh+arg_20]
0x1800c40e9  call    sqlite3AddGenerated
0x1800c40ee  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c40f3  mov     rdx, [r12-28h]; jumptable 00000001800C3C1F case 46
0x1800c40f8  lea     r8, [r12+8]
0x1800c40fd  jmp     short loc_1800C40E5
0x1800c40ff  mov     dword ptr [r12+8], 1; jumptable 00000001800C3C1F cases 48,98,124,139,281
0x1800c4108  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c410d  xor     r13d, r13d; jumptable 00000001800C3C1F cases 15,18,21,47,49,62,72,81,100,241,246
0x1800c4110  mov     [r12+20h], r13d
0x1800c4115  jmp     def_1800C3C1F; jumptable 00000001800C3C1F default case, cases 325,327,338
0x1800c411a  mov     eax, [r12+0Ch]; jumptable 00000001800C3C1F case 50
0x1800c411f  not     eax
0x1800c4121  and     eax, [r12-10h]
  ... truncated ...
```

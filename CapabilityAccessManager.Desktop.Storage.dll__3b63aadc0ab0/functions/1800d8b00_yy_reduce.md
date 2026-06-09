# yy_reduce

- ea: `0x1800d8b00`
- end: `0x1800dcf60`
- name: `yy_reduce`
- size: `17504`
- prototype: ``
- caller_count: `1`
- callee_count: `104`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18008bf60`

## callees

- `0x180005980`
- `0x180023bf0`
- `0x180023c80`
- `0x18002dce0`
- `0x18002ea80`
- `0x1800349e0`
- `0x180039a90`
- `0x18003a790`
- `0x180044640`
- `0x18004dba0`
- `0x180056870`
- `0x180056930`
- `0x180061cf0`
- `0x180061e50`
- `0x1800626b0`
- `0x180062900`
- `0x180062b80`
- `0x180062ea0`
- `0x1800631a0`
- `0x1800634a0`
- `0x180063bb0`
- `0x180064160`
- `0x180064610`
- `0x180064ce0`
- `0x1800658d0`
- `0x180065d80`
- `0x180065f70`
- `0x18006da60`
- `0x18006f3f0`
- `0x18006fc70`
- `0x180070f50`
- `0x180071400`
- `0x180071650`
- `0x180071700`
- `0x180071a90`
- `0x180072e80`
- `0x1800730c0`
- `0x180073370`
- `0x180073670`
- `0x180073a20`
- `0x1800743d0`
- `0x180074990`
- `0x180074b50`
- `0x180074c80`
- `0x180074ed0`
- `0x1800750d0`
- `0x1800795a0`
- `0x1800797e0`
- `0x1800798a0`
- `0x18007a2f0`

## string_xrefs

- `0x1800d8bc0`: `ROLLBACK`
- `0x1800d8bc9`: `COMMIT`
- `0x1800dbf93`: `qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers`
- `0x1800dbfac`: `the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers`
- `0x1800dbfc1`: `the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers`

## pseudocode

```c
__int64 __fastcall yy_reduce(__int64 *a1, unsigned int a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  __int64 v5; // rbx
  const char *v6; // r8
  unsigned int v7; // r14d
  __int64 v8; // r10
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdi
  int v14; // r10d
  unsigned __int8 *v15; // r8
  int v16; // edx
  const char *v17; // r9
  __int64 v18; // rcx
  const char *v19; // r9
  int v20; // r10d
  unsigned __int8 *v21; // r8
  int v22; // edx
  const char *v23; // r9
  __int64 v24; // rcx
  __int128 v25; // xmm1
  __int64 v26; // r14
  __int64 v27; // rdi
  int v28; // r15d
  int v29; // eax
  int v30; // r8d
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 i; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r15
  _QWORD *v40; // rdi
  __int64 v41; // r12
  __int64 v42; // rax
  _QWORD *v43; // r14
  int v44; // r13d
  __int64 v45; // r12
  __int64 j; // rdx
  __int64 v47; // rax
  __int16 v48; // cx
  _BYTE *v49; // rcx
  _BYTE *k; // rax
  __int64 v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdi
  __int64 v56; // rdx
  __int64 v57; // rdi
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdi
  __int64 v61; // r14
  __int64 v62; // rdx
  int v63; // eax
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rdi
  __int64 v67; // rax
  int *appended; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  int v71; // r8d
  __int64 v72; // rax
  bool v73; // zf
  int *v74; // rcx
  int *v75; // rdi
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // r8
  int *v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rdi
  int v84; // r15d
  int v85; // r8d
  __int64 v86; // r13
  __int64 v87; // r14
  int v88; // eax
  int v89; // r8d
  int *v90; // rcx
  __int64 v91; // rax
  __int64 v92; // rax
  int *v93; // rdx
  __int64 v94; // rax
  _QWORD *v95; // r14
  unsigned int *v96; // rsi
  __int64 v97; // r12
  const char *v98; // r8
  __int64 v99; // rax
  int *v100; // rdi
  _QWORD *v101; // r15
  __int64 v102; // rcx
  __int64 v103; // rsi
  int *v104; // r13
  __int64 v105; // rcx
  __int64 v106; // r8
  int *v107; // r13
  __int64 v108; // rdx
  _QWORD *v109; // r12
  unsigned int *v110; // rsi
  __int64 v111; // rdi
  const char *v112; // r8
  int *v113; // r14
  __int64 v114; // rax
  _QWORD *v115; // r15
  __int64 v116; // rcx
  __int64 v117; // rsi
  int *v118; // r13
  __int64 v119; // rcx
  __int64 v120; // r8
  int *v121; // r13
  __int64 v122; // rdx
  _QWORD *v123; // rdx
  int v124; // r8d
  int *v125; // rdi
  __int64 v126; // rax
  _QWORD *v127; // r14
  _QWORD *v128; // r12
  unsigned int *v129; // rsi
  __int64 v130; // rdi
  const char *v131; // r8
  int *v132; // r14
  __int64 v133; // rax
  _QWORD *v134; // r15
  __int64 v135; // rcx
  __int64 v136; // rsi
  int *v137; // r13
  __int64 v138; // rcx
  __int64 v139; // r8
  int *v140; // r13
  __int64 v141; // rdx
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // rax
  __int64 v145; // r10
  _DWORD *v146; // rdx
  int *v147; // rax
  __int64 v148; // rdx
  int *v149; // r8
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rdi
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  int *v158; // rax
  int v159; // esi
  int v160; // r8d
  __int64 v161; // rcx
  int *v162; // rax
  int v163; // esi
  int v164; // r8d
  __int64 v165; // rcx
  __int64 v166; // r9
  __int64 v167; // r8
  _DWORD *v168; // rdx
  int *v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rsi
  __int64 v173; // r13
  __int64 v174; // r14
  __int64 v175; // r12
  __int64 v176; // r15
  __int64 v177; // rdi
  __int64 v178; // rax
  __int64 v179; // r14
  __int64 v180; // r15
  __int64 v181; // rsi
  __int64 v182; // rdi
  __int64 v183; // rax
  __int64 v184; // r15
  __int64 v185; // r14
  __int64 v186; // rdi
  __int64 v187; // rax
  __int64 v188; // rdi
  __int64 v189; // rax
  __int64 v190; // r14
  __int64 v191; // rdi
  __int64 v192; // rax
  __int64 v193; // r9
  __int64 v194; // rdx
  __int64 v195; // rax
  _BYTE *v196; // rax
  __int64 v197; // rax
  unsigned int v198; // esi
  __int64 v199; // rax
  _QWORD *v200; // rdi
  __int64 v201; // rax
  __int64 v202; // rdx
  __int64 v203; // r8
  int v204; // eax
  __int64 v205; // rax
  __int64 v206; // rdx
  __int64 v207; // rdi
  __int64 v208; // rax
  __int64 v209; // rdx
  __int64 v210; // rdi
  __int64 v211; // rdi
  __int64 v212; // rax
  __int64 v213; // r15
  __int64 v214; // r14
  __int16 v215; // si
  int v216; // r15d
  int v217; // eax
  int v218; // r8d
  int v219; // edi
  __int64 v220; // rdx
  __int64 v221; // rax
  __int64 v222; // rax
  __int64 v223; // rax
  int v224; // edi
  __int64 v225; // rdx
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 v228; // rax
  _QWORD *v229; // rsi
  __int64 v230; // rax
  __int64 v231; // rdi
  _QWORD *v232; // rsi
  __int64 v233; // rax
  _BYTE *v234; // rax
  __int64 v235; // rcx
  _BYTE *v236; // rax
  __int64 v237; // rdx
  __int64 v238; // r14
  __int16 v239; // si
  __int64 v240; // rdi
  int v241; // r15d
  int v242; // eax
  int v243; // r8d
  __int64 v244; // rax
  __int64 v245; // rax
  _QWORD *v246; // rdi
  __int64 v247; // rax
  __int64 v248; // rsi
  __int64 v249; // rax
  __int64 v250; // rax
  const char *v251; // r8
  __int64 v252; // rax
  __int64 v253; // r14
  _QWORD *v254; // r13
  _QWORD *v255; // rdi
  __int64 v256; // rdx
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // rdx
  __int64 v260; // rax
  __int64 v261; // rcx
  __int64 v262; // rdx
  __int64 v263; // rax
  int *v264; // rax
  int *v265; // rcx
  __int64 v266; // r12
  int v267; // edx
  int v268; // eax
  _BYTE *v269; // rcx
  _DWORD **v270; // r14
  int v271; // r8d
  __int64 v272; // rax
  const char *v273; // r9
  __int64 v274; // rdx
  __int64 v275; // rax
  __int64 v276; // rax
  __int64 v277; // rdx
  int *v278; // rsi
  __int64 v279; // r15
  __int64 v280; // rax
  __int64 v281; // r8
  __int64 v282; // r14
  __int64 v283; // rdx
  __int64 v284; // rax
  __int64 v285; // rdx
  __int64 v286; // r8
  __int64 v287; // rax
  __int64 v288; // r8
  __int64 v289; // rax
  __int64 v290; // r8
  int v291; // esi
  __int64 v292; // r14
  int v293; // r15d
  _DWORD *v294; // r12
  _QWORD *v295; // rax
  _QWORD *v296; // rdx
  int v297; // r9d
  int v298; // r8d
  int v299; // edx
  __int64 v300; // rdx
  int v301; // eax
  __int64 v302; // rcx
  __int64 v303; // r15
  __int64 v304; // rdi
  __int64 v305; // r12
  __int64 v306; // rax
  __int64 v307; // r14
  __int64 v308; // r15
  __int64 v309; // r12
  __int64 v310; // r14
  __int64 v311; // rdi
  __int64 v312; // rax
  __int64 v313; // rsi
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // rax
  __int64 v317; // r14
  _DWORD *v318; // r12
  __int64 v319; // r13
  __int64 v320; // rax
  void *v321; // rax
  void *v322; // r15
  size_t v323; // rax
  size_t v324; // r12
  void *v325; // rax
  _QWORD *v326; // r9
  __int64 v327; // rdx
  int v328; // ecx
  __int64 v329; // r8
  __int64 v330; // rdx
  int v331; // eax
  __int64 v332; // rax
  char v333; // r13
  __int64 v334; // r12
  __int64 v335; // r14
  __int64 v336; // rsi
  __int64 v337; // rax
  __int64 v338; // rdi
  _QWORD *v339; // rdi
  int v340; // r8d
  _WORD *v341; // rcx
  int v342; // eax
  __int64 result; // rax
  __int64 v344; // rsi
  __int64 v345; // rdx
  __int64 v346; // r9
  _QWORD *v347; // rdi
  __int64 v348; // r8
  __int64 v349; // rdi
  __int64 v350; // rdx
  __int64 v351; // rcx
  __int64 v352; // rax
  __int64 v353; // rdx
  __int64 v354; // rax
  __int64 v355; // rdx
  _OWORD *v356; // rax
  __int64 v357; // r8
  __int64 v358; // rdx
  __int64 v359; // [rsp+28h] [rbp-81h]
  int v360; // [rsp+68h] [rbp-41h]
  __int128 v361; // [rsp+78h] [rbp-31h] BYREF
  void *Src[2]; // [rsp+88h] [rbp-21h] BYREF
  char v363[4]; // [rsp+98h] [rbp-11h] BYREF
  __int128 v364; // [rsp+9Ch] [rbp-Dh]
  __int128 v365; // [rsp+B0h] [rbp+7h]
  unsigned int v367; // [rsp+110h] [rbp+67h]

  v367 = a2;
  v5 = *a1;
  switch ( a2 )
  {
    case 0u:
      if ( !a5[41] )
        *((_BYTE *)a5 + 299) = 1;
      goto LABEL_781;
    case 1u:
      if ( !a5[41] )
        *((_BYTE *)a5 + 299) = 2;
      goto LABEL_781;
    case 2u:
      sqlite3FinishCoding(a5);
      goto LABEL_781;
    case 3u:
      sqlite3BeginTransaction(a5, *(unsigned int *)(v5 - 16));
      goto LABEL_781;
    case 4u:
      *(_DWORD *)(v5 + 32) = 7;
      goto LABEL_781;
    case 5u:
    case 6u:
    case 7u:
    case 0x59u:
    case 0x5Bu:
    case 0x102u:
    case 0x13Fu:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      goto LABEL_781;
    case 8u:
    case 9u:
      v6 = "COMMIT";
      v7 = 0;
      if ( *(_WORD *)(v5 - 22) == 12 )
        v6 = "ROLLBACK";
      LOBYTE(v7) = *(_WORD *)(v5 - 22) == 12;
      if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a5, 22, (_DWORD)v6, 0, 0) )
      {
        v8 = a5[2];
        if ( v8 )
          goto LABEL_17;
        if ( !a5[21] && (*(_BYTE *)(*a5 + 96LL) & 8) == 0 )
          *((_BYTE *)a5 + 35) = 1;
        v8 = sqlite3VdbeCreate(a5);
        if ( v8 )
        {
LABEL_17:
          v9 = *(int *)(v8 + 144);
          if ( *(_DWORD *)(v8 + 148) > (int)v9 )
          {
            *(_DWORD *)(v8 + 144) = v9 + 1;
            v10 = 3 * v9;
            v11 = *(_QWORD *)(v8 + 136);
            *(_DWORD *)(v11 + 8 * v10) = 1;
            *(_DWORD *)(v11 + 8 * v10 + 4) = 1;
            *(_DWORD *)(v11 + 8 * v10 + 8) = v7;
            *(_DWORD *)(v11 + 8 * v10 + 12) = 0;
            *(_QWORD *)(v11 + 8 * v10 + 16) = 0;
          }
          else
          {
            LODWORD(v359) = 0;
            growOp3(v8, 1, 1, v7, v359);
          }
        }
      }
      goto LABEL_781;
    case 0xAu:
      sqlite3Savepoint(a5, 0, v5 + 8);
      goto LABEL_781;
    case 0xBu:
      sqlite3Savepoint(a5, 1, v5 + 8);
      goto LABEL_781;
    case 0xCu:
      sqlite3Savepoint(a5, 2, v5 + 8);
      goto LABEL_781;
    case 0xDu:
      sqlite3StartTable((_DWORD)a5, v5 - 16, v5 + 8, *(_DWORD *)(v5 - 88), 0, 0, *(_DWORD *)(v5 - 40));
      goto LABEL_781;
    case 0xEu:
      ++*((_BYTE *)a5 + 36);
      v12 = *a5;
      ++*(_DWORD *)(v12 + 416);
      *(_WORD *)(v12 + 420) = 0;
      goto LABEL_781;
    case 0xFu:
    case 0x12u:
    case 0x15u:
    case 0x2Fu:
    case 0x31u:
    case 0x3Eu:
    case 0x48u:
    case 0x51u:
    case 0x62u:
    case 0xEDu:
    case 0xF2u:
      *(_DWORD *)(v5 + 32) = 0;
      goto LABEL_781;
    case 0x10u:
      *(_DWORD *)(v5 - 40) = 1;
      goto LABEL_781;
    case 0x11u:
      *(_DWORD *)(v5 + 8) = *(_BYTE *)(*a5 + 197LL) == 0;
      goto LABEL_781;
    case 0x13u:
      sqlite3EndTable((_DWORD)a5, v5 - 40, v5 - 16, *(_DWORD *)(v5 + 8), 0);
      goto LABEL_781;
    case 0x14u:
      v13 = a5;
      sqlite3EndTable((_DWORD)a5, 0, 0, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_143;
    case 0x16u:
      *(_DWORD *)(v5 - 40) |= *(_DWORD *)(v5 + 8);
      goto LABEL_781;
    case 0x17u:
      v14 = *(_DWORD *)(v5 + 16);
      if ( v14 != 5 )
        goto LABEL_40;
      v15 = *(unsigned __int8 **)(v5 + 8);
      if ( !v15 )
        goto LABEL_40;
      v16 = 5;
      v17 = "rowid";
      while ( 1 )
      {
        v18 = *v15;
        --v16;
        if ( !(_BYTE)v18 || *((_BYTE *)qword_180114680 + v18) != *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v17) )
          break;
        ++v15;
        ++v17;
        if ( v16 <= 0 )
        {
          --v16;
          break;
        }
      }
      if ( v16 < 0
        || *((unsigned __int8 *)qword_180114680 + *v15) == *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v17) )
      {
        *(_DWORD *)(v5 - 16) = 640;
      }
      else
      {
LABEL_40:
        v19 = *(const char **)(v5 + 8);
        *(_DWORD *)(v5 - 16) = 0;
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", v14, v19);
      }
      goto LABEL_781;
    case 0x18u:
      v20 = *(_DWORD *)(v5 + 16);
      if ( v20 != 6 )
        goto LABEL_51;
      v21 = *(unsigned __int8 **)(v5 + 8);
      if ( !v21 )
        goto LABEL_51;
      v22 = 6;
      v23 = "strict";
      while ( 1 )
      {
        v24 = *v21;
        --v22;
        if ( !(_BYTE)v24 || *((_BYTE *)qword_180114680 + v24) != *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v23) )
          break;
        ++v21;
        ++v23;
        if ( v22 <= 0 )
        {
          --v22;
          break;
        }
      }
      if ( v22 < 0
        || *((unsigned __int8 *)qword_180114680 + *v21) == *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v23) )
      {
        *(_DWORD *)(v5 + 8) = 0x10000;
      }
      else
      {
LABEL_51:
        sqlite3ErrorMsg(a5, "unknown table option: %.*s", v20, *(const char **)(v5 + 8));
        *(_DWORD *)(v5 + 8) = 0;
      }
      goto LABEL_781;
    case 0x19u:
      v25 = *(_OWORD *)(v5 - 16);
      *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
      v361 = v25;
      sqlite3AddColumn(a5, &v361, Src);
      goto LABEL_781;
    case 0x1Au:
    case 0x41u:
    case 0x68u:
      *(_DWORD *)(v5 + 40) = 0;
      *(_QWORD *)(v5 + 32) = 0;
      goto LABEL_781;
    case 0x1Bu:
      *(_DWORD *)(v5 - 56) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64);
      goto LABEL_781;
    case 0x1Cu:
      *(_DWORD *)(v5 - 104) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 112);
      goto LABEL_781;
    case 0x1Du:
      *(_DWORD *)(v5 - 8) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 16);
      goto LABEL_781;
    case 0x1Eu:
      *(_QWORD *)(v5 + 32) = *a4;
      goto LABEL_781;
    case 0x1Fu:
      *(_OWORD *)(v5 + 32) = *(_OWORD *)a4;
      goto LABEL_781;
    case 0x20u:
    case 0x43u:
      *(_OWORD *)(a5 + 13) = *(_OWORD *)(v5 + 8);
      goto LABEL_781;
    case 0x21u:
      sqlite3AddDefaultValue(
        a5,
        *(_QWORD *)(v5 + 8),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8));
      goto LABEL_781;
    case 0x22u:
      sqlite3AddDefaultValue(a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40) + 1LL, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x23u:
      sqlite3AddDefaultValue(
        a5,
        *(_QWORD *)(v5 + 8),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8));
      goto LABEL_781;
    case 0x24u:
      v26 = *(_QWORD *)(v5 + 8);
      v27 = sqlite3DbMallocRawNN(*a5, 72);
      if ( v27 )
      {
        v28 = 1;
        *(_OWORD *)v27 = 0;
        *(_OWORD *)(v27 + 16) = 0;
        *(_OWORD *)(v27 + 32) = 0;
        *(_OWORD *)(v27 + 48) = 0;
        *(_QWORD *)(v27 + 64) = 0;
        *(_BYTE *)v27 = -83;
        *(_WORD *)(v27 + 50) = -1;
        *(_DWORD *)(v27 + 40) = 1;
        if ( v26 )
        {
          *(_QWORD *)(v27 + 16) = v26;
          *(_DWORD *)(v27 + 4) |= *(_DWORD *)(v26 + 4) & 0x400208;
          v29 = *(_DWORD *)(v26 + 40);
          if ( v29 >= 1 )
          {
            v28 = v29 + 1;
            *(_DWORD *)(v27 + 40) = v29 + 1;
          }
        }
        v30 = *(_DWORD *)(*a5 + 148LL);
        if ( v28 > v30 )
          sqlite3ErrorMsg(a5, "Expression tree is too large (maximum depth %d)", v30);
      }
      else if ( v26 )
      {
        sqlite3ExprDeleteNN(*a5, v26);
      }
      sqlite3AddDefaultValue(a5, v27, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8));
      goto LABEL_781;
    case 0x25u:
      *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
      v31 = tokenExpr(a5, 117, Src);
      v32 = v31;
      if ( v31 )
        sqlite3ExprIdToTrueFalse(v31);
      sqlite3AddDefaultValue(a5, v32, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 + 8) + *(unsigned int *)(v5 + 16));
      goto LABEL_781;
    case 0x26u:
      v33 = a5[43];
      if ( v33 )
      {
        v34 = *(__int16 *)(v33 + 54);
        if ( (int)v34 >= 1 )
        {
          v35 = *(_QWORD *)(v33 + 8) + 24 * v34;
          *(_DWORD *)(v35 - 16) ^= (*(_DWORD *)(v35 - 16) ^ *(unsigned __int8 *)(v5 + 8)) & 0xF;
          *(_DWORD *)(v33 + 48) |= 0x800u;
          if ( (*(_BYTE *)(v35 - 6) & 8) != 0 )
          {
            for ( i = *(_QWORD *)(v33 + 16); i; i = *(_QWORD *)(i + 40) )
            {
              if ( **(__int16 **)(i + 8) == *(__int16 *)(v33 + 54) - 1 )
                *(_DWORD *)(i + 100) |= 8u;
            }
          }
        }
      }
      goto LABEL_781;
    case 0x27u:
      sqlite3AddPrimaryKey((_DWORD)a5, 0, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40));
      goto LABEL_781;
    case 0x28u:
      sqlite3CreateIndex(a5, 0, 0, 0, 0, *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_781;
    case 0x29u:
      sqlite3AddCheckConstraint(a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x2Au:
      sqlite3CreateForeignKey((_DWORD)a5, 0, v5 - 40, *(_QWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x2Bu:
      v37 = a5[43];
      if ( v37 )
      {
        if ( !*(_BYTE *)(v37 + 63) )
        {
          v38 = *(_QWORD *)(v37 + 72);
          if ( v38 )
            *(_BYTE *)(v38 + 44) = *(_BYTE *)(v5 + 8);
        }
      }
      goto LABEL_781;
    case 0x2Cu:
      v39 = a5[43];
      if ( !v39 )
        goto LABEL_781;
      if ( *((_BYTE *)a5 + 300) >= 2u )
        goto LABEL_781;
      v40 = (_QWORD *)*a5;
      v41 = *(__int16 *)(v39 + 54);
      v42 = sqlite3NameFromToken(*a5, v5 + 8);
      v43 = (_QWORD *)v42;
      if ( !v42 )
        goto LABEL_781;
      if ( sqlite3LocateCollSeq(a5, v42) )
      {
        v44 = v41 - 1;
        v45 = 24 * v41;
        sqlite3ColumnSetColl(v40, v45 + *(_QWORD *)(v39 + 8) - 24LL, v43);
        for ( j = *(_QWORD *)(v39 + 16); j; j = *(_QWORD *)(j + 40) )
        {
          if ( **(__int16 **)(j + 8) == v44 )
          {
            v47 = *(_QWORD *)(v39 + 8);
            v48 = *(_WORD *)(v45 + v47 - 6);
            if ( (v48 & 0x200) != 0 )
            {
              for ( k = *(_BYTE **)(v45 + v47 - 24); *k; ++k )
                ;
              if ( (v48 & 4) != 0 )
              {
                do
                  ++k;
                while ( *k );
              }
              v49 = k + 1;
            }
            else
            {
              v49 = 0;
            }
            **(_QWORD **)(j + 64) = v49;
          }
        }
      }
      if ( !v40 )
        goto LABEL_114;
      if ( (unsigned __int64)v43 >= v40[62] )
        goto LABEL_112;
      if ( (unsigned __int64)v43 < v40[60] )
      {
        if ( (unsigned __int64)v43 < v40[61] )
        {
LABEL_112:
          if ( v40[97] )
            measureAllocationSize(v40, v43);
          else
LABEL_114:
            sqlite3_free(v43);
        }
        else
        {
          *v43 = v40[57];
          v40[57] = v43;
        }
      }
      else
      {
        *v43 = v40[59];
        v40[59] = v43;
      }
      goto LABEL_781;
    case 0x2Du:
      sqlite3AddGenerated(a5, *(_QWORD *)(v5 - 16), 0);
      goto LABEL_781;
    case 0x2Eu:
      sqlite3AddGenerated(a5, *(_QWORD *)(v5 - 40), v5 + 8);
      goto LABEL_781;
    case 0x30u:
    case 0x60u:
    case 0x7Au:
    case 0x89u:
    case 0x115u:
      *(_DWORD *)(v5 + 8) = 1;
      goto LABEL_781;
    case 0x32u:
      *(_DWORD *)(v5 - 16) = *(_DWORD *)(v5 + 8) | *(_DWORD *)(v5 - 16) & ~*(_DWORD *)(v5 + 12);
      goto LABEL_781;
    case 0x33u:
      goto LABEL_420;
    case 0x34u:
      goto LABEL_714;
    case 0x35u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 36) = 255;
      goto LABEL_781;
    case 0x36u:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8) << 8;
      *(_DWORD *)(v5 - 36) = 65280;
      goto LABEL_781;
    case 0x37u:
      *(_DWORD *)(v5 - 16) = 8;
      goto LABEL_781;
    case 0x38u:
      *(_DWORD *)(v5 - 16) = 9;
      goto LABEL_781;
    case 0x39u:
      *(_DWORD *)(v5 + 8) = 10;
      goto LABEL_781;
    case 0x3Au:
      *(_DWORD *)(v5 + 8) = 7;
      goto LABEL_781;
    case 0x3Bu:
    case 0x40u:
    case 0x8Bu:
      *(_DWORD *)(v5 - 16) = 0;
      goto LABEL_781;
    case 0x3Cu:
      *(_DWORD *)(v5 - 40) = 0;
      goto LABEL_781;
    case 0x3Du:
    case 0x4Cu:
    case 0xABu:
      *(_DWORD *)(v5 - 16) = *(_DWORD *)(v5 + 8);
      goto LABEL_781;
    case 0x3Fu:
    case 0x50u:
    case 0x8Cu:
    case 0xD7u:
    case 0xDAu:
    case 0xF3u:
      *(_DWORD *)(v5 - 16) = 1;
      goto LABEL_781;
    case 0x42u:
      *((_DWORD *)a5 + 28) = 0;
      goto LABEL_781;
    case 0x44u:
      sqlite3AddPrimaryKey((_DWORD)a5, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40), 0);
      goto LABEL_781;
    case 0x45u:
      sqlite3CreateIndex(a5, 0, 0, 0, *(_DWORD **)(v5 - 40), *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
      goto LABEL_781;
    case 0x46u:
      sqlite3AddCheckConstraint(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      goto LABEL_781;
    case 0x47u:
      sqlite3CreateForeignKey((_DWORD)a5, *(_QWORD *)(v5 - 136), v5 - 64, *(_QWORD *)(v5 - 40), *(_DWORD *)(v5 - 16));
      v51 = a5[43];
      if ( v51 )
      {
        if ( !*(_BYTE *)(v51 + 63) )
        {
          v52 = *(_QWORD *)(v51 + 72);
          if ( v52 )
            *(_BYTE *)(v52 + 44) = *(_BYTE *)(v5 + 8);
        }
      }
      goto LABEL_781;
    case 0x49u:
    case 0x4Bu:
      *(_DWORD *)(v5 + 32) = 11;
      goto LABEL_781;
    case 0x4Au:
      *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
      goto LABEL_781;
    case 0x4Du:
      *(_DWORD *)(v5 + 8) = 4;
      goto LABEL_781;
    case 0x4Eu:
    case 0xACu:
      *(_DWORD *)(v5 + 8) = 5;
      goto LABEL_781;
    case 0x4Fu:
      sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), 0, *(unsigned int *)(v5 - 16));
      goto LABEL_781;
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
      goto LABEL_781;
    case 0x53u:
      sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), 1, *(unsigned int *)(v5 - 16));
      goto LABEL_781;
    case 0x54u:
      v13 = a5;
      v53 = *(_QWORD *)(v5 + 8);
      v363[0] = 9;
      v364 = 0;
      v365 = 0;
      sqlite3Select(a5, v53, v363);
LABEL_143:
      v54 = *(_QWORD *)(v5 + 8);
      goto LABEL_144;
    case 0x55u:
      v55 = *(_QWORD *)(v5 + 8);
      v56 = *(_QWORD *)(v5 - 16);
      if ( v55 )
      {
        *(_QWORD *)(v55 + 104) = v56;
        parserDoubleLinkSelect(a5, v55);
        *(_QWORD *)(v5 - 40) = v55;
      }
      else
      {
        sqlite3WithDelete(*a5, v56);
        *(_QWORD *)(v5 - 40) = 0;
      }
      goto LABEL_781;
    case 0x56u:
      v57 = *(_QWORD *)(v5 + 8);
      v58 = *(_QWORD *)(v5 - 16);
      if ( v57 )
      {
        *(_QWORD *)(v57 + 104) = v58;
        parserDoubleLinkSelect(a5, v57);
        *(_QWORD *)(v5 - 64) = v57;
      }
      else
      {
        sqlite3WithDelete(*a5, v58);
        *(_QWORD *)(v5 - 64) = 0;
      }
      goto LABEL_781;
    case 0x57u:
      v59 = *(_QWORD *)(v5 + 8);
      if ( v59 )
        parserDoubleLinkSelect(a5, v59);
      goto LABEL_781;
    case 0x58u:
      v60 = *(_QWORD *)(v5 + 8);
      v61 = *(_QWORD *)(v5 - 40);
      if ( v60 )
      {
        if ( !*(_QWORD *)(v60 + 80)
          || (v62 = *(_QWORD *)(v5 + 8),
              LODWORD(Src[1]) = 0,
              parserDoubleLinkSelect(a5, v62),
              v63 = sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)Src, v60, 0),
              (v60 = sqlite3SelectNew((_DWORD)a5, 0, v63, 0, 0, 0, 0, 0, 0)) != 0) )
        {
          *(_BYTE *)v60 = *(_BYTE *)(v5 - 16);
          *(_QWORD *)(v60 + 80) = v61;
          if ( v61 )
            *(_DWORD *)(v61 + 4) &= ~0x400u;
          *(_DWORD *)(v60 + 4) &= ~0x400u;
          if ( *(_DWORD *)(v5 - 16) != 135 )
          {
            *((_BYTE *)a5 + 34) = 1;
            *(_QWORD *)(v5 - 40) = v60;
            goto LABEL_781;
          }
          goto LABEL_538;
        }
      }
      if ( !v61 )
        goto LABEL_538;
      clearSelect(*a5, v61, 1);
      *(_QWORD *)(v5 - 40) = v60;
      goto LABEL_781;
    case 0x5Au:
      *(_DWORD *)(v5 - 16) = 135;
      goto LABEL_781;
    case 0x5Cu:
      *(_QWORD *)(v5 - 184) = sqlite3SelectNew(
                                (_DWORD)a5,
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 112),
                                *(_QWORD *)(v5 - 88),
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 - 40),
                                *(_QWORD *)(v5 - 16),
                                *(_DWORD *)(v5 - 160),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x5Du:
      v64 = sqlite3SelectNew(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 160),
              *(_QWORD *)(v5 - 136),
              *(_QWORD *)(v5 - 112),
              *(_QWORD *)(v5 - 88),
              *(_QWORD *)(v5 - 64),
              *(_QWORD *)(v5 - 16),
              *(_DWORD *)(v5 - 184),
              *(_QWORD *)(v5 + 8));
      v65 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 208) = v64;
      if ( v64 )
        *(_QWORD *)(v64 + 120) = v65;
      else
        sqlite3WindowListDelete(*a5, v65);
      goto LABEL_781;
    case 0x5Eu:
      *(_QWORD *)(v5 - 64) = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 512, 0);
      goto LABEL_781;
    case 0x5Fu:
      v66 = *(_QWORD *)(v5 - 88);
      v67 = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 1536, 0);
      if ( v66 )
        *(_DWORD *)(v66 + 4) &= ~0x400u;
      if ( v67 )
      {
        *(_BYTE *)v67 = -121;
        *(_QWORD *)(v67 + 80) = v66;
      }
      else
      {
        v67 = v66;
      }
      goto LABEL_780;
    case 0x61u:
    case 0xECu:
    case 0x116u:
      *(_DWORD *)(v5 + 8) = 2;
      goto LABEL_781;
    case 0x63u:
    case 0x69u:
    case 0x6Cu:
    case 0x84u:
    case 0x8Eu:
    case 0x90u:
    case 0x92u:
    case 0x97u:
    case 0x99u:
    case 0xA4u:
    case 0xADu:
    case 0xE4u:
    case 0xE5u:
    case 0xE6u:
    case 0xE9u:
    case 0xEEu:
    case 0xF8u:
    case 0x108u:
    case 0x11Bu:
      *(_QWORD *)(v5 + 32) = 0;
      goto LABEL_781;
    case 0x64u:
      appended = *(int **)(v5 - 88);
      v69 = *(_QWORD *)(v5 - 40);
      if ( appended )
      {
        v70 = *appended;
        v71 = v70 + 1;
        if ( appended[1] >= (int)v70 + 1 )
        {
          v72 = 8 * v70;
          *appended = v71;
          *(_OWORD *)&appended[v72 + 2] = xmmword_180114128;
          *(_OWORD *)&appended[v72 + 6] = xmmword_180114138;
          *(_QWORD *)&appended[v72 + 2] = v69;
        }
        else
        {
          appended = (int *)sqlite3ExprListAppendGrow(*a5, appended, *(_QWORD *)(v5 - 40));
        }
      }
      else
      {
        appended = (int *)sqlite3ExprListAppendNew(*a5, *(_QWORD *)(v5 - 40));
      }
      v73 = *(_DWORD *)(v5 + 16) == 0;
      *(_QWORD *)(v5 - 88) = appended;
      if ( !v73 )
        sqlite3ExprListSetName(a5, appended, v5 + 8, 1);
      v74 = *(int **)(v5 - 88);
      if ( v74 )
      {
        v75 = &v74[8 * *v74];
        if ( !*((_QWORD *)v75 - 2) )
        {
          v76 = sqlite3DbSpanDup(*a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
          *(v75 - 1) &= ~2u;
          *(v75 - 1) |= 1u;
          *((_QWORD *)v75 - 2) = v76;
        }
      }
      goto LABEL_781;
    case 0x65u:
      v77 = sqlite3Expr(*a5, 180, 0);
      v78 = v77;
      if ( v77 && (*(_BYTE *)(v77 + 4) & 3) == 0 )
        *(_DWORD *)(v77 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 84);
      v79 = *(int **)(v5 - 40);
      if ( v79 )
      {
        v80 = *v79;
        if ( v79[1] >= (int)v80 + 1 )
        {
          *v79 = v80 + 1;
          v81 = 8 * v80;
          *(_OWORD *)&v79[v81 + 2] = xmmword_180114128;
          *(_OWORD *)&v79[v81 + 6] = xmmword_180114138;
          *(_QWORD *)&v79[v81 + 2] = v78;
          *(_QWORD *)(v5 - 40) = v79;
        }
        else
        {
          *(_QWORD *)(v5 - 40) = sqlite3ExprListAppendGrow(*a5, v79, v78);
        }
      }
      else
      {
        *(_QWORD *)(v5 - 40) = sqlite3ExprListAppendNew(*a5, v77);
      }
      goto LABEL_781;
    case 0x66u:
      v82 = sqlite3DbMallocRawNN(*a5, 72);
      v83 = v82;
      v84 = 1;
      if ( v82 )
      {
        *(_OWORD *)v82 = 0;
        *(_OWORD *)(v82 + 16) = 0;
        *(_OWORD *)(v82 + 32) = 0;
        *(_OWORD *)(v82 + 48) = 0;
        *(_QWORD *)(v82 + 64) = 0;
        *(_BYTE *)v82 = -76;
        *(_WORD *)(v82 + 50) = -1;
        *(_DWORD *)(v82 + 40) = 1;
        v85 = *(_DWORD *)(*a5 + 148LL);
        if ( v85 < 1 )
          sqlite3ErrorMsg(a5, "Expression tree is too large (maximum depth %d)", v85);
        if ( (*(_BYTE *)(v83 + 4) & 3) == 0 )
          *(_DWORD *)(v83 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 84);
      }
      *(_OWORD *)Src = *(_OWORD *)(v5 - 40);
      v86 = tokenExpr(a5, 59, Src);
      v87 = sqlite3DbMallocRawNN(*a5, 72);
      if ( v87 )
      {
        *(_OWORD *)v87 = 0;
        *(_OWORD *)(v87 + 16) = 0;
        *(_OWORD *)(v87 + 32) = 0;
        *(_OWORD *)(v87 + 48) = 0;
        *(_QWORD *)(v87 + 64) = 0;
        *(_BYTE *)v87 = -115;
        *(_WORD *)(v87 + 50) = -1;
        if ( v83 )
        {
          *(_QWORD *)(v87 + 24) = v83;
          *(_DWORD *)(v87 + 4) |= *(_DWORD *)(v83 + 4) & 0x400208;
          v84 = *(_DWORD *)(v83 + 40) + 1;
        }
        *(_DWORD *)(v87 + 40) = v84;
        if ( v86 )
        {
          *(_QWORD *)(v87 + 16) = v86;
          *(_DWORD *)(v87 + 4) |= *(_DWORD *)(v86 + 4) & 0x400208;
          v88 = *(_DWORD *)(v86 + 40);
          if ( v88 >= v84 )
          {
            v84 = v88 + 1;
            *(_DWORD *)(v87 + 40) = v88 + 1;
          }
        }
        v89 = *(_DWORD *)(*a5 + 148LL);
        if ( v84 > v89 )
          sqlite3ErrorMsg(a5, "Expression tree is too large (maximum depth %d)", v89);
      }
      else
      {
        if ( v86 )
          sqlite3ExprDeleteNN(*a5, v86);
        if ( v83 )
          sqlite3ExprDeleteNN(*a5, v83);
      }
      v90 = *(int **)(v5 - 88);
      if ( v90 )
      {
        v91 = *v90;
        if ( v90[1] >= (int)v91 + 1 )
        {
          *v90 = v91 + 1;
          v92 = 8 * v91;
          *(_OWORD *)&v90[v92 + 2] = xmmword_180114128;
          *(_OWORD *)&v90[v92 + 6] = xmmword_180114138;
          *(_QWORD *)&v90[v92 + 2] = v87;
          *(_QWORD *)(v5 - 88) = v90;
        }
        else
        {
          *(_QWORD *)(v5 - 88) = sqlite3ExprListAppendGrow(*a5, *(_QWORD *)(v5 - 88), v87);
        }
      }
      else
      {
        *(_QWORD *)(v5 - 88) = sqlite3ExprListAppendNew(*a5, v87);
      }
      goto LABEL_781;
    case 0x67u:
    case 0x73u:
    case 0xFEu:
    case 0xFFu:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      goto LABEL_781;
    case 0x6Au:
      *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      sqlite3SrcListShiftJoinType(a5);
      goto LABEL_781;
    case 0x6Bu:
      v93 = *(int **)(v5 - 16);
      if ( v93 )
      {
        v94 = *v93;
        if ( (int)v94 > 0 )
          LOBYTE(v93[26 * v94 - 9]) = *(_BYTE *)(v5 + 8);
      }
      goto LABEL_781;
    case 0x6Du:
      v95 = (_QWORD *)(v5 + 8);
      v96 = *(unsigned int **)(v5 - 88);
      v97 = *a5;
      if ( v96 )
      {
        v100 = (int *)sqlite3SrcListEnlarge(a5, *(_QWORD *)(v5 - 88), 1, *v96);
        if ( v100 )
          goto LABEL_228;
        sqlite3SrcListDelete(v97, v96);
LABEL_245:
        if ( v5 == -8 )
        {
LABEL_250:
          *(_QWORD *)(v5 - 88) = 0;
          goto LABEL_781;
        }
LABEL_246:
        if ( *v95 )
        {
          sqlite3ExprDeleteNN(v97, *v95);
          *(_QWORD *)(v5 - 88) = 0;
          goto LABEL_781;
        }
        if ( *(_QWORD *)(v5 + 16) )
          sqlite3IdListDelete(v97);
        goto LABEL_250;
      }
      if ( v5 != -8 && (*v95 || *(_QWORD *)(v5 + 16)) )
      {
        v98 = "USING";
        if ( *v95 )
          v98 = "ON";
        sqlite3ErrorMsg(a5, "a JOIN clause is required before %s", v98);
        goto LABEL_246;
      }
      v99 = sqlite3DbMallocRawNN(*a5, 112);
      v100 = (int *)v99;
      if ( !v99 )
        goto LABEL_245;
      *(_DWORD *)(v99 + 4) = 1;
      *(_DWORD *)v99 = 1;
      *(_OWORD *)(v99 + 8) = 0;
      *(_OWORD *)(v99 + 24) = 0;
      *(_OWORD *)(v99 + 40) = 0;
      *(_OWORD *)(v99 + 56) = 0;
      *(_OWORD *)(v99 + 72) = 0;
      *(_OWORD *)(v99 + 88) = 0;
      *(_QWORD *)(v99 + 104) = 0;
      *(_DWORD *)(v99 + 76) = -1;
LABEL_228:
      v101 = (_QWORD *)(v5 - 40);
      v102 = 26LL * *v100;
      v103 = 0;
      if ( v5 != 40 && !*v101 )
      {
        v104 = &v100[v102 - 20];
        *(_QWORD *)&v361 = &v100[v102 - 22];
LABEL_231:
        *(_QWORD *)v104 = sqlite3NameFromToken(v97, v5 - 64);
        v105 = 0;
        goto LABEL_232;
      }
      v104 = &v100[v102 - 20];
      *(_QWORD *)&v361 = &v100[v102 - 22];
      if ( v5 == 40 )
        goto LABEL_231;
      *(_QWORD *)v104 = sqlite3NameFromToken(v97, v5 - 40);
      v105 = sqlite3NameFromToken(v97, v5 - 64);
LABEL_232:
      v106 = v5 - 16;
      *(_QWORD *)v361 = v105;
      v107 = &v100[26 * *v100];
      if ( *((_BYTE *)a5 + 300) >= 2u )
      {
        v108 = *((_QWORD *)v107 - 10);
        if ( v108 )
        {
          if ( v5 == 40 || !*v101 )
            v101 = (_QWORD *)(v5 - 64);
          sqlite3RenameTokenMap(a5, v108, v101);
          v106 = v5 - 16;
        }
      }
      if ( *(_DWORD *)(v106 + 8) )
        *((_QWORD *)v107 - 9) = sqlite3NameFromToken(v97, v106);
      if ( v5 != -8 )
      {
        if ( *(_QWORD *)(v5 + 16) )
        {
          *(v107 - 8) |= 0x400u;
          *((_QWORD *)v107 - 3) = *(_QWORD *)(v5 + 16);
          *(_QWORD *)(v5 - 88) = v100;
          goto LABEL_781;
        }
        v103 = *v95;
      }
      *((_QWORD *)v107 - 3) = v103;
      *(_QWORD *)(v5 - 88) = v100;
LABEL_781:
      v340 = (unsigned __int16)word_180112F50[v367];
      v341 = (_WORD *)(v5 + 24LL * *((char *)qword_180113280 + v367) + 24);
      v342 = word_1801125E0[*(unsigned __int16 *)(v5 + 24LL * *((char *)qword_180113280 + v367))];
      *a1 = (__int64)v341;
      v341[1] = v340;
      result = (unsigned __int16)word_18010FF20[v340 + v342];
      *v341 = result;
      return result;
    case 0x6Eu:
      v109 = (_QWORD *)(v5 + 8);
      v110 = *(unsigned int **)(v5 - 112);
      v111 = *a5;
      if ( v110 )
      {
        v113 = (int *)sqlite3SrcListEnlarge(a5, *(_QWORD *)(v5 - 112), 1, *v110);
        if ( v113 )
          goto LABEL_278;
        sqlite3SrcListDelete(v111, v110);
        goto LABEL_295;
      }
      if ( v5 != -8 && (*v109 || *(_QWORD *)(v5 + 16)) )
      {
        v112 = "USING";
        if ( *v109 )
          v112 = "ON";
        sqlite3ErrorMsg(a5, "a JOIN clause is required before %s", v112);
        goto LABEL_296;
      }
      if ( *(_WORD *)(v111 + 420) < 0x70u )
      {
        if ( *(_DWORD *)(v111 + 416) )
        {
          if ( *(_BYTE *)(v111 + 103) )
            goto LABEL_295;
        }
        else
        {
          ++*(_DWORD *)(v111 + 436);
        }
        goto LABEL_276;
      }
      v113 = *(int **)(v111 + 472);
      if ( v113 )
      {
        *(_QWORD *)(v111 + 472) = *(_QWORD *)v113;
        ++*(_DWORD *)(v111 + 432);
      }
      else
      {
        v113 = *(int **)(v111 + 464);
        if ( v113 )
        {
          *(_QWORD *)(v111 + 464) = *(_QWORD *)v113;
          ++*(_DWORD *)(v111 + 432);
        }
        else
        {
          v113 = *(int **)(v111 + 456);
          if ( v113 )
          {
            *(_QWORD *)(v111 + 456) = *(_QWORD *)v113;
            ++*(_DWORD *)(v111 + 432);
          }
          else
          {
            v113 = *(int **)(v111 + 448);
            if ( !v113 )
            {
              ++*(_DWORD *)(v111 + 440);
LABEL_276:
              v113 = (int *)dbMallocRawFinish(v111, 112);
              if ( v113 )
                goto LABEL_277;
LABEL_295:
              if ( v5 == -8 )
              {
LABEL_300:
                *(_QWORD *)(v5 - 112) = 0;
                goto LABEL_781;
              }
LABEL_296:
              if ( *v109 )
              {
                sqlite3ExprDeleteNN(v111, *v109);
                *(_QWORD *)(v5 - 112) = 0;
                goto LABEL_781;
              }
              if ( *(_QWORD *)(v5 + 16) )
                sqlite3IdListDelete(v111);
              goto LABEL_300;
            }
            v114 = *(_QWORD *)v113;
            ++*(_DWORD *)(v111 + 432);
            *(_QWORD *)(v111 + 448) = v114;
          }
        }
      }
LABEL_277:
      v113[1] = 1;
      *v113 = 1;
      *(_OWORD *)(v113 + 2) = 0;
      *(_OWORD *)(v113 + 6) = 0;
      *(_OWORD *)(v113 + 10) = 0;
      *(_OWORD *)(v113 + 14) = 0;
      *(_OWORD *)(v113 + 18) = 0;
      *(_OWORD *)(v113 + 22) = 0;
      *((_QWORD *)v113 + 13) = 0;
      v113[19] = -1;
LABEL_278:
      v115 = (_QWORD *)(v5 - 64);
      v116 = 26LL * *v113;
      v117 = 0;
      if ( v5 == 64 || *v115 )
      {
        v118 = &v113[v116 - 20];
        *(_QWORD *)&v361 = &v113[v116 - 22];
        if ( v5 != 64 )
        {
          *(_QWORD *)v118 = sqlite3NameFromToken(v111, v5 - 64);
          v119 = sqlite3NameFromToken(v111, v5 - 88);
LABEL_282:
          v120 = v5 - 40;
          *(_QWORD *)v361 = v119;
          v121 = &v113[26 * *v113];
          if ( *((_BYTE *)a5 + 300) >= 2u )
          {
            v122 = *((_QWORD *)v121 - 10);
            if ( v122 )
            {
              if ( v5 == 64 || !*v115 )
                v115 = (_QWORD *)(v5 - 88);
              sqlite3RenameTokenMap(a5, v122, v115);
              v120 = v5 - 40;
            }
          }
          if ( *(_DWORD *)(v120 + 8) )
            *((_QWORD *)v121 - 9) = sqlite3NameFromToken(v111, v120);
          if ( v5 != -8 )
          {
            if ( *(_QWORD *)(v5 + 16) )
            {
              *(v121 - 8) |= 0x400u;
              v117 = *(_QWORD *)(v5 + 16);
            }
            else
            {
              v117 = *v109;
            }
          }
          *((_QWORD *)v121 - 3) = v117;
          v123 = (_QWORD *)(v5 - 16);
          *(_QWORD *)(v5 - 112) = v113;
          v124 = *(_DWORD *)(v5 - 16 + 8);
          if ( v124 )
          {
            v125 = &v113[26 * *v113];
            if ( v124 != 1 || *v123 )
            {
              v126 = sqlite3NameFromToken(*a5, v123);
              *(v125 - 8) |= 2u;
              *((_QWORD *)v125 - 1) = v126;
            }
            else
            {
              *(v125 - 8) |= 1u;
            }
          }
          goto LABEL_781;
        }
      }
      else
      {
        v118 = &v113[v116 - 20];
        *(_QWORD *)&v361 = &v113[v116 - 22];
      }
      *(_QWORD *)v118 = sqlite3NameFromToken(v111, v5 - 88);
      v119 = 0;
      goto LABEL_282;
    case 0x6Fu:
      v127 = a5;
      v128 = (_QWORD *)(v5 + 8);
      v129 = *(unsigned int **)(v5 - 160);
      v130 = *a5;
      if ( v129 )
      {
        v132 = (int *)sqlite3SrcListEnlarge(a5, *(_QWORD *)(v5 - 160), 1, *v129);
        if ( v132 )
          goto LABEL_332;
        sqlite3SrcListDelete(v130, v129);
LABEL_349:
        v127 = a5;
LABEL_350:
        if ( v5 == -8 )
        {
LABEL_355:
          v142 = *(_QWORD *)(v5 - 64);
          *(_QWORD *)(v5 - 160) = 0;
          if ( v142 )
            exprListDeleteNN(*v127, v142);
          goto LABEL_781;
        }
LABEL_351:
        if ( *v128 )
        {
          sqlite3ExprDeleteNN(v130, *v128);
        }
        else if ( *(_QWORD *)(v5 + 16) )
        {
          sqlite3IdListDelete(v130);
        }
        goto LABEL_355;
      }
      if ( v5 != -8 && (*v128 || *(_QWORD *)(v5 + 16)) )
      {
        v131 = "USING";
        if ( *v128 )
          v131 = "ON";
        sqlite3ErrorMsg(a5, "a JOIN clause is required before %s", v131);
        goto LABEL_351;
      }
      if ( *(_WORD *)(v130 + 420) < 0x70u )
      {
        if ( *(_DWORD *)(v130 + 416) )
        {
          if ( *(_BYTE *)(v130 + 103) )
            goto LABEL_350;
        }
        else
        {
          ++*(_DWORD *)(v130 + 436);
        }
        goto LABEL_330;
      }
      v132 = *(int **)(v130 + 472);
      if ( v132 )
      {
        *(_QWORD *)(v130 + 472) = *(_QWORD *)v132;
        ++*(_DWORD *)(v130 + 432);
      }
      else
      {
        v132 = *(int **)(v130 + 464);
        if ( v132 )
        {
          *(_QWORD *)(v130 + 464) = *(_QWORD *)v132;
          ++*(_DWORD *)(v130 + 432);
        }
        else
        {
          v132 = *(int **)(v130 + 456);
          if ( v132 )
          {
            *(_QWORD *)(v130 + 456) = *(_QWORD *)v132;
            ++*(_DWORD *)(v130 + 432);
          }
          else
          {
            v132 = *(int **)(v130 + 448);
            if ( !v132 )
            {
              ++*(_DWORD *)(v130 + 440);
LABEL_330:
              v132 = (int *)dbMallocRawFinish(v130, 112);
              if ( v132 )
                goto LABEL_331;
              goto LABEL_349;
            }
            v133 = *(_QWORD *)v132;
            ++*(_DWORD *)(v130 + 432);
            *(_QWORD *)(v130 + 448) = v133;
          }
        }
      }
LABEL_331:
      v132[1] = 1;
      *v132 = 1;
      *(_OWORD *)(v132 + 2) = 0;
      *(_OWORD *)(v132 + 6) = 0;
      *(_OWORD *)(v132 + 10) = 0;
      *(_OWORD *)(v132 + 14) = 0;
      *(_OWORD *)(v132 + 18) = 0;
      *(_OWORD *)(v132 + 22) = 0;
      *((_QWORD *)v132 + 13) = 0;
      v132[19] = -1;
LABEL_332:
      v134 = (_QWORD *)(v5 - 112);
      v135 = 26LL * *v132;
      v136 = 0;
      if ( v5 == 112 || *v134 )
      {
        v137 = &v132[v135 - 20];
        *(_QWORD *)&v361 = &v132[v135 - 22];
        if ( v5 != 112 )
        {
          *(_QWORD *)v137 = sqlite3NameFromToken(v130, v5 - 112);
          v138 = sqlite3NameFromToken(v130, v5 - 136);
LABEL_336:
          v139 = v5 - 16;
          *(_QWORD *)v361 = v138;
          v140 = &v132[26 * *v132];
          if ( *((_BYTE *)a5 + 300) >= 2u )
          {
            v141 = *((_QWORD *)v140 - 10);
            if ( v141 )
            {
              if ( v5 == 112 || !*v134 )
                v134 = (_QWORD *)(v5 - 136);
              sqlite3RenameTokenMap(a5, v141, v134);
              v139 = v5 - 16;
            }
          }
          if ( *(_DWORD *)(v139 + 8) )
            *((_QWORD *)v140 - 9) = sqlite3NameFromToken(v130, v139);
          if ( v5 != -8 )
          {
            if ( *(_QWORD *)(v5 + 16) )
            {
              *(v140 - 8) |= 0x400u;
              v136 = *(_QWORD *)(v5 + 16);
            }
            else
            {
              v136 = *v128;
            }
          }
          *((_QWORD *)v140 - 3) = v136;
          *(_QWORD *)(v5 - 160) = v132;
          v143 = 26LL * *v132;
          v144 = *(_QWORD *)(v5 - 64);
          v132[v143 - 8] |= 4u;
          *(_QWORD *)&v132[v143 - 2] = v144;
          goto LABEL_781;
        }
      }
      else
      {
        v137 = &v132[v135 - 20];
        *(_QWORD *)&v361 = &v132[v135 - 22];
      }
      *(_QWORD *)v137 = sqlite3NameFromToken(v130, v5 - 136);
      v138 = 0;
      goto LABEL_336;
    case 0x70u:
      *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendFromTerm(
                                (_DWORD)a5,
                                *(_QWORD *)(v5 - 112),
                                0,
                                0,
                                v5 - 16,
                                *(_QWORD *)(v5 - 64),
                                v5 + 8);
      goto LABEL_781;
    case 0x71u:
      v145 = *(_QWORD *)(v5 - 112);
      if ( v145 || *(_DWORD *)(v5 - 8) || *(_QWORD *)(v5 + 8) || *(_QWORD *)(v5 + 16) )
      {
        v146 = *(_DWORD **)(v5 - 64);
        if ( v146 && *v146 == 1 )
        {
          v147 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, v145, 0, 0, v5 - 16, 0, v5 + 8);
          *(_QWORD *)(v5 - 112) = v147;
          if ( v147 )
          {
            v148 = *(_QWORD *)(v5 - 64);
            v149 = &v147[26 * *v147];
            *((_QWORD *)v149 - 10) = *(_QWORD *)(v148 + 24);
            *((_QWORD *)v149 - 11) = *(_QWORD *)(v148 + 16);
            v150 = *(_QWORD *)(v148 + 48);
            *((_QWORD *)v149 - 7) = v150;
            if ( v150 && (*(_DWORD *)(v150 + 4) & 0x800) != 0 )
              *(v149 - 8) |= 0x2000u;
            if ( (*(_BYTE *)(v148 + 72) & 4) != 0 )
            {
              *((_QWORD *)v149 - 1) = *(_QWORD *)(v148 + 96);
              *(_DWORD *)(v148 + 72) &= ~4u;
              *(_QWORD *)(v148 + 96) = 0;
              *(v149 - 8) |= 4u;
            }
            *(_QWORD *)(v148 + 16) = 0;
            *(_QWORD *)(v148 + 24) = 0;
            *(_QWORD *)(v148 + 48) = 0;
          }
          sqlite3SrcListDelete(*a5, *(_QWORD *)(v5 - 64));
        }
        else
        {
          sqlite3SrcListShiftJoinType(a5);
          v151 = sqlite3SelectNew((_DWORD)a5, 0, *(_QWORD *)(v5 - 64), 0, 0, 0, 0, 2048, 0);
          *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendFromTerm(
                                    (_DWORD)a5,
                                    *(_QWORD *)(v5 - 112),
                                    0,
                                    0,
                                    v5 - 16,
                                    v151,
                                    v5 + 8);
        }
      }
      else
      {
        *(_QWORD *)(v5 - 112) = *(_QWORD *)(v5 - 64);
      }
      goto LABEL_781;
    case 0x72u:
    case 0x81u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_DWORD *)(v5 + 40) = 0;
      goto LABEL_781;
    case 0x74u:
      v152 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      v153 = v152;
      if ( *((_BYTE *)a5 + 300) < 2u || !v152 )
        goto LABEL_820;
      sqlite3RenameTokenMap(a5, *(_QWORD *)(v152 + 24), v5 + 8);
      *(_QWORD *)(v5 + 8) = v153;
      goto LABEL_781;
    case 0x75u:
      v154 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      v60 = v154;
      if ( *((_BYTE *)a5 + 300) < 2u || !v154 )
        goto LABEL_538;
      sqlite3RenameTokenMap(a5, *(_QWORD *)(v154 + 24), v5 + 8);
      *(_QWORD *)(v5 - 40) = v60;
      goto LABEL_781;
    case 0x76u:
      *(_QWORD *)(v5 + 8) = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
      goto LABEL_781;
    case 0x77u:
      *(_QWORD *)(v5 - 40) = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
      goto LABEL_781;
    case 0x78u:
      v155 = sqlite3SrcListAppend(a5, 0, v5 - 88, v5 - 40);
      *(_QWORD *)(v5 - 88) = v155;
      if ( v155 )
        *(_QWORD *)(*(_QWORD *)(v5 - 88) + 32LL) = sqlite3NameFromToken(*a5, v5 + 8);
      goto LABEL_781;
    case 0x79u:
      v156 = sqlite3SrcListAppend(a5, 0, v5 - 40, 0);
      *(_QWORD *)(v5 - 40) = v156;
      if ( v156 )
        *(_QWORD *)(*(_QWORD *)(v5 - 40) + 32LL) = sqlite3NameFromToken(*a5, v5 + 8);
      goto LABEL_781;
    case 0x7Bu:
      *(_DWORD *)(v5 - 16) = sqlite3JoinType(a5, v5 - 16, 0, 0);
      goto LABEL_781;
    case 0x7Cu:
      *(_DWORD *)(v5 - 40) = sqlite3JoinType(a5, v5 - 40, v5 - 16, 0);
      goto LABEL_781;
    case 0x7Du:
      *(_DWORD *)(v5 - 64) = sqlite3JoinType(a5, v5 - 64, v5 - 40, v5 - 16);
      goto LABEL_781;
    case 0x7Eu:
      *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 8) = 0;
      goto LABEL_781;
    case 0x7Fu:
      v157 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 64) = 0;
      *(_QWORD *)(v5 - 56) = v157;
      goto LABEL_781;
    case 0x80u:
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 0;
      goto LABEL_781;
    case 0x82u:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      goto LABEL_781;
    case 0x83u:
      *(_DWORD *)(v5 - 8) = 1;
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_781;
    case 0x85u:
    case 0x8Fu:
      goto LABEL_776;
    case 0x86u:
      v158 = (int *)sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 88) = v158;
      if ( v158 )
      {
        v159 = 0;
        v160 = *(_DWORD *)(v5 + 8);
        v161 = 8LL * *v158;
        if ( *(_DWORD *)(v5 - 16) != -1 )
          v159 = *(_DWORD *)(v5 - 16);
        LOBYTE(v158[v161 - 2]) = v159;
        if ( v160 != -1 )
        {
          v158[v161 - 1] |= 0x20u;
          if ( v159 != v160 )
            LOBYTE(v158[v161 - 2]) = v159 | 2;
        }
      }
      goto LABEL_781;
    case 0x87u:
      v162 = (int *)sqlite3ExprListAppendNew(*a5, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 40) = v162;
      if ( v162 )
      {
        v163 = 0;
        v164 = *(_DWORD *)(v5 + 8);
        v165 = 8LL * *v162;
        if ( *(_DWORD *)(v5 - 16) != -1 )
          v163 = *(_DWORD *)(v5 - 16);
        LOBYTE(v162[v165 - 2]) = v163;
        if ( v164 != -1 )
        {
          v162[v165 - 1] |= 0x20u;
          if ( v163 != v164 )
            LOBYTE(v162[v165 - 2]) = v163 | 2;
        }
      }
      goto LABEL_781;
    case 0x88u:
    case 0xD6u:
    case 0xD9u:
      *(_DWORD *)(v5 + 8) = 0;
      goto LABEL_781;
    case 0x8Au:
    case 0x8Du:
      *(_DWORD *)(v5 + 32) = -1;
      goto LABEL_781;
    case 0x91u:
    case 0x98u:
    case 0x9Au:
    case 0xE3u:
    case 0xF7u:
    case 0x109u:
    case 0x11Cu:
    case 0x14Bu:
      goto LABEL_812;
    case 0x93u:
      *(_QWORD *)(v5 - 16) = sqlite3PExpr(a5, 148, *(_QWORD *)(v5 + 8), 0);
      goto LABEL_781;
    case 0x94u:
      v166 = *(_QWORD *)(v5 + 8);
      v167 = *(_QWORD *)(v5 - 40);
      goto LABEL_417;
    case 0x95u:
      v166 = *(_QWORD *)(v5 - 40);
      v167 = *(_QWORD *)(v5 + 8);
LABEL_417:
      *(_QWORD *)(v5 - 64) = sqlite3PExpr(a5, 148, v167, v166);
      goto LABEL_781;
    case 0x96u:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 40), v5 - 16);
      sqlite3DeleteFrom((_DWORD)a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8), 0, 0);
      goto LABEL_781;
    case 0x9Bu:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
LABEL_420:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_781;
    case 0x9Cu:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 64) = *(_QWORD *)(v5 - 40);
      goto LABEL_781;
    case 0x9Du:
      sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 112), v5 - 88);
      v168 = *(_DWORD **)(v5 - 40);
      if ( v168 && *v168 > *(_DWORD *)(*a5 + 144LL) )
        sqlite3ErrorMsg(a5, "too many columns in %s", "set list");
      v169 = *(int **)(v5 - 16);
      if ( v169 )
      {
        if ( *v169 > 1 )
        {
          v170 = sqlite3SelectNew((_DWORD)a5, 0, (_DWORD)v169, 0, 0, 0, 0, 2048, 0);
          LODWORD(Src[1]) = 0;
          Src[0] = 0;
          v169 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)Src, v170, 0);
        }
        *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendList(a5, *(_QWORD *)(v5 - 112), v169);
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
      goto LABEL_781;
    case 0x9Eu:
      v171 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 88) = v171;
      sqlite3ExprListSetName(a5, v171, v5 - 40, 1);
      goto LABEL_781;
    case 0x9Fu:
      *(_QWORD *)(v5 - 136) = sqlite3ExprListAppendVector(
                                a5,
                                *(_QWORD *)(v5 - 136),
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xA0u:
      v172 = sqlite3ExprListAppendNew(*a5, *(_QWORD *)(v5 + 8));
      sqlite3ExprListSetName(a5, v172, v5 - 40, 1);
      *(_QWORD *)(v5 - 40) = v172;
      goto LABEL_781;
    case 0xA1u:
      v67 = sqlite3ExprListAppendVector(a5, 0, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
      goto LABEL_780;
    case 0xA2u:
      sqlite3Insert(
        (_DWORD)a5,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 - 40),
        *(_DWORD *)(v5 - 112),
        *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xA3u:
      sqlite3Insert((_DWORD)a5, *(_QWORD *)(v5 - 88), 0, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 - 136), 0);
      goto LABEL_781;
    case 0xA5u:
      *(_QWORD *)(v5 - 16) = 0;
      goto LABEL_437;
    case 0xA6u:
      v173 = *(_QWORD *)(v5 + 8);
      v174 = *(_QWORD *)(v5 - 40);
      v175 = *(_QWORD *)(v5 - 136);
      v176 = *(_QWORD *)(v5 - 184);
      *(_QWORD *)&v361 = *(_QWORD *)(v5 - 16);
      v177 = *a5;
      if ( *a5 )
        v178 = sqlite3DbMallocRawNN(*a5, 88);
      else
        v178 = sqlite3Malloc(88);
      if ( v178 )
      {
        *(_OWORD *)(v178 + 41) = 0;
        *(_OWORD *)(v178 + 57) = 0;
        *(_OWORD *)(v178 + 72) = 0;
        *(_QWORD *)v178 = v176;
        *(_QWORD *)(v178 + 8) = v175;
        *(_QWORD *)(v178 + 16) = v174;
        *(_QWORD *)(v178 + 24) = v361;
        *(_BYTE *)(v178 + 40) = v174 != 0;
        *(_QWORD *)(v178 + 32) = v173;
        *(_QWORD *)(v5 - 256) = v178;
      }
      else
      {
        if ( v176 )
          exprListDeleteNN(v177, v176);
        if ( v175 )
          sqlite3ExprDeleteNN(v177, v175);
        if ( v174 )
          exprListDeleteNN(v177, v174);
        if ( (_QWORD)v361 )
          sqlite3ExprDeleteNN(v177, v361);
        if ( v173 )
          upsertDelete(v177, v173);
        *(_QWORD *)(v5 - 256) = 0;
      }
      goto LABEL_781;
    case 0xA7u:
      v179 = *(_QWORD *)(v5 + 8);
      v180 = *(_QWORD *)(v5 - 64);
      v181 = *(_QWORD *)(v5 - 112);
      v182 = *a5;
      if ( *a5 )
        v183 = sqlite3DbMallocRawNN(*a5, 88);
      else
        v183 = sqlite3Malloc(88);
      if ( v183 )
      {
        *(_OWORD *)(v183 + 41) = 0;
        *(_OWORD *)(v183 + 57) = 0;
        *(_OWORD *)(v183 + 72) = 0;
        *(_QWORD *)v183 = v181;
        *(_QWORD *)(v183 + 16) = 0;
        *(_QWORD *)(v183 + 24) = 0;
        *(_QWORD *)(v183 + 8) = v180;
        *(_BYTE *)(v183 + 40) = 0;
        *(_QWORD *)(v183 + 32) = v179;
        *(_QWORD *)(v5 - 184) = v183;
      }
      else
      {
        if ( v181 )
          exprListDeleteNN(v182, v181);
        if ( v180 )
          sqlite3ExprDeleteNN(v182, v180);
        if ( v179 )
          upsertDelete(v182, v179);
        *(_QWORD *)(v5 - 184) = 0;
      }
      goto LABEL_781;
    case 0xA8u:
      if ( *a5 )
        v67 = sqlite3DbMallocRawNN(*a5, 88);
      else
        v67 = sqlite3Malloc(88);
      if ( v67 )
      {
        *(_OWORD *)(v67 + 41) = 0;
        *(_OWORD *)(v67 + 57) = 0;
        *(_OWORD *)(v67 + 72) = 0;
        *(_QWORD *)v67 = 0;
        *(_QWORD *)(v67 + 8) = 0;
        *(_QWORD *)(v67 + 16) = 0;
        *(_QWORD *)(v67 + 24) = 0;
        *(_BYTE *)(v67 + 40) = 0;
        *(_QWORD *)(v67 + 32) = 0;
      }
      else
      {
        v67 = 0;
      }
      goto LABEL_780;
    case 0xA9u:
      v184 = *(_QWORD *)(v5 - 16);
      v185 = *(_QWORD *)(v5 - 40);
      v186 = *a5;
      if ( *a5 )
        v187 = sqlite3DbMallocRawNN(*a5, 88);
      else
        v187 = sqlite3Malloc(88);
      if ( v187 )
      {
        *(_OWORD *)(v187 + 41) = 0;
        *(_OWORD *)(v187 + 57) = 0;
        *(_OWORD *)(v187 + 72) = 0;
        *(_QWORD *)v187 = 0;
        *(_QWORD *)(v187 + 8) = 0;
        *(_QWORD *)(v187 + 16) = v185;
        *(_QWORD *)(v187 + 24) = v184;
        *(_BYTE *)(v187 + 40) = v185 != 0;
        *(_QWORD *)(v187 + 32) = 0;
        *(_QWORD *)(v5 - 160) = v187;
      }
      else
      {
        if ( v185 )
          exprListDeleteNN(v186, v185);
        if ( v184 )
          sqlite3ExprDeleteNN(v186, v184);
        *(_QWORD *)(v5 - 160) = 0;
      }
      goto LABEL_781;
    case 0xAAu:
LABEL_437:
      sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xAEu:
    case 0xB1u:
    case 0xEAu:
    case 0xEFu:
      *(_QWORD *)(v5 - 40) = *(_QWORD *)(v5 - 16);
      goto LABEL_781;
    case 0xAFu:
      *(_QWORD *)(v5 - 40) = sqlite3IdListAppend(a5, *(_QWORD *)(v5 - 40), v5 + 8);
      goto LABEL_781;
    case 0xB0u:
      *(_QWORD *)(v5 + 8) = sqlite3IdListAppend(a5, 0, v5 + 8);
      goto LABEL_781;
    case 0xB2u:
      *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
      *(_QWORD *)(v5 + 8) = tokenExpr(a5, 59, Src);
      goto LABEL_781;
    case 0xB3u:
      *(_OWORD *)Src = *(_OWORD *)(v5 - 40);
      v188 = tokenExpr(a5, 59, Src);
      *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
      v189 = tokenExpr(a5, 59, Src);
      *(_QWORD *)(v5 - 40) = sqlite3PExpr(a5, 141, v188, v189);
      goto LABEL_781;
    case 0xB4u:
      *(_OWORD *)Src = *(_OWORD *)(v5 - 88);
      v190 = tokenExpr(a5, 59, Src);
      *(_OWORD *)Src = *(_OWORD *)(v5 - 40);
      v191 = tokenExpr(a5, 59, Src);
      *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
      v192 = tokenExpr(a5, 59, Src);
      v193 = sqlite3PExpr(a5, 141, v191, v192);
      if ( *((_BYTE *)a5 + 300) >= 2u )
        sqlite3RenameTokenRemap(a5, 0, v190, v193);
      v67 = sqlite3PExpr(a5, 141, v190, v193);
      goto LABEL_780;
    case 0xB5u:
    case 0xB6u:
      v194 = *(unsigned __int16 *)(v5 + 2);
      *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
      *(_QWORD *)(v5 + 8) = tokenExpr(a5, v194, Src);
      goto LABEL_781;
    case 0xB7u:
      v195 = sqlite3ExprAlloc(*a5, 155, v5 + 8, 1);
      if ( v195 )
        *(_DWORD *)(v195 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 84);
      *(_QWORD *)(v5 + 8) = v195;
      goto LABEL_781;
    case 0xB8u:
      v196 = *(_BYTE **)(v5 + 8);
      if ( *v196 == 35 && (*((_BYTE *)&qword_1801147A0 + (unsigned __int8)v196[1]) & 4) != 0 )
      {
        v73 = *((_BYTE *)a5 + 30) == 0;
        *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
        if ( v73 )
        {
          sqlite3ErrorMsg(a5, "near \"%T\": syntax error", Src);
          *(_QWORD *)(v5 + 8) = 0;
        }
        else
        {
          v197 = sqlite3PExpr(a5, 176, 0, 0);
          *(_QWORD *)(v5 + 8) = v197;
          if ( v197 )
            sqlite3GetInt32((char *)Src[0] + 1, v197 + 44);
        }
      }
      else
      {
        v198 = *(_DWORD *)(v5 + 16);
        *(_OWORD *)Src = *(_OWORD *)(v5 + 8);
        v199 = tokenExpr(a5, 156, Src);
        *(_QWORD *)(v5 + 8) = v199;
        sqlite3ExprAssignVarNumber(a5, v199, v198);
      }
      goto LABEL_781;
    case 0xB9u:
      *(_QWORD *)(v5 - 40) = sqlite3ExprAddCollateToken(a5, *(_QWORD *)(v5 - 40), v5 + 8, 1);
      goto LABEL_781;
    case 0xBAu:
      v200 = a5;
      v201 = sqlite3ExprAlloc(*a5, 36, v5 - 16, 1);
      v202 = *(_QWORD *)(v5 - 64);
      v203 = v201;
      *(_QWORD *)(v5 - 112) = v201;
      if ( !v201 )
        goto LABEL_656;
      *(_DWORD *)(v201 + 40) = 1;
      if ( v202 )
      {
        *(_QWORD *)(v201 + 16) = v202;
        *(_DWORD *)(v201 + 4) |= *(_DWORD *)(v202 + 4) & 0x400208;
        v204 = *(_DWORD *)(v202 + 40);
        if ( v204 >= 1 )
          *(_DWORD *)(v203 + 40) = v204 + 1;
      }
      goto LABEL_781;
    case 0xBBu:
      v67 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 16), v5 - 88, *(unsigned int *)(v5 - 40));
      goto LABEL_780;
    case 0xBCu:
      *(_QWORD *)(v5 - 64) = sqlite3ExprFunction(a5, 0, v5 - 64, 0);
      goto LABEL_781;
    case 0xBDu:
      v205 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 40), v5 - 112, *(unsigned int *)(v5 - 64));
      v206 = *(_QWORD *)(v5 + 8);
      v207 = v205;
      if ( v205 )
      {
        *(_DWORD *)(v205 + 4) |= 0x1000000u;
        *(_QWORD *)(v205 + 64) = v206;
        *(_QWORD *)(v206 + 112) = v205;
        if ( (*(_BYTE *)(v205 + 4) & 4) != 0 && *(_BYTE *)(v206 + 32) != 0xA6 )
        {
          sqlite3ErrorMsg(a5, "DISTINCT is not supported for window functions");
          *(_QWORD *)(v5 - 112) = v207;
          goto LABEL_781;
        }
      }
      else
      {
        sqlite3WindowDelete(*a5, v206);
      }
      *(_QWORD *)(v5 - 112) = v207;
      goto LABEL_781;
    case 0xBEu:
      v208 = sqlite3ExprFunction(a5, 0, v5 - 88, 0);
      v209 = *(_QWORD *)(v5 + 8);
      v210 = v208;
      if ( !v208 )
      {
        sqlite3WindowDelete(*a5, v209);
        *(_QWORD *)(v5 - 88) = 0;
        goto LABEL_781;
      }
      *(_DWORD *)(v208 + 4) |= 0x1000000u;
      *(_QWORD *)(v208 + 64) = v209;
      *(_QWORD *)(v209 + 112) = v208;
      if ( (*(_BYTE *)(v208 + 4) & 4) != 0 && *(_BYTE *)(v209 + 32) != 0xA6 )
      {
        sqlite3ErrorMsg(a5, "DISTINCT is not supported for window functions");
        *(_QWORD *)(v5 - 88) = v210;
        goto LABEL_781;
      }
      goto LABEL_788;
    case 0xBFu:
      *(_QWORD *)(v5 + 8) = sqlite3ExprFunction(a5, 0, v5 + 8, 0);
      goto LABEL_781;
    case 0xC0u:
      v211 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
      v212 = sqlite3PExpr(a5, 177, 0, 0);
      *(_QWORD *)(v5 - 88) = v212;
      if ( v212 )
      {
        *(_QWORD *)(v212 + 32) = v211;
        if ( *(_DWORD *)v211 )
          *(_DWORD *)(*(_QWORD *)(v5 - 88) + 4LL) |= *(_DWORD *)(*(_QWORD *)(v211 + 8) + 4LL) & 0x400208;
      }
      else if ( v211 )
      {
        exprListDeleteNN(*a5, v211);
      }
      goto LABEL_781;
    case 0xC1u:
      *(_QWORD *)(v5 - 40) = sqlite3ExprAnd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xC2u:
    case 0xC3u:
    case 0xC4u:
    case 0xC5u:
    case 0xC6u:
    case 0xC7u:
    case 0xC8u:
      v213 = *(_QWORD *)(v5 + 8);
      v214 = *(_QWORD *)(v5 - 40);
      v215 = *(_WORD *)(v5 - 22);
      v60 = sqlite3DbMallocRawNN(*a5, 72);
      if ( v60 )
      {
        *(_OWORD *)v60 = 0;
        *(_OWORD *)(v60 + 16) = 0;
        *(_OWORD *)(v60 + 32) = 0;
        *(_OWORD *)(v60 + 48) = 0;
        *(_QWORD *)(v60 + 64) = 0;
        *(_BYTE *)v60 = v215;
        *(_WORD *)(v60 + 50) = -1;
        if ( v213 )
        {
          *(_QWORD *)(v60 + 24) = v213;
          *(_DWORD *)(v60 + 4) |= *(_DWORD *)(v213 + 4) & 0x400208;
          v216 = *(_DWORD *)(v213 + 40) + 1;
        }
        else
        {
          v216 = 1;
        }
        *(_DWORD *)(v60 + 40) = v216;
        if ( v214 )
        {
          *(_QWORD *)(v60 + 16) = v214;
          *(_DWORD *)(v60 + 4) |= *(_DWORD *)(v214 + 4) & 0x400208;
          v217 = *(_DWORD *)(v214 + 40);
          if ( v217 >= v216 )
          {
            v216 = v217 + 1;
            *(_DWORD *)(v60 + 40) = v217 + 1;
          }
        }
        v218 = *(_DWORD *)(*a5 + 148LL);
        if ( v216 > v218 )
        {
          sqlite3ErrorMsg(a5, "Expression tree is too large (maximum depth %d)", v218);
          *(_QWORD *)(v5 - 40) = v60;
          goto LABEL_781;
        }
      }
      else
      {
        if ( v214 )
          sqlite3ExprDeleteNN(*a5, v214);
        if ( v213 )
          sqlite3ExprDeleteNN(*a5, v213);
      }
LABEL_538:
      *(_QWORD *)(v5 - 40) = v60;
      goto LABEL_781;
    case 0xC9u:
      *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) |= 0x80000000;
      goto LABEL_781;
    case 0xCAu:
      v219 = *(_DWORD *)(v5 - 8);
      v220 = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 8) = v219 & 0x7FFFFFFF;
      v221 = sqlite3ExprListAppendNew(*a5, v220);
      v222 = sqlite3ExprListAppend(a5, v221, *(_QWORD *)(v5 - 40));
      v223 = sqlite3ExprFunction(a5, v222, v5 - 16, 0);
      *(_QWORD *)(v5 - 40) = v223;
      if ( v219 < 0 )
      {
        v223 = sqlite3PExpr(a5, 19, v223, 0);
        *(_QWORD *)(v5 - 40) = v223;
      }
      goto LABEL_544;
    case 0xCBu:
      v224 = *(_DWORD *)(v5 - 56);
      v225 = *(_QWORD *)(v5 - 40);
      *(_DWORD *)(v5 - 56) = v224 & 0x7FFFFFFF;
      v226 = sqlite3ExprListAppendNew(*a5, v225);
      v227 = sqlite3ExprListAppend(a5, v226, *(_QWORD *)(v5 - 88));
      v228 = sqlite3ExprListAppend(a5, v227, *(_QWORD *)(v5 + 8));
      v223 = sqlite3ExprFunction(a5, v228, v5 - 64, 0);
      *(_QWORD *)(v5 - 88) = v223;
      if ( v224 < 0 )
      {
        v223 = sqlite3PExpr(a5, 19, v223, 0);
        *(_QWORD *)(v5 - 88) = v223;
      }
LABEL_544:
      if ( v223 )
        *(_DWORD *)(v223 + 4) |= 0x100u;
      goto LABEL_781;
    case 0xCCu:
      *(_QWORD *)(v5 - 16) = sqlite3PExpr(a5, *(unsigned __int16 *)(v5 + 2), *(_QWORD *)(v5 - 16), 0);
      goto LABEL_781;
    case 0xCDu:
      *(_QWORD *)(v5 - 40) = sqlite3PExpr(a5, 51, *(_QWORD *)(v5 - 40), 0);
      goto LABEL_781;
    case 0xCEu:
      v229 = a5;
      v230 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      v231 = v230;
      *(_QWORD *)(v5 - 40) = v230;
      goto LABEL_551;
    case 0xCFu:
      v232 = a5;
      v233 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
      v231 = v233;
      *(_QWORD *)(v5 - 64) = v233;
      goto LABEL_557;
    case 0xD0u:
      v229 = a5;
      v230 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 + 8));
      v231 = v230;
      *(_QWORD *)(v5 - 112) = v230;
LABEL_551:
      if ( !v230 )
        goto LABEL_781;
      v234 = *(_BYTE **)(v5 + 8);
      if ( !v234 || *v234 != 121 || *((_BYTE *)v229 + 300) >= 2u )
        goto LABEL_781;
      v235 = *v229;
      *(_BYTE *)v231 = 50;
      goto LABEL_562;
    case 0xD1u:
      v232 = a5;
      v233 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
      v231 = v233;
      *(_QWORD *)(v5 - 88) = v233;
LABEL_557:
      if ( !v233 )
        goto LABEL_781;
      v236 = *(_BYTE **)(v5 + 8);
      if ( !v236 || *v236 != 121 || *((_BYTE *)v232 + 300) >= 2u )
        goto LABEL_781;
      v235 = *v232;
      *(_BYTE *)v231 = 51;
LABEL_562:
      v237 = *(_QWORD *)(v231 + 24);
      if ( v237 )
        sqlite3ExprDeleteNN(v235, v237);
      *(_QWORD *)(v231 + 24) = 0;
      goto LABEL_781;
    case 0xD2u:
    case 0xD3u:
      v238 = *(_QWORD *)(v5 + 8);
      v239 = *(_WORD *)(v5 - 22);
      v240 = sqlite3DbMallocRawNN(*a5, 72);
      if ( v240 )
      {
        v241 = 1;
        *(_OWORD *)v240 = 0;
        *(_OWORD *)(v240 + 16) = 0;
        *(_OWORD *)(v240 + 32) = 0;
        *(_OWORD *)(v240 + 48) = 0;
        *(_QWORD *)(v240 + 64) = 0;
        *(_BYTE *)v240 = v239;
        *(_WORD *)(v240 + 50) = -1;
        *(_DWORD *)(v240 + 40) = 1;
        if ( v238 )
        {
          *(_QWORD *)(v240 + 16) = v238;
          *(_DWORD *)(v240 + 4) |= *(_DWORD *)(v238 + 4) & 0x400208;
          v242 = *(_DWORD *)(v238 + 40);
          if ( v242 >= 1 )
          {
            v241 = v242 + 1;
            *(_DWORD *)(v240 + 40) = v242 + 1;
          }
        }
        v243 = *(_DWORD *)(*a5 + 148LL);
        if ( v241 > v243 )
        {
          sqlite3ErrorMsg(a5, "Expression tree is too large (maximum depth %d)", v243);
          *(_QWORD *)(v5 - 16) = v240;
          goto LABEL_781;
        }
      }
      else if ( v238 )
      {
        sqlite3ExprDeleteNN(*a5, v238);
      }
LABEL_573:
      *(_QWORD *)(v5 - 16) = v240;
      goto LABEL_781;
    case 0xD4u:
      *(_QWORD *)(v5 - 16) = sqlite3PExpr(a5, (unsigned int)(*(_WORD *)(v5 - 22) == 106) + 173, *(_QWORD *)(v5 + 8), 0);
      goto LABEL_781;
    case 0xD5u:
      v244 = sqlite3ExprListAppendNew(*a5, *(_QWORD *)(v5 - 40));
      v245 = sqlite3ExprListAppend(a5, v244, *(_QWORD *)(v5 + 8));
      *(_QWORD *)(v5 - 40) = sqlite3ExprFunction(a5, v245, v5 - 16, 0);
      goto LABEL_781;
    case 0xD8u:
      v246 = a5;
      v247 = sqlite3ExprListAppendNew(*a5, *(_QWORD *)(v5 - 40));
      v248 = sqlite3ExprListAppend(a5, v247, *(_QWORD *)(v5 + 8));
      v249 = sqlite3PExpr(a5, 48, *(_QWORD *)(v5 - 88), 0);
      *(_QWORD *)(v5 - 88) = v249;
      if ( v249 )
      {
        *(_QWORD *)(v249 + 32) = v248;
      }
      else if ( v248 )
      {
        exprListDeleteNN(*a5, v248);
      }
      goto LABEL_581;
    case 0xDBu:
      v250 = *(_QWORD *)(v5 - 16);
      if ( !v250 )
      {
        sqlite3ExprUnmapAndDelete(a5, *(_QWORD *)(v5 - 88));
        v251 = "false";
        if ( *(_DWORD *)(v5 - 64) )
          v251 = "true";
        v252 = sqlite3Expr(*a5, 117, v251);
        *(_QWORD *)(v5 - 88) = v252;
        if ( v252 )
          sqlite3ExprIdToTrueFalse(v252);
        goto LABEL_781;
      }
      v253 = *(_QWORD *)(v250 + 8);
      if ( *(_DWORD *)v250 == 1
        && (unsigned int)sqlite3ExprIsConstant(*(_QWORD *)(v250 + 8))
        && (v254 = (_QWORD *)(v5 - 88), **(_BYTE **)(v5 - 88) != 0xB1) )
      {
        v255 = a5;
        *(_QWORD *)(*(_QWORD *)(v5 - 16) + 8LL) = 0;
        v256 = *(_QWORD *)(v5 - 16);
        if ( v256 )
          exprListDeleteNN(*a5, v256);
        v257 = sqlite3PExpr(a5, 174, v253, 0);
        *v254 = sqlite3PExpr(a5, 53, *v254, v257);
      }
      else
      {
        if ( **(_DWORD **)(v5 - 16) == 1 && *(_BYTE *)v253 == 0x8A )
        {
          v255 = a5;
          v254 = (_QWORD *)(v5 - 88);
          v258 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
          *(_QWORD *)(v5 - 88) = v258;
          v259 = *(_QWORD *)(v253 + 32);
          if ( v258 )
          {
            *(_DWORD *)(v258 + 4) |= 0x401000u;
            *(_QWORD *)(v258 + 32) = v259;
            sqlite3ExprSetHeightAndFlags(a5, v258);
            *(_QWORD *)(v253 + 32) = 0;
          }
          else
          {
            if ( v259 )
              clearSelect(*a5, v259, 1);
            *(_QWORD *)(v253 + 32) = 0;
          }
        }
        else
        {
          v255 = a5;
          v254 = (_QWORD *)(v5 - 88);
          v260 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
          *(_QWORD *)(v5 - 88) = v260;
          v261 = v260;
          if ( v260 )
          {
            v263 = *(_QWORD *)(v260 + 16);
            if ( *(_BYTE *)v263 == 0xB1 )
            {
              v264 = *(int **)(v263 + 32);
              v265 = *(int **)(v5 - 16);
              v266 = 0;
              Src[0] = v265;
              v267 = *v264;
              v268 = 0;
              v360 = 0;
              LODWORD(v361) = v267;
              if ( *v265 <= 0 )
                goto LABEL_622;
              while ( 1 )
              {
                v269 = *(_BYTE **)&v265[8 * v268 + 2];
                v270 = (_DWORD **)(v269 + 32);
                v271 = *v269 == 0xB1 ? **v270 : 1;
                if ( v271 != v267 )
                  break;
                v272 = sqlite3SelectNew((_DWORD)a5, (unsigned int)*v270, 0, 0, 0, 0, 0, 512, 0);
                *v270 = 0;
                if ( v272 )
                {
                  if ( v266 )
                  {
                    *(_BYTE *)v272 = -121;
                    *(_QWORD *)(v272 + 80) = v266;
                  }
                  v266 = v272;
                }
                v265 = (int *)Src[0];
                v268 = v360 + 1;
                v267 = v361;
                v360 = v268;
                if ( v268 >= *(_DWORD *)Src[0] )
                  goto LABEL_619;
              }
              v273 = byte_180122168;
              if ( v271 > 1 )
                v273 = "s";
              sqlite3ErrorMsg(a5, "IN(...) element has %d term%s - expected %d", v271, v273, v267);
              v265 = (int *)Src[0];
LABEL_619:
              if ( v266 && *(_QWORD *)(v266 + 80) )
              {
                *(_DWORD *)(v266 + 4) |= 0x400u;
                exprListDeleteNN(*a5, v265);
              }
              else
              {
LABEL_622:
                exprListDeleteNN(*a5, v265);
                if ( !v266 )
                  goto LABEL_628;
              }
              parserDoubleLinkSelect(a5, v266);
              v274 = *v254;
              if ( !*v254 )
              {
                clearSelect(*a5, v266, 1);
                goto LABEL_628;
              }
              *(_DWORD *)(v274 + 4) |= 0x401000u;
              *(_QWORD *)(v274 + 32) = v266;
            }
            else
            {
              *(_QWORD *)(v261 + 32) = *(_QWORD *)(v5 - 16);
              v274 = *v254;
            }
            sqlite3ExprSetHeightAndFlags(a5, v274);
            goto LABEL_628;
          }
        }
        v262 = *(_QWORD *)(v5 - 16);
        if ( v262 )
          exprListDeleteNN(*v255, v262);
      }
LABEL_628:
      if ( *(_DWORD *)(v5 - 64) )
        *v254 = sqlite3PExpr(v255, 19, *v254, 0);
      goto LABEL_781;
    case 0xDCu:
      v13 = a5;
      v275 = sqlite3PExpr(a5, 138, 0, 0);
      *(_QWORD *)(v5 - 40) = v275;
      goto LABEL_647;
    case 0xDDu:
      v246 = a5;
      v276 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
      v277 = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(v5 - 88) = v276;
      if ( v276 )
      {
        *(_QWORD *)(v276 + 32) = v277;
        goto LABEL_633;
      }
      if ( v277 )
        clearSelect(*a5, v277, 1);
      goto LABEL_581;
    case 0xDEu:
      v246 = a5;
      v278 = 0;
      v279 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 - 16);
      v280 = sqlite3SelectNew((_DWORD)a5, 0, v279, 0, 0, 0, 0, 0, 0);
      v281 = *(_QWORD *)(v5 + 8);
      v282 = v280;
      if ( v281 )
      {
        if ( v280 )
          v278 = (int *)v279;
        if ( v278 )
        {
          v283 = 26LL * *v278;
          v278[v283 - 8] |= 4u;
          *(_QWORD *)&v278[v283 - 2] = v281;
        }
        else
        {
          exprListDeleteNN(*a5, *(_QWORD *)(v5 + 8));
        }
      }
      v276 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
      *(_QWORD *)(v5 - 88) = v276;
      if ( v276 )
      {
        *(_QWORD *)(v276 + 32) = v282;
LABEL_633:
        *(_DWORD *)(v276 + 4) |= 0x401000u;
        sqlite3ExprSetHeightAndFlags(v246, v276);
      }
      else if ( v282 )
      {
        clearSelect(*a5, v282, 1);
      }
LABEL_581:
      if ( *(_DWORD *)(v5 - 64) )
      {
        v67 = sqlite3PExpr(v246, 19, *(_QWORD *)(v5 - 88), 0);
LABEL_780:
        *(_QWORD *)(v5 - 88) = v67;
      }
      goto LABEL_781;
    case 0xDFu:
      v13 = a5;
      v275 = sqlite3PExpr(a5, 20, 0, 0);
      *(_QWORD *)(v5 - 64) = v275;
LABEL_647:
      v54 = *(_QWORD *)(v5 - 16);
      if ( v275 )
      {
        *(_QWORD *)(v275 + 32) = v54;
        *(_DWORD *)(v275 + 4) |= 0x401000u;
        sqlite3ExprSetHeightAndFlags(v13, v275);
      }
      else
      {
LABEL_144:
        if ( v54 )
          clearSelect(*v13, v54, 1);
      }
      goto LABEL_781;
    case 0xE0u:
      v200 = a5;
      v284 = sqlite3PExpr(a5, 157, *(_QWORD *)(v5 - 64), 0);
      v285 = *(_QWORD *)(v5 - 40);
      *(_QWORD *)(v5 - 88) = v284;
      if ( v284 )
      {
        v286 = *(_QWORD *)(v5 - 16);
        if ( v286 )
          v285 = sqlite3ExprListAppend(a5, v285, v286);
        *(_QWORD *)(*(_QWORD *)(v5 - 88) + 32LL) = v285;
        sqlite3ExprSetHeightAndFlags(a5, *(_QWORD *)(v5 - 88));
      }
      else
      {
        if ( v285 )
          exprListDeleteNN(*a5, v285);
        v202 = *(_QWORD *)(v5 - 16);
LABEL_656:
        if ( v202 )
          sqlite3ExprDeleteNN(*v200, v202);
      }
      goto LABEL_781;
    case 0xE1u:
      v287 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
      v288 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 88) = v287;
      v67 = sqlite3ExprListAppend(a5, v287, v288);
      goto LABEL_780;
    case 0xE2u:
      v289 = sqlite3ExprListAppendNew(*a5, *(_QWORD *)(v5 - 40));
      v290 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 64) = v289;
      *(_QWORD *)(v5 - 64) = sqlite3ExprListAppend(a5, v289, v290);
      goto LABEL_781;
    case 0xE7u:
      *(_QWORD *)(v5 - 40) = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xE8u:
      *(_QWORD *)(v5 + 8) = sqlite3ExprListAppendNew(*a5, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xEBu:
      v291 = *(_DWORD *)(v5 - 184);
      v292 = *(_QWORD *)(v5 + 8);
      v293 = *(_DWORD *)(v5 - 232);
      v294 = *(_DWORD **)(v5 - 40);
      v295 = (_QWORD *)sqlite3SrcListAppend(a5, 0, v5 - 88, 0);
      sqlite3CreateIndex(a5, v5 - 160, v5 - 136, v295, v294, v293, v5 - 256, v292, 0, v291, 0);
      if ( *((_BYTE *)a5 + 300) >= 2u )
      {
        v296 = (_QWORD *)a5[44];
        if ( v296 )
          sqlite3RenameTokenMap(a5, *v296, v5 - 88);
      }
      goto LABEL_781;
    case 0xF0u:
      v67 = parserAddExprIdListTerm(
              (_DWORD)a5,
              *(_QWORD *)(v5 - 88),
              (int)v5 - 40,
              *(_DWORD *)(v5 - 16),
              *(_DWORD *)(v5 + 8));
      goto LABEL_780;
    case 0xF1u:
      *(_QWORD *)(v5 - 40) = parserAddExprIdListTerm(
                               (_DWORD)a5,
                               0,
                               (int)v5 - 40,
                               *(_DWORD *)(v5 - 16),
                               *(_DWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xF4u:
      sqlite3DropIndex(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_781;
    case 0xF5u:
      sqlite3Vacuum(a5, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xF6u:
      sqlite3Vacuum(a5, v5 - 16, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0xF9u:
      sqlite3Pragma((_DWORD)a5, v5 - 16, v5 + 8, 0, 0);
      goto LABEL_781;
    case 0xFAu:
      sqlite3Pragma((_DWORD)a5, v5 - 64, v5 - 40, v5 + 8, 0);
      goto LABEL_781;
    case 0xFBu:
      sqlite3Pragma((_DWORD)a5, v5 - 88, v5 - 64, v5 - 16, 0);
      goto LABEL_781;
    case 0xFCu:
      v297 = v5 + 8;
      v298 = v5 - 40;
      v299 = v5 - 64;
      goto LABEL_678;
    case 0xFDu:
      v297 = v5 - 16;
      v298 = v5 - 64;
      v299 = v5 - 88;
LABEL_678:
      sqlite3Pragma((_DWORD)a5, v299, v298, v297, 1);
      goto LABEL_781;
    case 0x100u:
      v300 = *(_QWORD *)(v5 - 16);
      v301 = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_QWORD *)(v5 - 64);
      Src[0] = *(void **)(v5 - 64);
      LODWORD(Src[1]) = v301;
      sqlite3FinishTrigger(a5, v300, Src);
      goto LABEL_781;
    case 0x101u:
      sqlite3BeginTrigger(
        a5,
        v5 - 160,
        v5 - 136,
        *(_DWORD *)(v5 - 112),
        *(_DWORD *)(v5 - 88),
        *(_DWORD **)(v5 - 80),
        *(_QWORD *)(v5 - 40),
        *(_QWORD *)(v5 + 8),
        *(_DWORD *)(v5 - 232),
        *(_DWORD *)(v5 - 184));
      v302 = 160;
      if ( *(_DWORD *)(v5 - 128) )
        v302 = 136;
      *(_OWORD *)(v5 - 232) = *(_OWORD *)(v5 - v302);
      goto LABEL_781;
    case 0x103u:
      *(_DWORD *)(v5 - 16) = 65;
      goto LABEL_781;
    case 0x104u:
      *(_DWORD *)(v5 + 32) = 33;
      goto LABEL_781;
    case 0x105u:
    case 0x106u:
      *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
      *(_QWORD *)(v5 + 16) = 0;
      goto LABEL_781;
    case 0x107u:
      *(_QWORD *)(v5 - 32) = *(_QWORD *)(v5 + 8);
      *(_DWORD *)(v5 - 40) = 129;
      goto LABEL_781;
    case 0x10Au:
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) + 80LL) = *(_QWORD *)(v5 - 16);
      *(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_781;
    case 0x10Bu:
      *(_QWORD *)(*(_QWORD *)(v5 - 16) + 88LL) = *(_QWORD *)(v5 - 16);
      goto LABEL_781;
    case 0x10Cu:
      *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
      sqlite3ErrorMsg(
        a5,
        "qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers");
      goto LABEL_781;
    case 0x10Du:
      sqlite3ErrorMsg(a5, "the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_781;
    case 0x10Eu:
      sqlite3ErrorMsg(a5, "the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers");
      goto LABEL_781;
    case 0x10Fu:
      *(_QWORD *)(v5 - 184) = sqlite3TriggerUpdateStep(
                                (_DWORD)a5,
                                (int)v5 - 136,
                                *(_QWORD *)(v5 - 40),
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 - 16),
                                *(_BYTE *)(v5 - 160),
                                *(_QWORD *)(v5 - 184),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x110u:
      *(_QWORD *)(v5 - 160) = sqlite3TriggerInsertStep(
                                (_DWORD)a5,
                                (int)v5 - 88,
                                *(_QWORD *)(v5 - 64),
                                *(_QWORD *)(v5 - 40),
                                *(_BYTE *)(v5 - 136),
                                *(_QWORD *)(v5 - 16),
                                *(_QWORD *)(v5 - 160),
                                *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x111u:
      v303 = *(_QWORD *)(v5 - 16);
      LOBYTE(a2) = 0x80;
      v304 = v303;
      v305 = *a5;
      v306 = triggerStepAllocate((_DWORD)a5, a2, (int)v5 - 64, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 + 8));
      v307 = v306;
      if ( v306 )
      {
        if ( *((_BYTE *)a5 + 300) < 2u )
        {
          if ( v303 )
            v303 = exprDup(v305, v303, 1, 0);
          else
            v303 = 0;
          v306 = v307;
        }
        else
        {
          v304 = 0;
        }
        *(_QWORD *)(v306 + 40) = v303;
        *(_BYTE *)(v307 + 1) = 11;
      }
      if ( v304 )
        sqlite3ExprDeleteNN(v305, v304);
      *(_QWORD *)(v5 - 112) = v307;
      goto LABEL_781;
    case 0x112u:
      v308 = *(_QWORD *)(v5 + 8);
      v309 = *(_QWORD *)(v5 - 40);
      v310 = *(_QWORD *)(v5 - 16);
      v311 = *a5;
      if ( *a5 )
        v312 = sqlite3DbMallocRawNN(*a5, 96);
      else
        v312 = sqlite3Malloc(96);
      v313 = v312;
      if ( v312 )
      {
        *(_OWORD *)v312 = 0;
        *(_OWORD *)(v312 + 16) = 0;
        *(_OWORD *)(v312 + 32) = 0;
        *(_OWORD *)(v312 + 48) = 0;
        *(_OWORD *)(v312 + 64) = 0;
        *(_OWORD *)(v312 + 80) = 0;
        *(_WORD *)v312 = 2954;
        *(_QWORD *)(v312 + 16) = v310;
        *(_QWORD *)(v312 + 72) = triggerSpanDup(v311, v309, v308);
        *(_QWORD *)(v5 - 40) = v313;
      }
      else
      {
        if ( v310 )
          clearSelect(v311, v310, 1);
LABEL_714:
        *(_QWORD *)(v5 - 40) = 0;
      }
      goto LABEL_781;
    case 0x113u:
      v314 = sqlite3PExpr(a5, 71, 0, 0);
      *(_QWORD *)(v5 - 64) = v314;
      if ( v314 )
        *(_BYTE *)(v314 + 1) = 4;
      goto LABEL_781;
    case 0x114u:
      v315 = sqlite3ExprAlloc(*a5, 71, v5 - 16, 1);
      *(_QWORD *)(v5 - 112) = v315;
      if ( v315 )
        *(_BYTE *)(v315 + 1) = *(_BYTE *)(v5 - 64);
      goto LABEL_781;
    case 0x117u:
      *(_DWORD *)(v5 + 8) = 3;
      goto LABEL_781;
    case 0x118u:
      sqlite3DropTrigger(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
      goto LABEL_781;
    case 0x119u:
      codeAttach(
        (_DWORD)a5,
        24,
        (unsigned int)qword_18010F730,
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 64),
        *(_QWORD *)(v5 - 16),
        *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x11Au:
      sqlite3Detach(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x11Du:
      sqlite3Reindex(a5, 0, 0);
      goto LABEL_781;
    case 0x11Eu:
      sqlite3Reindex(a5, v5 - 16, v5 + 8);
      goto LABEL_781;
    case 0x11Fu:
      sqlite3Analyze(a5, 0, 0);
      goto LABEL_781;
    case 0x120u:
      sqlite3Analyze(a5, v5 - 16, v5 + 8);
      goto LABEL_781;
    case 0x121u:
      sqlite3AlterRenameTable((__int64)a5, *(_QWORD **)(v5 - 64), v5 + 8);
      goto LABEL_781;
    case 0x122u:
      *(_DWORD *)(v5 - 8) = *((_DWORD *)a5 + 70) + *((_DWORD *)a5 + 72) - *(_DWORD *)(v5 - 16);
      sqlite3AlterFinishAddColumn();
      goto LABEL_781;
    case 0x123u:
      sqlite3AlterDropColumn(a5, *(_QWORD *)(v5 - 64), v5 + 8);
      goto LABEL_781;
    case 0x124u:
      ++*((_BYTE *)a5 + 36);
      v316 = *a5;
      ++*(_DWORD *)(v316 + 416);
      *(_WORD *)(v316 + 420) = 0;
      sqlite3AlterBeginAddColumn(a5, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x125u:
      sqlite3AlterRenameColumn((__int64)a5, *(_QWORD **)(v5 - 112), v5 - 40, v5 + 8);
      goto LABEL_781;
    case 0x126u:
      sqlite3VtabFinishParse(a5, 0);
      goto LABEL_781;
    case 0x127u:
      sqlite3VtabFinishParse(a5, v5 + 8);
      goto LABEL_781;
    case 0x128u:
      sqlite3StartTable((_DWORD)a5, v5 - 64, v5 - 40, 0, 0, 1, *(_DWORD *)(v5 - 88));
      v317 = a5[43];
      if ( v317 )
      {
        *(_BYTE *)(v317 + 63) = 1;
        v318 = (_DWORD *)(v5 + 8);
        v319 = *a5;
        v320 = sqlite3NameFromToken(*a5, v5 + 8);
        addModuleArgument(a5, v317, v320);
        addModuleArgument(a5, v317, 0);
        v321 = *(void **)v317;
        Src[0] = v321;
        if ( v321 )
        {
          v323 = strlen_0((const char *)v321);
          v324 = v323 + 1;
          if ( v319 )
            v325 = (void *)sqlite3DbMallocRawNN(v319, v323 + 1);
          else
            v325 = (void *)sqlite3Malloc(v323 + 1);
          v322 = v325;
          if ( v325 )
            memcpy_0(v325, Src[0], v324);
          v318 = (_DWORD *)(v5 + 8);
        }
        else
        {
          v322 = 0;
        }
        addModuleArgument(a5, v317, v322);
        *((_DWORD *)a5 + 68) = *v318 + v318[2] - *((_DWORD *)a5 + 66);
        v326 = *(_QWORD **)(v317 + 72);
        if ( v326 )
        {
          v327 = *(_QWORD *)(v317 + 96);
          v328 = -32768;
          if ( v327 )
          {
            v329 = *(_QWORD *)(v319 + 32);
            v328 = 0;
            if ( *(_QWORD *)(v329 + 24) != v327 )
            {
              do
                ++v328;
              while ( *(_QWORD *)(32LL * v328 + v329 + 24) != v327 );
            }
          }
          sqlite3AuthCheck((_DWORD)a5, 29, *(_QWORD *)v317, *v326, *(_QWORD *)(32LL * v328 + *(_QWORD *)(*a5 + 32LL)));
        }
      }
      goto LABEL_781;
    case 0x129u:
      addArgumentToVtab(a5);
      a5[47] = 0;
      *((_DWORD *)a5 + 96) = 0;
      goto LABEL_781;
    case 0x12Au:
    case 0x12Bu:
    case 0x12Cu:
      v330 = a5[47];
      if ( v330 )
      {
        v331 = *(_DWORD *)(v5 + 16) + *(_DWORD *)(v5 + 8) - v330;
      }
      else
      {
        a5[47] = *(_QWORD *)(v5 + 8);
        v331 = *(_DWORD *)(v5 + 16);
      }
      *((_DWORD *)a5 + 96) = v331;
      goto LABEL_781;
    case 0x12Du:
    case 0x12Eu:
      if ( *(_QWORD *)(v5 + 8) )
      {
        v332 = sqlite3ParserAddCleanup(a5, sqlite3WithDelete);
        if ( v332 )
        {
          if ( !*((_DWORD *)a5 + 12) )
          {
            *(_QWORD *)(v332 + 8) = a5[50];
            a5[50] = v332;
          }
        }
      }
      goto LABEL_781;
    case 0x12Fu:
      *(_BYTE *)(v5 + 8) = 1;
      goto LABEL_781;
    case 0x130u:
      *(_BYTE *)(v5 - 16) = 0;
      goto LABEL_781;
    case 0x131u:
      *(_BYTE *)(v5 - 40) = 2;
      goto LABEL_781;
    case 0x132u:
      v333 = *(_BYTE *)(v5 - 64);
      v334 = *(_QWORD *)(v5 - 16);
      v335 = *(_QWORD *)(v5 - 88);
      v336 = *a5;
      if ( *a5 )
        v337 = sqlite3DbMallocRawNN(*a5, 48);
      else
        v337 = sqlite3Malloc(48);
      v338 = v337;
      if ( v337 )
      {
        *(_OWORD *)v337 = 0;
        *(_OWORD *)(v337 + 16) = 0;
        *(_OWORD *)(v337 + 32) = 0;
      }
      if ( *(_BYTE *)(v336 + 103) )
      {
        if ( v335 )
          exprListDeleteNN(v336, v335);
        if ( v334 )
          clearSelect(v336, v334, 1);
        *(_QWORD *)(v5 - 112) = v338;
      }
      else
      {
        *(_QWORD *)(v337 + 16) = v334;
        *(_QWORD *)(v337 + 8) = v335;
        *(_QWORD *)v337 = sqlite3NameFromToken(*a5, v5 - 112);
        *(_BYTE *)(v338 + 40) = v333;
        *(_QWORD *)(v5 - 112) = v338;
      }
      goto LABEL_781;
    case 0x133u:
      *(_QWORD *)(v5 + 8) = sqlite3WithAdd(a5, 0, *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x134u:
      *(_QWORD *)(v5 - 40) = sqlite3WithAdd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
      goto LABEL_781;
    case 0x135u:
      sqlite3WindowChain(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40));
      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 64LL) = *(_QWORD *)(v5 - 40);
LABEL_776:
      *(_QWORD *)(v5 - 40) = *(_QWORD *)(v5 + 8);
      goto LABEL_781;
    case 0x136u:
      v339 = *(_QWORD **)(v5 - 16);
      if ( v339 )
        *v339 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 - 88), *(unsigned int *)(v5 - 80));
      goto LABEL_779;
    case 0x137u:
      v210 = *(_QWORD *)(v5 + 8);
      v344 = *(_QWORD *)(v5 - 16);
      v345 = *(_QWORD *)(v5 - 40);
      if ( v210 )
      {
        *(_QWORD *)(v210 + 16) = v345;
        *(_QWORD *)(v210 + 24) = v344;
        *(_QWORD *)(v5 - 88) = v210;
      }
      else
      {
        if ( v345 )
          exprListDeleteNN(*a5, v345);
        if ( v344 )
          exprListDeleteNN(*a5, v344);
LABEL_788:
        *(_QWORD *)(v5 - 88) = v210;
      }
      goto LABEL_781;
    case 0x138u:
      v346 = *(_QWORD *)(v5 - 16);
      v347 = (_QWORD *)(v5 - 112);
      v348 = *(_QWORD *)(v5 - 40);
      goto LABEL_798;
    case 0x139u:
      v349 = *(_QWORD *)(v5 + 8);
      v350 = *(_QWORD *)(v5 - 16);
      if ( v349 )
      {
        *(_QWORD *)(v349 + 24) = v350;
        *(_QWORD *)(v349 + 16) = 0;
        *(_QWORD *)(v5 - 64) = v349;
      }
      else
      {
        if ( v350 )
          exprListDeleteNN(*a5, v350);
        *(_QWORD *)(v5 - 64) = 0;
      }
      goto LABEL_781;
    case 0x13Au:
      v346 = *(_QWORD *)(v5 - 16);
      v347 = (_QWORD *)(v5 - 88);
      goto LABEL_797;
    case 0x13Bu:
      v347 = (_QWORD *)(v5 - 16);
      LODWORD(v346) = 0;
LABEL_797:
      LODWORD(v348) = 0;
LABEL_798:
      *v347 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), v348, v346, (__int64)v347);
      goto LABEL_781;
    case 0x13Cu:
      *(_QWORD *)(v5 + 32) = sqlite3WindowAlloc((_DWORD)a5, 0, 90, 0, 85, 0, 0);
      goto LABEL_781;
    case 0x13Du:
      *(_QWORD *)(v5 - 40) = sqlite3WindowAlloc(
                               (_DWORD)a5,
                               *(_DWORD *)(v5 - 40),
                               *(_DWORD *)(v5 - 16),
                               *(_QWORD *)(v5 - 8),
                               85,
                               0,
                               *(_BYTE *)(v5 + 8));
      goto LABEL_781;
    case 0x13Eu:
      *(_QWORD *)(v5 - 112) = sqlite3WindowAlloc(
                                (_DWORD)a5,
                                *(_DWORD *)(v5 - 112),
                                *(_DWORD *)(v5 - 64),
                                *(_QWORD *)(v5 - 56),
                                *(_DWORD *)(v5 - 16),
                                *(_QWORD *)(v5 - 8),
                                *(_BYTE *)(v5 + 8));
      goto LABEL_781;
    case 0x141u:
    case 0x143u:
    case 0x145u:
      LODWORD(Src[0]) = *(unsigned __int16 *)(v5 - 22);
      *(void **)(v5 - 16) = Src[0];
      *(_QWORD *)(v5 - 8) = 0;
      goto LABEL_781;
    case 0x144u:
      v351 = *(_QWORD *)(v5 - 16);
      LODWORD(Src[0]) = *(unsigned __int16 *)(v5 + 2);
      *(void **)(v5 - 16) = Src[0];
      *(_QWORD *)(v5 - 8) = v351;
      goto LABEL_781;
    case 0x146u:
      *(_BYTE *)(v5 + 32) = 0;
      goto LABEL_781;
    case 0x147u:
      *(_BYTE *)(v5 - 16) = *(_BYTE *)(v5 + 8);
      goto LABEL_781;
    case 0x148u:
    case 0x149u:
      *(_BYTE *)(v5 - 16) = *(_BYTE *)(v5 - 22);
      goto LABEL_781;
    case 0x14Au:
      *(_BYTE *)(v5 + 8) = *(_BYTE *)(v5 + 2);
      goto LABEL_781;
    case 0x14Cu:
      v352 = *(_QWORD *)(v5 + 8);
      v353 = *(_QWORD *)(v5 - 16);
      if ( v352 )
      {
        *(_QWORD *)(v352 + 72) = v353;
        *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      }
      else
      {
        if ( v353 )
          sqlite3ExprDeleteNN(*a5, v353);
LABEL_812:
        *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
      }
      goto LABEL_781;
    case 0x14Eu:
      if ( *a5 )
        v354 = sqlite3DbMallocRawNN(*a5, 144);
      else
        v354 = sqlite3Malloc(144);
      v153 = v354;
      if ( v354 )
      {
        *(_OWORD *)v354 = 0;
        *(_OWORD *)(v354 + 16) = 0;
        *(_OWORD *)(v354 + 32) = 0;
        *(_OWORD *)(v354 + 48) = 0;
        *(_OWORD *)(v354 + 64) = 0;
        *(_OWORD *)(v354 + 80) = 0;
        *(_OWORD *)(v354 + 96) = 0;
        *(_OWORD *)(v354 + 112) = 0;
        *(_OWORD *)(v354 + 128) = 0;
        *(_BYTE *)(v354 + 32) = -90;
        *(_QWORD *)(v354 + 72) = *(_QWORD *)(v5 + 8);
        *(_QWORD *)(v5 + 8) = v354;
      }
      else
      {
        v355 = *(_QWORD *)(v5 + 8);
        if ( v355 )
          sqlite3ExprDeleteNN(*a5, v355);
LABEL_820:
        *(_QWORD *)(v5 + 8) = v153;
      }
      goto LABEL_781;
    case 0x14Fu:
      *(_QWORD *)(v5 - 64) = *(_QWORD *)(v5 - 16);
      goto LABEL_781;
    case 0x150u:
      if ( *a5 )
        v356 = (_OWORD *)sqlite3DbMallocRawNN(*a5, 144);
      else
        v356 = (_OWORD *)sqlite3Malloc(144);
      v240 = (__int64)v356;
      if ( !v356 )
        goto LABEL_573;
      *v356 = 0;
      v356[1] = 0;
      v356[2] = 0;
      v356[3] = 0;
      v356[4] = 0;
      v356[5] = 0;
      v356[6] = 0;
      v356[7] = 0;
      v356[8] = 0;
      v357 = *(unsigned int *)(v5 + 16);
      v358 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 - 16) = v356;
      *(_QWORD *)v356 = sqlite3DbStrNDup(*a5, v358, v357);
      goto LABEL_781;
    case 0x151u:
LABEL_779:
      v67 = *(_QWORD *)(v5 - 16);
      goto LABEL_780;
    default:
      goto LABEL_781;
  }
}

```

## disassembly

```asm
0x1800d8b00  mov     rax, rsp
0x1800d8b03  mov     [rax+10h], edx
0x1800d8b06  mov     [rax+8], rcx
0x1800d8b0a  push    rbp
0x1800d8b0b  push    rbx
0x1800d8b0c  lea     rbp, [rax-57h]
0x1800d8b10  sub     rsp, 0E8h
0x1800d8b17  mov     rbx, [rcx]
0x1800d8b1a  lea     r11, cs:180000000h
0x1800d8b21  cmp     edx, 151h; switch 338 cases
0x1800d8b27  ja      def_1800D8B52; jumptable 00000001800D8B52 default case
0x1800d8b2d  mov     [rax+18h], rsi
0x1800d8b31  mov     [rax-18h], rdi
0x1800d8b35  mov     [rax-20h], r12
0x1800d8b39  mov     [rax-28h], r13
0x1800d8b3d  mov     [rax-30h], r14
0x1800d8b41  mov     [rax-38h], r15
0x1800d8b45  mov     eax, edx
0x1800d8b47  mov     r8d, ds:(jpt_1800D8B52 - 180000000h)[r11+rax*4]
0x1800d8b4f  add     r8, r11
0x1800d8b52  jmp     r8; switch jump
0x1800d8b55  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 0
0x1800d8b59  cmp     qword ptr [rax+148h], 0
0x1800d8b61  jnz     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8b67  mov     byte ptr [rax+12Bh], 1
0x1800d8b6e  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8b73  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 1
0x1800d8b77  cmp     qword ptr [rax+148h], 0
0x1800d8b7f  jnz     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8b85  mov     byte ptr [rax+12Bh], 2
0x1800d8b8c  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8b91  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 2
0x1800d8b95  call    sqlite3FinishCoding
0x1800d8b9a  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8b9f  mov     edx, [rbx-10h]; jumptable 00000001800D8B52 case 3
0x1800d8ba2  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8ba6  call    sqlite3BeginTransaction
0x1800d8bab  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8bb0  mov     dword ptr [rbx+20h], 7; jumptable 00000001800D8B52 case 4
0x1800d8bb7  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8bbc  mov     rdi, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 cases 8,9
0x1800d8bc0  lea     rcx, aRollback; "ROLLBACK"
0x1800d8bc7  xor     esi, esi
0x1800d8bc9  lea     r8, aCommit; "COMMIT"
0x1800d8bd0  cmp     word ptr [rbx-16h], 0Ch
0x1800d8bd5  mov     r14d, esi
0x1800d8bd8  mov     edx, 16h
0x1800d8bdd  mov     [rsp+0F0h+var_D0], rsi
0x1800d8be2  cmovz   r8, rcx
0x1800d8be6  setz    r14b
0x1800d8bea  xor     r9d, r9d
0x1800d8bed  mov     rcx, rdi
0x1800d8bf0  call    sqlite3AuthCheck
0x1800d8bf5  test    eax, eax
0x1800d8bf7  jnz     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8bfd  mov     r10, [rdi+10h]
0x1800d8c01  test    r10, r10
0x1800d8c04  jnz     short loc_1800D8C30
0x1800d8c06  cmp     [rdi+0A8h], rsi
0x1800d8c0d  jnz     short loc_1800D8C1C
0x1800d8c0f  mov     rax, [rdi]
0x1800d8c12  test    byte ptr [rax+60h], 8
0x1800d8c16  jnz     short loc_1800D8C1C
0x1800d8c18  mov     byte ptr [rdi+23h], 1
0x1800d8c1c  mov     rcx, rdi
0x1800d8c1f  call    sqlite3VdbeCreate
0x1800d8c24  mov     r10, rax
0x1800d8c27  test    rax, rax
0x1800d8c2a  jz      loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8c30  movsxd  rcx, dword ptr [r10+90h]
0x1800d8c37  cmp     [r10+94h], ecx
0x1800d8c3e  jg      short loc_1800D8C60
0x1800d8c40  mov     r15d, 1
0x1800d8c46  mov     dword ptr [rsp+0F0h+var_D0], esi
0x1800d8c4a  mov     r8d, r15d
0x1800d8c4d  mov     edx, r15d
0x1800d8c50  mov     r9d, r14d
0x1800d8c53  mov     rcx, r10
0x1800d8c56  call    growOp3
0x1800d8c5b  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8c60  lea     eax, [rcx+1]
0x1800d8c63  mov     [r10+90h], eax
0x1800d8c6a  lea     rcx, [rcx+rcx*2]
0x1800d8c6e  mov     rax, [r10+88h]
0x1800d8c75  mov     dword ptr [rax+rcx*8], 1
0x1800d8c7c  mov     dword ptr [rax+rcx*8+4], 1
0x1800d8c84  mov     [rax+rcx*8+8], r14d
0x1800d8c89  mov     [rax+rcx*8+0Ch], esi
0x1800d8c8d  mov     [rax+rcx*8+10h], rsi
0x1800d8c92  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8c97  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 10
0x1800d8c9b  lea     r8, [rbx+8]
0x1800d8c9f  xor     edx, edx
0x1800d8ca1  call    sqlite3Savepoint
0x1800d8ca6  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8cab  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 11
0x1800d8caf  lea     r8, [rbx+8]
0x1800d8cb3  mov     edx, 1
0x1800d8cb8  call    sqlite3Savepoint
0x1800d8cbd  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8cc2  mov     rcx, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 12
0x1800d8cc6  lea     r8, [rbx+8]
0x1800d8cca  mov     edx, 2
0x1800d8ccf  call    sqlite3Savepoint
0x1800d8cd4  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8cd9  mov     eax, [rbx-28h]; jumptable 00000001800D8B52 case 13
0x1800d8cdc  lea     r8, [rbx+8]
0x1800d8ce0  mov     r9d, [rbx-58h]
0x1800d8ce4  lea     rdx, [rbx-10h]
0x1800d8ce8  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8cec  xor     esi, esi
0x1800d8cee  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1800d8cf2  mov     dword ptr [rsp+0F0h+var_C8], esi
0x1800d8cf6  mov     dword ptr [rsp+0F0h+var_D0], esi
0x1800d8cfa  call    sqlite3StartTable
0x1800d8cff  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8d04  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 14
0x1800d8d08  inc     byte ptr [rax+24h]
0x1800d8d0b  mov     rcx, [rax]
0x1800d8d0e  inc     dword ptr [rcx+1A0h]
0x1800d8d14  xor     esi, esi
0x1800d8d16  mov     [rcx+1A4h], si
0x1800d8d1d  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8d22  mov     dword ptr [rbx-28h], 1; jumptable 00000001800D8B52 case 16
0x1800d8d29  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8d2e  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 17
0x1800d8d32  xor     esi, esi
0x1800d8d34  mov     rcx, [rax]
0x1800d8d37  cmp     [rcx+0C5h], sil
0x1800d8d3e  setz    sil
0x1800d8d42  mov     [rbx+8], esi
0x1800d8d45  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8d4a  mov     r9d, [rbx+8]; jumptable 00000001800D8B52 case 19
0x1800d8d4e  lea     r8, [rbx-10h]
0x1800d8d52  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8d56  lea     rdx, [rbx-28h]
0x1800d8d5a  xor     esi, esi
0x1800d8d5c  mov     [rsp+0F0h+var_D0], rsi
0x1800d8d61  call    sqlite3EndTable
0x1800d8d66  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8d6b  mov     rax, [rbx+8]; jumptable 00000001800D8B52 case 20
0x1800d8d6f  xor     r9d, r9d
0x1800d8d72  mov     rdi, [rbp+4Fh+arg_20]
0x1800d8d76  xor     r8d, r8d
0x1800d8d79  mov     rcx, rdi
0x1800d8d7c  mov     [rsp+0F0h+var_D0], rax
0x1800d8d81  xor     edx, edx
0x1800d8d83  call    sqlite3EndTable
0x1800d8d88  jmp     loc_1800D95A1
0x1800d8d8d  mov     eax, [rbx+8]; jumptable 00000001800D8B52 case 22
0x1800d8d90  or      [rbx-28h], eax
0x1800d8d93  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8d98  mov     r10d, [rbx+10h]; jumptable 00000001800D8B52 case 23
0x1800d8d9c  cmp     r10d, 5
0x1800d8da0  jnz     short loc_1800D8E10
0x1800d8da2  mov     r8, [rbx+8]
0x1800d8da6  test    r8, r8
0x1800d8da9  jz      short loc_1800D8E10
0x1800d8dab  mov     edx, r10d
0x1800d8dae  lea     r9, aRowid_1; "rowid"
0x1800d8db5  movzx   ecx, byte ptr [r8]
0x1800d8db9  dec     edx
0x1800d8dbb  test    cl, cl
0x1800d8dbd  jz      short loc_1800D8DE2
0x1800d8dbf  movzx   eax, byte ptr [r9]
0x1800d8dc3  movzx   eax, byte ptr [rax+r11+114680h]
0x1800d8dcc  cmp     [rcx+r11+114680h], al
0x1800d8dd4  jnz     short loc_1800D8DE2
0x1800d8dd6  inc     r8
0x1800d8dd9  inc     r9
0x1800d8ddc  test    edx, edx
0x1800d8dde  jg      short loc_1800D8DB5
0x1800d8de0  dec     edx
0x1800d8de2  test    edx, edx
0x1800d8de4  js      short loc_1800D8E04
0x1800d8de6  movzx   eax, byte ptr [r9]
0x1800d8dea  movzx   ecx, byte ptr [rax+r11+114680h]
0x1800d8df3  movzx   eax, byte ptr [r8]
0x1800d8df7  movzx   eax, byte ptr [rax+r11+114680h]
0x1800d8e00  cmp     eax, ecx
0x1800d8e02  jnz     short loc_1800D8E10
0x1800d8e04  mov     dword ptr [rbx-10h], 280h
0x1800d8e0b  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8e10  mov     r9, [rbx+8]
0x1800d8e14  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x1800d8e1b  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8e1f  xor     esi, esi
0x1800d8e21  mov     r8d, r10d
0x1800d8e24  mov     [rbx-10h], esi
0x1800d8e27  call    sqlite3ErrorMsg
0x1800d8e2c  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8e31  mov     r10d, [rbx+10h]; jumptable 00000001800D8B52 case 24
0x1800d8e35  cmp     r10d, 6
0x1800d8e39  jnz     short loc_1800D8EAC
0x1800d8e3b  mov     r8, [rbx+8]
0x1800d8e3f  test    r8, r8
0x1800d8e42  jz      short loc_1800D8EAC
0x1800d8e44  mov     edx, r10d
0x1800d8e47  lea     r9, aStrict; "strict"
0x1800d8e4e  xchg    ax, ax
0x1800d8e50  movzx   ecx, byte ptr [r8]
0x1800d8e54  dec     edx
0x1800d8e56  test    cl, cl
0x1800d8e58  jz      short loc_1800D8E7D
0x1800d8e5a  movzx   eax, byte ptr [r9]
0x1800d8e5e  movzx   eax, byte ptr [rax+r11+114680h]
0x1800d8e67  cmp     [rcx+r11+114680h], al
0x1800d8e6f  jnz     short loc_1800D8E7D
0x1800d8e71  inc     r8
0x1800d8e74  inc     r9
0x1800d8e77  test    edx, edx
0x1800d8e79  jg      short loc_1800D8E50
0x1800d8e7b  dec     edx
0x1800d8e7d  test    edx, edx
0x1800d8e7f  js      short loc_1800D8E9F
0x1800d8e81  movzx   eax, byte ptr [r9]
0x1800d8e85  movzx   ecx, byte ptr [rax+r11+114680h]
0x1800d8e8e  movzx   eax, byte ptr [r8]
0x1800d8e92  movzx   eax, byte ptr [rax+r11+114680h]
0x1800d8e9b  cmp     eax, ecx
0x1800d8e9d  jnz     short loc_1800D8EAC
0x1800d8e9f  mov     esi, 10000h
0x1800d8ea4  mov     [rbx+8], esi
0x1800d8ea7  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8eac  mov     r9, [rbx+8]
0x1800d8eb0  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x1800d8eb7  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8ebb  xor     esi, esi
0x1800d8ebd  mov     r8d, r10d
0x1800d8ec0  call    sqlite3ErrorMsg
0x1800d8ec5  mov     [rbx+8], esi
0x1800d8ec8  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8ecd  movups  xmm0, xmmword ptr [rbx+8]; jumptable 00000001800D8B52 case 25
0x1800d8ed1  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8ed5  lea     r8, [rbp+4Fh+Src]
0x1800d8ed9  movups  xmm1, xmmword ptr [rbx-10h]
0x1800d8edd  lea     rdx, [rbp+4Fh+var_80]
0x1800d8ee1  movaps  xmmword ptr [rbp+4Fh+Src], xmm0
0x1800d8ee5  movaps  [rbp+4Fh+var_80], xmm1
0x1800d8ee9  call    sqlite3AddColumn
0x1800d8eee  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8ef3  xor     esi, esi; jumptable 00000001800D8B52 cases 26,65,104
0x1800d8ef5  mov     [rbx+28h], esi
0x1800d8ef8  mov     [rbx+20h], rsi
0x1800d8efc  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f01  mov     eax, [rbx+10h]; jumptable 00000001800D8B52 case 27
0x1800d8f04  sub     eax, [rbx-40h]
0x1800d8f07  add     eax, [rbx+8]
0x1800d8f0a  mov     [rbx-38h], eax
0x1800d8f0d  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f12  mov     eax, [rbx+10h]; jumptable 00000001800D8B52 case 28
0x1800d8f15  sub     eax, [rbx-70h]
0x1800d8f18  add     eax, [rbx+8]
0x1800d8f1b  mov     [rbx-68h], eax
0x1800d8f1e  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f23  mov     eax, [rbx+10h]; jumptable 00000001800D8B52 case 29
0x1800d8f26  sub     eax, [rbx-10h]
0x1800d8f29  add     eax, [rbx+8]
0x1800d8f2c  mov     [rbx-8], eax
0x1800d8f2f  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f34  mov     rax, [r9]; jumptable 00000001800D8B52 case 30
0x1800d8f37  mov     [rbx+20h], rax
0x1800d8f3b  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f40  movups  xmm0, xmmword ptr [r9]; jumptable 00000001800D8B52 case 31
0x1800d8f44  movups  xmmword ptr [rbx+20h], xmm0
0x1800d8f48  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f4d  mov     rax, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 cases 32,67
0x1800d8f51  movups  xmm0, xmmword ptr [rbx+8]
0x1800d8f55  movups  xmmword ptr [rax+68h], xmm0
0x1800d8f59  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f5e  mov     r8, [rbx-10h]; jumptable 00000001800D8B52 case 33
0x1800d8f62  mov     r9d, [rbx-8]
0x1800d8f66  mov     rdx, [rbx+8]
0x1800d8f6a  add     r9, r8
0x1800d8f6d  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8f71  call    sqlite3AddDefaultValue
0x1800d8f76  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f7b  mov     r8, [rbx-28h]; jumptable 00000001800D8B52 case 34
0x1800d8f7f  mov     r9, [rbx+8]
0x1800d8f83  inc     r8
0x1800d8f86  mov     rdx, [rbx-10h]
0x1800d8f8a  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8f8e  call    sqlite3AddDefaultValue
0x1800d8f93  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8f98  mov     r9d, [rbx-8]; jumptable 00000001800D8B52 case 35
0x1800d8f9c  add     r9, [rbx-10h]
0x1800d8fa0  mov     r8, [rbx-28h]
0x1800d8fa4  mov     rdx, [rbx+8]
0x1800d8fa8  mov     rcx, [rbp+4Fh+arg_20]
0x1800d8fac  call    sqlite3AddDefaultValue
0x1800d8fb1  jmp     loc_1800DC68E; jumptable 00000001800D8B52 cases 320,322,333
0x1800d8fb6  mov     r12, [rbp+4Fh+arg_20]; jumptable 00000001800D8B52 case 36
0x1800d8fba  mov     edx, 48h ; 'H'
0x1800d8fbf  mov     r14, [rbx+8]
0x1800d8fc3  mov     rcx, [r12]
0x1800d8fc7  call    sqlite3DbMallocRawNN
0x1800d8fcc  mov     rdi, rax
0x1800d8fcf  test    rax, rax
0x1800d8fd2  jz      short loc_1800D9046
0x1800d8fd4  xorps   xmm0, xmm0
  ... truncated ...
```

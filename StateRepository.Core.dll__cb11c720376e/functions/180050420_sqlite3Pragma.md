# sqlite3Pragma

- ea: `0x180050420`
- end: `0x180053d44`
- name: `sqlite3Pragma`
- size: `14628`
- prototype: ``
- caller_count: `1`
- callee_count: `119`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031b38`

## callees

- `0x180001110`
- `0x180005810`
- `0x180005c54`
- `0x180005d14`
- `0x1800073ec`
- `0x180008838`
- `0x180009f00`
- `0x18000a220`
- `0x18000a7a0`
- `0x18000a9e0`
- `0x18000aac0`
- `0x18000b220`
- `0x18000c930`
- `0x18000e808`
- `0x18000fa9c`
- `0x18000fd7c`
- `0x180010390`
- `0x180010810`
- `0x180010d10`
- `0x1800119e0`
- `0x180011d80`
- `0x180012454`
- `0x1800126ec`
- `0x1800139a4`
- `0x180013a00`
- `0x180013c28`
- `0x1800143f0`
- `0x180014434`
- `0x180014af0`
- `0x180014b90`
- `0x1800150f4`
- `0x1800157d4`
- `0x180016250`
- `0x180016398`
- `0x180016444`
- `0x180018600`
- `0x18001bdf0`
- `0x18001c02c`
- `0x18001c1c4`
- `0x18001c220`
- `0x180023b30`
- `0x180024440`
- `0x1800256c4`
- `0x180027aa0`
- `0x180028c94`
- `0x1800303e0`
- `0x1800351c8`
- `0x180036688`
- `0x180037070`
- `0x1800370c0`

## string_xrefs

- `0x1800537e7`: `not a writable directory`
- `0x180053c93`: `Safety level may not be changed inside a transaction`

## pseudocode

```c
__int64 __fastcall sqlite3Pragma(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // r12
  __int64 *v9; // rdi
  __int64 result; // rax
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rax
  char *v15; // r13
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // r10
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned __int64 v35; // rbx
  __int64 v36; // rbx
  int v37; // eax
  unsigned int AutoVacuum; // edi
  int v39; // ebx
  _DWORD *v40; // rax
  int v41; // edi
  __int64 v42; // rcx
  __int64 v43; // r10
  unsigned int v44; // r11d
  __int64 v45; // rbx
  _DWORD *v46; // rax
  __int64 v47; // rcx
  int Int32; // eax
  __int64 v49; // rdx
  int v50; // edi
  __int64 v51; // rbx
  char Boolean; // al
  __int64 v53; // rcx
  __int64 v54; // rbx
  unsigned __int64 v55; // rcx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  unsigned int v62; // ebx
  __int64 j; // rcx
  __int64 v64; // rax
  __int64 **v65; // rbx
  unsigned int v66; // esi
  unsigned __int8 v67; // al
  unsigned int i; // ebx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rdx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  __int64 v82; // rax
  __int64 v83; // rbx
  unsigned int v84; // eax
  __int64 v85; // rbx
  unsigned int v86; // edi
  bool v87; // zf
  __int64 Index; // rsi
  __int64 v89; // rax
  unsigned int v90; // eax
  const char **v91; // rbx
  bool v92; // cf
  unsigned int v93; // r12d
  __int64 v94; // rdx
  __int64 v95; // rcx
  int v96; // ebx
  unsigned int v97; // ebx
  __int64 v98; // rax
  unsigned int v99; // ebx
  __int64 m; // rsi
  __int64 n; // rdi
  _QWORD *v102; // rdi
  __int64 v103; // rax
  __int64 v104; // rsi
  __int64 v105; // rbx
  unsigned int v106; // eax
  unsigned int v107; // r9d
  __int64 v108; // rdx
  unsigned int v109; // eax
  __int64 v110; // rcx
  int v111; // edi
  __int64 v112; // rcx
  __int64 v113; // rdx
  __int64 v114; // r8
  int v115; // eax
  __int64 v116; // r8
  int v117; // r10d
  int v118; // eax
  int v119; // ecx
  __int64 v120; // rax
  _QWORD *v121; // rax
  __int64 Table; // rsi
  unsigned int v123; // eax
  __int64 v124; // rcx
  __int64 v125; // rbx
  int v126; // edx
  __int64 v127; // rcx
  int v128; // eax
  __int64 v129; // rax
  __int64 v130; // r8
  unsigned int v131; // eax
  const char **v132; // rcx
  int v133; // r13d
  __int64 v134; // r8
  const char **v135; // rbx
  __int64 v136; // rax
  int v137; // eax
  int v138; // ecx
  __int64 v139; // rdi
  int k; // r12d
  int v141; // r9d
  int v142; // ebx
  __int64 v143; // rax
  const char **v144; // rbx
  const char *v145; // rdx
  char **ii; // rbx
  __int64 v147; // rdx
  char v148; // r11
  __int64 v149; // rcx
  int v150; // r11d
  _DWORD *v151; // rax
  int v152; // ebx
  __int64 v153; // rax
  __int64 v154; // r8
  int v155; // ebx
  int v156; // eax
  __int64 v157; // r9
  unsigned int v158; // eax
  __int64 v159; // rcx
  __int64 v160; // rax
  __int64 v161; // rax
  int v162; // ecx
  _QWORD *v163; // rax
  __int64 v164; // rdx
  __int64 v165; // rdx
  int v166; // eax
  int *v167; // rax
  int v168; // ebx
  _QWORD *v169; // r8
  __int64 v170; // r14
  __int64 v171; // rdx
  __int64 v172; // rcx
  __int64 jj; // rdx
  __int64 v174; // r8
  __int64 v175; // r9
  int v176; // ecx
  unsigned int v177; // ebx
  __int64 v178; // rax
  __int64 v179; // r10
  __int64 v180; // rax
  __int64 v181; // rcx
  unsigned int v182; // r12d
  __int64 v183; // rax
  unsigned int v184; // r9d
  const char ***v185; // rdx
  __int64 v186; // rcx
  const char **v187; // rax
  unsigned int v188; // edi
  unsigned int v189; // ebx
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // rbx
  const char **v193; // rax
  const char **v194; // rbx
  unsigned int TempRange; // eax
  __int64 v196; // r10
  int v197; // edx
  int v198; // edi
  const char *v199; // r12
  int v200; // eax
  int v201; // r9d
  int v202; // edx
  int kk; // r8d
  int v204; // eax
  int v205; // r9d
  unsigned int v206; // ebx
  __int64 v207; // rax
  __int64 v208; // rax
  int v209; // ebx
  int v210; // r14d
  __int64 v211; // r12
  __int64 v212; // rdx
  int v213; // r8d
  bool v214; // cc
  __int64 v215; // rcx
  BOOL v216; // r8d
  int v217; // r11d
  int v218; // edx
  int v219; // eax
  _BYTE *v220; // r9
  int v221; // r8d
  __int64 v222; // rax
  __int64 v223; // rdx
  __int64 v224; // r8
  __int16 v225; // ax
  int v226; // eax
  int v227; // ecx
  const char **v228; // rax
  unsigned int v229; // eax
  __int64 v230; // r8
  unsigned int v231; // r9d
  int v232; // ecx
  int v233; // r10d
  __int64 v234; // rax
  unsigned int v235; // edx
  __int64 v236; // rax
  __int64 v237; // rdx
  __int64 v238; // r8
  __int64 v239; // r9
  __int64 v240; // r10
  __int64 v241; // rax
  char v242; // dl
  __int64 v243; // r8
  __int64 v244; // r9
  __int64 v245; // r8
  __int64 v246; // r9
  int v247; // ecx
  __int64 v248; // r8
  __int64 v249; // r9
  const char *v250; // rdx
  const char **v251; // rax
  const char **v252; // rcx
  int v253; // eax
  unsigned int v254; // r14d
  int v255; // ebx
  const char **v256; // r12
  __int64 v257; // rax
  char *v258; // rbx
  int v259; // ecx
  __int64 v260; // r8
  int v261; // edx
  const char **v262; // r12
  int v263; // eax
  unsigned int v264; // ebx
  unsigned int v265; // ebx
  unsigned int v266; // edx
  int v267; // r12d
  unsigned int v268; // ebx
  __int64 v269; // rax
  int v270; // edx
  int v271; // edi
  __int64 v272; // rax
  unsigned int v273; // ebx
  __int64 v274; // rax
  unsigned int v275; // r8d
  unsigned int v276; // r9d
  __int64 v277; // rax
  __int64 v278; // rdx
  int v279; // ebx
  __int64 v280; // rax
  __int64 v281; // r9
  __int64 v282; // rbx
  __int64 v283; // r8
  __int64 v284; // rbx
  __int64 ElementWithHash; // rax
  __int64 v286; // rax
  __int64 *v287; // rax
  __int64 v288; // rax
  unsigned int v289; // ebx
  __int64 v290; // rax
  __int64 v291; // rax
  __int64 v292; // rax
  __int64 v293; // r8
  __int64 Op; // rax
  int v295; // r9d
  unsigned int v296; // ecx
  unsigned int v297; // ecx
  unsigned int v298; // ecx
  unsigned int v299; // ecx
  __int64 v300; // rdx
  int v301; // r8d
  __int64 v302; // r13
  __int64 v303; // rax
  __int64 *v304; // rbx
  __int64 v305; // rcx
  int v306; // edx
  __int64 v307; // r13
  __int64 v308; // rax
  __int64 *v309; // rbx
  __int64 v310; // rcx
  unsigned __int8 *v311; // rax
  int v312; // ebx
  int v313; // eax
  int v314; // r9d
  int v315; // r8d
  __int64 LockingMode; // rdx
  int v317; // eax
  int nn; // r8d
  int v319; // r8d
  __int64 *v320; // rcx
  __int64 v321; // rax
  __int64 v322; // rdi
  __int64 v323; // rcx
  __int64 v324; // rdx
  unsigned int v325; // edi
  __int64 v326; // rcx
  unsigned int v327; // edx
  unsigned int i1; // ebx
  int v329; // eax
  __int64 v330; // rax
  int v331; // edi
  __int64 v332; // r13
  int v333; // ecx
  _QWORD *mm; // rbx
  unsigned int v335; // ecx
  unsigned int v336; // ecx
  unsigned int v337; // ecx
  int v338; // edi
  __int64 v339; // rsi
  int v340; // ebx
  __int64 i2; // rbx
  __int64 v342; // rbx
  int v343; // ecx
  __int64 v344; // rdx
  int v345; // ebx
  int v346; // eax
  const char **i3; // rax
  __int64 v348; // rdx
  _BYTE *v349; // r9
  int v350; // r8d
  const char *v351; // r10
  __int64 v352; // rcx
  unsigned int v353; // r9d
  int v354; // r8d
  int v355; // r8d
  __int64 v356; // rdx
  int TempReg; // ebx
  __int64 v358; // rdx
  int v359; // r9d
  __int64 v360; // rax
  __int64 v361; // rdx
  int v362; // r9d
  int v363; // r10d
  unsigned int v364; // ecx
  unsigned int v365; // ecx
  unsigned int v366; // ecx
  unsigned int v367; // ecx
  unsigned int v368; // ecx
  unsigned int v369; // ecx
  unsigned int v370; // ecx
  unsigned int v371; // ecx
  int v372; // r9d
  int v373; // esi
  int v374; // r11d
  int v375; // r8d
  __int64 v376; // rax
  __int64 v377; // rdx
  __int64 v378; // rcx
  __int64 v379; // rax
  __int64 v380; // rsi
  __int64 v381; // rdx
  int v382; // eax
  __int64 v383; // rdi
  __int64 v384; // rcx
  int v385; // edi
  __int64 v386; // rcx
  __int64 v387; // r13
  _QWORD *i4; // rax
  __int64 v389; // r8
  __int64 v390; // rax
  __int64 v391; // rax
  _QWORD *v392; // rax
  const char *v393; // rcx
  unsigned int v394; // esi
  int v395; // ebx
  __int64 v396; // rax
  __int64 v397; // rax
  __int64 v398; // rbx
  signed int v399; // edx
  __int64 v400; // r13
  int v401; // ecx
  signed int v402; // r8d
  __int64 v403; // r12
  __int16 v404; // ax
  int v405; // edi
  __int64 v406; // rax
  __int64 v407; // r9
  unsigned int v408; // r11d
  __int64 v409; // rax
  int v410; // r10d
  int v411; // r11d
  int v412; // r8d
  __int64 v413; // r9
  const char *v414; // r8
  char SafetyLevel; // al
  __int64 v416; // rcx
  int v417; // eax
  __int64 v418; // [rsp+20h] [rbp-E0h]
  __int64 v419; // [rsp+20h] [rbp-E0h]
  __int64 v420; // [rsp+20h] [rbp-E0h]
  int v421; // [rsp+20h] [rbp-E0h]
  __int64 v422; // [rsp+28h] [rbp-D8h]
  __int64 v423; // [rsp+28h] [rbp-D8h]
  __int64 v424; // [rsp+28h] [rbp-D8h]
  int v425; // [rsp+28h] [rbp-D8h]
  int v426; // [rsp+30h] [rbp-D0h]
  int v427; // [rsp+30h] [rbp-D0h]
  __int64 v428; // [rsp+38h] [rbp-C8h]
  int v429; // [rsp+40h] [rbp-C0h]
  int v430; // [rsp+48h] [rbp-B8h]
  unsigned int v431; // [rsp+60h] [rbp-A0h] BYREF
  int v432; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v433; // [rsp+68h] [rbp-98h] BYREF
  unsigned int IndexKey; // [rsp+6Ch] [rbp-94h]
  __int64 v435; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v436; // [rsp+78h] [rbp-88h]
  int v437; // [rsp+7Ch] [rbp-84h]
  char v438; // [rsp+80h] [rbp-80h]
  int v439; // [rsp+84h] [rbp-7Ch]
  __int64 v440; // [rsp+88h] [rbp-78h]
  const char **v441; // [rsp+90h] [rbp-70h]
  __int64 v442; // [rsp+98h] [rbp-68h]
  unsigned int v443; // [rsp+A0h] [rbp-60h]
  int v444; // [rsp+A4h] [rbp-5Ch] BYREF
  int v445; // [rsp+A8h] [rbp-58h]
  const char **v446; // [rsp+B0h] [rbp-50h] BYREF
  char *v447; // [rsp+B8h] [rbp-48h]
  unsigned int v448; // [rsp+C0h] [rbp-40h]
  __int64 v449; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v450; // [rsp+D0h] [rbp-30h] BYREF
  int v451; // [rsp+D8h] [rbp-28h]
  unsigned int v452; // [rsp+DCh] [rbp-24h] BYREF
  __int64 v453; // [rsp+E0h] [rbp-20h]
  unsigned int v454; // [rsp+E8h] [rbp-18h]
  __int64 v455; // [rsp+F0h] [rbp-10h]
  char *v456; // [rsp+F8h] [rbp-8h]
  __int64 v457; // [rsp+100h] [rbp+0h] BYREF
  __int64 v458; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v459; // [rsp+110h] [rbp+10h]
  __int64 *v460; // [rsp+118h] [rbp+18h]
  _QWORD v461[3]; // [rsp+120h] [rbp+20h]
  __int128 v462; // [rsp+138h] [rbp+38h] BYREF
  __int128 v463; // [rsp+148h] [rbp+48h]

  v5 = *a1;
  v449 = *a1;
  v458 = a3;
  v450 = 0;
  v462 = 0;
  v435 = a4;
  v463 = 0;
  v9 = a1;
  v460 = a1;
  result = sqlite3GetVdbe(a1);
  v442 = result;
  v11 = result;
  if ( result )
  {
    sqlite3VdbeAddOp3(result, 166, 1, 1, 0);
    *((_DWORD *)v9 + 15) = 2;
    result = sqlite3TwoPartName(v9, a2, a3, &v450);
    v12 = (int)result;
    v445 = result;
    if ( (int)result >= 0 )
    {
      v453 = *(_QWORD *)(v5 + 32);
      if ( (_DWORD)result != 1 || (result = sqlite3OpenTempDatabase(v9), !(_DWORD)result) )
      {
        result = sqlite3NameFromToken(v5, v450);
        v459 = (unsigned __int8 *)result;
        if ( result )
        {
          v13 = 32 * v12;
          v455 = 32 * v12;
          if ( a5 )
            v14 = sqlite3MPrintf(v5, "-%T", a4);
          else
            v14 = sqlite3NameFromToken(v5, a4);
          v15 = (char *)v14;
          v456 = (char *)v14;
          if ( *(_DWORD *)(v458 + 8) )
            v16 = *(_QWORD *)(v453 + 32 * v12);
          else
            v16 = 0;
          v440 = v16;
          if ( (unsigned int)sqlite3AuthCheck((_DWORD)v9, 19, (_DWORD)v459, (_DWORD)v15, v16) )
            goto LABEL_698;
          *(_QWORD *)&v462 = 0;
          *((_QWORD *)&v462 + 1) = v459;
          v463 = (unsigned __int64)v15;
          *(_DWORD *)(v5 + 664) = 0;
          if ( (unsigned int)sqlite3SafetyCheckOk(v5) )
          {
            v18 = *(_QWORD *)(v5 + 24);
            v433 = 1;
            sqlite3_mutex_enter(v18);
            v19 = sqlite3DbNameToBtree(v5, v440);
            v450 = v19;
            if ( v19 )
            {
              sqlite3BtreeEnter(v19);
              v20 = *(_DWORD *)(v5 + 664);
              v21 = sqlite3OsFileControl(*(_QWORD *)(**(_QWORD **)(v450 + 8) + 72LL), 14, &v462);
              v22 = v450;
              v433 = v21;
              *(_DWORD *)(v5 + 664) = v20;
              sqlite3BtreeLeave(v22);
              v13 = v455;
            }
            sqlite3_mutex_leave(*(_QWORD *)(v5 + 24));
            v17 = v433;
          }
          else
          {
            v17 = sqlite3ReportError(21, 185165, "misuse");
            v433 = v17;
          }
          if ( !v17 )
          {
            sqlite3VdbeSetNumCols(v11, 1);
            sqlite3VdbeSetColName(v11, 0, 0, v462, -1);
            returnSingleText(v11, v462);
            sqlite3_free(v462);
            goto LABEL_698;
          }
          if ( v17 != 12 )
          {
            if ( (_QWORD)v462 )
            {
              sqlite3ErrorMsg(v9, "%s", (const char *)v462);
              sqlite3_free(v462);
              v17 = v433;
            }
            goto LABEL_23;
          }
          v23 = pragmaLocate(v459);
          v441 = (const char **)v23;
          v25 = v23;
          if ( !v23 )
            goto LABEL_698;
          if ( (*(_BYTE *)(v23 + 9) & 1) != 0 )
          {
            if ( (unsigned int)sqlite3ReadSchema(v9) )
              goto LABEL_698;
            v25 = (__int64)v441;
          }
          if ( (*(_BYTE *)(v25 + 9) & 2) == 0 && ((*(_BYTE *)(v25 + 9) & 4) == 0 || !v15) )
          {
            setPragmaResultColumnNames(v11, v25);
            v25 = (__int64)v441;
          }
          v26 = *(unsigned __int8 *)(v25 + 8);
          if ( v26 <= 0x16 )
          {
            if ( v26 != 22 )
            {
              if ( v26 <= 0xC )
              {
                if ( v26 == 12 )
                {
                  *((_DWORD *)v9 + 15) = 3;
                  for ( i = 0; (signed int)i < *(_DWORD *)(v5 + 40); ++i )
                  {
                    v69 = *(_QWORD *)(32LL * (int)i + *(_QWORD *)(v5 + 32) + 8);
                    if ( v69 )
                    {
                      v70 = sqlite3PagerFilename(**(_QWORD **)(v69 + 8), 1);
                      sqlite3VdbeMultiLoad(v11, v73, "iss", i, *(_QWORD *)(v71 + v72), v70, v426, v428, v429, v430);
                    }
                  }
                  goto LABEL_698;
                }
                if ( v26 <= 7 )
                {
                  if ( v26 == 7 )
                  {
                    if ( v15 )
                    {
                      v432 = 1;
                      Int32 = sqlite3GetInt32(v15, &v432);
                      v50 = v432;
                      if ( Int32 )
                        sqlite3BtreeSetSpillSize(*(_QWORD *)(v453 + v13 + 8), (unsigned int)v432);
                      v51 = *(_QWORD *)(v5 + 48);
                      LOBYTE(v49) = v50 != 0;
                      Boolean = sqlite3GetBoolean(v15, v49);
                      v53 = v51;
                      v54 = v51 | 0x20;
                      v55 = v53 & 0xFFFFFFFFFFFFFFDFuLL;
                      if ( !Boolean )
                        v54 = v55;
                      *(_QWORD *)(v5 + 48) = v54;
                      goto LABEL_86;
                    }
                    if ( (*(_BYTE *)(v5 + 48) & 0x20) != 0 )
                      v37 = sqlite3BtreeSetSpillSize(*(_QWORD *)(v453 + v13 + 8), 0);
                    else
                      v37 = 0;
LABEL_62:
                    v31 = v37;
                    goto LABEL_697;
                  }
                  v27 = v26 - 1;
                  if ( !v27 )
                  {
                    v442 = 0;
                    if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
                      *(_DWORD *)(v5 + 744) = v442 & 0x7FFFFFFF;
                    v31 = *(int *)(v5 + 744);
                    goto LABEL_697;
                  }
                  v28 = v27 - 1;
                  if ( v28 )
                  {
                    v29 = v28 - 1;
                    if ( v29 )
                    {
                      v30 = v29 - 1;
                      if ( v30 )
                      {
                        if ( v30 == 2 )
                        {
                          if ( !v15 )
                          {
                            v31 = *(int *)(*(_QWORD *)(v453 + v13 + 24) + 116LL);
                            goto LABEL_697;
                          }
                          v432 = 0;
                          sqlite3GetInt32(v15, &v432);
                          v32 = v453;
                          *(_DWORD *)(*(_QWORD *)(v453 + v13 + 24) + 116LL) = v432;
                          v33 = *(_QWORD *)(v32 + v13 + 24);
                          v34 = *(_QWORD *)(v32 + v13 + 8);
LABEL_226:
                          sqlite3BtreeSetCacheSize(v34, *(unsigned int *)(v33 + 116));
                          goto LABEL_698;
                        }
LABEL_593:
                        if ( v15 )
                        {
                          v431 = 0;
                          sqlite3GetInt32(v15, &v431);
                          sqlite3_busy_timeout(v5, v431);
                        }
                        v31 = *(int *)(v5 + 748);
                        goto LABEL_697;
                      }
                      if ( !v15 )
                      {
                        setPragmaResultColumnNames(v11, v25);
                        v31 = (*(_QWORD *)(v5 + 48) & (unsigned __int64)v441[2]) != 0;
                        goto LABEL_697;
                      }
                      v35 = *(_QWORD *)(v25 + 16) & 0xFFFFFFFFFFFFBFFFuLL;
                      if ( *(_BYTE *)(v5 + 101) )
                        v35 = *(_QWORD *)(v25 + 16);
                      if ( (unsigned __int8)sqlite3GetBoolean(v15, 0) )
                      {
                        if ( (v35 & 1) == 0 || (*(_DWORD *)(v5 + 48) & 0x10000000) == 0 )
                          *(_QWORD *)(v5 + 48) |= v35;
                      }
                      else
                      {
                        *(_QWORD *)(v5 + 48) &= ~v35;
                        if ( v35 == 0x80000 )
                        {
                          *(_QWORD *)(v5 + 768) = 0;
                        }
                        else if ( (v35 & 1) != 0 && !(unsigned int)sqlite3_stricmp(v15, "reset") )
                        {
                          sqlite3ResetAllSchemasOfConnection(v5);
                        }
                      }
                      sqlite3VdbeAddOp3(v11, 166, 0, 0, 0);
LABEL_86:
                      setAllPagerFlags(v5);
                      goto LABEL_698;
                    }
                    v36 = *(_QWORD *)(v453 + v13 + 8);
                    if ( v15 )
                    {
                      AutoVacuum = getAutoVacuum(v15);
                      *(_BYTE *)(v5 + 106) = AutoVacuum;
                      if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v36, AutoVacuum) && AutoVacuum - 1 <= 1 )
                      {
                        v39 = *(_DWORD *)(v11 + 144);
                        v40 = (_DWORD *)sqlite3VdbeAddOpList(v11, 5, qword_1800A77F0);
                        v40[14] = v39 + 4;
                        v40[27] = AutoVacuum - 1;
                        v40[1] = v12;
                        v40[7] = v12;
                        v40[25] = v12;
                        sqlite3VdbeUsesBtree(v11, (unsigned int)v12);
                      }
                      goto LABEL_698;
                    }
                    v37 = sqlite3BtreeGetAutoVacuum(v36);
                    goto LABEL_62;
                  }
                  v41 = *(_DWORD *)(v25 + 16);
                  sqlite3VdbeUsesBtree(v11, (unsigned int)v12);
                  if ( v15 && (*(_BYTE *)(v43 + 9) & 8) == 0 )
                  {
                    v432 = 0;
                    v45 = sqlite3VdbeAddOpList(v42, v44, qword_1800A6560);
                    *(_DWORD *)(v45 + 4) = v12;
                    *(_DWORD *)(v45 + 28) = v12;
                    *(_DWORD *)(v45 + 32) = v41;
                    sqlite3GetInt32(v15, &v432);
                    *(_DWORD *)(v45 + 36) = v432;
                    *(_WORD *)(v45 + 26) = 1;
                    if ( v41 == 1 && (*(_DWORD *)(v5 + 48) & 0x10000000) != 0 )
                      *(_BYTE *)(v45 + 24) = -69;
                    goto LABEL_698;
                  }
                  v46 = (_DWORD *)sqlite3VdbeAddOpList(v42, 3, &qword_1800A7328);
                  v47 = v11;
                  v46[1] = v12;
                  v46[7] = v12;
                  v46[9] = v41;
LABEL_72:
                  sqlite3VdbeReusable(v47);
                  goto LABEL_698;
                }
                v56 = v26 - 8;
                if ( !v56 )
                {
                  if ( v15 )
                  {
                    v67 = sqlite3GetBoolean(v15, 0);
                    sqlite3RegisterLikeFunctions(v5, v67);
                  }
                  goto LABEL_698;
                }
                v57 = v56 - 1;
                if ( v57 )
                {
                  v58 = v57 - 1;
                  if ( !v58 )
                  {
                    *((_DWORD *)v9 + 15) = 1;
                    v62 = 0;
                    for ( j = 0; ; j = v62 )
                    {
                      v64 = sqlite3_compileoption_get(j);
                      v47 = v11;
                      if ( !v64 )
                        break;
                      ++v62;
                      sqlite3VdbeAddOp4(v11, 118, 0, 1, 0, v64, 0);
                      sqlite3VdbeAddOp3(v11, 84, 1, 1, 0);
                    }
                    goto LABEL_72;
                  }
                  if ( v58 != 1 )
                    goto LABEL_593;
                  v59 = sqlite3MutexAlloc(11);
                  sqlite3_mutex_enter(v59);
                  if ( !v15 )
                  {
                    v60 = sqlite3_data_directory;
LABEL_617:
                    returnSingleText(v11, v60);
LABEL_622:
                    v379 = sqlite3MutexAlloc(11);
                    sqlite3_mutex_leave(v379);
                    goto LABEL_698;
                  }
                  if ( !*v15
                    || (v61 = *(_QWORD *)v5,
                        v432 = 0,
                        !(*(unsigned int (__fastcall **)(__int64, char *, __int64, int *))(v61 + 56))(
                           v61,
                           v15,
                           1,
                           &v432))
                    && v432 )
                  {
                    sqlite3_free(sqlite3_data_directory);
                    if ( *v15 )
                      sqlite3_data_directory = sqlite3_mprintf("%s", v15);
                    else
                      sqlite3_data_directory = 0;
                    goto LABEL_622;
                  }
                  goto LABEL_621;
                }
                *((_DWORD *)v9 + 15) = 2;
                v65 = *(__int64 ***)(v5 + 632);
                v66 = 0;
                if ( !v65 )
                  goto LABEL_698;
                do
                {
                  sqlite3VdbeMultiLoad(v11, 1, "is", v66, *v65[2], v422, v426, v428, v429, v430);
                  v65 = (__int64 **)*v65;
                  ++v66;
                }
                while ( v65 );
LABEL_683:
                v15 = v456;
                goto LABEL_698;
              }
              v74 = v26 - 13;
              if ( !v74 )
              {
                sqlite3VdbeUsesBtree(v11, (unsigned int)v12);
                if ( !v15 )
                {
                  *((_DWORD *)v9 + 15) += v150;
                  v151 = (_DWORD *)sqlite3VdbeAddOpList(v149, 9, qword_1800A6940);
                  v151[1] = v12;
                  v151[7] = v12;
                  v151[37] = -2000;
                  goto LABEL_698;
                }
                v432 = 0;
                sqlite3GetInt32(v15, &v432);
                v152 = sqlite3AbsInt32((unsigned int)v432);
                sqlite3BeginWriteOperation(v9, 0, (unsigned int)v12);
                sqlite3VdbeAddOp3(v11, 100, v12, 3, v152);
                v153 = v455;
                v154 = v453;
                *(_DWORD *)(*(_QWORD *)(v453 + v455 + 24) + 116LL) = v152;
                v33 = *(_QWORD *)(v154 + v153 + 24);
                v34 = *(_QWORD *)(v154 + v153 + 8);
                goto LABEL_226;
              }
              v75 = v74 - 1;
              if ( v75 )
              {
                v76 = v75 - 1;
                if ( !v76 )
                {
                  _mm_lfence();
                  v118 = *((_DWORD *)v9 + 15);
                  v119 = v118 + 1;
                  v118 += 5;
                  *((_DWORD *)v9 + 15) = v118;
                  v432 = v118;
                  v120 = *(_QWORD *)(v5 + 32);
                  v437 = v119;
                  v121 = *(_QWORD **)(*(_QWORD *)(v120 + v13 + 24) + 16LL);
                  while ( v121 )
                  {
                    if ( v15 )
                    {
                      Table = sqlite3LocateTable(v9, 0, v15, v440);
                      v121 = 0;
                    }
                    else
                    {
                      Table = v121[2];
                      v121 = (_QWORD *)*v121;
                    }
                    v455 = (__int64)v121;
                    if ( Table && !*(_BYTE *)(Table + 63) && *(_QWORD *)(Table + 72) )
                    {
                      v123 = sqlite3SchemaToIndex(v5, *(_QWORD *)(Table + 96));
                      v124 = *(_QWORD *)(v5 + 32);
                      IndexKey = v123;
                      v125 = *(_QWORD *)(32LL * (int)v123 + v124);
                      v440 = v125;
                      sqlite3CodeVerifySchema(v9, v123);
                      sqlite3TableLock(v9, IndexKey, *(unsigned int *)(Table + 40), 0, *(_QWORD *)Table);
                      v126 = v432 + *(__int16 *)(Table + 54);
                      if ( *((_DWORD *)v9 + 15) < v126 )
                        *((_DWORD *)v9 + 15) = v126;
                      sqlite3OpenTable((_DWORD)v9, 0, IndexKey, Table, 102);
                      sqlite3VdbeAddOp4(v11, 118, 0, v437, 0, *(_QWORD *)Table, 0);
                      v127 = *(_QWORD *)(Table + 72);
                      v128 = 1;
                      while ( 1 )
                      {
                        v450 = v127;
                        v433 = v128;
                        if ( !v127 )
                          break;
                        v129 = sqlite3FindTable(v5, *(_QWORD *)(v127 + 16), v125);
                        v442 = v129;
                        if ( v129 )
                        {
                          v130 = *(unsigned int *)(v129 + 40);
                          v419 = *(_QWORD *)v129;
                          v446 = 0;
                          sqlite3TableLock(v9, IndexKey, v130, 0, v419);
                          if ( (unsigned int)sqlite3FkLocateIndex((_DWORD)v9, v442, v450, (unsigned int)&v446, 0) )
                            goto LABEL_698;
                          if ( v446 )
                          {
                            sqlite3VdbeAddOp3(v11, 102, v433, *((_DWORD *)v446 + 22), IndexKey);
                            sqlite3VdbeSetP4KeyInfo(v9, v446);
                          }
                          else
                          {
                            sqlite3OpenTable((_DWORD)v9, v433, IndexKey, v442, 102);
                          }
                        }
                        v128 = v433 + 1;
                        v127 = *(_QWORD *)(v450 + 8);
                      }
                      if ( *((_DWORD *)v9 + 14) < v128 )
                        *((_DWORD *)v9 + 14) = v128;
                      v131 = sqlite3VdbeAddOp3(v11, 36, 0, 0, 0);
                      v132 = *(const char ***)(Table + 72);
                      v452 = v131;
                      IndexKey = 1;
                      v441 = v132;
                      if ( v132 )
                      {
                        v133 = v432;
                        v436 = v437 + 2;
                        v443 = v437 + 1;
                        do
                        {
                          v134 = v125;
                          v135 = v441;
                          v136 = sqlite3FindTable(v5, v441[2], v134);
                          v435 = v136;
                          v446 = 0;
                          v450 = 0;
                          if ( v136 )
                            sqlite3FkLocateIndex((_DWORD)v9, v136, (_DWORD)v441, (unsigned int)&v446, (__int64)&v450);
                          v137 = *((_DWORD *)v9 + 18) - 1;
                          *((_DWORD *)v9 + 18) = v137;
                          v138 = v133 + *((_DWORD *)v135 + 10);
                          v433 = v137;
                          if ( *((_DWORD *)v9 + 15) < v138 )
                            *((_DWORD *)v9 + 15) = v138;
                          v445 = *((_DWORD *)v135 + 10);
                          if ( v445 > 0 )
                          {
                            v139 = v450;
                            for ( k = 0; k < v445; ++k )
                            {
                              if ( v139 )
                                v141 = *(_DWORD *)(v139 + 4LL * k);
                              else
                                v141 = (int)v135[2 * k + 8];
                              sqlite3ExprCodeGetColumnOfTable(v11, Table, 0, v141, k + v133);
                              sqlite3VdbeAddOp3(v11, 51, k + v133, v433, 0);
                              v135 = v441;
                              v445 = *((_DWORD *)v441 + 10);
                            }
                            v5 = v449;
                            v9 = v460;
                          }
                          if ( v446 )
                          {
                            v142 = *((_DWORD *)v135 + 10);
                            v143 = sqlite3IndexAffinityStr(v5, v446);
                            sqlite3VdbeAddOp4(v11, 96, v133, v142, 0, v143, v445);
                            v135 = v441;
                            sqlite3VdbeAddOp4Int(v11, 29, IndexKey, v433, v133, *((_DWORD *)v441 + 10));
                          }
                          else if ( v435 )
                          {
                            sqlite3VdbeAddOp3(v11, 30, IndexKey, *(_DWORD *)(v11 + 144) + 2, v133);
                            sqlite3VdbeAddOp3(v11, 9, 0, v433, 0);
                          }
                          sqlite3VdbeAddOp3(v11, (*(_DWORD *)(Table + 48) & 0x80u) != 0 ? 75 : 135, 0, v443, 0);
                          LODWORD(v420) = IndexKey - 1;
                          sqlite3VdbeMultiLoad(v11, v436, "siX", v135[2], v420, v424, v427, v428, v429, v430);
                          sqlite3VdbeAddOp3(v11, 84, v437, 4, 0);
                          sqlite3VdbeResolveLabel(v11, v433);
                          sqlite3DbFree(v5, v450);
                          v144 = (const char **)v135[1];
                          ++IndexKey;
                          v441 = v144;
                          v87 = v144 == 0;
                          v125 = v440;
                        }
                        while ( !v87 );
                        v15 = v456;
                        v131 = v452;
                      }
                      sqlite3VdbeAddOp3(v11, 39, 0, v131 + 1, 0);
                      *(_DWORD *)(sqlite3VdbeGetOp(v11, v452) + 8) = *(_DWORD *)(v11 + 144);
                      v121 = (_QWORD *)v455;
                    }
                  }
                  goto LABEL_698;
                }
                v77 = v76 - 1;
                if ( !v77 )
                {
                  if ( !v15 )
                    goto LABEL_698;
                  v103 = sqlite3FindTable(v5, v15, v440);
                  v104 = v103;
                  if ( !v103 )
                    goto LABEL_698;
                  if ( *(_BYTE *)(v103 + 63) )
                    goto LABEL_698;
                  v105 = *(_QWORD *)(v103 + 72);
                  if ( !v105 )
                    goto LABEL_698;
                  v106 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v103 + 96));
                  v433 = v107;
                  *((_DWORD *)v9 + 15) = 8;
                  sqlite3CodeVerifySchema(v9, v106);
                  v109 = v433;
                  v110 = 0;
                  do
                  {
                    v111 = 0;
                    if ( *(int *)(v105 + 40) > 0 )
                    {
                      do
                      {
                        LOBYTE(v110) = *(_BYTE *)(v105 + 45);
                        actionName(v110, v108, v111);
                        LOBYTE(v112) = *(_BYTE *)(v105 + 46);
                        v115 = actionName(v112, v113, v114);
                        LODWORD(v418) = v111;
                        sqlite3VdbeMultiLoad(
                          v11,
                          1,
                          "iissssss",
                          v433,
                          v418,
                          *(_QWORD *)(v105 + 16),
                          *(_QWORD *)(*(_QWORD *)(v104 + 8) + 24LL * *(int *)(v105 + 16 * (v116 + 4))),
                          *(_QWORD *)(v105 + 16 * v116 + 72),
                          v115,
                          v117);
                        ++v111;
                      }
                      while ( v111 < *(_DWORD *)(v105 + 40) );
                      v109 = v433;
                      v110 = 0;
                    }
                    v105 = *(_QWORD *)(v105 + 8);
                    v433 = ++v109;
                  }
                  while ( v105 );
                  goto LABEL_683;
                }
                v78 = v77 - 1;
                if ( !v78 )
                {
                  v99 = (*(_DWORD *)(v5 + 44) >> 5) & 1;
                  *((_DWORD *)v9 + 15) = 6;
                  for ( m = 0; m != 23; ++m )
                  {
                    for ( n = qword_1800B5D10[m]; n; n = *(_QWORD *)(n + 64) )
                      pragmaFunclistLine(v11, n, 1, v99);
                  }
                  v102 = *(_QWORD **)(v5 + 608);
                  v15 = v456;
                  while ( v102 )
                  {
                    pragmaFunclistLine(v11, v102[2], 0, v99);
                    v102 = (_QWORD *)*v102;
                  }
                  goto LABEL_698;
                }
                v79 = v78 - 1;
                if ( v79 )
                {
                  v80 = v79 - 1;
                  if ( !v80 )
                  {
                    v432 = 0;
                    if ( !v15 || !(unsigned int)sqlite3GetInt32(v15, &v432) || (v96 = v432, v432 <= 0) )
                      v96 = 0x7FFFFFFF;
                    sqlite3BeginWriteOperation(v9, 0, (unsigned int)v12);
                    sqlite3VdbeAddOp3(v11, 71, v96, 1, 0);
                    v97 = sqlite3VdbeAddOp3(v11, 62, v12, 0, 0);
                    sqlite3VdbeAddOp3(v11, 84, 1, 0, 0);
                    sqlite3VdbeAddOp3(v11, 86, 1, -1, 0);
                    sqlite3VdbeAddOp3(v11, 50, 1, v97, 0);
                    *(_DWORD *)(sqlite3VdbeGetOp(v11, v97) + 8) = *(_DWORD *)(v11 + 144);
                    goto LABEL_698;
                  }
                  v81 = v80 - 1;
                  if ( v81 )
                  {
                    if ( v81 == 1 )
                    {
                      if ( v15 )
                      {
                        v82 = sqlite3FindTable(v5, v15, v440);
                        v83 = v82;
                        if ( v82 )
                        {
                          v84 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v82 + 96));
                          *((_DWORD *)v9 + 15) = 5;
                          sqlite3CodeVerifySchema(v9, v84);
                          v85 = *(_QWORD *)(v83 + 16);
                          v86 = 0;
                          while ( v85 )
                          {
                            v87 = *(_QWORD *)(v85 + 72) == 0;
                            v461[0] = "c";
                            v461[1] = "u";
                            LODWORD(v428) = !v87;
                            v461[2] = "pk";
                            LODWORD(v422) = *(_BYTE *)(v85 + 98) != 0;
                            sqlite3VdbeMultiLoad(
                              v11,
                              1,
                              "isisi",
                              v86,
                              *(_QWORD *)v85,
                              v422,
                              v461[*(_DWORD *)(v85 + 100) & 3],
                              v428,
                              v429,
                              v430);
                            v85 = *(_QWORD *)(v85 + 40);
                            ++v86;
                          }
                        }
                      }
                      goto LABEL_698;
                    }
                    goto LABEL_593;
                  }
                  if ( !v15 )
                    goto LABEL_698;
                  Index = sqlite3FindIndex(v5, v15, v440);
                  if ( !Index )
                  {
                    v89 = sqlite3LocateTable(v9, 2, v15, v440);
                    if ( !v89 )
                      goto LABEL_698;
                    if ( *(char *)(v89 + 48) >= 0 )
                      goto LABEL_698;
                    Index = sqlite3PrimaryKeyIndex(v89);
                    if ( !Index )
                      goto LABEL_698;
                  }
                  v90 = sqlite3SchemaToIndex(v5, *(_QWORD *)(Index + 48));
                  v91 = v441;
                  v92 = v441[2] != 0;
                  v432 = *(unsigned __int16 *)((v92 ? 2 : 0) + Index + 94);
                  *((_DWORD *)v9 + 15) = v92 ? 6 : 3;
                  v435 = *(_QWORD *)(Index + 24);
                  sqlite3CodeVerifySchema(v9, v90);
                  if ( !v432 )
                    goto LABEL_698;
                  v93 = 0;
                  do
                  {
                    v94 = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v93);
                    if ( (v94 & 0x8000u) == 0LL )
                      v95 = *(_QWORD *)(*(_QWORD *)(v435 + 8) + 24 * v94);
                    else
                      v95 = 0;
                    LODWORD(v418) = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v93);
                    sqlite3VdbeMultiLoad(v11, 1, "iisX", v93, v418, v95, v426, v428, v429, v430);
                    if ( v91[2] )
                    {
                      LODWORD(v423) = v93 < *(unsigned __int16 *)(Index + 94);
                      sqlite3VdbeMultiLoad(
                        v11,
                        4,
                        "isiX",
                        *(unsigned __int8 *)(*(_QWORD *)(Index + 56) + v93),
                        *(_QWORD *)(*(_QWORD *)(Index + 64) + 8LL * v93),
                        v423,
                        v426,
                        v428,
                        v429,
                        v430);
                    }
                    sqlite3VdbeAddOp3(v11, 84, 1, *((_DWORD *)v9 + 15), 0);
                    ++v93;
                  }
                  while ( (int)v93 < v432 );
                  goto LABEL_682;
                }
                v442 = 0;
                if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
                  sqlite3_hard_heap_limit64(-1);
                v98 = sqlite3_hard_heap_limit64(-1);
LABEL_696:
                v31 = v98;
                goto LABEL_697;
              }
              if ( v15 )
              {
                if ( (*(_BYTE *)(v5 + 44) & 0x40) == 0 )
                {
                  for ( ii = &off_18009D270; *ii; ii += 2 )
                  {
                    if ( !(unsigned int)sqlite3StrICmp(v15, *ii) )
                    {
                      if ( *((_BYTE *)ii + 8) )
                        v148 = *((_BYTE *)ii + 8);
                      LOBYTE(v147) = v148;
                      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v5 + 32) + 24LL) + 113LL) = v148;
                      sqlite3SetTextEncoding(v5, v147);
                      break;
                    }
                  }
                  if ( !*ii )
                    sqlite3ErrorMsg(v9, "unsupported encoding: %s", v15);
                }
                goto LABEL_698;
              }
              if ( (unsigned int)sqlite3ReadSchema(v9) )
                goto LABEL_698;
              v145 = (&off_18009D270)[2 * *(unsigned __int8 *)(*v9 + 100)];
LABEL_473:
              returnSingleText(v11, v145);
              goto LABEL_698;
            }
            v155 = v445;
            v440 = 0;
            v87 = *((_BYTE *)qword_18009E760 + *v459) == 113;
            v438 = *((_BYTE *)qword_18009E760 + *v459);
            LODWORD(v453) = v87;
            v87 = *(_QWORD *)v458 == 0;
            v156 = 100;
            *((_DWORD *)v9 + 15) = 6;
            if ( v87 )
              v155 = -1;
            v437 = 100;
            v445 = v155;
            v433 = 100;
            if ( !v15 )
              goto LABEL_238;
            if ( (unsigned int)sqlite3GetInt32(*(_QWORD *)v435, &v433) )
            {
              v156 = v433;
              v437 = v433;
              if ( (int)v433 > 0 )
                goto LABEL_238;
              v156 = 100;
            }
            else
            {
              if ( v155 < 0 )
                v157 = 0;
              else
                v157 = *(_QWORD *)(32LL * v155 + *(_QWORD *)(v5 + 32));
              v440 = sqlite3LocateTable(v9, 0, v15, v157);
              v156 = v433;
            }
            v437 = v156;
LABEL_238:
            sqlite3VdbeAddOp3(v11, 71, v156 - 1, 1, 0);
            v158 = 0;
            v451 = 0;
            if ( *(int *)(v5 + 40) <= 0 )
              goto LABEL_420;
            while ( 1 )
            {
              if ( v155 < 0 || v158 == v155 )
              {
                sqlite3CodeVerifySchema(v9, v158);
                v159 = 32LL * v451;
                *((_BYTE *)v9 + 35) = 0;
                v160 = *(_QWORD *)(v5 + 32);
                v441 = (const char **)v159;
                v161 = *(_QWORD *)(v159 + v160 + 24);
                v162 = 0;
                v450 = v161;
                v163 = *(_QWORD **)(v161 + 16);
                if ( v163 )
                {
                  do
                  {
                    v164 = v163[2];
                    if ( !v440 || v440 == v164 )
                    {
                      if ( *(char *)(v164 + 48) >= 0 )
                        ++v162;
                      v165 = *(_QWORD *)(v164 + 16);
                      while ( v165 )
                      {
                        v165 = *(_QWORD *)(v165 + 40);
                        ++v162;
                      }
                    }
                    v163 = (_QWORD *)*v163;
                  }
                  while ( v163 );
                  if ( v162 )
                  {
                    v166 = v162 + 1;
                    if ( !v440 )
                      v166 = v162;
                    v167 = (int *)sqlite3DbMallocRawNN(v5, 4LL * v166 + 4);
                    v435 = (__int64)v167;
                    if ( !v167 )
                    {
LABEL_419:
                      v15 = v456;
LABEL_420:
                      v291 = sqlite3VdbeAddOpList(v11, 7, qword_1800A6F40);
                      if ( v291 )
                      {
                        *(_DWORD *)(v291 + 8) = 1 - v437;
                        *(_BYTE *)(v291 + 49) = -1;
                        *(_QWORD *)(v291 + 64) = "ok";
                        *(_BYTE *)(v291 + 121) = -1;
                        v292 = sqlite3ErrStr(11);
                        *(_QWORD *)(v293 + 136) = v292;
                      }
                      Op = sqlite3VdbeGetOp(v11, 0);
                      *(_DWORD *)(Op + 12) = v295;
                      goto LABEL_698;
                    }
                    v168 = 0;
                    if ( v440 )
                    {
                      v168 = 1;
                      v167[1] = 0;
                    }
                    v169 = *(_QWORD **)(v450 + 16);
                    if ( v169 )
                    {
                      v170 = v440;
                      do
                      {
                        v171 = v169[2];
                        if ( !v170 || v170 == v171 )
                        {
                          if ( *(char *)(v171 + 48) >= 0 )
                          {
                            v172 = v168++;
                            v167[v172 + 1] = *(_DWORD *)(v171 + 40);
                          }
                          for ( jj = *(_QWORD *)(v171 + 16); jj; jj = *(_QWORD *)(jj + 40) )
                            v167[++v168] = *(_DWORD *)(jj + 88);
                        }
                        v169 = (_QWORD *)*v169;
                      }
                      while ( v169 );
                      v11 = v442;
                    }
                    *v167 = v168;
                    if ( *((_DWORD *)v9 + 15) < v168 + 8 )
                      *((_DWORD *)v9 + 15) = v168 + 8;
                    sqlite3VdbeAddOp3(v11, 75, 0, 8, v168 + 8);
                    *((_BYTE *)v9 + 31) = 0;
                    *((_DWORD *)v9 + 11) = 0;
                    sqlite3VdbeAddOp4(v11, 155, 1, v168, 8, v435, -14);
                    sqlite3VdbeChangeP5(v11, (unsigned __int8)v451, v174, v175);
                    v177 = sqlite3VdbeAddOp3(v176, 51, 2, 0, 0);
                    v178 = sqlite3MPrintf(
                             v5,
                             "*** in database %s ***\n",
                             *(const char **)((char *)v441 + *(_QWORD *)(v5 + 32)));
                    sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v178, -6);
                    sqlite3VdbeAddOp3(v11, 112, 2, 3, 3);
                    integrityCheckResultRow(v11);
                    *(_DWORD *)(sqlite3VdbeGetOp(v11, v177) + 8) = *(_DWORD *)(v11 + 144);
                    sqlite3VdbeAddOp4(v11, 118, 0, 2, 0, (__int64)"wrong # of entries in index ", 0);
                    v179 = 0;
                    v180 = *(_QWORD *)(v450 + 16);
                    v455 = v180;
                    if ( v180 )
                    {
                      v181 = v440;
                      v182 = v440 != 0;
                      do
                      {
                        v183 = *(_QWORD *)(v180 + 16);
                        if ( !v181 || v181 == v183 )
                        {
                          v87 = *(_BYTE *)(v183 + 48) >= 0;
                          v184 = v182;
                          v433 = v182;
                          if ( v87 )
                          {
                            ++v182;
                            v185 = (const char ***)(v183 + 16);
                          }
                          else
                          {
                            v186 = *(_QWORD *)(v183 + 16);
                            if ( v186 )
                            {
                              do
                              {
                                v185 = (const char ***)(v183 + 16);
                                if ( (*(_DWORD *)(v186 + 100) & 3) == 2 )
                                  break;
                                v186 = *(_QWORD *)(v186 + 40);
                                v433 = ++v184;
                              }
                              while ( v186 );
                            }
                            else
                            {
                              v185 = (const char ***)(v183 + 16);
                            }
                          }
                          v187 = *v185;
                          v441 = v187;
                          if ( v187 )
                          {
                            v188 = v182 + 8;
                            do
                            {
                              if ( !v187[9] )
                              {
                                v189 = sqlite3VdbeAddOp3(v11, 54, v188, 0, v184 + 8);
                                sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)*v441, 0);
                                sqlite3VdbeAddOp3(v11, 112, 4, 2, 3);
                                integrityCheckResultRow(v11);
                                v190 = sqlite3VdbeGetOp(v11, v189);
                                v179 = 0;
                                *(_DWORD *)(v190 + 8) = *(_DWORD *)(v11 + 144);
                                v187 = v441;
                              }
                              v187 = (const char **)v187[5];
                              ++v182;
                              v184 = v433;
                              ++v188;
                              v441 = v187;
                            }
                            while ( v187 );
                          }
                        }
                        v181 = v440;
                        v180 = *(_QWORD *)v455;
                        v455 = v180;
                      }
                      while ( v180 );
                      v5 = v449;
                      v9 = v460;
                    }
                    v191 = v450;
                    v192 = *(_QWORD *)(v450 + 16);
                    v435 = v192;
                    if ( v192 )
                    {
                      v193 = (const char **)v440;
                      while ( 1 )
                      {
                        v194 = *(const char ***)(v192 + 16);
                        v446 = v194;
                        v444 = v179;
                        v452 = v179;
                        if ( v193 && v193 != v194 || *((_BYTE *)v194 + 63) != (_BYTE)v179 )
                          goto LABEL_399;
                        if ( v438 == 113 || *((char *)v194 + 48) >= 0 )
                        {
                          v455 = v179;
                          v433 = v179;
                        }
                        else
                        {
                          v455 = sqlite3PrimaryKeyIndex(v194);
                          TempRange = sqlite3GetTempRange(v9, *(unsigned __int16 *)(v455 + 94));
                          v197 = *(unsigned __int16 *)(v196 + 94) - 1;
                          v433 = TempRange;
                          sqlite3VdbeAddOp3(v11, 75, 1, TempRange, TempRange + v197);
                          v179 = 0;
                        }
                        sqlite3OpenTableAndIndices(
                          (_DWORD)v9,
                          (_DWORD)v194,
                          102,
                          0,
                          1,
                          v179,
                          (__int64)&v444,
                          (__int64)&v452);
                        sqlite3VdbeAddOp3(v11, 71, 0, 7, 0);
                        if ( v194[2] )
                        {
                          v198 = 8;
                          v199 = v194[2];
                          do
                          {
                            sqlite3VdbeAddOp3(v11, 71, 0, v198, 0);
                            v199 = (const char *)*((_QWORD *)v199 + 5);
                            ++v198;
                          }
                          while ( v199 );
                          v5 = v449;
                          v9 = v460;
                          v194 = v446;
                        }
                        sqlite3VdbeAddOp3(v11, 36, v444, 0, 0);
                        v200 = sqlite3VdbeAddOp3(v11, 86, 7, 1, 0);
                        v87 = *((_BYTE *)v194 + 48) >= 0;
                        LODWORD(v458) = v200;
                        if ( v87 )
                        {
                          v201 = *((__int16 *)v194 + 27);
                          v202 = -1;
                          if ( v201 > 0 )
                          {
                            for ( kk = 0; kk < v201; ++kk )
                            {
                              v204 = v202 + 1;
                              if ( (v194[1][24 * kk + 18] & 0x20) != 0 )
                                v204 = v202;
                              v202 = v204;
                            }
                          }
                          v205 = v202 - 1;
                          if ( v202 != *((__int16 *)v194 + 26) )
                            v205 = v202;
                        }
                        else
                        {
                          v205 = *(unsigned __int16 *)(sqlite3PrimaryKeyIndex(v194) + 96) - 1;
                        }
                        if ( v205 >= 0 )
                        {
                          sqlite3VdbeAddOp3(v11, 94, v444, v205, 3);
                          sqlite3VdbeTypeofColumn(v11, 3);
                        }
                        if ( v438 != 113 && v455 )
                        {
                          v206 = sqlite3VdbeAddOp4Int(v11, 41, v444, 0, v433, *(unsigned __int16 *)(v455 + 94));
                          sqlite3VdbeAddOp3(v11, 51, v433, 0, 0);
                          v207 = sqlite3MPrintf(v5, "row not in PRIMARY KEY order for %s", *v446);
                          sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v207, -6);
                          integrityCheckResultRow(v11);
                          *(_DWORD *)(sqlite3VdbeGetOp(v11, v206) + 8) = *(_DWORD *)(v11 + 144);
                          v208 = sqlite3VdbeGetOp(v11, v206 + 1);
                          v209 = 0;
                          *(_DWORD *)(v208 + 8) = *(_DWORD *)(v11 + 144);
                          if ( *(_WORD *)(v455 + 94) )
                          {
                            v210 = v444;
                            v211 = v455;
                            do
                            {
                              sqlite3ExprCodeLoadIndexColumn((_DWORD)v9, v211, v210, v209, v209 + v433);
                              ++v209;
                            }
                            while ( v209 < *(unsigned __int16 *)(v211 + 94) );
                            v11 = v442;
                            v5 = v449;
                            v194 = v446;
                          }
                          else
                          {
                            v194 = v446;
                          }
                        }
                        v212 = 0;
                        v213 = (_DWORD)v194[6] & 0x10000;
                        v214 = *((_WORD *)v194 + 27) > 0;
                        v432 = v213;
                        while ( 1 )
                        {
                          v448 = v212;
                          if ( !v214 )
                            break;
                          if ( (_DWORD)v212 == *((__int16 *)v194 + 26) )
                            goto LABEL_358;
                          v215 = (__int64)&v194[1][24 * (int)v212];
                          v441 = (const char **)v215;
                          if ( v213 )
                          {
                            v216 = (*(_DWORD *)(v215 + 8) & 0xF0u) > 0x10;
                            v454 = v216;
                          }
                          else if ( *(char *)(v215 + 12) <= 65 )
                          {
                            v216 = 0;
                            v454 = 0;
                          }
                          else
                          {
                            v216 = 1;
                            v454 = 1;
                          }
                          if ( (*(_BYTE *)(v215 + 8) & 0xF) != 0 || v216 )
                          {
                            v87 = (*(_BYTE *)(v215 + 18) & 0x20) == 0;
                            IndexKey = 5;
                            if ( v87 )
                            {
                              if ( *(_WORD *)(v215 + 16) )
                              {
                                v457 = 0;
                                v219 = sqlite3ColumnExpr(v194);
                                LOBYTE(v220) = *v220;
                                LOBYTE(v221) = *(_BYTE *)(v5 + 100);
                                sqlite3ValueFromExpr(v5, v219, v221, (_DWORD)v220, (__int64)&v457);
                                if ( v457 )
                                {
                                  IndexKey = *((unsigned __int8 *)qword_18009EC50 + (*(_WORD *)(v457 + 20) & 0x3F));
                                  sqlite3ValueFree(v457);
                                }
                                v212 = v448;
                              }
                              v87 = *((_BYTE *)v194 + 48) >= 0;
                              v439 = v444;
                              if ( v87 )
                              {
                                v225 = sqlite3TableColumnToStorage(v194, v212);
                                v217 = v439;
                              }
                              else
                              {
                                v222 = sqlite3PrimaryKeyIndex(v194);
                                v225 = sqlite3TableColumnToIndex(v222, v223, v224);
                              }
                              v218 = v225;
                            }
                            else
                            {
                              sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)v194, v444, v212, 3);
                              v217 = -1;
                              v439 = -1;
                              v218 = 3;
                            }
                            v226 = *((_DWORD *)v9 + 18) - 1;
                            LODWORD(v447) = v218;
                            v431 = v226;
                            v227 = v226 - 1;
                            v228 = v441;
                            *((_DWORD *)v9 + 18) = v227;
                            v436 = v227;
                            if ( ((_BYTE)v228[1] & 0xF) != 0 )
                            {
                              v229 = sqlite3VdbeAddOp4Int(v11, 18, v217, v227, v218, IndexKey);
                              LODWORD(v457) = v229;
                              if ( v439 >= 0 )
                              {
                                sqlite3VdbeChangeP5(v11, 13, v230, v229);
                                sqlite3VdbeAddOp3(v232, 94, v233, (_DWORD)v447, 3);
                                sqlite3ColumnDefault(v11, v194, v448, 3);
                                v443 = sqlite3VdbeAddOp3(v11, 52, 3, v436, 0);
                              }
                              else
                              {
                                sqlite3VdbeChangeP5(v11, 15, v230, v229);
                                v443 = v231;
                              }
                              v234 = sqlite3MPrintf(v5, "NULL value in %s.%s", *v194, *v441);
                              sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v234, -6);
                              v235 = v454;
                              if ( v454 )
                              {
                                sqlite3VdbeAddOp3(v11, 9, 0, v431, 0);
                                v236 = sqlite3VdbeGetOp(v11, (unsigned int)v457);
                                v237 = v443;
                                *(_DWORD *)(v236 + 8) = *(_DWORD *)(v11 + 144);
                                *(_DWORD *)(sqlite3VdbeGetOp(v11, v237) + 8) = *(_DWORD *)(v11 + 144);
                                v228 = v441;
                                v227 = v436;
                                goto LABEL_344;
                              }
                              v228 = v441;
                              v227 = v436;
                            }
                            else
                            {
LABEL_344:
                              v235 = v454;
                            }
                            if ( v432 )
                            {
                              if ( v235 )
                              {
                                sqlite3VdbeAddOp4Int(v11, 18, v439, v227, (_DWORD)v447, IndexKey);
                                sqlite3VdbeChangeP5(
                                  v11,
                                  *((unsigned __int8 *)&qword_1800A7838[1] + ((*((_DWORD *)v441 + 2) >> 4) & 0xFu) + 7),
                                  v238,
                                  v441);
                                v241 = sqlite3MPrintf(
                                         v5,
                                         "non-%s value in %s.%s",
                                         *(const char **)(v240
                                                        + 8LL
                                                        * ((unsigned int)((unsigned __int8)*(_DWORD *)(v239 + 8) >> 4)
                                                         - 1)
                                                        + 742720),
                                         *v194,
                                         *(const char **)&v194[1][24 * v448]);
                                goto LABEL_355;
                              }
LABEL_356:
                              sqlite3VdbeResolveLabel(v11, v431);
                              integrityCheckResultRow(v11);
                              sqlite3VdbeResolveLabel(v11, v436);
                              LODWORD(v212) = v448;
                              goto LABEL_357;
                            }
                            v242 = *((_BYTE *)v228 + 12);
                            if ( v242 == 66 )
                            {
                              sqlite3VdbeAddOp4Int(v11, 18, v439, v227, (_DWORD)v447, IndexKey);
                              sqlite3VdbeChangeP5(v11, 28, v243, v244);
                              v241 = sqlite3MPrintf(v5, "NUMERIC value in %s.%s", *v194, *(_QWORD *)&v194[1][24 * v448]);
                            }
                            else
                            {
                              if ( v242 < 67 )
                                goto LABEL_356;
                              sqlite3VdbeAddOp4Int(v11, 18, v439, v227, (_DWORD)v447, IndexKey);
                              sqlite3VdbeChangeP5(v11, 27, v245, v246);
                              if ( v439 >= 0 )
                                sqlite3ExprCodeGetColumnOfTable(v247, (_DWORD)v194, v444, v448, 3);
                              sqlite3VdbeAddOp4(v11, 96, 3, 1, 0, (__int64)"C", -1);
                              sqlite3VdbeAddOp4Int(v11, 18, -1, v436, 3, IndexKey);
                              sqlite3VdbeChangeP5(v11, 28, v248, v249);
                              v241 = sqlite3MPrintf(v5, "TEXT value in %s.%s", *v194, *(_QWORD *)&v194[1][24 * v448]);
                            }
LABEL_355:
                            sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v241, -6);
                            goto LABEL_356;
                          }
LABEL_357:
                          v213 = v432;
LABEL_358:
                          v212 = (unsigned int)(v212 + 1);
                          v214 = (int)v212 < *((__int16 *)v194 + 27);
                        }
                        v250 = v194[4];
                        if ( v250 && (*(_DWORD *)(v5 + 48) & 0x200LL) == 0 )
                        {
                          v251 = (const char **)sqlite3ExprListDup(v5, v250, 0);
                          v441 = v251;
                          v252 = v251;
                          if ( !*(_BYTE *)(v5 + 103) )
                          {
                            v431 = *((_DWORD *)v9 + 18) - 1;
                            v443 = v431 - 1;
                            *((_DWORD *)v9 + 18) = v431 - 1;
                            *((_DWORD *)v9 + 17) = v444 + 1;
                            v253 = *(_DWORD *)v251 - 1;
                            if ( *(_DWORD *)v252 - 1 > 0 )
                            {
                              v254 = v431;
                              v255 = v253;
                              v256 = v252;
                              do
                                sqlite3ExprIfFalse(v9, v256[4 * (unsigned int)v255-- + 1], v254, 0);
                              while ( v255 > 0 );
                              v11 = v442;
                              v5 = v449;
                              v194 = v446;
                              v252 = v441;
                            }
                            sqlite3ExprIfTrue(v9, v252[1], v443, 16);
                            sqlite3VdbeResolveLabel(v11, v431);
                            *((_DWORD *)v9 + 17) = 0;
                            v257 = sqlite3MPrintf(v5, "CHECK constraint failed in %s", *v194);
                            sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v257, -6);
                            integrityCheckResultRow(v11);
                            sqlite3VdbeResolveLabel(v11, v443);
                            v252 = v441;
                          }
                          sqlite3ExprListDeleteGeneric(v5, v252);
                        }
                        if ( v438 != 113 )
                        {
                          v258 = (char *)v194[2];
                          v259 = 0;
                          v439 = 0;
                          v260 = 0;
                          v447 = v258;
                          v261 = -1;
                          if ( v258 )
                          {
                            v262 = v446;
                            do
                            {
                              v263 = *((_DWORD *)v9 + 18) - 1;
                              v431 = 0;
                              LODWORD(v457) = v263;
                              *((_DWORD *)v9 + 18) = v263;
                              if ( (char *)v455 != v258 )
                              {
                                IndexKey = sqlite3GenerateIndexKey(
                                             (_DWORD)v9,
                                             (_DWORD)v258,
                                             v444,
                                             0,
                                             0,
                                             (__int64)&v431,
                                             v260,
                                             v261);
                                v441 = (const char **)v258;
                                sqlite3VdbeAddOp3(v11, 86, v439 + 8, 1, 0);
                                v425 = *((unsigned __int16 *)v258 + 48);
                                v443 = v452 + v439;
                                v264 = sqlite3VdbeAddOp4Int(v11, 29, v452 + v439, v457, IndexKey, v425);
                                sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, (__int64)"row ", 0);
                                sqlite3VdbeAddOp3(v11, 112, 7, 3, 3);
                                sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)" missing from index ", 0);
                                sqlite3VdbeAddOp3(v11, 112, 4, 3, 3);
                                v432 = sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, *(_QWORD *)v447, 0);
                                sqlite3VdbeAddOp3(v11, 112, 4, 3, 3);
                                v454 = integrityCheckResultRow(v11);
                                *(_DWORD *)(sqlite3VdbeGetOp(v11, v264) + 8) = *(_DWORD *)(v11 + 144);
                                if ( *((char *)v262 + 48) >= 0 )
                                {
                                  sqlite3VdbeAddOp3(v11, 142, v443, 3, 0);
                                  v265 = sqlite3VdbeAddOp3(
                                           v11,
                                           54,
                                           3,
                                           0,
                                           *((unsigned __int16 *)v447 + 48) + IndexKey - 1);
                                  sqlite3VdbeAddOp4(
                                    v11,
                                    118,
                                    0,
                                    3,
                                    0,
                                    (__int64)"rowid not at end-of-record for row ",
                                    0);
                                  sqlite3VdbeAddOp3(v11, 112, 7, 3, 3);
                                  sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)" of index ", 0);
                                  sqlite3VdbeAddOp3(v11, 9, 0, v432 - 1, 0);
                                  *(_DWORD *)(sqlite3VdbeGetOp(v11, v265) + 8) = *(_DWORD *)(v11 + 144);
                                }
                                v258 = v447;
                                v266 = 0;
                                v436 = 0;
                                if ( *((_WORD *)v447 + 47) )
                                {
                                  v267 = 0;
                                  do
                                  {
                                    if ( *(char **)(*((_QWORD *)v258 + 8) + 8LL * v267) != "BINARY" )
                                    {
                                      if ( !v266 )
                                      {
                                        v436 = *((_DWORD *)v9 + 18) - 1;
                                        *((_DWORD *)v9 + 18) = v436;
                                      }
                                      sqlite3VdbeAddOp3(v11, 94, v439 + v452, v267, 3);
                                      sqlite3VdbeAddOp3(v11, 53, 3, v436, v267 + IndexKey);
                                      v266 = v436;
                                    }
                                    ++v267;
                                  }
                                  while ( v267 < *((unsigned __int16 *)v258 + 47) );
                                  v262 = v446;
                                  if ( v266 )
                                  {
                                    v268 = sqlite3VdbeAddOp3(v11, 9, 0, 0, 0);
                                    sqlite3VdbeResolveLabel(v11, v436);
                                    sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, (__int64)"row ", 0);
                                    sqlite3VdbeAddOp3(v11, 112, 7, 3, 3);
                                    sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)" values differ from index ", 0);
                                    sqlite3VdbeAddOp3(v11, 9, 0, v432 - 1, 0);
                                    v269 = sqlite3VdbeGetOp(v11, v268);
                                    v258 = v447;
                                    *(_DWORD *)(v269 + 8) = *(_DWORD *)(v11 + 144);
                                  }
                                }
                                if ( v258[98] )
                                {
                                  v270 = *((_DWORD *)v9 + 18) - 1;
                                  *((_DWORD *)v9 + 18) = v270;
                                  v436 = v270;
                                  if ( *((_WORD *)v258 + 47) )
                                  {
                                    v271 = 0;
                                    do
                                    {
                                      v272 = *((_QWORD *)v258 + 1);
                                      if ( *(__int16 *)(v272 + 2LL * v271) < 0
                                        || (v262[1][24 * *(__int16 *)(v272 + 2LL * v271) + 8] & 0xF) == 0 )
                                      {
                                        sqlite3VdbeAddOp3(v11, 51, v271 + IndexKey, v270, 0);
                                        v270 = v436;
                                      }
                                      ++v271;
                                    }
                                    while ( v271 < *((unsigned __int16 *)v258 + 47) );
                                    v9 = v460;
                                  }
                                  v273 = sqlite3VdbeAddOp3(v11, 39, v439 + v452, 0, 0);
                                  sqlite3VdbeAddOp3(v11, 9, 0, v436, 0);
                                  v274 = sqlite3VdbeGetOp(v11, v273);
                                  v258 = v447;
                                  v275 = v439 + v452;
                                  v276 = v436;
                                  *(_DWORD *)(v274 + 8) = *(_DWORD *)(v11 + 144);
                                  sqlite3VdbeAddOp4Int(v11, 41, v275, v276, IndexKey, *((unsigned __int16 *)v258 + 47));
                                  sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, (__int64)"non-unique entry in index ", 0);
                                  sqlite3VdbeAddOp3(v11, 9, 0, v432, 0);
                                  sqlite3VdbeResolveLabel(v11, v436);
                                }
                                v277 = sqlite3VdbeGetOp(v11, v454);
                                v278 = v431;
                                *(_DWORD *)(v277 + 8) = *(_DWORD *)(v11 + 144);
                                sqlite3ResolvePartIdxLabel(v9, v278);
                                v259 = v439;
                                v261 = IndexKey;
                                v260 = (__int64)v441;
                              }
                              v258 = (char *)*((_QWORD *)v258 + 5);
                              ++v259;
                              v447 = v258;
                              v439 = v259;
                            }
                            while ( v258 );
                            v5 = v449;
                          }
                        }
                        v279 = v458;
                        sqlite3VdbeAddOp3(v11, 39, v444, v458, 0);
                        v280 = sqlite3VdbeGetOp(v11, (unsigned int)(v279 - 1));
                        v179 = 0;
                        *(_DWORD *)(v280 + 8) = *(_DWORD *)(v11 + 144);
                        if ( v455 )
                          sqlite3ReleaseTempRange(v9, v433, *(unsigned __int16 *)(v455 + 94), v281);
                        v193 = (const char **)v440;
LABEL_399:
                        v192 = *(_QWORD *)v435;
                        v435 = v192;
                        if ( !v192 )
                        {
                          v191 = v450;
                          break;
                        }
                      }
                    }
                    v282 = *(_QWORD *)(v191 + 16);
                    v435 = v282;
                    if ( v282 )
                    {
                      v283 = v440;
                      do
                      {
                        v284 = *(_QWORD *)(v282 + 16);
                        if ( (!v283 || v283 == v284) && *(_BYTE *)(v284 + 63) == 1 )
                        {
                          if ( *(__int16 *)(v284 + 54) > (__int16)v179
                            || (ElementWithHash = findElementWithHash(v5 + 552, **(_QWORD **)(v284 + 72), 0),
                                LOWORD(v179) = 0,
                                *(_QWORD *)(ElementWithHash + 16)) )
                          {
                            sqlite3ViewGetColumnNames(v9, v284);
                            v286 = *(_QWORD *)(v284 + 80);
                            LOWORD(v179) = 0;
                            if ( v286 )
                            {
                              v287 = *(__int64 **)(v286 + 16);
                              if ( v287 )
                              {
                                v288 = *v287;
                                if ( v288 )
                                {
                                  if ( *(int *)v288 >= 4 && *(_QWORD *)(v288 + 192) )
                                  {
                                    sqlite3VdbeAddOp3(v11, 174, v451, 3, v453);
                                    ++*(_DWORD *)(v284 + 44);
                                    sqlite3VdbeAppendP4(v11, v284, 4294967280LL);
                                    v289 = sqlite3VdbeAddOp3(v11, 51, 3, 0, 0);
                                    integrityCheckResultRow(v11);
                                    v290 = sqlite3VdbeGetOp(v11, v289);
                                    LOWORD(v179) = 0;
                                    *(_DWORD *)(v290 + 8) = *(_DWORD *)(v11 + 144);
                                  }
                                }
                              }
                            }
                          }
                          v283 = v440;
                        }
                        v282 = *(_QWORD *)v435;
                        v435 = v282;
                      }
                      while ( v282 );
                    }
                    v155 = v445;
                  }
                }
                v158 = v451;
              }
              v451 = ++v158;
              if ( (signed int)v158 >= *(_DWORD *)(v5 + 40) )
                goto LABEL_419;
            }
          }
          if ( (unsigned __int8)v26 <= 0x22u )
          {
            if ( (_BYTE)v26 == 34 )
            {
              sqlite3_db_release_memory(v5);
              goto LABEL_698;
            }
            if ( (unsigned __int8)v26 <= 0x1Du )
            {
              if ( (_BYTE)v26 == 29 )
              {
                *((_DWORD *)v9 + 15) = 1;
                for ( mm = *(_QWORD **)(v5 + 560); mm; mm = (_QWORD *)*mm )
                  sqlite3VdbeMultiLoad(v11, 1, "s", *(_QWORD *)(mm[2] + 8LL), v418, v422, v426, v428, v429, v430);
                goto LABEL_698;
              }
              v296 = v26 - 23;
              if ( v296 )
              {
                v297 = v296 - 1;
                if ( !v297 )
                {
                  v320 = *(__int64 **)(*(_QWORD *)(v453 + v13 + 8) + 8LL);
                  v321 = -2;
                  v435 = -2;
                  v322 = *v320;
                  if ( v15 )
                  {
                    sqlite3DecOrHexToI64(v15);
                    v321 = -1;
                  }
                  if ( v321 >= -1 )
                  {
                    v323 = *(_QWORD *)(v322 + 296);
                    *(_QWORD *)(v322 + 208) = v321;
                    if ( v323 )
                      *(_QWORD *)(v323 + 32) = v321;
                  }
                  v31 = *(_QWORD *)(v322 + 208);
                  goto LABEL_697;
                }
                v298 = v297 - 2;
                if ( v298 )
                {
                  v299 = v298 - 1;
                  if ( v299 )
                  {
                    if ( v299 != 1 )
                      goto LABEL_593;
                    v449 = 0;
                    if ( !v15 )
                      goto LABEL_449;
                    sqlite3DecOrHexToI64(v15);
                    v442 = v449;
                    v300 = v458;
                    if ( *(_DWORD *)(v458 + 8) )
                    {
                      v306 = *(_DWORD *)(v5 + 40) - 1;
                      v431 = v306;
                      if ( v306 >= 0 )
                      {
                        v307 = v442;
                        do
                        {
                          v308 = *(_QWORD *)(32LL * (unsigned int)v306 + *(_QWORD *)(v5 + 32) + 8);
                          v435 = v308;
                          if ( v308 && v306 == (_DWORD)v12 )
                          {
                            v309 = *(__int64 **)(v308 + 8);
                            sqlite3BtreeEnter(v308);
                            v310 = *v309;
                            *(_QWORD *)(v310 + 160) = v307;
                            pagerFixMaplimit(v310);
                            sqlite3BtreeLeave(v435);
                            v306 = v431;
                            v307 = v449;
                          }
                          v431 = --v306;
                        }
                        while ( v306 >= 0 );
                        goto LABEL_448;
                      }
                    }
                    else
                    {
                      *(_QWORD *)(v5 + 64) = v449;
                      v301 = *(_DWORD *)(v5 + 40) - 1;
                      v431 = v301;
                      if ( v301 >= 0 )
                      {
                        v302 = v442;
                        do
                        {
                          v303 = *(_QWORD *)(32LL * (unsigned int)v301 + *(_QWORD *)(v5 + 32) + 8);
                          v435 = v303;
                          if ( v303 && (v301 == (_DWORD)v12 || !*(_DWORD *)(v300 + 8)) )
                          {
                            v304 = *(__int64 **)(v303 + 8);
                            sqlite3BtreeEnter(v303);
                            v305 = *v304;
                            *(_QWORD *)(v305 + 160) = v302;
                            pagerFixMaplimit(v305);
                            sqlite3BtreeLeave(v435);
                            v300 = v458;
                            v301 = v431;
                            v302 = v449;
                          }
                          v431 = --v301;
                        }
                        while ( v301 >= 0 );
LABEL_448:
                        v15 = v456;
                      }
                    }
LABEL_449:
                    v449 = -1;
                    v17 = sqlite3_file_control(v5, v440, 18, &v449);
                    if ( v17 )
                    {
                      if ( v17 == 12 )
                        goto LABEL_698;
LABEL_23:
                      ++*((_DWORD *)v9 + 13);
                      *((_DWORD *)v9 + 6) = v17;
                      goto LABEL_698;
                    }
                    v31 = v449;
                    goto LABEL_697;
                  }
                  v435 = 0;
                  sqlite3CodeVerifySchema(v9, (unsigned int)v12);
                  v311 = v459;
                  v312 = *((_DWORD *)v9 + 15) + 1;
                  *((_DWORD *)v9 + 15) = v312;
                  if ( *((_BYTE *)qword_18009E760 + *v311) == 112 )
                  {
                    sqlite3VdbeAddOp3(v11, 178, v12, v312, 0);
                  }
                  else
                  {
                    if ( !v15 || (unsigned int)sqlite3DecOrHexToI64(v15) || (v313 = v435, v435 < 0) )
                    {
                      v313 = 0;
                    }
                    else if ( v435 > 4294967294LL )
                    {
                      v313 = -2;
                    }
                    sqlite3VdbeAddOp3(v11, 179, v12, v312, v313);
                  }
                  v314 = 1;
                  v421 = 0;
                  v315 = v312;
LABEL_463:
                  sqlite3VdbeAddOp3(v11, 84, v315, v314, v421);
                  goto LABEL_698;
                }
                LockingMode = (unsigned int)getLockingMode(v15);
                if ( !*(_DWORD *)(v458 + 8) )
                {
                  if ( (_DWORD)LockingMode == -1 )
                  {
                    v317 = *(unsigned __int8 *)(v5 + 105);
                    goto LABEL_471;
                  }
                  for ( nn = 2; nn < *(_DWORD *)(v5 + 40); nn = v319 + 1 )
                    sqlite3PagerLockingMode(
                      **(_QWORD **)(*(_QWORD *)(32LL * nn + *(_QWORD *)(v5 + 32) + 8) + 8LL),
                      LockingMode);
                  *(_BYTE *)(v5 + 105) = LockingMode;
                }
                v317 = sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(v453 + v13 + 8) + 8LL), LockingMode);
LABEL_471:
                v145 = "exclusive";
                if ( v317 != 1 )
                  v145 = "normal";
                goto LABEL_473;
              }
              v324 = 0;
              if ( !v15 )
                goto LABEL_485;
              v325 = sqlite3Strlen30(v15);
              v326 = 0;
              for ( i1 = v327; ; v326 = i1 )
              {
                v330 = sqlite3JournalModename(v326);
                if ( !v330 )
                  goto LABEL_485;
                v329 = sqlite3_strnicmp(v15, v330, v325);
                v324 = 0;
                if ( !v329 )
                  break;
                ++i1;
              }
              if ( i1 == 2 )
              {
                if ( (*(_DWORD *)(v5 + 48) & 0x10000000) != 0 )
                {
LABEL_485:
                  i1 = -1;
                  goto LABEL_486;
                }
              }
              else if ( i1 == -1 )
              {
LABEL_486:
                if ( *(_DWORD *)(v458 + 8) == (_DWORD)v324 )
                {
                  LODWORD(v12) = v324;
                  *(_DWORD *)(v458 + 8) = 1;
                }
              }
              v331 = *(_DWORD *)(v5 + 40) - 1;
              if ( v331 >= 0 )
              {
                v332 = v458;
                do
                {
                  if ( *(_QWORD *)(32LL * (unsigned int)v331 + *(_QWORD *)(v5 + 32) + 8) != v324
                    && (v331 == (_DWORD)v12 || *(_DWORD *)(v332 + 8) == (_DWORD)v324) )
                  {
                    sqlite3VdbeUsesBtree(v11, (unsigned int)v331);
                    sqlite3VdbeAddOp3(v333, 4, v331, 1, i1);
                    v324 = 0;
                  }
                  --v331;
                }
                while ( v331 >= 0 );
                v15 = v456;
              }
              v421 = v324;
              v314 = 1;
LABEL_497:
              v315 = 1;
              goto LABEL_463;
            }
            v335 = v26 - 30;
            if ( v335 )
            {
              v336 = v335 - 1;
              if ( v336 )
              {
                v337 = v336 - 1;
                if ( v337 )
                {
                  if ( v337 != 1 )
                    goto LABEL_593;
                  v338 = 0;
                  v339 = *(_QWORD *)(v453 + v13 + 8);
                  v340 = -1;
                  if ( v15 )
                  {
                    if ( (unsigned int)sqlite3_stricmp(v15, "fast") )
                      v340 = (unsigned __int8)sqlite3GetBoolean(v15, 0);
                    else
                      v340 = 2;
                  }
                  if ( !*(_DWORD *)(v458 + 8) && v340 >= 0 && *(int *)(v5 + 40) > 0 )
                  {
                    do
                      sqlite3BtreeSecureDelete(
                        *(_QWORD *)(32LL * v338++ + *(_QWORD *)(v5 + 32) + 8),
                        (unsigned int)v340);
                    while ( v338 < *(_DWORD *)(v5 + 40) );
                  }
                  v37 = sqlite3BtreeSecureDelete(v339, (unsigned int)v340);
                  goto LABEL_62;
                }
                for ( i2 = 0; i2 != 67; ++i2 )
                  sqlite3VdbeMultiLoad(v11, 1, "s", (&off_18009C420)[3 * i2], v418, v422, v426, v428, v429, v430);
                goto LABEL_683;
              }
              v342 = *(_QWORD *)(v453 + v13 + 8);
              if ( v15 )
              {
                v431 = 0;
                sqlite3GetInt32(v15, &v431);
                v344 = v431;
                *(_DWORD *)(v5 + 116) = v431;
                if ( (unsigned int)sqlite3BtreeSetPageSize(v342, v344, 0, 0) == 7 )
                  sqlite3OomFault(v5);
                goto LABEL_698;
              }
              if ( v342 )
                v343 = *(_DWORD *)(*(_QWORD *)(v342 + 8) + 52LL);
              else
                v343 = 0;
              v31 = v343;
LABEL_697:
              returnSingleInt(v11, v31);
              goto LABEL_698;
            }
            if ( v15 )
            {
              v431 = 0;
              sqlite3GetInt32(v15, &v431);
              IndexKey = v431;
              if ( (v431 & 2) == 0 )
                goto LABEL_698;
              v432 = 0;
              v345 = 0;
              LODWORD(v447) = 0;
              if ( (v431 & 0x10) == 0 )
              {
                v433 = 0;
                goto LABEL_536;
              }
            }
            else
            {
              v432 = 0;
              v345 = 0;
              IndexKey = 65534;
              LODWORD(v447) = 0;
            }
            v433 = (unsigned int)(*(_DWORD *)(v5 + 744) - 1) > 0x7CE ? 0x7D0 : 0;
LABEL_536:
            v437 = *((_DWORD *)v9 + 14);
            *((_DWORD *)v9 + 14) = v437 + 1;
            if ( v440 )
            {
              v346 = v12;
              v445 = v12;
            }
            else
            {
              v346 = *(_DWORD *)(v5 + 40) - 1;
              v445 = v346;
              if ( (int)v12 > v346 )
                goto LABEL_575;
            }
            do
            {
              if ( (_DWORD)v12 != 1 )
              {
                sqlite3CodeVerifySchema(v9, (unsigned int)v12);
                for ( i3 = *(const char ***)(*(_QWORD *)(32LL * (int)v12 + *(_QWORD *)(v5 + 32) + 24) + 16LL);
                      ;
                      i3 = (const char **)*i3 )
                {
                  v446 = i3;
                  if ( !i3 )
                    break;
                  v348 = (__int64)i3[2];
                  v435 = v348;
                  if ( !*(_BYTE *)(v348 + 63) )
                  {
                    v349 = *(_BYTE **)v348;
                    if ( !*(_QWORD *)v348 )
                      goto LABEL_551;
                    v350 = 7;
                    v351 = "sqlite_";
                    do
                    {
                      --v350;
                      if ( !*v349
                        || *((_BYTE *)qword_18009E760 + (unsigned __int8)*v349) != *((_BYTE *)qword_18009E760
                                                                                   + *(unsigned __int8 *)v351) )
                      {
                        goto LABEL_549;
                      }
                      ++v349;
                      ++v351;
                    }
                    while ( v350 > 0 );
                    --v350;
LABEL_549:
                    if ( v350 >= 0
                      && *((unsigned __int8 *)qword_18009E760 + (unsigned __int8)*v349) != *((unsigned __int8 *)qword_18009E760
                                                                                           + *(unsigned __int8 *)v351) )
                    {
LABEL_551:
                      v352 = *(_QWORD *)(v348 + 16);
                      v353 = 0;
                      v354 = *(unsigned __int16 *)(v348 + 58);
                      v443 = v354;
                      v431 = 0;
                      if ( v352 )
                      {
                        do
                        {
                          ++v353;
                          if ( *(char *)(v352 + 100) >= 0 )
                            v354 = -1;
                          v352 = *(_QWORD *)(v352 + 40);
                        }
                        while ( v352 );
                        v431 = v353;
                        v443 = v354;
                      }
                      if ( (*(_DWORD *)(v348 + 48) & 0x100) != 0
                        || (IndexKey & 0x10000) != 0
                        || *(_QWORD *)(v348 + 16) && (v354 & 0x8000u) != 0 )
                      {
                        if ( ++v432 == 2 )
                        {
                          sqlite3BeginWriteOperation(v9, 0, (unsigned int)v12);
                          LODWORD(v348) = v435;
                          v353 = v431;
                        }
                        LODWORD(v447) = v353 + (_DWORD)v447 + 1;
                        sqlite3OpenTable((_DWORD)v9, v437, v12, v348, 102);
                        if ( (v443 & 0x8000u) != 0 )
                        {
                          v431 = IndexKey & 1;
                          sqlite3VdbeAddOp3(v11, 36, v437, *(_DWORD *)(v11 + 144) + v431 + 2, 0);
                        }
                        else
                        {
                          if ( (__int16)v443 < 33 )
                            v355 = -1;
                          else
                            v355 = (__int16)v443 - 33;
                          v431 = IndexKey & 1;
                          sqlite3VdbeAddOp4Int(
                            v11,
                            33,
                            v437,
                            *(_DWORD *)(v11 + 144) + v431 + 2,
                            v355,
                            (__int16)v443 + 33);
                        }
                        v356 = sqlite3MPrintf(
                                 v5,
                                 "ANALYZE \"%w\".\"%w\"",
                                 *(_QWORD *)(32LL * (int)v12 + *(_QWORD *)(v5 + 32)),
                                 *(_QWORD *)v435);
                        if ( v431 )
                        {
                          TempReg = sqlite3GetTempReg(v9);
                          sqlite3VdbeAddOp4(v11, 118, 0, TempReg, v359, v358, -6);
                          sqlite3VdbeAddOp3(v11, 84, TempReg, 1, 0);
                        }
                        else
                        {
                          sqlite3VdbeAddOp4(v11, 148, v433 != 0 ? 2 : 0, v433, 0, v356, -6);
                        }
                      }
                    }
                    i3 = v446;
                  }
                }
                v346 = v445;
              }
              LODWORD(v12) = v12 + 1;
            }
            while ( (int)v12 <= v346 );
            v15 = v456;
            v345 = (int)v447;
LABEL_575:
            sqlite3VdbeAddOp3(v11, 166, 0, 0, 0);
            if ( !*(_BYTE *)(v5 + 103) )
            {
              if ( v433 )
              {
                if ( v345 > 100 )
                {
                  v360 = sqlite3VdbeGetOp(v11, 0);
                  v363 = *(_DWORD *)(v11 + 144);
                  if ( v363 > 0 )
                  {
                    do
                    {
                      if ( *(_BYTE *)(v360 + 24 * v361) == 0x94 )
                        *(_DWORD *)(v360 + 24 * v361 + 8) = v362;
                      v361 = (unsigned int)(v361 + 1);
                    }
                    while ( (int)v361 < v363 );
                  }
                }
              }
            }
            goto LABEL_698;
          }
          v364 = v26 - 35;
          if ( !v364 )
          {
            v435 = 0;
            if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
              sqlite3_soft_heap_limit64(v435);
            v98 = sqlite3_soft_heap_limit64(-1);
            goto LABEL_696;
          }
          v365 = v364 - 1;
          if ( v365 )
          {
            v366 = v365 - 1;
            if ( !v366 )
            {
              if ( !v15 )
                goto LABEL_698;
              sqlite3CodeVerifyNamedSchema(v9, v440);
              v397 = sqlite3LocateTable(v9, 2, v15, v440);
              v435 = v397;
              v398 = v397;
              if ( !v397 )
                goto LABEL_698;
              v442 = sqlite3PrimaryKeyIndex(v397);
              *((_DWORD *)v9 + 15) = 7;
              sqlite3ViewGetColumnNames(v9, v398);
              LOWORD(v399) = *(_WORD *)(v398 + 54);
              if ( (__int16)v399 <= 0 )
                goto LABEL_698;
              v400 = *(_QWORD *)(v398 + 8);
              v401 = 0;
              v402 = 0;
              v403 = v435;
              v432 = 0;
              v431 = 0;
              do
              {
                v404 = *(_WORD *)(v400 + 18);
                if ( (v404 & 0x62) == 0 || v441[2] )
                {
                  if ( (v404 & 1) != 0 )
                  {
                    v405 = 1;
                    if ( v442 && (__int16)v399 >= 1 )
                    {
                      do
                      {
                        if ( *(__int16 *)(*(_QWORD *)(v442 + 8) + 2LL * v405 - 2) == v402 )
                          break;
                        ++v405;
                      }
                      while ( v405 <= (__int16)v399 );
                    }
                  }
                  else
                  {
                    v405 = 0;
                  }
                  v406 = sqlite3ColumnExpr(v403);
                  if ( v408 < 2 && v406 )
                    v435 = *(_QWORD *)(v406 + 8);
                  else
                    v435 = v407;
                  v409 = sqlite3ColumnType(v400, qword_18009EEF0);
                  v413 = (unsigned int)(v412 - v432);
                  v414 = "issisii";
                  if ( !v441[2] )
                    v414 = "issisi";
                  sqlite3VdbeMultiLoad(v11, 1, v414, v413, *(_QWORD *)v400, v409, v410, v435, v405, v411);
                  v402 = v431;
                  v401 = v432;
                }
                else
                {
                  v432 = ++v401;
                }
                v399 = *(__int16 *)(v403 + 54);
                ++v402;
                v400 += 24;
                v431 = v402;
              }
              while ( v402 < v399 );
LABEL_682:
              v5 = v449;
              goto LABEL_683;
            }
            v367 = v366 - 1;
            if ( v367 )
            {
              v368 = v367 - 1;
              if ( !v368 )
              {
                if ( v15 )
                {
                  changeTempStorage(v9, (__int64)v15);
                  goto LABEL_698;
                }
                v31 = *(unsigned __int8 *)(v5 + 102);
                goto LABEL_697;
              }
              v369 = v368 - 1;
              if ( !v369 )
              {
                v376 = sqlite3MutexAlloc(11);
                sqlite3_mutex_enter(v376);
                if ( !v15 )
                {
                  v60 = sqlite3_temp_directory;
                  goto LABEL_617;
                }
                if ( !*v15
                  || (v378 = *(_QWORD *)v5,
                      v431 = 0,
                      !(*(unsigned int (__fastcall **)(__int64, char *, __int64, unsigned int *))(v378 + 56))(
                         v378,
                         v15,
                         1,
                         &v431))
                  && v431 )
                {
                  if ( *(_BYTE *)(v5 + 102) <= 1u )
                    invalidateTempStorage(v9, v377);
                  sqlite3_free(sqlite3_temp_directory);
                  if ( *v15 )
                    sqlite3_temp_directory = sqlite3_mprintf("%s", v15);
                  else
                    sqlite3_temp_directory = 0;
                  goto LABEL_622;
                }
LABEL_621:
                sqlite3ErrorMsg(v9, "not a writable directory");
                goto LABEL_622;
              }
              v370 = v369 - 1;
              if ( !v370 )
              {
                v435 = 0;
                if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
                  sqlite3_limit(v5, 11, v435 & 0x7FFFFFFF);
                v37 = sqlite3_limit(v5, 11, 0xFFFFFFFFLL);
                goto LABEL_62;
              }
              v371 = v370 - 1;
              if ( !v371 )
              {
                if ( v15 )
                {
                  v431 = 0;
                  sqlite3GetInt32(v15, &v431);
                  sqlite3_wal_autocheckpoint(v5, v431);
                }
                if ( *(__int64 (__fastcall **)())(v5 + 360) == sqlite3WalDefaultHook )
                  v37 = *(_DWORD *)(v5 + 368);
                else
                  v37 = 0;
                goto LABEL_62;
              }
              if ( v371 != 1 )
                goto LABEL_593;
              v372 = 12;
              if ( *(_QWORD *)v458 )
                v372 = v12;
              v373 = 0;
              LODWORD(v453) = v372;
              if ( v15 )
              {
                if ( (unsigned int)sqlite3StrICmp(v15, "full") )
                {
                  if ( (unsigned int)sqlite3StrICmp(v15, "restart") )
                  {
                    if ( !(unsigned int)sqlite3StrICmp(v15, "truncate") )
                      v373 = 3;
                  }
                  else
                  {
                    v373 = v374;
                  }
                }
                else
                {
                  v373 = 1;
                }
              }
              v375 = v453;
              *((_DWORD *)v9 + 15) = 3;
              sqlite3VdbeAddOp3(v11, 3, v375, v373, 1);
              v314 = 3;
              v421 = 0;
              goto LABEL_497;
            }
            v380 = v440;
            v381 = v440;
            *((_DWORD *)v9 + 15) = 6;
            sqlite3CodeVerifyNamedSchema(v9, v381);
            v382 = 0;
            v437 = 0;
            if ( *(int *)(v5 + 40) <= 0 )
              goto LABEL_698;
            while ( 1 )
            {
              v383 = v382;
              if ( v380 && (unsigned int)sqlite3_stricmp(v380, *(_QWORD *)(32LL * v382 + *(_QWORD *)(v5 + 32))) )
                goto LABEL_659;
              v384 = *(_QWORD *)(32 * v383 + *(_QWORD *)(v5 + 32) + 24);
              v385 = *(_DWORD *)(v384 + 12);
              v386 = v384 + 8;
              if ( v385 )
              {
                v387 = v437;
                do
                {
                  for ( i4 = *(_QWORD **)(v386 + 8); ; i4 = (_QWORD *)*i4 )
                  {
                    if ( !i4 )
                      goto LABEL_645;
                    v389 = i4[2];
                    if ( !*(_WORD *)(v389 + 54) )
                      break;
                  }
                  --v385;
                  v390 = sqlite3MPrintf(v5, "SELECT*FROM\"%w\"", *(_QWORD *)v389);
                  v442 = v390;
                  if ( v390 )
                  {
                    v435 = 0;
                    sqlite3LockAndPrepare(v5, v390, -1, 0, 0, (__int64)&v435, 0);
                    sqlite3_finalize(v435);
                    sqlite3DbFree(v5, v442);
                  }
                  if ( *(_BYTE *)(v5 + 103) )
                  {
                    sqlite3ErrorMsg(*(_QWORD *)(v5 + 352), "out of memory");
                    *(_DWORD *)(*(_QWORD *)(v5 + 352) + 24LL) = 7;
                  }
                  v386 = *(_QWORD *)(32 * v387 + *(_QWORD *)(v5 + 32) + 24) + 8LL;
                }
                while ( v385 );
LABEL_645:
                v15 = v456;
              }
              v391 = *(_QWORD *)(v386 + 8);
              v435 = v391;
              if ( v391 )
                break;
LABEL_659:
              v382 = v437 + 1;
              v437 = v382;
              if ( v382 >= *(_DWORD *)(v5 + 40) )
                goto LABEL_698;
            }
            while ( 1 )
            {
              v392 = *(_QWORD **)(v391 + 16);
              v442 = (__int64)v392;
              if ( !v15 )
                goto LABEL_650;
              if ( !(unsigned int)sqlite3_stricmp(v15, *v392) )
                break;
LABEL_657:
              v391 = *(_QWORD *)v435;
              v435 = v391;
              if ( !v391 )
              {
                v380 = v440;
                goto LABEL_659;
              }
            }
            v392 = (_QWORD *)v442;
LABEL_650:
            if ( *((_BYTE *)v392 + 63) == 2 )
            {
              v393 = "view";
            }
            else if ( *((_BYTE *)v392 + 63) == 1 )
            {
              v393 = "virtual";
            }
            else
            {
              v393 = "shadow";
              if ( (v392[6] & 0x1000) == 0 )
                v393 = "table";
            }
            v394 = *((_DWORD *)v392 + 12);
            v395 = *((__int16 *)v392 + 27);
            v442 = (__int64)v393;
            v396 = sqlite3PreferredTableName(*v392);
            LODWORD(v428) = (v394 >> 7) & 1;
            sqlite3VdbeMultiLoad(
              v11,
              1,
              "sssiii",
              *(_QWORD *)(32LL * v437 + *(_QWORD *)(v5 + 32)),
              v396,
              v442,
              v395,
              v428,
              HIWORD(v394) & 1,
              v430);
            goto LABEL_657;
          }
          if ( !v15 )
          {
            v31 = *(unsigned __int8 *)(v453 + v13 + 16) - 1LL;
            goto LABEL_697;
          }
          if ( !*(_BYTE *)(v5 + 101) )
          {
            sqlite3ErrorMsg(v9, "Safety level may not be changed inside a transaction");
            goto LABEL_698;
          }
          if ( (_DWORD)v12 != 1 )
          {
            LOBYTE(v24) = 1;
            SafetyLevel = getSafetyLevel(v15, 0, v24);
            v416 = v453;
            v417 = (SafetyLevel + 1) & 7;
            if ( !v417 )
              LOBYTE(v417) = 1;
            *(_BYTE *)(v453 + v13 + 16) = v417;
            *(_BYTE *)(v416 + v13 + 17) = 1;
            goto LABEL_86;
          }
LABEL_698:
          sqlite3DbFree(v5, v459);
          return sqlite3DbFree(v5, v15);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180050420  push    rbp
0x180050422  push    rbx
0x180050423  push    rsi
0x180050424  push    rdi
0x180050425  push    r12
0x180050427  push    r13
0x180050429  push    r14
0x18005042b  push    r15
0x18005042d  lea     rbp, [rsp-68h]
0x180050432  sub     rsp, 168h
0x180050439  mov     rax, cs:__security_cookie
0x180050440  xor     rax, rsp
0x180050443  mov     [rbp+0A0h+var_48], rax
0x180050447  mov     r12, [rcx]
0x18005044a  xorps   xmm0, xmm0
0x18005044d  mov     rbx, r8
0x180050450  mov     [rbp+0A0h+var_D8], r12
0x180050454  xor     r15d, r15d
0x180050457  mov     [rbp+0A0h+var_98], rbx
0x18005045b  mov     [rbp+0A0h+var_D0], r15
0x18005045f  mov     r13, r9
0x180050462  movups  [rbp+0A0h+var_68], xmm0
0x180050466  mov     [rsp+1A0h+var_130], r9
0x18005046b  mov     rsi, rdx
0x18005046e  movups  [rbp+0A0h+var_58], xmm0
0x180050472  mov     rdi, rcx
0x180050475  mov     [rbp+0A0h+var_88], rcx
0x180050479  call    sqlite3GetVdbe
0x18005047e  mov     [rbp+0A0h+var_108], rax
0x180050482  mov     r14, rax
0x180050485  test    rax, rax
0x180050488  jz      loc_180053D24
0x18005048e  mov     dword ptr [rsp+1A0h+var_180], r15d
0x180050493  mov     edx, 0A6h
0x180050498  mov     r15d, 1
0x18005049e  mov     rcx, rax
0x1800504a1  mov     r9d, r15d
0x1800504a4  mov     r8d, r15d
0x1800504a7  call    sqlite3VdbeAddOp3
0x1800504ac  lea     r9, [rbp+0A0h+var_D0]
0x1800504b0  mov     dword ptr [rdi+3Ch], 2
0x1800504b7  mov     r8, rbx
0x1800504ba  mov     rdx, rsi
0x1800504bd  mov     rcx, rdi
0x1800504c0  call    sqlite3TwoPartName
0x1800504c5  movsxd  rsi, eax
0x1800504c8  mov     [rbp+0A0h+var_F8], esi
0x1800504cb  test    eax, eax
0x1800504cd  js      loc_180053D24
0x1800504d3  mov     rax, [r12+20h]
0x1800504d8  mov     [rbp+0A0h+var_C0], rax
0x1800504dc  cmp     esi, r15d
0x1800504df  jnz     short loc_1800504F1
0x1800504e1  mov     rcx, rdi
0x1800504e4  call    sqlite3OpenTempDatabase
0x1800504e9  test    eax, eax
0x1800504eb  jnz     loc_180053D24
0x1800504f1  mov     rdx, [rbp+0A0h+var_D0]
0x1800504f5  mov     rcx, r12
0x1800504f8  call    sqlite3NameFromToken
0x1800504fd  mov     [rbp+0A0h+var_90], rax
0x180050501  test    rax, rax
0x180050504  jz      loc_180053D24
0x18005050a  mov     rbx, rsi
0x18005050d  mov     rcx, r12
0x180050510  shl     rbx, 5
0x180050514  cmp     [rbp+0A0h+arg_20], 0
0x18005051b  mov     [rbp+0A0h+var_B0], rbx
0x18005051f  jz      short loc_180050532
0x180050521  mov     r8, r13
0x180050524  lea     rdx, aT; "-%T"
0x18005052b  call    sqlite3MPrintf
0x180050530  jmp     short loc_18005053A
0x180050532  mov     rdx, r13
0x180050535  call    sqlite3NameFromToken
0x18005053a  mov     r13, rax
0x18005053d  mov     [rbp+0A0h+var_A8], rax
0x180050541  mov     rax, [rbp+0A0h+var_98]
0x180050545  xor     ecx, ecx
0x180050547  cmp     [rax+8], ecx
0x18005054a  jbe     short loc_180050556
0x18005054c  mov     rax, [rbp+0A0h+var_C0]
0x180050550  mov     rax, [rax+rbx]
0x180050554  jmp     short loc_180050559
0x180050556  mov     rax, rcx
0x180050559  mov     r8, [rbp+0A0h+var_90]
0x18005055d  mov     r9, r13
0x180050560  mov     edx, 13h
0x180050565  mov     [rbp+0A0h+var_118], rax
0x180050569  mov     rcx, rdi
0x18005056c  mov     [rsp+1A0h+var_180], rax
0x180050571  call    sqlite3AuthCheck
0x180050576  xor     ecx, ecx
0x180050578  test    eax, eax
0x18005057a  jnz     loc_180053D0D
0x180050580  mov     rax, [rbp+0A0h+var_90]
0x180050584  mov     qword ptr [rbp+0A0h+var_68], rcx
0x180050588  mov     qword ptr [rbp+0A0h+var_58+8], rcx
0x18005058c  mov     qword ptr [rbp+0A0h+var_68+8], rax
0x180050590  mov     qword ptr [rbp+0A0h+var_58], r13
0x180050594  mov     [r12+298h], ecx
0x18005059c  mov     rcx, r12
0x18005059f  call    sqlite3SafetyCheckOk
0x1800505a4  test    eax, eax
0x1800505a6  jnz     short loc_1800505C2
0x1800505a8  lea     r8, aMisuse; "misuse"
0x1800505af  mov     edx, 2D34Dh
0x1800505b4  lea     ecx, [rax+15h]
0x1800505b7  call    sqlite3ReportError
0x1800505bc  mov     [rsp+1A0h+var_138], eax
0x1800505c0  jmp     short loc_18005063A
0x1800505c2  mov     rcx, [r12+18h]
0x1800505c7  mov     [rsp+1A0h+var_138], r15d
0x1800505cc  call    sqlite3_mutex_enter
0x1800505d1  mov     rdx, [rbp+0A0h+var_118]
0x1800505d5  mov     rcx, r12
0x1800505d8  call    sqlite3DbNameToBtree
0x1800505dd  mov     [rbp+0A0h+var_D0], rax
0x1800505e1  test    rax, rax
0x1800505e4  jz      short loc_18005062C
0x1800505e6  mov     rcx, rax
0x1800505e9  call    sqlite3BtreeEnter
0x1800505ee  mov     rax, [rbp+0A0h+var_D0]
0x1800505f2  lea     r8, [rbp+0A0h+var_68]
0x1800505f6  mov     ebx, [r12+298h]
0x1800505fe  mov     rcx, [rax+8]
0x180050602  mov     rdx, [rcx]
0x180050605  mov     rcx, [rdx+48h]
0x180050609  mov     edx, 0Eh
0x18005060e  call    sqlite3OsFileControl
0x180050613  mov     rcx, [rbp+0A0h+var_D0]
0x180050617  mov     [rsp+1A0h+var_138], eax
0x18005061b  mov     [r12+298h], ebx
0x180050623  call    sqlite3BtreeLeave
0x180050628  mov     rbx, [rbp+0A0h+var_B0]
0x18005062c  mov     rcx, [r12+18h]
0x180050631  call    sqlite3_mutex_leave
0x180050636  mov     eax, [rsp+1A0h+var_138]
0x18005063a  test    eax, eax
0x18005063c  jnz     short loc_18005067D
0x18005063e  mov     edx, r15d
0x180050641  mov     rcx, r14
0x180050644  call    sqlite3VdbeSetNumCols
0x180050649  mov     r9, qword ptr [rbp+0A0h+var_68]
0x18005064d  xor     r8d, r8d
0x180050650  xor     edx, edx
0x180050652  mov     [rsp+1A0h+var_180], 0FFFFFFFFFFFFFFFFh
0x18005065b  mov     rcx, r14
0x18005065e  call    sqlite3VdbeSetColName
0x180050663  mov     rdx, qword ptr [rbp+0A0h+var_68]
0x180050667  mov     rcx, r14
0x18005066a  call    returnSingleText
0x18005066f  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x180050673  call    sqlite3_free
0x180050678  jmp     loc_180053D0D
0x18005067d  cmp     eax, 0Ch
0x180050680  jz      short loc_1800506B3
0x180050682  mov     r8, qword ptr [rbp+0A0h+var_68]
0x180050686  test    r8, r8
0x180050689  jz      short loc_1800506A7
0x18005068b  lea     rdx, aS_7; "%s"
0x180050692  mov     rcx, rdi
0x180050695  call    sqlite3ErrorMsg
0x18005069a  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x18005069e  call    sqlite3_free
0x1800506a3  mov     eax, [rsp+1A0h+var_138]
0x1800506a7  add     [rdi+34h], r15d
0x1800506ab  mov     [rdi+18h], eax
0x1800506ae  jmp     loc_180053D0D
0x1800506b3  mov     rcx, [rbp+0A0h+var_90]
0x1800506b7  call    pragmaLocate
0x1800506bc  mov     [rbp+0A0h+var_110], rax
0x1800506c0  mov     r10, rax
0x1800506c3  test    rax, rax
0x1800506c6  jz      loc_180053D0D
0x1800506cc  test    [rax+9], r15b
0x1800506d0  jz      short loc_1800506E6
0x1800506d2  mov     rcx, rdi
0x1800506d5  call    sqlite3ReadSchema
0x1800506da  test    eax, eax
0x1800506dc  jnz     loc_180053D0D
0x1800506e2  mov     r10, [rbp+0A0h+var_110]
0x1800506e6  mov     r11d, 2
0x1800506ec  test    [r10+9], r11b
0x1800506f0  jnz     short loc_180050713
0x1800506f2  test    byte ptr [r10+9], 4
0x1800506f7  jz      short loc_1800506FE
0x1800506f9  test    r13, r13
0x1800506fc  jnz     short loc_180050713
0x1800506fe  mov     rdx, r10
0x180050701  mov     rcx, r14
0x180050704  call    setPragmaResultColumnNames
0x180050709  mov     r10, [rbp+0A0h+var_110]
0x18005070d  mov     r11d, 2
0x180050713  movzx   ecx, byte ptr [r10+8]
0x180050718  cmp     ecx, 16h
0x18005071b  ja      loc_180052C3C
0x180050721  jz      loc_18005175F
0x180050727  mov     eax, 0Ch
0x18005072c  cmp     ecx, eax
0x18005072e  ja      loc_180050C4F
0x180050734  jz      loc_180050BE3
0x18005073a  cmp     ecx, 7
0x18005073d  ja      loc_180050A68
0x180050743  jz      loc_1800509DE
0x180050749  sub     ecx, r15d
0x18005074c  jz      loc_18005099E
0x180050752  sub     ecx, r15d
0x180050755  jz      loc_1800508FF
0x18005075b  sub     ecx, r15d
0x18005075e  jz      loc_180050877
0x180050764  sub     ecx, r15d
0x180050767  jz      short loc_1800507BB
0x180050769  cmp     ecx, r11d
0x18005076c  jnz     loc_180053638
0x180050772  xor     eax, eax
0x180050774  test    r13, r13
0x180050777  jnz     short loc_18005078B
0x180050779  mov     rax, [rbp+0A0h+var_C0]
0x18005077d  mov     rax, [rax+rbx+18h]
0x180050782  movsxd  rdx, dword ptr [rax+74h]
0x180050786  jmp     loc_180053D05
0x18005078b  lea     rdx, [rsp+1A0h+var_13C]
0x180050790  mov     [rsp+1A0h+var_13C], eax
0x180050794  mov     rcx, r13
0x180050797  call    sqlite3GetInt32
0x18005079c  mov     r8, [rbp+0A0h+var_C0]
0x1800507a0  mov     eax, [rsp+1A0h+var_13C]
0x1800507a4  mov     rcx, [r8+rbx+18h]
0x1800507a9  mov     [rcx+74h], eax
0x1800507ac  mov     rdx, [r8+rbx+18h]
0x1800507b1  mov     rcx, [r8+rbx+8]
0x1800507b6  jmp     loc_180051752
0x1800507bb  xor     edi, edi
0x1800507bd  test    r13, r13
0x1800507c0  jnz     short loc_1800507E4
0x1800507c2  mov     rdx, r10
0x1800507c5  mov     rcx, r14
0x1800507c8  call    setPragmaResultColumnNames
0x1800507cd  mov     rbx, [rbp+0A0h+var_110]
0x1800507d1  mov     edx, edi
0x1800507d3  mov     rax, [r12+30h]
0x1800507d8  test    [rbx+10h], rax
0x1800507dc  setnz   dl
0x1800507df  jmp     loc_180053D05
0x1800507e4  mov     rbx, [r10+10h]
0x1800507e8  mov     rcx, r13
0x1800507eb  btr     rbx, 0Eh
0x1800507f0  cmp     [r12+65h], dil
0x1800507f5  cmovnz  rbx, [r10+10h]
0x1800507fa  xor     edx, edx
0x1800507fc  call    sqlite3GetBoolean
0x180050801  test    al, al
0x180050803  jz      short loc_18005081D
0x180050805  test    r15b, bl
0x180050808  jz      short loc_180050816
0x18005080a  mov     eax, [r12+30h]
0x18005080f  bt      rax, 1Ch
0x180050814  jb      short loc_18005085B
0x180050816  or      [r12+30h], rbx
0x18005081b  jmp     short loc_18005085B
0x18005081d  mov     rax, rbx
0x180050820  not     rax
0x180050823  and     [r12+30h], rax
0x180050828  cmp     rbx, 80000h
0x18005082f  jnz     short loc_18005083B
0x180050831  mov     [r12+300h], rdi
0x180050839  jmp     short loc_18005085B
0x18005083b  test    r15b, bl
0x18005083e  jz      short loc_18005085B
0x180050840  lea     rdx, aReset; "reset"
0x180050847  mov     rcx, r13
0x18005084a  call    sqlite3_stricmp
0x18005084f  test    eax, eax
0x180050851  jnz     short loc_18005085B
0x180050853  mov     rcx, r12
0x180050856  call    sqlite3ResetAllSchemasOfConnection
0x18005085b  xor     r9d, r9d
0x18005085e  mov     dword ptr [rsp+1A0h+var_180], edi
0x180050862  xor     r8d, r8d
0x180050865  mov     edx, 0A6h
0x18005086a  mov     rcx, r14
0x18005086d  call    sqlite3VdbeAddOp3
0x180050872  jmp     loc_180050A5B
0x180050877  mov     rax, [rbp+0A0h+var_C0]
0x18005087b  mov     rbx, [rax+rbx+8]
0x180050880  test    r13, r13
0x180050883  jnz     short loc_180050895
0x180050885  mov     rcx, rbx
0x180050888  call    sqlite3BtreeGetAutoVacuum
0x18005088d  movsxd  rdx, eax
0x180050890  jmp     loc_180053D05
0x180050895  mov     rcx, r13
0x180050898  call    getAutoVacuum
0x18005089d  mov     edi, eax
0x18005089f  mov     edx, eax
0x1800508a1  mov     rcx, rbx
0x1800508a4  mov     [r12+6Ah], dil
0x1800508a9  call    sqlite3BtreeSetAutoVacuum
0x1800508ae  test    eax, eax
  ... truncated ...
```
